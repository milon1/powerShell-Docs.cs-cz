---
ms.date: 06/12/2017
keywords: DSC, powershell, konfigurace, instalační program
title: Metoda SendConfigurationApply třídy MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: da3a08307122ab38ee4a6fd5d4a9b97579a988f7
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403629"
---
# <a name="sendconfigurationapply-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="bad57-103">Metoda SendConfigurationApply třídy MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="bad57-103">SendConfigurationApply method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="bad57-104">Odešle dokument konfigurace spravovaných uzlů a použít danou konfiguraci pomocí konfigurace agenta.</span><span class="sxs-lookup"><span data-stu-id="bad57-104">Sends the configuration document to the managed node and uses the Configuration Agent to apply the configuration.</span></span>

## <a name="syntax"></a><span data-ttu-id="bad57-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="bad57-105">Syntax</span></span>

```mof
uint32 SendConfigurationApply(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="bad57-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="bad57-106">Parameters</span></span>

<span data-ttu-id="bad57-107">*ConfigurationData* \[v\] dat prostředí pro konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="bad57-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="bad57-108">*Vynutit* \[v\] **true** vynutit konfiguraci tak, aby zastavit.</span><span class="sxs-lookup"><span data-stu-id="bad57-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="bad57-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="bad57-109">Return value</span></span>

<span data-ttu-id="bad57-110">Vrátí nulu v případě úspěchu; v opačném případě vrátí kód chyby.</span><span class="sxs-lookup"><span data-stu-id="bad57-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="bad57-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="bad57-111">Remarks</span></span>

<span data-ttu-id="bad57-112">Toto je statické metody.</span><span class="sxs-lookup"><span data-stu-id="bad57-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="bad57-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="bad57-113">Requirements</span></span>

<span data-ttu-id="bad57-114">**SOUBOR MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="bad57-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="bad57-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="bad57-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="bad57-116">Viz taky</span><span class="sxs-lookup"><span data-stu-id="bad57-116">See also</span></span>

[<span data-ttu-id="bad57-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="bad57-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)