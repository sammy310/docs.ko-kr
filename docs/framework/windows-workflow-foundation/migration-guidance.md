---
title: 마이그레이션 지침
ms.date: 03/30/2017
ms.assetid: cb65c132-58c9-4028-b3d4-1efc71d5e60e
ms.openlocfilehash: 16f725dcb5d6f6e5d06771b7836fa187be005910
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559202"
---
# <a name="migration-guidance"></a><span data-ttu-id="e4100-102">마이그레이션 지침</span><span class="sxs-lookup"><span data-stu-id="e4100-102">Migration Guidance</span></span>

<span data-ttu-id="e4100-103">.NET Framework 4에서 Microsoft는 두 번째 주요 버전의 WF (Windows Workflow Foundation)를 출시 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-103">In the .NET Framework 4, Microsoft is releasing the second major version of Windows Workflow Foundation (WF).</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="e4100-104">은 (는) WinFX에서 릴리스 되었으며 ( \* WF3 라고 함), 3.5 .NET Framework에서 향상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-104">was released in WinFX (this included the types in the System.Workflow.\* namespaces; now referred to as WF3) and enhanced in .NET Framework 3.5.</span></span> <span data-ttu-id="e4100-105">WF3는 .NET Framework 4의 일부 이기도 하지만 새 워크플로 기술 (W F 4의 형식 \* , 이라고 함)과 함께 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-105">WF3 is also part of the .NET Framework 4, but it exists there alongside new workflow technology (the types in the System.Activities.\* namespaces; referred to as WF4).</span></span> <span data-ttu-id="e4100-106">WF4 사용을 고려하는 경우 타이밍을 제어한다는 점을 먼저 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-106">When considering when to adopt WF4, it is important to first recognize that you control the timing.</span></span>  
  
- <span data-ttu-id="e4100-107">WF3는 .NET Framework 4의 완전히 지원 되는 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-107">WF3 is a fully supported part of the .NET Framework 4.</span></span>  
  
- <span data-ttu-id="e4100-108">WF3 응용 프로그램은 수정 없이 .NET Framework 4에서 실행 되며 완전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-108">WF3 applications run on the .NET Framework 4 without modification and continue to be fully supported.</span></span>  
  
- <span data-ttu-id="e4100-109">새 WF3 응용 프로그램을 만들 수 있으며 Visual Studio 2012에서 기존 응용 프로그램을 편집할 수 있으며 완전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-109">New WF3 applications can be created and your existing applications can be edited in Visual Studio 2012 and are fully supported.</span></span>  
  
 <span data-ttu-id="e4100-110">따라서 .NET Framework 4를 채택 하는 결정은 \* WF3 ()에서 w f 4 ()로 이동 하는 결정에서 분리 됩니다. \*</span><span class="sxs-lookup"><span data-stu-id="e4100-110">Thus, the decision to adopt the .NET Framework 4 is decoupled from your decision to move to WF4 (System.Activities.\*) from WF3 (System.Workflow.\*).</span></span> <span data-ttu-id="e4100-111">이 항목에서는 WF3 및 WF4 작업에 대한 정보를 담은 WF 마이그레이션 지침의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-111">This topic provides links to WF migration guidance that provides information about working with WF3 and WF4.</span></span>  
  
