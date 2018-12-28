---
ms.date: 06/12/2017
keywords: DSC, powershell, konfigurace, instalační program
title: Metoda SendConfiguration třídy MSFT_DSCLocalConfigurationManager
ms.openlocfilehash: 3529bc56ecba19ed0fbbf070a4e86d0692824d39
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403625"
---
# <a name="sendconfiguration-method-of-the-msftdsclocalconfigurationmanager-class"></a><span data-ttu-id="ea84e-103">Metoda SendConfiguration třídy MSFT_DSCLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="ea84e-103">SendConfiguration method of the MSFT_DSCLocalConfigurationManager class</span></span>

<span data-ttu-id="ea84e-104">Odešle dokument konfigurace spravovaných uzlů a uloží ho jako nedokončená změna.</span><span class="sxs-lookup"><span data-stu-id="ea84e-104">Sends the configuration document to the managed node and saves it as a pending change.</span></span>

## <a name="syntax"></a><span data-ttu-id="ea84e-105">Syntaxe</span><span class="sxs-lookup"><span data-stu-id="ea84e-105">Syntax</span></span>

```mof
uint32 SendConfiguration(
  [in] uint8   ConfigurationData[],
  [in] boolean force
);
```

## <a name="parameters"></a><span data-ttu-id="ea84e-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="ea84e-106">Parameters</span></span>

<span data-ttu-id="ea84e-107">*ConfigurationData* \[v\] dat prostředí pro konfiguraci.</span><span class="sxs-lookup"><span data-stu-id="ea84e-107">*ConfigurationData* \[in\] The environment data for the configuration.</span></span>

<span data-ttu-id="ea84e-108">*Vynutit* \[v\] **true** vynutit konfiguraci tak, aby zastavit.</span><span class="sxs-lookup"><span data-stu-id="ea84e-108">*force* \[in\] **true** to force the configuration to stop.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea84e-109">Návratová hodnota</span><span class="sxs-lookup"><span data-stu-id="ea84e-109">Return value</span></span>

<span data-ttu-id="ea84e-110">Vrátí nulu v případě úspěchu; v opačném případě vrátí kód chyby.</span><span class="sxs-lookup"><span data-stu-id="ea84e-110">Returns zero on success; otherwise returns an error code.</span></span>

## <a name="remarks"></a><span data-ttu-id="ea84e-111">Poznámky</span><span class="sxs-lookup"><span data-stu-id="ea84e-111">Remarks</span></span>

<span data-ttu-id="ea84e-112">Toto je statické metody.</span><span class="sxs-lookup"><span data-stu-id="ea84e-112">This is a static method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea84e-113">Požadavky</span><span class="sxs-lookup"><span data-stu-id="ea84e-113">Requirements</span></span>

<span data-ttu-id="ea84e-114">**SOUBOR MOF:** DscCore.mof</span><span class="sxs-lookup"><span data-stu-id="ea84e-114">**MOF:** DscCore.mof</span></span>

<span data-ttu-id="ea84e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea84e-115">**Namespace**: Root\Microsoft\Windows\DesiredStateConfiguration</span></span>

## <a name="see-also"></a><span data-ttu-id="ea84e-116">Viz taky</span><span class="sxs-lookup"><span data-stu-id="ea84e-116">See also</span></span>

[<span data-ttu-id="ea84e-117">**MSFT_DSCLocalConfigurationManager**</span><span class="sxs-lookup"><span data-stu-id="ea84e-117">**MSFT_DSCLocalConfigurationManager**</span></span>](msft-dsclocalconfigurationmanager.md)