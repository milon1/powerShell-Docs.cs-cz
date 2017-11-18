---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "Přihlašovací údaje uživatele s DSC"
ms.openlocfilehash: f15b2e4bfb888e2f3646a33cc0191e33a7ebb8ab
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="running-dsc-with-user-credentials"></a>Přihlašovací údaje uživatele s DSC 

> Platí pro: Prostředí Windows PowerShell 5.0, 5.1 prostředí Windows PowerShell

Prostředek DSC pod zadanou sadu přihlašovacích údajů můžete spustit pomocí automatického **PsDscRunAsCredential** vlastnosti v konfiguraci. Ve výchozím nastavení spouští DSC každý prostředek, jako systémový účet.
Existují situace, kdy spuštěná jako uživatel je nezbytné, například instalaci balíčky MSI v kontextu konkrétního uživatele, nastavení klíče registru uživatele, přístup k určité místní adresáře uživatele nebo přístup k síti sdílet.

Má každý prostředek DSC **PsDscRunAsCredential** vlastnost, která může být nastaven na všechny přihlašovací údaje uživatele ( [PSCredential](https://msdn.microsoft.com/en-us/library/ms572524(v=VS.85).aspx) objekt).
Přihlašovací údaje mohou být pevně zakódované jako hodnota vlastnosti v konfiguraci, nebo nastavte hodnotu na [Get-Credential](https://technet.microsoft.com/en-us/library/hh849815.aspx), který se zobrazí výzva pro pověření při kompilaci (pro informace o konfiguraci kompilování konfigurace, najdete v části [konfigurace](configurations.md).

>**Poznámka:** v prostředí PowerShell 5.0, pomocí **PsDscRunAsCredential** vlastnost v konfiguracích volání složené prostředků nebyla podporována. 
>V prostředí PowerShell 5.1 **PsDscRunAsCredential** vlastnost je podporována v konfiguracích volání složené prostředky.

>**Poznámka:** **PsDscRunAsCredential** vlastnost není k dispozici v prostředí PowerShell 4.0.

V následujícím příkladu **Get-Credential** se používá k vyzvat uživatele k zadání přihlašovacích údajů. [Registru](registryResource.md) prostředků se používá ke změně klíč registru, který určuje barvu pozadí pro okno příkazového řádku systému Windows.

```powershell
Configuration ChangeCmdBackGroundColor
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        Registry CmdPath
        {
            Key                  = 'HKEY_CURRENT_USER\SOFTWARE\Microsoft\Command Processor'
            ValueName            = 'DefaultColor'
            ValueData            = '1F'
            ValueType            = 'DWORD'
            Ensure               = 'Present'
            Force                = $true
            Hex                  = $true
            PsDscRunAsCredential = Get-Credential
        }
    }
}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost';
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}

ChangeCmdBackGroundColor -ConfigurationData $configData
```
>**Poznámka:** tento příklad předpokládá, že máte platný certifikát v `C:\publicKeys\targetNode.cer`, a že kryptografický otisk certifikátu je hodnota použitá.
>Informace o šifrování pověření v souborech MOF konfigurace DSC najdete v tématu [zabezpečení souboru MOF](secureMOF.md).
