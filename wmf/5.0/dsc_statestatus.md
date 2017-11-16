---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, prostředí powershell, instalační program"
ms.openlocfilehash: 32f8e20889ddc526def4b925e8d0761a2e851e19
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="unified-and-consistent-state-and-status-representation"></a><span data-ttu-id="eb9ac-102">Jednotné a konzistentní stav a stav reprezentace</span><span class="sxs-lookup"><span data-stu-id="eb9ac-102">Unified and Consistent State and Status Representation</span></span>

<span data-ttu-id="eb9ac-103">Řadu vylepšení byly provedeny v této verzi pro automatizaci vytvořené LCM stav a stav DSC.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-103">A series of enhancements have been made in this release for automations built LCM state and DSC status.</span></span> <span data-ttu-id="eb9ac-104">Patří mezi ně jednotné a konzistentní stav a stav vyjádření, vlastnost datetime spravovatelných objektů stav vrácen rutinou Get-DscConfigurationStatus a rozšířené vlastnosti podrobností LCM stav vrácený Get-DscLocalConfigurationManager rutiny.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-104">These include unified and consistent state and status representations, manageable datetime property of status objects returned by Get-DscConfigurationStatus cmdlet and enhanced LCM state details property returned by Get-DscLocalConfigurationManager cmdlet.</span></span>

<span data-ttu-id="eb9ac-105">Reprezentace LCM stav a stav operace DSC jsou kdykoli znovu spustit a jednotná podle následujících pravidel:</span><span class="sxs-lookup"><span data-stu-id="eb9ac-105">The representation of LCM state and DSC operation status are revisited and unified according to following rules:</span></span>
1.  <span data-ttu-id="eb9ac-106">Notprocessed prostředků neovlivní LCM stav a stav DSC.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-106">Notprocessed resource does not impact LCM state and DSC status.</span></span>
2.  <span data-ttu-id="eb9ac-107">LCM zastavit zpracování další prostředky, jakmile narazí na prostředek, který požaduje restartování.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-107">LCM stop processing further resources once it encounters a resource that requests reboot.</span></span>
3.  <span data-ttu-id="eb9ac-108">Na prostředek, který požaduje restartování není v požadovaném stavu, dokud se ve skutečnosti stane restartování.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-108">A resource that requests reboot is not in desired state until reboot actually happens.</span></span>
4.  <span data-ttu-id="eb9ac-109">Po zjištění na prostředek, který selže, LCM uchová zpracování další prostředky, dokud nejsou závislé na jednu selhání.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-109">After encountering a resource that fails, LCM keeps processing further resources as long as they are not dependent on the failure one.</span></span>
5.  <span data-ttu-id="eb9ac-110">Celkový stav, který vrátila Rutina Get-DscConfigurationStatus je supertřídou sada stavu všech prostředků.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-110">The overall status returned by Get-DscConfigurationStatus cmdlet is the super set of all resources’ status.</span></span>
6.  <span data-ttu-id="eb9ac-111">Stav PendingReboot je nadmnožinou PendingConfiguration stavu.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-111">The PendingReboot state is a superset of PendingConfiguration state.</span></span>

<span data-ttu-id="eb9ac-112">Následující tabulka znázorňuje výsledné stav a stav souvisejících vlastností v rámci několik typické scénáře.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-112">The table below illustrates the resultant state and status related properties under a few typical scenarios.</span></span>

