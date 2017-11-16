---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, prostředí powershell, instalační program"
title: "Nové scénáře a funkce v WMF 5.1"
ms.openlocfilehash: 430781c5c9a59fc544db4f94098313ae1e9cf610
ms.sourcegitcommit: a6ee6e64d369ecf82c730411bed9750278fdb5c1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/18/2017
---
# <a name="new-scenarios-and-features-in-wmf-51"></a><span data-ttu-id="51c3c-103">Nové scénáře a funkce v WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="51c3c-103">New Scenarios and Features in WMF 5.1</span></span> #

> <span data-ttu-id="51c3c-104">Poznámka: Tyto informace jsou předběžné a může se změnit.</span><span class="sxs-lookup"><span data-stu-id="51c3c-104">Note: This information is preliminary and subject to change.</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="51c3c-105">Edice PowerShellu</span><span class="sxs-lookup"><span data-stu-id="51c3c-105">PowerShell Editions</span></span> ##
<span data-ttu-id="51c3c-106">Od verze 5.1 je PowerShell k dispozici v různých edicích, které uvádějí různé sady funkcí a kompatibilitu platformy.</span><span class="sxs-lookup"><span data-stu-id="51c3c-106">Starting with version 5.1, PowerShell is available in different editions which denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="51c3c-107">**Desktop Edition:** Tato edice je založená na rozhraní .NET Framework a zajišťuje kompatibilitu se skripty a moduly cílenými na verze PowerShellu spouštěné na plných edicích Windows, jako je Jádro serveru a Windows Desktop.</span><span class="sxs-lookup"><span data-stu-id="51c3c-107">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="51c3c-108">**Core Edition:** Tato edice je založená na rozhraní .NET Core a zajišťuje kompatibilitu se skripty a moduly cílenými na verze PowerShellu spouštěné na edicích Windows s nízkými nároky na prostředky, jako je Nano Server a Windows IoT.</span><span class="sxs-lookup"><span data-stu-id="51c3c-108">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

