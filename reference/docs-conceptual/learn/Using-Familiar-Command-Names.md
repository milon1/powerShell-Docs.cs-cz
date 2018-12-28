---
ms.date: 08/27/2018
keywords: rutiny prostředí PowerShell
title: Použití známých názvů příkazů
ms.assetid: 021e2424-c64e-4fa5-aa98-aa6405758d5d
ms.openlocfilehash: c5665f64fd832eb9c807f413a8e879f63db7f8c6
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53404111"
---
# <a name="using-familiar-command-names"></a><span data-ttu-id="a79c6-103">Použití známých názvů příkazů</span><span class="sxs-lookup"><span data-stu-id="a79c6-103">Using familiar command names</span></span>

<span data-ttu-id="a79c6-104">PowerShell podporuje aliasy jako reference k příkazům alternativní názvy.</span><span class="sxs-lookup"><span data-stu-id="a79c6-104">PowerShell supports aliases to refer to commands by alternate names.</span></span> <span data-ttu-id="a79c6-105">Aliasy umožňuje uživatelům s prostředím v jiné prostředí používat běžné názvy příkazů, které už znáte podobných operací v prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a79c6-105">Aliasing allows users with experience in other shells to use common command names that they already know for similar operations in PowerShell.</span></span>

<span data-ttu-id="a79c6-106">Aliasy přiřadí nový název jiného příkazu.</span><span class="sxs-lookup"><span data-stu-id="a79c6-106">Aliasing associates a new name with another command.</span></span> <span data-ttu-id="a79c6-107">Například Powershellu má vnitřní funkci s názvem `Clear-Host` , který vymaže v okně výstup.</span><span class="sxs-lookup"><span data-stu-id="a79c6-107">For example, PowerShell has an internal function named `Clear-Host` that clears the output window.</span></span> <span data-ttu-id="a79c6-108">Můžete zadat buď `cls` nebo `clear` alias příkazového řádku.</span><span class="sxs-lookup"><span data-stu-id="a79c6-108">You can type either the `cls` or `clear` alias at a command prompt.</span></span> <span data-ttu-id="a79c6-109">Interpretuje tyto aliasy prostředí PowerShell a běží `Clear-Host` funkce.</span><span class="sxs-lookup"><span data-stu-id="a79c6-109">PowerShell interprets these aliases and runs the `Clear-Host` function.</span></span>

<span data-ttu-id="a79c6-110">Tato funkce pomáhá uživatelům předvést prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a79c6-110">This feature helps users to learn PowerShell.</span></span> <span data-ttu-id="a79c6-111">První, většina **cmd.exe** a Unix uživatelé mají velké repertoáru příkazů, které uživatelé již znáte pod názvem.</span><span class="sxs-lookup"><span data-stu-id="a79c6-111">First, most **cmd.exe** and Unix users have a large repertoire of commands that users already know by name.</span></span> <span data-ttu-id="a79c6-112">Ekvivalenty Powershellu nemusí vytvářet identické výsledky.</span><span class="sxs-lookup"><span data-stu-id="a79c6-112">The PowerShell equivalents may not produce identical results.</span></span> <span data-ttu-id="a79c6-113">Výsledky jsou však zavřít dostatek, které uživatelé můžou pracovat bez znalosti názvu příkazu prostředí PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a79c6-113">However, the results are close enough that users can do work without knowing the PowerShell command name.</span></span> <span data-ttu-id="a79c6-114">"Prsty paměti" je jiný hlavní příčiny frustrace při učení nové příkazové okno.</span><span class="sxs-lookup"><span data-stu-id="a79c6-114">"Finger memory" is another major source of frustration when learning a new command shell.</span></span> <span data-ttu-id="a79c6-115">Pokud jste už použili **cmd.exe** let, můžete například reflexively zadat `cls` příkaz pro vymazání obrazovky.</span><span class="sxs-lookup"><span data-stu-id="a79c6-115">If you have used **cmd.exe** for years, you might reflexively type the `cls` command to clear the screen.</span></span> <span data-ttu-id="a79c6-116">Bez aliasu pro `Clear-Host`, zobrazí se chybová zpráva a nebude vědět, co dělat, zrušte výstup.</span><span class="sxs-lookup"><span data-stu-id="a79c6-116">Without the alias for `Clear-Host`, you receive an error message and won't know what to do to clear the output.</span></span>

<span data-ttu-id="a79c6-117">Následující seznam uvádí některé nejběžnější **cmd.exe** a příkazů systému Unix, které můžete použít v prostředí PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a79c6-117">The following list shows a few of the common **cmd.exe** and Unix commands that you can use in PowerShell:</span></span>

