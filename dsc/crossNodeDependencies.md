---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "Určení závislostí mezi uzly"
ms.openlocfilehash: 885c130fb050629aac4c072e18a147d77b9deb8f
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/27/2017
---
# <a name="specifying-cross-node-dependencies"></a>Určení závislostí mezi uzly

> Platí pro: Prostředí Windows PowerShell 5.0

DSC poskytuje speciální prostředky **WaitForAll**, **WaitForAny**, a **WaitForSome** který lze použít v konfiguracích k určení závislostí na konfigurace na dalších uzly. Chování těchto prostředků je následující:

* **WaitForAll**: úspěšná, pokud je zadaný prostředek s požadovaným stavem na všechny cílové uzly, které jsou definované v **NodeName** vlastnost.
* **WaitForAny**: úspěšná, pokud je zadaný prostředek s požadovaným stavem na alespoň jeden z cílových uzlů definované v **NodeName** vlastnost.
* **WaitForSome**: Určuje **NodeCount** vlastnost kromě **NodeName** vlastnost. Prostředek úspěšné, pokud je v požadovaném stavu na minimální počet uzlů (zadáno v **NodeCount**) definované **NodeName** vlastnost. 

## <a name="using-waitforxxxx-resources"></a>Pomocí WaitForXXXX prostředků

Použít **WaitForXXXX** prostředky, vytvořit blok prostředků tohoto typu prostředků, které určuje prostředek DSC a uzly pro čekání. Pak použijete **DependsOn** blokuje vlastnost v jiných prostředků ve vaší konfiguraci čekat podmínky uvedené v **WaitForXXXX** uzlu proběhla úspěšně.

Například v následující konfiguraci cílový uzel čeká **xADDomain** prostředků na dokončení na **MyDC** uzel s maximálně 30 opakování, v intervalech 15 sekund, než Cílový uzel můžete připojit k doméně.

```powershell
Configuration JoinDomain

{
    Import-DscResource -Module xComputerManagement, xActiveDirectory

    Node myDC
    {
        WindowsFeature InstallAD
        {
            Ensure = 'Present' 
            Name = 'AD-Domain-Services' 
        }

        xADDomain NewDomain 
        { 
            DomainName = 'Contoso.com'            
            DomainAdministratorCredential = (Get-Credential)
            SafemodeAdministratorPassword = (Get-Credential)
            DatabasePath = "C:\Windows\NTDS"
            LogPath = "C:\Windows\NTDS"
            SysvolPath = "C:\Windows\Sysvol"
        }

    }

    Node myDomainJoinedServer
    {

        WaitForAll DC
        {
            ResourceName      = '[xADDomain]NewDomain'
            NodeName          = 'MyDC'
            RetryIntervalSec  = 15
            RetryCount        = 30
        }

        xComputer JoinDomain
        {
            Name             = 'myPC'
            DomainName       = 'Contoso.com'
            Credential       = (Get-Credential)
            DependsOn        ='[WaitForAll]DC'
        }
    }
}
```

>**Poznámka:** ve výchozím nastavení WaitForXXX prostředky zkuste jednou a pak neúspěšné. I když to není nutné, obvykle můžete zadat interval opakování a počet.

## <a name="see-also"></a>Viz také
* [Konfigurace DSC](configurations.md)
* [Prostředky DSC](resources.md)
* [Konfigurace správce místní konfigurace](metaConfig.md)
