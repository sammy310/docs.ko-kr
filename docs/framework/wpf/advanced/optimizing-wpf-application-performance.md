---
title: 앱 성능 최적화
ms.date: 03/30/2017
helpviewer_keywords:
- application rendering [WPF], performance
- application optimization [WPF]
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: ac8c6aa3-3c68-4a24-9827-3b6c829c1ebf
ms.openlocfilehash: 54d69e87ef2a9c5318e394422e3bcfcabcc76210
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646257"
---
# <a name="optimizing-wpf-application-performance"></a><span data-ttu-id="a3d9f-102">WPF 애플리케이션 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="a3d9f-102">Optimizing WPF Application Performance</span></span>
<span data-ttu-id="a3d9f-103">이 섹션은 응용 프로그램의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 성능을 향상시키는 방법을 찾고 있는 응용 프로그램 개발자를 위한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="a3d9f-103">This section is intended as a reference for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application developers who are looking for ways to improve the performance of their applications.</span></span> <span data-ttu-id="a3d9f-104">Microsoft .NET Framework를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]처음 접하는 개발자인 경우 먼저 두 플랫폼에 익숙해져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d9f-104">If you are a developer who is new to the Microsoft .NET Framework and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], you should first familiarize yourself with both platforms.</span></span> <span data-ttu-id="a3d9f-105">이 섹션에서는 두 가지 모두에 대한 실무 지식을 가정하고 응용 프로그램을 실행하고 실행할 수 있을 만큼 충분히 알고 있는 프로그래머를 위해 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3d9f-105">This section assumes working knowledge of both, and is written for programmers who already know enough to get their applications up and running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a3d9f-106">이 섹션에서 제공하는 성능 데이터는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 512 RAM과 ATI Radeon 9700 그래픽 카드가 있는 2.8GHz PC에서 실행되는 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d9f-106">The performance data provided in this section are based on [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications running on a 2.8 GHz PC with 512 RAM and an ATI Radeon 9700 graphics card.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3d9f-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a3d9f-107">In This Section</span></span>  
 [<span data-ttu-id="a3d9f-108">애플리케이션 성능 계획</span><span class="sxs-lookup"><span data-stu-id="a3d9f-108">Planning for Application Performance</span></span>](planning-for-application-performance.md)  
  
 [<span data-ttu-id="a3d9f-109">하드웨어 활용</span><span class="sxs-lookup"><span data-stu-id="a3d9f-109">Taking Advantage of Hardware</span></span>](optimizing-performance-taking-advantage-of-hardware.md)  
  
 [<span data-ttu-id="a3d9f-110">레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="a3d9f-110">Layout and Design</span></span>](optimizing-performance-layout-and-design.md)  
  
 [<span data-ttu-id="a3d9f-111">2D 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="a3d9f-111">2D Graphics and Imaging</span></span>](optimizing-performance-2d-graphics-and-imaging.md)  
  
 [<span data-ttu-id="a3d9f-112">개체 동작</span><span class="sxs-lookup"><span data-stu-id="a3d9f-112">Object Behavior</span></span>](optimizing-performance-object-behavior.md)  
  
 [<span data-ttu-id="a3d9f-113">애플리케이션 리소스</span><span class="sxs-lookup"><span data-stu-id="a3d9f-113">Application Resources</span></span>](optimizing-performance-application-resources.md)  
  
 [<span data-ttu-id="a3d9f-114">텍스트</span><span class="sxs-lookup"><span data-stu-id="a3d9f-114">Text</span></span>](optimizing-performance-text.md)  
  
 [<span data-ttu-id="a3d9f-115">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="a3d9f-115">Data Binding</span></span>](optimizing-performance-data-binding.md)  
  
 [<span data-ttu-id="a3d9f-116">컨트롤</span><span class="sxs-lookup"><span data-stu-id="a3d9f-116">Controls</span></span>](optimizing-performance-controls.md)  
  
 [<span data-ttu-id="a3d9f-117">기타 성능 추천 사항</span><span class="sxs-lookup"><span data-stu-id="a3d9f-117">Other Performance Recommendations</span></span>](optimizing-performance-other-recommendations.md)  
  
 [<span data-ttu-id="a3d9f-118">애플리케이션 시작 시간</span><span class="sxs-lookup"><span data-stu-id="a3d9f-118">Application Startup Time</span></span>](application-startup-time.md)  
  
## <a name="see-also"></a><span data-ttu-id="a3d9f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3d9f-119">See also</span></span>

- <xref:System.Windows.Media.RenderOptions>
- <xref:System.Windows.Media.RenderCapability>
- [<span data-ttu-id="a3d9f-120">그래픽 렌더링 계층</span><span class="sxs-lookup"><span data-stu-id="a3d9f-120">Graphics Rendering Tiers</span></span>](graphics-rendering-tiers.md)
- [<span data-ttu-id="a3d9f-121">WPF 그래픽 렌더링 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-121">WPF Graphics Rendering Overview</span></span>](../graphics-multimedia/wpf-graphics-rendering-overview.md)
- [<span data-ttu-id="a3d9f-122">레이아웃</span><span class="sxs-lookup"><span data-stu-id="a3d9f-122">Layout</span></span>](layout.md)
- [<span data-ttu-id="a3d9f-123">WPF의 트리</span><span class="sxs-lookup"><span data-stu-id="a3d9f-123">Trees in WPF</span></span>](trees-in-wpf.md)
- [<span data-ttu-id="a3d9f-124">Drawing 개체 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-124">Drawing Objects Overview</span></span>](../graphics-multimedia/drawing-objects-overview.md)
- [<span data-ttu-id="a3d9f-125">DrawingVisual 개체 사용</span><span class="sxs-lookup"><span data-stu-id="a3d9f-125">Using DrawingVisual Objects</span></span>](../graphics-multimedia/using-drawingvisual-objects.md)
- [<span data-ttu-id="a3d9f-126">종속성 속성 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-126">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="a3d9f-127">Freezable 개체 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-127">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="a3d9f-128">XAML 리소스</span><span class="sxs-lookup"><span data-stu-id="a3d9f-128">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="a3d9f-129">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="a3d9f-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="a3d9f-130">서식 있는 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="a3d9f-130">Drawing Formatted Text</span></span>](drawing-formatted-text.md)
- [<span data-ttu-id="a3d9f-131">WPF의 입력 체계</span><span class="sxs-lookup"><span data-stu-id="a3d9f-131">Typography in WPF</span></span>](typography-in-wpf.md)
- [<span data-ttu-id="a3d9f-132">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-132">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a3d9f-133">탐색 개요</span><span class="sxs-lookup"><span data-stu-id="a3d9f-133">Navigation Overview</span></span>](../app-development/navigation-overview.md)
- [<span data-ttu-id="a3d9f-134">애니메이션에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="a3d9f-134">Animation Tips and Tricks</span></span>](../graphics-multimedia/animation-tips-and-tricks.md)
- [<span data-ttu-id="a3d9f-135">연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱</span><span class="sxs-lookup"><span data-stu-id="a3d9f-135">Walkthrough: Caching Application Data in a WPF Application</span></span>](walkthrough-caching-application-data-in-a-wpf-application.md)