## <a name="wf-migration-white-papers-and-cookbooks"></a><span data-ttu-id="e4100-112">WF 마이그레이션 백서 및 cookbook</span><span class="sxs-lookup"><span data-stu-id="e4100-112">WF migration white papers and cookbooks</span></span>

 <span data-ttu-id="e4100-113">[WF 마이그레이션 개요](/previous-versions/appfabric/ff383417(v=azure.10)) 항목에서는 WF3와 w f 4 및 마이그레이션 전략 간의 관계에 대 한 광범위 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-113">The [WF Migration Overview](/previous-versions/appfabric/ff383417(v=azure.10)) topic provides a broad overview of the relationship between WF3 and WF4 and migration strategies.</span></span> <span data-ttu-id="e4100-114">관련 항목에서는 특정 항목을 자세히 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-114">Companion topics drill into specific topics.</span></span>  
  
 <span data-ttu-id="e4100-115">[WF 마이그레이션 개요](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-115">[WF Migration Overview](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-116">WF3과 WF4 간의 관계를 설명하고 .NET 4에서 워크플로 기술의 사용자 또는 잠재 사용자가 선택할 수 있는 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-116">Describes the relationship between WF3 and WF4, and the choices you have as a user or a potential user of workflow technology in .NET 4.</span></span>  
  
 <span data-ttu-id="e4100-117">[WF 마이그레이션: WF3 개발을 위한 최선의 방법](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-117">[WF Migration: Best Practices for WF3 Development](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-118">WF4로 쉽게 마이그레이션할 수 있도록 WF3 아티팩트를 디자인하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-118">Discusses how to design WF3 artifacts so they can be more easily migrated to WF4.</span></span>  
  
 <span data-ttu-id="e4100-119">[WF 지침: 규칙](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-119">[WF Guidance: Rules](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-120">규칙 관련 투자를 .NET Framework 4 솔루션으로 가져오는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-120">Discusses how to bring rules-related investments forward into .NET Framework 4 solutions.</span></span>  
  
 <span data-ttu-id="e4100-121">[WF 지침: 상태 시스템](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-121">[WF Guidance: State Machine](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-122">상태 시스템 활동이 없는 경우의 WF4 흐름 제어 모델링을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-122">Discusses WF4 control flow modeling in the absence of a State-Machine activity.</span></span>  
  
 <span data-ttu-id="e4100-123">이 지침은 .NET Framework 4를 대상으로 하는 워크플로 프로젝트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-123">Note that this guidance only applies to workflow projects that target .NET Framework 4.</span></span> <span data-ttu-id="e4100-124">상태 시스템 워크플로는 .NET 4.0.1 플랫폼 업데이트 1 릴리스에서 추가되었으며 .NET Framework 4.5의 일부로 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-124">State Machine workflows were added in .NET 4.0.1 with the release of Platform Update 1, and were included as part of .NET Framework 4.5.</span></span> <span data-ttu-id="e4100-125">.NET 4.0.1-4.0.3 및 .NET Framework 4.5의 상태 시스템 워크플로에 대 한 자세한 내용은 [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) And [state machine 워크플로만](state-machine-workflows.md)항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e4100-125">For more information about state machine workflows in .NET 4.0.1 - 4.0.3 and .NET Framework 4.5, see [Update 4.0.1 for Microsoft .NET Framework 4 Features](/previous-versions/dotnet/netframework-4.0/hh290669(v=vs.100)) and [State Machine Workflows](state-machine-workflows.md).</span></span>  
  
 <span data-ttu-id="e4100-126">[WF 마이그레이션 설명서: 사용자 지정 활동](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-126">[WF Migration Cookbook: Custom Activities](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-127">WF4에서 WF3 사용자 지정 활동을 다시 디자인하기 위한 지침과 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-127">Provides examples and instructions for redesigning WF3 custom activities on WF4.</span></span>  
  
 <span data-ttu-id="e4100-128">[WF 마이그레이션 설명서: 고급 사용자 지정 활동](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-128">[WF Migration Cookbook: Advanced Custom Activities](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-129">WF3 큐를 사용하고 자식 활동을 WF4 사용자 지정 활동으로 예약하는 고급 WF3 사용자 지정 활동을 다시 디자인하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-129">Provides guidance for redesigning advanced WF3 custom activities that use WF3 queues and schedule child activities as WF4 custom activities.</span></span>  
  
 <span data-ttu-id="e4100-130">[WF 마이그레이션 설명서: 워크플로](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-130">[WF Migration Cookbook: Workflows](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-131">WF4에서 WF3 워크플로를 다시 디자인하기 위한 지침과 예를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-131">Provides examples and instructions for redesigning WF3 workflows on WF4.</span></span>  
  
 <span data-ttu-id="e4100-132">[WF 마이그레이션 설명서: 워크플로 호스팅](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-132">[WF Migration Cookbook: Workflow Hosting](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-133">WF3 호스팅 코드를 WF4 호스팅 코드로 다시 디자인하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-133">Provides guidance for redesigning WF3 hosting code as WF4 hosting code.</span></span> <span data-ttu-id="e4100-134">이 설명서의 목적은 WF3과 WF4 간의 주요 워크플로 호스팅 차이점을 설명하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-134">The goal is to cover the key differences in workflow hosting between WF3 and WF4.</span></span>  
  
 <span data-ttu-id="e4100-135">[WF 마이그레이션 설명서: 워크플로 추적](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-135">[WF Migration Cookbook: Workflow Tracking](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-136">WF3 추적 코드 및 구성을 해당하는 WF4 추적 코드 및 구성을 사용하여 다시 디자인하기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-136">Provides guidance for redesigning WF3 tracking code and configuration using equivalent WF4 tracking code and configuration.</span></span>  
  
 <span data-ttu-id="e4100-137">[WF 지침: 워크플로 서비스](/previous-versions/appfabric/ff383417(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e4100-137">[WF Guidance: Workflow Services](/previous-versions/appfabric/ff383417(v=azure.10))</span></span>  
 <span data-ttu-id="e4100-138">일반적인 기본 제공 활동의 시나리오에서 WF3으로 만들어진 WCF(Windows Communication Foundation) 웹 서비스(일반적으로 워크플로 서비스라고 함)를 구현하는 워크플로를 WF4를 사용하도록 다시 디자인하기 위한 단계별 지침을 예제 중심으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e4100-138">Provides example-oriented step-by-step instructions for redesigning workflows that implement Windows Communication Foundation (WCF) web services (commonly referred to as workflow services) created in WF3 to use WF4, for common scenarios for out-of-box activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4100-139">참조</span><span class="sxs-lookup"><span data-stu-id="e4100-139">See also</span></span>

- <xref:System.Activities.Statements.Interop>