|||||
|-|-|-|-|
|<span data-ttu-id="a79c6-118">CAT</span><span class="sxs-lookup"><span data-stu-id="a79c6-118">cat</span></span>|<span data-ttu-id="a79c6-119">adresář</span><span class="sxs-lookup"><span data-stu-id="a79c6-119">dir</span></span>|<span data-ttu-id="a79c6-120">připojení</span><span class="sxs-lookup"><span data-stu-id="a79c6-120">mount</span></span>|<span data-ttu-id="a79c6-121">Správce prostředků</span><span class="sxs-lookup"><span data-stu-id="a79c6-121">rm</span></span>|
|<span data-ttu-id="a79c6-122">CD</span><span class="sxs-lookup"><span data-stu-id="a79c6-122">cd</span></span>|<span data-ttu-id="a79c6-123">echo</span><span class="sxs-lookup"><span data-stu-id="a79c6-123">echo</span></span>|<span data-ttu-id="a79c6-124">Přesunutí</span><span class="sxs-lookup"><span data-stu-id="a79c6-124">move</span></span>|<span data-ttu-id="a79c6-125">rmdir</span><span class="sxs-lookup"><span data-stu-id="a79c6-125">rmdir</span></span>|
|<span data-ttu-id="a79c6-126">chdir</span><span class="sxs-lookup"><span data-stu-id="a79c6-126">chdir</span></span>|<span data-ttu-id="a79c6-127">Vymazání</span><span class="sxs-lookup"><span data-stu-id="a79c6-127">erase</span></span>|<span data-ttu-id="a79c6-128">popd</span><span class="sxs-lookup"><span data-stu-id="a79c6-128">popd</span></span>|<span data-ttu-id="a79c6-129">Přejít do režimu spánku</span><span class="sxs-lookup"><span data-stu-id="a79c6-129">sleep</span></span>|
|<span data-ttu-id="a79c6-130">Vymazat</span><span class="sxs-lookup"><span data-stu-id="a79c6-130">clear</span></span>|<span data-ttu-id="a79c6-131">H</span><span class="sxs-lookup"><span data-stu-id="a79c6-131">h</span></span>|<span data-ttu-id="a79c6-132">PS</span><span class="sxs-lookup"><span data-stu-id="a79c6-132">ps</span></span>|<span data-ttu-id="a79c6-133">Řazení</span><span class="sxs-lookup"><span data-stu-id="a79c6-133">sort</span></span>|
|<span data-ttu-id="a79c6-134">specifikace CLS</span><span class="sxs-lookup"><span data-stu-id="a79c6-134">cls</span></span>|<span data-ttu-id="a79c6-135">Historie</span><span class="sxs-lookup"><span data-stu-id="a79c6-135">history</span></span>|<span data-ttu-id="a79c6-136">pushd</span><span class="sxs-lookup"><span data-stu-id="a79c6-136">pushd</span></span>|<span data-ttu-id="a79c6-137">TEE</span><span class="sxs-lookup"><span data-stu-id="a79c6-137">tee</span></span>|
|<span data-ttu-id="a79c6-138">Kopírování</span><span class="sxs-lookup"><span data-stu-id="a79c6-138">copy</span></span>|<span data-ttu-id="a79c6-139">ukončit</span><span class="sxs-lookup"><span data-stu-id="a79c6-139">kill</span></span>|<span data-ttu-id="a79c6-140">PWD</span><span class="sxs-lookup"><span data-stu-id="a79c6-140">pwd</span></span>|<span data-ttu-id="a79c6-141">typ</span><span class="sxs-lookup"><span data-stu-id="a79c6-141">type</span></span>|
|<span data-ttu-id="a79c6-142">del</span><span class="sxs-lookup"><span data-stu-id="a79c6-142">del</span></span>|<span data-ttu-id="a79c6-143">LP</span><span class="sxs-lookup"><span data-stu-id="a79c6-143">lp</span></span>|<span data-ttu-id="a79c6-144">r</span><span class="sxs-lookup"><span data-stu-id="a79c6-144">r</span></span>|<span data-ttu-id="a79c6-145">zápis</span><span class="sxs-lookup"><span data-stu-id="a79c6-145">write</span></span>|
|<span data-ttu-id="a79c6-146">diff</span><span class="sxs-lookup"><span data-stu-id="a79c6-146">diff</span></span>|<span data-ttu-id="a79c6-147">Ls</span><span class="sxs-lookup"><span data-stu-id="a79c6-147">ls</span></span>|<span data-ttu-id="a79c6-148">ren</span><span class="sxs-lookup"><span data-stu-id="a79c6-148">ren</span></span>||

