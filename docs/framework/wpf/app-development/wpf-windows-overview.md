---
title: Windows 개요
description: Windows Presentation Foundation (WPF)에서 독립 실행형 응용 프로그램에 대 한 windows를 만들고 관리 하는 기본 사항에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], displaying content via
- XAML pages [WPF], displaying
- content [WPF], displaying via XAML
- window objects [WPF]
- hosting [WPF], applications
- managing windows [WPF]
- dialog boxes [WPF]
- Page object [WPF]
- NavigationWindow objects [WPF]
- applications [WPF], hosting
- content [WPF], displaying
- events [WPF]
- content [WPF], displaying via procedural code
- modal windows [WPF]
- procedural code [WPF], displaying content via
- displaying content via procedural code [WPF]
- window management [WPF]
- displaying content [WPF]
- window events [WPF]
- windows [WPF]
- modal dialog boxes [WPF]
- displaying XAML pages [WPF]
ms.assetid: 737d04ec-8861-46c3-8d44-fa11d3528d23
ms.openlocfilehash: e1ad3c118fbaea8f1e23d012721f0cf3c2c50015
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622889"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="4b2fc-103">WPF 창 개요</span><span class="sxs-lookup"><span data-stu-id="4b2fc-103">WPF Windows Overview</span></span>
<span data-ttu-id="4b2fc-104">사용자는 Windows를 통해 Windows Presentation Foundation (WPF) 독립 실행형 응용 프로그램과 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-104">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="4b2fc-105">창의 기본 용도는 데이터를 시각화하는 콘텐츠를 호스트하고 사용자가 데이터와 상호 작용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-105">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="4b2fc-106">독립 실행형 WPF 응용 프로그램은 클래스를 사용 하 여 자체 창을 제공 <xref:System.Windows.Window> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-106">Standalone WPF applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="4b2fc-107">이 항목에서는 <xref:System.Windows.Window> 독립 실행형 응용 프로그램에서 windows를 만들고 관리 하는 기본 사항을 다루기 전에 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-107">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-108">Xbap (XAML 브라우저 응용 프로그램) 및 느슨한 페이지를 비롯 한 브라우저에서 호스팅되는 WPF 응용 프로그램 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 은 자체 창을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-108">Browser-hosted WPF applications, including XAML browser applications (XBAPs) and loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="4b2fc-109">대신 Windows Internet Explorer에서 제공 하는 windows에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-109">Instead, they are hosted in windows provided by Windows Internet Explorer.</span></span> <span data-ttu-id="4b2fc-110">[WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-110">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a><span data-ttu-id="4b2fc-111">Window 클래스</span><span class="sxs-lookup"><span data-stu-id="4b2fc-111">The Window Class</span></span>  
 <span data-ttu-id="4b2fc-112">다음 그림에서는 창의 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-112">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![창 요소를 보여 주는 스크린샷](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="4b2fc-114">창은 비클라이언트 영역과 클라이언트 영역의 두 영역으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-114">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="4b2fc-115">창의 *비클라이언트 영역은* WPF에서 구현 되며, 다음을 포함 하 여 대부분의 창에 공통적인 창 부분을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-115">The *non-client area* of a window is implemented by WPF and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
- <span data-ttu-id="4b2fc-116">테두리.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-116">A border.</span></span>  
  
- <span data-ttu-id="4b2fc-117">제목 표시줄.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-117">A title bar.</span></span>  
  
- <span data-ttu-id="4b2fc-118">아이콘.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-118">An icon.</span></span>  
  
- <span data-ttu-id="4b2fc-119">최소화, 최대화 및 복원 단추.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-119">Minimize, Maximize, and Restore buttons.</span></span>  
  
- <span data-ttu-id="4b2fc-120">닫기 단추.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-120">A Close button.</span></span>  
  
- <span data-ttu-id="4b2fc-121">사용자가 창을 최소화, 최대화, 복원, 이동, 크기 조정 및 닫을 수 있는 메뉴 항목이 들어 있는 시스템 메뉴.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-121">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="4b2fc-122">창의 *클라이언트 영역은* 창의 비클라이언트 영역에 있는 영역이 며 개발자가 메뉴 모음, 도구 모음 및 컨트롤과 같은 응용 프로그램 관련 콘텐츠를 추가 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-122">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="4b2fc-123">WPF에서 창은 <xref:System.Windows.Window> 다음 작업을 수행 하는 데 사용 하는 클래스에 의해 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-123">In WPF, a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
- <span data-ttu-id="4b2fc-124">창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-124">Display a window.</span></span>  
  
- <span data-ttu-id="4b2fc-125">창의 크기, 위치 및 모양을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-125">Configure the size, position, and appearance of a window.</span></span>  
  
- <span data-ttu-id="4b2fc-126">애플리케이션별 콘텐츠를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-126">Host application-specific content.</span></span>  
  
- <span data-ttu-id="4b2fc-127">창의 수명을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-127">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a><span data-ttu-id="4b2fc-128">창 구현</span><span class="sxs-lookup"><span data-stu-id="4b2fc-128">Implementing a Window</span></span>  
 <span data-ttu-id="4b2fc-129">일반적인 창의 구현은 모양과 동작으로 구성 되며, *모양은* 창이 사용자에 게 표시 되는 방식을 정의 하 고 *동작은* 사용자가 상호 작용할 때 창이 작동 하는 방식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-129">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="4b2fc-130">WPF에서 코드 또는 태그 중 하나를 사용 하 여 창의 모양 및 동작을 구현할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-130">In WPF, you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="4b2fc-131">그러나 일반적으로 창의 모양은 태그를 사용 하 여 구현 되며, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 해당 동작은 다음 예제와 같이 코드를 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-131">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="4b2fc-132">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]태그 파일 및 코드 숨김이 함께 작동 하도록 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-132">To enable a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
