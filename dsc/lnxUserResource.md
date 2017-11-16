---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "DSC pro Linux nxUser prostředků"
ms.openlocfilehash: d708edcee592835ce448752465125d451afbd45b
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-for-linux-nxuser-resource"></a><span data-ttu-id="6fa0f-103">DSC pro Linux nxUser prostředků</span><span class="sxs-lookup"><span data-stu-id="6fa0f-103">DSC for Linux nxUser Resource</span></span>

<span data-ttu-id="6fa0f-104">**NxUser** prostředků v prostředí PowerShell požadovaného stavu konfigurace (DSC) poskytuje mechanismus pro ke správě místních uživatelů na uzlu Linux.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-104">The **nxUser** resource in PowerShell Desired State Configuration (DSC) provides a mechanism to to manage local users on a Linux node.</span></span>

## <a name="syntax"></a><span data-ttu-id="6fa0f-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="6fa0f-105">Syntax</span></span>

```
nxUser <string> #ResourceName
{
    UserName = <string>
    [ Ensure = <string> { Absent | Present }  ]
    [ FullName = <string> ]
    [ Description = <string> ]
    [ Password = <string> ]
    [ Disabled = <bool> ]
    [ PasswordChangeRequired = <bool> ]
    [ HomeDirectory = <string> ]
    [ GroupID = <string> ]
    [ DependsOn = <string[]> ]

}
```

## <a name="properties"></a><span data-ttu-id="6fa0f-106">Properties</span><span class="sxs-lookup"><span data-stu-id="6fa0f-106">Properties</span></span>