<span data-ttu-id="a79c6-149">`Get-Alias` Rutiny se dozvíte, skutečným názvem nativní příkaz prostředí PowerShell, které jsou spojené s aliasem.</span><span class="sxs-lookup"><span data-stu-id="a79c6-149">The `Get-Alias` cmdlet shows you the real name of the native PowerShell command associated with an alias.</span></span>

```powershell
PS> Get-Alias cls
```

```Output
CommandType     Name                               Version    Source
-----------     ----                               -------    ------
Alias           cls -> Clear-Host
```

## <a name="interpreting-standard-aliases"></a><span data-ttu-id="a79c6-150">Interpretace standardní aliasy</span><span class="sxs-lookup"><span data-stu-id="a79c6-150">Interpreting standard aliases</span></span>

<span data-ttu-id="a79c6-151">Aliasy jsme popisuje předchozí byly navrženy pro název kompatibilitu s další příkazových prostředích systémů.</span><span class="sxs-lookup"><span data-stu-id="a79c6-151">The aliases we described previous were designed for name-compatibility with other command shells.</span></span>
<span data-ttu-id="a79c6-152">Většina aliasy, které jsou integrované do prostředí PowerShell jsou navržené pro zkrácení.</span><span class="sxs-lookup"><span data-stu-id="a79c6-152">Most aliases built into PowerShell are designed for brevity.</span></span> <span data-ttu-id="a79c6-153">Je snazší typu, ale jsou obtížně čitelné, pokud neznáte odkazují na kratší názvy.</span><span class="sxs-lookup"><span data-stu-id="a79c6-153">Shorter names are easier to type, but are difficult to read if you don't know what they refer to.</span></span>

<span data-ttu-id="a79c6-154">Aliasy prostředí PowerShell se pokusí najít kompromis mezi jasné a zkrácení.</span><span class="sxs-lookup"><span data-stu-id="a79c6-154">PowerShell aliases try to compromise between clarity and brevity.</span></span> <span data-ttu-id="a79c6-155">PowerShell používá standardní sadu aliasy pro běžné podstatná jména a příkazy.</span><span class="sxs-lookup"><span data-stu-id="a79c6-155">PowerShell uses a standard set of aliases for common nouns and verbs.</span></span>

<span data-ttu-id="a79c6-156">Příklad zkratky:</span><span class="sxs-lookup"><span data-stu-id="a79c6-156">Example abbreviations:</span></span>

| <span data-ttu-id="a79c6-157">Podstatné jméno nebo příkaz</span><span class="sxs-lookup"><span data-stu-id="a79c6-157">Noun or Verb</span></span> | <span data-ttu-id="a79c6-158">Zkratka</span><span class="sxs-lookup"><span data-stu-id="a79c6-158">Abbreviation</span></span> |
|--------------|--------------|
| <span data-ttu-id="a79c6-159">Get</span><span class="sxs-lookup"><span data-stu-id="a79c6-159">Get</span></span>          | <span data-ttu-id="a79c6-160">G</span><span class="sxs-lookup"><span data-stu-id="a79c6-160">g</span></span>            |
| <span data-ttu-id="a79c6-161">Nastavit</span><span class="sxs-lookup"><span data-stu-id="a79c6-161">Set</span></span>          | <span data-ttu-id="a79c6-162">s</span><span class="sxs-lookup"><span data-stu-id="a79c6-162">s</span></span>            |
| <span data-ttu-id="a79c6-163">Položka</span><span class="sxs-lookup"><span data-stu-id="a79c6-163">Item</span></span>         | <span data-ttu-id="a79c6-164">Můžu</span><span class="sxs-lookup"><span data-stu-id="a79c6-164">i</span></span>            |
| <span data-ttu-id="a79c6-165">Umístění</span><span class="sxs-lookup"><span data-stu-id="a79c6-165">Location</span></span>     | <span data-ttu-id="a79c6-166">L</span><span class="sxs-lookup"><span data-stu-id="a79c6-166">l</span></span>            |
| <span data-ttu-id="a79c6-167">Příkaz</span><span class="sxs-lookup"><span data-stu-id="a79c6-167">Command</span></span>      | <span data-ttu-id="a79c6-168">cm</span><span class="sxs-lookup"><span data-stu-id="a79c6-168">cm</span></span>           |
| <span data-ttu-id="a79c6-169">Alias</span><span class="sxs-lookup"><span data-stu-id="a79c6-169">Alias</span></span>        | <span data-ttu-id="a79c6-170">Al</span><span class="sxs-lookup"><span data-stu-id="a79c6-170">al</span></span>           |

