---
ms.date: 06/12/2017
keywords: DSC, powershell, konfigurace, instalační program
title: Možnosti přihlašovacích údajů v konfiguračních datech
ms.openlocfilehash: a1ecccfd0560903fa8c1cec9a4d57e7217be7f6c
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403732"
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="ddcfa-103">Možnosti přihlašovacích údajů v konfiguračních datech</span><span class="sxs-lookup"><span data-stu-id="ddcfa-103">Credentials Options in Configuration Data</span></span>
><span data-ttu-id="ddcfa-104">Platí pro: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="ddcfa-104">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="ddcfa-105">Hesla v prostém textu a uživatelé domény</span><span class="sxs-lookup"><span data-stu-id="ddcfa-105">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="ddcfa-106">Konfigurace DSC obsahující přihlašovací údaje bez šifrování se vygeneruje chybovou zprávu o hesla v prostém textu.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-106">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span>
<span data-ttu-id="ddcfa-107">DSC, vygeneruje upozornění při použití přihlašovacích údajů do domény.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-107">Also, DSC will generate a warning when using domain credentials.</span></span>
<span data-ttu-id="ddcfa-108">Můžete potlačit pomocí klíčových dat konfigurace DSC tyto chybové zprávy a upozornění:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-108">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>
* <span data-ttu-id="ddcfa-109">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="ddcfa-109">**PsDscAllowPlainTextPassword**</span></span>
* <span data-ttu-id="ddcfa-110">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="ddcfa-110">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="ddcfa-111">Ukládání a přenos hesel ve formátu prostého textu nešifrované není obecně bezpečné.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-111">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="ddcfa-112">Doporučuje se zabezpečení přihlašovacích údajů pomocí techniky popsané dále v tomto tématu.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-112">Securing credentials by using the techniques covered later in this topic is recommended.</span></span>
> <span data-ttu-id="ddcfa-113">Služba Azure Automation DSC umožňuje centrálně spravovat přihlašovací údaje pro kompilaci v konfiguracích a bezpečně uložen.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-113">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span>
> <span data-ttu-id="ddcfa-114">Informace najdete v tématu: [Kompilace konfigurací DSC / Assety přihlašovacích údajů](/azure/automation/automation-dsc-compile#credential-assets)</span><span class="sxs-lookup"><span data-stu-id="ddcfa-114">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

<span data-ttu-id="ddcfa-115">Následuje příklad předá přihlašovací údaje ve formátu prostého textu:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-115">The following is an example of passing plain text credentials:</span></span>

```powershell
#Prompt user for their credentials
#credentials will be unencrypted in the MOF
$promptedCreds = get-credential -Message "Please enter your credentials to generate a DSC MOF:"

# Store passwords in plaintext, in the document itself
# will also be stored in plaintext in the mof
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "User1"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

# DSC requires explicit confirmation before storing passwords insecurely
$ConfigurationData = @{
    AllNodes = @(
        @{
            # The "*" means "all nodes named in ConfigData" so we don't have to repeat ourselves
            NodeName="*"
            PSDscAllowPlainTextPassword = $true
        },
        #however, each node still needs to be explicitly defined for "*" to have meaning
        @{
            NodeName = "TestMachine1"
        },
        #we can also use a property to define node-specific passwords, although this is no more secure
        @{
            NodeName = "TestMachine2";
            UserName = "User2"
            LocalPassword = "ThisIsYetAnotherPlaintextPassword"
        }
        )
}
configuration unencryptedPasswordDemo
{
    Node "TestMachine1"
    {
        # We use the plaintext password to generate a new account
        User User1
        {
            UserName = $username
            Password = $credential
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }
        # We use the prompted password to add this account to the local admins group
        Group addToAdmin
        {
            # Ensure the user exists before we add the user to a group
            DependsOn = "[User]User1"
            Credential = $promptedCreds
            GroupName = "Administrators"
            Ensure = "Present"
            MembersToInclude = "User1"
        }
    }

    Node "TestMachine2"
    {
        # Now we'll use a node-specific password to this machine
        $password = $Node.LocalPassword | ConvertTo-SecureString -asPlainText -Force
        $username = $node.UserName
        [PSCredential] $nodeCred = New-Object System.Management.Automation.PSCredential($username,$password)

        User User2
        {
            UserName = $username
            Password = $nodeCred
            Description = "local account"
            Ensure = "Present"
            Disabled = $false
            PasswordNeverExpires = $true
            PasswordChangeRequired = $false
        }

        Group addToAdmin
        {
            Credential = $promptedCreds
            GroupName = "Administrators"
            DependsOn = "[User]User2"
            Ensure = "Present"
            MembersToInclude = "User2"
        }
    }

}
# We declared the ConfigurationData in a local variable, but we need to pass it in to our configuration function
# We need to invoke the configuration function we created to generate a MOF
unencryptedPasswordDemo -ConfigurationData $ConfigurationData
# We need to pass the MOF to the machines we named.
#-wait: doesn't use jobs so we get blocked at the prompt until the configuration is done
#-verbose: so we can see what's going on and catch any errors
#-force: for testing purposes, I run start-dscconfiguration frequently + want to make sure i'm
#        not blocked by previous configurations that are still running
Start-DscConfiguration ./unencryptedPasswordDemo -verbose -wait -force
```

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="ddcfa-116">Zpracování přihlašovacích údajů v DSC</span><span class="sxs-lookup"><span data-stu-id="ddcfa-116">Handling Credentials in DSC</span></span>

<span data-ttu-id="ddcfa-117">Prostředky DSC konfigurace spustit jako `Local System` ve výchozím nastavení.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-117">DSC configuration resources run as `Local System` by default.</span></span>
<span data-ttu-id="ddcfa-118">Ale některé prostředky nutné přihlašovací údaje, například při `Package` prostředků je potřeba nainstalovat software v rámci konkrétního uživatelského účtu.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-118">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="ddcfa-119">Použít starší prostředky pevně zakódovaná `Credential` název vlastnosti pro toto zpracování.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-119">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span>
<span data-ttu-id="ddcfa-120">Automatické přidání WMF 5.0 `PsDscRunAsCredential` vlastnost pro všechny prostředky.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-120">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span>
<span data-ttu-id="ddcfa-121">Informace o používání `PsDscRunAsCredential`, naleznete v tématu [DSC spuštěná s pověřeními uživatele](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-121">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span>
<span data-ttu-id="ddcfa-122">Novější a vlastních prostředků pomocí této vlastnosti automatické místo vytvoření vlastní vlastnost pro přihlašovací údaje.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-122">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="ddcfa-123">Návrh některých prostředků mají používat více přihlašovací údaje pro konkrétní důvod, proč a mají své vlastní vlastnosti přihlašovacích údajů.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-123">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="ddcfa-124">Pokud chcete zjistit přihlašovací údaje, které k dispozici vlastnosti prostředku, použijte buď `Get-DscResource -Name ResourceName -Syntax` nebo technologie Intellisense v prostředí ISE (`CTRL+SPACE`).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-124">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

```powershell
PS C:\> Get-DscResource -Name Group -Syntax
Group [String] #ResourceName
{
    GroupName = [string]
    [Credential = [PSCredential]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Members = [string[]]]
    [MembersToExclude = [string[]]]
    [MembersToInclude = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="ddcfa-125">Tento příklad používá [skupiny](../resources/resources.md) prostředku z `PSDesiredStateConfiguration` integrovaný modul prostředků DSC.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-125">This example uses a [Group](../resources/resources.md) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span>
<span data-ttu-id="ddcfa-126">Můžete vytvořit místní skupiny a přidat nebo odebrat členy.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-126">It can create local groups and add or remove members.</span></span>
<span data-ttu-id="ddcfa-127">Přijímá i `Credential` vlastnost a automatické `PsDscRunAsCredential` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-127">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span>
<span data-ttu-id="ddcfa-128">Nicméně pouze prostředek používá `Credential` vlastnost.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-128">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="ddcfa-129">Další informace o `PsDscRunAsCredential` vlastnost, naleznete v tématu [DSC spuštěná s pověřeními uživatele](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-129">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="ddcfa-130">Příklad: Skupina prostředků vlastnost Credential</span><span class="sxs-lookup"><span data-stu-id="ddcfa-130">Example: The Group resource Credential property</span></span>

<span data-ttu-id="ddcfa-131">DSC běží pod `Local System`, takže už má oprávnění ke změně místní uživatelé a skupiny.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-131">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span>
<span data-ttu-id="ddcfa-132">Pokud Přidání člena je místní účet, nevyžadují se přihlašovací údaje je nezbytné.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-132">If the member added is a local account, then no credential is necessary.</span></span>
<span data-ttu-id="ddcfa-133">Pokud `Group` zdroj přidá doménový účet do místní skupiny a pak je nutné přihlašovací údaje.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-133">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="ddcfa-134">Anonymní dotazy do služby Active Directory nejsou povoleny.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-134">Anonymous queries to Active Directory are not allowed.</span></span>
<span data-ttu-id="ddcfa-135">`Credential` Vlastnost `Group` prostředků je účet domény používaný k dotazu služby Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-135">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span>
<span data-ttu-id="ddcfa-136">Pro většinu účelů příčinou může být obecný uživatelský účet ve výchozím nastavení můžou uživatelé *čtení* většinu objektů ve službě Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-136">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="ddcfa-137">Příklad konfigurace</span><span class="sxs-lookup"><span data-stu-id="ddcfa-137">Example Configuration</span></span>

<span data-ttu-id="ddcfa-138">Následující příklad kódu používá DSC k naplnění místní skupinu jako uživatel domény:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-138">The following example code uses DSC to populate a local group with a domain user:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred
```

<span data-ttu-id="ddcfa-139">Tento kód vygeneruje chyby i upozornění:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-139">This code generates both an error and warning message:</span></span>

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing
property 'Credential' OF TYPE 'Group': Converting and storing encrypted
passwords as plain text is not recommended. For more information on securing
credentials in MOF file, please refer to MSDN blog:
http://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:297 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance

WARNING: It is not recommended to use domain credential for node 'localhost'.
In order to suppress the warning, you can add a property named
'PSDscAllowDomainUser' with a value of $true to your DSC configuration data
for node 'localhost'.
```

<span data-ttu-id="ddcfa-140">V tomto příkladu má dva problémy:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-140">This example has two issues:</span></span>
1. <span data-ttu-id="ddcfa-141">Chyba vysvětluje, že nedoporučujeme používat hesla v prostém textu</span><span class="sxs-lookup"><span data-stu-id="ddcfa-141">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="ddcfa-142">Upozornění se nedoporučuje používat přihlašovací údaje domény</span><span class="sxs-lookup"><span data-stu-id="ddcfa-142">A warning advises against using a domain credential</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="ddcfa-143">PsDscAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="ddcfa-143">PsDscAllowPlainTextPassword</span></span>

<span data-ttu-id="ddcfa-144">První chybovou zprávu má adresu URL s dokumentací.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-144">The first error message has a URL with documentation.</span></span>
<span data-ttu-id="ddcfa-145">Tento odkaz vysvětluje, jak šifrovat pomocí hesla [ConfigurationData](./configData.md) strukturu a certifikát.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-145">This link explains how to encrypt passwords using a [ConfigurationData](./configData.md) structure and a certificate.</span></span>
<span data-ttu-id="ddcfa-146">Další informace o certifikátech a DSC [přečtěte si tento příspěvek](http://aka.ms/certs4dsc).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-146">For more information on certificates and DSC [read this post](http://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="ddcfa-147">Vynutit heslo jako prostý text, prostředek, vyžaduje `PsDscAllowPlainTextPassword` – klíčové slovo v konfiguračních datech části následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-147">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowPlainTextPassword = $true
        }
    )
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred -ConfigurationData $cd
```

> [!NOTE]
> <span data-ttu-id="ddcfa-148">`NodeName` se nesmí rovnat hvězdičky, konkrétní uzel název je povinné.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-148">`NodeName` cannot equal asterisk, a specific node name is mandatory.</span></span>

<span data-ttu-id="ddcfa-149">**Microsoft se výzva, aby hesla v prostém textu kvůli významné riziko zabezpečení.**</span><span class="sxs-lookup"><span data-stu-id="ddcfa-149">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="ddcfa-150">Přihlašovací údaje domény</span><span class="sxs-lookup"><span data-stu-id="ddcfa-150">Domain Credentials</span></span>

<span data-ttu-id="ddcfa-151">Spuštění skriptu konfigurace příklad znovu (s nebo bez šifrování), stále generuje upozornění, že používáte doménu účtu zadání přihlašovacích údajů se nedoporučuje.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-151">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span>
<span data-ttu-id="ddcfa-152">Pomocí místního účtu eliminuje potenciální riziko pověření domény, které lze použít na jiných serverech.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-152">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="ddcfa-153">**Při použití přihlašovacích údajů pomocí prostředků DSC, dáváte přednost místní účet kontrolu nad účtem domény, pokud je to možné.**</span><span class="sxs-lookup"><span data-stu-id="ddcfa-153">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="ddcfa-154">Pokud je '\' nebo '\@' v `Username` vlastnosti přihlašovacích údajů, pak DSC bude zpracována jako účet domény.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-154">If there is a '\' or '@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span>
<span data-ttu-id="ddcfa-155">Dojde k výjimce pro "localhost", "127.0.0.1" a ":: 1" v části domény uživatelské jméno.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-155">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="ddcfa-156">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="ddcfa-156">PSDscAllowDomainUser</span></span>

<span data-ttu-id="ddcfa-157">V DSC `Group` prostředků příklad výše, dotazování domény služby Active Directory *vyžaduje* účet domény.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-157">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span>
<span data-ttu-id="ddcfa-158">V takovém případě přidejte `PSDscAllowDomainUser` vlastnost `ConfigurationData` blokovat následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-158">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

```powershell
$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            # PSDscAllowPlainTextPassword = $true
            CertificateFile = "C:\PublicKeys\server1.cer"
        }
    )
}
```

<span data-ttu-id="ddcfa-159">Konfigurační skript nyní vygeneruje soubor MOF bez jakýchkoli chyb nebo upozornění.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-159">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>