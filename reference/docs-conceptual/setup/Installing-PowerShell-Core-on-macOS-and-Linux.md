# <a name="installing-powershell-core-on-macos-and-linux"></a>Instalace jádra prostředí PowerShell v systému macOS a Linux

Podporuje [Ubuntu 14.04][u14], [Ubuntu 16.04][u16], [Ubuntu č. 17.04] [ u17], [Debian 8][deb8], [Debian 9][deb9], [CentOS 7] [ cos], [Red Hat Enterprise Linux (RHEL) 7][rhel7], [OpenSUSE 42.2][opensuse], [Fedora 25 ] [ fed25], [Fedora 26][fed26], [Arch Linux][arch]a [systému macOS 10.12][mac].

Pro Linux distribuce, které nejsou oficiálně podporované, můžete se pokusit [prostředí PowerShell AppImage][lai].
Můžete také zkusit nasazení binárních souborů prostředí PowerShell přímo pomocí sady Linux [ `tar.gz` archivu][tar], ale je potřeba nastavit podle operačního systému v samostatné kroky potřebné závislosti.

Všechny balíčky jsou k dispozici na našem Githubu [uvolní][] stránky.
Spustit po instalaci balíčku `pwsh` z terminálu.

[u14]: #ubuntu-1404
[u16]: #ubuntu-1604
[u17]: #ubuntu-1704
[deb8]: #debian-8
[deb9]: #debian-9
[cos]: #centos-7
[rhel7]: #red-hat-enterprise-linux-rhel-7
[opensuse]: #opensuse-422
[fed25]: #fedora-25
[fed26]: #fedora-26
[arch]: #arch-linux
[lai]: #linux-appimage
[mac]: #macos-1012
[tar]: #binary-archives

## <a name="ubuntu-1404"></a>Ubuntu 14.04

### <a name="installation-via-package-repository---ubuntu-1404"></a>Instalaci přes úložiště balíčků - Ubuntu 14.04

Základní prostředí PowerShell pro Linux, je publikovaný na balíček úložiště pro Snadná instalace (a aktualizace).
Toto je upřednostňovaná metoda.

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/14.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, od toho stačí použít `sudo apt-get upgrade powershell` jej aktualizovat.

### <a name="installation-via-direct-download---ubuntu-1404"></a>Instalace prostřednictvím přímé stahování - Ubuntu 14.04

Stáhněte si balíček Debian `powershell_6.0.0-rc-1.ubuntu.14.04_amd64.deb` z [uvolní][] stránky do počítače Ubuntu.

Potom spusťte následující v terminálu:

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.14.04_amd64.deb
sudo apt-get install -f
```

> Pamatujte, že `dpkg -i` se nezdaří s unmet závislosti; příkaz Další `apt-get install -f` řeší tyto a pak dokončení konfigurace balíčku prostředí PowerShell.

### <a name="uninstallation---ubuntu-1404"></a>Odinstalace - Ubuntu 14.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1604"></a>Ubuntu 16.04

### <a name="installation-via-package-repository---ubuntu-1604"></a>Instalaci přes úložiště balíčků - Ubuntu 16.04

Základní prostředí PowerShell pro Linux, je publikovaný na balíček úložiště pro Snadná instalace (a aktualizace).
Toto je upřednostňovaná metoda.

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/16.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, od toho stačí použít `sudo apt-get upgrade powershell` jej aktualizovat.

### <a name="installation-via-direct-download---ubuntu-1604"></a>Instalace prostřednictvím přímé stahování - Ubuntu 16.04

Stáhněte si balíček Debian `powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb` z [uvolní][] stránky do počítače Ubuntu.

Potom spusťte následující v terminálu:

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb
sudo apt-get install -f
```

> Pamatujte, že `dpkg -i` se nezdaří s unmet závislosti; příkaz Další `apt-get install -f` řeší tyto a pak dokončení konfigurace balíčku prostředí PowerShell.

### <a name="uninstallation---ubuntu-1604"></a>Odinstalace - Ubuntu 16.04

```sh
sudo apt-get remove powershell
```

## <a name="ubuntu-1704"></a>Ubuntu č. 17.04