<span data-ttu-id="a79c6-171">Tyto aliasy jsou srozumitelné, když víte, zkrácené názvy.</span><span class="sxs-lookup"><span data-stu-id="a79c6-171">These aliases are understandable when you know the shorthand names.</span></span>

| <span data-ttu-id="a79c6-172">Název rutiny</span><span class="sxs-lookup"><span data-stu-id="a79c6-172">Cmdlet name</span></span>    | <span data-ttu-id="a79c6-173">Alias</span><span class="sxs-lookup"><span data-stu-id="a79c6-173">Alias</span></span> |
|----------------|-------|
| `Get-Item `    | <span data-ttu-id="a79c6-174">grafického rozhraní</span><span class="sxs-lookup"><span data-stu-id="a79c6-174">gi</span></span>    |
| `Set-Item`     | <span data-ttu-id="a79c6-175">si</span><span class="sxs-lookup"><span data-stu-id="a79c6-175">si</span></span>    |
| `Get-Location` | <span data-ttu-id="a79c6-176">GL</span><span class="sxs-lookup"><span data-stu-id="a79c6-176">gl</span></span>    |
| `Set-Location` | <span data-ttu-id="a79c6-177">SL</span><span class="sxs-lookup"><span data-stu-id="a79c6-177">sl</span></span>    |
| `Get-Command`  | <span data-ttu-id="a79c6-178">gcm</span><span class="sxs-lookup"><span data-stu-id="a79c6-178">gcm</span></span>   |
| `Get-Alias`    | <span data-ttu-id="a79c6-179">GAL</span><span class="sxs-lookup"><span data-stu-id="a79c6-179">gal</span></span>   |

<span data-ttu-id="a79c6-180">Jakmile jste obeznámeni s aliasy prostředí PowerShell, je snadno uhodnutelné, který **sal** alias odkazuje na `Set-Alias`.</span><span class="sxs-lookup"><span data-stu-id="a79c6-180">Once you're familiar with PowerShell aliasing, it's easy to guess that the **sal** alias refers to `Set-Alias`.</span></span>

## <a name="creating-new-aliases"></a><span data-ttu-id="a79c6-181">Vytváří se nový aliasy</span><span class="sxs-lookup"><span data-stu-id="a79c6-181">Creating new aliases</span></span>

<span data-ttu-id="a79c6-182">Můžete vytvořit vlastní aliasy pomocí `Set-Alias` rutiny.</span><span class="sxs-lookup"><span data-stu-id="a79c6-182">You can create your own aliases using the `Set-Alias` cmdlet.</span></span> <span data-ttu-id="a79c6-183">Například následující příkazy vytvoří standardní rutiny aliasy jsme uvedli:</span><span class="sxs-lookup"><span data-stu-id="a79c6-183">For example, the following statements create the standard cmdlet aliases previously discussed:</span></span>

```powershell
Set-Alias -Name gi -Value Get-Item
Set-Alias -Name si -Value Set-Item
Set-Alias -Name gl -Value Get-Location
Set-Alias -Name sl -Value Set-Location
Set-Alias -Name gcm -Value Get-Command
```

<span data-ttu-id="a79c6-184">Interně prostředí PowerShell používá podobné příkazy během spouštění, ale nejsou změnit tyto aliasy.</span><span class="sxs-lookup"><span data-stu-id="a79c6-184">Internally, PowerShell uses similar commands during startup, but these aliases are not changeable.</span></span>
<span data-ttu-id="a79c6-185">Pokud se pokusíte provést jednu z těchto příkazů, obdržíte chybu s vysvětlením, že alias nelze upravit.</span><span class="sxs-lookup"><span data-stu-id="a79c6-185">If you try to execute one of these commands, you get an error explaining that the alias can't be modified.</span></span> <span data-ttu-id="a79c6-186">Příklad:</span><span class="sxs-lookup"><span data-stu-id="a79c6-186">For example:</span></span>

```
PS> Set-Alias -Name gi -Value Get-Item
Set-Alias : Alias is not writeable because alias gi is read-only or constant and cannot be written to.
At line:1 char:10
+ Set-Alias  <<<< -Name gi -Value Get-Item
```