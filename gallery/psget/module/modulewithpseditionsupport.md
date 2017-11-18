---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "Galerie prostředí powershell, rutiny, psget"
title: modulewithpseditionsupport
ms.openlocfilehash: 8122756b78e18fe55daef5c46dc299b87ddcaf1a
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="modules-with-compatible-powershell-editions"></a>Moduly s kompatibilní verze prostředí PowerShell
Od verze 5.1 je PowerShell k dispozici v různých edicích, které uvádějí různé sady funkcí a kompatibilitu platformy.

- **Desktop Edition:** Tato edice je založená na rozhraní .NET Framework a zajišťuje kompatibilitu se skripty a moduly cílenými na verze PowerShellu spouštěné na plných edicích Windows, jako je Jádro serveru a Windows Desktop.
- **Core Edition:** Tato edice je založená na rozhraní .NET Core a zajišťuje kompatibilitu se skripty a moduly cílenými na verze PowerShellu spouštěné na edicích Windows s nízkými nároky na prostředky, jako je Nano Server a Windows IoT.

## <a name="the-running-edition-of-powershell-is-shown-in-the-psedition-property-of-psversiontable"></a>Používaná verze PowerShellu je uvedena ve vlastnosti PSEdition parametru $PSVersionTable.
```powershell
$PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.14300.1000
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
CLRVersion                     4.0.30319.42000
BuildVersion                   10.0.14300.1000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

## <a name="module-authors-can-declare-their-modules-to-be-compatible-with-one-or-more-powershell-editions-using-the-compatiblepseditions-module-manifest-key-this-key-is-only-supported-on-powershell-51-or-later"></a>Autoři modulu mají možnost deklarovat své moduly jako kompatibilní s jednou nebo více edicemi PowerShellu, které používají klíč manifestu CompatiblePSEditions. Podporu tohoto klíče poskytují jenom prostředí PowerShell 5.1 nebo novější.
*Poznámka:* po modul manifestu je zadaný klíč CompatiblePSEditions, nelze jej importovat na nižší verze prostředí PowerShell.

```powershell
New-ModuleManifest -Path .\TestModuleWithEdition.psd1 -CompatiblePSEditions Desktop,Core -PowerShellVersion 5.1
$ModuleInfo = Test-ModuleManifest -Path .\TestModuleWithEdition.psd1
$ModuleInfo.CompatiblePSEditions
Desktop
Core

$ModuleInfo | Get-Member CompatiblePSEditions

   TypeName: System.Management.Automation.PSModuleInfo

Name                 MemberType Definition
----                 ---------- ----------
CompatiblePSEditions Property   System.Collections.Generic.IEnumerable[string] CompatiblePSEditions {get;}

```
Při získávání seznamu dostupných modulů můžete filtrovat seznam podle edice PowerShellu.
```powershell
Get-Module -ListAvailable -PSEdition Desktop

    Directory: C:\Program Files\WindowsPowerShell\Modules


ModuleType Version    Name                                ExportedCommands
---------- -------    ----                                ----------------
Manifest   1.0        ModuleWithPSEditions

Get-Module -ListAvailable -PSEdition Core | % CompatiblePSEditions
Desktop
Core

```

## <a name="module-authors-can-publish-a-single-module-targeting-to-either-or-both-powershell-editions-desktop-and-core"></a>Autoři modulu můžete publikovat v modulu single cílení na obojím prostředí PowerShell edice (Desktop a jader) 

Jeden modul může pracovat na ploše a základní verze, v tomto modulu má autor přidat požadované logiku v buď RootModule nebo v manifestu modulu pomocí $PSEdition proměnné.
Moduly může mít dvě sady cílené na CoreCLR a FullCLR zkompilované knihovny DLL.
Tady je několik možností balíček modulu s logiku pro načítání knihoven DLL správné.

### <a name="option-1-packaging-a-module-for-targeting-multiple-versions-and-multiple-editions-of-powershell"></a>Možnost 1: Zabalení modul pro cílení na více verzí a víc edicí prostředí PowerShell

#### <a name="module-folder-contents"></a>Obsah složky modulu
- Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll 
- Microsoft.Windows.PowerShell.ScriptAnalyzer.dll 
- PSScriptAnalyzer.psd1
- PSScriptAnalyzer.psm1
- ScriptAnalyzer.format.ps1xml
- ScriptAnalyzer.types.ps1xml
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll 
- coreclr\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll 
- en-US\about_PSScriptAnalyzer.help.txt
- en-US\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll-Help.xml
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.BuiltinRules.dll 
- PSv3\Microsoft.Windows.PowerShell.ScriptAnalyzer.dll 
- Settings\CmdletDesign.psd1
- Settings\DSC.psd1
- Settings\ScriptFunctions.psd1
- Settings\ScriptingStyle.psd1
- Settings\ScriptSecurity.psd1

#### <a name="contents-of-psscriptanalyzerpsd1-file"></a>Obsah souboru PSScriptAnalyzer.psd1

```powershell
@{
 
# Author of this module
Author = 'Microsoft Corporation'

# Script module or binary module file associated with this manifest.
RootModule = 'PSScriptAnalyzer.psm1'

# Version number of this module.
ModuleVersion = '1.6.1'

# ---
}
```

#### <a name="contents-of-psscriptanalyzerpsm1-file"></a>Obsah souboru PSScriptAnalyzer.psm1
Níže logiku načte požadovaná sestavení v závislosti na aktuální edice nebo verze.

```powershell
#
# Script module for module 'PSScriptAnalyzer'
#
Set-StrictMode -Version Latest

