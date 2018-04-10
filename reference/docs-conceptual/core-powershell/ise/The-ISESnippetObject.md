---
ms.date: 06/05/2017
keywords: rutiny prostředí PowerShell
title: Objekt ISESnippetObject
ms.assetid: 98bc8113-c3cd-4201-bdb9-9d9bdb7e266c
ms.openlocfilehash: f80080f4207cf226fb7466c4842446d08c081347
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2018
---
# <a name="the-isesnippetobject"></a><span data-ttu-id="a7b2f-103">Objekt ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="a7b2f-103">The ISESnippetObject</span></span>

<span data-ttu-id="a7b2f-104">**ISESnippet** objekt je instance třídy Microsoft.PowerShell.Host.ISE.ISESnippet.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-104">An **ISESnippet** object is an instance of the Microsoft.PowerShell.Host.ISE.ISESnippet class.</span></span> <span data-ttu-id="a7b2f-105">Členové **$psISE.CurrentPowerShellTab.Snippets** kolekce jsou všechny příklady **ISESnippet** objekty.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-105">The members of the **$psISE.CurrentPowerShellTab.Snippets** collection are all examples of **ISESnippet** objects.</span></span> <span data-ttu-id="a7b2f-106">Nejjednodušší způsob, jak vytvořit fragment je použití [New-IseSnippet&#91;PSITPro5_ISE&#93; ](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) rutiny.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-106">The easiest way to create a snippet is to use the [New-IseSnippet&#91;PSITPro5_ISE&#93;](https://technet.microsoft.com/library/0a6339a3-2683-4a8e-8929-90ad9a95c3e0) cmdlet.</span></span>

## <a name="properties"></a><span data-ttu-id="a7b2f-107">Properties</span><span class="sxs-lookup"><span data-stu-id="a7b2f-107">Properties</span></span>

### <a name="author"></a><span data-ttu-id="a7b2f-108">Autor</span><span class="sxs-lookup"><span data-stu-id="a7b2f-108">Author</span></span>

<span data-ttu-id="a7b2f-109">Podporované v prostředí Windows PowerShell ISE 3.0 a novější a nejsou k dispozici v dřívějších verzích.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="a7b2f-110">Vlastnost jen pro čtení, získá jméno autora fragmentu.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-110">The read-only property that gets the name of the author of the snippet.</span></span>

```powershell
# Get the author of the first snippet item
$psISE.CurrentPowerShellTab.Snippets.Item(0).Author
```

### <a name="codefragment"></a><span data-ttu-id="a7b2f-111">CodeFragment</span><span class="sxs-lookup"><span data-stu-id="a7b2f-111">CodeFragment</span></span>

<span data-ttu-id="a7b2f-112">Podporované v prostředí Windows PowerShell ISE 3.0 a novější a nejsou k dispozici v dřívějších verzích.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-112">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="a7b2f-113">Vlastnost jen pro čtení, získá fragment kódu, který má být vložen do editoru.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-113">The read-only property that gets the code fragment to be inserted into the editor.</span></span>

```powershell
# Get the code fragment associated with the first snippet item.
$psISE.CurrentPowerShellTab.Snippets.Item(0).CodeFragment
```

### <a name="shortcut"></a><span data-ttu-id="a7b2f-114">Zástupce</span><span class="sxs-lookup"><span data-stu-id="a7b2f-114">Shortcut</span></span>

<span data-ttu-id="a7b2f-115">Podporované v prostředí Windows PowerShell ISE 3.0 a novější a nejsou k dispozici v dřívějších verzích.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-115">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="a7b2f-116">Vlastnost jen pro čtení, který získá Windows klávesové zkratky pro položku nabídky.</span><span class="sxs-lookup"><span data-stu-id="a7b2f-116">The read-only property that gets the Windows keyboard shortcut for the menu item.</span></span>

```powershell
# Get the shortcut for the first submenu item.
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Clear()
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus.Add('_Process', {Get-Process}, 'Alt+P')
$psISE.CurrentPowerShellTab.AddOnsMenu.Submenus[0].Shortcut
```

## <a name="see-also"></a><span data-ttu-id="a7b2f-117">Viz také</span><span class="sxs-lookup"><span data-stu-id="a7b2f-117">See Also</span></span>

- [<span data-ttu-id="a7b2f-118">Objekt ISESnippetCollection</span><span class="sxs-lookup"><span data-stu-id="a7b2f-118">The ISESnippetCollection Object</span></span>](The-ISESnippetCollection-Object.md)
- [<span data-ttu-id="a7b2f-119">Účelem ISE Windows PowerShell skriptování objektový Model</span><span class="sxs-lookup"><span data-stu-id="a7b2f-119">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](purpose-of-the-windows-powershell-ise-scripting-object-model.md)
- [<span data-ttu-id="a7b2f-120">Hierarchie objektového modelu prostředí ISE</span><span class="sxs-lookup"><span data-stu-id="a7b2f-120">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)