- <span data-ttu-id="4b2fc-133">태그에서 요소는 `Window` 특성을 포함 해야 합니다 `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-133">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="4b2fc-134">응용 프로그램을 빌드할 때 `x:Class` 태그 파일에가 있으면 MSBuild (Microsoft build engine)가 `partial` 에서 파생 되 <xref:System.Windows.Window> 고 특성으로 지정 된 이름을 가진 클래스를 만듭니다 `x:Class` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-134">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="4b2fc-135">이렇게 하려면 스키마에 대 한 XML 네임 스페이스 선언을 추가 해야 합니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-135">This requires the addition of an XML namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="4b2fc-136">생성 된 `partial` 클래스는 `InitializeComponent` 이벤트를 등록 하 고 태그에 구현 된 속성을 설정 하기 위해 호출 하는 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-136">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
- <span data-ttu-id="4b2fc-137">코드를 사용할 때 클래스는 `partial` 태그의 특성으로 지정 되는 동일한 이름의 클래스 여야 `x:Class` 하며에서 파생 되어야 합니다 <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-137">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="4b2fc-138">이렇게 하면 `partial` 응용 프로그램을 빌드할 때 태그 파일에 대해 생성 되는 클래스와 코드 숨김이 연결 될 수 있습니다 ( [WPF 응용 프로그램 빌드](building-a-wpf-application-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-138">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
- <span data-ttu-id="4b2fc-139">코드 숨김으로 클래스는 메서드를 <xref:System.Windows.Window> 호출 하는 생성자를 구현 해야 합니다 `InitializeComponent` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-139">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="4b2fc-140">`InitializeComponent`는 태그 파일의 생성 된 클래스에 의해 구현 되어 `partial` 이벤트를 등록 하 고 태그에 정의 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-140">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-141">Visual Studio를 사용 하 여 프로젝트에 새를 추가 하는 경우 <xref:System.Windows.Window> 는 <xref:System.Windows.Window> 태그와 코드 숨김으로 모두 사용 하 여 구현 되며, 여기에 설명 된 대로 태그와 코드 이름 파일 간의 연결을 만드는 데 필요한 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-141">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="4b2fc-142">이 구성을 적용 하면 창의 모양을 태그에 정의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 하 고 코드 숨김으로 동작을 구현 하는 데 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-142">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="4b2fc-143">다음 예제에서는 태그에서 구현 된 단추와 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 코드 숨김으로 구현 된 단추의 이벤트에 대 한 이벤트 처리기가 있는 창을 보여 줍니다 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-143">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="4b2fc-144">MSBuild에 대해 창 정의 구성</span><span class="sxs-lookup"><span data-stu-id="4b2fc-144">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="4b2fc-145">창을 구현 하는 방법에 따라 MSBuild에 대해 구성 되는 방식이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-145">How you implement your window determines how it is configured for MSBuild.</span></span> <span data-ttu-id="4b2fc-146">태그와 코드 숨김으로 모두 사용 하 여 정의 된 창의 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="4b2fc-146">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
- <span data-ttu-id="4b2fc-147">XAML 태그 파일은 MSBuild 항목으로 구성 됩니다 `Page` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-147">XAML markup files are configured as MSBuild `Page` items.</span></span>  
  
- <span data-ttu-id="4b2fc-148">코드 숨겨진 파일은 MSBuild 항목으로 구성 됩니다 `Compile` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-148">Code-behind files are configured as MSBuild `Compile` items.</span></span>  
  
 <span data-ttu-id="4b2fc-149">이는 다음 MSBuild 프로젝트 파일에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-149">This is shown in the following MSBuild project file.</span></span>  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003" ... >  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="4b2fc-150">WPF 응용 프로그램을 빌드하는 방법에 대 한 자세한 내용은 [Wpf 응용 프로그램 빌드](building-a-wpf-application-wpf.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-150">For information about building WPF applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a><span data-ttu-id="4b2fc-151">창 수명</span><span class="sxs-lookup"><span data-stu-id="4b2fc-151">Window Lifetime</span></span>  
 <span data-ttu-id="4b2fc-152">다른 클래스와 마찬가지로 창에는 창이 열린 후 처음 인스턴스화될 때 시작하여, 열린 후 활성화 및 비활성화되고 최종적으로 닫힐 때까지의 기간인 수명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-152">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a><span data-ttu-id="4b2fc-153">창 열기</span><span class="sxs-lookup"><span data-stu-id="4b2fc-153">Opening a Window</span></span>  
 <span data-ttu-id="4b2fc-154">창을 열려면 먼저 다음 예제에서 설명하는 것처럼 창의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-154">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="4b2fc-155">이 예제에서는 `MarkupAndCodeBehindWindow` 이벤트가 발생할 때 발생 하는 응용 프로그램이 시작 될 때가 인스턴스화됩니다 <xref:System.Windows.Application.Startup> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-155">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="4b2fc-156">창이 인스턴스화될 때이에 대 한 참조가 개체에 의해 관리 되는 창 목록에 자동으로 추가 됩니다 <xref:System.Windows.Application> (참조 <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-156">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="4b2fc-157">또한 인스턴스화될 첫 번째 창은 기본적으로 <xref:System.Windows.Application> 주 응용 프로그램 창으로 설정 됩니다 (참조 <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-157">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="4b2fc-158">마지막으로 메서드를 호출 하 여 창을 엽니다. <xref:System.Windows.Window.Show%2A> 결과는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-158">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![창을 호출 하 여 열린 창입니다. Show](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="4b2fc-160">를 호출 하 여 연 창은 <xref:System.Windows.Window.Show%2A> 모덜리스 창이 며,이 창은 응용 프로그램이 동일한 응용 프로그램에서 다른 창을 활성화할 수 있도록 하는 모드에서 작동 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-160">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-161"><xref:System.Windows.Window.ShowDialog%2A>대화 상자와 같은 창을 모달로 열기 위해가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-161"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="4b2fc-162">자세한 내용은 [대화 상자 개요](dialog-boxes-overview.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-162">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="4b2fc-163"><xref:System.Windows.Window.Show%2A>가 호출 되 면 창에서 사용자 입력을 받을 수 있도록 하는 인프라를 설정 하기 전에 초기화 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-163">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="4b2fc-164">창이 초기화 되 면 <xref:System.Windows.Window.SourceInitialized> 이벤트가 발생 하 고 창이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-164">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="4b2fc-165">바로 가기로를 <xref:System.Windows.Application.StartupUri%2A> 설정 하 여 응용 프로그램이 시작 될 때 자동으로 열리는 첫 번째 창을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-165">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="4b2fc-166">응용 프로그램이 시작 되 면의 값으로 지정 된 창이 <xref:System.Windows.Application.StartupUri%2A> 모덜리스 창으로으로 열리고 내부적으로 해당 메서드를 호출 하 여 창이 열립니다. <xref:System.Windows.Window.Show%2A></span><span class="sxs-lookup"><span data-stu-id="4b2fc-166">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a><span data-ttu-id="4b2fc-167">창 소유권</span><span class="sxs-lookup"><span data-stu-id="4b2fc-167">Window Ownership</span></span>  
 <span data-ttu-id="4b2fc-168">메서드를 사용 하 여 연 창에는 <xref:System.Windows.Window.Show%2A> 해당 창을 만든 창과의 암시적 관계가 없습니다. 사용자가 다른 창에 독립적으로 상호 작용할 수 있습니다. 즉, 두 창에서 모두 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-168">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
- <span data-ttu-id="4b2fc-169">창 중 하나에 속성이로 설정 되어 있지 않은 경우 다른를 포함 <xref:System.Windows.Window.Topmost%2A> `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-169">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
- <span data-ttu-id="4b2fc-170">다른 창에 영향을 주지 않고 최소화, 최대화 및 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-170">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="4b2fc-171">일부 창은 해당 창을 여는 창과의 관계를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-171">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="4b2fc-172">예를 들어 IDE (통합 개발 환경) 응용 프로그램은 속성 창 및 도구 창을 열 수 있습니다 .이 창에서 일반적인 동작을 통해 해당 창을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-172">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="4b2fc-173">또한 이러한 창은 항상 해당 창을 만든 창과 함께 닫히고, 최소화되고, 최대화되고, 복원되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-173">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="4b2fc-174">이러한 관계는 한 *창을 다른 창* 으로 만들고 소유자 창에 대 한 <xref:System.Windows.Window.Owner%2A> 참조로 *소유 창의* 속성을 설정 하 여 설정할 수 있습니다. *owner window*</span><span class="sxs-lookup"><span data-stu-id="4b2fc-174">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="4b2fc-175">다음 예제에서 이를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-175">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="4b2fc-176">소유권이 설정된 후:</span><span class="sxs-lookup"><span data-stu-id="4b2fc-176">After ownership is established:</span></span>  
  
