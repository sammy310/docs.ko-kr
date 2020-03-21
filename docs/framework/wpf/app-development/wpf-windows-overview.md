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
# <a name="wpf-windows-overview"></a>WPF 창 개요
사용자는 창을 통해 WPF(Windows 프레젠테이션 기반) 독립 실행형 응용 프로그램과 상호 작용합니다. 창의 기본 용도는 데이터를 시각화하는 콘텐츠를 호스트하고 사용자가 데이터와 상호 작용할 수 있도록 하는 것입니다. 독립 실행형 WPF 응용 프로그램은 클래스를 <xref:System.Windows.Window> 사용하여 자체 창을 제공합니다. 이 항목에서는 <xref:System.Windows.Window> 독립 실행형 응용 프로그램에서 창을 만들고 관리하는 기본 을 다루기 전에 소개합니다.  
  
> [!NOTE]
> XAML 브라우저 응용 프로그램(XBAPs) 및 느슨한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 페이지를 비롯한 브라우저 호스팅 WPF 응용 프로그램은 자체 창을 제공하지 않습니다. 대신 Windows Internet Explorer에서 제공하는 창에서 호스팅됩니다. [WPF XAML 브라우저 응용 프로그램 개요를](wpf-xaml-browser-applications-overview.md)참조하십시오.  

<a name="TheWindowClass"></a>
## <a name="the-window-class"></a>Window 클래스  
 다음 그림은 창의 구성 부분을 보여 줍니다.  
  
 ![창 요소를 보여 주는 스크린샷입니다.](./media/wpf-windows-overview/window-constituent-elements.png)  
  
 창은 비클라이언트 영역과 클라이언트 영역의 두 영역으로 나뉩니다.  
  
 창의 *비클라이언트 영역은* WPF에 의해 구현되며 다음을 포함하여 대부분의 창에 공통적인 창 부분을 포함합니다.  
  
- 테두리.  
  
- 제목 표시줄.  
  
- 아이콘.  
  
- 최소화, 최대화 및 복원 단추.  
  
- 닫기 단추.  
  
- 사용자가 창을 최소화, 최대화, 복원, 이동, 크기 조정 및 닫을 수 있는 메뉴 항목이 들어 있는 시스템 메뉴.  
  
 창의 *클라이언트 영역은* 창의 비클라이언트 영역 내의 영역이며 개발자가 메뉴 모음, 도구 모음 및 컨트롤과 같은 응용 프로그램 별 콘텐츠를 추가하는 데 사용됩니다.  
  
 WPF에서 창은 다음을 <xref:System.Windows.Window> 수행하는 데 사용하는 클래스로 캡슐화됩니다.  
  
- 창을 표시합니다.  
  
- 창의 크기, 위치 및 모양을 구성합니다.  
  
- 애플리케이션별 콘텐츠를 호스팅합니다.  
  
- 창의 수명을 관리합니다.  
  
