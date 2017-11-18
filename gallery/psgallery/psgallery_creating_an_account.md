---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "Galerie prostředí powershell, rutiny, psgallery"
title: "Vytvoření účtu Galerie prostředí PowerShell"
ms.openlocfilehash: e21575320f220c1ba7ecd9bd464a814b3ebf49d9
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
## <a name="creating-a-powershell-gallery-account"></a>Vytvoření účtu Galerie prostředí PowerShell

Před publikováním nic do Galerie prostředí PowerShell, je nutné vytvořit účet Galerie prostředí PowerShell. Galerie prostředí PowerShell účty musí být propojena s povoleným e-mailu účtu Azure Active Directory nebo e-mailový účet Microsoft (s doménou outlook.com, hotmail.com, atd.)

Chcete-li vytvořit účet Galerie prostředí PowerShell, přejděte na https://PowerShellGallery.com a klikněte na "Register" (viz následující obrázek). 

![Zaregistrovat nový účet](./images/CreatingAccount-Register.png)

Na další stránce Pokud chcete používat účet služby Azure Active Directory, vyberte "Pracovní nebo školní účet" a přihlaste se pomocí účtu. Použít účet Microsoft - například ten, který v doméně Hotmail.com nebo Outlook.com – zvolte "Osobní účet" a přihlaste se. 

Jakmile jste přihlášení, vyzve k vytvoření uživatelské jméno pro galerii prostředí PowerShell. Přečtěte si podmínky použití a zásady ochrany osobních údajů, které jsou propojeny v, zadejte uživatelské jméno a potom kliknutím na tlačítko Registrovat.

Poznámka: Tento název účtu nelze změnit po vytvoření.  
V tématu [Správa vlastníků položky](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/managing-item-owners) další podrobnosti týkající se to.

## <a name="recommended-practices-for-powershell-gallery-accounts"></a>Doporučené postupy pro účty Galerie prostředí PowerShell

Je důležité, aby e-mailový účet, který používá s vaším účtem Galerie prostředí PowerShell aktivně sledovat.
Všechny communiction s vlastníci položky galerie prostředí PowerShell je e-mailem na adresu spojenou s vaším účtem Galerie prostředí PowerShell.
Pokud jsme nelze kontaktovat vlastníka položek, může být provozní tým nutné odstranit položku za určitých okolností.

Organizace, které často publikovat do Galerie prostředí PowerShell vytvořit jedinečný účet pro tento účel v Outlook.com nebo jiné domény, účet Microsoft.
V mnoha případech není pravidelně sledovat tento účet. Osvědčeným postupem je v takovém případě používat předávání Outlook k odesílání e-mailu na jiný účet, obvykle jednu v rámci organizace, které se budou monitorovat pomocí položky vlastníka/vlastníků.

Pokud existují více vlastníky přidružený k položce, bude veškerá komunikace, které pocházejí z Galerie Powershellu přejděte na všechny vlastníky.
V tématu [Správa vlastníků položky](https://msdn.microsoft.com/en-us/powershell/gallery/psgallery/managing-item-owners) další podrobnosti o přidání vlastníky k položce. 
