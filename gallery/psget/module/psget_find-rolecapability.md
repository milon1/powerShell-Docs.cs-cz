---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "Galerie prostředí powershell, rutiny, psget"
title: "Najít RoleCapability"
ms.openlocfilehash: 77c5b492d9681fa05315401fba410c508af1d13b
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="find-rolecapability"></a><span data-ttu-id="ecbba-103">Najít RoleCapability</span><span class="sxs-lookup"><span data-stu-id="ecbba-103">Find-RoleCapability</span></span>

<span data-ttu-id="ecbba-104">Vyhledá role funkce v modulech.</span><span class="sxs-lookup"><span data-stu-id="ecbba-104">Finds role capabilities in modules.</span></span>

## <a name="description"></a><span data-ttu-id="ecbba-105">Popis</span><span class="sxs-lookup"><span data-stu-id="ecbba-105">Description</span></span>
<span data-ttu-id="ecbba-106">Rutinu najít RoleCapability vyhledá role funkce prostředí PowerShell v modulech.</span><span class="sxs-lookup"><span data-stu-id="ecbba-106">The Find-RoleCapability cmdlet finds PowerShell role capabilities in modules.</span></span> <span data-ttu-id="ecbba-107">Najít RoleCapability vyhledá moduly v registrovaných úložiště.</span><span class="sxs-lookup"><span data-stu-id="ecbba-107">Find-RoleCapability searches modules in registered repositories.</span></span> <span data-ttu-id="ecbba-108">Pro každou funkci role, která tato rutina vyhledá vrátí objekt PSGetRoleCapabilityInfo.</span><span class="sxs-lookup"><span data-stu-id="ecbba-108">For each role capability that this cmdlet finds, it returns a PSGetRoleCapabilityInfo object.</span></span> <span data-ttu-id="ecbba-109">Objekt PSGetRoleCapabilityInfo můžete předat do rutiny Install-Module nainstalovat modul, který obsahuje funkce role.</span><span class="sxs-lookup"><span data-stu-id="ecbba-109">You can pass a PSGetRoleCapabilityInfo object to the Install-Module cmdlet to install the module that contains the role capability.</span></span>
<span data-ttu-id="ecbba-110">Možnosti prostředí PowerShell role definovat, které příkazy, aplikace a tak dále jsou k dispozici pro uživatele na koncový bod právě dostatečně správy JEA ().</span><span class="sxs-lookup"><span data-stu-id="ecbba-110">PowerShell role capabilities define which commands, applications, and so on are available to a user at a Just Enough Administration (JEA) endpoint.</span></span> <span data-ttu-id="ecbba-111">Funkce role jsou definované soubory s příponou .psrc.</span><span class="sxs-lookup"><span data-stu-id="ecbba-111">Role capabilities are defined by files with a .psrc extension.</span></span>

- <span data-ttu-id="ecbba-112">Najít RoleCapability můžete filtrovat s parametry verze: MinimumVersion, RequiredVersion, AllVersions.</span><span class="sxs-lookup"><span data-stu-id="ecbba-112">Find-RoleCapability can filter with version parameters: MinimumVersion, RequiredVersion, AllVersions.</span></span>
  - <span data-ttu-id="ecbba-113">Tyto parametry se vzájemně vylučují.</span><span class="sxs-lookup"><span data-stu-id="ecbba-113">These parameters are mutually exclusive.</span></span>
  - <span data-ttu-id="ecbba-114">Tyto parametry verze jsou povoleny pouze s názvem modulu single bez žádné zástupné znaky.</span><span class="sxs-lookup"><span data-stu-id="ecbba-114">These version parameters are allowed only with the single module name without any wildcards.</span></span>
  - <span data-ttu-id="ecbba-115">Pokud není zadán parametr RequiredVersion, vrátí RoleCapability najít nejnovější verzi modulu, která je rovna nebo větší než minimální verze zadaná nebo nejnovější verzi modulu, pokud je zadána žádná minimální verze.</span><span class="sxs-lookup"><span data-stu-id="ecbba-115">If the RequiredVersion parameter is not specified, Find-RoleCapability returns the latest version of the module that is equal to or greater than the minimum version specified or the latest version of the module if no minimum version is specified.</span></span>
  - <span data-ttu-id="ecbba-116">Pokud je zadán parametr RequiredVersion, najít RoleCapability pouze vrátí verzi modul, který přesně odpovídá zadaná verze.</span><span class="sxs-lookup"><span data-stu-id="ecbba-116">If the RequiredVersion parameter is specified, Find-RoleCapability only returns the version of the module that exactly matches the specified version.</span></span>
- <span data-ttu-id="ecbba-117">Najít RoleCapability můžete filtrovat podle metadata modulu s parametrem - značky</span><span class="sxs-lookup"><span data-stu-id="ecbba-117">Find-RoleCapability can filter on module metadata with the -Tag parameter</span></span>
- <span data-ttu-id="ecbba-118">Najít RoleCapability můžete filtrovat podle jazyka vyhledávání podle úložiště s parametrem - filtru.</span><span class="sxs-lookup"><span data-stu-id="ecbba-118">Find-RoleCapability can filter on repository-specific search language with the -Filter parameter.</span></span>
- <span data-ttu-id="ecbba-119">Najít RoleCapability můžete filtrovat podle moduly ze všech nebo několika registrované úložišť.</span><span class="sxs-lookup"><span data-stu-id="ecbba-119">Find-RoleCapability can filter on modules from all or few of the registered repositories.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="ecbba-120">Syntaxe rutin</span><span class="sxs-lookup"><span data-stu-id="ecbba-120">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Find-RoleCapability -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="ecbba-121">Referenční informace o rutinách online nápovědy</span><span class="sxs-lookup"><span data-stu-id="ecbba-121">Cmdlet online help reference</span></span>

[<span data-ttu-id="ecbba-122">Najít RoleCapability</span><span class="sxs-lookup"><span data-stu-id="ecbba-122">Find-RoleCapability</span></span>](http://go.microsoft.com/fwlink/?LinkId=718029)

## <a name="example-commands"></a><span data-ttu-id="ecbba-123">Příklady příkazů</span><span class="sxs-lookup"><span data-stu-id="ecbba-123">Example commands</span></span>
```powershell

# Find a specific role capability
Find-RoleCapability -Name Maintenance

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Maintenance                         1.5.0      RoleCapModule                       PrivatePSGallery

# Find multiple role capabilities
Find-RoleCapability -Name MyJeaRole, Maintenance

# Find all available role capabilities from all registered repositories
Find-RoleCapability

# Find available role capabilities from few registered repositories
Find-RoleCapability -Repository PSGallery,PrivatePSGallery

# Find all role capabilities in a specified repository
Find-RoleCapability -Repository PSGallery

# Find a role capability defined in a specific module
Find-RoleCapability -Name Maintenance -ModuleName RoleCapModule

# Find role capabilities from all versions of a module
Find-RoleCapability -ModuleName RoleCapModule -AllVersions

# Find role capabilities with module name and MinimumVersion.
Find-RoleCapability -ModuleName RoleCapModule -MinimumVersion 1.1

# Find role capabilities with module name and exact version
Find-RoleCapability -ModuleName RoleCapModule -RequiredVersion 1.4.0

# Find role capabilities defined modules with -Filter based search. -Filter searches in description and module names
Find-RoleCapability -Filter Cookbook
Find-RoleCapability -Filter RBAC

# Find all role capabilities with tags Azure or DSC in module metadata
Find-RoleCapability -Tag Azure, DSC

```