<a name="DefiningAWindow"></a>
## <a name="implementing-a-window"></a>창 구현  
 일반적인 창의 구현은 모양과 동작으로 구성되며, *여기서 모양은* 창이 사용자에게 보이는 방식을 정의하고 *동작은* 사용자가 윈도우와 상호 작용할 때 창이 작동하는 방식을 정의합니다. WPF에서 코드 또는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그를 사용하여 창의 모양과 동작을 구현할 수 있습니다.  
  
 그러나 일반적으로 창의 모양은 태그를 사용 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 하 여 구현 하 고 해당 동작은 다음 예제와 같이 코드 숨김을 사용 하 여 구현 됩니다.  
  
 [!code-xaml[WindowsOverviewSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 파일과 코드 숨은 파일이 함께 작동하도록 하려면 다음이 필요합니다.  
  
- 태그에서 `Window` 요소에 특성을 `x:Class` 포함해야 합니다. 응용 프로그램이 빌드될 때 `x:Class` 태그 파일에 있으면 Microsoft 빌드 엔진(MSBuild)이 `partial` <xref:System.Windows.Window> `x:Class` 특성에서 파생되고 특성에 의해 지정된 이름을 포함하는 클래스를 만듭니다. 이를 위해서는 스키마()에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` 대한 XML 네임스페이스 선언을 추가해야 합니다. 생성된 `partial` 클래스는 이벤트를 `InitializeComponent` 등록하고 태그에 구현된 속성을 설정하기 위해 호출되는 메서드를 구현합니다.  
  
- code-behind에서 클래스는 태그의 `partial` `x:Class` 특성에 의해 지정된 이름이 같은 클래스여야 하며 <xref:System.Windows.Window>에서 파생되어야 합니다. 이렇게 하면 코드 숨기는 파일을 `partial` 응용 프로그램이 빌드될 때 태그 파일에 대해 생성된 클래스와 연결될 수 있습니다(WPF [응용 프로그램 빌드](building-a-wpf-application-wpf.md)참조).  
  
- 코드 숨결에서 <xref:System.Windows.Window> 클래스는 메서드를 호출 하는 `InitializeComponent` 생성자 구현 해야 합니다. `InitializeComponent`태그 파일의 생성된 `partial` 클래스에 의해 구현되어 태그를 등록하고 태그에 정의된 속성을 설정합니다.  
  
> [!NOTE]
> Visual Studio를 <xref:System.Windows.Window> <xref:System.Windows.Window> 사용하여 프로젝트에 새 파일을 추가하는 경우 태그 와 코드 숨결을 모두 사용하여 구현되며 여기에 설명된 태그와 코드 숨는 파일 간의 연결을 만드는 데 필요한 구성이 포함됩니다.  
  
 이 구성을 사용하면 태그에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창의 모양을 정의하고 코드 숨결에서 해당 동작을 구현하는 데 집중할 수 있습니다. 다음 예제에서는 태그에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구현된 단추와 코드 숨결로 구현된 단추 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트에 대한 이벤트 처리기가 있는 창을 보여 주습니다.  
  
 [!code-xaml[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml#markupandcodebehindwindowmarkup)]  
  
 [!code-csharp[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/CSharp/MarkupAndCodeBehindWindow.xaml.cs#markupandcodebehindwindowcodebehind)]
 [!code-vb[WindowsOverviewWindowWithButtonSnippets#MarkupAndCodeBehindWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewWindowWithButtonSnippets/VisualBasic/MarkupAndCodeBehindWindow.xaml.vb#markupandcodebehindwindowcodebehind)]  
  
<a name="ConfiguringWindowForMSBuild"></a>
## <a name="configuring-a-window-definition-for-msbuild"></a>MSBuild에 대해 창 정의 구성  
 창을 구현하는 방법에 따라 MSBuild에 대해 창이 구성되는 방식이 결정됩니다. 태그와 코드 숨미를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 모두 사용하여 정의된 창의 경우:  
  
- XAML 태그 파일은 MSBuild `Page` 항목으로 구성됩니다.  
  
- 코드 숨은 파일은 MSBuild `Compile` 항목으로 구성됩니다.  
  
 이는 다음 MSBuild 프로젝트 파일에 표시됩니다.  
  
```xml  
<Project ...  
                xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    ...  
    <Page Include="MarkupAndCodeBehindWindow.xaml" />  
    <Compile Include=" MarkupAndCodeBehindWindow.xaml.cs" />  
    ...  
</Project>  
```  
  
 WPF 응용 프로그램 빌드에 대한 자세한 내용은 [WPF 응용 프로그램 빌드를](building-a-wpf-application-wpf.md)참조하십시오.  
  
<a name="WindowLifetime"></a>
## <a name="window-lifetime"></a>창 수명  
 다른 클래스와 마찬가지로 창에는 창이 열린 후 처음 인스턴스화될 때 시작하여, 열린 후 활성화 및 비활성화되고 최종적으로 닫힐 때까지의 기간인 수명이 있습니다.  

<a name="Opening_a_Window"></a>
### <a name="opening-a-window"></a>창 열기  
 창을 열려면 먼저 다음 예제에서 설명하는 것처럼 창의 인스턴스를 만듭니다.  
  
 [!code-xaml[WindowsOverviewStartupEventSnippets#AppMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml#appmarkup)]  
  
 [!code-csharp[WindowsOverviewStartupEventSnippets#AppCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewStartupEventSnippets/CSharp/App.xaml.cs#appcodebehind)]  
  
 이 예제에서는 `MarkupAndCodeBehindWindow` <xref:System.Windows.Application.Startup> 응용 프로그램이 시작될 때 인스턴스화되며 이벤트가 발생할 때 발생합니다.  
  
 창이 인스턴스화되면 <xref:System.Windows.Application> 해당 창에 대한 참조가 개체에서 관리하는 창 목록에 자동으로 추가됩니다(참조). <xref:System.Windows.Application.Windows%2A?displayProperty=nameWithType> 또한 인스턴스화할 첫 번째 창은 기본적으로 기본 응용 <xref:System.Windows.Application> 프로그램 창으로 설정됩니다(참조). <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>  
  
 메서드를 호출하여 창이 <xref:System.Windows.Window.Show%2A> 마지막으로 열립니다. 결과는 다음 그림에 표시됩니다.  
  
 ![창에서 창으로 열립니다.표시](./media/wpf-windows-overview//window-opened-show-method.png)  
  
 호출을 <xref:System.Windows.Window.Show%2A> 통해 열리는 창은 모덜리스 창으로, 사용자가 동일한 응용 프로그램에서 다른 창을 활성화할 수 있는 모드에서 응용 프로그램이 작동합니다.  
  
> [!NOTE]
> <xref:System.Windows.Window.ShowDialog%2A>대화 상자와 같은 창을 열도록 호출됩니다. 자세한 내용은 [대화 상자 개요를](dialog-boxes-overview.md) 참조하십시오.  
  
 호출될 때 <xref:System.Windows.Window.Show%2A> 창은 사용자 입력을 받을 수 있는 인프라를 설정하는 데 표시되기 전에 초기화 작업을 수행합니다. 창이 초기화되면 <xref:System.Windows.Window.SourceInitialized> 이벤트가 발생되고 창이 표시됩니다.  
  
 바로 가기로 <xref:System.Windows.Application.StartupUri%2A> 응용 프로그램이 시작될 때 자동으로 열리는 첫 번째 창을 지정하도록 설정할 수 있습니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ApplicationStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/App.xaml#applicationstartupurimarkup)]  
  
 응용 프로그램이 시작되면 값으로 지정된 <xref:System.Windows.Application.StartupUri%2A> 창이 모데없이 열립니다. 내부적으로 창을 호출하여 <xref:System.Windows.Window.Show%2A> 열립니다.  
  
<a name="Ownership"></a>
#### <a name="window-ownership"></a>창 소유권  
 <xref:System.Windows.Window.Show%2A> 메서드를 사용하여 열리는 창에는 메서드를 만든 창과 암시적 관계가 없습니다. 사용자는 두 창 중 어느 창도 독립적으로 상호 작용할 수 있으며, 이는 두 창 중 하나가 다음을 수행할 수 있음을 의미합니다.  
  
- 다른 창을 덮습니다(창 중 <xref:System.Windows.Window.Topmost%2A> 하나에 속성이 설정되어 있는 `true`경우).  
  
- 다른 창에 영향을 주지 않고 최소화, 최대화 및 복원합니다.  
  
 일부 창은 해당 창을 여는 창과의 관계를 필요로 합니다. 예를 들어 IDE(통합 개발 환경) 응용 프로그램은 속성 창을 열고 이를 만드는 창을 덮는 일반적인 동작이 있는 도구 창을 열 수 있습니다. 또한 이러한 창은 항상 해당 창을 만든 창과 함께 닫히고, 최소화되고, 최대화되고, 복원되어야 합니다. 이러한 관계는 한 창을 다른 *창으로* 만들어 설정할 수 <xref:System.Windows.Window.Owner%2A> 있으며 소유자 *창에*대한 참조를 사용하여 *소유한 창의* 속성을 설정하여 달성됩니다. 이는 다음 예에서 확인할 수 있습니다.  
  
 [!code-csharp[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/CSharp/MainWindow.xaml.cs#setwindowownercode)]
 [!code-vb[WindowOwnerOwnedWindowsSnippets#SetWindowOwnerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowOwnerOwnedWindowsSnippets/visualbasic/mainwindow.xaml.vb#setwindowownercode)]  
  
 소유권이 설정된 후:  
  
- 소유 된 창은 속성의 값을 검사하여 <xref:System.Windows.Window.Owner%2A> 소유자 창을 참조 할 수 있습니다.  
  
- 소유자 창은 속성의 값을 검사하여 소유한 모든 <xref:System.Windows.Window.OwnedWindows%2A> 창을 검색할 수 있습니다.  
  
<a name="Preventing"></a>
#### <a name="preventing-window-activation"></a>창 활성화 방지  
 인터넷 메신저 스타일 응용 프로그램의 대화 창 또는 전자 메일 응용 프로그램의 알림 창과 같이 표시될 때 창을 활성화하지 않아야 하는 시나리오가 있습니다.  
  
 응용 프로그램에 표시할 때 활성화되지 않아야 하는 창이 <xref:System.Windows.Window.ShowActivated%2A> 있는 `false` 경우 <xref:System.Windows.Window.Show%2A> 메서드를 처음 호출하기 전에 해당 속성을 설정하여 설정할 수 있습니다. 이렇게 하면 다음과 같은 결과가 나타납니다.  
  
- 창이 활성화되지 않습니다.  
  
- 창의 <xref:System.Windows.Window.Activated> 이벤트가 발생되지 않습니다.  
  
- 현재 활성 창이 활성 상태로 유지됩니다.  
  
 그러나 사용자가 클라이언트 영역이나 비클라이언트 영역을 클릭하여 창을 활성화하면 해당 창이 활성화됩니다. 이 경우 다음과 같습니다.  
  
- 창이 활성화됩니다.  
  
- 창의 <xref:System.Windows.Window.Activated> 이벤트가 발생합니다.  
  
- 이전에 활성 상태였던 창이 비활성화됩니다.  
  
- <xref:System.Windows.Window.Deactivated> 창및이벤트는 <xref:System.Windows.Window.Activated> 이후에 사용자 작업에 대한 응답으로 예상대로 발생합니다.  
  
<a name="Window_Activation"></a>
### <a name="window-activation"></a>창 활성화  
 창이 처음 열리면 활성 창이 됩니다(로 설정된 <xref:System.Windows.Window.ShowActivated%2A> 상태로 `false`표시되지 않는 한). *활성 창은* 키 스트로크 및 마우스 클릭과 같은 사용자 입력을 현재 캡처하는 창입니다. 창이 활성화되면 이벤트가 발생합니다. <xref:System.Windows.Window.Activated>  
  
> [!NOTE]
> 창이 처음 열리면 <xref:System.Windows.FrameworkElement.Loaded> 이벤트 <xref:System.Windows.Window.ContentRendered> 발생 후에만 <xref:System.Windows.Window.Activated> 및 이벤트가 발생합니다. 이 점을 염두에 두고 창을 발생시 <xref:System.Windows.Window.ContentRendered> 열어 두는 것으로 간주할 수 있습니다.  
  
 창이 활성 창이 되면 사용자는 같은 애플리케이션의 다른 창을 활성화하거나 다른 애플리케이션을 활성화할 수 있습니다. 이 경우 현재 활성 창이 비활성화되고 <xref:System.Windows.Window.Deactivated> 이벤트가 발생합니다. 마찬가지로 사용자가 현재 비활성화된 창을 선택하면 창이 다시 활성화되고 <xref:System.Windows.Window.Activated> 발생합니다.  
  
 처리해야 <xref:System.Windows.Window.Activated> 하는 <xref:System.Windows.Window.Deactivated> 일반적인 이유 중 하나는 창이 활성화되어 있을 때만 실행할 수 있는 기능을 활성화하고 사용하지 않도록 설정하는 것입니다. 예를 들어 일부 창은 게임 및 비디오 플레이어를 포함하여 지속적인 사용자의 입력이나 주의가 필요한 대화식 콘텐츠를 표시합니다. 다음 예제에서는 이 동작을 처리하고 <xref:System.Windows.Window.Activated> <xref:System.Windows.Window.Deactivated> 구현하는 방법을 보여 주는 간소화된 비디오 플레이어입니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ActivationDeactivationMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml#activationdeactivationmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/CustomMediaPlayerWindow.xaml.cs#activationdeactivationcodebehind)]
 [!code-vb[WindowsOverviewSnippets#ActivationDeactivationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/CustomMediaPlayerWindow.xaml.vb#activationdeactivationcodebehind)]  
  
 다른 형식의 애플리케이션은 창이 비활성화되었을 때 계속 백그라운드에서 코드를 실행할 수 있습니다. 예를 들어 메일 클라이언트는 사용자가 다른 애플리케이션을 사용하고 있을 때 메일 서버를 계속 폴링할 수 있습니다. 이러한 애플리케이션에는 기본 창이 비활성화되었을 때 다른 동작 또는 추가 동작을 제공하기도 합니다. 메일 프로그램의 경우에 이것은 새 메일 항목을 받은 편지함에 추가하고 시스템 트레이에 알림 아이콘을 추가하는 작업을 의미할 수 있습니다. 알림 아이콘은 메일 창이 활성화되어 있지 않을 때만 표시되며, <xref:System.Windows.Window.IsActive%2A> 이 아이콘은 속성을 검사하여 결정할 수 있습니다.  
  
 백그라운드 작업이 완료되면 창에서 메서드를 호출하여 <xref:System.Windows.Window.Activate%2A> 사용자에게 더 긴급하게 알릴 수 있습니다. 사용자가 호출될 때 <xref:System.Windows.Window.Activate%2A> 활성화된 다른 응용 프로그램과 상호 작용하는 경우 창의 작업 표시줄 단추가 깜박입니다. 사용자가 현재 응용 프로그램과 상호 작용하는 <xref:System.Windows.Window.Activate%2A> 경우 호출하면 창이 포그라운드로 이동합니다.  
  
> [!NOTE]
> <xref:System.Windows.Application.Activated?displayProperty=nameWithType> 및 <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> 이벤트를 사용하여 응용 프로그램 범위 활성화를 처리할 수 있습니다.  
  
<a name="Closing_a_Window"></a>
### <a name="closing-a-window"></a>창 닫기  
 창의 수명은 사용자가 창을 닫을 때 끝나게 됩니다. 창은 다음을 포함하여 비클라이언트 영역의 요소를 사용하여 닫을 수 있습니다.  
  
- **시스템** **닫기** 항목입니다.  
  
- ALT+F4 누르기.  
  
- **닫기** 버튼을 누른다.  
  
 클라이언트 영역에 창을 닫기 위한 추가적인 메커니즘을 제공할 수 있으며 이 메커니즘에는 일반적으로 다음이 포함됩니다.  
  
- 일반적으로 기본 응용 프로그램 창에 대한 **파일** 메뉴의 **종료** 항목입니다.  
  
- **파일** 메뉴에서 일반적으로 보조 응용 프로그램 창에서 **닫기** 항목입니다.  
  
- 일반적으로 모달 대화 상자의 **취소** 단추입니다.  
  
- 일반적으로 모덜리스 대화 상자에서 **닫기** 단추입니다.  
  
 이러한 사용자 지정 메커니즘 중 하나에 대한 응답으로 창을 닫려면 메서드를 <xref:System.Windows.Window.Close%2A> 호출해야 합니다. 다음 예제는 **파일** 메뉴에서 **종료를** 선택하여 창을 닫는 기능을 구현합니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowWithFileExitMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml#windowwithfileexitmarkup)]  
  
 [!code-csharp[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowWithFileExit.xaml.cs#windowwithfileexitcodebehind)]
 [!code-vb[WindowsOverviewSnippets#WindowWithFileExitCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowsOverviewSnippets/VisualBasic/WindowWithFileExit.xaml.vb#windowwithfileexitcodebehind)]  
  
 창이 닫히면 두 개의 <xref:System.Windows.Window.Closing> 이벤트가 <xref:System.Windows.Window.Closed>발생합니다.  
  
 <xref:System.Windows.Window.Closing>창이 닫히기 전에 발생하며 창 닫을 방지할 수 있는 메커니즘을 제공합니다. 대개 창이 닫히면 안 되는 한 가지 이유는 창 콘텐츠에 수정된 데이터가 있는 경우입니다. 이 경우 <xref:System.Windows.Window.Closing> 이벤트를 처리하여 데이터가 더러워졌는지 확인하고, 데이터가 더러워지는 경우 사용자에게 데이터를 저장하지 않고 창을 계속 닫을지 또는 창 닫기를 취소할지 물어볼 수 있습니다. 다음 예제에서는 처리의 <xref:System.Windows.Window.Closing>주요 측면을 보여 주며 있습니다.  
  
 [!code-csharp[WindowClosingSnippets](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowClosingSnippets/CSharp/DataWindow.xaml.cs)]
 [!code-vb[WindowClosingSnippets](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WindowClosingSnippets/visualbasic/datawindow.xaml.vb)]  

 <xref:System.Windows.Window.Closing> 이벤트 처리기는 <xref:System.ComponentModel.CancelEventArgs>창이 닫히지 않도록 `Boolean` <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> 설정한 `true` 속성을 구현하는 를 전달합니다.  
  
 <xref:System.Windows.Window.Closing> 처리되지 않거나 처리되었지만 취소되지 않으면 창이 닫힙됩니다. 창이 실제로 닫히기 <xref:System.Windows.Window.Closed> 직전에 발생합니다. 이 시점에서는 창 닫기를 방지할 수 없습니다.  
  
> [!NOTE]
> 주 응용 프로그램 창이 닫히거나 마지막 창이 닫히면 <xref:System.Windows.Application.MainWindow%2A>응용 프로그램을 자동으로 종료하도록 구성할 수 있습니다.  자세한 내용은 <xref:System.Windows.Application.ShutdownMode%2A>를 참조하십시오.  
  
 비 클라이언트 및 클라이언트 영역에서 제공되는 메커니즘을 통해 창을 명시적으로 닫을 수 있지만 다음을 포함하여 응용 프로그램 또는 Windows의 다른 부분에서 의한 동작으로 인해 창을 암시적으로 닫을 수도 있습니다.  
  
- 사용자가 Windows를 로그오프하거나 종료합니다.  
  
- 창의 소유자가 닫힙니다(참조). <xref:System.Windows.Window.Owner%2A>  
  
- 기본 응용 프로그램 창이 <xref:System.Windows.ShutdownMode.OnMainWindowClose>닫혀 있습니다. <xref:System.Windows.Application.ShutdownMode%2A>  
  
- <xref:System.Windows.Application.Shutdown%2A>을 호출합니다.  
  
> [!NOTE]
> 창을 닫은 뒤에는 다시 열 수 없습니다.  
  
<a name="Window_Lifetime_Events"></a>
### <a name="window-lifetime-events"></a>창 수명 이벤트  
 다음 그림에서는 창의 수명 동안 주 이벤트의 시퀀스를 보여 주입니다.  
  
 ![창의 수명 동안의 이벤트를 보여 주는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-events.png)  
  
 다음 그림에서는 활성화 없이 표시되는 창의 수명 동안 주 이벤트의<xref:System.Windows.Window.ShowActivated%2A> 시퀀스를 보여 주입니다(창이 표시되기 `false` 전에 설정됨).  
  
 ![활성화하지 않고 창의 수명에 있는 이벤트를 보여 주는 다이어그램입니다.](./media/wpf-windows-overview/window-lifetime-no-activation.png)  
  
<a name="WindowLocation"></a>
## <a name="window-location"></a>창 위치  
 창은 열릴 때 바탕 화면에 상대적인 x 및 y 크기의 위치를 가집니다. 이 위치는 각각 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 특성을 검사하여 결정할 수 있습니다. 이 속성을 설정하여 창의 위치를 변경할 수 있습니다.  
  
 다음 <xref:System.Windows.WindowStartupLocation> 열거값 중 하나로 <xref:System.Windows.Window> <xref:System.Windows.Window.WindowStartupLocation%2A> 속성을 설정하여 a의 초기 위치를 지정할 수도 있습니다.  
  
- <xref:System.Windows.WindowStartupLocation.CenterOwner>(기본값)  
  
- <xref:System.Windows.WindowStartupLocation.CenterScreen>  
  
- <xref:System.Windows.WindowStartupLocation.Manual>  
  
 시작 <xref:System.Windows.WindowStartupLocation.Manual>위치가 로 지정되고 <xref:System.Windows.Window.Left%2A> 및 <xref:System.Windows.Window.Top%2A> 속성이 설정되지 <xref:System.Windows.Window> 않은 경우 Windows에 위치가 표시되도록 요청합니다.  
  
<a name="Topmost_Windows_and_Z_Order"></a>
### <a name="topmost-windows-and-z-order"></a>최상위 창 및 Z 순서  
 창에는 x 및 y 위치 이외에도 다른 창과 상대적인 수직 위치를 결정하는 z 차원의 위치도 있습니다. 이를 창의 z 순서라고 하며 여기에는 일반 z 순서와 최상위 z 순서의 두 가지 유형이 있습니다. *일반 z-순서의* 창 위치는 현재 활성 상태인지 여부에 따라 결정됩니다. 기본적으로 창은 일반 z 순서로 배치됩니다. *최상위 z-order의* 창 위치는 현재 활성 상태인지 여부에 따라 결정됩니다. 최상위 z 수준의 창은 항상 일반 z 순서 창의 위에 위치합니다. 창은 <xref:System.Windows.Window.Topmost%2A> 속성을 로 설정하여 최상위 z 순서에 `true`있습니다.  
  
 [!code-xaml[WindowsOverviewSnippets#TopmostWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TopmostWindow.xaml#topmostwindowmarkup1)]  
  
 각 z 순서 안에서는 현재 활성화된 창이 같은 z 순서를 가진 다른 모든 창 위에 나타납니다.  
  
<a name="WindowSize"></a>
## <a name="window-size"></a>창 크기  
 데스크톱 위치 외에도 창에는 다양한 너비 및 높이 속성 및 <xref:System.Windows.Window.SizeToContent%2A>.  
  
 <xref:System.Windows.FrameworkElement.MinWidth%2A>s은 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.MaxWidth%2A> 창이 수명 동안 가질 수 있는 너비 범위를 관리하는 데 사용되며 다음 예제와 같이 구성됩니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WidthWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WidthWindow.xaml#widthwindowmarkup1)]  
  
 창 높이는 <xref:System.Windows.FrameworkElement.MinHeight%2A>에서 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>관리되며 다음 예제와 같이 구성됩니다.  
  
 [!code-xaml[WindowsOverviewSnippets#HeightWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/HeightWindow.xaml#heightwindowmarkup1)]  
  
 다양한 너비 값과 높이 값이 각각 범위를 지정하고 있기 때문에, 크기 조정 가능한 창의 너비와 높이는 지정한 범위 내에서 임의의 크기로 설정될 수 있습니다. 현재 너비와 높이를 감지하려면 <xref:System.Windows.FrameworkElement.ActualHeight%2A>각각 검사하고 <xref:System.Windows.FrameworkElement.ActualWidth%2A>  
  
 창의 너비와 높이를 창 내용의 크기에 맞는 크기를 지정하려면 다음 값을 가진 <xref:System.Windows.Window.SizeToContent%2A> 속성을 사용할 수 있습니다.  
  
- <xref:System.Windows.SizeToContent.Manual>. 아무런 영향이 없습니다(기본값).  
  
- <xref:System.Windows.SizeToContent.Width>. 콘텐츠 너비와 둘 다 <xref:System.Windows.FrameworkElement.MinWidth%2A> 설정및 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 콘텐츠 너비와 동일한 효과가 있는 콘텐츠 너비에 맞춥습니다.  
  
- <xref:System.Windows.SizeToContent.Height>. 콘텐츠 높이에 맞게 <xref:System.Windows.FrameworkElement.MinHeight%2A> 설정및 <xref:System.Windows.FrameworkElement.MaxHeight%2A> 콘텐츠 높이와 동일한 효과를 가짐입니다.  
  
- <xref:System.Windows.SizeToContent.WidthAndHeight>. 콘텐츠 너비와 높이에 맞게 콘텐츠의 높이와 <xref:System.Windows.FrameworkElement.MinHeight%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A> 둘 다 설정 및 콘텐츠 <xref:System.Windows.FrameworkElement.MinWidth%2A> 의 <xref:System.Windows.FrameworkElement.MaxWidth%2A> 너비를 설정하는 것과 동일한 효과를 내립니다.  
  
 다음 예는 창이 처음 표시될 때 콘텐츠에 맞도록 수직 및 수평으로 크기를 자동으로 조정하는 창을 보여 줍니다.  
  
 [!code-xaml[WindowsOverviewSnippets#SizeToContentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/SizeToContentWindow.xaml#sizetocontentwindowmarkup1)]  
  
 다음 예제에서는 코드에서 <xref:System.Windows.Window.SizeToContent%2A> 속성을 설정하여 창의 내용에 맞게 창 크기를 조정하는 방법을 보여 주며 있습니다.
  
 [!code-csharp[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#setwindowsizetocontentpropertycode)]
 [!code-vb[HOWTOWindowManagementSnippets#SetWindowSizeToContentPropertyCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#setwindowsizetocontentpropertycode)]  
  
<a name="OrderOfPrecedence"></a>
## <a name="order-of-precedence-for-sizing-properties"></a>크기 조정 속성에 대한 우선 순위 순서  
 기본적으로 창의 다양한 크기 속성이 결합되어 크기 조정 가능한 창의 너비와 높이의 범위가 정의됩니다. 유효한 범위가 유지되도록 하려면 <xref:System.Windows.Window> 다음 우선 순위를 사용하여 크기 속성의 값을 평가합니다.  
  
 **높이 속성:**  
  
1. <xref:System.Windows.FrameworkElement.MinHeight%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxHeight%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Height?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Height%2A?displayProperty=nameWithType>  
  
 **너비 속성:**  
  
1. <xref:System.Windows.FrameworkElement.MinWidth%2A?displayProperty=nameWithType>
  
2. <xref:System.Windows.FrameworkElement.MaxWidth%2A?displayProperty=nameWithType>
  
3. <xref:System.Windows.SizeToContent.Width?displayProperty=nameWithType>/<xref:System.Windows.SizeToContent.WidthAndHeight?displayProperty=nameWithType>
  
4. <xref:System.Windows.FrameworkElement.Width%2A?displayProperty=nameWithType>  
  
 우선 순위는 <xref:System.Windows.Window.WindowState%2A> 속성으로 관리되는 창이 최대화될 때 의 크기를 결정할 수도 있습니다.  
  
<a name="WindowState"></a>
## <a name="window-state"></a>창 상태  
 크기 조정 가능한 창의 수명은 표준, 최소화 및 최대화의 세 가지 상태를 가질 수 있습니다. *정상* 상태가 있는 창은 창의 기본 상태입니다. 크기 조정 가능 창이 표준 상태인 경우 사용자는 크기 조정 그립이나 테두리를 사용하여 창을 이동하고 크기 조정할 수 있습니다.  
  
 로 설정된 경우 <xref:System.Windows.Window.ShowInTaskbar%2A> *최소화된* 상태의 창이 작업 표시줄 `true`단추로 축소됩니다. 그렇지 않으면 가능한 가장 작은 크기로 축소되고 바탕 화면의 왼쪽 아래 모서리로 재배치됩니다. 이러한 최소화된 창 유형은 테두리나 크기 조정 그립을 사용하여 크기 조정할 수 없습니다. 하지만 작업 표시줄에 표시되지 않은 최소화된 창은 바탕 화면에서 끌 수 있습니다.  
  
 *최대화 된* 상태의 창은 할 수있는 최대 크기로 확장되며 , 이는 <xref:System.Windows.FrameworkElement.MaxWidth%2A> <xref:System.Windows.FrameworkElement.MaxHeight%2A>의 <xref:System.Windows.Window.SizeToContent%2A> 및 속성이 받아쓰기하는 크기만큼 커질 것입니다. 최소화된 창과 마찬가지로 최대화된 창은 크기 조정 그립을 사용하거나 테두리를 끌어서 크기 조정할 수 없습니다.  
  
> [!NOTE]
> 의 <xref:System.Windows.Window.Top%2A>값은 <xref:System.Windows.Window.Left%2A>의 <xref:System.Windows.FrameworkElement.Width%2A>값입니다 . <xref:System.Windows.FrameworkElement.Height%2A>  
  
 창의 상태는 다음 <xref:System.Windows.Window.WindowState%2A> <xref:System.Windows.WindowState> 열거 값 중 하나를 가질 수 있는 속성을 설정하여 구성할 수 있습니다.  
  
- <xref:System.Windows.WindowState.Normal>(기본값)  
  
- <xref:System.Windows.WindowState.Maximized>  
  
- <xref:System.Windows.WindowState.Minimized>  
  
 다음 예제에서는 열릴 때 최대화되어 표시되는 창을 만드는 방법을 보여 줍니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStateWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStateWindow.xaml#windowstatewindowmarkup1)]  
  
 일반적으로 창의 초기 <xref:System.Windows.Window.WindowState%2A> 상태를 구성하도록 설정해야 합니다. 크기 조정 가능한 창이 표시되면 사용자는 창의 제목 표시줄에서 최소화, 최대화 및 복원 단추를 눌러 창 상태를 변경할 수 있습니다.  
  
<a name="WindowAppearance"></a>
## <a name="window-appearance"></a>창 모양  
 단추, 레이블 및 텍스트 상자와 같은 창 특정 콘텐츠를 창에 추가하여 창의 클라이언트 영역의 모양을 변경할 수 있습니다. 클라이언트가 아닌 영역을 <xref:System.Windows.Window> 구성하려면 창아이콘을 <xref:System.Windows.Window.Icon%2A> 설정하고 <xref:System.Windows.Window.Title%2A> 제목을 설정하는 등 여러 속성을 제공합니다.  
  
 또한 창의 크기 조정 모드, 창 스타일 및 바탕 화면 작업 표시줄에 단추로 표시될 것인지 여부를 구성하여 비클라이언트 영역 테두리의 모양과 동작을 변경할 수도 있습니다.  

<a name="Resize_Mode"></a>
### <a name="resize-mode"></a>크기 조정 모드  
 속성에 <xref:System.Windows.Window.WindowStyle%2A> 따라 사용자가 창 크기를 조정할 수 있는 방법(및 if)을 제어할 수 있습니다. 창 스타일을 선택하면 사용자가 마우스로 테두리를 드래그하여 창 크기를 조정할 수 있는지 여부, **클라이언트가**아닌 영역에 최소화, **최대화**및 **크기 조정** 단추가 나타나는지 여부, 창이 활성화되어 있는지 여부에 영향을 줍니다.  
  
 다음 <xref:System.Windows.ResizeMode> 열거 값 중 하나가 될 <xref:System.Windows.Window.ResizeMode%2A> 수 있는 해당 속성을 설정하여 창 크기를 조정하는 방법을 구성할 수 있습니다.  
  
- <xref:System.Windows.ResizeMode.NoResize>  
  
- <xref:System.Windows.ResizeMode.CanMinimize>  
  
- <xref:System.Windows.ResizeMode.CanResize>(기본값)  
  
- <xref:System.Windows.ResizeMode.CanResizeWithGrip>  
  
 마찬가지로 <xref:System.Windows.Window.WindowStyle%2A>창의 크기 조정 모드는 수명 동안 변경될 가능성이 낮으므로 태그에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창으로 설정할 가능성이 큽니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ResizeModeWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ResizeModeWindow.xaml#resizemodewindowmarkup1)]  
  
 속성을 검사하여 창을 최대화, 최소화 또는 복원하는지 여부를 검색할 <xref:System.Windows.Window.WindowState%2A> 수 있습니다.  
  
<a name="Window_Style"></a>
### <a name="window-style"></a>창 스타일  
 창의 비클라이언트 영역에서 노출되는 테두리는 대부분의 애플리케이션에 적합합니다. 하지만 창의 유형에 따라 다른 유형의 테두리가 필요하거나 테두리가 전혀 필요 없는 경우가 있습니다.  
  
 창이 받는 테두리 유형을 제어하려면 <xref:System.Windows.Window.WindowStyle%2A> <xref:System.Windows.WindowStyle> 열거형의 다음 값 중 하나로 해당 속성을 설정합니다.  
  
- <xref:System.Windows.WindowStyle.None>  
  
- <xref:System.Windows.WindowStyle.SingleBorderWindow>(기본값)  
  
- <xref:System.Windows.WindowStyle.ThreeDBorderWindow>  
  
- <xref:System.Windows.WindowStyle.ToolWindow>  
  
 이러한 창 스타일의 효과는 다음 그림에 나와 있습니다.  
  
 ![창 테두리 스타일의 그림입니다.](./media/wpf-windows-overview/window-border-styles.png)  
  
 태그 또는 <xref:System.Windows.Window.WindowStyle%2A> 코드를 사용하여 설정할 수 있습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 창의 수명 동안 변경될 가능성이 낮으므로 태그를 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 구성할 가능성이 큽니다.  
  
 [!code-xaml[WindowsOverviewSnippets#WindowStyleWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/WindowStyleWindow.xaml#windowstylewindowmarkup1)]  
  
#### <a name="non-rectangular-window-style"></a>사각형이 아닌 창 스타일  
 테두리 스타일이 <xref:System.Windows.Window.WindowStyle%2A> 충분하지 않은 경우도 있습니다. 예를 들어 Microsoft Windows 미디어 플레이어에서 사용하는 것과 같이 직사각형이 아닌 테두리가 있는 응용 프로그램을 만들 수 있습니다.  
  
 예를 들어 다음 그림에 표시된 음성 거품 창을 고려하십시오.  
  
 ![나를 드래그 말한다 음성 거품 창.](./media/wpf-windows-overview/non-rectangular-window-figure.png)  
  
 이러한 유형의 창은 <xref:System.Windows.Window.WindowStyle%2A> 속성을 <xref:System.Windows.WindowStyle.None>로 설정하고 투명도가 있는 <xref:System.Windows.Window> 특수 지원을 사용하여 만들 수 있습니다.  
  
 [!code-xaml[WindowsOverviewSnippets#TransparentWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/TransparentWindow.xaml#transparentwindowmarkup1)]  
  
 값을 조합하여 사용하면 창이 완전히 투명하게 렌더링됩니다. 이 상태에서는 창의 비클라이언트 영역 표시(닫기 메뉴, 최소화, 최대화 및 복원 단추 등)를 사용할 수 없습니다. 따라서 직접 제공해야 합니다.  
  
<a name="Task_Bar_Presence"></a>
### <a name="task-bar-presence"></a>작업 표시줄 표시  

창의 기본 모양에는 다음 그림에 표시된 것과 같은 작업 표시줄 단추가 포함됩니다.

 ![작업 표시줄 단추를 가진 창을 보여 주는 스크린샷입니다.](./media/wpf-windows-overview/window-taskbar-button.png)  
  
 일부 유형의 창에는 메시지 상자 및 대화 상자와 같은 작업 표시 줄 단추가 [없습니다(대화 상자 개요](dialog-boxes-overview.md)참조). 기본적으로 속성을`true` 설정하여 창에 대한 작업 표시줄 <xref:System.Windows.Window.ShowInTaskbar%2A> 단추를 표시할지 여부를 제어할 수 있습니다.  
  
 [!code-xaml[WindowsOverviewSnippets#ShowInTaskbarWindowMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/WindowsOverviewSnippets/CSharp/ShowInTaskbarWindow.xaml#showintaskbarwindowmarkup1)]  
  
<a name="SecurityConsiderations"></a>
## <a name="security-considerations"></a>보안 고려사항  
 <xref:System.Windows.Window>인스턴스화하려면 보안 권한이 필요합니다. `UnmanagedCode` 로컬 시스템에 설치되어 실행되는 애플리케이션의 경우에는 애플리케이션에 허용된 권한 집합에 속합니다.  
  
 그러나 ClickOnce를 사용하여 인터넷 또는 로컬 인트라넷 영역에서 시작된 응용 프로그램에 부여된 권한 집합을 벗어나는 것입니다. 따라서 사용자는 ClickOnce 보안 경고를 받게 되며 응용 프로그램에 대한 권한 집합을 완전 신뢰로 상승시켜야 합니다.  
  
 또한 XBAPs는 기본적으로 창이나 대화 상자를 표시할 수 없습니다. 독립 실행형 응용 프로그램 보안 고려 사항에 대한 설명은 [WPF 보안 전략 - 플랫폼 보안을](../wpf-security-strategy-platform-security.md)참조하십시오.  
  
<a name="Other_Types_of_Windows"></a>
## <a name="other-types-of-windows"></a>다른 유형의 창  
 <xref:System.Windows.Navigation.NavigationWindow>은 탐색 가능한 콘텐츠를 호스트하도록 설계된 창입니다. 자세한 내용은 [탐색 개요)를](navigation-overview.md)참조하십시오.  
  
 대화 상자는 기능 수행을 위해 사용자로부터 정보를 수집할 때 많이 사용됩니다. 예를 들어 사용자가 파일을 열려고 할 때 파일 **열기** 대화 상자는 일반적으로 응용 프로그램에서 사용자로부터 파일 이름을 얻으려고 표시됩니다. 자세한 내용은 [대화 상자 개요](dialog-boxes-overview.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Window>
- <xref:System.Windows.MessageBox>
- <xref:System.Windows.Navigation.NavigationWindow>
- <xref:System.Windows.Application>
- [대화 상자 개요](dialog-boxes-overview.md)
- [WPF 애플리케이션 빌드](building-a-wpf-application-wpf.md)
