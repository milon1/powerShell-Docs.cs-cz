---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "DSC pro Linux nxScript prostředků"
ms.openlocfilehash: 5fc448d15f9bec77be64b5f9ee801f6616cf7208
ms.sourcegitcommit: 4807ab554d55fdee499980835bcc279368b1df68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="dsc-for-linux-nxscript-resource"></a><span data-ttu-id="5df4f-103">DSC pro Linux nxScript prostředků</span><span class="sxs-lookup"><span data-stu-id="5df4f-103">DSC for Linux nxScript Resource</span></span>

<span data-ttu-id="5df4f-104">**NxScript** prostředků v prostředí PowerShell požadovaného stavu konfigurace (DSC) poskytuje mechanismus ke spouštění skriptů Linux na uzlu Linux.</span><span class="sxs-lookup"><span data-stu-id="5df4f-104">The **nxScript** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to run Linux scripts on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="5df4f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="5df4f-105">Syntax</span></span>

```
nxScript <string> #ResourceName
{
    GetScript = <string>
    SetScript = <string>
    TestScript = <string>
    [ User = <string> ]
    [ Group = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="5df4f-106">Properties</span><span class="sxs-lookup"><span data-stu-id="5df4f-106">Properties</span></span>

|  <span data-ttu-id="5df4f-107">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="5df4f-107">Property</span></span> |  <span data-ttu-id="5df4f-108">Popis</span><span class="sxs-lookup"><span data-stu-id="5df4f-108">Description</span></span> | 
|---|---|
| <span data-ttu-id="5df4f-109">GetScript</span><span class="sxs-lookup"><span data-stu-id="5df4f-109">GetScript</span></span>| <span data-ttu-id="5df4f-110">Poskytuje skript, který spouští při vyvolání [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx) rutiny.</span><span class="sxs-lookup"><span data-stu-id="5df4f-110">Provides a script that runs when you invoke the [Get-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521625.aspx) cmdlet.</span></span> <span data-ttu-id="5df4f-111">Skript musí začínat shebang, například #! / bin/bash.</span><span class="sxs-lookup"><span data-stu-id="5df4f-111">The script must begin with a shebang, such as #!/bin/bash.</span></span>| 
| <span data-ttu-id="5df4f-112">SetScript</span><span class="sxs-lookup"><span data-stu-id="5df4f-112">SetScript</span></span>| <span data-ttu-id="5df4f-113">Poskytuje skript.</span><span class="sxs-lookup"><span data-stu-id="5df4f-113">Provides a script.</span></span> <span data-ttu-id="5df4f-114">Při vyvolání [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) rutiny **TestScript** spustí první.</span><span class="sxs-lookup"><span data-stu-id="5df4f-114">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, the **TestScript** runs first.</span></span> <span data-ttu-id="5df4f-115">Pokud **TestScript** bloku vrátí ukončovací kód než 0, **SetScript** bloku se spustí.</span><span class="sxs-lookup"><span data-stu-id="5df4f-115">If the **TestScript** block returns an exit code other than 0, the **SetScript** block will run.</span></span> <span data-ttu-id="5df4f-116">Pokud **TestScript** vrátí ukončovací kód 0, **SetScript** se nespustí.</span><span class="sxs-lookup"><span data-stu-id="5df4f-116">If the **TestScript** returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="5df4f-117">Skript musí začínat shebang, jako například `#!/bin/bash`.</span><span class="sxs-lookup"><span data-stu-id="5df4f-117">The script must begin with a shebang, such as `#!/bin/bash`.</span></span>| 
| <span data-ttu-id="5df4f-118">TestScript</span><span class="sxs-lookup"><span data-stu-id="5df4f-118">TestScript</span></span>| <span data-ttu-id="5df4f-119">Poskytuje skript.</span><span class="sxs-lookup"><span data-stu-id="5df4f-119">Provides a script.</span></span> <span data-ttu-id="5df4f-120">Při vyvolání [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) tento skript spouští rutiny.</span><span class="sxs-lookup"><span data-stu-id="5df4f-120">When you invoke the [Start-DscConfiguration](https://technet.microsoft.com/en-us/library/dn521623.aspx) cmdlet, this script runs.</span></span> <span data-ttu-id="5df4f-121">Pokud vrátí ukončovací kód než 0, se spustí SetScript.</span><span class="sxs-lookup"><span data-stu-id="5df4f-121">If it returns an exit code other than 0, the SetScript will run.</span></span> <span data-ttu-id="5df4f-122">Vrátí ukončovací kód 0,-li **SetScript** se nespustí.</span><span class="sxs-lookup"><span data-stu-id="5df4f-122">If it returns an exit code of 0, the **SetScript** will not run.</span></span> <span data-ttu-id="5df4f-123">**TestScript** poběží i v případě vyvolání [Test DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) rutiny.</span><span class="sxs-lookup"><span data-stu-id="5df4f-123">The **TestScript** also runs when you invoke the [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) cmdlet.</span></span> <span data-ttu-id="5df4f-124">V takovém případě však **SetScript** se nespustí, bez ohledu na to, jaké ukončovací kód je vrácen z **TestScript**.</span><span class="sxs-lookup"><span data-stu-id="5df4f-124">However, in this case, the **SetScript** will not run, no matter what exit code is returned from the **TestScript**.</span></span> <span data-ttu-id="5df4f-125">**TestScript** musí vracet ukončovací kód 0, pokud skutečné konfigurace odpovídá aktuální konfiguraci požadovaného stavu a ukončení kódu jiné než 0, pokud neodpovídá.</span><span class="sxs-lookup"><span data-stu-id="5df4f-125">The **TestScript** must return an exit code of 0 if the actual configuration matches the current desired state configuration, and an exit code other than 0 if it does not match.</span></span> <span data-ttu-id="5df4f-126">(Aktuální konfigurace požadovaného stavu je poslední konfigurace použity na uzlu, který používá DSC).</span><span class="sxs-lookup"><span data-stu-id="5df4f-126">(The current desired state configuration is the last configuration enacted on the node that is using DSC).</span></span> <span data-ttu-id="5df4f-127">Skript musí začínat shebang, jako je například 1#!/bin/bash.1</span><span class="sxs-lookup"><span data-stu-id="5df4f-127">The script must begin with a shebang, such as 1#!/bin/bash.1</span></span>| 
| <span data-ttu-id="5df4f-128">Uživatel</span><span class="sxs-lookup"><span data-stu-id="5df4f-128">User</span></span>| <span data-ttu-id="5df4f-129">Uživatele k spuštění skriptu jako.</span><span class="sxs-lookup"><span data-stu-id="5df4f-129">The user to run the script as.</span></span>| 
| <span data-ttu-id="5df4f-130">Skupina</span><span class="sxs-lookup"><span data-stu-id="5df4f-130">Group</span></span>| <span data-ttu-id="5df4f-131">Skupina pro spuštění skriptu jako.</span><span class="sxs-lookup"><span data-stu-id="5df4f-131">The group to run the script as.</span></span>| 
| <span data-ttu-id="5df4f-132">dependsOn</span><span class="sxs-lookup"><span data-stu-id="5df4f-132">DependsOn</span></span> | <span data-ttu-id="5df4f-133">Určuje, že konfigurace jiný prostředek musí spouštět předtím, než je tento prostředek nakonfigurován.</span><span class="sxs-lookup"><span data-stu-id="5df4f-133">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="5df4f-134">Například pokud **ID** prostředku blok skriptu konfigurace, který chcete spustit nejprve je **ResourceName** a její typ je **ResourceType**, pomocí této syntaxe Vlastnost je `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="5df4f-134">For example, if the **ID** of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="example"></a><span data-ttu-id="5df4f-135">Příklad</span><span class="sxs-lookup"><span data-stu-id="5df4f-135">Example</span></span>

<span data-ttu-id="5df4f-136">Následující příklad ukazuje použití **nxScript** prostředek se má provést další konfiguraci správy.</span><span class="sxs-lookup"><span data-stu-id="5df4f-136">The following example demonstrates the use of the **nxScript** resource to perform additional configuration management.</span></span>

```
Import-DSCResource -Module nx 

Node $node {
nxScript KeepDirEmpty{

    GetScript = @"
#!/bin/bash
ls /tmp/mydir/ | wc -l
"@

    SetScript = @"
#!/bin/bash
rm -rf /tmp/mydir/*
"@

    TestScript = @'
#!/bin/bash
filecount=`ls /tmp/mydir | wc -l`
if [ $filecount -gt 0 ]
then
    exit 1
else
    exit 0
fi
'@
} 
}
```