- <span data-ttu-id="4b2fc-177">소유 된 창은 해당 속성의 값을 검사 하 여 소유자 창을 참조할 수 있습니다 <xref:System.Windows.Window.Owner%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-177">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
- <span data-ttu-id="4b2fc-178">소유자 창은 해당 속성의 값을 검사 하 여 소유 하 고 있는 모든 창을 검색할 수 있습니다 <xref:System.Windows.Window.OwnedWindows%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-178">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a><span data-ttu-id="4b2fc-179">창 활성화 방지</span><span class="sxs-lookup"><span data-stu-id="4b2fc-179">Preventing Window Activation</span></span>  
 <span data-ttu-id="4b2fc-180">인터넷 메신저 스타일 응용 프로그램의 대화 창 또는 전자 메일 응용 프로그램의 알림 창과 같이 창이 표시 될 때 활성화 되지 않아야 하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-180">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="4b2fc-181">응용 프로그램에 표시 될 때 활성화 하지 않아야 하는 창이 있는 경우 <xref:System.Windows.Window.ShowActivated%2A> `false` 메서드를 처음으로 호출 하기 전에 해당 속성을로 설정할 수 있습니다 <xref:System.Windows.Window.Show%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-181">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="4b2fc-182">이렇게 하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-182">As a consequence:</span></span>  
  
- <span data-ttu-id="4b2fc-183">창이 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-183">The window is not activated.</span></span>  
  
- <span data-ttu-id="4b2fc-184">창의 이벤트는 <xref:System.Windows.Window.Activated> 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-184">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
- <span data-ttu-id="4b2fc-185">현재 활성 창이 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-185">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="4b2fc-186">그러나 사용자가 클라이언트 영역이나 비클라이언트 영역을 클릭하여 창을 활성화하면 해당 창이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-186">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="4b2fc-187">이 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-187">In this case:</span></span>  
  
- <span data-ttu-id="4b2fc-188">창이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-188">The window is activated.</span></span>  
  
- <span data-ttu-id="4b2fc-189">창의 <xref:System.Windows.Window.Activated> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-189">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
- <span data-ttu-id="4b2fc-190">이전에 활성 상태였던 창이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-190">The previously activated window is deactivated.</span></span>  
  
