---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "Galerie prostředí powershell, rutiny, psget"
title: "Uložit – modul"
ms.openlocfilehash: acea38b0eebc58dafda0ab58b91dc6a70ffffd3b
ms.sourcegitcommit: 58371abe9db4b9a0e4e1eb82d39a9f9e187355f9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2017
---
# <a name="save-module"></a><span data-ttu-id="3d937-103">Uložit – modul</span><span class="sxs-lookup"><span data-stu-id="3d937-103">Save-Module</span></span>

<span data-ttu-id="3d937-104">Uloží modul místně bez nutnosti její instalace.</span><span class="sxs-lookup"><span data-stu-id="3d937-104">Saves a module locally without installing it.</span></span>

## <a name="description"></a><span data-ttu-id="3d937-105">Popis</span><span class="sxs-lookup"><span data-stu-id="3d937-105">Description</span></span>

<span data-ttu-id="3d937-106">Rutina modulu uložit uloží modul místně z zadané úložiště pro kontroly.</span><span class="sxs-lookup"><span data-stu-id="3d937-106">The Save-Module cmdlet saves a module locally from the specified repository for inspection.</span></span> <span data-ttu-id="3d937-107">Modul není nainstalován.</span><span class="sxs-lookup"><span data-stu-id="3d937-107">The module is not installed.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="3d937-108">Syntaxe rutin</span><span class="sxs-lookup"><span data-stu-id="3d937-108">Cmdlet syntax</span></span>
```powershell
Get-Command -Name Save-Module -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="3d937-109">Referenční informace o rutinách online nápovědy</span><span class="sxs-lookup"><span data-stu-id="3d937-109">Cmdlet online help reference</span></span>

[<span data-ttu-id="3d937-110">Uložit – modul</span><span class="sxs-lookup"><span data-stu-id="3d937-110">Save-Module</span></span>](http://go.microsoft.com/fwlink/?LinkId=531351)

## <a name="example-commands"></a><span data-ttu-id="3d937-111">Příklady příkazů</span><span class="sxs-lookup"><span data-stu-id="3d937-111">Example commands</span></span>

```powershell
Save-Module -Repository MSPSGallery -Name ModuleWithDependencies2 -Path C:\MySavedModuleLocation
dir C:\MySavedModuleLocation

Directory: C:\MySavedModuleLocation

Mode LastWriteTime Length Name
---- ------------- ------ ----
d----- 4/21/2015 5:40 PM ModuleWithDependencies2
d----- 4/21/2015 5:40 PM NestedRequiredModule1
d----- 4/21/2015 5:40 PM NestedRequiredModule2
d----- 4/21/2015 5:40 PM NestedRequiredModule3
d----- 4/21/2015 5:40 PM RequiredModule1
d----- 4/21/2015 5:40 PM RequiredModule2
d----- 4/21/2015 5:40 PM RequiredModule3


# Find a command and save its module
# This command finds the specified command, and then passes it to Save-Module to save it to the C:\temp folder.
Find-Command -Name "Get-NestedRequiredModule4" -Repository "INT" | Save-Module -Path "C:\temp\" -Verbose


# Save the role capability modules by piping the Find-RoleCapability output to Save-Module cmdlet.
Find-RoleCapability -Name Maintenance,MyJeaRole | Save-Module -Path C:\MyModulesPath


# Save a specific prerelease version of a module to C:\MySavedModuleLocation
Save-Module -Name ContosoServer -RequiredVersion 1.1.3-alpha -Path C:\MySavedModuleLocation -AllowPrerelease

# Install the latest version of a module by name, including prelrelease versions if one exists
Install-Module -Name ContosoServer -Path C:\MySavedModuleLocation -AllowPrerelease



```