### <a name="installation-via-package-repository---ubuntu-1704"></a>Instalaci přes úložiště balíčků - Ubuntu č. 17.04

Základní prostředí PowerShell pro Linux, je publikovaný na balíček úložiště pro Snadná instalace (a aktualizace).
Toto je upřednostňovaná metoda.

```sh
# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Ubuntu repository
curl https://packages.microsoft.com/config/ubuntu/17.04/prod.list | sudo tee /etc/apt/sources.list.d/microsoft.list

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, od toho stačí použít `sudo apt-get upgrade powershell` jej aktualizovat.

### <a name="installation-via-direct-download---ubuntu-1704"></a>Instalace prostřednictvím přímé stahování - Ubuntu č. 17.04

Stáhněte si balíček Debian `powershell_6.0.0-rc-1.ubuntu.17.04_amd64.deb` z [uvolní][] stránky do počítače Ubuntu.

Potom spusťte následující v terminálu:

```sh
sudo dpkg -i powershell_6.0.0-rc-1.ubuntu.17.04_amd64.deb
sudo apt-get install -f
```

> Pamatujte, že `dpkg -i` se nezdaří s unmet závislosti; příkaz Další `apt-get install -f` řeší tyto a pak dokončení konfigurace balíčku prostředí PowerShell.

### <a name="uninstallation---ubuntu-1704"></a>Odinstalace - Ubuntu č. 17.04

```sh
sudo apt-get remove powershell
```

## <a name="debian-8"></a>Debian 8

### <a name="installation-via-package-repository---debian-8"></a>Instalaci přes úložiště balíčků - Debian 8

Základní prostředí PowerShell pro Linux, je publikovaný na balíček úložiště pro Snadná instalace (a aktualizace).
Toto je upřednostňovaná metoda.

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, od toho stačí použít `sudo apt-get upgrade powershell` jej aktualizovat.

### <a name="installation-via-direct-download---debian-8"></a>Instalace prostřednictvím přímé stahování - Debian 8

Stáhněte si balíček Debian `powershell_6.0.0-rc-1.debian.8_amd64.deb` z [uvolní][] stránky do Debian počítače.

Potom spusťte následující v terminálu:

```sh
sudo dpkg -i powershell_6.0.0-rc-1.debian.8_amd64.deb
sudo apt-get install -f
```

> Pamatujte, že `dpkg -i` se nezdaří s unmet závislosti; příkaz Další `apt-get install -f` řeší tyto a pak dokončení konfigurace balíčku prostředí PowerShell.

### <a name="uninstallation---debian-8"></a>Odinstalace - Debian 8

```sh
sudo apt-get remove powershell
```

## <a name="debian-9"></a>Debian 9

### <a name="installation-via-package-repository---debian-9"></a>Instalaci přes úložiště balíčků - Debian 9

Základní prostředí PowerShell pro Linux, je publikovaný na balíček úložiště pro Snadná instalace (a aktualizace).
Toto je upřednostňovaná metoda.

```sh
# Install system components
sudo apt-get update
sudo apt-get install curl gnupg apt-transport-https

# Import the public repository GPG keys
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

# Register the Microsoft Product feed
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/microsoft.list'

# Update the list of products
sudo apt-get update

# Install PowerShell
sudo apt-get install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, od toho stačí použít `sudo apt-get upgrade powershell` jej aktualizovat.

### <a name="installation-via-direct-download---debian-9"></a>Instalace prostřednictvím přímé stahování - Debian 9

Stáhněte si balíček Debian `powershell_6.0.0-rc-1.debian.9_amd64.deb` z [uvolní][] stránky do Debian počítače.

Potom spusťte následující v terminálu:

```sh
sudo dpkg -i powershell_6.0.0-rc-1.debian.9_amd64.deb
sudo apt-get install -f
```

> Pamatujte, že `dpkg -i` se nezdaří s unmet závislosti; příkaz Další `apt-get install -f` řeší tyto a pak dokončení konfigurace balíčku prostředí PowerShell.

### <a name="uninstallation---debian-9"></a>Odinstalace - Debian 9

```sh
sudo apt-get remove powershell
```

