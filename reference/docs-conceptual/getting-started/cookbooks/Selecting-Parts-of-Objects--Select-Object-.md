---
ms.date: 2017-06-05
keywords: "rutiny prostředí PowerShell"
title: "Výběr části objektů, vyberte objekt"
ms.assetid: 72e64b1a-d351-4500-9da3-24d8a71d7a92
ms.openlocfilehash: 8c9633e80f63e1d474c46fa772108aee4f79751d
ms.sourcegitcommit: 74255f0b5f386a072458af058a15240140acb294
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="selecting-parts-of-objects-select-object"></a><span data-ttu-id="47dda-103">Výběr částí objektů (Select-Object)</span><span class="sxs-lookup"><span data-stu-id="47dda-103">Selecting Parts of Objects (Select-Object)</span></span>
<span data-ttu-id="47dda-104">Můžete použít **Select-Object** rutiny k vytvoření nových, vlastních objektů prostředí Windows PowerShell, které obsahují vlastnosti vybrané objekty, které budete používat při jejich vytváření.</span><span class="sxs-lookup"><span data-stu-id="47dda-104">You can use the **Select-Object** cmdlet to create new, custom Windows PowerShell objects that contain properties selected from the objects you use to create them.</span></span> <span data-ttu-id="47dda-105">Zadejte následující příkaz pro vytvoření nového objektu, který obsahuje pouze název a FreeSpace vlastnosti třídy Win32_LogicalDisk WMI:</span><span class="sxs-lookup"><span data-stu-id="47dda-105">Type the following command to create a new object that includes only the Name and FreeSpace properties of the Win32_LogicalDisk WMI class:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace

Name                                    FreeSpace
----                                    ---------
C:                                      50664845312
```

<span data-ttu-id="47dda-106">Po vydání tohoto příkazu nevidíte typu dat, ale pokud jste po Select-Object prostřednictvím kanálu výsledek, který má Get-člen, můžete zadat, že máte nový typ objektu, PSCustomObject:</span><span class="sxs-lookup"><span data-stu-id="47dda-106">You cannot see the type of data after issuing that command, but if you pipe the result to Get-Member after the Select-Object, you can tell that you have a new type of object, a PSCustomObject:</span></span>

```
PS> Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace| Get-Member

   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       System.Boolean Equals(Object obj)
GetHashCode Method       System.Int32 GetHashCode()
GetType     Method       System.Type GetType()
ToString    Method       System.String ToString()
FreeSpace   NoteProperty  FreeSpace=...
Name        NoteProperty System.String Name=C:
```

<span data-ttu-id="47dda-107">Select-Object se mnoha způsoby.</span><span class="sxs-lookup"><span data-stu-id="47dda-107">Select-Object has many uses.</span></span> <span data-ttu-id="47dda-108">Jeden z nich se replikuje data, která pak můžete upravovat.</span><span class="sxs-lookup"><span data-stu-id="47dda-108">One of them is replicating data that you can then modify.</span></span> <span data-ttu-id="47dda-109">Nyní jsme může zpracovávat problému, který jsme narazili v předchozí části.</span><span class="sxs-lookup"><span data-stu-id="47dda-109">We can now handle the problem we ran across in the previous section.</span></span> <span data-ttu-id="47dda-110">Aktualizujeme hodnotu FreeSpace v našem nově vytvořené objekty a výstup bude obsahovat popisné označení:</span><span class="sxs-lookup"><span data-stu-id="47dda-110">We can update the value of FreeSpace in our newly-created objects and the output will include the descriptive label:</span></span>

```
Get-WmiObject -Class Win32_LogicalDisk | Select-Object -Property Name,FreeSpace | ForEach-Object -Process {$_.FreeSpace = ($_.FreeSpace)/1024.0/1024.0; $_}
Name                                                                  FreeSpace
----                                                                  ---------
C:                                                                48317.7265625
```
