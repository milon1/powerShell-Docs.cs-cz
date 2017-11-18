---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, prostředí powershell, instalační program"
contributor: vaibch
title: "Chyba rutiny správce přepínače sítě"
ms.openlocfilehash: d9fcdedbfc7d0c3f68624ed1db6259e04c3d06d1
ms.sourcegitcommit: fee03bb9802222078c8d5f6c8efb0698024406ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2017
---
Rutiny správce přepínače sítě můžete použít ke správě přepínače sítě prostřednictvím služby WSMAN. Jsou schopný přijímat hodnoty z kanálů několik rutiny tohoto modulu. Ve verzi Preview 5.1 WMF rutiny, které může přijmout hodnoty z kanálu nepodaří spustit, když nejsou k hodnotám předaným pomocí kanálů.

Pokud není použit parametr "InputObject", by měly být nadále rutina spustí bez chyb.

Tady je seznam ovlivněných rutin, tj. Tyto rutiny může přijmout hodnotu pro parametr "InputObject" z kanálu. Provádění rutiny se nezdaří, pokud není tato hodnota předaná z kanálu.

- Zakázat NetworkSwitchEthernetPort
- Povolit NetworkSwitchEthernetPort
- Odebrat NetworkSwitchEthernetPortIPAddress
- Set-NetworkSwitchEthernetPortIPAddress
- Set-NetworkSwitchPortMode
- Set-NetworkSwitchPortProperty
- Zakázat NetworkSwitchFeature
- Povolit NetworkSwitchFeature
- Odebrat NetworkSwitchVlan
- Set-NetworkSwitchVlanProperty

### <a name="resolution"></a>Řešení
Rutiny pracovní dobře, když je hodnota parametru InputObject se předávají do ní prostřednictvím kanálu. Několik příkladů, které fungují pro výše uvedené rutiny jsou:

- Zakázat NetworkSwitchEthernetPort
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Disable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- Povolit NetworkSwitchEthernetPort
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Enable-NetworkSwitchEthernetPort -CimSession $cimSession
```

- Odebrat NetworkSwitchEthernetPortIPAddress
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Remove-NetworkSwitchEthernetPortIPAddress -CimSession $cimSession
```

- Set-NetworkSwitchEthernetPortIPAddress
```powershell
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$ipAddress = "192.168.10.1"
$subnetAddress = "255.255.255.0"
$port | Set-NetworkSwitchEthernetPortIPAddress -IpAddress $ipAddress -SubnetAddress $subnetAddress -CimSession $cimSession
```

- Set-NetworkSwitchPortProperty
```powershell
$portProperties = @{Caption = "New Caption"}
$port = Get-CimInstance -Namespace root/interop -ClassName CIM_EthernetPort -CimSession $cimSession | Select-Object -First 1
$port | Set-NetworkSwitchPortProperty -Property $portProperties -CimSession $cimSession
```

- Zakázat NetworkSwitchFeature
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Disable-NetworkSwitchFeature -CimSession $cimSession
```

- Povolit NetworkSwitchFeature
```powershell
$feature = Get-CimInstance -Namespace root/interop -ClassName MSFT_Feature -CimSession $cimSession | Select-Object -First 1
$feature | Enable-NetworkSwitchFeature -CimSession $cimSession
```

- Set-NetworkSwitchVlanProperty
```powershell
$properties = @{Caption = "New Caption"}
$vlan = Get-CimInstance -ClassName CIM_NetworkVlan -Namespace root/interop -CimSession $cimSession | Select-Object -First 1
$vlan | Set-NetworkSwitchVlanProperty -Property $properties -CimSession $cimSession
```
