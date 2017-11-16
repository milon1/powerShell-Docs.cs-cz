---
ms.date: 2017-06-05
keywords: "rutiny prostředí PowerShell"
title: Objekt ISEFile
ms.assetid: 1c6d91f3-c556-42a2-a017-79b6b7b4b7db
ms.openlocfilehash: a1fbd48e872684cc578adb03f52430eabdc54c2c
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2017
---
# <a name="the-isefile-object"></a><span data-ttu-id="101c6-103">Objekt ISEFile</span><span class="sxs-lookup"><span data-stu-id="101c6-103">The ISEFile Object</span></span>
  <span data-ttu-id="101c6-104">**ISEFile** je soubor v systému Windows PowerShell® Integrované skriptovací prostředí (ISE).</span><span class="sxs-lookup"><span data-stu-id="101c6-104">An **ISEFile** object represents a file in Windows PowerShell® Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="101c6-105">Je instance třídy Microsoft.PowerShell.Host.ISE.ISEFile.</span><span class="sxs-lookup"><span data-stu-id="101c6-105">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span> <span data-ttu-id="101c6-106">Toto téma uvádí jeho člen metod a vlastností člena.</span><span class="sxs-lookup"><span data-stu-id="101c6-106">This topic lists its member methods and member properties.</span></span> <span data-ttu-id="101c6-107">**$PsISE.CurrentFile** a všechny instance třídy Microsoft.PowerShell.Host.ISE.ISEFile jsou soubory v kolekci soubory na kartě prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="101c6-107">The **$psISE.CurrentFile** and the files in the Files collection in a PowerShell tab are all instances of the Microsoft.PowerShell.Host.ISE.ISEFile class.</span></span>

## <a name="methods"></a><span data-ttu-id="101c6-108">Metody</span><span class="sxs-lookup"><span data-stu-id="101c6-108">Methods</span></span>

