---
ms.date: 06/12/2017
keywords: DSC, powershell, konfigurace, instalační program
title: Třída MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 7f6aaf209601e99b0120407eb301d32fcfda9eb8
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403817"
---
# <a name="msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="74dcd-103">Třída MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="74dcd-103">MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="74dcd-104">Místní Configuration Manageru (LCM), který řídí stavy konfigurační soubory a používá konfiguraci agenta použít konfigurace.</span><span class="sxs-lookup"><span data-stu-id="74dcd-104">The Local Configuration Manager (LCM) that controls the states of configuration files and uses Configuration Agent to apply the configurations.</span></span>

<span data-ttu-id="74dcd-105">Následující syntaxe je zjednodušená z kódu formátu MOF (Managed Object) a zahrnuje všechny zděděné vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="74dcd-105">The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.</span></span>

## <a name="syntax"></a><span data-ttu-id="74dcd-106">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="74dcd-106">Syntax</span></span>

```
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## <a name="members"></a><span data-ttu-id="74dcd-107">Členové</span><span class="sxs-lookup"><span data-stu-id="74dcd-107">Members</span></span>

<span data-ttu-id="74dcd-108">**MSFT_DSCLocalConfigurationManager** třída má následující členy:</span><span class="sxs-lookup"><span data-stu-id="74dcd-108">The **MSFT_DSCLocalConfigurationManager** class has the following members:</span></span>

- <span data-ttu-id="74dcd-109">[Metody] []</span><span class="sxs-lookup"><span data-stu-id="74dcd-109">[Methods][]</span></span>

### <a name="methods"></a><span data-ttu-id="74dcd-110">Metody</span><span class="sxs-lookup"><span data-stu-id="74dcd-110">Methods</span></span>

<span data-ttu-id="74dcd-111">**MSFT_DSCLocalConfigurationManager** třída má tyto metody.</span><span class="sxs-lookup"><span data-stu-id="74dcd-111">The **MSFT_DSCLocalConfigurationManager** class has these methods.</span></span>

|<span data-ttu-id="74dcd-112">Metoda</span><span class="sxs-lookup"><span data-stu-id="74dcd-112">Method</span></span> |<span data-ttu-id="74dcd-113">Popis</span><span class="sxs-lookup"><span data-stu-id="74dcd-113">Description</span></span> |
|:--- |:---|
| [<span data-ttu-id="74dcd-114">Třída ApplyConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-114">ApplyConfiguration</span></span>](msft-dsclocalconfigurationmanager-applyconfiguration.md)| <span data-ttu-id="74dcd-115">Pomocí agenta konfigurace použije konfiguraci, která čeká na vyřízení.</span><span class="sxs-lookup"><span data-stu-id="74dcd-115">Uses the Configuration Agent to apply the configuration that is pending.</span></span>|
| [<span data-ttu-id="74dcd-116">DisableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-116">DisableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| <span data-ttu-id="74dcd-117">Zakáže ladění prostředků DSC.</span><span class="sxs-lookup"><span data-stu-id="74dcd-117">Disables DSC resource debugging.</span></span>|
| [<span data-ttu-id="74dcd-118">EnableDebugConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-118">EnableDebugConfiguration</span></span>](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| <span data-ttu-id="74dcd-119">Povolí ladění prostředků DSC.</span><span class="sxs-lookup"><span data-stu-id="74dcd-119">Enables DSC resource debugging.</span></span>|
| [<span data-ttu-id="74dcd-120">GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-120">GetConfiguration</span></span>](msft-dsclocalconfigurationmanager-getconfiguration.md)| <span data-ttu-id="74dcd-121">Odešle dokument konfigurace spravovaných uzlů a používá **získat** metody konfigurace agenta použít danou konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="74dcd-121">Sends the configuration document to the managed node and uses the **Get** method of the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="74dcd-122">GetConfigurationResultOutput</span><span class="sxs-lookup"><span data-stu-id="74dcd-122">GetConfigurationResultOutput</span></span>](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| <span data-ttu-id="74dcd-123">Získá výstup agenta konfigurace týkající se určité úlohy.</span><span class="sxs-lookup"><span data-stu-id="74dcd-123">Gets the Configuration Agent output relating to a specific job.</span></span>|
| [<span data-ttu-id="74dcd-124">GetConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="74dcd-124">GetConfigurationStatus</span></span>](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| <span data-ttu-id="74dcd-125">Zobrazit historii stavu konfigurace.</span><span class="sxs-lookup"><span data-stu-id="74dcd-125">Get the configuration status history.</span></span>|
| [<span data-ttu-id="74dcd-126">GetMetaConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-126">GetMetaConfiguration</span></span>](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| <span data-ttu-id="74dcd-127">Získá LCM nastavení, které se používají k řízení konfigurace agenta.</span><span class="sxs-lookup"><span data-stu-id="74dcd-127">Gets the LCM settings that are used to control Configuration Agent.</span></span>|
| [<span data-ttu-id="74dcd-128">PerformRequiredConfigurationChecks</span><span class="sxs-lookup"><span data-stu-id="74dcd-128">PerformRequiredConfigurationChecks</span></span>](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| <span data-ttu-id="74dcd-129">Spustí kontrolu konzistence.</span><span class="sxs-lookup"><span data-stu-id="74dcd-129">Starts the consistency check.</span></span>|
| [<span data-ttu-id="74dcd-130">RemoveConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-130">RemoveConfiguration</span></span>](msft-dsclocalconfigurationmanager-removeconfiguration.md)| <span data-ttu-id="74dcd-131">Odstraní konfigurační soubory.</span><span class="sxs-lookup"><span data-stu-id="74dcd-131">Removes the configuration files.</span></span>|
| [<span data-ttu-id="74dcd-132">ResourceGet</span><span class="sxs-lookup"><span data-stu-id="74dcd-132">ResourceGet</span></span>](msft-dsclocalconfigurationmanager-resourceget.md)| <span data-ttu-id="74dcd-133">Volá přímo **získat** metoda prostředek DSC.</span><span class="sxs-lookup"><span data-stu-id="74dcd-133">Directly calls the **Get** method of a DSC resource.</span></span>|
| [<span data-ttu-id="74dcd-134">ResourceSet</span><span class="sxs-lookup"><span data-stu-id="74dcd-134">ResourceSet</span></span>](msft-dsclocalconfigurationmanager-resourceset.md)| <span data-ttu-id="74dcd-135">Volá přímo **nastavit** metoda prostředek DSC.</span><span class="sxs-lookup"><span data-stu-id="74dcd-135">Directly calls the **Set** method of a DSC resource.</span></span>|
| [<span data-ttu-id="74dcd-136">ResourceTest</span><span class="sxs-lookup"><span data-stu-id="74dcd-136">ResourceTest</span></span>](msft-dsclocalconfigurationmanager-resourcetest.md)| <span data-ttu-id="74dcd-137">Volá přímo **Test** metoda prostředek DSC.</span><span class="sxs-lookup"><span data-stu-id="74dcd-137">Directly calls the **Test** method of a DSC resource.</span></span>|
| [<span data-ttu-id="74dcd-138">Vrácení zpět</span><span class="sxs-lookup"><span data-stu-id="74dcd-138">RollBack</span></span>](msft-dsclocalconfigurationmanager-rollback.md)| <span data-ttu-id="74dcd-139">Zobrazí souhrn po zpět předchozí konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="74dcd-139">Rolls back to a previous configuration.</span></span>|
| [<span data-ttu-id="74dcd-140">SendConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-140">SendConfiguration</span></span>](msft-dsclocalconfigurationmanager-sendconfiguration.md)| <span data-ttu-id="74dcd-141">Odešle dokument konfigurace spravovaných uzlů a uloží ho jako nedokončená změna.</span><span class="sxs-lookup"><span data-stu-id="74dcd-141">Sends the configuration document to the managed node and saves it as a pending change.</span></span>|
| [<span data-ttu-id="74dcd-142">SendConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="74dcd-142">SendConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| <span data-ttu-id="74dcd-143">Odešle dokument konfigurace spravovaných uzlů a použít danou konfiguraci pomocí konfigurace agenta.</span><span class="sxs-lookup"><span data-stu-id="74dcd-143">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>|
| [<span data-ttu-id="74dcd-144">SendConfigurationApplyAsync</span><span class="sxs-lookup"><span data-stu-id="74dcd-144">SendConfigurationApplyAsync</span></span>](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| <span data-ttu-id="74dcd-145">Poslat dokument konfigurace spravovaných uzlů a začnete používat konfigurace agenta pro použití konfigurace.</span><span class="sxs-lookup"><span data-stu-id="74dcd-145">Send the configuration document to the managed node and start using the Configuration Agent to apply the configuration.</span></span> <span data-ttu-id="74dcd-146">Použijte GetConfigurationResultOutput k načtení výsledků výstupu.</span><span class="sxs-lookup"><span data-stu-id="74dcd-146">Use GetConfigurationResultOutput to retrieve result output.</span></span>|
| [<span data-ttu-id="74dcd-147">SendMetaConfigurationApply</span><span class="sxs-lookup"><span data-stu-id="74dcd-147">SendMetaConfigurationApply</span></span>](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| <span data-ttu-id="74dcd-148">Nastaví LCM nastavení, které se používají k řízení konfigurace agenta.</span><span class="sxs-lookup"><span data-stu-id="74dcd-148">Sets the LCM settings that are used to control the Configuration Agent.</span></span>|
| [<span data-ttu-id="74dcd-149">StopConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-149">StopConfiguration</span></span>](msft-dsclocalconfigurationmanager-stopconfiguration.md)| <span data-ttu-id="74dcd-150">Zastaví probíhající konfigurace.</span><span class="sxs-lookup"><span data-stu-id="74dcd-150">Stops the configuration that is in progress.</span></span>|
| [<span data-ttu-id="74dcd-151">TestConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-151">TestConfiguration</span></span>](msft-dsclocalconfigurationmanager-testconfiguration.md)| <span data-ttu-id="74dcd-152">Odešle dokument konfigurace spravovaných uzlů a ověří aktuální konfiguraci proti dokumentu.</span><span class="sxs-lookup"><span data-stu-id="74dcd-152">Sends the configuration document to the managed node and verifies the current configuration against the document.</span></span>|

## <a name="requirements"></a><span data-ttu-id="74dcd-153">Požadavky</span><span class="sxs-lookup"><span data-stu-id="74dcd-153">Requirements</span></span>

<span data-ttu-id="74dcd-154">**SOUBOR MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="74dcd-154">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="74dcd-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="74dcd-155">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>