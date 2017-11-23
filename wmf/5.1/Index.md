---
ms.date: 2017-08-12
author: JKeithB
ms.topic: reference
keywords: wmf,powershell,setup
title: "Poznámky k verzi WMF 5.1"
ms.openlocfilehash: 3a6b7fb84d679d9bbe7a89e30c8c769e26f7381a
ms.sourcegitcommit: 4102ecc35d473211f50a453f6ae3fbea31cb3428
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2017
---
# <a name="windows-management-framework-wmf-51"></a><span data-ttu-id="e5f90-103">Windows Management Framework (WMF) 5.1</span><span class="sxs-lookup"><span data-stu-id="e5f90-103">Windows Management Framework (WMF) 5.1</span></span> #

<span data-ttu-id="e5f90-104">WMF umožňuje uživatelům aktualizovat ve stávajících systémech Windows verze komponent PowerShell, WMI, WinRM a Protokolování softwarového inventáře (SIL), které byly vydané ve Windows Serveru 2016.</span><span class="sxs-lookup"><span data-stu-id="e5f90-104">WMF provides users with the ability to update existing Windows systems to the versions of PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span> 

<span data-ttu-id="e5f90-105">WMF 5.1 můžete instalovat na Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 a 2012 R2. Verze WMF 5.1 nabízí oproti WMF 5.0 RTM celou řadu vylepšení. Například:</span><span class="sxs-lookup"><span data-stu-id="e5f90-105">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides a number of improvements over WMF 5.0 RTM including:</span></span>

- <span data-ttu-id="e5f90-106">Nové rutiny pro místní uživatelé a skupiny, Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="e5f90-106">New cmdlets: local users and groups; Get-ComputerInfo</span></span>
- <span data-ttu-id="e5f90-107">Vylepšení PowerShellGet zahrnuje vynucení podepsaných modulů a instalaci modulů JEA</span><span class="sxs-lookup"><span data-stu-id="e5f90-107">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="e5f90-108">Přidaná podpora funkce PackageManagement pro kontejnery, nastavení CBS, nastavení založené na souboru EXE a balíčky CAB</span><span class="sxs-lookup"><span data-stu-id="e5f90-108">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="e5f90-109">Vylepšené ladění pro třídy DSC a PowerShellu</span><span class="sxs-lookup"><span data-stu-id="e5f90-109">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="e5f90-110">Vylepšené zabezpečení, včetně vynucení modulů podepsaných v katalogu, které pocházejí ze serveru vyžádané replikace při používání rutin PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e5f90-110">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="e5f90-111">Odpovědi na celou řadu požadavků a problémů uživatelů</span><span class="sxs-lookup"><span data-stu-id="e5f90-111">Responses to a number of user requests and issues</span></span>

<span data-ttu-id="e5f90-112">Další informace o novinkách této verze najdete v tématech, kterými se zabývá článek [Nové scénáře a funkce](https://docs.microsoft.com/en-us/powershell/wmf/5.1/scenarios-features).</span><span class="sxs-lookup"><span data-stu-id="e5f90-112">To learn about what is new in this release, browse the topics listed under [New Scenarios and Features](https://docs.microsoft.com/en-us/powershell/wmf/5.1/scenarios-features).</span></span> 

<span data-ttu-id="e5f90-113">V tématu [Instalace a konfigurace](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure) je seznam požadavků a pokyny k instalaci WMF.</span><span class="sxs-lookup"><span data-stu-id="e5f90-113">The [Install and Configure](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure) topic lists the requirements and provides installation instructions for WMF.</span></span> 

<span data-ttu-id="e5f90-114">V tématu [Kompatibilita](https://docs.microsoft.com/en-us/powershell/wmf/5.1/compatibility) je seznam verzí WMF, které je možné nainstalovat do určité verze Windows.</span><span class="sxs-lookup"><span data-stu-id="e5f90-114">The [Compatibility](https://docs.microsoft.com/en-us/powershell/wmf/5.1/compatibility) topic lists which versions of WMF may be installed on which Windows releases.</span></span> 

<span data-ttu-id="e5f90-115">Téma [Kompatibilita produktu](https://docs.microsoft.com/en-us/powershell/wmf/5.1/productincompat) obsahuje seznam aplikací Microsoftu, které v této chvíli neschválily používání WMF 5.1.</span><span class="sxs-lookup"><span data-stu-id="e5f90-115">[Product Compatibility](https://docs.microsoft.com/en-us/powershell/wmf/5.1/productincompat) lists the Microsoft applications that have not approved WMF 5.1 for use at this time.</span></span> 

<span data-ttu-id="e5f90-116">Podrobnosti o komponentách WMF najdete v dokumentaci MSDN:</span><span class="sxs-lookup"><span data-stu-id="e5f90-116">Details for the components of WMF will be found in MSDN documentation:</span></span>

- [<span data-ttu-id="e5f90-117">PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="e5f90-117">PowerShell 5.1</span></span>](https://docs.microsoft.com/en-us/powershell/) 
- <span data-ttu-id="e5f90-118">[WMI](https://msdn.microsoft.com/en-us/library/jj152383(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="e5f90-118">[WMI](https://msdn.microsoft.com/en-us/library/jj152383(v=vs.85).aspx)</span></span>
- <span data-ttu-id="e5f90-119">[WinRM](https://msdn.microsoft.com/en-us/library/aa384426(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="e5f90-119">[WinRM](https://msdn.microsoft.com/en-us/library/aa384426(v=vs.85).aspx)</span></span>
- <span data-ttu-id="e5f90-120">[Protokolování inventáře softwaru](https://technet.microsoft.com/en-us/library/dn383584(v=ws.11).aspx)</span><span class="sxs-lookup"><span data-stu-id="e5f90-120">[Software Inventory Logging](https://technet.microsoft.com/en-us/library/dn383584(v=ws.11).aspx)</span></span>
