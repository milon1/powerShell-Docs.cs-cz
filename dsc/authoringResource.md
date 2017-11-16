---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC prostředí powershell, konfiguraci, instalační program"
title: "Sestavení vlastní Windows PowerShell Desired State Configuration prostředky"
ms.openlocfilehash: 75b494db4ee6e381491decb11d35b60105217a0f
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2017
---
# <a name="build-custom-windows-powershell-desired-state-configuration-resources"></a><span data-ttu-id="f55a1-103">Sestavení vlastní Windows PowerShell Desired State Configuration prostředky</span><span class="sxs-lookup"><span data-stu-id="f55a1-103">Build Custom Windows PowerShell Desired State Configuration Resources</span></span>

> <span data-ttu-id="f55a1-104">Platí pro: Prostředí Windows PowerShell 4.0, prostředí Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="f55a1-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="f55a1-105">Požadovaného stavu aplikace Windows PowerShell (DSC) má integrovanou prostředky, které můžete použít ke konfiguraci prostředí.</span><span class="sxs-lookup"><span data-stu-id="f55a1-105">Windows PowerShell Desired State Configuration (DSC) has built-in resources that you can use to configure your environment.</span></span> <span data-ttu-id="f55a1-106">(Další informace najdete v tématu [předdefinované Windows PowerShell požadovaného stavu konfigurace prostředků](builtInResource.md).) Toto téma obsahuje přehled vývoje prostředky a odkazy na témata s konkrétní informace a příklady.</span><span class="sxs-lookup"><span data-stu-id="f55a1-106">(For more information, see [Built-In Windows PowerShell Desired State Configuration Resources](builtInResource.md).) This topic provides an overview of developing resources and links to topics with specific information and examples.</span></span>

## <a name="dsc-resource-components"></a><span data-ttu-id="f55a1-107">Součásti prostředků DSC</span><span class="sxs-lookup"><span data-stu-id="f55a1-107">DSC resource components</span></span>

<span data-ttu-id="f55a1-108">Prostředek DSC je modul prostředí Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f55a1-108">A DSC resource is a Windows PowerShell module.</span></span> <span data-ttu-id="f55a1-109">Tento modul obsahuje schéma (definice konfigurovatelné vlastnosti) a implementace (kód, který ve skutečnosti zajišťuje zpracování zadané konfigurace) pro daný prostředek.</span><span class="sxs-lookup"><span data-stu-id="f55a1-109">The module contains both the schema (the definition of the configurable properties) and the implementation (the code that does the actual work specified by a configuration) for the resource.</span></span> <span data-ttu-id="f55a1-110">Schéma prostředků DSC lze definovat v souboru MOF a implementaci se provádí pomocí modulu skriptu.</span><span class="sxs-lookup"><span data-stu-id="f55a1-110">A DSC resource schema can be defined in a MOF file, and the implementation is performed by a script module.</span></span> <span data-ttu-id="f55a1-111">Počínaje podpory prostředí PowerShell tříd v verze 5, schéma a implementace obě určeny v třídě.</span><span class="sxs-lookup"><span data-stu-id="f55a1-111">Beginning with the support of PowerShell classes in version 5, the schema and implementation can both be defined in a class.</span></span> <span data-ttu-id="f55a1-112">Následující témata popisují postup vytvoření prostředky DSC podrobněji.</span><span class="sxs-lookup"><span data-stu-id="f55a1-112">The following topics describe in more detail how to create DSC resources.</span></span>

* [<span data-ttu-id="f55a1-113">Psaní vlastních prostředků DSC s MOF</span><span class="sxs-lookup"><span data-stu-id="f55a1-113">Writing a custom DSC resource with MOF</span></span>](authoringResourceMOF.md) 
* [<span data-ttu-id="f55a1-114">Implementace prostředek DSC v jazyce C#</span><span class="sxs-lookup"><span data-stu-id="f55a1-114">Implementing a DSC resource in C#</span></span>](authoringResourceMofCS.md) 
* [<span data-ttu-id="f55a1-115">Psaní vlastních prostředků DSC s třídami, prostředí PowerShell</span><span class="sxs-lookup"><span data-stu-id="f55a1-115">Writing a custom DSC resource with PowerShell classes</span></span>](authoringResourceClass.md) 
* [<span data-ttu-id="f55a1-116">Složené prostředky: použití konfigurace DSC jako prostředek</span><span class="sxs-lookup"><span data-stu-id="f55a1-116">Composite resources: Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md) 
* [<span data-ttu-id="f55a1-117">V nástroji Návrhář prostředků</span><span class="sxs-lookup"><span data-stu-id="f55a1-117">Using the Resource Designer tool</span></span>](authoringResourceMofDesigner.md) 
