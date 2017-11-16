---
ms.date: 2017-06-05
keywords: "rutiny prostředí PowerShell"
title: "Pomocí karty rozšíření"
ms.assetid: c8730471-bf6a-43b8-ab1d-f9ef5a74f04e
ms.openlocfilehash: 8412bd97a95719f07b16c6671d3b8801bbfab8e3
ms.sourcegitcommit: 4807ab554d55fdee499980835bcc279368b1df68
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="using-tab-expansion"></a><span data-ttu-id="52f59-103">Pomocí karty rozšíření</span><span class="sxs-lookup"><span data-stu-id="52f59-103">Using Tab Expansion</span></span>
<span data-ttu-id="52f59-104">Prostředí shell příkazového řádku často poskytují způsob, jak automaticky dokončit názvy dlouhé soubory nebo příkazy urychlení zadání příkazu a poskytuje.</span><span class="sxs-lookup"><span data-stu-id="52f59-104">Command-line shells often provide a way to complete the names of long files or commands automatically, speeding up command entry and providing .</span></span> <span data-ttu-id="52f59-105">Prostředí Windows PowerShell umožňuje zadejte názvy souborů a rutiny stisknutím **kartě** klíč.</span><span class="sxs-lookup"><span data-stu-id="52f59-105">Windows PowerShell allows you to fill in file names and cmdlet names by pressing the **Tab** key.</span></span>

> [!NOTE]
> <span data-ttu-id="52f59-106">Vnitřní funkce TabExpansion nebo TabExpansion2 řídí karta rozšíření.</span><span class="sxs-lookup"><span data-stu-id="52f59-106">Tab expansion is controlled by the internal function TabExpansion or TabExpansion2.</span></span> <span data-ttu-id="52f59-107">Vzhledem k tomu, že tuto funkci můžete upravit nebo přepsat, je toto pojednání Průvodce chování výchozí konfigurace prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52f59-107">Since this function can be modified or overridden, this discussion is a guide to the behavior of the default PowerShell configuration.</span></span>

<span data-ttu-id="52f59-108">Zadejte název souboru nebo cestu z dostupných možností automaticky, zadejte část názvu a stiskněte klávesu **kartě** klíč.</span><span class="sxs-lookup"><span data-stu-id="52f59-108">To fill in a filename or path from the available choices automatically, type part of the name and press the **Tab** key.</span></span> <span data-ttu-id="52f59-109">Prostředí PowerShell bude automaticky rozbalte název na první shodu, která najde.</span><span class="sxs-lookup"><span data-stu-id="52f59-109">PowerShell will automatically expand the name to the first match that it finds.</span></span> <span data-ttu-id="52f59-110">Stisknutím **kartě** klíč opakovaně bude procházet všechny dostupné možnosti.</span><span class="sxs-lookup"><span data-stu-id="52f59-110">Pressing the **Tab** key repeatedly will cycle through all of the available choices.</span></span>

<span data-ttu-id="52f59-111">Karta rozšíření názvů rutiny se poněkud liší.</span><span class="sxs-lookup"><span data-stu-id="52f59-111">The tab expansion of cmdlet names is slightly different.</span></span> <span data-ttu-id="52f59-112">K rozšíření karta na název rutiny, zadejte celý první část názvu (akce) a pomlčky, který následuje.</span><span class="sxs-lookup"><span data-stu-id="52f59-112">To use tab expansion on a cmdlet name, type the entire first part of the name (the verb) and the hyphen that follows it.</span></span> <span data-ttu-id="52f59-113">Můžete vyplnit více název částečnou shodu.</span><span class="sxs-lookup"><span data-stu-id="52f59-113">You can fill in more of the name for a partial match.</span></span> <span data-ttu-id="52f59-114">Pokud zadáte například **get-co** a potom stiskněte klávesu **kartě** klíče, prostředí PowerShell se automaticky rozšíří na **Get-Command** rutiny (Všimněte si, že změní také případě písmen jejich standardní formuláře).</span><span class="sxs-lookup"><span data-stu-id="52f59-114">For example, if you type **get-co** and then press the **Tab** key, PowerShell will automatically expand this to the **Get-Command** cmdlet (notice that it also changes the case of letters to their standard form).</span></span> <span data-ttu-id="52f59-115">Pokud vyberete **kartě** klíče znovu, prostředí PowerShell nahradí to jenom jiné odpovídající název, **Get-Content**.</span><span class="sxs-lookup"><span data-stu-id="52f59-115">If you press **Tab** key again, PowerShell replaces this with the only other matching cmdlet name, **Get-Content**.</span></span>

<span data-ttu-id="52f59-116">Karta rozšíření můžete opakovaně použít na stejném řádku.</span><span class="sxs-lookup"><span data-stu-id="52f59-116">You can use tab expansion repeatedly on the same line.</span></span> <span data-ttu-id="52f59-117">Například můžete použít kartu rozšíření na název **Get-Content** rutiny zadáním:</span><span class="sxs-lookup"><span data-stu-id="52f59-117">For example, you can use tab expansion on the name of the **Get-Content** cmdlet by entering:</span></span>

```
PS> Get-Con<Tab>
```

<span data-ttu-id="52f59-118">Po stisknutí klávesy **kartě** klíče, příkaz zasahuje do:</span><span class="sxs-lookup"><span data-stu-id="52f59-118">When you press the **Tab** key, the command expands to:</span></span>

```
PS> Get-Content
```

<span data-ttu-id="52f59-119">Můžete pak částečně zadejte cestu k souboru protokolu aktivní instalace a použít karta rozšíření znovu:</span><span class="sxs-lookup"><span data-stu-id="52f59-119">You can then partially specify the path to the Active Setup log file and use tab expansion again:</span></span>

```
PS> Get-Content c:\windows\acts<Tab>
```

<span data-ttu-id="52f59-120">Po stisknutí klávesy **kartě** klíče, příkaz zasahuje do:</span><span class="sxs-lookup"><span data-stu-id="52f59-120">When you press the **Tab** key, the command expands to:</span></span>

```
PS> Get-Content C:\windows\actsetup.log
```

> [!NOTE]
> <span data-ttu-id="52f59-121">Jedním z omezení karta rozšíření procesu je, že jsou karty vždy vyhodnocena jako pokusy o dokončení slovo.</span><span class="sxs-lookup"><span data-stu-id="52f59-121">One limitation of the tab expansion process is that tabs are always interpreted as attempts to complete a word.</span></span> <span data-ttu-id="52f59-122">Pokud je kopírujete a vkládáte příkladech do konzoly prostředí PowerShell, ujistěte se, že ukázku neobsahuje karty; Pokud ano, nepředvídatelné výsledky a nebude skoro určitě předpokladům.</span><span class="sxs-lookup"><span data-stu-id="52f59-122">If you copy and paste command examples into a PowerShell console, make sure that the sample does not contain tabs; if it does, the results will be unpredictable and will almost certainly not be what you intended.</span></span>
