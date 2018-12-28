---
title: Vzdálená komunikace WSMan (WS-Management) v PowerShellu Core
description: Vzdálená komunikace v prostředí PowerShell Core pomocí WSMan
ms.date: 08/06/2018
ms.openlocfilehash: ce58ed88f59f32b0f83951e55de36e829f7fa3f4
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404099"
---
# <a name="ws-management-wsman-remoting-in-powershell-core"></a><span data-ttu-id="9008a-103">Vzdálená komunikace WSMan (WS-Management) v PowerShellu Core</span><span class="sxs-lookup"><span data-stu-id="9008a-103">WS-Management (WSMan) Remoting in PowerShell Core</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="9008a-104">Pokyny k vytvoření koncového bodu vzdálené komunikace</span><span class="sxs-lookup"><span data-stu-id="9008a-104">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="9008a-105">Balíček PowerShell Core pro Windows zahrnuje modul plug-in WinRM (`pwrshplugin.dll`) a instalační skript (`Install-PowerShellRemoting.ps1`) v `$PSHome`.</span><span class="sxs-lookup"><span data-stu-id="9008a-105">The PowerShell Core package for Windows includes a WinRM plug-in (`pwrshplugin.dll`) and an installation script (`Install-PowerShellRemoting.ps1`) in `$PSHome`.</span></span>
<span data-ttu-id="9008a-106">Tyto soubory prostředí PowerShell tak, aby přijímal příchozí připojení vzdáleného prostředí PowerShell, když svůj koncový bod je zadán povolit.</span><span class="sxs-lookup"><span data-stu-id="9008a-106">These files enable PowerShell to accept incoming PowerShell remote connections when its endpoint is specified.</span></span>

### <a name="motivation"></a><span data-ttu-id="9008a-107">Motivace</span><span class="sxs-lookup"><span data-stu-id="9008a-107">Motivation</span></span>

