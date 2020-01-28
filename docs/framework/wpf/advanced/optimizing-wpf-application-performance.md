---
title: 앱 성능 최적화
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: cc6ea051401199a87965565c920068fd55cb05d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743953"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="a9b9c-102">WPF 응용 프로그램 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="a9b9c-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="a9b9c-103">이 섹션은 응용 프로그램의 성능을 향상 시키는 방법을 찾고 있는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램 개발자를 위한 참조로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9b9c-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="a9b9c-104">Microsoft .NET Framework 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 처음 사용 하는 개발자는 먼저 두 플랫폼에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b9c-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="a9b9c-105">이 섹션에서는 두 가지 모두에 대 한 실무 지식이 있다고 가정 하 고, 응용 프로그램을 실행 하는 데 충분 한 지식이 이미 있는 프로그래머를 위해 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9b9c-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9b9c-106">이 섹션에서 제공 하는 성능 데이터는 2.8 GHz PC에서 실행 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 기반으로 512 RAM 및 ATI Radeon 9700 그래픽 카드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9b9c-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a9b9c-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a9b9c-107">In This Section</span></span>  
 [<span data-ttu-id="a9b9c-108">애플리케이션 성능 계획</span><span class="sxs-lookup"><span data-stu-id="a9b9c-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="a9b9c-109">하드웨어 이용</span><span class="sxs-lookup"><span data-stu-id="a9b9c-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="a9b9c-110">레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="a9b9c-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="a9b9c-111">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="a9b9c-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="a9b9c-112">개체 동작</span><span class="sxs-lookup"><span data-stu-id="a9b9c-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="a9b9c-113">애플리케이션 리소스</span><span class="sxs-lookup"><span data-stu-id="a9b9c-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="a9b9c-114">Text</span><span class="sxs-lookup"><span data-stu-id="a9b9c-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="a9b9c-115">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="a9b9c-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="a9b9c-116">컨트롤</span><span class="sxs-lookup"><span data-stu-id="a9b9c-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="a9b9c-117">기타 성능 권장 사항</span><span class="sxs-lookup"><span data-stu-id="a9b9c-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="a9b9c-118">애플리케이션 시작 시간</span><span class="sxs-lookup"><span data-stu-id="a9b9c-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="a9b9c-119">참조</span><span class="sxs-lookup"><span data-stu-id="a9b9c-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="a9b9c-120">그래픽 렌더링 계층</span><span class="sxs-lookup"><span data-stu-id="a9b9c-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="a9b9c-121">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="a9b9c-122">레이아웃</span><span class="sxs-lookup"><span data-stu-id="a9b9c-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="a9b9c-123">WPF의 트리</span><span class="sxs-lookup"><span data-stu-id="a9b9c-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="a9b9c-124">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="a9b9c-125">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="a9b9c-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="a9b9c-126">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="a9b9c-127">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="a9b9c-128">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="a9b9c-128">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="a9b9c-129">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="a9b9c-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="a9b9c-130">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="a9b9c-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="a9b9c-131">WPF의 입력 체계</span><span class="sxs-lookup"><span data-stu-id="a9b9c-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="a9b9c-132">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a9b9c-133">탐색 개요</span><span class="sxs-lookup"><span data-stu-id="a9b9c-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="a9b9c-134">애니메이션에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="a9b9c-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="a9b9c-135">연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="a9b9c-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
