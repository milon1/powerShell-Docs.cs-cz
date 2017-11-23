# [Přehled Windows Management Frameworku (WMF)](README.md)

# [WMF 5.1](5.1/release-notes.md)
## [Nové scénáře a funkce](5.1/scenarios-features.md)
### [Vylepšení platformy Desired State Configuration (DSC)](5.1/DSC-improvements.md)
### [Vylepšení powershellové konzoly](5.1/console-improvements.md)
### [Vylepšení powershellového jádra](5.1/engine-improvements.md)
### [Vylepšení správy balíčků](5.1/package-management-improvements.md)
### [Vylepšení funkce JEA](5.1/jea-improvements.md)
### [Katalogové rutiny](5.1/catalog-cmdlets.md)
### [Opravy chyb ve WMF 5.1](5.1/bugfixes.md)
## [Instalace a konfigurace](5.1/install-configure.md)
## [Známé problémy](5.1/known-issues.md)
## [Kompatibilita](5.1/Compatibility.md)
## [Kompatibilita produktů](5.1/productincompat.md)

# [WMF 5.0](5.0/releasenotes.md)
## [Podrobné informace o instalaci](5.0/requirements.md)
## [Známé problémy a omezení](5.0/limitation_overview.md)
### [Známé problémy platformy Desired State Configuration (DSC)](5.0/limitation_dsc.md)
## [Stav kompatibility produktů](5.0/productincompat.md)
## [Scénáře povolené ve WMF 5.0]()
### [Funkce Just Enough Administration (JEA)](5.0/jea_overview.md)
#### [Vytvoření koncového bodu JEA a připojení k tomuto bodu](5.0/jea_endpoint.md)
#### [Hlášení o JEA](5.0/jea_report.md)
### [Vytváření vlastních typů pomocí tříd PowerShellu](5.0/class_overview.md)
#### [Definování vlastních typů](5.0/class_newtype.md)
#### [Deklarace základní třídy](5.0/class_base.md)
#### [Deklarace implementovaného rozhraní](5.0/class_interface.md)
#### [Volání konstruktoru základní třídy](5.0/class_baseconstructor.md)
#### [Volání metody základní třídy](5.0/class_basemethod.md)
### [Vylepšené ladění powershellového skriptu](5.0/debug_overview.md)
### [Vylepšení platformy Desired State Configuration (DSC)](5.0/dsc_improvements.md)
#### [Konfigurace]()
##### [Určení závislostí mezi uzly](5.0/dsc_waitfor.md)
##### [Šifrované soubory MOF](5.0/dsc_encryptedmof.md)
##### [Nápověda a podpora ke konfiguraci DSC](5.0/dsc_confighelp.md)
##### [Lepší vytváření v PowerShell ISE](5.0/dsc_authoring.md)
##### [Povolení identických duplicitních prostředků v konfiguraci](5.0/dsc_identicalduplicate.md)
##### [Klíčové slovo Import-DscResource podporuje parametr -ModuleVersion](5.0/dsc_importdscresource.md)
##### [Podpora konfiguračního klíčového slova v subsystému WOW64](5.0/dsc_wow64.md)
#### [Prostředky]()
##### [Prostředky DSC založené na třídě](5.0/dsc_classbasedresource.md)
##### [Ladění skriptů prostředků DSC](5.0/dsc_resourcedebugging.md)
##### [Automatická podpora funkce RunAs u prostředků DSC](5.0/dsc_runas.md)
##### [Souběžná podpora verzí prostředků DSC](5.0/dsc_sxsresource.md)
##### [Nové integrované prostředky](5.0/dsc_newresources.md)
#### [Local Configuration Manager]()
##### [Konfigurace uzlu několika konfiguračními fragmenty](5.0/dsc_partialconfig.md)
###### [Podpora smíšených režimů RefreshMode](5.0/dsc_partialconfig_mixedmode.md)
##### [Konfigurace jádra DSC novým atributem](5.0/dsc_metaconfiguration.md)
##### [Podrobné informace o stavu LCM](5.0/dsc_lcmstate.md)
##### [Frekvence RefreshMode a ConfigurationMode nemusí odpovídat vzájemnému součinu](5.0/dsc_freqnomultiple.md)
##### [Další hodnota vlastnosti RefreshMode](5.0/dsc_refreshmode.md)
#### [Rutiny]()
##### [Podrobné informace o stavu konfigurace](5.0/dsc_getconfigurationstatus.md)
##### [Rutina Test-DscConfiguration podporuje referenční konfigurace](5.0/dsc_testconfiguration.md)
##### [Přímý přístup k metodám prostředků DSC](5.0/dsc_directaccess.md)
##### [Dodání konfiguračního dokumentu bez jeho použití](5.0/dsc_publishconfig.md)
##### [Odebrání dokumentů DSC](5.0/dsc_removeconfigdoc.md)
##### [Jednotné vyjádření stavu](5.0/dsc_statestatus.md)
##### [Rutina Set-DscLocalConfigurationManager podporuje parametr -Force](5.0/dsc_setdsclcm.md)
#### [Režim načítání]()
##### [Načítání konfigurací DSC na vyžádání](5.0/dsc_updateconfig.md)
##### [Oddělení ID uzlu od ID konfigurace](5.0/dsc_nodeid.md)
##### [Oddělení úložišť konfigurace, prostředků a sestav](5.0/dsc_repository.md)
##### [Hlášení stavu konfigurace na centrální místo](5.0/dsc_reporting.md)
### [Použití přepisu a protokolování k auditování využití PowerShellu](5.0/audit_overview.md)
#### [Vylepšené možnosti přepisu](5.0/audit_transcript.md)
#### [Trasování a protokolování skriptu](5.0/audit_script.md)
#### [Rutiny Cryptographic Message Syntax (CMS)](5.0/audit_cms.md)
### [Použití správce balíčků ke zjišťování, instalaci a uchovávání softwaru](5.0/oneget_overview.md)
#### [Rutiny správce balíčků](5.0/oneget_cmdlets.md)
### [Použití správce balíčků PowerShellGet ke zjišťování, instalaci a uchovávání powershellových modulů](5.0/psget_module_overview.md)
#### [Registrace powershellového úložiště](5.0/psget_psrepository.md)
#### [Souběžná podpora verzí v PowerShellu 5.0 a v novějších verzích](5.0/psget_modulesxsinstall.md)
#### [Instalace závislostí modulů](5.0/psget_moduledependency.md)
#### [Rutiny správce balíčků PowerShellGet pro správu modulů](5.0/psget_modulecmdlets.md)
### [Použití správce balíčků PowerShelGet ke zjišťování, instalaci a správě powershellových skriptů](5.0/psget_script_overview.md)
#### [Rutiny správce balíčků PowerShellGet pro správu skriptů](5.0/psget_scriptcmdlets.md)
### [Nové a aktualizované rutiny založené na připomínkách komunity](5.0/feedback_cmdlets.md)
#### [Symbolické odkazy využívající rutiny položek](5.0/feedback_symbolic.md)
#### [Rutiny archivu](5.0/feedback_archive.md)
#### [Rutiny schránky](5.0/feedback_clipboard.md)
#### [Rutina Convert-String](5.0/feedback_convertstring.md)
#### [Extrakce a analýza strukturovaných objektů mimo řetězec](5.0/feedback_convertfromString.md)
#### [Rutina Format-Hex](5.0/feedback_formathex.md)
#### [Parametr NoNewLine](5.0/feedback_nonewline.md)
#### [Rutina New-TemporaryFile](5.0/feedback_tempfile.md)
#### [Rutina New-Guid](5.0/feedback_newguid.md)
#### [Rutina Get-ChildItem má parametr -Depth](5.0/feedback_getchilditem.md)
#### [Aktualizace objektu FileInfo](5.0/feedback_fileinfo.md)
#### [Podpora modulů při deklaraci rozsahů verzí (1.* atd.)](5.0/feedback_moduleversionranges.md)
### [Informační stream](5.0/informationstream_overview.md)
### [Generování powershellových rutin na základě koncového bodu OData](5.0/odata_overview.md)
### [Použití PowerShellu ke správě síťového přepínače](5.0/networkswitch_overview.md)
### [Protokolování softwarového inventáře (SIL)](5.0/sil_overview.md)