| <span data-ttu-id="eb9ac-113">**Scénář**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-113">**Scenario**</span></span>                    | <span data-ttu-id="eb9ac-114">**LCMState\***</span><span class="sxs-lookup"><span data-stu-id="eb9ac-114">**LCMState\***</span></span>       | <span data-ttu-id="eb9ac-115">**Stav**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-115">**Status**</span></span> | <span data-ttu-id="eb9ac-116">**Požadovaný restart**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-116">**Reboot Requested**</span></span>  | <span data-ttu-id="eb9ac-117">**ResourcesInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-117">**ResourcesInDesiredState**</span></span>  | <span data-ttu-id="eb9ac-118">**ResourcesNotInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-118">**ResourcesNotInDesiredState**</span></span> |
|---------------------------------|----------------------|------------|---------------|------------------------------|--------------------------------|
| <span data-ttu-id="eb9ac-119">S**^**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-119">S**^**</span></span>                          | <span data-ttu-id="eb9ac-120">Nečinnosti</span><span class="sxs-lookup"><span data-stu-id="eb9ac-120">Idle</span></span>                 | <span data-ttu-id="eb9ac-121">Úspěch</span><span class="sxs-lookup"><span data-stu-id="eb9ac-121">Success</span></span>    | <span data-ttu-id="eb9ac-122">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-122">$false</span></span>        | <span data-ttu-id="eb9ac-123">S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-123">S</span></span>                            | <span data-ttu-id="eb9ac-124">$null</span><span class="sxs-lookup"><span data-stu-id="eb9ac-124">$null</span></span>                          |
| <span data-ttu-id="eb9ac-125">F**^**</span><span class="sxs-lookup"><span data-stu-id="eb9ac-125">F**^**</span></span>                          | <span data-ttu-id="eb9ac-126">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9ac-126">PendingConfiguration</span></span> | <span data-ttu-id="eb9ac-127">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-127">Failure</span></span>    | <span data-ttu-id="eb9ac-128">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-128">$false</span></span>        | <span data-ttu-id="eb9ac-129">$null</span><span class="sxs-lookup"><span data-stu-id="eb9ac-129">$null</span></span>                        | <span data-ttu-id="eb9ac-130">F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-130">F</span></span>                              |
| <span data-ttu-id="eb9ac-131">S, F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-131">S,F</span></span>                             | <span data-ttu-id="eb9ac-132">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9ac-132">PendingConfiguration</span></span> | <span data-ttu-id="eb9ac-133">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-133">Failure</span></span>    | <span data-ttu-id="eb9ac-134">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-134">$false</span></span>        | <span data-ttu-id="eb9ac-135">S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-135">S</span></span>                            | <span data-ttu-id="eb9ac-136">F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-136">F</span></span>                              |
| <span data-ttu-id="eb9ac-137">F, S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-137">F,S</span></span>                             | <span data-ttu-id="eb9ac-138">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9ac-138">PendingConfiguration</span></span> | <span data-ttu-id="eb9ac-139">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-139">Failure</span></span>    | <span data-ttu-id="eb9ac-140">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-140">$false</span></span>        | <span data-ttu-id="eb9ac-141">S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-141">S</span></span>                            | <span data-ttu-id="eb9ac-142">F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-142">F</span></span>                              |
| <span data-ttu-id="eb9ac-143">S<sub>1</sub>, F, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="eb9ac-143">S<sub>1</sub>, F, S<sub>2</sub></span></span> | <span data-ttu-id="eb9ac-144">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9ac-144">PendingConfiguration</span></span> | <span data-ttu-id="eb9ac-145">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-145">Failure</span></span>    | <span data-ttu-id="eb9ac-146">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-146">$false</span></span>        | <span data-ttu-id="eb9ac-147">S<sub>1</sub>, S<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="eb9ac-147">S<sub>1</sub>, S<sub>2</sub></span></span> | <span data-ttu-id="eb9ac-148">F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-148">F</span></span>                              |
| <span data-ttu-id="eb9ac-149">F<sub>1</sub>, S, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="eb9ac-149">F<sub>1</sub>, S, F<sub>2</sub></span></span> | <span data-ttu-id="eb9ac-150">PendingConfiguration</span><span class="sxs-lookup"><span data-stu-id="eb9ac-150">PendingConfiguration</span></span> | <span data-ttu-id="eb9ac-151">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-151">Failure</span></span>    | <span data-ttu-id="eb9ac-152">$false</span><span class="sxs-lookup"><span data-stu-id="eb9ac-152">$false</span></span>        | <span data-ttu-id="eb9ac-153">S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-153">S</span></span>                            | <span data-ttu-id="eb9ac-154">F<sub>1</sub>, F<sub>2</sub></span><span class="sxs-lookup"><span data-stu-id="eb9ac-154">F<sub>1</sub>, F<sub>2</sub></span></span>   |
| <span data-ttu-id="eb9ac-155">S, r</span><span class="sxs-lookup"><span data-stu-id="eb9ac-155">S, r</span></span>                            | <span data-ttu-id="eb9ac-156">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="eb9ac-156">PendingReboot</span></span>        | <span data-ttu-id="eb9ac-157">Úspěch</span><span class="sxs-lookup"><span data-stu-id="eb9ac-157">Success</span></span>    | <span data-ttu-id="eb9ac-158">$true</span><span class="sxs-lookup"><span data-stu-id="eb9ac-158">$true</span></span>         | <span data-ttu-id="eb9ac-159">S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-159">S</span></span>                            | <span data-ttu-id="eb9ac-160">R</span><span class="sxs-lookup"><span data-stu-id="eb9ac-160">r</span></span>                              |
| <span data-ttu-id="eb9ac-161">F, r</span><span class="sxs-lookup"><span data-stu-id="eb9ac-161">F, r</span></span>                            | <span data-ttu-id="eb9ac-162">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="eb9ac-162">PendingReboot</span></span>        | <span data-ttu-id="eb9ac-163">Chyba</span><span class="sxs-lookup"><span data-stu-id="eb9ac-163">Failure</span></span>    | <span data-ttu-id="eb9ac-164">$true</span><span class="sxs-lookup"><span data-stu-id="eb9ac-164">$true</span></span>         | <span data-ttu-id="eb9ac-165">$null</span><span class="sxs-lookup"><span data-stu-id="eb9ac-165">$null</span></span>                        | <span data-ttu-id="eb9ac-166">F, r</span><span class="sxs-lookup"><span data-stu-id="eb9ac-166">F, r</span></span>                           |
| <span data-ttu-id="eb9ac-167">r, S</span><span class="sxs-lookup"><span data-stu-id="eb9ac-167">r, S</span></span>                            | <span data-ttu-id="eb9ac-168">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="eb9ac-168">PendingReboot</span></span>        | <span data-ttu-id="eb9ac-169">Úspěch</span><span class="sxs-lookup"><span data-stu-id="eb9ac-169">Success</span></span>    | <span data-ttu-id="eb9ac-170">$true</span><span class="sxs-lookup"><span data-stu-id="eb9ac-170">$true</span></span>         | <span data-ttu-id="eb9ac-171">$null</span><span class="sxs-lookup"><span data-stu-id="eb9ac-171">$null</span></span>                        | <span data-ttu-id="eb9ac-172">R</span><span class="sxs-lookup"><span data-stu-id="eb9ac-172">r</span></span>                              |
| <span data-ttu-id="eb9ac-173">r, F</span><span class="sxs-lookup"><span data-stu-id="eb9ac-173">r, F</span></span>                            | <span data-ttu-id="eb9ac-174">PendingReboot</span><span class="sxs-lookup"><span data-stu-id="eb9ac-174">PendingReboot</span></span>        | <span data-ttu-id="eb9ac-175">Úspěch</span><span class="sxs-lookup"><span data-stu-id="eb9ac-175">Success</span></span>    | <span data-ttu-id="eb9ac-176">$true</span><span class="sxs-lookup"><span data-stu-id="eb9ac-176">$true</span></span>         | <span data-ttu-id="eb9ac-177">$null</span><span class="sxs-lookup"><span data-stu-id="eb9ac-177">$null</span></span>                        | <span data-ttu-id="eb9ac-178">R</span><span class="sxs-lookup"><span data-stu-id="eb9ac-178">r</span></span>                              |