- <span data-ttu-id="4b2fc-191"><xref:System.Windows.Window.Deactivated>이후 창의 및 <xref:System.Windows.Window.Activated> 이벤트는 사용자 동작에 대 한 응답으로 예상 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-191">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a><span data-ttu-id="4b2fc-192">창 활성화</span><span class="sxs-lookup"><span data-stu-id="4b2fc-192">Window Activation</span></span>  
 <span data-ttu-id="4b2fc-193">창이 처음 열리면 창이 활성 창이 됩니다 (를로 설정 하 여 표시 되지 않은 경우 <xref:System.Windows.Window.ShowActivated%2A> `false` ).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-193">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="4b2fc-194">*활성 창은* 키 입력 및 마우스 클릭과 같은 사용자 입력을 현재 캡처하는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-194">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="4b2fc-195">창이 활성화 되 면 <xref:System.Windows.Window.Activated> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-195">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-196">창이 처음 열릴 때 <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.Window.ContentRendered> 이벤트는 이벤트가 발생 한 후에만 발생 <xref:System.Windows.Window.Activated> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-196">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="4b2fc-197">이 점을 염두에 두면가 발생할 때 창이 효과적으로 열린 것으로 간주 될 수 있습니다 <xref:System.Windows.Window.ContentRendered> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-197">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="4b2fc-198">창이 활성 창이 되면 사용자는 같은 애플리케이션의 다른 창을 활성화하거나 다른 애플리케이션을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-198">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="4b2fc-199">이 경우 현재 활성화 된 창이 비활성화 되 고 이벤트를 발생 시킵니다 <xref:System.Windows.Window.Deactivated> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-199">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="4b2fc-200">마찬가지로 사용자가 현재 비활성화 된 창을 선택 하면 창이 다시 활성화 <xref:System.Windows.Window.Activated> 되 고 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-200">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="4b2fc-201">및를 처리 하는 일반적인 이유 중 하나는 <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> 창이 활성 상태일 때만 실행 될 수 있는 기능을 사용 하거나 사용 하지 않도록 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-201">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="4b2fc-202">예를 들어 일부 창은 게임 및 비디오 플레이어를 포함하여 지속적인 사용자의 입력이나 주의가 필요한 대화식 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-202">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="4b2fc-203">다음 예제는 <xref:System.Windows.Window.Activated> 이 동작을 처리 하 고 구현 하는 방법을 보여 주는 간단한 비디오 플레이어입니다 <xref:System.Windows.Window.Deactivated> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-203">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="4b2fc-204">다른 형식의 애플리케이션은 창이 비활성화되었을 때 계속 백그라운드에서 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-204">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="4b2fc-205">예를 들어 메일 클라이언트는 사용자가 다른 애플리케이션을 사용하고 있을 때 메일 서버를 계속 폴링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-205">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="4b2fc-206">이러한 애플리케이션에는 기본 창이 비활성화되었을 때 다른 동작 또는 추가 동작을 제공하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-206">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="4b2fc-207">메일 프로그램의 경우에 이것은 새 메일 항목을 받은 편지함에 추가하고 시스템 트레이에 알림 아이콘을 추가하는 작업을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-207">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="4b2fc-208">알림 아이콘은 메일 창이 활성화 되지 않은 경우에만 표시 되어야 합니다 .이는 속성을 검사 하 여 확인할 수 있습니다 <xref:System.Windows.Window.IsActive%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-208">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="4b2fc-209">백그라운드 작업이 완료 되 면 메서드를 호출 하 여 사용자에 게 더 급하게 알림을 보낼 수 있습니다 <xref:System.Windows.Window.Activate%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-209">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="4b2fc-210">사용자가를 호출할 때 활성화 된 다른 응용 프로그램과 상호 작용 하는 경우 <xref:System.Windows.Window.Activate%2A> 창의 작업 표시줄 단추가 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-210">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="4b2fc-211">사용자가 현재 응용 프로그램과 상호 작용 하는 경우를 호출 하면 <xref:System.Windows.Window.Activate%2A> 창이 포그라운드로 전환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-211">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-212">및 이벤트를 사용 하 여 응용 프로그램 범위 활성화를 처리할 수 있습니다 <xref:System.Windows.Application.Activated?displayProperty=nameWithType> <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-212">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a><span data-ttu-id="4b2fc-213">창 닫기</span><span class="sxs-lookup"><span data-stu-id="4b2fc-213">Closing a Window</span></span>  
 <span data-ttu-id="4b2fc-214">창의 수명은 사용자가 창을 닫을 때 끝나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-214">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="4b2fc-215">창은 다음을 포함하여 비클라이언트 영역의 요소를 사용하여 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-215">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
- <span data-ttu-id="4b2fc-216">**시스템** 메뉴의 **닫기** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-216">The **Close** item of the **System** menu.</span></span>  
  
