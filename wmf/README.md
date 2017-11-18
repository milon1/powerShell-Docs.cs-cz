---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, prostředí powershell, instalační program"
title: Windows Management Framework (WMF)
ms.openlocfilehash: 9a9281c5eeb771c472623bff6fa6bd6d6aa7814a
ms.sourcegitcommit: fee03bb9802222078c8d5f6c8efb0698024406ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2017
---
# <a name="windows-management-framework"></a>Windows Management Framework

Windows Management Framework (WMF) je mechanismus doručování, který poskytuje rozhraní, které je konzistentní správu v rámci různých typů systému Windows a Windows Server.
V instalaci WMF získat zákazníkům bezproblémový způsob, jak zajistit vzájemnou funkční spolupráci mezi mix operační systémy ve svém prostředí.
WMF provede aktualizace funkce správy v dané verzi Windows a Windows Server, k dispozici pro instalaci na nižších verzích (obvykle 2 nižší verze) systému Windows a Windows Server.

Instalaci WMF přidá nebo aktualizuje následující funkce:

- Windows PowerShell
- Windows PowerShell Desired State Configuration (DSC)
- Windows PowerShell skriptu integrované prostředí (ISE)
- Vzdálená správa systému Windows (WinRM)
- Windows Management Instrumentation (WMI)
- Windows PowerShell webové služby (OData IIS rozšíření správy)
- (SIL) protokolování inventáře softwaru
- CIM poskytovatele správce serveru

## <a name="wmf-release-notes"></a>Poznámky k verzi WMF

Další informace o různých rozšíření v prostředí PowerShell a jiných součástí dané WMF, naleznete na následujících odkazech zkontrolujte poznámky k verzi:

- [WMF 5.1](5.1/release-notes.md)
- [WMF 5.0](5.0/releasenotes.md)
- [FORMÁT WMF 4.0](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [PODPORA PRODUKTU WMF 3.0](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a>Dostupnost WMF v rámci operační systémy Windows

| Verze operačního systému | [WMF 5.1](https://aka.ms/wmf51download) | [WMF 5.0](https://aka.ms/wmf5download) | [FORMÁT WMF 4.0](https://aka.ms/wmf4download) |  [PODPORA PRODUKTU WMF 3.0](https://aka.ms/wmf3download) | [WMF 2.0](https://aka.ms/wmf2download) |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| Windows Server 2016 | Se dodává v poli |  |  |  |  |
| Windows 10 | Se dodává v poli | Se dodává v poli  | | | |  
| Windows Server 2012 R2| Ano | Ano | Se dodává v poli |  |  |
| Windows 8.1 | Ano | Ano |  Se dodává v poli |  |  |
| Windows Server 2012 | Ano | Ano | Ano |  Se dodává v poli | |
| Windows 8 |  |  |  | Se dodává v poli | |
| Windows Server 2008 R2 SP1 | Ano | Ano | Ano |  Ano| Se dodává v poli |
| Windows 7 s aktualizací SP1  | Ano | Ano | Ano | Ano | Se dodává v poli |
| Windows Server 2008 SP2 | | | | Ano | Ano |
| Windows Vista | | | | | Ano |
| Windows Server 2003| | | |  | Ano |
| Windows XP | | | |  | Ano |

**"Se dodává v poli"**: funkce `specified WMF` byly odeslány v uvedených verzí systému Windows a Windows Server.
Proto `specified WMF` nemusí být nainstalován na verze uvedené operačního systému.