|  <span data-ttu-id="6fa0f-107">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="6fa0f-107">Property</span></span> |  <span data-ttu-id="6fa0f-108">Určuje název účtu, pro které chcete zajistit určitý stav.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-108">Indicates the account name for which you want to ensure a specific state.</span></span> | 
|---|---|
| <span data-ttu-id="6fa0f-109">UserName</span><span class="sxs-lookup"><span data-stu-id="6fa0f-109">UserName</span></span>| <span data-ttu-id="6fa0f-110">Určuje umístění, kde chcete zajistit stav pro soubor nebo adresář.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-110">Specifies the location where you want to ensure the state for a file or directory.</span></span>| 
| <span data-ttu-id="6fa0f-111">Ujistěte se</span><span class="sxs-lookup"><span data-stu-id="6fa0f-111">Ensure</span></span>| <span data-ttu-id="6fa0f-112">Určuje, jestli účet existuje.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-112">Specifies whether the account exists.</span></span> <span data-ttu-id="6fa0f-113">Nastavením této vlastnosti "Přítomen" zajistit, že existuje účet a nastavte ji na "Chybí" zajistit, že účet neexistuje.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-113">Set this property to "Present" to ensure that the account exists, and set it to "Absent" to ensure that the account does not exist.</span></span>| 
| <span data-ttu-id="6fa0f-114">Úplný název</span><span class="sxs-lookup"><span data-stu-id="6fa0f-114">FullName</span></span>| <span data-ttu-id="6fa0f-115">Řetězec, který obsahuje úplný název pro uživatelský účet.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-115">A string that contains the full name to use for the user account.</span></span>| 
| <span data-ttu-id="6fa0f-116">Popis</span><span class="sxs-lookup"><span data-stu-id="6fa0f-116">Description</span></span>| <span data-ttu-id="6fa0f-117">Popis pro uživatelský účet.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-117">The description for the user account.</span></span>| 
| <span data-ttu-id="6fa0f-118">Heslo</span><span class="sxs-lookup"><span data-stu-id="6fa0f-118">Password</span></span>| <span data-ttu-id="6fa0f-119">Hodnota hash hesla uživatele v příslušný formulář pro počítače se systémem Linux.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-119">The hash of the users password in the appropriate form for the Linux computer.</span></span> <span data-ttu-id="6fa0f-120">Obvykle je to solené SHA-256, nebo hodnotu hash SHA-512.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-120">Typically, this is a salted SHA-256, or SHA-512 hash.</span></span> <span data-ttu-id="6fa0f-121">Na Debian a Ubuntu Linux tato hodnota může být generována pomocí příkazu mkpasswd.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-121">On Debian and Ubuntu Linux, this value can be generated with the mkpasswd command.</span></span> <span data-ttu-id="6fa0f-122">Pro ostatní distribucích systému Linux metodu crypt knihovny jazyka Python Crypt slouží ke generování hodnoty hash.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-122">For other Linux distros, the crypt method of Python’s Crypt library can be used to generate the hash.</span></span>| 
| <span data-ttu-id="6fa0f-123">Zakázáno</span><span class="sxs-lookup"><span data-stu-id="6fa0f-123">Disabled</span></span>| <span data-ttu-id="6fa0f-124">Určuje, zda je povolen.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-124">Indicates whether the account is enabled.</span></span> <span data-ttu-id="6fa0f-125">Tuto vlastnost nastavit na **$true** zajistit, že tento účet je zakázané a nastavte ji na **$false** zajistit, že je povolena.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-125">Set this property to **$true** to ensure that this account is disabled, and set it to **$false** to ensure that it is enabled.</span></span>| 
| <span data-ttu-id="6fa0f-126">PasswordChangeRequired</span><span class="sxs-lookup"><span data-stu-id="6fa0f-126">PasswordChangeRequired</span></span>| <span data-ttu-id="6fa0f-127">Určuje, zda může uživatel změnit heslo.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-127">Indicates whether the user can change the password.</span></span> <span data-ttu-id="6fa0f-128">Tuto vlastnost nastavit na **$true** zajistit, že uživatel nemůže změnit heslo a nastavte ji na **$false** umožňuje uživatelům změnit heslo.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-128">Set this property to **$true** to ensure that the user cannot change the password, and set it to **$false** to allow the user to change the password.</span></span> <span data-ttu-id="6fa0f-129">Výchozí hodnota je **$false**.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-129">The default value is **$false**.</span></span> <span data-ttu-id="6fa0f-130">Tato vlastnost je Vyhodnocená jenom Pokud uživatelský účet dříve neexistoval a je vytvářena.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-130">This property is only evaluated if the user account did not exist previously and is being created.</span></span>| 
| <span data-ttu-id="6fa0f-131">Domovský_adresář</span><span class="sxs-lookup"><span data-stu-id="6fa0f-131">HomeDirectory</span></span>| <span data-ttu-id="6fa0f-132">Domovský adresář pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-132">The home directory for the user.</span></span>| 
| <span data-ttu-id="6fa0f-133">GroupID</span><span class="sxs-lookup"><span data-stu-id="6fa0f-133">GroupID</span></span>| <span data-ttu-id="6fa0f-134">Identifikátor primární skupiny uživatele.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-134">The primary group ID for the user.</span></span>| 
| <span data-ttu-id="6fa0f-135">dependsOn</span><span class="sxs-lookup"><span data-stu-id="6fa0f-135">DependsOn</span></span> | <span data-ttu-id="6fa0f-136">Určuje, že konfigurace jiný prostředek musí spouštět předtím, než je tento prostředek nakonfigurován.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6fa0f-137">Například pokud ID bloku skriptu konfigurace prostředků, který chcete spustit nejprve je "ResourceName" a "Typ prostředku" je její typ, syntaxe pro používání této vlastnosti je `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="6fa0f-137">For example, if the ID of the resource configuration script block that you want to run first is "ResourceName" and its type is "ResourceType", the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>| 

## <a name="example"></a><span data-ttu-id="6fa0f-138">Příklad</span><span class="sxs-lookup"><span data-stu-id="6fa0f-138">Example</span></span>

<span data-ttu-id="6fa0f-139">Následující příklad zajistí, že uživatel "monuser" existuje a je členem skupiny "DBusers".</span><span class="sxs-lookup"><span data-stu-id="6fa0f-139">The following example ensures that the user "monuser" exists and is a member of the group "DBusers".</span></span>

```
Import-DSCResource -Module nx 

Node $node {
nxUser UserExample{
   UserName = "monuser"
   Description = "Monitoring user"
   Password  =    '$6$fZAne/Qc$MZejMrOxDK0ogv9SLiBP5J5qZFBvXLnDu8HY1Oy7ycX.Y3C7mGPUfeQy3A82ev3zIabhDQnj2ayeuGn02CqE/0'
   Ensure = "Present"
   HomeDirectory = "/home/monuser"
}
 
nxGroup GroupExample{
   GroupName = "DBusers"
   Ensure = "Present"
   MembersToInclude = "monuser"
   DependsOn = "[nxUser]UserExample"            
}
}
```
