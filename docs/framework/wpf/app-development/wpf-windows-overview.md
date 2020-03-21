---
title: 윈도우 개요
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
ms.openlocfilehash: b06afb56f43a874815cf9f679f1f7fefbdfd4565
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145542"
---
# <a name="wpf-windows-overview"></a><span data-ttu-id="b6b46-102">WPF 창 개요</span><span class="sxs-lookup"><span data-stu-id="b6b46-102">WPF Windows Overview</span></span>
<span data-ttu-id="b6b46-103">사용자는 창을 통해 WPF(Windows 프레젠테이션 기반) 독립 실행형 응용 프로그램과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-103">Users interact with Windows Presentation Foundation (WPF) standalone applications through windows.</span></span> <span data-ttu-id="b6b46-104">창의 기본 용도는 데이터를 시각화하는 콘텐츠를 호스트하고 사용자가 데이터와 상호 작용할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-104">The primary purpose of a window is to host content that visualizes data and enables users to interact with data.</span></span> <span data-ttu-id="b6b46-105">독립 실행형 WPF 응용 프로그램은 클래스를 <xref:System.Windows.Window> 사용하여 자체 창을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-105">Standalone WPF applications provide their own windows by using the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="b6b46-106">이 항목에서는 <xref:System.Windows.Window> 독립 실행형 응용 프로그램에서 창을 만들고 관리하는 기본 을 다루기 전에 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-106">This topic introduces <xref:System.Windows.Window> before covering the fundamentals of creating and managing windows in standalone applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-107">XAML 브라우저 응용 프로그램(XBAPs) 및 느슨한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지를 비롯한 브라우저 호스팅 WPF 응용 프로그램은 자체 창을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-107">Browser-hosted WPF applications, including XAML browser applications (XBAPs) and loose [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] pages, don't provide their own windows.</span></span> <span data-ttu-id="b6b46-108">대신 Windows Internet Explorer에서 제공하는 창에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-108">Instead, they are hosted in windows provided by Windows Internet Explorer.</span></span> <span data-ttu-id="b6b46-109">[WPF XAML 브라우저 응용 프로그램 개요를](wpf-xaml-browser-applications-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-109">See [WPF XAML Browser Applications Overview](wpf-xaml-browser-applications-overview.md).</span></span>  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a><span data-ttu-id="b6b46-110">Window 클래스</span><span class="sxs-lookup"><span data-stu-id="b6b46-110">The Window Class</span></span>  
 <span data-ttu-id="b6b46-111">다음 그림은 창의 구성 부분을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-111">The following figure illustrates the constituent parts of a window:</span></span>  
  
 ![창 요소를 보여 주는 스크린샷입니다.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 <span data-ttu-id="b6b46-113">창은 비클라이언트 영역과 클라이언트 영역의 두 영역으로 나뉩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-113">A window is divided into two areas: the non-client area and client area.</span></span>  
  
 <span data-ttu-id="b6b46-114">창의 *비클라이언트 영역은* WPF에 의해 구현되며 다음을 포함하여 대부분의 창에 공통적인 창 부분을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-114">The *non-client area* of a window is implemented by WPF and includes the parts of a window that are common to most windows, including the following:</span></span>  
  
- <span data-ttu-id="b6b46-115">테두리.</span><span class="sxs-lookup"><span data-stu-id="b6b46-115">A border.</span></span>  
  
- <span data-ttu-id="b6b46-116">제목 표시줄.</span><span class="sxs-lookup"><span data-stu-id="b6b46-116">A title bar.</span></span>  
  
- <span data-ttu-id="b6b46-117">아이콘.</span><span class="sxs-lookup"><span data-stu-id="b6b46-117">An icon.</span></span>  
  
- <span data-ttu-id="b6b46-118">최소화, 최대화 및 복원 단추.</span><span class="sxs-lookup"><span data-stu-id="b6b46-118">Minimize, Maximize, and Restore buttons.</span></span>  
  
- <span data-ttu-id="b6b46-119">닫기 단추.</span><span class="sxs-lookup"><span data-stu-id="b6b46-119">A Close button.</span></span>  
  
- <span data-ttu-id="b6b46-120">사용자가 창을 최소화, 최대화, 복원, 이동, 크기 조정 및 닫을 수 있는 메뉴 항목이 들어 있는 시스템 메뉴.</span><span class="sxs-lookup"><span data-stu-id="b6b46-120">A System menu with menu items that allow users to minimize, maximize, restore, move, resize, and close a window.</span></span>  
  
 <span data-ttu-id="b6b46-121">창의 *클라이언트 영역은* 창의 비클라이언트 영역 내의 영역이며 개발자가 메뉴 모음, 도구 모음 및 컨트롤과 같은 응용 프로그램 별 콘텐츠를 추가하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-121">The *client area* of a window is the area within a window's non-client area and is used by developers to add application-specific content, such as menu bars, tool bars, and controls.</span></span>  
  
 <span data-ttu-id="b6b46-122">WPF에서 창은 다음을 <xref:System.Windows.Window> 수행하는 데 사용하는 클래스로 캡슐화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-122">In WPF, a window is encapsulated by the <xref:System.Windows.Window> class that you use to do the following:</span></span>  
  
- <span data-ttu-id="b6b46-123">창을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-123">Display a window.</span></span>  
  
- <span data-ttu-id="b6b46-124">창의 크기, 위치 및 모양을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-124">Configure the size, position, and appearance of a window.</span></span>  
  
- <span data-ttu-id="b6b46-125">애플리케이션별 콘텐츠를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-125">Host application-specific content.</span></span>  
  
- <span data-ttu-id="b6b46-126">창의 수명을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-126">Manage the lifetime of a window.</span></span>  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a><span data-ttu-id="b6b46-127">창 구현</span><span class="sxs-lookup"><span data-stu-id="b6b46-127">Implementing a Window</span></span>  
 <span data-ttu-id="b6b46-128">일반적인 창의 구현은 모양과 동작으로 구성되며, *여기서 모양은* 창이 사용자에게 보이는 방식을 정의하고 *동작은* 사용자가 윈도우와 상호 작용할 때 창이 작동하는 방식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-128">The implementation of a typical window comprises both appearance and behavior, where *appearance* defines how a window looks to users and *behavior* defines the way a window functions as users interact with it.</span></span> <span data-ttu-id="b6b46-129">WPF에서 코드 또는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그를 사용하여 창의 모양과 동작을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-129">In WPF, you can implement the appearance and behavior of a window using either code or [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 <span data-ttu-id="b6b46-130">그러나 일반적으로 창의 모양은 태그를 사용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 하 여 구현 하 고 해당 동작은 다음 예제와 같이 코드 숨김을 사용 하 여 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-130">In general, however, the appearance of a window is implemented using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and its behavior is implemented using code-behind, as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 <span data-ttu-id="b6b46-131">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 파일과 코드 숨은 파일이 함께 작동하도록 하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-131">To enable a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup file and code-behind file to work together, the following are required:</span></span>  
  
- <span data-ttu-id="b6b46-132">태그에서 `Window` 요소에 특성을 `x:Class` 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-132">In markup, the `Window` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="b6b46-133">응용 프로그램이 빌드될 때 `x:Class` 태그 파일에 있으면 Microsoft 빌드 엔진(MSBuild)이 `partial` <xref:System.Windows.Window> `x:Class` 특성에서 파생되고 특성에 의해 지정된 이름을 포함하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-133">When the application is built, the existence of `x:Class` in the markup file causes Microsoft build engine (MSBuild) to create a `partial` class that derives from <xref:System.Windows.Window> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="b6b46-134">이를 위해서는 스키마()에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` 대한 XML 네임스페이스 선언을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-134">This requires the addition of an XML namespace declaration for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] schema ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ).</span></span> <span data-ttu-id="b6b46-135">생성된 `partial` 클래스는 이벤트를 `InitializeComponent` 등록하고 태그에 구현된 속성을 설정하기 위해 호출되는 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-135">The generated `partial` class implements the `InitializeComponent` method, which is called to register the events and set the properties that are implemented in markup.</span></span>  
  
- <span data-ttu-id="b6b46-136">code-behind에서 클래스는 태그의 `partial` `x:Class` 특성에 의해 지정된 이름이 같은 클래스여야 하며 <xref:System.Windows.Window>에서 파생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-136">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup, and it must derive from <xref:System.Windows.Window>.</span></span> <span data-ttu-id="b6b46-137">이렇게 하면 코드 숨기는 파일을 `partial` 응용 프로그램이 빌드될 때 태그 파일에 대해 생성된 클래스와 연결될 수 있습니다(WPF [응용 프로그램 빌드](building-a-wpf-application-wpf.md)참조).</span><span class="sxs-lookup"><span data-stu-id="b6b46-137">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
- <span data-ttu-id="b6b46-138">코드 숨결에서 <xref:System.Windows.Window> 클래스는 메서드를 호출 하는 `InitializeComponent` 생성자 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-138">In code-behind, the <xref:System.Windows.Window> class must implement a constructor that calls the `InitializeComponent` method.</span></span> <span data-ttu-id="b6b46-139">`InitializeComponent`태그 파일의 생성된 `partial` 클래스에 의해 구현되어 태그를 등록하고 태그에 정의된 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-139">`InitializeComponent` is implemented by the markup file's generated `partial` class to register events and set properties that are defined in markup.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-140">Visual Studio를 <xref:System.Windows.Window> <xref:System.Windows.Window> 사용하여 프로젝트에 새 파일을 추가하는 경우 태그 와 코드 숨결을 모두 사용하여 구현되며 여기에 설명된 태그와 코드 숨는 파일 간의 연결을 만드는 데 필요한 구성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-140">When you add a new <xref:System.Windows.Window> to your project by using Visual Studio, the <xref:System.Windows.Window> is implemented using both markup and code-behind, and includes the necessary configuration to create the association between the markup and code-behind files as described here.</span></span>  
  
 <span data-ttu-id="b6b46-141">이 구성을 사용하면 태그에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창의 모양을 정의하고 코드 숨결에서 해당 동작을 구현하는 데 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-141">With this configuration in place, you can focus on defining the appearance of the window in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and implementing its behavior in code-behind.</span></span> <span data-ttu-id="b6b46-142">다음 예제에서는 태그에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구현된 단추와 코드 숨결로 구현된 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 이벤트 처리기가 있는 창을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-142">The following example shows a window with a button, implemented in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup, and an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, implemented in code-behind.</span></span>  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a><span data-ttu-id="b6b46-143">MSBuild에 대해 창 정의 구성</span><span class="sxs-lookup"><span data-stu-id="b6b46-143">Configuring a Window Definition for MSBuild</span></span>  
 <span data-ttu-id="b6b46-144">창을 구현하는 방법에 따라 MSBuild에 대해 창이 구성되는 방식이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-144">How you implement your window determines how it is configured for MSBuild.</span></span> <span data-ttu-id="b6b46-145">태그와 코드 숨미를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 모두 사용하여 정의된 창의 경우:</span><span class="sxs-lookup"><span data-stu-id="b6b46-145">For a window that is defined using both [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup and code-behind:</span></span>  
  
- <span data-ttu-id="b6b46-146">XAML 태그 파일은 MSBuild `Page` 항목으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-146">XAML markup files are configured as MSBuild `Page` items.</span></span>  
  
- <span data-ttu-id="b6b46-147">코드 숨은 파일은 MSBuild `Compile` 항목으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-147">Code-behind files are configured as MSBuild `Compile` items.</span></span>  
  
 <span data-ttu-id="b6b46-148">이는 다음 MSBuild 프로젝트 파일에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-148">This is shown in the following MSBuild project file.</span></span>  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 <span data-ttu-id="b6b46-149">WPF 응용 프로그램 빌드에 대한 자세한 내용은 [WPF 응용 프로그램 빌드를](building-a-wpf-application-wpf.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-149">For information about building WPF applications, see [Building a WPF Application](building-a-wpf-application-wpf.md).</span></span>  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a><span data-ttu-id="b6b46-150">창 수명</span><span class="sxs-lookup"><span data-stu-id="b6b46-150">Window Lifetime</span></span>  
 <span data-ttu-id="b6b46-151">다른 클래스와 마찬가지로 창에는 창이 열린 후 처음 인스턴스화될 때 시작하여, 열린 후 활성화 및 비활성화되고 최종적으로 닫힐 때까지의 기간인 수명이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-151">As with any class, a window has a lifetime that begins when it is first instantiated, after which it is opened, activated and deactivated, and eventually closed.</span></span>  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a><span data-ttu-id="b6b46-152">창 열기</span><span class="sxs-lookup"><span data-stu-id="b6b46-152">Opening a Window</span></span>  
 <span data-ttu-id="b6b46-153">창을 열려면 먼저 다음 예제에서 설명하는 것처럼 창의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-153">To open a window, you first create an instance of it, which is demonstrated in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 <span data-ttu-id="b6b46-154">이 예제에서는 `MarkupAndCodeBehindWindow` <xref:System.Windows.Application.Startup> 응용 프로그램이 시작될 때 인스턴스화되며 이벤트가 발생할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-154">In this example, the `MarkupAndCodeBehindWindow` is instantiated when the application starts, which occurs when the <xref:System.Windows.Application.Startup> event is raised.</span></span>  
  
 <span data-ttu-id="b6b46-155">창이 인스턴스화되면 <xref:System.Windows.Application> 해당 창에 대한 참조가 개체에서 관리하는 창 목록에 자동으로 추가됩니다(참조). <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b6b46-155">When a window is instantiated, a reference to it is automatically added to a list of windows that is managed by the <xref:System.Windows.Application> object (see <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="b6b46-156">또한 인스턴스화할 첫 번째 창은 기본적으로 기본 응용 <xref:System.Windows.Application> 프로그램 창으로 설정됩니다(참조). <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b6b46-156">Additionally, the first window to be instantiated is, by default, set by <xref:System.Windows.Application> as the main application window (see <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="b6b46-157">메서드를 호출하여 창이 <xref:System.Windows.Window.Show%2A> 마지막으로 열립니다. 결과는 다음 그림에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-157">The window is finally opened by calling the <xref:System.Windows.Window.Show%2A> method; the result is shown in the following figure.</span></span>  
  
 ![창에서 창으로 열립니다.표시](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 <span data-ttu-id="b6b46-159">호출을 <xref:System.Windows.Window.Show%2A> 통해 열리는 창은 모덜리스 창으로, 사용자가 동일한 응용 프로그램에서 다른 창을 활성화할 수 있는 모드에서 응용 프로그램이 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-159">A window that is opened by calling <xref:System.Windows.Window.Show%2A> is a modeless window, which means that the application operates in a mode that allows users to activate other windows in the same application.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-160"><xref:System.Windows.Window.ShowDialog%2A>대화 상자와 같은 창을 열도록 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-160"><xref:System.Windows.Window.ShowDialog%2A> is called to open windows such as dialog boxes modally.</span></span> <span data-ttu-id="b6b46-161">자세한 내용은 [대화 상자 개요를](dialog-boxes-overview.md) 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-161">See [Dialog Boxes Overview](dialog-boxes-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="b6b46-162">호출될 때 <xref:System.Windows.Window.Show%2A> 창은 사용자 입력을 받을 수 있는 인프라를 설정하는 데 표시되기 전에 초기화 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-162">When <xref:System.Windows.Window.Show%2A> is called, a window performs initialization work before it is shown to establish infrastructure that allows it to receive user input.</span></span> <span data-ttu-id="b6b46-163">창이 초기화되면 <xref:System.Windows.Window.SourceInitialized> 이벤트가 발생되고 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-163">When the window is initialized, the <xref:System.Windows.Window.SourceInitialized> event is raised and the window is shown.</span></span>  
  
 <span data-ttu-id="b6b46-164">바로 가기로 <xref:System.Windows.Application.StartupUri%2A> 응용 프로그램이 시작될 때 자동으로 열리는 첫 번째 창을 지정하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-164">As a shortcut, <xref:System.Windows.Application.StartupUri%2A> can be set to specify the first window that is opened automatically when an application starts.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 <span data-ttu-id="b6b46-165">응용 프로그램이 시작되면 값으로 지정된 <xref:System.Windows.Application.StartupUri%2A> 창이 모데없이 열립니다. 내부적으로 창을 호출하여 <xref:System.Windows.Window.Show%2A> 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-165">When the application starts, the window specified by the value of <xref:System.Windows.Application.StartupUri%2A> is opened modelessly; internally, the window is opened by calling its <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a><span data-ttu-id="b6b46-166">창 소유권</span><span class="sxs-lookup"><span data-stu-id="b6b46-166">Window Ownership</span></span>  
 <span data-ttu-id="b6b46-167"><xref:System.Windows.Window.Show%2A> 메서드를 사용하여 열리는 창에는 메서드를 만든 창과 암시적 관계가 없습니다. 사용자는 두 창 중 어느 창도 독립적으로 상호 작용할 수 있으며, 이는 두 창 중 하나가 다음을 수행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-167">A window that is opened by using the <xref:System.Windows.Window.Show%2A> method does not have an implicit relationship with the window that created it; users can interact with either window independently of the other, which means that either window can do the following:</span></span>  
  
- <span data-ttu-id="b6b46-168">다른 창을 덮습니다(창 중 <xref:System.Windows.Window.Topmost%2A> 하나에 속성이 설정되어 있는 `true`경우).</span><span class="sxs-lookup"><span data-stu-id="b6b46-168">Cover the other (unless one of the windows has its <xref:System.Windows.Window.Topmost%2A> property set to `true`).</span></span>  
  
- <span data-ttu-id="b6b46-169">다른 창에 영향을 주지 않고 최소화, 최대화 및 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-169">Be minimized, maximized, and restored without affecting the other.</span></span>  
  
 <span data-ttu-id="b6b46-170">일부 창은 해당 창을 여는 창과의 관계를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-170">Some windows require a relationship with the window that opens them.</span></span> <span data-ttu-id="b6b46-171">예를 들어 IDE(통합 개발 환경) 응용 프로그램은 속성 창을 열고 이를 만드는 창을 덮는 일반적인 동작이 있는 도구 창을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-171">For example, an Integrated Development Environment (IDE) application may open property windows and tool windows whose typical behavior is to cover the window that creates them.</span></span> <span data-ttu-id="b6b46-172">또한 이러한 창은 항상 해당 창을 만든 창과 함께 닫히고, 최소화되고, 최대화되고, 복원되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-172">Furthermore, such windows should always close, minimize, maximize, and restore in concert with the window that created them.</span></span> <span data-ttu-id="b6b46-173">이러한 관계는 한 창을 다른 *창으로* 만들어 설정할 수 <xref:System.Windows.Window.Owner%2A> 있으며 소유자 *창에*대한 참조를 사용하여 *소유한 창의* 속성을 설정하여 달성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-173">Such a relationship can be established by making one window *own* another, and is achieved by setting the <xref:System.Windows.Window.Owner%2A> property of the *owned window* with a reference to the *owner window*.</span></span> <span data-ttu-id="b6b46-174">이는 다음 예에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-174">This is shown in the following example.</span></span>  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 <span data-ttu-id="b6b46-175">소유권이 설정된 후:</span><span class="sxs-lookup"><span data-stu-id="b6b46-175">After ownership is established:</span></span>  
  
- <span data-ttu-id="b6b46-176">소유 된 창은 속성의 값을 검사하여 <xref:System.Windows.Window.Owner%2A> 소유자 창을 참조 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-176">The owned window can reference its owner window by inspecting the value of its <xref:System.Windows.Window.Owner%2A> property.</span></span>  
  
- <span data-ttu-id="b6b46-177">소유자 창은 속성의 값을 검사하여 소유한 모든 <xref:System.Windows.Window.OwnedWindows%2A> 창을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-177">The owner window can discover all the windows it owns by inspecting the value of its <xref:System.Windows.Window.OwnedWindows%2A> property.</span></span>  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a><span data-ttu-id="b6b46-178">창 활성화 방지</span><span class="sxs-lookup"><span data-stu-id="b6b46-178">Preventing Window Activation</span></span>  
 <span data-ttu-id="b6b46-179">인터넷 메신저 스타일 응용 프로그램의 대화 창 또는 전자 메일 응용 프로그램의 알림 창과 같이 표시될 때 창을 활성화하지 않아야 하는 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-179">There are scenarios where windows should not be activated when shown, such as conversation windows of an Internet messenger-style application or notification windows of an email application.</span></span>  
  
 <span data-ttu-id="b6b46-180">응용 프로그램에 표시할 때 활성화되지 않아야 하는 창이 <xref:System.Windows.Window.ShowActivated%2A> 있는 `false` 경우 <xref:System.Windows.Window.Show%2A> 메서드를 처음 호출하기 전에 해당 속성을 설정하여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-180">If your application has a window that shouldn't be activated when shown, you can set its <xref:System.Windows.Window.ShowActivated%2A> property to `false` before calling the <xref:System.Windows.Window.Show%2A> method for the first time.</span></span> <span data-ttu-id="b6b46-181">이렇게 하면 다음과 같은 결과가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-181">As a consequence:</span></span>  
  
- <span data-ttu-id="b6b46-182">창이 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-182">The window is not activated.</span></span>  
  
- <span data-ttu-id="b6b46-183">창의 <xref:System.Windows.Window.Activated> 이벤트가 발생되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-183">The window's <xref:System.Windows.Window.Activated> event is not raised.</span></span>  
  
- <span data-ttu-id="b6b46-184">현재 활성 창이 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-184">The currently activated window remains activated.</span></span>  
  
 <span data-ttu-id="b6b46-185">그러나 사용자가 클라이언트 영역이나 비클라이언트 영역을 클릭하여 창을 활성화하면 해당 창이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-185">The window will become activated, however, as soon as the user activates it by clicking either the client or non-client area.</span></span> <span data-ttu-id="b6b46-186">이 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-186">In this case:</span></span>  
  
- <span data-ttu-id="b6b46-187">창이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-187">The window is activated.</span></span>  
  
- <span data-ttu-id="b6b46-188">창의 <xref:System.Windows.Window.Activated> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-188">The window's <xref:System.Windows.Window.Activated> event is raised.</span></span>  
  
- <span data-ttu-id="b6b46-189">이전에 활성 상태였던 창이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-189">The previously activated window is deactivated.</span></span>  
  
- <span data-ttu-id="b6b46-190"><xref:System.Windows.Window.Deactivated> 창및이벤트는 <xref:System.Windows.Window.Activated> 이후에 사용자 작업에 대한 응답으로 예상대로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-190">The window's <xref:System.Windows.Window.Deactivated> and <xref:System.Windows.Window.Activated> events are subsequently raised as expected in response to user actions.</span></span>  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a><span data-ttu-id="b6b46-191">창 활성화</span><span class="sxs-lookup"><span data-stu-id="b6b46-191">Window Activation</span></span>  
 <span data-ttu-id="b6b46-192">창이 처음 열리면 활성 창이 됩니다(로 설정된 <xref:System.Windows.Window.ShowActivated%2A> 상태로 `false`표시되지 않는 한).</span><span class="sxs-lookup"><span data-stu-id="b6b46-192">When a window is first opened, it becomes the active window (unless it is shown with <xref:System.Windows.Window.ShowActivated%2A> set to `false`).</span></span> <span data-ttu-id="b6b46-193">*활성 창은* 키 스트로크 및 마우스 클릭과 같은 사용자 입력을 현재 캡처하는 창입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-193">The *active window* is the window that is currently capturing user input, such as key strokes and mouse clicks.</span></span> <span data-ttu-id="b6b46-194">창이 활성화되면 이벤트가 발생합니다. <xref:System.Windows.Window.Activated></span><span class="sxs-lookup"><span data-stu-id="b6b46-194">When a window becomes active, it raises the <xref:System.Windows.Window.Activated> event.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-195">창이 처음 열리면 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 <xref:System.Windows.Window.ContentRendered> 발생 후에만 <xref:System.Windows.Window.Activated> 및 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-195">When a window is first opened, the <xref:System.Windows.FrameworkElement.Loaded> and <xref:System.Windows.Window.ContentRendered> events are raised only after the <xref:System.Windows.Window.Activated> event is raised.</span></span> <span data-ttu-id="b6b46-196">이 점을 염두에 두고 창을 발생시 <xref:System.Windows.Window.ContentRendered> 열어 두는 것으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-196">With this in mind, a window can effectively be considered opened when <xref:System.Windows.Window.ContentRendered> is raised.</span></span>  
  
 <span data-ttu-id="b6b46-197">창이 활성 창이 되면 사용자는 같은 애플리케이션의 다른 창을 활성화하거나 다른 애플리케이션을 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-197">After a window becomes active, a user can activate another window in the same application, or activate another application.</span></span> <span data-ttu-id="b6b46-198">이 경우 현재 활성 창이 비활성화되고 <xref:System.Windows.Window.Deactivated> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-198">When that happens, the currently active window becomes deactivated and raises the <xref:System.Windows.Window.Deactivated> event.</span></span> <span data-ttu-id="b6b46-199">마찬가지로 사용자가 현재 비활성화된 창을 선택하면 창이 다시 활성화되고 <xref:System.Windows.Window.Activated> 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-199">Likewise, when the user selects a currently deactivated window, the window becomes active again and <xref:System.Windows.Window.Activated> is raised.</span></span>  
  
 <span data-ttu-id="b6b46-200">처리해야 <xref:System.Windows.Window.Activated> 하는 <xref:System.Windows.Window.Deactivated> 일반적인 이유 중 하나는 창이 활성화되어 있을 때만 실행할 수 있는 기능을 활성화하고 사용하지 않도록 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-200">One common reason to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> is to enable and disable functionality that can only run when a window is active.</span></span> <span data-ttu-id="b6b46-201">예를 들어 일부 창은 게임 및 비디오 플레이어를 포함하여 지속적인 사용자의 입력이나 주의가 필요한 대화식 콘텐츠를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-201">For example, some windows display interactive content that requires constant user input or attention, including games and video players.</span></span> <span data-ttu-id="b6b46-202">다음 예제에서는 이 동작을 처리하고 <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> 구현하는 방법을 보여 주는 간소화된 비디오 플레이어입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-202">The following example is a simplified video player that demonstrates how to handle <xref:System.Windows.Window.Activated> and <xref:System.Windows.Window.Deactivated> to implement this behavior.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 <span data-ttu-id="b6b46-203">다른 형식의 애플리케이션은 창이 비활성화되었을 때 계속 백그라운드에서 코드를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-203">Other types of applications may still run code in the background when a window is deactivated.</span></span> <span data-ttu-id="b6b46-204">예를 들어 메일 클라이언트는 사용자가 다른 애플리케이션을 사용하고 있을 때 메일 서버를 계속 폴링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-204">For example, a mail client may continue polling the mail server while the user is using other applications.</span></span> <span data-ttu-id="b6b46-205">이러한 애플리케이션에는 기본 창이 비활성화되었을 때 다른 동작 또는 추가 동작을 제공하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-205">Applications like these often provide different or additional behavior while the main window is deactivated.</span></span> <span data-ttu-id="b6b46-206">메일 프로그램의 경우에 이것은 새 메일 항목을 받은 편지함에 추가하고 시스템 트레이에 알림 아이콘을 추가하는 작업을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-206">With respect to the mail program, this may mean both adding the new mail item to the inbox and adding a notification icon to the system tray.</span></span> <span data-ttu-id="b6b46-207">알림 아이콘은 메일 창이 활성화되어 있지 않을 때만 표시되며, <xref:System.Windows.Window.IsActive%2A> 이 아이콘은 속성을 검사하여 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-207">A notification icon need only be displayed when the mail window isn't active, which can be determined by inspecting the <xref:System.Windows.Window.IsActive%2A> property.</span></span>  
  
 <span data-ttu-id="b6b46-208">백그라운드 작업이 완료되면 창에서 메서드를 호출하여 <xref:System.Windows.Window.Activate%2A> 사용자에게 더 긴급하게 알릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-208">If a background task completes, a window may want to notify the user more urgently by calling <xref:System.Windows.Window.Activate%2A> method.</span></span> <span data-ttu-id="b6b46-209">사용자가 호출될 때 <xref:System.Windows.Window.Activate%2A> 활성화된 다른 응용 프로그램과 상호 작용하는 경우 창의 작업 표시줄 단추가 깜박입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-209">If the user is interacting with another application activated when <xref:System.Windows.Window.Activate%2A> is called, the window's taskbar button flashes.</span></span> <span data-ttu-id="b6b46-210">사용자가 현재 응용 프로그램과 상호 작용하는 <xref:System.Windows.Window.Activate%2A> 경우 호출하면 창이 포그라운드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-210">If a user is interacting with the current application, calling <xref:System.Windows.Window.Activate%2A> will bring the window to the foreground.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-211"><xref:System.Windows.Application.Activated?displayProperty=nameWithType> 및 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 이벤트를 사용하여 응용 프로그램 범위 활성화를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-211">You can handle application-scope activation using the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> and <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> events.</span></span>  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a><span data-ttu-id="b6b46-212">창 닫기</span><span class="sxs-lookup"><span data-stu-id="b6b46-212">Closing a Window</span></span>  
 <span data-ttu-id="b6b46-213">창의 수명은 사용자가 창을 닫을 때 끝나게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-213">The life of a window starts coming to an end when a user closes it.</span></span> <span data-ttu-id="b6b46-214">창은 다음을 포함하여 비클라이언트 영역의 요소를 사용하여 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-214">A window can be closed by using elements in the non-client area, including the following:</span></span>  
  
- <span data-ttu-id="b6b46-215">**시스템** **닫기** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-215">The **Close** item of the **System** menu.</span></span>  
  
- <span data-ttu-id="b6b46-216">ALT+F4 누르기.</span><span class="sxs-lookup"><span data-stu-id="b6b46-216">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="b6b46-217">**닫기** 버튼을 누른다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-217">Pressing the **Close** button.</span></span>  
  
 <span data-ttu-id="b6b46-218">클라이언트 영역에 창을 닫기 위한 추가적인 메커니즘을 제공할 수 있으며 이 메커니즘에는 일반적으로 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-218">You can provide additional mechanisms to the client area to close a window, the more common of which include the following:</span></span>  
  
- <span data-ttu-id="b6b46-219">일반적으로 기본 응용 프로그램 창에 대한 **파일** 메뉴의 **종료** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-219">An **Exit** item in the **File** menu, typically for main application windows.</span></span>  
  
- <span data-ttu-id="b6b46-220">**파일** 메뉴에서 일반적으로 보조 응용 프로그램 창에서 **닫기** 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-220">A **Close** item in the **File** menu, typically on a secondary application window.</span></span>  
  
- <span data-ttu-id="b6b46-221">일반적으로 모달 대화 상자의 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-221">A **Cancel** button, typically on a modal dialog box.</span></span>  
  
- <span data-ttu-id="b6b46-222">일반적으로 모덜리스 대화 상자에서 **닫기** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-222">A **Close** button, typically on a modeless dialog box.</span></span>  
  
 <span data-ttu-id="b6b46-223">이러한 사용자 지정 메커니즘 중 하나에 대한 응답으로 창을 닫려면 메서드를 <xref:System.Windows.Window.Close%2A> 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-223">To close a window in response to one of these custom mechanisms, you need to call the <xref:System.Windows.Window.Close%2A> method.</span></span> <span data-ttu-id="b6b46-224">다음 예제는 **파일** 메뉴에서 **종료를** 선택하여 창을 닫는 기능을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-224">The following example implements the ability to close a window by choosing the **Exit** on the **File** menu.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 <span data-ttu-id="b6b46-225">창이 닫히면 두 개의 <xref:System.Windows.Window.Closing> 이벤트가 <xref:System.Windows.Window.Closed>발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-225">When a window closes, it raises two events: <xref:System.Windows.Window.Closing> and <xref:System.Windows.Window.Closed>.</span></span>  
  
 <span data-ttu-id="b6b46-226"><xref:System.Windows.Window.Closing>창이 닫히기 전에 발생하며 창 닫을 방지할 수 있는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-226"><xref:System.Windows.Window.Closing> is raised before the window closes, and it provides a mechanism by which window closure can be prevented.</span></span> <span data-ttu-id="b6b46-227">대개 창이 닫히면 안 되는 한 가지 이유는 창 콘텐츠에 수정된 데이터가 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-227">One common reason to prevent window closure is if window content contains modified data.</span></span> <span data-ttu-id="b6b46-228">이 경우 <xref:System.Windows.Window.Closing> 이벤트를 처리하여 데이터가 더러워졌는지 확인하고, 데이터가 더러워지는 경우 사용자에게 데이터를 저장하지 않고 창을 계속 닫을지 또는 창 닫기를 취소할지 물어볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-228">In this situation, the <xref:System.Windows.Window.Closing> event can be handled to determine whether data is dirty and, if so, to ask the user whether to either continue closing the window without saving the data or to cancel window closure.</span></span> <span data-ttu-id="b6b46-229">다음 예제에서는 처리의 <xref:System.Windows.Window.Closing>주요 측면을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-229">The following example shows the key aspects of handling <xref:System.Windows.Window.Closing>.</span></span>  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <span data-ttu-id="b6b46-230"><xref:System.Windows.Window.Closing> 이벤트 처리기는 <xref:System.ComponentModel.CancelEventArgs>창이 닫히지 않도록 `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 설정한 `true` 속성을 구현하는 를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-230">The <xref:System.Windows.Window.Closing> event handler is passed a <xref:System.ComponentModel.CancelEventArgs>, which implements the `Boolean`<xref:System.ComponentModel.CancelEventArgs.Cancel%2A> property that you set to `true` to prevent a window from closing.</span></span>  
  
 <span data-ttu-id="b6b46-231"><xref:System.Windows.Window.Closing> 처리되지 않거나 처리되었지만 취소되지 않으면 창이 닫힙됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-231">If <xref:System.Windows.Window.Closing> is not handled, or it is handled but not canceled, the window will close.</span></span> <span data-ttu-id="b6b46-232">창이 실제로 닫히기 <xref:System.Windows.Window.Closed> 직전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-232">Just before a window actually closes, <xref:System.Windows.Window.Closed> is raised.</span></span> <span data-ttu-id="b6b46-233">이 시점에서는 창 닫기를 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-233">At this point, a window cannot be prevented from closing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-234">주 응용 프로그램 창이 닫히거나 마지막 창이 닫히면 <xref:System.Windows.Application.MainWindow%2A>응용 프로그램을 자동으로 종료하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-234">An application can be configured to shut down automatically when either the main application window closes (see <xref:System.Windows.Application.MainWindow%2A>) or the last window closes.</span></span> <span data-ttu-id="b6b46-235"> 자세한 내용은 <xref:System.Windows.Application.ShutdownMode%2A>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-235">For details, see <xref:System.Windows.Application.ShutdownMode%2A>.</span></span>  
  
 <span data-ttu-id="b6b46-236">비 클라이언트 및 클라이언트 영역에서 제공되는 메커니즘을 통해 창을 명시적으로 닫을 수 있지만 다음을 포함하여 응용 프로그램 또는 Windows의 다른 부분에서 의한 동작으로 인해 창을 암시적으로 닫을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-236">While a window can be explicitly closed through mechanisms provided in the non-client and client areas, a window can also be implicitly closed as a result of behavior in other parts of the application or Windows, including the following:</span></span>  
  
- <span data-ttu-id="b6b46-237">사용자가 Windows를 로그오프하거나 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-237">A user logs off or shuts down Windows.</span></span>  
  
- <span data-ttu-id="b6b46-238">창의 소유자가 닫힙니다(참조). <xref:System.Windows.Window.Owner%2A></span><span class="sxs-lookup"><span data-stu-id="b6b46-238">A window's owner closes (see <xref:System.Windows.Window.Owner%2A>).</span></span>  
  
- <span data-ttu-id="b6b46-239">기본 응용 프로그램 창이 <xref:System.Windows.ShutdownMode.OnMainWindowClose>닫혀 있습니다. <xref:System.Windows.Application.ShutdownMode%2A></span><span class="sxs-lookup"><span data-stu-id="b6b46-239">The main application window is closed and <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
- <span data-ttu-id="b6b46-240"><xref:System.Windows.Application.Shutdown%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-240"><xref:System.Windows.Application.Shutdown%2A> is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-241">창을 닫은 뒤에는 다시 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-241">A window cannot be reopened after it is closed.</span></span>  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a><span data-ttu-id="b6b46-242">창 수명 이벤트</span><span class="sxs-lookup"><span data-stu-id="b6b46-242">Window Lifetime Events</span></span>  
 <span data-ttu-id="b6b46-243">다음 그림에서는 창의 수명 동안 주 이벤트의 시퀀스를 보여 주입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-243">The following illustration shows the sequence of the principal events in the lifetime of a window:</span></span>  
  
 ![창의 수명 동안의 이벤트를 보여 주는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 <span data-ttu-id="b6b46-245">다음 그림에서는 활성화 없이 표시되는 창의 수명 동안 주 이벤트의<xref:System.Windows.Window.ShowActivated%2A> 시퀀스를 보여 주입니다(창이 표시되기 `false` 전에 설정됨).</span><span class="sxs-lookup"><span data-stu-id="b6b46-245">The following illustration shows the sequence of the principal events in the lifetime of a window that is shown without activation (<xref:System.Windows.Window.ShowActivated%2A> is set to `false` before the window is shown):</span></span>  
  
 ![활성화하지 않고 창의 수명에 있는 이벤트를 보여 주는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a><span data-ttu-id="b6b46-247">창 위치</span><span class="sxs-lookup"><span data-stu-id="b6b46-247">Window Location</span></span>  
 <span data-ttu-id="b6b46-248">창은 열릴 때 바탕 화면에 상대적인 x 및 y 크기의 위치를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-248">While a window is open, it has a location in the x and y dimensions relative to the desktop.</span></span> <span data-ttu-id="b6b46-249">이 위치는 각각 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 특성을 검사하여 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-249">This location can be determined by inspecting the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties, respectively.</span></span> <span data-ttu-id="b6b46-250">이 속성을 설정하여 창의 위치를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-250">You can set these properties to change the location of the window.</span></span>  
  
 <span data-ttu-id="b6b46-251">다음 <xref:System.Windows.WindowStartupLocation> 열거값 중 하나로 <xref:System.Windows.Window> <xref:System.Windows.Window.WindowStartupLocation%2A> 속성을 설정하여 a의 초기 위치를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-251">You can also specify the initial location of a <xref:System.Windows.Window> when it first appears by setting the <xref:System.Windows.Window.WindowStartupLocation%2A> property with one of the following <xref:System.Windows.WindowStartupLocation> enumeration values:</span></span>  
  
- <span data-ttu-id="b6b46-252"><xref:System.Windows.WindowStartupLocation.CenterOwner>(기본값)</span><span class="sxs-lookup"><span data-stu-id="b6b46-252"><xref:System.Windows.WindowStartupLocation.CenterOwner> (default)</span></span>  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 <span data-ttu-id="b6b46-253">시작 <xref:System.Windows.WindowStartupLocation.Manual>위치가 로 지정되고 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성이 설정되지 <xref:System.Windows.Window> 않은 경우 Windows에 위치가 표시되도록 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-253">If the startup location is specified as <xref:System.Windows.WindowStartupLocation.Manual>, and the <xref:System.Windows.Window.Left%2A> and <xref:System.Windows.Window.Top%2A> properties have not been set, <xref:System.Windows.Window> will ask Windows for a location to appear in.</span></span>  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a><span data-ttu-id="b6b46-254">최상위 창 및 Z 순서</span><span class="sxs-lookup"><span data-stu-id="b6b46-254">Topmost Windows and Z-Order</span></span>  
 <span data-ttu-id="b6b46-255">창에는 x 및 y 위치 이외에도 다른 창과 상대적인 수직 위치를 결정하는 z 차원의 위치도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-255">Besides having an x and y location, a window also has a location in the z dimension, which determines its vertical position with respect to other windows.</span></span> <span data-ttu-id="b6b46-256">이를 창의 z 순서라고 하며 여기에는 일반 z 순서와 최상위 z 순서의 두 가지 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-256">This is known as the window's z-order, and there are two types: normal z-order and topmost z-order.</span></span> <span data-ttu-id="b6b46-257">*일반 z-순서의* 창 위치는 현재 활성 상태인지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-257">The location of a window in the *normal z-order* is determined by whether it is currently active or not.</span></span> <span data-ttu-id="b6b46-258">기본적으로 창은 일반 z 순서로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-258">By default, a window is located in the normal z-order.</span></span> <span data-ttu-id="b6b46-259">*최상위 z-order의* 창 위치는 현재 활성 상태인지 여부에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-259">The location of a window in the *topmost z-order* is also determined by whether it is currently active or not.</span></span> <span data-ttu-id="b6b46-260">최상위 z 수준의 창은 항상 일반 z 순서 창의 위에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-260">Furthermore, windows in the topmost z-order are always located above windows in the normal z-order.</span></span> <span data-ttu-id="b6b46-261">창은 <xref:System.Windows.Window.Topmost%2A> 속성을 로 설정하여 최상위 z 순서에 `true`있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-261">A window is located in the topmost z-order by setting its <xref:System.Windows.Window.Topmost%2A> property to `true`.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 <span data-ttu-id="b6b46-262">각 z 순서 안에서는 현재 활성화된 창이 같은 z 순서를 가진 다른 모든 창 위에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-262">Within each z-order, the currently active window appears above all other windows in the same z-order.</span></span>  
  
<a name="WindowSize"></a>
## <a name="window-size"></a><span data-ttu-id="b6b46-263">창 크기</span><span class="sxs-lookup"><span data-stu-id="b6b46-263">Window Size</span></span>  
 <span data-ttu-id="b6b46-264">데스크톱 위치 외에도 창에는 다양한 너비 및 높이 속성 및 <xref:System.Windows.Window.SizeToContent%2A>.</span><span class="sxs-lookup"><span data-stu-id="b6b46-264">Besides having a desktop location, a window has a size that is determined by several properties, including the various width and height properties and <xref:System.Windows.Window.SizeToContent%2A>.</span></span>  
  
 <span data-ttu-id="b6b46-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>s은 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> 창이 수명 동안 가질 수 있는 너비 범위를 관리하는 데 사용되며 다음 예제와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-265"><xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.MaxWidth%2A> are used to manage the range of widths that a window can have during its lifetime, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 <span data-ttu-id="b6b46-266">창 높이는 <xref:System.Windows.FrameworkElement.MinHeight%2A>에서 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>관리되며 다음 예제와 같이 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-266">Window height is managed by <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and are configured as shown in the following example.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 <span data-ttu-id="b6b46-267">다양한 너비 값과 높이 값이 각각 범위를 지정하고 있기 때문에, 크기 조정 가능한 창의 너비와 높이는 지정한 범위 내에서 임의의 크기로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-267">Because the various width values and height values each specify a range, it is possible for the width and height of a resizable window to be anywhere within the specified range for the respective dimension.</span></span> <span data-ttu-id="b6b46-268">현재 너비와 높이를 감지하려면 <xref:System.Windows.FrameworkElement.ActualHeight%2A>각각 검사하고 <xref:System.Windows.FrameworkElement.ActualWidth%2A></span><span class="sxs-lookup"><span data-stu-id="b6b46-268">To detect its current width and height, inspect <xref:System.Windows.FrameworkElement.ActualWidth%2A> and <xref:System.Windows.FrameworkElement.ActualHeight%2A>, respectively.</span></span>  
  
 <span data-ttu-id="b6b46-269">창의 너비와 높이를 창 내용의 크기에 맞는 크기를 지정하려면 다음 값을 가진 <xref:System.Windows.Window.SizeToContent%2A> 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-269">If you'd like the width and height of your window to have a size that fits to the size of the window's content, you can use the <xref:System.Windows.Window.SizeToContent%2A> property, which has the following values:</span></span>  
  
- <span data-ttu-id="b6b46-270"><xref:System.Windows.SizeToContent.Manual>.</span><span class="sxs-lookup"><span data-stu-id="b6b46-270"><xref:System.Windows.SizeToContent.Manual>.</span></span> <span data-ttu-id="b6b46-271">아무런 영향이 없습니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="b6b46-271">No effect (default).</span></span>  
  
- <span data-ttu-id="b6b46-272"><xref:System.Windows.SizeToContent.Width>.</span><span class="sxs-lookup"><span data-stu-id="b6b46-272"><xref:System.Windows.SizeToContent.Width>.</span></span> <span data-ttu-id="b6b46-273">콘텐츠 너비와 둘 다 <xref:System.Windows.FrameworkElement.MinWidth%2A> 설정및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 콘텐츠 너비와 동일한 효과가 있는 콘텐츠 너비에 맞춥습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-273">Fit to content width, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
- <span data-ttu-id="b6b46-274"><xref:System.Windows.SizeToContent.Height>.</span><span class="sxs-lookup"><span data-stu-id="b6b46-274"><xref:System.Windows.SizeToContent.Height>.</span></span> <span data-ttu-id="b6b46-275">콘텐츠 높이에 맞게 <xref:System.Windows.FrameworkElement.MinHeight%2A> 설정및 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 콘텐츠 높이와 동일한 효과를 가짐입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-275">Fit to content height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content.</span></span>  
  
- <span data-ttu-id="b6b46-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span><span class="sxs-lookup"><span data-stu-id="b6b46-276"><xref:System.Windows.SizeToContent.WidthAndHeight>.</span></span> <span data-ttu-id="b6b46-277">콘텐츠 너비와 높이에 맞게 콘텐츠의 높이와 <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> 둘 다 설정 및 콘텐츠 <xref:System.Windows.FrameworkElement.MinWidth%2A> 의 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 너비를 설정하는 것과 동일한 효과를 내립니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-277">Fit to content width and height, which has the same effect as setting both <xref:System.Windows.FrameworkElement.MinHeight%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> to the height of the content, and setting both <xref:System.Windows.FrameworkElement.MinWidth%2A> and <xref:System.Windows.FrameworkElement.MaxWidth%2A> to the width of the content.</span></span>  
  
 <span data-ttu-id="b6b46-278">다음 예는 창이 처음 표시될 때 콘텐츠에 맞도록 수직 및 수평으로 크기를 자동으로 조정하는 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-278">The following example shows a window that automatically sizes to fit its content, both vertically and horizontally, when first shown.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 <span data-ttu-id="b6b46-279">다음 예제에서는 코드에서 <xref:System.Windows.Window.SizeToContent%2A> 속성을 설정하여 창의 내용에 맞게 창 크기를 조정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-279">The following example shows how to set the <xref:System.Windows.Window.SizeToContent%2A> property in code to specify how a window resizes to fit its content    .</span></span>
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a><span data-ttu-id="b6b46-280">크기 조정 속성에 대한 우선 순위 순서</span><span class="sxs-lookup"><span data-stu-id="b6b46-280">Order of Precedence for Sizing Properties</span></span>  
 <span data-ttu-id="b6b46-281">기본적으로 창의 다양한 크기 속성이 결합되어 크기 조정 가능한 창의 너비와 높이의 범위가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-281">Essentially, the various sizes properties of a window combine to define the range of width and height for a resizable window.</span></span> <span data-ttu-id="b6b46-282">유효한 범위가 유지되도록 하려면 <xref:System.Windows.Window> 다음 우선 순위를 사용하여 크기 속성의 값을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-282">To ensure a valid range is maintained, <xref:System.Windows.Window> evaluates the values of the size properties using the following orders of precedence.</span></span>  
  
 <span data-ttu-id="b6b46-283">**높이 속성:**</span><span class="sxs-lookup"><span data-stu-id="b6b46-283">**For Height Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="b6b46-284">**너비 속성:**</span><span class="sxs-lookup"><span data-stu-id="b6b46-284">**For Width Properties:**</span></span>  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="b6b46-285">우선 순위는 <xref:System.Windows.Window.WindowState%2A> 속성으로 관리되는 창이 최대화될 때 의 크기를 결정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-285">The order of precedence can also determine the size of a window when it is maximized, which is managed with the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="WindowState"></a>
## <a name="window-state"></a><span data-ttu-id="b6b46-286">창 상태</span><span class="sxs-lookup"><span data-stu-id="b6b46-286">Window State</span></span>  
 <span data-ttu-id="b6b46-287">크기 조정 가능한 창의 수명은 표준, 최소화 및 최대화의 세 가지 상태를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-287">During the lifetime of a resizable window, it can have three states: normal, minimized, and maximized.</span></span> <span data-ttu-id="b6b46-288">*정상* 상태가 있는 창은 창의 기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-288">A window with a *normal* state is the default state of a window.</span></span> <span data-ttu-id="b6b46-289">크기 조정 가능 창이 표준 상태인 경우 사용자는 크기 조정 그립이나 테두리를 사용하여 창을 이동하고 크기 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-289">A window with this state allows a user to move and resize it by using a resize grip or the border, if it is resizable.</span></span>  
  
 <span data-ttu-id="b6b46-290">로 설정된 경우 <xref:System.Windows.Window.ShowInTaskbar%2A> *최소화된* 상태의 창이 작업 표시줄 `true`단추로 축소됩니다. 그렇지 않으면 가능한 가장 작은 크기로 축소되고 바탕 화면의 왼쪽 아래 모서리로 재배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-290">A window with a *minimized* state collapses to its task bar button if <xref:System.Windows.Window.ShowInTaskbar%2A> is set to `true`; otherwise, it collapses to the smallest possible size it can be and relocates itself to the bottom-left corner of the desktop.</span></span> <span data-ttu-id="b6b46-291">이러한 최소화된 창 유형은 테두리나 크기 조정 그립을 사용하여 크기 조정할 수 없습니다. 하지만 작업 표시줄에 표시되지 않은 최소화된 창은 바탕 화면에서 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-291">Neither type of minimized window can be resized using a border or resize grip, although a minimized window that isn't shown in the task bar can be dragged around the desktop.</span></span>  
  
 <span data-ttu-id="b6b46-292">*최대화 된* 상태의 창은 할 수있는 최대 크기로 확장되며 , 이는 <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>의 <xref:System.Windows.Window.SizeToContent%2A> 및 속성이 받아쓰기하는 크기만큼 커질 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-292">A window with a *maximized* state expands to the maximum size it can be, which will only be as large as its <xref:System.Windows.FrameworkElement.MaxWidth%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.Window.SizeToContent%2A> properties dictate.</span></span> <span data-ttu-id="b6b46-293">최소화된 창과 마찬가지로 최대화된 창은 크기 조정 그립을 사용하거나 테두리를 끌어서 크기 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-293">Like a minimized window, a maximized window cannot be resized by using a resize grip or by dragging the border.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6b46-294">의 <xref:System.Windows.Window.Top%2A>값은 <xref:System.Windows.Window.Left%2A>의 <xref:System.Windows.FrameworkElement.Width%2A>값입니다 . <xref:System.Windows.FrameworkElement.Height%2A></span><span class="sxs-lookup"><span data-stu-id="b6b46-294">The values of the <xref:System.Windows.Window.Top%2A>, <xref:System.Windows.Window.Left%2A>, <xref:System.Windows.FrameworkElement.Width%2A>, and <xref:System.Windows.FrameworkElement.Height%2A> properties of a window always represent the values for the normal state, even when the window is currently maximized or minimized.</span></span>  
  
 <span data-ttu-id="b6b46-295">창의 상태는 다음 <xref:System.Windows.Window.WindowState%2A> <xref:System.Windows.WindowState> 열거 값 중 하나를 가질 수 있는 속성을 설정하여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-295">The state of a window can be configured by setting its <xref:System.Windows.Window.WindowState%2A> property, which can have one of the following <xref:System.Windows.WindowState> enumeration values:</span></span>  
  
- <span data-ttu-id="b6b46-296"><xref:System.Windows.WindowState.Normal>(기본값)</span><span class="sxs-lookup"><span data-stu-id="b6b46-296"><xref:System.Windows.WindowState.Normal> (default)</span></span>  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 <span data-ttu-id="b6b46-297">다음 예제에서는 열릴 때 최대화되어 표시되는 창을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-297">The following example shows how to create a window that is shown as maximized when it opens.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 <span data-ttu-id="b6b46-298">일반적으로 창의 초기 <xref:System.Windows.Window.WindowState%2A> 상태를 구성하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-298">In general, you should set <xref:System.Windows.Window.WindowState%2A> to configure the initial state of a window.</span></span> <span data-ttu-id="b6b46-299">크기 조정 가능한 창이 표시되면 사용자는 창의 제목 표시줄에서 최소화, 최대화 및 복원 단추를 눌러 창 상태를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-299">Once a resizable window is shown, users can press the minimize, maximize, and restore buttons on the window's title bar to change the window state.</span></span>  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a><span data-ttu-id="b6b46-300">창 모양</span><span class="sxs-lookup"><span data-stu-id="b6b46-300">Window Appearance</span></span>  
 <span data-ttu-id="b6b46-301">단추, 레이블 및 텍스트 상자와 같은 창 특정 콘텐츠를 창에 추가하여 창의 클라이언트 영역의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-301">You change the appearance of the client area of a window by adding window-specific content to it, such as buttons, labels, and text boxes.</span></span> <span data-ttu-id="b6b46-302">클라이언트가 아닌 영역을 <xref:System.Windows.Window> 구성하려면 창아이콘을 <xref:System.Windows.Window.Icon%2A> 설정하고 <xref:System.Windows.Window.Title%2A> 제목을 설정하는 등 여러 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-302">To configure the non-client area, <xref:System.Windows.Window> provides several properties, which include <xref:System.Windows.Window.Icon%2A> to set a window's icon and <xref:System.Windows.Window.Title%2A> to set its title.</span></span>  
  
 <span data-ttu-id="b6b46-303">또한 창의 크기 조정 모드, 창 스타일 및 바탕 화면 작업 표시줄에 단추로 표시될 것인지 여부를 구성하여 비클라이언트 영역 테두리의 모양과 동작을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-303">You can also change the appearance and behavior of non-client area border by configuring a window's resize mode, window style, and whether it appears as a button in the desktop task bar.</span></span>  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a><span data-ttu-id="b6b46-304">크기 조정 모드</span><span class="sxs-lookup"><span data-stu-id="b6b46-304">Resize Mode</span></span>  
 <span data-ttu-id="b6b46-305">속성에 <xref:System.Windows.Window.WindowStyle%2A> 따라 사용자가 창 크기를 조정할 수 있는 방법(및 if)을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-305">Depending on the <xref:System.Windows.Window.WindowStyle%2A> property, you can control how (and if) users can resize the window.</span></span> <span data-ttu-id="b6b46-306">창 스타일을 선택하면 사용자가 마우스로 테두리를 드래그하여 창 크기를 조정할 수 있는지 여부, **클라이언트가**아닌 영역에 최소화, **최대화**및 **크기 조정** 단추가 나타나는지 여부, 창이 활성화되어 있는지 여부에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-306">The choice of window style affects whether a user can resize the window by dragging its border with the mouse, whether the **Minimize**, **Maximize**, and **Resize** buttons appear on the non-client area, and, if they do appear, whether they are enabled.</span></span>  
  
 <span data-ttu-id="b6b46-307">다음 <xref:System.Windows.ResizeMode> 열거 값 중 하나가 될 <xref:System.Windows.Window.ResizeMode%2A> 수 있는 해당 속성을 설정하여 창 크기를 조정하는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-307">You can configure how a window resizes by setting its <xref:System.Windows.Window.ResizeMode%2A> property, which can be one of the following <xref:System.Windows.ResizeMode> enumeration values:</span></span>  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <span data-ttu-id="b6b46-308"><xref:System.Windows.ResizeMode.CanResize>(기본값)</span><span class="sxs-lookup"><span data-stu-id="b6b46-308"><xref:System.Windows.ResizeMode.CanResize> (default)</span></span>  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 <span data-ttu-id="b6b46-309">마찬가지로 <xref:System.Windows.Window.WindowStyle%2A>창의 크기 조정 모드는 수명 동안 변경될 가능성이 낮으므로 태그에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창으로 설정할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-309">As with <xref:System.Windows.Window.WindowStyle%2A>, the resize mode of a window is unlikely to change during its lifetime, which means that you'll most likely set it from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 <span data-ttu-id="b6b46-310">속성을 검사하여 창을 최대화, 최소화 또는 복원하는지 여부를 검색할 <xref:System.Windows.Window.WindowState%2A> 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-310">Note that you can detect whether a window is maximized, minimized, or restored by inspecting the <xref:System.Windows.Window.WindowState%2A> property.</span></span>  
  
<a name="Window_Style"></a>
### <a name="window-style"></a><span data-ttu-id="b6b46-311">창 스타일</span><span class="sxs-lookup"><span data-stu-id="b6b46-311">Window Style</span></span>  
 <span data-ttu-id="b6b46-312">창의 비클라이언트 영역에서 노출되는 테두리는 대부분의 애플리케이션에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-312">The border that is exposed from the non-client area of a window is suitable for most applications.</span></span> <span data-ttu-id="b6b46-313">하지만 창의 유형에 따라 다른 유형의 테두리가 필요하거나 테두리가 전혀 필요 없는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-313">However, there are circumstances where different types of borders are needed, or no borders are needed at all, depending on the type of window.</span></span>  
  
 <span data-ttu-id="b6b46-314">창이 받는 테두리 유형을 제어하려면 <xref:System.Windows.Window.WindowStyle%2A> <xref:System.Windows.WindowStyle> 열거형의 다음 값 중 하나로 해당 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-314">To control what type of border a window gets, you set its <xref:System.Windows.Window.WindowStyle%2A> property with one of the following values of the <xref:System.Windows.WindowStyle> enumeration:</span></span>  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <span data-ttu-id="b6b46-315"><xref:System.Windows.WindowStyle.SingleBorderWindow>(기본값)</span><span class="sxs-lookup"><span data-stu-id="b6b46-315"><xref:System.Windows.WindowStyle.SingleBorderWindow> (default)</span></span>  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 <span data-ttu-id="b6b46-316">이러한 창 스타일의 효과는 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-316">The effect of these window styles are illustrated in the following figure:</span></span>  
  
 ![창 테두리 스타일의 그림입니다.](./media/wpf-windows-overview/window-border-styles.png)  
  
 <span data-ttu-id="b6b46-318">태그 또는 <xref:System.Windows.Window.WindowStyle%2A> 코드를 사용하여 설정할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창의 수명 동안 변경될 가능성이 낮으므로 태그를 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구성할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-318">You can set <xref:System.Windows.Window.WindowStyle%2A> using either [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup or code; because it is unlikely to change during the lifetime of a window, you will most likely configure it using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] markup.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a><span data-ttu-id="b6b46-319">사각형이 아닌 창 스타일</span><span class="sxs-lookup"><span data-stu-id="b6b46-319">Non-Rectangular Window Style</span></span>  
 <span data-ttu-id="b6b46-320">테두리 스타일이 <xref:System.Windows.Window.WindowStyle%2A> 충분하지 않은 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-320">There are also situations where the border styles that <xref:System.Windows.Window.WindowStyle%2A> allows you to have are not sufficient.</span></span> <span data-ttu-id="b6b46-321">예를 들어 Microsoft Windows 미디어 플레이어에서 사용하는 것과 같이 직사각형이 아닌 테두리가 있는 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-321">For example, you may want to create an application with a non-rectangular border, like Microsoft Windows Media Player uses.</span></span>  
  
 <span data-ttu-id="b6b46-322">예를 들어 다음 그림에 표시된 음성 거품 창을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-322">For example, consider the speech bubble window shown in the following figure:</span></span>  
  
 ![나를 드래그 말한다 음성 거품 창.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 <span data-ttu-id="b6b46-324">이러한 유형의 창은 <xref:System.Windows.Window.WindowStyle%2A> 속성을 <xref:System.Windows.WindowStyle.None>로 설정하고 투명도가 있는 <xref:System.Windows.Window> 특수 지원을 사용하여 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-324">This type of window can be created by setting the <xref:System.Windows.Window.WindowStyle%2A> property to <xref:System.Windows.WindowStyle.None>, and by using special support that <xref:System.Windows.Window> has for transparency.</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 <span data-ttu-id="b6b46-325">값을 조합하여 사용하면 창이 완전히 투명하게 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-325">This combination of values instructs the window to render completely transparent.</span></span> <span data-ttu-id="b6b46-326">이 상태에서는 창의 비클라이언트 영역 표시(닫기 메뉴, 최소화, 최대화 및 복원 단추 등)를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-326">In this state, the window's non-client area adornments (the Close menu, Minimize, Maximize, and Restore buttons, and so on) cannot be used.</span></span> <span data-ttu-id="b6b46-327">따라서 직접 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-327">Consequently, you need to provide your own.</span></span>  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a><span data-ttu-id="b6b46-328">작업 표시줄 표시</span><span class="sxs-lookup"><span data-stu-id="b6b46-328">Task Bar Presence</span></span>  

<span data-ttu-id="b6b46-329">창의 기본 모양에는 다음 그림에 표시된 것과 같은 작업 표시줄 단추가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-329">The default appearance of a window includes a taskbar button, like the one shown in the following figure:</span></span>

 ![작업 표시줄 단추를 가진 창을 보여 주는 스크린샷입니다.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 <span data-ttu-id="b6b46-331">일부 유형의 창에는 메시지 상자 및 대화 상자와 같은 작업 표시 줄 단추가 [없습니다(대화 상자 개요](dialog-boxes-overview.md)참조).</span><span class="sxs-lookup"><span data-stu-id="b6b46-331">Some types of windows don't have a task bar button, such as message boxes and dialog boxes (see [Dialog Boxes Overview](dialog-boxes-overview.md)).</span></span> <span data-ttu-id="b6b46-332">기본적으로 속성을`true` 설정하여 창에 대한 작업 표시줄 <xref:System.Windows.Window.ShowInTaskbar%2A> 단추를 표시할지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-332">You can control whether the task bar button for a window is shown by setting the <xref:System.Windows.Window.ShowInTaskbar%2A> property (`true` by default).</span></span>  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a><span data-ttu-id="b6b46-333">보안 고려사항</span><span class="sxs-lookup"><span data-stu-id="b6b46-333">Security Considerations</span></span>  
 <span data-ttu-id="b6b46-334"><xref:System.Windows.Window>인스턴스화하려면 보안 권한이 필요합니다. `UnmanagedCode`</span><span class="sxs-lookup"><span data-stu-id="b6b46-334"><xref:System.Windows.Window> requires `UnmanagedCode` security permission to be instantiated.</span></span> <span data-ttu-id="b6b46-335">로컬 시스템에 설치되어 실행되는 애플리케이션의 경우에는 애플리케이션에 허용된 권한 집합에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-335">For applications installed on and launched from the local machine, this falls within the set of permissions that are granted to the application.</span></span>  
  
 <span data-ttu-id="b6b46-336">그러나 ClickOnce를 사용하여 인터넷 또는 로컬 인트라넷 영역에서 시작된 응용 프로그램에 부여된 권한 집합을 벗어나는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-336">However, this falls outside the set of permissions granted to applications that are launched from the Internet or Local intranet zone using ClickOnce.</span></span> <span data-ttu-id="b6b46-337">따라서 사용자는 ClickOnce 보안 경고를 받게 되며 응용 프로그램에 대한 권한 집합을 완전 신뢰로 상승시켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-337">Consequently, users will receive a ClickOnce security warning and will need to elevate the permission set for the application to full trust.</span></span>  
  
 <span data-ttu-id="b6b46-338">또한 XBAPs는 기본적으로 창이나 대화 상자를 표시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-338">Additionally, XBAPs cannot show windows or dialog boxes by default.</span></span> <span data-ttu-id="b6b46-339">독립 실행형 응용 프로그램 보안 고려 사항에 대한 설명은 [WPF 보안 전략 - 플랫폼 보안을](../wpf-security-strategy-platform-security.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-339">For a discussion on standalone application security considerations, see [WPF Security Strategy - Platform Security](../wpf-security-strategy-platform-security.md).</span></span>  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a><span data-ttu-id="b6b46-340">다른 유형의 창</span><span class="sxs-lookup"><span data-stu-id="b6b46-340">Other Types of Windows</span></span>  
 <span data-ttu-id="b6b46-341"><xref:System.Windows.Navigation.NavigationWindow>은 탐색 가능한 콘텐츠를 호스트하도록 설계된 창입니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-341"><xref:System.Windows.Navigation.NavigationWindow> is a window that is designed to host navigable content.</span></span> <span data-ttu-id="b6b46-342">자세한 내용은 [탐색 개요)를](navigation-overview.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6b46-342">For more information, see [Navigation Overview](navigation-overview.md)).</span></span>  
  
 <span data-ttu-id="b6b46-343">대화 상자는 기능 수행을 위해 사용자로부터 정보를 수집할 때 많이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-343">Dialog boxes are windows that are often used to gather information from a user to complete a function.</span></span> <span data-ttu-id="b6b46-344">예를 들어 사용자가 파일을 열려고 할 때 파일 **열기** 대화 상자는 일반적으로 응용 프로그램에서 사용자로부터 파일 이름을 얻으려고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6b46-344">For example, when a user wants to open a file, the **Open File** dialog box is usually displayed by an application to get the file name from the user.</span></span> <span data-ttu-id="b6b46-345">자세한 내용은 [대화 상자 개요](dialog-boxes-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6b46-345">For more information, see [Dialog Boxes Overview](dialog-boxes-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b46-346">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6b46-346">See also</span></span>

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [<span data-ttu-id="b6b46-347">대화 상자 개요</span><span class="sxs-lookup"><span data-stu-id="b6b46-347">Dialog Boxes Overview</span></span>](dialog-boxes-overview.md)
- [<span data-ttu-id="b6b46-348">WPF 애플리케이션 빌드</span><span class="sxs-lookup"><span data-stu-id="b6b46-348">Building a WPF Application</span></span>](building-a-wpf-application-wpf.md)