<span data-ttu-id="eb9ac-179">^ S<sub>i</sub>: řadu prostředky, které bylo úspěšně použito F<sub>i</sub>: řadu prostředky, které použije neúspěšně r: A prostředků, které vyžadují restartování:\*</span><span class="sxs-lookup"><span data-stu-id="eb9ac-179">^ S<sub>i</sub>: A series of resources that applied successfully F<sub>i</sub>: A series of resources that applied unsuccessfully r: A resource that requires reboot \*</span></span>

```powershell
$LCMState = (Get-DscLocalConfigurationManager).LCMState
$Status = (Get-DscConfigurationStatus).Status

$RebootRequested = (Get-DscConfigurationStatus).RebootRequested

$ResourcesInDesiredState = (Get-DscConfigurationStatus).ResourcesInDesiredState

$ResourcesNotInDesiredState = (Get-DscConfigurationStatus).ResourcesNotInDesiredState
```
## <a name="enhancement-in-get-dscconfigurationstatus-cmdlet"></a><span data-ttu-id="eb9ac-180">Vylepšení v rutině Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="eb9ac-180">Enhancement in Get-DscConfigurationStatus cmdlet</span></span>

<span data-ttu-id="eb9ac-181">Rutina Get-DscConfigurationStatus v této verzi se provedly několik vylepšení.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-181">A few enhancements have been made to Get-DscConfigurationStatus cmdlet in this release.</span></span> <span data-ttu-id="eb9ac-182">Vlastnost počátečním objektů vrácený rutinu dříve, je typu String.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-182">Previously, the StartDate property of objects returned by the cmdlet is of String type.</span></span> <span data-ttu-id="eb9ac-183">Nyní je typu datum a čas, který umožňuje komplexní, výběru a filtrování snadnější podle vnitřní vlastnosti objektu data a času.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-183">Now, it is of Datetime type, which enables complex selecting and filtering easier based on the intrinsic properties of a Datetime object.</span></span>
```powershell
(Get-DscConfigurationStatus).StartDate | fl \*
DateTime : Friday, November 13, 2015 1:39:44 PM
Date : 11/13/2015 12:00:00 AM
Day : 13
DayOfWeek : Friday
DayOfYear : 317
Hour : 13
Kind : Local
Millisecond : 886
Minute : 39
Month : 11
Second : 44
Ticks : 635830187848860000
TimeOfDay : 13:39:44.8860000
Year : 2015
```

