---
ms.date: 2017-08-09
keywords: "prostředí PowerShell, rutiny, stažení, instalace, instalační program, windows 10, windows 8.1, windows 8.0, windows 7"
title: "Instalace prostředí Windows PowerShell"
ms.openlocfilehash: 781bf50b6ac649e72bcdbb708555275fb7422d94
ms.sourcegitcommit: 3720ce4efb6735694cfb53a1b793d949af5d1bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/29/2017
---
# <a name="installing-windows-powershell"></a>Instalace prostředí Windows PowerShell

Prostředí PowerShell nainstalovaný ve výchozím nastavení v každé Windows od verze Windows 7 SP1 a Windows Server 2008 R2 SP1.

Uživatelé Linuxu, systému macOS a systému Windows, které chcete nainstalovat **prostředí PowerShell 6** (beta) ve své počítače, třeba:

1. Získat prostředí PowerShell pro konkrétní operační systém a verze, ze [Githubu](https://github.com/powershell/powershell#get-powershell)
1. Postupujte podle pokynů pro instalaci
  - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
  - [systému macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)
  - [Windows](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi)

6 prostředí PowerShell je také k dispozici pro Docker; v tématu [Docker instalace](https://github.com/PowerShell/PowerShell/tree/master/docker) pokyny.

## <a name="finding-powershell-in-windows-10-81-80-and-7"></a>Hledání prostředí PowerShell v systému Windows 10, 8.1, 8.0 a 7

Někdy vyhledání prostředí PowerShell konzoly nebo ISE (Integrované skriptovací prostředí) v systému Windows může být složité, jako jeho umístění přechází z jedné verze systému Windows na další.

Následující tabulky by měly pomoci při hledání prostředí PowerShell ve vaší verzi systému Windows.
Všechny verze tady jsou původní verze, vydání, s žádné aktualizace.

### <a name="for-console"></a>Pro konzolu

Verze | Umístění
-- | --
Windows 10 | Klikněte levém dolním rohu Windows ikonu, začněte psát prostředí PowerShell
Windows 8.1, 8.0 | Na obrazovce start začněte psát prostředí PowerShell.<br/>Pokud na ploše klikněte levém dolním rohu Windows ikonu, začněte psát prostředí PowerShell
Windows 7 s aktualizací SP1 | Klikněte na levém dolním rohu Windows ikonu, při spuštění pole hledání zadáte prostředí PowerShell

### <a name="for-ise"></a>Pro ISE

Verze | Umístění
-- | --
Windows 10 | Klikněte levém dolním rohu Windows ikonu, začněte psát ISE
Windows 8.1, 8.0 | Na obrazovce start zadejte **prostředí PowerShell ISE**.<br/>Pokud je na ploše, klikněte na ikonu Windows dolním rohu, zadejte **prostředí PowerShell ISE**
Windows 7 s aktualizací SP1 | Klikněte na levém dolním rohu Windows ikonu, při spuštění pole hledání zadáte prostředí PowerShell

## <a name="finding-powershell-in-windows-server-versions"></a>Hledání v systému Windows Server verze prostředí PowerShell

Od verze Windows Server 2008 R2, můžete nainstalovat operační systém Windows bez grafické uživatelské rozhraní (GUI).
Edice systému Windows Server bez grafického uživatelského rozhraní jsou pojmenované **základní** s názvem edice a edice s grafické uživatelské rozhraní **plochy**.

### <a name="windows-server-core-editions"></a>Edice systému Windows Server Core

Ve všech edicích základní při přihlášení k serveru zobrazí okno příkazového řádku systému Windows.

Typ `powershell` a stiskněte klávesu **ENTER** spuštění prostředí PowerShell v relaci příkazového řádku. Typ `exit` ukončit relaci prostředí PowerShell a vrátíte se do příkazového řádku.

### <a name="windows-server-desktop-editions"></a>Edice Windows serveru Desktop

Ve všech edicích plochy klikněte na ikonu Windows levém dolním rohu, začněte psát prostředí PowerShell.
Zobrazí konzole a možnosti ISE.

Jedinou výjimkou výše uvedené pravidlo je (ISE) v systému Windows Server 2008 R2 SP1; v takovém případě klikněte na ikonu Windows levém dolním rohu, zadejte PowerShell ISE.

## <a name="how-to-check-the-version-of-powershell"></a>Postupy: Kontrola verze prostředí PowerShell

K vyhledání, která verze prostředí PowerShell jste nainstalovali, spusťte konzolu PowerShell (nebo ISE) a typ `$PSVersionTable` a stiskněte klávesu **ENTER**.

## <a name="upgrading-existing-windows-powershell"></a>Upgrade stávající prostředí Windows PowerShell

Instalační balíček pro prostředí PowerShell dodává uvnitř instalační program WMF.
Verze Instalační služby WMF odpovídá verzi prostředí PowerShell; není k dispozici žádný samostatný instalační program pro prostředí Windows PowerShell.

Pokud je potřeba aktualizovat vaší stávající verzi prostředí PowerShell, v systému Windows, použijte v následující tabulce vyhledejte instalační program pro verzi prostředí PowerShell, které chcete aktualizovat.

Windows | PS 3.0 | PS 4.0 | PS 5.0 | PS 5.1 |
--|--|--|--|--|
Windows 10 (viz Note1)<br/>Windows Server 2016 | - | - | - | nainstalovaná
Windows 8.1<br/>Windows Server 2012 R2 | - | nainstalovaná | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
Windows 8<br/>Windows Server 2012 | nainstalovaná | [FORMÁT WMF 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
Windows 7 s aktualizací SP1<br/>Windows Server 2008 R2 SP1 | [PODPORA PRODUKTU WMF 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) | [FORMÁT WMF 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

> **Poznámka: 1**:
  >>
  >> Počáteční verze Windows 10 ve funkci Automatické aktualizace povolena získá z verze 5.0 pro 5.1 aktualizovat prostředí PowerShell.
  >>
  >> Pokud původní verzi Windows 10 není aktualizován prostřednictvím aktualizací systému Windows, verze prostředí PowerShell je 5.0.

## <a name="need-azure-powershell"></a>Třeba prostředí Azure PowerShell

Pokud hledáte **prostředí Azure PowerShell**, můžete začít s [Přehled prostředí Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure).

Co může být nutné, jinak je [nainstalovat a nakonfigurovat Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)

## <a name="see-also"></a>Viz také

- [Požadavky na prostředí PowerShell systému Windows](Windows-PowerShell-System-Requirements.md)
- [Spuštění prostředí Windows PowerShell](Starting-Windows-PowerShell.md)