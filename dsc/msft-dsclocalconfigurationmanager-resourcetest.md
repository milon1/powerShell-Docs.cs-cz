---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "Metoda ResourceTest MSFT_DSCLocalConfigurationManager třídy"
ms.openlocfilehash: 73d7d543505a3768a0660084345d3858e055514f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="resourcetest-method-of-the-msftdsclocalconfigurationmanager-class"></a>Metoda ResourceTest MSFT_DSCLocalConfigurationManager třídy

Volá přímo **Test** metoda prostředek DSC.

<a name="syntax"></a>Syntaxe
------

```mof
uint32 ResourceTest(
  [in]  string  ResourceType,
  [in]  string  ModuleName,
  [in]  uint8   resourceProperty[],
  [out] boolean InDesiredState
);
```

<a name="parameters"></a>Parameters
----------

*Typ prostředku* \[v\]  
Název prostředku k volání.

*Název modulu* \[v\]  
Název modulu, který obsahuje prostředek k volání.

*resourceProperty* \[v\]  
Určuje název vlastnosti prostředku a jeho hodnotu v zatřiďovací tabulku jako klíč a hodnotu, v uvedeném pořadí. Použití [Get-DscResource](https://technet.microsoft.com/en-us/library/dn521625.aspx) rutiny zjistit vlastnosti prostředku a jejich typy.

*InDesiredState* \[out\]  
Při návratu, je tato vlastnost nastavená na **true** Pokud cílový uzel je v požadovaném stavu.

## <a name="return-value"></a>Návratová hodnota
------------

Vrátí nula v případě úspěchu; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky

Jde o statickou metodu.

## <a name="requirements"></a>Požadavky
------------
>**MOF:** DscCore.mof

>**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration


## <a name="see-also"></a>Viz taky


[**MSFT_DSCLocalConfigurationManager**](msft-dsclocalconfigurationmanager.md)


 

 


