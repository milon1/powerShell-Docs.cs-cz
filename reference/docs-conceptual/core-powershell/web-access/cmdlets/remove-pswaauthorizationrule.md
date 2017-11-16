---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "rutiny prostředí PowerShell"
ms.date: 2016-12-12
title: odebrat pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: a8304b68a446de0be98aa732304c71302fb8389e
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2017
---
# <a name="remove-pswaauthorizationrule"></a><span data-ttu-id="2a55c-103">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2a55c-103">Remove-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="2a55c-104">STRUČNÝ OBSAH</span><span class="sxs-lookup"><span data-stu-id="2a55c-104">SYNOPSIS</span></span>

<span data-ttu-id="2a55c-105">Odebere zadané autorizační pravidlo z Windows PowerShell® Web Access.</span><span class="sxs-lookup"><span data-stu-id="2a55c-105">Removes a specified authorization rule from Windows PowerShell® Web Access.</span></span>

## <a name="syntax"></a><span data-ttu-id="2a55c-106">SYNTAXE</span><span class="sxs-lookup"><span data-stu-id="2a55c-106">SYNTAX</span></span>

### <a name="id"></a><span data-ttu-id="2a55c-107">Id</span><span class="sxs-lookup"><span data-stu-id="2a55c-107">Id</span></span>
```
Remove-PswaAuthorizationRule [-Id] <Int32[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

### <a name="rule"></a><span data-ttu-id="2a55c-108">Pravidlo</span><span class="sxs-lookup"><span data-stu-id="2a55c-108">Rule</span></span>
```
Remove-PswaAuthorizationRule [-Rule] <PswaAuthorizationRule[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="2a55c-109">POPIS</span><span class="sxs-lookup"><span data-stu-id="2a55c-109">DESCRIPTION</span></span>

<span data-ttu-id="2a55c-110">Odebere zadané autorizační pravidlo z Windows PowerShell Web Access.</span><span class="sxs-lookup"><span data-stu-id="2a55c-110">Removes a specified authorization rule from Windows PowerShell Web Access.</span></span>

## <a name="parameters"></a><span data-ttu-id="2a55c-111">PARAMETRY</span><span class="sxs-lookup"><span data-stu-id="2a55c-111">PARAMETERS</span></span>

### <a name="-force"></a><span data-ttu-id="2a55c-112">-Force</span><span class="sxs-lookup"><span data-stu-id="2a55c-112">-Force</span></span>

<span data-ttu-id="2a55c-113">Spustí se bez zobrazení výzvy k potvrzení.</span><span class="sxs-lookup"><span data-stu-id="2a55c-113">Runs the cmdlet without prompting for confirmation.</span></span> <span data-ttu-id="2a55c-114">Ve výchozím nastavení rutina požádá o potvrzení, než budete pokračovat.</span><span class="sxs-lookup"><span data-stu-id="2a55c-114">By default the cmdlet asks for confirmation before proceeding.</span></span>

|||  
|-|-|
| <span data-ttu-id="2a55c-115">Aliasy</span><span class="sxs-lookup"><span data-stu-id="2a55c-115">Aliases</span></span>                              | <span data-ttu-id="2a55c-116">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-116">none</span></span>                                 |
| <span data-ttu-id="2a55c-117">Povinné?</span><span class="sxs-lookup"><span data-stu-id="2a55c-117">Required?</span></span>                            | <span data-ttu-id="2a55c-118">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-118">false</span></span>                                |
| <span data-ttu-id="2a55c-119">Pozice?</span><span class="sxs-lookup"><span data-stu-id="2a55c-119">Position?</span></span>                            | <span data-ttu-id="2a55c-120">S názvem</span><span class="sxs-lookup"><span data-stu-id="2a55c-120">named</span></span>                                |
| <span data-ttu-id="2a55c-121">Výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="2a55c-121">Default Value</span></span>                        | <span data-ttu-id="2a55c-122">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-122">none</span></span>                                 |
| <span data-ttu-id="2a55c-123">Přijmout kanálový vstup?</span><span class="sxs-lookup"><span data-stu-id="2a55c-123">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2a55c-124">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-124">false</span></span>                                |
| <span data-ttu-id="2a55c-125">Přijímat zástupné znaky?</span><span class="sxs-lookup"><span data-stu-id="2a55c-125">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2a55c-126">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-126">false</span></span>                                |

### <a name="-id-ltint32gt"></a><span data-ttu-id="2a55c-127">-Id &lt;Int32\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="2a55c-127">-Id &lt;Int32\[\]&gt;</span></span>

<span data-ttu-id="2a55c-128">Určuje identifikátory (ID) jeden nebo více pravidel odebrat.</span><span class="sxs-lookup"><span data-stu-id="2a55c-128">Specifies the identifiers (IDs) of one or more rules to remove.</span></span>

|||  
|-|-|
| <span data-ttu-id="2a55c-129">Aliasy</span><span class="sxs-lookup"><span data-stu-id="2a55c-129">Aliases</span></span>                              | <span data-ttu-id="2a55c-130">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-130">none</span></span>                                 |
| <span data-ttu-id="2a55c-131">Povinné?</span><span class="sxs-lookup"><span data-stu-id="2a55c-131">Required?</span></span>                            | <span data-ttu-id="2a55c-132">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="2a55c-132">true</span></span>                                 |
| <span data-ttu-id="2a55c-133">Pozice?</span><span class="sxs-lookup"><span data-stu-id="2a55c-133">Position?</span></span>                            | <span data-ttu-id="2a55c-134">2</span><span class="sxs-lookup"><span data-stu-id="2a55c-134">2</span></span>                                    |
| <span data-ttu-id="2a55c-135">Výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="2a55c-135">Default Value</span></span>                        | <span data-ttu-id="2a55c-136">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-136">none</span></span>                                 |
| <span data-ttu-id="2a55c-137">Přijmout kanálový vstup?</span><span class="sxs-lookup"><span data-stu-id="2a55c-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2a55c-138">Hodnotu true (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="2a55c-138">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="2a55c-139">Přijímat zástupné znaky?</span><span class="sxs-lookup"><span data-stu-id="2a55c-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2a55c-140">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-140">false</span></span>                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a><span data-ttu-id="2a55c-141">-Pravidla &lt;PswaAuthorizationRule\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="2a55c-141">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span></span>

<span data-ttu-id="2a55c-142">Určuje pravidla k odebrání.</span><span class="sxs-lookup"><span data-stu-id="2a55c-142">Specifies the rules to remove.</span></span>

|||  
|-|-|
| <span data-ttu-id="2a55c-143">Aliasy</span><span class="sxs-lookup"><span data-stu-id="2a55c-143">Aliases</span></span>                              | <span data-ttu-id="2a55c-144">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-144">none</span></span>                                 |
| <span data-ttu-id="2a55c-145">Povinné?</span><span class="sxs-lookup"><span data-stu-id="2a55c-145">Required?</span></span>                            | <span data-ttu-id="2a55c-146">Hodnota TRUE</span><span class="sxs-lookup"><span data-stu-id="2a55c-146">true</span></span>                                 |
| <span data-ttu-id="2a55c-147">Pozice?</span><span class="sxs-lookup"><span data-stu-id="2a55c-147">Position?</span></span>                            | <span data-ttu-id="2a55c-148">2</span><span class="sxs-lookup"><span data-stu-id="2a55c-148">2</span></span>                                    |
| <span data-ttu-id="2a55c-149">Výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="2a55c-149">Default Value</span></span>                        | <span data-ttu-id="2a55c-150">žádný</span><span class="sxs-lookup"><span data-stu-id="2a55c-150">none</span></span>                                 |
| <span data-ttu-id="2a55c-151">Přijmout kanálový vstup?</span><span class="sxs-lookup"><span data-stu-id="2a55c-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2a55c-152">Hodnotu true (ByValue)</span><span class="sxs-lookup"><span data-stu-id="2a55c-152">True (ByValue)</span></span>                       |
| <span data-ttu-id="2a55c-153">Přijímat zástupné znaky?</span><span class="sxs-lookup"><span data-stu-id="2a55c-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2a55c-154">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-154">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="2a55c-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="2a55c-155">-Confirm</span></span>

<span data-ttu-id="2a55c-156">Před spuštěním rutiny zobrazí výzvu k potvrzení.</span><span class="sxs-lookup"><span data-stu-id="2a55c-156">Prompts you for confirmation before running the cmdlet.</span></span>

|||  
|-|-|
| <span data-ttu-id="2a55c-157">Povinné?</span><span class="sxs-lookup"><span data-stu-id="2a55c-157">Required?</span></span>                            | <span data-ttu-id="2a55c-158">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-158">false</span></span>                                |
| <span data-ttu-id="2a55c-159">Pozice?</span><span class="sxs-lookup"><span data-stu-id="2a55c-159">Position?</span></span>                            | <span data-ttu-id="2a55c-160">S názvem</span><span class="sxs-lookup"><span data-stu-id="2a55c-160">named</span></span>                                |
| <span data-ttu-id="2a55c-161">Výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="2a55c-161">Default Value</span></span>                        | <span data-ttu-id="2a55c-162">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-162">false</span></span>                                |
| <span data-ttu-id="2a55c-163">Přijmout kanálový vstup?</span><span class="sxs-lookup"><span data-stu-id="2a55c-163">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2a55c-164">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-164">false</span></span>                                |
| <span data-ttu-id="2a55c-165">Přijímat zástupné znaky?</span><span class="sxs-lookup"><span data-stu-id="2a55c-165">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2a55c-166">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-166">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="2a55c-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="2a55c-167">-WhatIf</span></span>

<span data-ttu-id="2a55c-168">Zobrazuje, co by se stalo při spuštění rutiny.</span><span class="sxs-lookup"><span data-stu-id="2a55c-168">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="2a55c-169">Rutina není spuštěna.</span><span class="sxs-lookup"><span data-stu-id="2a55c-169">The cmdlet is not run.</span></span>

|||  
|-|-|
| <span data-ttu-id="2a55c-170">Povinné?</span><span class="sxs-lookup"><span data-stu-id="2a55c-170">Required?</span></span>                            | <span data-ttu-id="2a55c-171">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-171">false</span></span>                                |
| <span data-ttu-id="2a55c-172">Pozice?</span><span class="sxs-lookup"><span data-stu-id="2a55c-172">Position?</span></span>                            | <span data-ttu-id="2a55c-173">S názvem</span><span class="sxs-lookup"><span data-stu-id="2a55c-173">named</span></span>                                |
| <span data-ttu-id="2a55c-174">Výchozí hodnota</span><span class="sxs-lookup"><span data-stu-id="2a55c-174">Default Value</span></span>                        | <span data-ttu-id="2a55c-175">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-175">false</span></span>                                |
| <span data-ttu-id="2a55c-176">Přijmout kanálový vstup?</span><span class="sxs-lookup"><span data-stu-id="2a55c-176">Accept Pipeline Input?</span></span>               | <span data-ttu-id="2a55c-177">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-177">false</span></span>                                |
| <span data-ttu-id="2a55c-178">Přijímat zástupné znaky?</span><span class="sxs-lookup"><span data-stu-id="2a55c-178">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="2a55c-179">false</span><span class="sxs-lookup"><span data-stu-id="2a55c-179">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="2a55c-180">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="2a55c-180">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="2a55c-181">Tato rutina podporuje běžné parametry:-Verbose,-Debug, - ErrorAction, - ErrorVariable,-OutBuffer a - OutVariable.</span><span class="sxs-lookup"><span data-stu-id="2a55c-181">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="2a55c-182">Další informace najdete v tématu [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="2a55c-182">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="2a55c-183">VSTUPY</span><span class="sxs-lookup"><span data-stu-id="2a55c-183">INPUTS</span></span>

### <a name="int"></a><span data-ttu-id="2a55c-184">celá čísla\[\]</span><span class="sxs-lookup"><span data-stu-id="2a55c-184">int\[\]</span></span>

<span data-ttu-id="2a55c-185">Tato rutina přijímá pole celých čísel nebo pole objektů PswaAuthorizationRule.</span><span class="sxs-lookup"><span data-stu-id="2a55c-185">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

### <a name="pswaauthorizationrule"></a><span data-ttu-id="2a55c-186">PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="2a55c-186">PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="2a55c-187">Tato rutina přijímá pole celých čísel nebo pole objektů PswaAuthorizationRule.</span><span class="sxs-lookup"><span data-stu-id="2a55c-187">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="2a55c-188">VÝSTUPY</span><span class="sxs-lookup"><span data-stu-id="2a55c-188">OUTPUTS</span></span>

<span data-ttu-id="2a55c-189">Tato rutina neprodukuje žádný výstup.</span><span class="sxs-lookup"><span data-stu-id="2a55c-189">This cmdlet produces no output.</span></span>

## <a name="examples"></a><span data-ttu-id="2a55c-190">PŘÍKLADY</span><span class="sxs-lookup"><span data-stu-id="2a55c-190">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="2a55c-191">PŘÍKLAD 1</span><span class="sxs-lookup"><span data-stu-id="2a55c-191">EXAMPLE 1</span></span>

<span data-ttu-id="2a55c-192">V tomto příkladu odebere autorizační pravidlo s ID *2*.</span><span class="sxs-lookup"><span data-stu-id="2a55c-192">This example removes the authorization rule with an ID of *2*.</span></span>

```
Remove-PswaAuthorizationRule –Id 2
```

### <a name="example-2-example-2-subheading"></a><span data-ttu-id="2a55c-193">Příklad 2 {.subHeading #example-2}</span><span class="sxs-lookup"><span data-stu-id="2a55c-193">EXAMPLE 2 {#example-2 .subHeading}</span></span>

<span data-ttu-id="2a55c-194">Tento příklad odebere všechna autorizační pravidla a také vyžaduje potvrzení uživatelem.</span><span class="sxs-lookup"><span data-stu-id="2a55c-194">This example removes all authorization rules and also requires confirmation by the user.</span></span>

```
Get-PswaAuthorizationRule | Remove-PswaAuthorizationRule -Confirm
```

## <a name="related-topics"></a><span data-ttu-id="2a55c-195">Příbuzná témata</span><span class="sxs-lookup"><span data-stu-id="2a55c-195">Related topics</span></span>

- [<span data-ttu-id="2a55c-196">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2a55c-196">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="2a55c-197">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2a55c-197">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="2a55c-198">Rutiny Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="2a55c-198">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="2a55c-199">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="2a55c-199">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)