<span data-ttu-id="51c3c-109">**Další informace o používání prostředí PowerShell edice**</span><span class="sxs-lookup"><span data-stu-id="51c3c-109">**Learn more about using PowerShell Editions**</span></span>
- [<span data-ttu-id="51c3c-110">Určení spuštěné ve verzi prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c3c-110">Determine running edition of PowerShell</span></span>]()
- [<span data-ttu-id="51c3c-111">Deklarace modul kompatibility na konkrétní verze prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c3c-111">Declare a module's compatibility to specific PowerShell versions</span></span>]()
- [<span data-ttu-id="51c3c-112">Filtrování výsledků Get-Module podle CompatiblePSEditions</span><span class="sxs-lookup"><span data-stu-id="51c3c-112">Filter Get-Module results by CompatiblePSEditions</span></span>]()
- [<span data-ttu-id="51c3c-113">Zabránit spuštění skriptu, není-li spustit na kompatibilní verzi prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="51c3c-113">Prevent script execution unless run on a compatible edition of PowerShell</span></span>]()

## <a name="catalog-cmdlets"></a><span data-ttu-id="51c3c-114">Rutiny katalogu</span><span class="sxs-lookup"><span data-stu-id="51c3c-114">Catalog Cmdlets</span></span>  

<span data-ttu-id="51c3c-115">Byly přidány dva nové rutiny v [Microsoft.PowerShell.Security](https://technet.microsoft.com/en-us/library/hh847877.aspx) modulu; tato generovat a ověření souborů katalogu systému Windows.</span><span class="sxs-lookup"><span data-stu-id="51c3c-115">Two new cmdlets have been added in the [Microsoft.PowerShell.Security](https://technet.microsoft.com/en-us/library/hh847877.aspx) module; these generate and validate Windows catalog files.</span></span>  

###<a name="new-filecatalog"></a><span data-ttu-id="51c3c-116">Nové FileCatalog</span><span class="sxs-lookup"><span data-stu-id="51c3c-116">New-FileCatalog</span></span> 
--------------------------------

<span data-ttu-id="51c3c-117">Nové FileCatalog vytvoří soubor katalogu systému Windows pro sadu složek a souborů.</span><span class="sxs-lookup"><span data-stu-id="51c3c-117">New-FileCatalog creates a Windows catalog file for set of folders and files.</span></span> <span data-ttu-id="51c3c-118">Tento soubor katalogu obsahuje hodnoty hash pro všechny soubory v zadané cesty.</span><span class="sxs-lookup"><span data-stu-id="51c3c-118">This catalog file contains hashes for all files in specified paths.</span></span> <span data-ttu-id="51c3c-119">Uživatele můžete distribuovat sadu složek spolu s odpovídající soubor katalogu představující těchto složek.</span><span class="sxs-lookup"><span data-stu-id="51c3c-119">Users can distribute the set of folders along with corresponding catalog file representing those folders.</span></span> <span data-ttu-id="51c3c-120">Tyto informace jsou užitečné pro ověření, zda byly provedeny změny do složek od okamžiku vytvoření katalogu.</span><span class="sxs-lookup"><span data-stu-id="51c3c-120">This information is useful to validate whether any changes have been made to the folders since catalog creation time.</span></span>    

```powershell
New-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-CatalogVersion <int>] [-WhatIf] [-Confirm] [<CommonParameters>]
```
<span data-ttu-id="51c3c-121">Jsou podporovány katalogu verze 1 a 2.</span><span class="sxs-lookup"><span data-stu-id="51c3c-121">Catalog versions 1 and 2 are supported.</span></span> <span data-ttu-id="51c3c-122">Verze 1 používá algoritmus hash SHA1 k vytvoření hodnoty hash souboru; verze 2 používá algoritmus SHA256.</span><span class="sxs-lookup"><span data-stu-id="51c3c-122">Version 1 uses the SHA1 hashing algorithm to create file hashes; version 2 uses SHA256.</span></span> <span data-ttu-id="51c3c-123">Katalog verze 2 není podporována na *Windows Server 2008 R2* nebo *Windows 7*.</span><span class="sxs-lookup"><span data-stu-id="51c3c-123">Catalog version 2 is not supported on *Windows Server 2008 R2* or *Windows 7*.</span></span> <span data-ttu-id="51c3c-124">Měli byste použít katalogu verze 2 v *Windows 8*, *systému Windows Server 2012*a novějších operačních systémech.</span><span class="sxs-lookup"><span data-stu-id="51c3c-124">You should use catalog version 2 on *Windows 8*, *Windows Server 2012*, and later operating systems.</span></span>  

![](../images/NewFileCatalog.jpg)

<span data-ttu-id="51c3c-125">Tím se vytvoří soubor katalogu.</span><span class="sxs-lookup"><span data-stu-id="51c3c-125">This creates the catalog file.</span></span> 

![](../images/CatalogFile1.jpg)  

![](../images/CatalogFile2.jpg) 

<span data-ttu-id="51c3c-126">Chcete-li ověřit integritu soubor katalogu (Pester.cat v výše příkladu), podepište ho pomocí [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) rutiny.</span><span class="sxs-lookup"><span data-stu-id="51c3c-126">To verify the integrity of catalog file (Pester.cat in above example), sign it using [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) cmdlet.</span></span>   


###<a name="test-filecatalog"></a><span data-ttu-id="51c3c-127">Test FileCatalog</span><span class="sxs-lookup"><span data-stu-id="51c3c-127">Test-FileCatalog</span></span> 
--------------------------------

<span data-ttu-id="51c3c-128">Test FileCatalog ověří katalogu představující sadu složek.</span><span class="sxs-lookup"><span data-stu-id="51c3c-128">Test-FileCatalog validates the catalog representing a set of folders.</span></span> 

```powershell
Test-FileCatalog [-CatalogFilePath] <string> [[-Path] <string[]>] [-Detailed] [-FilesToSkip <string[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

![](../images/TestFileCatalog.jpg)

<span data-ttu-id="51c3c-129">Tato rutina porovná všechny hodnoty hash souborů a jejich relativní cesty v *katalogu* s těch, které jsou na *disku*.</span><span class="sxs-lookup"><span data-stu-id="51c3c-129">This cmdlet compares all the files hashes and their relative paths found in *catalog* with ones on *disk*.</span></span> <span data-ttu-id="51c3c-130">Pokud zjistí jakékoli neshody mezi hodnoty hash souboru a cesty vrátí stav jako *ValidationFailed*.</span><span class="sxs-lookup"><span data-stu-id="51c3c-130">If it detects any mismatch between file hashes and paths it returns the status as *ValidationFailed*.</span></span> <span data-ttu-id="51c3c-131">Uživatele můžete načíst pomocí těchto informací *-podrobné* parametr.</span><span class="sxs-lookup"><span data-stu-id="51c3c-131">Users can retrieve all this information by using the *-Detailed* parameter.</span></span> <span data-ttu-id="51c3c-132">Také se zobrazí stav podpisový katalogu v *podpis* vlastnost, která je ekvivalentní volání [Get-AuthenticodeSignature](https://technet.microsoft.com/en-us/library/hh849805.aspx) na soubor katalogu rutinu.</span><span class="sxs-lookup"><span data-stu-id="51c3c-132">It also displays signing status of catalog in *Signature* property which is equivalent to calling [Get-AuthenticodeSignature](https://technet.microsoft.com/en-us/library/hh849805.aspx) cmdlet on the catalog file.</span></span> <span data-ttu-id="51c3c-133">Uživatelé také přeskočit všechny soubory během ověřování pomocí *- FilesToSkip* parametr.</span><span class="sxs-lookup"><span data-stu-id="51c3c-133">Users can also skip any file during validation by using the *-FilesToSkip* parameter.</span></span> 


## <a name="module-analysis-cache"></a><span data-ttu-id="51c3c-134">Modul Analysis mezipaměti</span><span class="sxs-lookup"><span data-stu-id="51c3c-134">Module Analysis Cache</span></span> ##
<span data-ttu-id="51c3c-135">Od verze WMF 5.1, prostředí PowerShell umožňuje řídit soubor, který se používá k o modulu, například příkazy exportuje data do mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="51c3c-135">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="51c3c-136">Ve výchozím nastavení je tato mezipaměť uložené v souboru `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span><span class="sxs-lookup"><span data-stu-id="51c3c-136">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span>
<span data-ttu-id="51c3c-137">Mezipaměť je obvykle pro čtení na spuštění při vyhledávání pro příkaz a je zapsán v vlákna na pozadí zopakovat po importování modulu.</span><span class="sxs-lookup"><span data-stu-id="51c3c-137">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="51c3c-138">Chcete-li změnit výchozí umístění mezipaměti, nastavte `$env:PSModuleAnalysisCachePath` proměnnou prostředí před spuštěním prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51c3c-138">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="51c3c-139">Změny této proměnné prostředí mají vliv jenom podřízené procesy.</span><span class="sxs-lookup"><span data-stu-id="51c3c-139">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="51c3c-140">Hodnota by měla název úplná cesta (včetně názvu souboru), který má oprávnění k vytvoření a zapisovat soubory prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51c3c-140">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="51c3c-141">Mezipaměť souborů se zakázat, nastavte hodnotu neplatné umístění, například:</span><span class="sxs-lookup"><span data-stu-id="51c3c-141">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="51c3c-142">Nastaví tato cesta neplatná zařízení.</span><span class="sxs-lookup"><span data-stu-id="51c3c-142">This sets the path to an invalid device.</span></span> <span data-ttu-id="51c3c-143">Pokud PowerShell nemůže zapisovat do cesty, je vrácena žádná chyba, ale uvidíte pomocí trasovací zpráv o chybách:</span><span class="sxs-lookup"><span data-stu-id="51c3c-143">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="51c3c-144">Při zápisu se do mezipaměti, zkontroluje, prostředí PowerShell pro moduly, které už existují předejdete zbytečně velké mezipaměti.</span><span class="sxs-lookup"><span data-stu-id="51c3c-144">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span>
<span data-ttu-id="51c3c-145">Někdy těmito kontrolami není vhodná, v takovém případě můžete vypnout jejich nastavením:</span><span class="sxs-lookup"><span data-stu-id="51c3c-145">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="51c3c-146">Nastavení této proměnné prostředí se projeví okamžitě v aktuálním procesu.</span><span class="sxs-lookup"><span data-stu-id="51c3c-146">Setting this environment variable will take effect immediately in the current process.</span></span>

##<a name="specifying-module-version"></a><span data-ttu-id="51c3c-147">Určení verze modulu</span><span class="sxs-lookup"><span data-stu-id="51c3c-147">Specifying module version</span></span>

<span data-ttu-id="51c3c-148">V WMF 5.1 `using module` se chová stejně jako jiné související modulu konstrukce v prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51c3c-148">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span> <span data-ttu-id="51c3c-149">Dříve bylo žádný způsob, jak určit konkrétního modulu verze; kdyby existovalo víc verzí přítomen, výsledkem chyba.</span><span class="sxs-lookup"><span data-stu-id="51c3c-149">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>


<span data-ttu-id="51c3c-150">V WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="51c3c-150">In WMF 5.1:</span></span>

* <span data-ttu-id="51c3c-151">Můžete použít [ModuleSpecification – konstruktor (zatřiďovací tabulky)](https://msdn.microsoft.com/library/jj136290).</span><span class="sxs-lookup"><span data-stu-id="51c3c-151">You can use [ModuleSpecification Constructor (Hashtable)](https://msdn.microsoft.com/library/jj136290).</span></span> <span data-ttu-id="51c3c-152">Tato tabulka hodnota hash má stejný formát jako `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="51c3c-152">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

<span data-ttu-id="51c3c-153">**Příklad:**`using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="51c3c-153">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

* <span data-ttu-id="51c3c-154">Pokud existuje více verzí modulu, používá prostředí PowerShell **stejné logiky, která řešení** jako `Import-Module` a nevrací chybu – stejné chování jako `Import-Module` a `Import-DscResource`.</span><span class="sxs-lookup"><span data-stu-id="51c3c-154">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>


##<a name="improvements-to-pester"></a><span data-ttu-id="51c3c-155">Vylepšení Pester</span><span class="sxs-lookup"><span data-stu-id="51c3c-155">Improvements to Pester</span></span>
<span data-ttu-id="51c3c-156">V WMF 5.1 verzi Pester, který se dodává s prostředím PowerShell, má z 3.3.5 aktualizovaná tak, aby 3.4.0, a uveďte https://github.com/pester/Pester/pull/484/commits/3854ae8a1f215b39697ac6c2607baf42257b102e potvrzení, která umožňuje lepší chování Pester na Nano Server.</span><span class="sxs-lookup"><span data-stu-id="51c3c-156">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0, with the addition of commit https://github.com/pester/Pester/pull/484/commits/3854ae8a1f215b39697ac6c2607baf42257b102e, which enables better behavior for Pester on Nano Server.</span></span> 

<span data-ttu-id="51c3c-157">Můžete zkontrolovat změny ve verzích 3.3.5 k 3.4.0 zkontrolováním souboru ChangeLog.md v: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span><span class="sxs-lookup"><span data-stu-id="51c3c-157">You can review the changes in versions 3.3.5 to 3.4.0 by inspecting the ChangeLog.md file at: https://github.com/pester/Pester/blob/master/CHANGELOG.md</span></span>