<span data-ttu-id="9008a-108">Instalace powershellu mohou vytvořit relace prostředí PowerShell na vzdálených počítačích pomocí `New-PSSession` a `Enter-PSSession`.</span><span class="sxs-lookup"><span data-stu-id="9008a-108">An installation of PowerShell can establish PowerShell sessions to remote computers using `New-PSSession` and `Enter-PSSession`.</span></span>
<span data-ttu-id="9008a-109">Který umožňuje přijímat příchozí připojení vzdáleného prostředí PowerShell, musí uživatel vytvořit koncový bod vzdálené komunikace služby WinRM.</span><span class="sxs-lookup"><span data-stu-id="9008a-109">To enable it to accept incoming PowerShell remote connections, the user must create a WinRM remoting endpoint.</span></span>
<span data-ttu-id="9008a-110">Jedná se o explicitní vyjádřit výslovný souhlas scénář Pokud uživatel spustí instalaci PowerShellRemoting.ps1 vytvořte koncový bod služby WinRM.</span><span class="sxs-lookup"><span data-stu-id="9008a-110">This is an explicit opt-in scenario where the user runs Install-PowerShellRemoting.ps1 to create the WinRM endpoint.</span></span>
<span data-ttu-id="9008a-111">Instalační skript je krátkodobé řešení, dokud přidáme další funkce k `Enable-PSRemoting` provést stejnou akci.</span><span class="sxs-lookup"><span data-stu-id="9008a-111">The installation script is a short-term solution until we add additional functionality to `Enable-PSRemoting` to perform the same action.</span></span>
<span data-ttu-id="9008a-112">Další podrobnosti najdete v tématu problém [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span><span class="sxs-lookup"><span data-stu-id="9008a-112">For more details, please see issue [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span></span>

### <a name="script-actions"></a><span data-ttu-id="9008a-113">Akce skriptů</span><span class="sxs-lookup"><span data-stu-id="9008a-113">Script Actions</span></span>

<span data-ttu-id="9008a-114">Skript</span><span class="sxs-lookup"><span data-stu-id="9008a-114">The script</span></span>

1. <span data-ttu-id="9008a-115">Vytvoří adresář pro modul plug-in v rámci %windir%\System32\PowerShell</span><span class="sxs-lookup"><span data-stu-id="9008a-115">Creates a directory for the plug-in within %windir%\System32\PowerShell</span></span>
1. <span data-ttu-id="9008a-116">Zkopíruje pwrshplugin.dll do tohoto umístění</span><span class="sxs-lookup"><span data-stu-id="9008a-116">Copies pwrshplugin.dll to that location</span></span>
1. <span data-ttu-id="9008a-117">Generuje konfigurační soubor</span><span class="sxs-lookup"><span data-stu-id="9008a-117">Generates a configuration file</span></span>
1. <span data-ttu-id="9008a-118">Registry to modulu plug-in pomocí WinRM</span><span class="sxs-lookup"><span data-stu-id="9008a-118">Registers that plug-in with WinRM</span></span>

### <a name="registration"></a><span data-ttu-id="9008a-119">Registrace</span><span class="sxs-lookup"><span data-stu-id="9008a-119">Registration</span></span>

<span data-ttu-id="9008a-120">Skript je třeba spustit v relaci prostředí PowerShell na úrovni správce a běží ve dvou režimech.</span><span class="sxs-lookup"><span data-stu-id="9008a-120">The script must be executed within an Administrator-level PowerShell session and runs in two modes.</span></span>

#### <a name="executed-by-the-instance-of-powershell-that-it-will-register"></a><span data-ttu-id="9008a-121">Spuštění instance prostředí PowerShell, které se budou registrovat</span><span class="sxs-lookup"><span data-stu-id="9008a-121">Executed by the instance of PowerShell that it will register</span></span>

```powershell
Install-PowerShellRemoting.ps1
```

#### <a name="executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register"></a><span data-ttu-id="9008a-122">Spustit jiná instance prostředí PowerShell jménem instanci, která k registraci</span><span class="sxs-lookup"><span data-stu-id="9008a-122">Executed by another instance of PowerShell on behalf of the instance that it will register</span></span>

```powershell
<path to powershell>\Install-PowerShellRemoting.ps1 -PowerShellHome "<absolute path to the instance's $PSHOME>"
```

<span data-ttu-id="9008a-123">Příklad:</span><span class="sxs-lookup"><span data-stu-id="9008a-123">For Example:</span></span>

```powershell
Set-Location -Path 'C:\Program Files\PowerShell\6.0.0\'
.\Install-PowerShellRemoting.ps1 -PowerShellHome "C:\Program Files\PowerShell\6.0.0\"
```

<span data-ttu-id="9008a-124">**POZNÁMKA:** Vzdálená komunikace registrační skript restartuje WinRM, tak všechny existující PSRP relace bude ukončena ihned po spuštění skriptu.</span><span class="sxs-lookup"><span data-stu-id="9008a-124">**NOTE:** The remoting registration script will restart WinRM, so all existing PSRP sessions will terminate immediately after the script is run.</span></span> <span data-ttu-id="9008a-125">Pokud během vzdálené relace, to se ukončí připojení.</span><span class="sxs-lookup"><span data-stu-id="9008a-125">If run during a remote session, this will terminate the connection.</span></span>

## <a name="how-to-connect-to-the-new-endpoint"></a><span data-ttu-id="9008a-126">Jak se připojit k nový koncový bod</span><span class="sxs-lookup"><span data-stu-id="9008a-126">How to Connect to the New Endpoint</span></span>

<span data-ttu-id="9008a-127">Vytvořit relaci Powershellu se nový koncový bod prostředí PowerShell zadáním `-ConfigurationName "some endpoint name"`.</span><span class="sxs-lookup"><span data-stu-id="9008a-127">Create a PowerShell session to the new PowerShell endpoint by specifying `-ConfigurationName "some endpoint name"`.</span></span> <span data-ttu-id="9008a-128">Pokud chcete připojit k instanci prostředí PowerShell jako v předchozím příkladu, použijte buď:</span><span class="sxs-lookup"><span data-stu-id="9008a-128">To connect to the PowerShell instance from the example above, use either:</span></span>

```powershell
New-PSSession ... -ConfigurationName "powershell.6.0.0"
Enter-PSSession ... -ConfigurationName "powershell.6.0.0"
```

<span data-ttu-id="9008a-129">Všimněte si, že `New-PSSession` a `Enter-PSSession` volání, které neurčují `-ConfigurationName` se zaměří na výchozí koncový bod prostředí PowerShell, `microsoft.powershell`.</span><span class="sxs-lookup"><span data-stu-id="9008a-129">Note that `New-PSSession` and `Enter-PSSession` invocations that do not specify `-ConfigurationName` will target the default PowerShell endpoint, `microsoft.powershell`.</span></span>