### <a name="save-saveencoding-"></a><span data-ttu-id="101c6-109">Uložit\( \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="101c6-109">Save\( \[saveEncoding\] \)</span></span>
  <span data-ttu-id="101c6-110">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-110">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-111">Uloží soubor na disk.</span><span class="sxs-lookup"><span data-stu-id="101c6-111">Saves the file to disk.</span></span>

 <span data-ttu-id="101c6-112">**\[saveEncoding\]**  – volitelné [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx) znakem volitelný parametr, který se má použít pro uložený soubor kódování.</span><span class="sxs-lookup"><span data-stu-id="101c6-112">**\[saveEncoding\]** - optional [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="101c6-113">Výchozí hodnota je **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="101c6-113">The default value is **UTF8**.</span></span>

 <span data-ttu-id="101c6-114">**Výjimky**</span><span class="sxs-lookup"><span data-stu-id="101c6-114">**Exceptions**</span></span>
 -   <span data-ttu-id="101c6-115">**System.IO.IOException**: soubor nelze uložit.</span><span class="sxs-lookup"><span data-stu-id="101c6-115">**System.IO.IOException**: The file could not be saved.</span></span>

```
# Save the file using the default encoding (UTF8)
$psIse.CurrentFile.Save()

# Save the file as ASCII.
$psIse.CurrentFile.Save( [System.Text.Encoding]::ASCII )

# Gets the current encoding.
$myfile=$psIse.CurrentFile
$myfile.Encoding

```

### <a name="saveasfilename-saveencoding"></a><span data-ttu-id="101c6-116">Uložit jako\(filename, \[saveEncoding\]\)</span><span class="sxs-lookup"><span data-stu-id="101c6-116">SaveAs\(filename, \[saveEncoding\]\)</span></span>
  <span data-ttu-id="101c6-117">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-118">Kódování a uloží soubor s názvem zadaného souboru.</span><span class="sxs-lookup"><span data-stu-id="101c6-118">Saves the file with the specified file name and encoding.</span></span>

 <span data-ttu-id="101c6-119">**Název souboru** -String název, který se má použít k uložení souboru.</span><span class="sxs-lookup"><span data-stu-id="101c6-119">**filename** - String The name to be used to save the file.</span></span>

 <span data-ttu-id="101c6-120">**\[saveEncoding\]**  – volitelné [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx) znakem volitelný parametr, který se má použít pro uložený soubor kódování.</span><span class="sxs-lookup"><span data-stu-id="101c6-120">**\[saveEncoding\]** - optional [System.Text.Encoding](http://msdn.microsoft.com/library/system.text.encoding.aspx) An optional character encoding parameter to be used for the saved file.</span></span> <span data-ttu-id="101c6-121">Výchozí hodnota je **UTF8**.</span><span class="sxs-lookup"><span data-stu-id="101c6-121">The default value is **UTF8**.</span></span>

 <span data-ttu-id="101c6-122">**Výjimky**</span><span class="sxs-lookup"><span data-stu-id="101c6-122">**Exceptions**</span></span>
 -   <span data-ttu-id="101c6-123">**System.ArgumentNullException**: **filename** parametr má hodnotu null.</span><span class="sxs-lookup"><span data-stu-id="101c6-123">**System.ArgumentNullException**: The **filename** parameter is null.</span></span>

- <span data-ttu-id="101c6-124">**System.ArgumentException**: **filename** parametr je prázdný.</span><span class="sxs-lookup"><span data-stu-id="101c6-124">**System.ArgumentException**: The **filename** parameter is empty.</span></span>

- <span data-ttu-id="101c6-125">**System.IO.IOException**: soubor nelze uložit.</span><span class="sxs-lookup"><span data-stu-id="101c6-125">**System.IO.IOException**: The file could not be saved.</span></span>

```
# Save the file with a full path and name. 
$fullpath = "c:\temp\newname.txt"
$psIse.CurrentFile.SaveAs($fullPath) 
# Save the file with a full path and name and explicitly as UTF8. 
$psIse.CurrentFile.SaveAs( $fullPath, [System.Text.Encoding]::UTF8 )

```

## <a name="properties"></a><span data-ttu-id="101c6-126">Properties</span><span class="sxs-lookup"><span data-stu-id="101c6-126">Properties</span></span>

### <a name="displayname"></a><span data-ttu-id="101c6-127">DisplayName</span><span class="sxs-lookup"><span data-stu-id="101c6-127">DisplayName</span></span>
  <span data-ttu-id="101c6-128">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-128">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

 <span data-ttu-id="101c6-129">Vlastnost jen pro čtení, který získá řetězec, který obsahuje zobrazovaný název tohoto souboru.</span><span class="sxs-lookup"><span data-stu-id="101c6-129">The read-only property that gets the string that contains the display name of this file.</span></span> <span data-ttu-id="101c6-130">Název se zobrazí na **souboru** v horní části editoru.</span><span class="sxs-lookup"><span data-stu-id="101c6-130">The name is shown on the **File** tab at the top of the editor.</span></span> <span data-ttu-id="101c6-131">Přítomnost hvězdičku \( \* \) na konci názvu označuje, že soubor obsahuje změny, které nebyly uloženy.</span><span class="sxs-lookup"><span data-stu-id="101c6-131">The presence of an asterisk \(\*\) at the end of the name indicates that the file has changes that have not been saved.</span></span>

```
# Shows the display name of the file.
$psIse.CurrentFile.DisplayName

```

### <a name="editor"></a><span data-ttu-id="101c6-132">Editor</span><span class="sxs-lookup"><span data-stu-id="101c6-132">Editor</span></span>
  <span data-ttu-id="101c6-133">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-133">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-134">Vlastnost jen pro čtení, který získá [editoru objektu](The-ISEEditor-Object.md) používané pro zadaný soubor.</span><span class="sxs-lookup"><span data-stu-id="101c6-134">The read-only property that gets the [editor object](The-ISEEditor-Object.md) that is used for the specified file.</span></span>

```
# Gets the editor and the text.
$psIse.CurrentFile.Editor.Text

```

### <a name="encoding"></a><span data-ttu-id="101c6-135">Kódování</span><span class="sxs-lookup"><span data-stu-id="101c6-135">Encoding</span></span>
  <span data-ttu-id="101c6-136">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-136">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-137">Vlastnost jen pro čtení, získá původní kódování souborů.</span><span class="sxs-lookup"><span data-stu-id="101c6-137">The read-only property that gets the original file encoding.</span></span> <span data-ttu-id="101c6-138">Toto je **System.Text.Encoding** objektu.</span><span class="sxs-lookup"><span data-stu-id="101c6-138">This is a **System.Text.Encoding** object.</span></span>

```
# Shows the encoding for the file. 
$psIse.CurrentFile.Encoding

```

### <a name="fullpath"></a><span data-ttu-id="101c6-139">FullPath</span><span class="sxs-lookup"><span data-stu-id="101c6-139">FullPath</span></span>
  <span data-ttu-id="101c6-140">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-140">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-141">Vlastnost jen pro čtení, který získá řetězec, který určuje úplnou cestu otevřený soubor.</span><span class="sxs-lookup"><span data-stu-id="101c6-141">The read-only property that gets the string that specifies the full path of the opened file.</span></span>

```
# Shows the full path for the file. 
$psIse.CurrentFile.FullPath

```

### <a name="issaved"></a><span data-ttu-id="101c6-142">IsSaved</span><span class="sxs-lookup"><span data-stu-id="101c6-142">IsSaved</span></span>
  <span data-ttu-id="101c6-143">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-143">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-144">Jen pro čtení logická hodnota vlastnosti, která vrací **$true** Pokud byl uložen soubor po jeho poslední změny.</span><span class="sxs-lookup"><span data-stu-id="101c6-144">The read-only Boolean property that returns **$true** if the file has been saved after it was last modified.</span></span>

```
# Determines whether the file has been saved since it was last modified.
$myfile=$psIse.CurrentFile
$myfile.IsSaved

```

### <a name="isuntitled"></a><span data-ttu-id="101c6-145">IsUntitled</span><span class="sxs-lookup"><span data-stu-id="101c6-145">IsUntitled</span></span>
  <span data-ttu-id="101c6-146">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="101c6-146">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

 <span data-ttu-id="101c6-147">Vlastnosti jen pro čtení, která vrací **$true** Pokud soubor nikdy nebyla zadána název.</span><span class="sxs-lookup"><span data-stu-id="101c6-147">The read-only property that returns **$true** if the file has never been given a title.</span></span>

```
# Determines whether the file has never been given a title.
$psISE.CurrentFile.IsUntitled
$psISE.CurrentFile.SaveAs("temp.txt")
$psISE.CurrentFile.IsUntitled

```

## <a name="see-also"></a><span data-ttu-id="101c6-148">Viz také</span><span class="sxs-lookup"><span data-stu-id="101c6-148">See Also</span></span>
- [<span data-ttu-id="101c6-149">ISEFileCollectionObject</span><span class="sxs-lookup"><span data-stu-id="101c6-149">The ISEFileCollectionObject</span></span>](The-ISEFileCollection-Object.md) 
- [<span data-ttu-id="101c6-150">ISE Windows PowerShell skriptování objektový Model</span><span class="sxs-lookup"><span data-stu-id="101c6-150">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md) 
- [<span data-ttu-id="101c6-151">Odkaz na objekt modelu Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="101c6-151">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md)
- [<span data-ttu-id="101c6-152">Hierarchie ISE objektů modelu</span><span class="sxs-lookup"><span data-stu-id="101c6-152">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)