<span data-ttu-id="eb9ac-184">Následuje příklad, který vrátí že všechny záznamy operaci DSC došlo ve stejný den v týdnu jako dnes.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-184">Following is an example that returns all DSC operation records happened on the same day of week as today.</span></span>
```powershell
(Get-DscConfigurationStatus –All) | where { $\_.startdate.dayofweek -eq (Get-Date).DayOfWeek }
```

<span data-ttu-id="eb9ac-185">Tím se vyloučí záznamy operací, které nebyly provedeny změny konfigurace uzlu (tj. pouze operace čtení).</span><span class="sxs-lookup"><span data-stu-id="eb9ac-185">Records of operations that do not make changes to node’s configuration (i.e. read only operations) are eliminated.</span></span> <span data-ttu-id="eb9ac-186">Proto Test-DscConfiguration operace Get-DscConfiguration jsou již zfalšované v nevrátil z rutiny Get-DscConfigurationStatus objekty.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-186">Therefore, Test-DscConfiguration, Get-DscConfiguration operations are no longer adulterated in returned objects from Get-DscConfigurationStatus cmdlet.</span></span>
<span data-ttu-id="eb9ac-187">Zaznamenává meta operace nastavení konfigurace se přidá k návratu rutiny Get-DscConfigurationStatus.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-187">Records of meta configuration setting operation is added to the return of Get-DscConfigurationStatus cmdlet.</span></span>

<span data-ttu-id="eb9ac-188">Tady je příklad výsledku vrácený z Get-DscConfigurationStatus – všechny rutiny.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-188">Following is an example of result returned from Get-DscConfigurationStatus –All cmdlet.</span></span>
```powershell
All configuration operations:

Status StartDate Type RebootRequested
------ --------- ---- ---------------
Success 11/13/2015 11:38:16 AM Consistency False
Success 11/13/2015 11:23:16 AM Reboot False
Success 11/13/2015 11:21:43 AM Reboot True
Success 11/13/2015 11:20:44 AM Initial True
Success 11/13/2015 11:20:44 AM LocalConfigurationManager False
```

## <a name="enhancement-in-get-dsclocalconfigurationmanager-cmdlet"></a><span data-ttu-id="eb9ac-189">Vylepšení v rutině Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="eb9ac-189">Enhancement in Get-DscLocalConfigurationManager cmdlet</span></span>
<span data-ttu-id="eb9ac-190">Nové pole LCMStateDetail se přidá do objekt vrácený z rutiny Get-DscLocalConfigurationManager.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-190">A new field of LCMStateDetail is added to the object returned from Get-DscLocalConfigurationManager cmdlet.</span></span> <span data-ttu-id="eb9ac-191">V tomto poli se zaplní při LCMState je "Zaneprázdněn".</span><span class="sxs-lookup"><span data-stu-id="eb9ac-191">This field is populated when LCMState is “Busy”.</span></span> <span data-ttu-id="eb9ac-192">Se dá načíst pomocí následující rutiny:</span><span class="sxs-lookup"><span data-stu-id="eb9ac-192">It can be retrieved by following cmdlet:</span></span>
```powershell
(Get-DscLocalConfigurationManager).LCMStateDetail
```

<span data-ttu-id="eb9ac-193">Následuje příklad výstupu nepřetržitého monitorování v konfiguraci, která vyžaduje dvě restartování na vzdáleném uzlu.</span><span class="sxs-lookup"><span data-stu-id="eb9ac-193">Following is an example output of a continuous monitoring on a configuration that requires two reboots on a remote node.</span></span>
```powershell
Start a configuration that requires two reboots

Monitor LCM State:
LCM State: Busy, LCM is applying a new configuration.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: PendingReboot,
Machine is rebooting...
LCM State: Busy, LCM is continuing applying configuration after last reboot.
LCM State: Idle,
LCM State: Busy, LCM is performing a consistency check.
LCM State: Idle,
```
