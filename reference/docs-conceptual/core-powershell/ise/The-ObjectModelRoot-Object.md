---
ms.date: 2017-08-25
keywords: "rutiny prostředí PowerShell"
title: Objekt ObjectModelRoot
ms.openlocfilehash: eb3424ff147c35364fa08543d59ebd30f6d2d857
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2017
---
# <a name="the-objectmodelroot-object"></a><span data-ttu-id="247c0-103">Objekt ObjectModelRoot</span><span class="sxs-lookup"><span data-stu-id="247c0-103">The ObjectModelRoot Object</span></span>

<span data-ttu-id="247c0-104">**$PsISE** objekt, který je hlavní kořenový objekt ve Windows PowerShell® Integrované skriptovací prostředí (ISE) je instance třídy Microsoft.PowerShell.Host.ISE.ObjectModelRoot.</span><span class="sxs-lookup"><span data-stu-id="247c0-104">The **$psISE** object, which is the principal root object in Windows PowerShell® Integrated Scripting Environment (ISE) is an instance of the Microsoft.PowerShell.Host.ISE.ObjectModelRoot class.</span></span>
<span data-ttu-id="247c0-105">Toto téma popisuje vlastnosti **ObjectModelRoot** objektu.</span><span class="sxs-lookup"><span data-stu-id="247c0-105">This topic describes the properties of the **ObjectModelRoot** object.</span></span>

## <a name="properties"></a><span data-ttu-id="247c0-106">Properties</span><span class="sxs-lookup"><span data-stu-id="247c0-106">Properties</span></span>

### <a name="currentfile"></a><span data-ttu-id="247c0-107">CurrentFile</span><span class="sxs-lookup"><span data-stu-id="247c0-107">CurrentFile</span></span>

> <span data-ttu-id="247c0-108">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-108">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

<span data-ttu-id="247c0-109">Vlastnost jen pro čtení, získá soubor, který je přidružen k tomuto objektu hostitele, který je aktuálně aktivní.</span><span class="sxs-lookup"><span data-stu-id="247c0-109">The read-only property that gets the file, which is associated with this host object that currently has the focus.</span></span>

### <a name="currentpowershelltab"></a><span data-ttu-id="247c0-110">CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="247c0-110">CurrentPowerShellTab</span></span>

> <span data-ttu-id="247c0-111">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-111">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="247c0-112">Vlastnost jen pro čtení, získá kartě prostředí PowerShell, který je aktivní.</span><span class="sxs-lookup"><span data-stu-id="247c0-112">The read-only property that gets the PowerShell tab that has the focus.</span></span>

### <a name="currentvisiblehorizontaltool"></a><span data-ttu-id="247c0-113">CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="247c0-113">CurrentVisibleHorizontalTool</span></span>

> <span data-ttu-id="247c0-114">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-114">Supported in Windows PowerShell ISE 2.0 and later.</span></span>

<span data-ttu-id="247c0-115">Vlastnost jen pro čtení, který získá aktuálně viditelné nástroj rozšíření Windows PowerShell ISE, který se nachází v podokně vodorovné nástrojů v dolní části editoru.</span><span class="sxs-lookup"><span data-stu-id="247c0-115">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the horizontal tool pane at the bottom of the editor.</span></span>

### <a name="currentvisibleverticaltool"></a><span data-ttu-id="247c0-116">CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="247c0-116">CurrentVisibleVerticalTool</span></span>

> <span data-ttu-id="247c0-117">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-117">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

<span data-ttu-id="247c0-118">Vlastnost jen pro čtení, který získá aktuálně viditelné nástroj rozšíření Windows PowerShell ISE, který se nachází v podokně svislý nástroj na pravé straně editoru.</span><span class="sxs-lookup"><span data-stu-id="247c0-118">The read-only property that gets the currently visible Windows PowerShell ISE add-on tool that is located in the vertical tool pane on the right side of the editor.</span></span>

### <a name="options"></a><span data-ttu-id="247c0-119">Možnosti</span><span class="sxs-lookup"><span data-stu-id="247c0-119">Options</span></span>

> <span data-ttu-id="247c0-120">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-120">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

<span data-ttu-id="247c0-121">Vlastnost jen pro čtení, který získá různé možnosti, které mohou změnit nastavení v systému Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="247c0-121">The read-only property that gets the various options that can change settings in Windows PowerShell ISE.</span></span>

### <a name="powershelltabs"></a><span data-ttu-id="247c0-122">PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="247c0-122">PowerShellTabs</span></span>

> <span data-ttu-id="247c0-123">Podporuje se v prostředí Windows PowerShell ISE 2.0 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="247c0-123">Supported in Windows PowerShell ISE 2.0 and later.</span></span> 

<span data-ttu-id="247c0-124">Vlastnost jen pro čtení, získá kolekci karet prostředí PowerShell, které jsou otevřeny v systému Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="247c0-124">The read-only property that gets the collection of the PowerShell tabs, which are open in Windows PowerShell ISE.</span></span> <span data-ttu-id="247c0-125">Ve výchozím nastavení tento objekt obsahuje jedné karty prostředí PowerShell. Můžete ale přidat další karty prostředí PowerShell k tomuto objektu, pomocí skriptů nebo pomocí nabídek v systému Windows PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="247c0-125">By default, this object contains one PowerShell tab. However, you can add more PowerShell tabs to this object by using scripts or by using the menus in Windows PowerShell ISE.</span></span>

## <a name="see-also"></a><span data-ttu-id="247c0-126">Viz také</span><span class="sxs-lookup"><span data-stu-id="247c0-126">See Also</span></span>

- [<span data-ttu-id="247c0-127">ISE Windows PowerShell skriptování objektový Model</span><span class="sxs-lookup"><span data-stu-id="247c0-127">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="247c0-128">Odkaz na objekt modelu Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="247c0-128">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md)
- [<span data-ttu-id="247c0-129">Hierarchie ISE objektů modelu</span><span class="sxs-lookup"><span data-stu-id="247c0-129">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)