## <a name="centos-7"></a>CentOS 7

> Tento balíček funguje taky na Oracle Linux 7.

### <a name="installation-via-package-repository-preferred---centos-7"></a>Instalaci přes úložiště balíčků (doporučeno) - CentOS 7

Základní prostředí PowerShell pro Linux je publikovaný na oficiální Microsoft úložiště pro Snadná instalace (a aktualizace).

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, stačí použít `sudo yum update powershell` aktualizovat prostředí PowerShell.

### <a name="installation-via-direct-download---centos-7"></a>Instalace prostřednictvím přímé stahování - CentOS 7

Pomocí [CentOS 7][], stáhněte si balíček RPM `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` z [uvolní][] stránky do počítače CentOS.

Potom spusťte následující v terminálu:

```sh
sudo yum install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

Můžete taky nainstalovat RPM bez přechodný krok stahování ho:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---centos-7"></a>Odinstalace - CentOS 7

```sh
sudo yum remove powershell
```

[CentOS 7]: https://www.centos.org/download/

## <a name="red-hat-enterprise-linux-rhel-7"></a>Red Hat Enterprise Linux (RHEL) 7

### <a name="installation-via-package-repository-preferred---red-hat-enterprise-linux-rhel-7"></a>Instalaci přes úložiště balíčků (doporučeno) - Red Hat Enterprise Linux (RHEL) 7

Základní prostředí PowerShell pro Linux je publikovaný na oficiální Microsoft úložiště pro Snadná instalace (a aktualizace).

```sh
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo yum install -y powershell

# Start PowerShell
pwsh
```

Po registraci jednou úložiště společnosti Microsoft jako superuživatele, stačí použít `sudo yum update powershell` aktualizovat prostředí PowerShell.

### <a name="installation-via-direct-download---red-hat-enterprise-linux-rhel-7"></a>Instalace prostřednictvím přímé stahování - Red Hat Enterprise Linux (RHEL) 7

Stáhněte si balíček RPM `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` z [uvolní][] stránky do počítače Red Hat Enterprise Linux.

Potom spusťte následující v terminálu:

```sh
sudo yum install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

Můžete taky nainstalovat RPM bez přechodný krok stahování ho:

```sh
sudo yum install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---red-hat-enterprise-linux-rhel-7"></a>Odinstalace - Red Hat Enterprise Linux (RHEL) 7

```sh
sudo yum remove powershell
```

## <a name="opensuse-422"></a>OpenSUSE 42.2

> **Poznámka:** při instalaci prostředí PowerShell jádra, OpenSUSE může hlásit, že nic poskytuje `libcurl`.
`libcurl`by měl být již nainstalován na podporovaných verzích OpenSUSE.
Spustit `zypper search libcurl` k potvrzení.
Chyba nabídne 2 'řešení'. Zvolte řešení 2 pokračovat v instalaci jádra prostředí PowerShell.

### <a name="installation-via-package-repository-preferred---opensuse-422"></a>Instalaci přes úložiště balíčků (doporučeno) - OpenSUSE 42.2

Základní prostředí PowerShell pro Linux je publikovaný na oficiální Microsoft úložiště pro Snadná instalace (a aktualizace).

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Add the Microsoft Product feed
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/zypp/repos.d/microsoft.repo

# Update the list of products
sudo zypper update

# Install PowerShell
sudo zypper install powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---opensuse-422"></a>Instalace prostřednictvím přímé stahování - OpenSUSE 42.2

Stáhněte si balíček RPM `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` z [uvolní][] stránky do počítače OpenSUSE.

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

Můžete taky nainstalovat RPM bez přechodný krok stahování ho:

```sh
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo zypper install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---opensuse-422"></a>Odinstalace - OpenSUSE 42.2

```sh
sudo zypper remove powershell
```

## <a name="fedora-25"></a>Fedora 25

### <a name="installation-via-package-repository-preferred---fedora-25"></a>Instalaci přes úložiště balíčků (doporučeno) - Fedora 25

Základní prostředí PowerShell pro Linux je publikovaný na oficiální Microsoft úložiště pro Snadná instalace (a aktualizace).

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-25"></a>Instalace prostřednictvím přímé stahování - Fedora 25

