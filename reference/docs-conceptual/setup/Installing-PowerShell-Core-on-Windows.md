# <a name="installing-powershell-core-on-windows"></a><span data-ttu-id="27101-101">Instalace jádra prostředí PowerShell v systému Windows</span><span class="sxs-lookup"><span data-stu-id="27101-101">Installing PowerShell Core on Windows</span></span>

## <a name="msi"></a><span data-ttu-id="27101-102">MSI</span><span class="sxs-lookup"><span data-stu-id="27101-102">MSI</span></span>

<span data-ttu-id="27101-103">K instalaci prostředí PowerShell na Windows serveru nebo klienta Windows (funguje v Server 2008 R2, Windows 7 SP1 a novější), stáhněte balíček Instalační služby MSI</span><span class="sxs-lookup"><span data-stu-id="27101-103">To install PowerShell on a Windows client or Windows Server (works on Windows 7 SP1, Server 2008 R2, and later), download the MSI package from</span></span>
<!-- TODO: either the Download Center or -->
<span data-ttu-id="27101-104">Naše Githubu [uvolní][] stránky.</span><span class="sxs-lookup"><span data-stu-id="27101-104">our GitHub [releases][] page.</span></span>
<span data-ttu-id="27101-105">Soubor MSI vypadá takto-`PowerShell-6.0.0.<buildversion>.<os-arch>.msi`</span><span class="sxs-lookup"><span data-stu-id="27101-105">The MSI file looks like this - `PowerShell-6.0.0.<buildversion>.<os-arch>.msi`</span></span>

<span data-ttu-id="27101-106">Po stažení poklikejte na instalační program a postupujte podle pokynů.</span><span class="sxs-lookup"><span data-stu-id="27101-106">Once downloaded, double-click the installer and follow the prompts.</span></span>

<span data-ttu-id="27101-107">Je umístěn v nabídce Start po instalaci zástupce.</span><span class="sxs-lookup"><span data-stu-id="27101-107">There is a shortcut placed in the Start Menu upon installation.</span></span>