- <span data-ttu-id="4b2fc-217">ALT+F4 누르기.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-217">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="4b2fc-218">**닫기** 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-218">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="4b2fc-219">클라이언트 영역에 창을 닫기 위한 추가적인 메커니즘을 제공할 수 있으며 이 메커니즘에는 일반적으로 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-219">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
- <span data-ttu-id="4b2fc-220">일반적으로 주 응용 프로그램 창에 대 한 **파일** 메뉴의 **종료** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-220">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
- <span data-ttu-id="4b2fc-221">일반적으로 보조 응용 프로그램 창에 있는 **파일** 메뉴의 **닫기** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-221">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
- <span data-ttu-id="4b2fc-222">일반적으로 모달 대화 상자에서 **취소** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-222">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
- <span data-ttu-id="4b2fc-223">일반적으로 모덜리스 대화 상자에 있는 **닫기** 단추</span><span class="sxs-lookup"><span data-stu-id="4b2fc-223">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="4b2fc-224">이러한 사용자 지정 메커니즘 중 하나에 대 한 응답으로 창을 닫으려면 메서드를 호출 해야 <xref:System.Windows.Window.Close%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-224">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="4b2fc-225">다음 예제에서는 **파일** 메뉴에서 **끝내기** 를 선택 하 여 창을 닫는 기능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-225">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="4b2fc-226">창이 닫히면 및의 두 이벤트를 발생 시킵니다. <xref:System.Windows.Window.Closing> <xref:System.Windows.Window.Closed></span><span class="sxs-lookup"><span data-stu-id="4b2fc-226">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="4b2fc-227"><xref:System.Windows.Window.Closing>은 창이 닫히기 전에 발생 하며 창 닫기를 방지할 수 있는 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-227"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="4b2fc-228">대개 창이 닫히면 안 되는 한 가지 이유는 창 콘텐츠에 수정된 데이터가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-228">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="4b2fc-229">이 경우에는 이벤트를 처리 하 여 <xref:System.Windows.Window.Closing> 데이터가 변경 되었는지 여부를 확인 하 고, 데이터를 저장 하지 않고 창을 닫을지 아니면 창 닫기를 취소할지를 사용자에 게 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-229">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="4b2fc-230">다음 예에서는 처리의 주요 측면을 보여 줍니다 <xref:System.Windows.Window.Closing> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-230">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="4b2fc-231">이벤트 처리기에 전달 되는은 <xref:System.Windows.Window.Closing> <xref:System.ComponentModel.CancelEventArgs> `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> `true` 창이 닫히지 않도록 하기 위해 설정 하는 속성을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-231">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="4b2fc-232"><xref:System.Windows.Window.Closing>가 처리 되지 않거나 처리 되었지만 취소 되지 않은 경우 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-232">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="4b2fc-233">창이 실제로 닫히기 직전에 <xref:System.Windows.Window.Closed> 이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-233">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="4b2fc-234">이 시점에서는 창 닫기를 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-234">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-235">주 응용 프로그램 창이 닫히거나 (참조 <xref:System.Windows.Application.MainWindow%2A> ) 마지막 창이 닫히면 응용 프로그램은 자동으로 종료 되도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-235">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="4b2fc-236"> 자세한 내용은 <xref:System.Windows.Application.ShutdownMode%2A>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-236">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="4b2fc-237">비클라이언트 및 클라이언트 영역에서 제공 하는 메커니즘을 통해 창을 명시적으로 닫을 수 있지만, 다음을 포함 하 여 응용 프로그램이 나 창의 다른 부분에서 동작의 결과로 창이 암시적으로 닫힐 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-237">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>  
  
- <span data-ttu-id="4b2fc-238">사용자가 로그 오프 하거나 Windows를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-238">A user logs off or shuts down Windows.</span></span>  
  
- <span data-ttu-id="4b2fc-239">창의 소유자가 닫힙니다 (참조 <xref:System.Windows.Window.Owner%2A> ).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-239">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
- <span data-ttu-id="4b2fc-240">주 응용 프로그램 창이 닫혀 있고 <xref:System.Windows.Application.ShutdownMode%2A> 가입니다 <xref:System.Windows.ShutdownMode.OnMainWindowClose> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-240">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
- <span data-ttu-id="4b2fc-241"><xref:System.Windows.Application.Shutdown%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-241"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-242">창을 닫은 뒤에는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-242">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a><span data-ttu-id="4b2fc-243">창 수명 이벤트</span><span class="sxs-lookup"><span data-stu-id="4b2fc-243">Window Lifetime Events</span></span>  
 <span data-ttu-id="4b2fc-244">다음 그림에서는 창의 수명에서 주 이벤트의 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-244">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![창의 수명으로 이벤트를 표시 하는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="4b2fc-246">다음 그림에서는 활성화 없이 표시 되는 창의 수명에서 주 이벤트의 시퀀스를 보여 줍니다 ( <xref:System.Windows.Window.ShowActivated%2A> `false` 창이 표시 되기 전에로 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-246">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![활성화 하지 않고 창의 수명으로 이벤트를 표시 하는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a><span data-ttu-id="4b2fc-248">창 위치</span><span class="sxs-lookup"><span data-stu-id="4b2fc-248">Window Location</span></span>  
 <span data-ttu-id="4b2fc-249">창은 열릴 때 바탕 화면에 상대적인 x 및 y 크기의 위치를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-249">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="4b2fc-250">이 위치는 <xref:System.Windows.Window.Left%2A> 각각 및 속성을 검사 하 여 확인할 수 있습니다 <xref:System.Windows.Window.Top%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-250">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="4b2fc-251">이 속성을 설정하여 창의 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-251">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="4b2fc-252"><xref:System.Windows.Window> <xref:System.Windows.Window.WindowStartupLocation%2A> 다음 열거형 값 중 하나로 속성을 설정 하 여 처음에 표시 되는의 초기 위치를 지정할 수도 있습니다 <xref:System.Windows.WindowStartupLocation> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-252">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
- <span data-ttu-id="4b2fc-253"><xref:System.Windows.WindowStartupLocation.CenterOwner>(기본값)</span><span class="sxs-lookup"><span data-stu-id="4b2fc-253"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="4b2fc-254">로 시작 위치를 지정 <xref:System.Windows.WindowStartupLocation.Manual> 하 고 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성을 설정 하지 않은 경우에는 <xref:System.Windows.Window> Windows에서에 표시 되는 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-254">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="4b2fc-255">최상위 창 및 Z 순서</span><span class="sxs-lookup"><span data-stu-id="4b2fc-255">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="4b2fc-256">창에는 x 및 y 위치 이외에도 다른 창과 상대적인 수직 위치를 결정하는 z 차원의 위치도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-256">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="4b2fc-257">이를 창의 z 순서라고 하며 여기에는 일반 z 순서와 최상위 z 순서의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-257">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="4b2fc-258">*표준 z 순서* 에서 창의 위치는 현재 활성화 되어 있는지 여부에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-258">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="4b2fc-259">기본적으로 창은 일반 z 순서로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-259">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="4b2fc-260">*위쪽 z 순서* 에서 창의 위치도 현재 활성 상태 인지 여부에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-260">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="4b2fc-261">최상위 z 수준의 창은 항상 일반 z 순서 창의 위에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-261">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="4b2fc-262">창은 해당 속성을로 설정 하 여 맨 위 z 순서에 있습니다 <xref:System.Windows.Window.Topmost%2A> `true` .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-262">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-263">각 z 순서 안에서는 현재 활성화된 창이 같은 z 순서를 가진 다른 모든 창 위에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-263">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>
## <a name="window-size"></a><span data-ttu-id="4b2fc-264">창 크기</span><span class="sxs-lookup"><span data-stu-id="4b2fc-264">Window Size</span></span>  
 <span data-ttu-id="4b2fc-265">데스크톱 위치를 포함 하는 것 외에도 창의 크기는 다양 한 너비 및 높이 속성 및를 포함 하 여 여러 속성에 의해 결정 됩니다 <xref:System.Windows.Window.SizeToContent%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-265">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="4b2fc-266"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 은 창이 수명 동안 포함할 수 있는 너비 범위를 관리 하는 데 사용 되 고 다음 예제와 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-266"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-267">창 높이는 <xref:System.Windows.FrameworkElement.MinHeight%2A> , 및에서 관리 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> 하며 다음 예제와 같이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-267">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-268">다양한 너비 값과 높이 값이 각각 범위를 지정하고 있기 때문에, 크기 조정 가능한 창의 너비와 높이는 지정한 범위 내에서 임의의 크기로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-268">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="4b2fc-269">현재 너비와 높이를 검색 하려면 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 및 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 를 각각 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-269">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="4b2fc-270">창의 너비와 높이를 창 내용의 크기에 맞게 조정 하려는 경우 다음 값을 포함 하는 속성을 사용할 수 있습니다 <xref:System.Windows.Window.SizeToContent%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-270">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
- <span data-ttu-id="4b2fc-271"><xref:System.Windows.SizeToContent.Manual>.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-271"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="4b2fc-272">아무런 영향이 없습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-272">No effect (default).</span></span>  
  
- <span data-ttu-id="4b2fc-273"><xref:System.Windows.SizeToContent.Width>.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-273"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="4b2fc-274">콘텐츠 너비에 맞춥니다. 이러한 효과는 <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 를 콘텐츠 너비와 동일 하 게 설정 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-274">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
- <span data-ttu-id="4b2fc-275"><xref:System.Windows.SizeToContent.Height>.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-275"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="4b2fc-276">콘텐츠 높이에 맞게 및를 콘텐츠의 높이로 설정 하는 것과 동일한 효과를 가집니다 <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-276">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
- <span data-ttu-id="4b2fc-277"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-277"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="4b2fc-278">콘텐츠 너비와 높이에 맞게 <xref:System.Windows.FrameworkElement.MinHeight%2A> 및를 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 콘텐츠의 높이로 설정 하 고 <xref:System.Windows.FrameworkElement.MinWidth%2A> 및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 를 콘텐츠의 너비로 설정 하는 것과 동일한 효과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-278">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="4b2fc-279">다음 예는 창이 처음 표시될 때 콘텐츠에 맞도록 수직 및 수평으로 크기를 자동으로 조정하는 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-279">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-280">다음 예제에서는 코드에서 속성을 설정 하 여 <xref:System.Windows.Window.SizeToContent%2A> 창의 크기가 콘텐츠에 맞게 조정 되는 방법을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-280">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="4b2fc-281">크기 조정 속성에 대한 우선 순위 순서</span><span class="sxs-lookup"><span data-stu-id="4b2fc-281">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="4b2fc-282">기본적으로 창의 다양한 크기 속성이 결합되어 크기 조정 가능한 창의 너비와 높이의 범위가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-282">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="4b2fc-283">유효한 범위가 유지 되도록 하기 위해는 <xref:System.Windows.Window> 다음과 같은 우선 순위 순서를 사용 하 여 size 속성의 값을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-283">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="4b2fc-284">**높이 속성:**</span><span class="sxs-lookup"><span data-stu-id="4b2fc-284">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="4b2fc-285">**너비 속성:**</span><span class="sxs-lookup"><span data-stu-id="4b2fc-285">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="4b2fc-286">우선 순위는 속성으로 관리 되는 최대화 된 창의 크기를 결정할 수도 있습니다 <xref:System.Windows.Window.WindowState%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-286">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>
## <a name="window-state"></a><span data-ttu-id="4b2fc-287">창 상태</span><span class="sxs-lookup"><span data-stu-id="4b2fc-287">Window State</span></span>  
 <span data-ttu-id="4b2fc-288">크기 조정 가능한 창의 수명은 표준, 최소화 및 최대화의 세 가지 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-288">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="4b2fc-289">*표준* 상태의 창은 창의 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-289">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="4b2fc-290">크기 조정 가능 창이 표준 상태인 경우 사용자는 크기 조정 그립이나 테두리를 사용하여 창을 이동하고 크기 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-290">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="4b2fc-291">가로 설정 되어 있으면 *최소화* 된 상태의 창이 작업 표시줄 단추로 축소 <xref:System.Windows.Window.ShowInTaskbar%2A> 되 고, `true` 그렇지 않으면 가능한 가장 작은 크기로 축소 하 고 바탕 화면 왼쪽 아래에 자신을 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-291">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="4b2fc-292">이러한 최소화된 창 유형은 테두리나 크기 조정 그립을 사용하여 크기 조정할 수 없습니다. 하지만 작업 표시줄에 표시되지 않은 최소화된 창은 바탕 화면에서 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-292">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="4b2fc-293">상태가 *최대화* 된 창은 최대 크기 (최대 크기)로 확장 됩니다 <xref:System.Windows.FrameworkElement.MaxWidth%2A> . 즉,, <xref:System.Windows.FrameworkElement.MaxHeight%2A> 및 속성에 따라 크기가 커질 수 있습니다 <xref:System.Windows.Window.SizeToContent%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-293">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="4b2fc-294">최소화된 창과 마찬가지로 최대화된 창은 크기 조정 그립을 사용하거나 테두리를 끌어서 크기 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-294">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4b2fc-295">창의 <xref:System.Windows.Window.Top%2A> ,, <xref:System.Windows.Window.Left%2A> 및 속성 값은 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 창이 현재 최대화 되거나 최소화 된 경우에도 항상 표준 상태 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-295">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="4b2fc-296"><xref:System.Windows.Window.WindowState%2A>다음 열거형 값 중 하나를 가질 수 있는 속성을 설정 하 여 창의 상태를 구성할 수 있습니다 <xref:System.Windows.WindowState> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-296">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
- <span data-ttu-id="4b2fc-297"><xref:System.Windows.WindowState.Normal>(기본값)</span><span class="sxs-lookup"><span data-stu-id="4b2fc-297"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="4b2fc-298">다음 예제에서는 열릴 때 최대화되어 표시되는 창을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-298">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-299">일반적으로를 설정 하 여 <xref:System.Windows.Window.WindowState%2A> 창의 초기 상태를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-299">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="4b2fc-300">크기 조정 가능한 창이 표시되면 사용자는 창의 제목 표시줄에서 최소화, 최대화 및 복원 단추를 눌러 창 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-300">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a><span data-ttu-id="4b2fc-301">창 모양</span><span class="sxs-lookup"><span data-stu-id="4b2fc-301">Window Appearance</span></span>  
 <span data-ttu-id="4b2fc-302">단추, 레이블 및 텍스트 상자와 같은 창 특정 콘텐츠를 창에 추가하여 창의 클라이언트 영역의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-302">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="4b2fc-303">비클라이언트 영역을 구성 하기 위해는 <xref:System.Windows.Window> <xref:System.Windows.Window.Icon%2A> 창의 아이콘을 설정 하 고 제목을 설정 하기 위한 여러 가지 속성을 제공 합니다 <xref:System.Windows.Window.Title%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-303">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="4b2fc-304">또한 창의 크기 조정 모드, 창 스타일 및 바탕 화면 작업 표시줄에 단추로 표시될 것인지 여부를 구성하여 비클라이언트 영역 테두리의 모양과 동작을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-304">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a><span data-ttu-id="4b2fc-305">크기 조정 모드</span><span class="sxs-lookup"><span data-stu-id="4b2fc-305">Resize Mode</span></span>  
 <span data-ttu-id="4b2fc-306">속성에 따라 <xref:System.Windows.Window.WindowStyle%2A> 사용자가 창의 크기를 조정 하는 방법을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-306">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="4b2fc-307">창 스타일 선택은 사용자가 마우스를 사용 하 여 창의 테두리를 끌어 창의 크기를 조정할 수 있는지 여부, **최소화**, **최대화**및 **크기 조정** 단추가 비클라이언트 영역에 표시 되는지 여부, 표시 되는 경우 설정 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-307">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="4b2fc-308"><xref:System.Windows.Window.ResizeMode%2A>다음 열거형 값 중 하나일 수 있는 속성을 설정 하 여 창의 크기를 조정 하는 방법을 구성할 수 있습니다 <xref:System.Windows.ResizeMode> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-308">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <span data-ttu-id="4b2fc-309"><xref:System.Windows.ResizeMode.CanResize>(기본값)</span><span class="sxs-lookup"><span data-stu-id="4b2fc-309"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="4b2fc-310">와 마찬가지로 <xref:System.Windows.Window.WindowStyle%2A> 창의 크기 조정 모드는 수명 중에 변경 될 가능성이 거의 없기 때문에 태그에서 설정 하는 것이 가장 좋습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-310">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-311">속성을 검사 하 여 창이 최대화, 최소화 또는 복원 되는지 여부를 검색할 수 있습니다 <xref:System.Windows.Window.WindowState%2A> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-311">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>
### <a name="window-style"></a><span data-ttu-id="4b2fc-312">창 스타일</span><span class="sxs-lookup"><span data-stu-id="4b2fc-312">Window Style</span></span>  
 <span data-ttu-id="4b2fc-313">창의 비클라이언트 영역에서 노출되는 테두리는 대부분의 애플리케이션에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-313">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="4b2fc-314">하지만 창의 유형에 따라 다른 유형의 테두리가 필요하거나 테두리가 전혀 필요 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-314">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="4b2fc-315">창이 가져오는 테두리 형식을 제어 하려면 <xref:System.Windows.Window.WindowStyle%2A> 열거형의 다음 값 중 하나를 사용 하 여 해당 속성을 설정 합니다 <xref:System.Windows.WindowStyle> .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-315">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <span data-ttu-id="4b2fc-316"><xref:System.Windows.WindowStyle.SingleBorderWindow>(기본값)</span><span class="sxs-lookup"><span data-stu-id="4b2fc-316"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="4b2fc-317">다음 그림에서는 이러한 창 스타일의 효과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-317">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![창 테두리 스타일에 대 한 그림입니다.](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="4b2fc-319"><xref:System.Windows.Window.WindowStyle%2A>태그 또는 코드를 사용 하 여를 설정할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . 창의 수명 중에 변경 될 가능성이 거의 없기 때문에 태그를 사용 하 여 구성 하는 것이 가장 좋습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4b2fc-319">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="4b2fc-320">사각형이 아닌 창 스타일</span><span class="sxs-lookup"><span data-stu-id="4b2fc-320">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="4b2fc-321">뿐만 아니라 테두리 스타일을 <xref:System.Windows.Window.WindowStyle%2A> 사용 해도 충분 하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-321">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="4b2fc-322">예를 들어 Microsoft Windows Media Player에서 사용 하는 것과 같이 사각형이 아닌 테두리를 사용 하 여 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-322">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>  
  
 <span data-ttu-id="4b2fc-323">예를 들어 다음 그림에 표시 된 음성 거품형 창을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-323">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 ![위로 끌기 라는 음성 거품형 창이 표시 됩니다.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="4b2fc-325">속성을로 설정 하 <xref:System.Windows.Window.WindowStyle%2A> <xref:System.Windows.WindowStyle.None> 고 <xref:System.Windows.Window> 투명도에 대 한 특수 지원을 사용 하 여이 유형의 창을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-325">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="4b2fc-326">값을 조합하여 사용하면 창이 완전히 투명하게 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-326">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="4b2fc-327">이 상태에서는 창의 비클라이언트 영역 표시(닫기 메뉴, 최소화, 최대화 및 복원 단추 등)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-327">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="4b2fc-328">따라서 직접 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-328">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a><span data-ttu-id="4b2fc-329">작업 표시줄 표시</span><span class="sxs-lookup"><span data-stu-id="4b2fc-329">Task Bar Presence</span></span>  

<span data-ttu-id="4b2fc-330">창의 기본 모양에는 다음 그림에 표시 된 것과 같은 작업 표시줄 단추가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-330">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![작업 표시줄 단추가 있는 창을 보여 주는 스크린샷](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="4b2fc-332">일부 유형의 창에는 메시지 상자 및 대화 상자와 같은 작업 표시줄 단추가 없습니다 ( [대화 상자 개요](dialog-boxes-overview.md)참조).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-332">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="4b2fc-333">속성을 설정 하 여 창에 대 한 작업 표시줄 단추를 표시할지 여부를 제어할 수 있습니다 <xref:System.Windows.Window.ShowInTaskbar%2A> ( `true` 기본값).</span><span class="sxs-lookup"><span data-stu-id="4b2fc-333">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a><span data-ttu-id="4b2fc-334">보안 고려사항</span><span class="sxs-lookup"><span data-stu-id="4b2fc-334">Security Considerations</span></span>  
 <span data-ttu-id="4b2fc-335"><xref:System.Windows.Window>`UnmanagedCode`인스턴스화할 보안 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-335"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="4b2fc-336">로컬 시스템에 설치되어 실행되는 애플리케이션의 경우에는 애플리케이션에 허용된 권한 집합에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-336">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="4b2fc-337">그러나이는 ClickOnce를 사용 하 여 인터넷 또는 로컬 인트라넷 영역에서 시작 된 응용 프로그램에 부여 된 사용 권한 집합을 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-337">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using ClickOnce.</span></span> <span data-ttu-id="4b2fc-338">따라서 사용자는 ClickOnce 보안 경고를 받게 되며 응용 프로그램에 대 한 권한 집합을 완전 신뢰로 승격 시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-338">Consequently, users will receive a ClickOnce security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="4b2fc-339">또한 Xbap는 기본적으로 창이 나 대화 상자를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-339">Additionally, XBAPs cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="4b2fc-340">독립 실행형 응용 프로그램 보안 고려 사항에 대 한 설명은 [WPF 보안 전략-플랫폼 보안](../wpf-security-strategy-platform-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-340">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a><span data-ttu-id="4b2fc-341">다른 유형의 창</span><span class="sxs-lookup"><span data-stu-id="4b2fc-341">Other Types of Windows</span></span>  
 <span data-ttu-id="4b2fc-342"><xref:System.Windows.Navigation.NavigationWindow>는 탐색 가능한 콘텐츠를 호스트 하도록 설계 된 창입니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-342"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="4b2fc-343">자세한 내용은 [탐색 개요](navigation-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-343">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="4b2fc-344">대화 상자는 기능 수행을 위해 사용자로부터 정보를 수집할 때 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-344">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="4b2fc-345">예를 들어 사용자가 파일을 열려고 할 때 파일 **열기** 대화 상자는 일반적으로 응용 프로그램에서 사용자 로부터 파일 이름을 가져오는 데 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-345">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="4b2fc-346">자세한 내용은 [대화 상자 개요](dialog-boxes-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b2fc-346">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2fc-347">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b2fc-347">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="4b2fc-348">대화 상자 개요</span><span class="sxs-lookup"><span data-stu-id="4b2fc-348">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="4b2fc-349">WPF 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="4b2fc-349">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