Stáhněte si balíček RPM `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` z [uvolní][] stránky do počítače Fedora.

Potom spusťte následující v terminálu:

```sh
sudo dnf install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

Můžete taky nainstalovat RPM bez přechodný krok stahování ho:

```sh
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-25"></a>Odinstalace - Fedora 25

```sh
sudo dnf remove powershell
```

## <a name="fedora-26"></a>Fedora 26

### <a name="installation-via-package-repository-preferred---fedora-26"></a>Instalaci přes úložiště balíčků (doporučeno) - Fedora 26

Základní prostředí PowerShell pro Linux je publikovaný na oficiální Microsoft úložiště pro Snadná instalace (a aktualizace).

```sh
# Register the Microsoft signature key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/7/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Update the list of products
sudo dnf update

# Install a system component
sudo dnf install compat-openssl10

# Install PowerShell
sudo dnf install -y powershell

# Start PowerShell
pwsh
```

### <a name="installation-via-direct-download---fedora-26"></a>Instalace prostřednictvím přímé stahování - Fedora 26

Stáhněte si balíček RPM `powershell-6.0.0_rc-1.rhel.7.x86_64.rpm` z [uvolní][] stránky do počítače Fedora.

Potom spusťte následující v terminálu:

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

Můžete taky nainstalovat RPM bez přechodný krok stahování ho:

```sh
sudo dnf update
sudo dnf install compat-openssl10
sudo dnf install https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0_rc-1.rhel.7.x86_64.rpm
```

### <a name="uninstallation---fedora-26"></a>Odinstalace - Fedora 26

```sh
sudo dnf remove powershell
```

## <a name="arch-linux"></a>Arch Linux

PowerShell je k dispozici [architektura Linux][] uživatele úložiště (AUR).

* Může být zkompilován s [označené nejnovější verze][arch-release]
* Mohou být zkompilovány z [nejnovější potvrzení změn na hlavní server][arch-git]
* Můžete nainstalovat, pomocí [nejnovější verzi binární][arch-bin]

Balíčky v AUR jsou udržuje komunitní – neexistuje žádná podpora oficiální.

