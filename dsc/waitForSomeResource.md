---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "WaitForSome prostředek DSC"
ms.openlocfilehash: 3ea9dc51cbb00cf6158abf114fdb31fd91307df9
ms.sourcegitcommit: f069ff0689006fece768f178c10e3e3eeaee09f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2017
---
# <a name="dsc-waitforsome-resource"></a><span data-ttu-id="2b4f9-103">WaitForSome prostředek DSC</span><span class="sxs-lookup"><span data-stu-id="2b4f9-103">DSC WaitForSome Resource</span></span>

> <span data-ttu-id="2b4f9-104">Platí pro: 5.0 a novější se prostředí Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b4f9-104">Applies To: Windows PowerShell 5.0 and later</span></span>

<span data-ttu-id="2b4f9-105">**WaitForAny** prostředků konfigurace požadovaného stavu (DSC) lze použít v rámci bloku uzlu v [konfigurace DSC](configurations.md) určete závislosti na konfiguraci na jiných uzlech.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-105">The **WaitForAny** Desired State Configuration (DSC) resource can be used within a node block in a [DSC configuration](configurations.md) to specify dependencies on configurations on other nodes.</span></span>

<span data-ttu-id="2b4f9-106">Tento prostředek úspěšná, pokud prostředek určeného **ResourceName** vlastnost je v požadovaném stavu na minimální počet uzlů (zadáno v **NodeCount**) definované **NodeName**  vlastnost.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-106">This resource succeeds if the resource specified by the **ResourceName** property is in the desired state on a minimum number of nodes (specified by **NodeCount**) defined by the **NodeName** property.</span></span> 


## <a name="syntax"></a><span data-ttu-id="2b4f9-107">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="2b4f9-107">Syntax</span></span>

```
WaitForSome [String] #ResourceName
{
    NodeCount = [UInt32]
    NodeName = [string[]]
    ResourceName = [string]
    [DependsOn = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
    [RetryCount = [UInt32]]
    [RetryIntervalSec = [UInt64]]
    [ThrottleLimit = [UInt32]]
}
```

## <a name="properties"></a><span data-ttu-id="2b4f9-108">Properties</span><span class="sxs-lookup"><span data-stu-id="2b4f9-108">Properties</span></span>

|  <span data-ttu-id="2b4f9-109">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="2b4f9-109">Property</span></span>  |  <span data-ttu-id="2b4f9-110">Popis</span><span class="sxs-lookup"><span data-stu-id="2b4f9-110">Description</span></span>   | 
|---|---| 
| <span data-ttu-id="2b4f9-111">NodeCount</span><span class="sxs-lookup"><span data-stu-id="2b4f9-111">NodeCount</span></span>| <span data-ttu-id="2b4f9-112">Minimální počet uzlů, které musí být v požadovaném stavu pro tento prostředek proběhla úspěšně.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-112">The minimum number of nodes that must be in the desired state for this resource to succeed.</span></span>|
| <span data-ttu-id="2b4f9-113">nodeName</span><span class="sxs-lookup"><span data-stu-id="2b4f9-113">NodeName</span></span>| <span data-ttu-id="2b4f9-114">Cílové uzly závislý na prostředku.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-114">The target nodes of the resource to depend on.</span></span>| 
| <span data-ttu-id="2b4f9-115">resourceName</span><span class="sxs-lookup"><span data-stu-id="2b4f9-115">ResourceName</span></span>| <span data-ttu-id="2b4f9-116">Název prostředku závislý na.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-116">The resource name to depend on.</span></span>| 
| <span data-ttu-id="2b4f9-117">RetryIntervalSec</span><span class="sxs-lookup"><span data-stu-id="2b4f9-117">RetryIntervalSec</span></span>| <span data-ttu-id="2b4f9-118">Počet sekund, než se budete pokoušet.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-118">The number of seconds before retrying.</span></span> <span data-ttu-id="2b4f9-119">Minimální hodnota je 1.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-119">Minimum is 1.</span></span>| 
| <span data-ttu-id="2b4f9-120">retryCount</span><span class="sxs-lookup"><span data-stu-id="2b4f9-120">RetryCount</span></span>| <span data-ttu-id="2b4f9-121">Maximální počet pokusů o opakování.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-121">The maximum number of times to retry.</span></span>| 
| <span data-ttu-id="2b4f9-122">ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="2b4f9-122">ThrottleLimit</span></span>| <span data-ttu-id="2b4f9-123">Počet počítačů pro připojení současně.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-123">Number of machines to connect simultaneously.</span></span> <span data-ttu-id="2b4f9-124">Výchozí hodnota je výchozí pro nové cimsession.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-124">Default is new-cimsession default.</span></span>| 
| <span data-ttu-id="2b4f9-125">dependsOn</span><span class="sxs-lookup"><span data-stu-id="2b4f9-125">DependsOn</span></span> | <span data-ttu-id="2b4f9-126">Určuje, že konfigurace jiný prostředek musí spouštět předtím, než je tento prostředek nakonfigurován.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-126">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="2b4f9-127">Pokud ID konfigurace prostředků skriptu blok, který chcete spustit nejprve je třeba __ResourceName__ a její typ je __ResourceType__, syntaxe pro používání této vlastnosti je `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="2b4f9-127">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|
| <span data-ttu-id="2b4f9-128">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="2b4f9-128">PsDscRunAsCredential</span></span> | <span data-ttu-id="2b4f9-129">V tématu [DSC pomocí uživatelských přihlašovacích údajů](https://docs.microsoft.com/en-us/powershell/dsc/runasuser)</span><span class="sxs-lookup"><span data-stu-id="2b4f9-129">See [Using DSC with User Credentials](https://docs.microsoft.com/en-us/powershell/dsc/runasuser)</span></span> |


## <a name="example"></a><span data-ttu-id="2b4f9-130">Příklad</span><span class="sxs-lookup"><span data-stu-id="2b4f9-130">Example</span></span>

<span data-ttu-id="2b4f9-131">Příklad toho, jak používat tento prostředek, naleznete v části [určení závislostí mezi uzly](crossNodeDependencies.md)</span><span class="sxs-lookup"><span data-stu-id="2b4f9-131">For an example of how to use this resource, see [Specifying cross-node dependencies](crossNodeDependencies.md)</span></span>
