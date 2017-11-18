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
# <a name="dsc-waitforsome-resource"></a>WaitForSome prostředek DSC

> Platí pro: 5.0 a novější se prostředí Windows PowerShell

**WaitForAny** prostředků konfigurace požadovaného stavu (DSC) lze použít v rámci bloku uzlu v [konfigurace DSC](configurations.md) určete závislosti na konfiguraci na jiných uzlech.

Tento prostředek úspěšná, pokud prostředek určeného **ResourceName** vlastnost je v požadovaném stavu na minimální počet uzlů (zadáno v **NodeCount**) definované **NodeName**  vlastnost. 


## <a name="syntax"></a>Syntaxe

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

## <a name="properties"></a>Properties

|  Vlastnost  |  Popis   | 
|---|---| 
| NodeCount| Minimální počet uzlů, které musí být v požadovaném stavu pro tento prostředek proběhla úspěšně.|
| nodeName| Cílové uzly závislý na prostředku.| 
| resourceName| Název prostředku závislý na.| 
| RetryIntervalSec| Počet sekund, než se budete pokoušet. Minimální hodnota je 1.| 
| retryCount| Maximální počet pokusů o opakování.| 
| ThrottleLimit| Počet počítačů pro připojení současně. Výchozí hodnota je výchozí pro nové cimsession.| 
| dependsOn | Určuje, že konfigurace jiný prostředek musí spouštět předtím, než je tento prostředek nakonfigurován. Pokud ID konfigurace prostředků skriptu blok, který chcete spustit nejprve je třeba __ResourceName__ a její typ je __ResourceType__, syntaxe pro používání této vlastnosti je `DependsOn = "[ResourceType]ResourceName"`.|
| PsDscRunAsCredential | V tématu [DSC pomocí uživatelských přihlašovacích údajů](https://docs.microsoft.com/en-us/powershell/dsc/runasuser) |


## <a name="example"></a>Příklad

Příklad toho, jak používat tento prostředek, naleznete v části [určení závislostí mezi uzly](crossNodeDependencies.md)