Další informace o instalaci balíčků z AUR najdete v tématu [architektura Linux wiki](https://wiki.archlinux.org/index.php/Arch_User_Repository#Installing_packages) nebo komunity [soubor Docker](https://github.com/PowerShell/PowerShell/blob/master/docker/community/archlinux/Dockerfile).

[architektura Linux]: https://www.archlinux.org/download/
[arch-release]: https://aur.archlinux.org/packages/powershell/
[arch-git]: https://aur.archlinux.org/packages/powershell-git/
[arch-bin]: https://aur.archlinux.org/packages/powershell-bin/

## <a name="linux-appimage"></a>Linux AppImage

Pomocí poslední distribuci systému Linux, stáhněte si AppImage `powershell-6.0.0-rc-x86_64.AppImage` z [uvolní][] stránky do počítače Linux.

Potom spusťte následující v terminálu:

```bash
chmod a+x powershell-6.0.0-rc-x86_64.AppImage
./powershell-6.0.0-rc-x86_64.AppImage
```

[AppImage][] vám umožní spustit prostředí PowerShell bez jeho instalaci.
Je přenosné aplikace, která obsahuje ureitou prostředí PowerShell a jeho závislosti (včetně závislostí systému .NET Core) do jednoho získá na ucelenosti balíčku.
Tento balíček funguje nezávisle na distribuční Linux uživatele a je jediné binární.

[appimage]: http://appimage.org/

## <a name="macos-1012"></a>systému macOS 10.12

### <a name="installation-via-homebrew-preferred---macos-1012"></a>Instalaci přes Homebrew (doporučeno) - systému macOS 10.12

[Homebrew] [ brew] je chybějící Správce balíčků pro systému macOS.
Pokud `brew` příkaz nebyl nalezen, je nutné nainstalovat následující Homebrew [podle pokynů v nich][brew].

Jakmile jste nainstalovali Homebrew, instalace prostředí PowerShell je snadné.
Nejdřív nainstalujte [obalového Homebrew souboru][cask], takže můžete nainstalovat další balíčky:

```sh
brew tap caskroom/cask
```

Nyní můžete nainstalovat prostředí PowerShell:

```sh
brew cask install powershell
```

Když jsou vydávány nové verze prostředí PowerShell, jednoduše aktualizovat na Homebrew vzorce a upgrade prostředí PowerShell:

```sh
brew update
brew cask reinstall powershell
```

> Poznámka: z důvodu [tento problém v obalového souboru](https://github.com/caskroom/homebrew-cask/issues/29301), aktuálně musíte udělat přeinstalovat k upgradu.

[brew]: http://brew.sh/
[cask]: https://caskroom.github.io/

### <a name="installation-via-direct-download---macos-1012"></a>Instalace prostřednictvím přímé stáhnout - systému macOS 10.12

Pomocí systému macOS 10.12, stáhněte si balíček PKG `powershell-6.0.0-rc-osx.10.12-x64.pkg` z [uvolní][] stránky do systému macOS počítače.

Buď poklikejte na soubor a postupujte podle pokynů nebo ji nainstalovat z terminálu:

```sh
sudo installer -pkg powershell-6.0.0-rc-osx.10.12-x64.pkg -target /
```

### <a name="uninstallation---macos-1012"></a>Odinstalace - systému macOS 10.12

Pokud jste nainstalovali prostředí PowerShell s Homebrew, je snadné odinstalace:

```sh
brew cask uninstall powershell
```

Pokud jste nainstalovali PowerShell prostřednictvím přímé stahování, musíte ručně odstranit prostředí PowerShell:

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

Chcete-li odinstalovat další cesty prostředí PowerShell (například cesta k profilu uživatele) najdete v tématu [cesty] [ paths] části níže v tomto dokumentu a odeberte požadovanou cesty s `sudo rm`.
(Poznámka: Toto není nutné v případě, že jste nainstalovali s Homebrew.)

[paths]:#paths

## <a name="kali"></a>Kali

### <a name="installation"></a>Instalace

```sh
# Install prerequisites
apt-get install libunwind8 libicu55
wget http://security.debian.org/debian-security/pool/updates/main/o/openssl/libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb
dpkg -i libssl1.0.0_1.0.1t-1+deb8u6_amd64.deb

# Install PowerShell
dpkg -i powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb

# Start PowerShell
pwsh
```

### <a name="run-powershell-in-latest-kali-kali-gnulinux-rolling-without-installing-it"></a>Spusťte prostředí PowerShell bez instalace se v nejnovější Kali (vrácení Kali GNU/Linux)

```sh
# Grab the latest App Image
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-x86_64.AppImage

# Make executable
chmod a+x powershell-6.0.0-rc-x86_64.AppImage

# Start PowerShell
./powershell-6.0.0-rc-x86_64.AppImage
```

### <a name="uninstallation---kali"></a>Odinstalace - Kali

```sh
dpkg -r powershell_6.0.0-rc-1.ubuntu.16.04_amd64.deb
```

## <a name="raspbian"></a>Raspbian

V současné době prostředí PowerShell je podporována pouze na Raspbian Stretch.

### <a name="installation"></a>Instalace

```sh
# Install prerequisites
sudo apt-get install libunwind8

# Grab the latest tar.gz
wget https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-linux-arm32.tar.gz

# Make folder to put powershell
mkdir ~/powershell

# Unpack the tar.gz file
tar -xvf ./powershell-6.0.0-rc-linux-arm32.tar.gz -C ~/powershell

# Start PowerShell
~/powershell/pwsh
```

### <a name="uninstallation---raspbian"></a>Odinstalace - Raspbian

```sh
rm -rf ~/powershell
```

## <a name="binary-archives"></a>Binární archivy

Prostředí PowerShell binární `tar.gz` archivy jsou k dispozici pro systému macOS a platformy Linux k povolení pokročilé scénáře nasazení.

### <a name="dependencies"></a>Závislosti

Pro systémy Linux prostředí PowerShell vytvoří přenosné binární soubory pro všechny distribuce systému Linux.
Ale .NET Core runtime vyžaduje jiný závislosti na různých distribucí, a proto prostředí PowerShell dělá to stejné.

Následující graf zobrazuje rozhraní .NET 2.0 základní závislosti na různých distribucí Linux, které jsou oficiálně podporované.

| Operační systém                 | Závislosti |
| ------------------ | ------------ |
| Ubuntu 14.04       | libc6, ust0-libgcc1, libgssapi-krb5-2, liblttng, libstdc ++ 6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Ubuntu 16.04       | libc6, ust0-libgcc1, libgssapi-krb5-2, liblttng, libstdc ++ 6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu55 |
| Ubuntu č. 17.04       | libc6, ust0-libgcc1, libgssapi-krb5-2, liblttng, libstdc ++ 6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu57 |
| Debian 8 (Klára)  | libc6, ust0-libgcc1, libgssapi-krb5-2, liblttng, libstdc ++ 6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.0, libicu52 |
| Debian 9 (Stretch) | libc6, ust0-libgcc1, libgssapi-krb5-2, liblttng, libstdc ++ 6, <br> libcurl3, libunwind8, libuuid1, zlib1g, libssl1.0.2, libicu57 |
| CentOS 7 <br> Oracle Linux 7 <br> RHEL 7 <br> OpenSUSE 42.2 <br> Fedora 25 | libunwind, libcurl, knihovny openssl, libicu |
| Fedora 26          | libunwind, libcurl, knihovny openssl, libicu, compat openssl10 |

Abyste mohli nasadit binární soubory prostředí PowerShell na Linuxových distribucích, které nejsou oficiálně podporované, museli byste nainstalujte potřebné závislosti pro cílový operační systém v samostatné kroky.
Například naše [soubor docker Amazon Linux] [ amazon-dockerfile] nejdřív nainstaluje závislosti a pak extrahuje sady Linux `tar.gz` archivu.

[amazon-dockerfile]: https://github.com/PowerShell/PowerShell/blob/master/docker/community/amazonlinux/Dockerfile

### <a name="installation---binary-archives"></a>Instalace - binární archivy

#### <a name="linux"></a>Linux

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-linux-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /opt/microsoft/powershell/6.0.0-rc

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /opt/microsoft/powershell/6.0.0-rc

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.0-rc/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /opt/microsoft/powershell/6.0.0-rc/pwsh /usr/bin/pwsh
```

#### <a name="macos"></a>systému macOS

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.0.0-rc/powershell-6.0.0-rc-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.0.0-rc

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.0.0-rc

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.0.0-rc/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.0.0-rc/pwsh /usr/local/bin/pwsh
```

### <a name="uninstallation---binary-archives"></a>Odinstalace - binární archivy

#### <a name="linux"></a>Linux

```sh
sudo rm -rf /usr/bin/pwsh /opt/microsoft/powershell
```

#### <a name="macos"></a>systému macOS

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

## <a name="paths"></a>Cesty

* `$PSHOME`je`/opt/microsoft/powershell/6.0.0-rc/`
* Profily uživatelů, bude číst ze`~/.config/powershell/profile.ps1`
* Výchozí profily bude číst ze`$PSHOME/profile.ps1`
* Moduly uživatele bude číst ze`~/.local/share/powershell/Modules`
* Sdílené moduly, bude číst ze`/usr/local/share/powershell/Modules`
* Výchozí moduly, bude číst ze`$PSHOME/Modules`
* Historie PSReadline budou zaznamenány do`~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt`

Profily respektují konfigurace Powershellu na hostitele, takže výchozí konkrétního hostitele profily existuje v `Microsoft.PowerShell_profile.ps1` ve stejném umístění.

Na Linuxu a systému macOS [XDG základní Directory specifikace] [ xdg-bds] je dodržena.

Všimněte si, že vzhledem k tomu, že systému macOS je odvozený od BSD, místo `/opt`, je Předpona použitá `/usr/local`.
Proto `$PSHOME` je `/usr/local/microsoft/powershell/6.0.0-rc/`, a symlink je umístěn na `/usr/local/bin/pwsh`.

[uvolní]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html