# Set up some helper variables to make it easier to work with the module
$PSModule = $ExecutionContext.SessionState.Module
$PSModuleRoot = $PSModule.ModuleBase

# Import the appropriate nested binary module based on the current PowerShell version
$binaryModuleRoot = $PSModuleRoot


if (($PSVersionTable.Keys -contains "PSEdition") -and ($PSVersionTable.PSEdition -ne 'Desktop')) {
    $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'coreclr'
}
else
{
    if ($PSVersionTable.PSVersion -lt [Version]'5.0') {
        $binaryModuleRoot = Join-Path -Path $PSModuleRoot -ChildPath 'PSv3'
    }    
}

$binaryModulePath = Join-Path -Path $binaryModuleRoot -ChildPath 'Microsoft.Windows.PowerShell.ScriptAnalyzer.dll'
$binaryModule = Import-Module -Name $binaryModulePath -PassThru

# When the module is unloaded, remove the nested binary module that was loaded with it
$PSModule.OnRemove = {
    Remove-Module -ModuleInfo $binaryModule
} 

```

### <a name="option-2-use-psedition-variable-in-the-psd1-file-to-load-the-proper-dlls-and-nestedrequired-modules"></a>Možnost 2: Použijte proměnnou $PSEdition v soubor PSD1 načíst správné knihovny DLL a vnořené/požadované moduly

V PS 5.1 nebo novější $PSEdition – globální proměnná je povolena v souboru manifestu modulu.
Pomocí této proměnné, Autor modulu můžete zadat podmíněného hodnoty v souboru manifestu modulu. $PSEdition proměnná může být odkaz v režimu s omezeným přístupem jazyk nebo datové části. 

*Poznámka:* po modul manifestu je zadán s klíčem CompatiblePSEditions nebo používá proměnnou $PSEdition, nelze jej importovat na nižší verze prostředí PowerShell.


#### <a name="sample-module-manifest-file-with-compatiblepseditions-key"></a>Ukázku souboru manifestu modulu klíčem CompatiblePSEditions

```powershell
@{ 
# - - -
 
# Script module or binary module file associated with this manifest.
RootModule = if($PSEdition -eq 'Core')
{
'coreclr\MyCoreClrRM.dll'
}
else # Desktop
{
'clr\MyFullClrRM.dll'
}
 
# Supported PSEditions
CompatiblePSEditions = 'Desktop', 'Core'
 
# Modules to import as nested modules of the module specified in RootModule/ModuleToProcess
NestedModules = if($PSEdition -eq 'Core')
{
'coreclr\MyCoreClrNM1.dll',
'coreclr\MyCoreClrNM2.dll'
}
else # Desktop
{
'clr\MyFullClrNM1.dll',
'clr\MyFullClrNM2.dll'
}
 
# -- - -
}
```

#### <a name="module-contents"></a>Obsah modulu

```powershell

PS C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions> dir -Recurse
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
d-----         7/5/2016   1:37 PM                clr                                                                                 
d-----         7/5/2016   1:36 PM                coreclr                                                                             
-a----         7/5/2016   1:34 PM           4906 ModuleWithEditions.psd1                                                             
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\clr
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
-a----         7/5/2016   1:35 PM              0 MyFullClrNM1.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyFullClrNM2.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyFullClrRM.dl                                                                      
 
    Directory: C:\Users\manikb\Documents\WindowsPowerShell\Modules\ModuleWithEditions\coreclr
 
Mode                LastWriteTime         Length Name                                                                                
----                -------------         ------ ----                                                                                
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM1.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyCoreClrNM2.dll                                                                    
-a----         7/5/2016   1:35 PM              0 MyCoreClrRM.dl                                                                      
```

## <a name="powershell-gallery-users-can-find-the-list-of-modules-supported-on-a-specific-powershell-edition-using-tags-pseditiondesktop-and-pseditoncore"></a>Galerie prostředí PowerShell můžou uživatelé najít seznamu modulů, které jsou podporovány na konkrétní verzi prostředí PowerShell pomocí značek PSEdition_Desktop a PSEditon_Core.
Moduly bez PSEdition_Desktop a PSEditon_Core značky jsou považovány za bez problémů fungují na edice Desktop prostředí PowerShell.

```powershell

# Find modules supported on PowerShell Desktop edition
Find-Module -Tag PSEditon_Desktop

# Find modules supported on PowerShell Core editions
Find-Module -Tag PSEditon_Core

```


## <a name="more-details"></a>Další informace
### <a name="scripts-with-pseditionsscriptscriptwithpseditionsupportmd"></a>[Skripty s PSEditions](../script/scriptwithpseditionsupport.md)
### <a name="pseditions-support-on-powershellgallerypsgallerypsgallerypseditionsmd"></a>[Podpora PSEditions na PowerShellGallery](../../psgallery/psgallery_pseditions.md)
### <a name="update-module-manifest-psgetupdate-modulemanifestmd"></a>[Aktualizace modulu manifest] (./psget_update-modulemanifest.md)