* <span data-ttu-id="27101-108">Ve výchozím nastavení je balíček nainstalován do`$env:ProgramFiles\PowerShell\`</span><span class="sxs-lookup"><span data-stu-id="27101-108">By default the package is installed to `$env:ProgramFiles\PowerShell\`</span></span>
* <span data-ttu-id="27101-109">Můžete spustit prostředí PowerShell pomocí nabídky Start nebo`$env:ProgramFiles\PowerShell\pwsh.exe`</span><span class="sxs-lookup"><span data-stu-id="27101-109">You can launch PowerShell via the Start Menu or `$env:ProgramFiles\PowerShell\pwsh.exe`</span></span>

### <a name="prerequisites"></a><span data-ttu-id="27101-110">Předpoklady</span><span class="sxs-lookup"><span data-stu-id="27101-110">Prerequisites</span></span>

<span data-ttu-id="27101-111">Pokud chcete povolit vzdálenou komunikaci prostředí PowerShell přes WSMan, musí být splněny následující požadavky:</span><span class="sxs-lookup"><span data-stu-id="27101-111">To enable PowerShell remoting over WSMan, the following prerequisites need to be met:</span></span>

* <span data-ttu-id="27101-112">Nainstalujte [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) na verze Windows starší než Windows 10.</span><span class="sxs-lookup"><span data-stu-id="27101-112">Install the [Universal C Runtime](https://www.microsoft.com/download/details.aspx?id=50410) on Windows versions prior to Windows 10.</span></span>
  <span data-ttu-id="27101-113">Je k dispozici prostřednictvím přímé stahování nebo Windows Update.</span><span class="sxs-lookup"><span data-stu-id="27101-113">It is available via direct download or Windows Update.</span></span>
  <span data-ttu-id="27101-114">Opravit plně (včetně volitelné balíčky), podporované systémy budou už máte to nainstalována.</span><span class="sxs-lookup"><span data-stu-id="27101-114">Fully patched (including optional packages), supported systems will already have this installed.</span></span>
* <span data-ttu-id="27101-115">Nainstalovat Windows Management Framework (WMF) [4.0](https://www.microsoft.com/download/details.aspx?id=40855) nebo novější ([5.1](https://www.microsoft.com/download/details.aspx?id=54616)) v systému Windows 7 a Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="27101-115">Install the Windows Management Framework (WMF) [4.0](https://www.microsoft.com/download/details.aspx?id=40855) or newer ([5.1](https://www.microsoft.com/download/details.aspx?id=54616)) on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="zip"></a><span data-ttu-id="27101-116">ZIP</span><span class="sxs-lookup"><span data-stu-id="27101-116">ZIP</span></span>

<span data-ttu-id="27101-117">Prostředí PowerShell binární ZIP archivy umožňujících pokročilé scénáře nasazení.</span><span class="sxs-lookup"><span data-stu-id="27101-117">PowerShell binary ZIP archives are provided to enable advanced deployment scenarios.</span></span>
<span data-ttu-id="27101-118">Potřeba poznamenat, že při použití archivu ZIP, nebude získat kontrolu požadovaných součástí jako balíček Instalační služby MSI.</span><span class="sxs-lookup"><span data-stu-id="27101-118">Be noted that when using the ZIP archive, you won't get the prerequisites check as in the MSI package.</span></span>
<span data-ttu-id="27101-119">Proto, aby pro vzdálenou komunikaci přes WSMan fungovat správně v systému Windows verze starší než Windows 10, musíte zajistit [požadavky](#prerequisites) jsou splněny.</span><span class="sxs-lookup"><span data-stu-id="27101-119">So in order for remoting over WSMan to work properly on Windows versions prior to Windows 10, you need to make sure the [prerequisites](#prerequisites) are met.</span></span>

## <a name="deploying-on-nano-server"></a><span data-ttu-id="27101-120">Nasazení na Nano Server</span><span class="sxs-lookup"><span data-stu-id="27101-120">Deploying on Nano Server</span></span>

<span data-ttu-id="27101-121">Tyto pokyny předpokládají, že na bitovou kopii Nano Server je již spuštěna verze prostředí PowerShell a že má být vygenerováno [Nano Server Image Builder](https://technet.microsoft.com/windows-server-docs/get-started/deploy-nano-server).</span><span class="sxs-lookup"><span data-stu-id="27101-121">These instructions assume that a version of PowerShell is already running on the Nano Server image and that it has been generated by the [Nano Server Image Builder](https://technet.microsoft.com/windows-server-docs/get-started/deploy-nano-server).</span></span>
<span data-ttu-id="27101-122">Nano Server je "bezobslužných" operačního systému a nasazení binárních souborů jádra prostředí PowerShell může dojít, dvěma různými způsoby:</span><span class="sxs-lookup"><span data-stu-id="27101-122">Nano Server is a "headless" OS and deployment of PowerShell Core binaries can happen in two different ways:</span></span>

1. <span data-ttu-id="27101-123">Offline – připojit virtuální pevný disk Nano Server a rozbalte obsah souboru zip do zvoleného umístění v rámci připojené image.</span><span class="sxs-lookup"><span data-stu-id="27101-123">Offline - Mount the Nano Server VHD and unzip the contents of the zip file to your chosen location within the mounted image.</span></span>
1. <span data-ttu-id="27101-124">Online – přenos souboru zip přes relaci prostředí PowerShell a rozbalte ho do zvoleného umístění.</span><span class="sxs-lookup"><span data-stu-id="27101-124">Online - Transfer the zip file over a PowerShell Session and unzip it in your chosen location.</span></span>

<span data-ttu-id="27101-125">V obou případech budete potřebovat verze Windows 10 x64 Zip balíček a bude nutné ke spuštění příkazů v rámci instance prostředí PowerShell "Administrator".</span><span class="sxs-lookup"><span data-stu-id="27101-125">In both cases, you will need the Windows 10 x64 Zip release package and will need to run the commands within an "Administrator" PowerShell instance.</span></span>

### <a name="offline-deployment-of-powershell-core"></a><span data-ttu-id="27101-126">Offline nasazení jádra prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="27101-126">Offline Deployment of PowerShell Core</span></span>

1. <span data-ttu-id="27101-127">Rozbalte balíček do adresáře v rámci připojené image Nano Server pomocí nástroje vaše oblíbené zip.</span><span class="sxs-lookup"><span data-stu-id="27101-127">Use your favorite zip utility to unzip the package to a directory within the mounted Nano Server image.</span></span>
1. <span data-ttu-id="27101-128">Odpojení bitové kopie a spustit ho.</span><span class="sxs-lookup"><span data-stu-id="27101-128">Unmount the image and boot it.</span></span>
1. <span data-ttu-id="27101-129">Připojte k instanci doručené pošty prostředí Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27101-129">Connect to the inbox instance of Windows PowerShell.</span></span>
1. <span data-ttu-id="27101-130">Postupujte podle pokynů pro vytvoření koncového bodu vzdálené komunikace pomocí [jiná instance technika](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="27101-130">Follow the instructions to create a remoting endpoint using the [another instance technique](#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

### <a name="online-deployment-of-powershell-core"></a><span data-ttu-id="27101-131">Online nasazení jádra prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="27101-131">Online Deployment of PowerShell Core</span></span>

<span data-ttu-id="27101-132">Následující postup vás provede nasazení jádra prostředí PowerShell pro spuštěnou instanci Nano Server a konfiguraci jeho vzdálený koncový bod.</span><span class="sxs-lookup"><span data-stu-id="27101-132">The following steps will guide you through the deployment of PowerShell Core to a running instance of Nano Server and the configuration of its remote endpoint.</span></span>

* <span data-ttu-id="27101-133">Připojte se k instanci doručené pošty prostředí Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="27101-133">Connect to the inbox instance of Windows PowerShell</span></span>

```powershell
$session = New-PSSession -ComputerName <Nano Server IP address> -Credential <An Administrator account on the system>
```

* <span data-ttu-id="27101-134">Zkopírujte soubor do instance Nano Server</span><span class="sxs-lookup"><span data-stu-id="27101-134">Copy the file to the Nano Server instance</span></span>

```powershell
Copy-Item <local PS Core download location>\powershell-<version>-win-x64.zip c:\ -ToSession $session
```

* <span data-ttu-id="27101-135">Zadejte relaci</span><span class="sxs-lookup"><span data-stu-id="27101-135">Enter the session</span></span>

```powershell
Enter-PSSession $session
```

* <span data-ttu-id="27101-136">Extrahujte soubor Zip</span><span class="sxs-lookup"><span data-stu-id="27101-136">Extract the Zip file</span></span>

```powershell
# Insert the appropriate version.
Expand-Archive -Path C:\powershell-<version>-win-x64.zip -DestinationPath "C:\PowerShellCore_<version>"
```

* <span data-ttu-id="27101-137">Pokud chcete založená na službě WSMan vzdálenou komunikaci, postupujte podle pokynů pro vytvoření koncového bodu vzdálené komunikace pomocí [jiná instance technika](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span><span class="sxs-lookup"><span data-stu-id="27101-137">If you want WSMan-based remoting, follow the instructions to create a remoting endpoint using the [another instance technique](../core-powershell/WSMan-Remoting-in-PowerShell-Core.md#executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register).</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="27101-138">Pokyny k vytvoření koncového bodu vzdálené komunikace</span><span class="sxs-lookup"><span data-stu-id="27101-138">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="27101-139">Prostředí PowerShell jádro podporuje protokol vzdálenou komunikaci prostředí PowerShell (PSRP) prostřednictvím služby WSMan a SSH.</span><span class="sxs-lookup"><span data-stu-id="27101-139">PowerShell Core supports the PowerShell Remoting Protocol (PSRP) over both WSMan and SSH.</span></span> <span data-ttu-id="27101-140">Další informace viz:</span><span class="sxs-lookup"><span data-stu-id="27101-140">For more information, see:</span></span>

* <span data-ttu-id="27101-141">[SSH vzdálenou komunikaci prostředí PowerShell jádra][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="27101-141">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
* <span data-ttu-id="27101-142">[Vzdálená komunikace WSMan v prostředí PowerShell jádra][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="27101-142">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="artifact-installation-instructions"></a><span data-ttu-id="27101-143">Pokyny k instalaci artefaktů</span><span class="sxs-lookup"><span data-stu-id="27101-143">Artifact Installation Instructions</span></span>

<span data-ttu-id="27101-144">Publikujeme archiv s CoreCLR bity na každé položky konfigurace sestavení s [AppVeyor][].</span><span class="sxs-lookup"><span data-stu-id="27101-144">We publish an archive with CoreCLR bits on every CI build with [AppVeyor][].</span></span>

## <a name="coreclr-artifacts"></a><span data-ttu-id="27101-145">Artefakty CoreCLR</span><span class="sxs-lookup"><span data-stu-id="27101-145">CoreCLR Artifacts</span></span>

* <span data-ttu-id="27101-146">Stáhněte si balíček zip z **artefakty** kartě konkrétní sestavení.</span><span class="sxs-lookup"><span data-stu-id="27101-146">Download zip package from **artifacts** tab of the particular build.</span></span>
* <span data-ttu-id="27101-147">Soubor zip odblokovat: klikněte pravým tlačítkem v Průzkumníku souborů -> Vlastnosti -> zaškrtávací políčko -> odblokovat použít</span><span class="sxs-lookup"><span data-stu-id="27101-147">Unblock zip file: right-click in File Explorer -> Properties -> check 'Unblock' box -> apply</span></span>
* <span data-ttu-id="27101-148">Extrahujte soubor zip do `bin` adresáře</span><span class="sxs-lookup"><span data-stu-id="27101-148">Extract zip file to `bin` directory</span></span>
* `./bin/pwsh.exe`

<!-- [download-center]: TODO -->
[uvolní]: https://github.com/PowerShell/PowerShell/releases
[signing]: ../../tools/Sign-Package.ps1
[ssh-remoting]: ../core-powershell/SSH-Remoting-in-PowerShell-Core.md
[wsman-remoting]: ../core-powershell/WSMan-Remoting-in-PowerShell-Core.md
[AppVeyor]: https://ci.appveyor.com/project/PowerShell/powershell
