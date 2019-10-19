---
title: 탐색 토폴로지 개요
ms.date: 03/30/2017
helpviewer_keywords:
- linear topology [WPF]
- fixed hierarchical topology [WPF]
- fixed linear topology [WPF]
- topologies [WPF]
- navigation topologies [WPF]
- dynamically-generated topology
ms.assetid: 5d5ee837-629a-4933-869a-186dc22ac43d
ms.openlocfilehash: 5d9b09085ed8057f53cae9f9177682b01e698f6d
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580717"
---
# <a name="navigation-topologies-overview"></a><span data-ttu-id="c9bc7-102">탐색 토폴로지 개요</span><span class="sxs-lookup"><span data-stu-id="c9bc7-102">Navigation Topologies Overview</span></span>
<a name="introduction"></a><span data-ttu-id="c9bc7-103">이 개요에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 탐색 토폴로지를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-103">This overview provides an introduction to navigation topologies in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span></span> <span data-ttu-id="c9bc7-104">세 가지 일반적인 탐색 토폴로지를 샘플과 함께 차례로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-104">Three common navigation topologies, with samples, are subsequently discussed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9bc7-105">이 항목을 읽기 전에 페이지 함수를 사용 하 여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 구조화 된 탐색 개념에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-105">Before reading this topic, you should be familiar with the concept of structured navigation in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] using page functions.</span></span> <span data-ttu-id="c9bc7-106">이러한 두 항목에 대 한 자세한 내용은 [구조적 탐색 개요](structured-navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-106">For more information on both of these topics, see [Structured Navigation Overview](structured-navigation-overview.md).</span></span>  
  
 <span data-ttu-id="c9bc7-107">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-107">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="c9bc7-108">탐색 토폴로지</span><span class="sxs-lookup"><span data-stu-id="c9bc7-108">Navigation Topologies</span></span>](#Navigation_Topologies)  
  
- [<span data-ttu-id="c9bc7-109">구조적 탐색 토폴로지</span><span class="sxs-lookup"><span data-stu-id="c9bc7-109">Structured Navigation Topologies</span></span>](#Structured_Navigation_Topologies)  
  
- [<span data-ttu-id="c9bc7-110">고정 선형 토폴로지 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-110">Navigation over a Fixed Linear Topology</span></span>](#Navigation_over_a_Fixed_Linear_Topology)  
  
- [<span data-ttu-id="c9bc7-111">고정 계층적 토폴로지 동적 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-111">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>](#Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology)  
  
- [<span data-ttu-id="c9bc7-112">동적으로 생성된 토폴로지 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-112">Navigation over a Dynamically Generated Topology</span></span>](#Navigation_over_a_Dynamically_Generated_Topology)  
  
<a name="Navigation_Topologies"></a>   
## <a name="navigation-topologies"></a><span data-ttu-id="c9bc7-113">탐색 토폴로지</span><span class="sxs-lookup"><span data-stu-id="c9bc7-113">Navigation Topologies</span></span>  
 <span data-ttu-id="c9bc7-114">@No__t_0 탐색은 일반적으로 클릭 하면 다른 페이지로 이동 하는 하이퍼링크 (<xref:System.Windows.Documents.Hyperlink>)가 있는 페이지 (<xref:System.Windows.Controls.Page>)로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-114">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], navigation typically consists of pages (<xref:System.Windows.Controls.Page>) with hyperlinks (<xref:System.Windows.Documents.Hyperlink>) that navigate to other pages when clicked.</span></span> <span data-ttu-id="c9bc7-115">탐색 되는 페이지는 Uri (uniform resource identifier)로 식별 됩니다 ( [WPF의 Pack uri](pack-uris-in-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="c9bc7-115">Pages that are navigated to are identified by uniform resource identifiers (URIs) (see [Pack URIs in WPF](pack-uris-in-wpf.md)).</span></span> <span data-ttu-id="c9bc7-116">페이지, 하이퍼링크 및 Uri (uniform resource identifier)를 보여 주는 다음과 같은 간단한 예제를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-116">Consider the following simple example that shows pages, hyperlinks, and uniform resource identifiers (URIs):</span></span>  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page1.xaml#page1)]  
  
 [!code-xaml[NavigationTopologiesOverviewSnippets#Page2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationTopologiesOverviewSnippets/CS/Page2.xaml#page2)]  
  
 <span data-ttu-id="c9bc7-117">이러한 페이지는 페이지 간에 이동할 수 있는 방법에 의해 구조가 결정 되는 *탐색 토폴로지에서* 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-117">These pages are arranged in a *navigation topology* whose structure is determined by how you can navigate between the pages.</span></span> <span data-ttu-id="c9bc7-118">이 특정 탐색 토폴로지는 간단한 시나리오에 적합하지만 탐색은 더 복잡한 토폴로지를 필요로 하며 그중 일부는 애플리케이션이 실행 중일 때만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-118">This particular navigation topology is suitable in simple scenarios, although navigation can require more complex topologies, some of which can only be defined when an application is running.</span></span>  
  
 <span data-ttu-id="c9bc7-119">이 항목에서는 *고정 선형*, *고정 계층*및 *동적으로 생성 된*세 가지 일반적인 탐색 토폴로지에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-119">This topic covers three common navigation topologies: *fixed linear*, *fixed hierarchical*, and *dynamically generated*.</span></span> <span data-ttu-id="c9bc7-120">각 탐색 토폴로지는 다음 그림에 표시 된 것과 같은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 있는 샘플을 사용 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-120">Each navigation topology is demonstrated with a sample that has a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] like the one that is shown in the following figure:</span></span>  
  
 ![데이터 항목 및 탐색 단추가 있는 작업 페이지](./media/navigation-topologies-overview/navigation-topology-data-items.png)  
  
<a name="Structured_Navigation_Topologies"></a>   
## <a name="structured-navigation-topologies"></a><span data-ttu-id="c9bc7-122">구조적 탐색 토폴로지</span><span class="sxs-lookup"><span data-stu-id="c9bc7-122">Structured Navigation Topologies</span></span>  
 <span data-ttu-id="c9bc7-123">탐색 토폴로지는 광범위하게 두 가지로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-123">There are two broad types of navigation topologies:</span></span>  
  
- <span data-ttu-id="c9bc7-124">**고정 토폴로지**: 컴파일 시 정의되며 런타임 시 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-124">**Fixed Topology**: defined at compile time and does not change at run time.</span></span> <span data-ttu-id="c9bc7-125">고정 토폴로지는 선형 순서 또는 계층적 순서로 고정된 페이지 시퀀스를 탐색하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-125">Fixed topologies are useful for navigation through a fixed sequence of pages in either a linear or hierarchical order.</span></span>  
  
- <span data-ttu-id="c9bc7-126">**동적 토폴로지**: 사용자, 애플리케이션 또는 시스템에서 수집한 입력을 기반으로 런타임 시 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-126">**Dynamic Topology**: defined at run time based on input that is collected from the user, the application, or the system.</span></span> <span data-ttu-id="c9bc7-127">동적 토폴로지는 페이지를 다른 시퀀스로 탐색할 수 있을 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-127">Dynamic topologies are useful when pages can be navigated in different sequences.</span></span>  
  
 <span data-ttu-id="c9bc7-128">페이지를 사용하여 탐색 토폴로지를 만들 수도 있지만 샘플에서는 페이지 함수를 사용하는데 이 기능이 토폴로지의 페이지를 통해 데이터를 전달하고 반환하는 지원을 단순화하는 추가 지원을 제공하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-128">Although it is possible to create navigation topologies using pages, the samples use page functions because they provide additional support that simplifies support for passing and returning data through the pages of a topology.</span></span>  
  
<a name="Navigation_over_a_Fixed_Linear_Topology"></a>   
## <a name="navigation-over-a-fixed-linear-topology"></a><span data-ttu-id="c9bc7-129">고정 선형 토폴로지 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-129">Navigation over a Fixed Linear Topology</span></span>  
 <span data-ttu-id="c9bc7-130">고정 선형 토폴로지는 고정된 시퀀스로 탐색되는 하나 이상의 마법사 페이지가 있는 마법사의 구조와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-130">A fixed linear topology is analogous to the structure of a wizard that has one or more wizard pages that are navigated in a fixed sequence.</span></span> <span data-ttu-id="c9bc7-131">다음 그림은 고정 선형 토폴로지를 사용 하는 마법사의 상위 수준 구조와 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-131">The following figure shows the high-level structure and flow of a wizard with a fixed linear topology:</span></span>  
  
 ![고정 선형 토폴로지를 표시 하는 다이어그램입니다.](./media/navigation-topologies-overview/navigation-topology-fixed-linear.png)  
  
 <span data-ttu-id="c9bc7-133">고정 선형 토폴로지를 탐색하는 일반적인 동작은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-133">The typical behaviors for navigating over a fixed linear topology include the following:</span></span>  
  
- <span data-ttu-id="c9bc7-134">호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-134">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="c9bc7-135">호출 페이지에서 첫 번째 마법사 페이지를 직접 호출할 수 있으므로 시작 관리자 페이지 ([!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없는 <xref:System.Windows.Navigation.PageFunction%601>)가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-135">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="c9bc7-136">그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-136">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="c9bc7-137">사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-137">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="c9bc7-138">사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-138">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="c9bc7-139">사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-139">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="c9bc7-140">사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-140">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="c9bc7-141">마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-141">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="c9bc7-142">사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-142">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="c9bc7-143">마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-143">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="c9bc7-144">이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-144">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Dynamic_Navigation_over_a_Fixed_Hierarchical_Topology"></a>   
## <a name="dynamic-navigation-over-a-fixed-hierarchical-topology"></a><span data-ttu-id="c9bc7-145">고정 계층적 토폴로지 동적 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-145">Dynamic Navigation over a Fixed Hierarchical Topology</span></span>  
 <span data-ttu-id="c9bc7-146">일부 응용 프로그램에서는 다음 그림에 표시 된 것 처럼 페이지에서 두 개 이상의 다른 페이지를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-146">In some applications, pages allow navigation to two or more other pages, as shown in the following figure:</span></span> 
  
 ![여러 페이지를 탐색할 수 있는 페이지를 표시 하는 다이어그램입니다.](./media/navigation-topologies-overview/navigation-topology-multiple-pages.png)  
  
 <span data-ttu-id="c9bc7-148">이 구조는 고정 계층적 토폴로지로 알려져 있으며 계층 구조가 통과되는 시퀀스는 종종 애플리케이션이나 사용자에 의해 런타임 시 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-148">This structure is known as a fixed hierarchical topology, and the sequence in which the hierarchy is traversed is often determined at run time by either the application or the user.</span></span> <span data-ttu-id="c9bc7-149">런타임 시 두 개 이상의 다른 페이지를 탐색할 수 있는 계층 구조의 각 페이지는 탐색할 페이지를 결정하는 데 필요한 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-149">At run time, each page in the hierarchy that allows navigation to two or more other pages gathers the data required to determine which page to navigate to.</span></span> <span data-ttu-id="c9bc7-150">다음 그림에서는 앞의 그림을 기반으로 가능한 몇 가지 탐색 시퀀스 중 하나를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-150">The following figure illustrates one of several possible navigation sequences based on the previous figure:</span></span>  
  
 ![가능한 탐색 시퀀스를 표시 하는 다이어그램입니다.](./media/navigation-topologies-overview/navigation-topology-fixed-hierarchical.png)  
  
 <span data-ttu-id="c9bc7-152">고정 계층적 구조의 페이지를 탐색하는 시퀀스가 런타임에 결정되더라도 사용자 환경은 고정 선형 토폴로지의 사용자 환경과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-152">Even though the sequence in which pages in a fixed hierarchical structure are navigated is determined at run time, the user experience is the same as the user experience for a fixed linear topology:</span></span>  
  
- <span data-ttu-id="c9bc7-153">호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-153">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="c9bc7-154">호출 페이지에서 첫 번째 마법사 페이지를 직접 호출할 수 있으므로 시작 관리자 페이지 ([!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없는 <xref:System.Windows.Navigation.PageFunction%601>)가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-154">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="c9bc7-155">그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-155">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="c9bc7-156">사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-156">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="c9bc7-157">사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-157">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="c9bc7-158">사용자는 저널을 탐색할 때 탐색 시퀀스를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-158">Users can change the navigation sequence if they navigate back through the journal.</span></span>  
  
- <span data-ttu-id="c9bc7-159">사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-159">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="c9bc7-160">사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-160">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="c9bc7-161">마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-161">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="c9bc7-162">사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-162">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="c9bc7-163">마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-163">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="c9bc7-164">이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-164">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
<a name="Navigation_over_a_Dynamically_Generated_Topology"></a>   
## <a name="navigation-over-a-dynamically-generated-topology"></a><span data-ttu-id="c9bc7-165">동적으로 생성된 토폴로지 탐색</span><span class="sxs-lookup"><span data-stu-id="c9bc7-165">Navigation over a Dynamically Generated Topology</span></span>  
 <span data-ttu-id="c9bc7-166">일부 애플리케이션에서 두 개 이상의 페이지를 탐색하는 시퀀스는 런타임 시 사용자, 애플리케이션 또는 외부 데이터에 의해서만 결정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-166">In some applications, the sequence in which two or more pages are navigated can only be determined at run time, whether by the user, the application, or external data.</span></span> <span data-ttu-id="c9bc7-167">다음 그림에서는 탐색 시퀀스가 결정 되지 않은 페이지 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-167">The following figure illustrates a set of pages with an undetermined navigation sequence:</span></span>  
  
 ![탐색 시퀀스가 결정 되지 않은 페이지 집합입니다.](./media/navigation-topologies-overview/navigation-topology-dynamically-generated.png)  
  
 <span data-ttu-id="c9bc7-169">다음 그림은 런타임에 사용자가 선택한 탐색 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-169">The next figure illustrates a navigation sequence that was chosen by the user at run time:</span></span>  
  
 ![런타임에 선택 된 탐색 시퀀스를 표시 하는 다이어그램입니다.](./media/navigation-topologies-overview/navigation-topology-sequence-chosen-run-time.png)  
  
 <span data-ttu-id="c9bc7-171">탐색 시퀀스를 동적으로 생성된 토폴로지라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-171">The navigation sequence is known as a dynamically generated topology.</span></span> <span data-ttu-id="c9bc7-172">다른 탐색 토폴로지와 마찬가지로 사용자의 환경은 이전 토폴로지의 경우와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-172">For the user, as with the other navigation topologies, the user experience is the same as it is for the previous topologies:</span></span>  
  
- <span data-ttu-id="c9bc7-173">호출 페이지에서 마법사를 초기화하고 첫 번째 마법사 페이지로 이동하는 시작 프로그램 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-173">Navigating from the calling page to a launcher page that initializes the wizard and navigates to the first wizard page.</span></span> <span data-ttu-id="c9bc7-174">호출 페이지에서 첫 번째 마법사 페이지를 직접 호출할 수 있으므로 시작 관리자 페이지 ([!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없는 <xref:System.Windows.Navigation.PageFunction%601>)가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-174">A launcher page (a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-less <xref:System.Windows.Navigation.PageFunction%601>) is not required, since a calling page can call the first wizard page directly.</span></span> <span data-ttu-id="c9bc7-175">그러나 시작 페이지를 사용하면 특히 초기화가 복잡한 경우 마법사 초기화를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-175">Using a launcher page, however, can simplify wizard initialization, particularly if initialization is complex.</span></span>  
  
- <span data-ttu-id="c9bc7-176">사용자는 뒤로 및 앞으로 단추(또는 하이퍼링크)를 사용하여 페이지 사이를 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-176">Users can navigate between pages by using Back and Forward buttons (or hyperlinks).</span></span>  
  
- <span data-ttu-id="c9bc7-177">사용자는 저널을 사용하여 페이지 간을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-177">Users can navigate between pages using the journal.</span></span>  
  
- <span data-ttu-id="c9bc7-178">사용자는 [취소] 단추를 눌러 마법사 페이지에서 마법사를 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-178">Users can cancel the wizard from any wizard page by pressing a Cancel button.</span></span>  
  
- <span data-ttu-id="c9bc7-179">사용자는 [마침] 단추를 눌러 마지막 마법사 페이지에서 마법사를 승인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-179">Users can accept the wizard on the last wizard page by pressing a Finish button.</span></span>  
  
- <span data-ttu-id="c9bc7-180">마법사가 취소되면 적절한 결과를 반환하며 데이터는 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-180">If a wizard is canceled, the wizard returns an appropriate result, and does not return any data.</span></span>  
  
- <span data-ttu-id="c9bc7-181">사용자가 마법사를 승인하면 마법사가 적절한 결과와 수집한 데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-181">If a user accepts a wizard, the wizard returns an appropriate result, and returns the data it collected.</span></span>  
  
- <span data-ttu-id="c9bc7-182">마법사가 완료되면(승인 또는 취소) 마법사가 구성하는 페이지가 저널에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-182">When the wizard is complete (accepted or canceled), the pages that the wizard comprises are removed from the journal.</span></span> <span data-ttu-id="c9bc7-183">이렇게 하면 마법사의 각 인스턴스가 격리되어 잠재적인 데이터 또는 비정상 상태를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9bc7-183">This keeps each instance of the wizard isolated, thereby avoiding potential data or state anomalies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bc7-184">참조</span><span class="sxs-lookup"><span data-stu-id="c9bc7-184">See also</span></span>

- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Navigation.PageFunction%601>
- <xref:System.Windows.Navigation.NavigationService>
- [<span data-ttu-id="c9bc7-185">구조적 탐색 개요</span><span class="sxs-lookup"><span data-stu-id="c9bc7-185">Structured Navigation Overview</span></span>](structured-navigation-overview.md)
