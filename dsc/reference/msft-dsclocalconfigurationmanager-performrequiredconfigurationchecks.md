---
ms.date: 06/12/2017
keywords: DSC, powershell, konfigurace, instalační program
title: Metoda PerformRequiredConfigurationChecks třídy MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: b92eefb7fbea6d96afa31f6b802ba10fe20d4103
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403637"
---
# <a name="performrequiredconfigurationchecks-method-of-the-msftdsclocalconfigurationmanager-class"></a>Metoda PerformRequiredConfigurationChecks třídy MSFT_DSCLocalConfigurationManager

Spustí kontrolu konzistence pomocí plánovače úloh.

## <a name="syntax"></a>Syntaxe

```mof
uint32 PerformRequiredConfigurationChecks(
  [in] uint32 Flags
);
```

## <a name="parameters"></a>Parameters

*Příznaky* \[v\] bitová maska, která určuje typ spuštění kontroly konzistence. Následující hodnoty jsou platné a je možné kombinovat pomocí logické bitové **nebo** operace:

|Hodnota |Popis |
|:--- |:---|
|**1** | Normální konzistence. |
|**2** | Pokračování kontrolu konzistence po restartu. Tato hodnota by neměla kombinovat s jinými hodnotami. |
|**4** | Konfigurace by měl být vyžádány z načítacího serveru zadaný v metaconfiguration pro uzel. Tato hodnota by měla vždy zkombinuje s **1**, pro hodnotu **5**. |
|**8** | Stav odeslání na server sestav. |

## <a name="return-value"></a>Návratová hodnota

Vrátí nulu v případě úspěchu; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky

Toto je statické metody.

## <a name="requirements"></a>Požadavky

**SOUBOR MOF:** DscCore.mof

**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration

## <a name="see-also"></a>Viz taky

[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)