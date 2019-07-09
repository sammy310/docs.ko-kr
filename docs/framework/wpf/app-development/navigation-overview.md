---
title: 탐색 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- loose XAML files [WPF]
- windows [WPF]
- Start page [WPF]
- HTML files [WPF]
- structured navigation [WPF]
- fragment navigation [WPF]
- URIs (Uniform Resource Identifiers)
- custom objects [WPF]
- Uniform Resource Identifiers (URIs)
- pages [WPF]
- frames [WPF]
- navigation hosts [WPF]
- journals [WPF]
- lifetimes [WPF]
- retaining content state [WPF]
- content state [WPF]
- programmatic navigation [WPF]
- hyperlinks [WPF]
ms.assetid: 86ad2143-606a-4e34-bf7e-51a2594248b8
ms.openlocfilehash: 73506c4151408a4c5f9ccca3be35ef99c9d7e81b
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663968"
---
# <a name="navigation-overview"></a>탐색 개요

Windows Presentation Foundation (WPF)는 두 가지 유형의 응용 프로그램에서 사용할 수 있는 브라우저 스타일 탐색을 지 원하는: 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]합니다. 탐색을 위한 패키지 콘텐츠에 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 제공 된 <xref:System.Windows.Controls.Page> 클래스. 간에 이동할 수 있습니다 <xref:System.Windows.Controls.Page> 간에 선언적으로 사용 하 여는 <xref:System.Windows.Documents.Hyperlink>, 또는 사용 하 여 프로그래밍 방식으로 <xref:System.Windows.Navigation.NavigationService>합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 저널을 사용하여 탐색했던 페이지를 기억했다가 다시 해당 페이지로 돌아옵니다.

<xref:System.Windows.Controls.Page>를 <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Navigation.NavigationService>, 저널에서 제공 하는 탐색 지원의 핵심을 형성 하 고 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]입니다. 이 개요에서는 느슨한 탐색을 포함 하는 고급 탐색 지원 다루기 전에 이러한 기능을 자세히 살펴봅니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일인 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 파일 및 개체입니다.

> [!NOTE]
> 이 항목에서는 "브라우저" 이라는 용어를 호스팅할 수 있는 브라우저만 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 현재 포함 하는 응용 프로그램 [!INCLUDE[TLA#tla_ie](../../../../includes/tlasharptla-ie-md.md)] 및 Firefox. 특정 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 기능이 특정 브라우저 에서만 지원 되는, 브라우저 버전 이라고 합니다.

## <a name="navigation-in-wpf-applications"></a>WPF 애플리케이션에서 탐색

이 항목에서는 주요 탐색 기능에 대 한 개요를 제공 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다. 이러한 기능은 모두 독립 실행형 응용 프로그램에 사용할 수 있습니다 하 고 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]이지만이 항목의 컨텍스트 내에서 표시를 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]입니다.

> [!NOTE]
> 이 항목에서는 빌드 및 배포 방법에 논의 하지 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다. 에 대 한 자세한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]를 참조 하세요 [WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md)합니다.

이 섹션에서는 다음과 같은 탐색 측면에 대해 설명합니다.

- [페이지 구현](#CreatingAXAMLPage)

- [시작 페이지 구성](#Configuring_a_Start_Page)

- [호스트 창 제목, 너비 및 높이 구성](#ConfiguringAXAMLPage)

- [하이퍼링크 탐색](#NavigatingBetweenXAMLPages)

- [조각 탐색](#FragmentNavigation)

- [탐색 서비스](#NavigationService)

- [탐색 서비스를 사용하여 프로그래밍 방식으로 탐색](#Programmatic_Navigation_with_the_Navigation_Service)

- [탐색 수명](#Navigation_Lifetime)

- [저널을 사용하여 탐색 기억](#NavigationHistory)

- [페이지 수명 및 저널](#PageLifetime)

- [탐색 기록을 사용하여 콘텐츠 상태 유지](#RetainingContentStateWithNavigationHistory)

- [쿠키](#Cookies)

- [구조적 탐색](#Structured_Navigation)

<a name="CreatingAXAMLPage"></a>

### <a name="implementing-a-page"></a>페이지 구현

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)],.NET Framework 개체, 사용자 지정 개체, 열거형 값, 사용자 정의 컨트롤을 포함 하는 여러 콘텐츠 형식을 탐색할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 및 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 파일입니다. 그러나 있습니다를 사용 하 여 가장 일반적이 고 편리한 콘텐츠 패키지 방법은 <xref:System.Windows.Controls.Page>합니다. 또한 <xref:System.Windows.Controls.Page> 모양을 높이고 개발 간소화 탐색 관련 기능을 구현 합니다.

사용 하 여 <xref:System.Windows.Controls.Page>, 탐색 가능한 페이지를 선언적으로 구현할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 다음과 같은 태그를 사용 하 여 콘텐츠입니다.

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

A <xref:System.Windows.Controls.Page> 에 구현 되는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그에 `Page` 루트 요소로 하며 합니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 네임 스페이스 선언 합니다. `Page` 요소를 탐색 하 고 표시 하려는 내용을 포함 합니다. 설정 하 여 콘텐츠를 추가 합니다 `Page.Content` 속성 요소를 다음 태그에 표시 된 대로 합니다.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content`는 하나의 자식 요소만 포함할 수 있습니다. 앞의 예제에서 콘텐츠는 단일 문자열 “Hello, Page!”입니다. 실제로에서는 일반적으로 사용 하 여 레이아웃 컨트롤을 자식 요소로 (참조 [레이아웃](../advanced/layout.md)) 추가 하 고 콘텐츠를 작성 합니다.

자식 요소를 `Page` 요소 내용의 간주 되는 <xref:System.Windows.Controls.Page> 결과적으로 명시적 데 필요 하지 않습니다 `Page.Content` 선언. 다음 태그는 이전 샘플을 선언적으로 구현한 것입니다.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

이 예에서 `Page.Content` 의 자식 요소를 사용 하 여 자동으로 설정 됩니다는 `Page` 요소입니다. 자세한 내용은 [WPF 콘텐츠 모델](../controls/wpf-content-model.md)을 참조하세요.

마크업 전용 <xref:System.Windows.Controls.Page> 콘텐츠를 표시 하는 데 유용 합니다. 그러나는 <xref:System.Windows.Controls.Page> 수도 사용자가 페이지와 상호 작용할 수 있도록 표시 컨트롤 및 이벤트를 처리 하 고 응용 프로그램 논리를 호출 하 여 사용자 상호 작용에 응답할 수 있습니다. 대화형 <xref:System.Windows.Controls.Page> 다음 예와에서 같이 태그 및 코드 숨김의 조합을 사용 하 여 구현 됩니다.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

태그 파일 및 코드 숨김 파일을 함께 사용하려면 다음과 같은 구성이 필요합니다.

- 태그에는 `Page` 요소에 포함 해야 합니다는 `x:Class` 특성입니다. 응용 프로그램을 빌드할 때 `x:Class` 태그에서 발생 [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)] 만들려는 `partial` 에서 파생 된 클래스 <xref:System.Windows.Controls.Page> 에 지정 된 이름을 가진는 `x:Class` 특성입니다. 추가 해야이 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 네임 스페이스 선언이 합니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). 생성 된 `partial` 구현 클래스 `InitializeComponent`, 태그에서 구현 되는 이벤트를 등록 하는 속성을 설정 하 라고 합니다.

- 코드 숨김 클래스 여야 합니다는 `partial` 으로 지정 된 된 동일한 이름 가진 클래스를 `x:Class` 태그에 특성에서 파생 되어야 합니다 <xref:System.Windows.Controls.Page>합니다. 이렇게 하면 코드 숨김 파일을 사용 하 여 연결할 수는 `partial` 응용 프로그램을 빌드할 때 태그 파일에 대해 생성 된 클래스 (참조 [WPF 응용 프로그램 빌드](building-a-wpf-application-wpf.md)).

- 코드 숨김에서 합니다 <xref:System.Windows.Controls.Page> 클래스에서 호출 하는 생성자를 구현 해야 합니다는 `InitializeComponent` 메서드. `InitializeComponent` 구현 파일의 생성 된 태그에서 `partial` 클래스 이벤트를 등록 하 고 태그에 정의 된 속성을 설정 합니다.

> [!NOTE]
> 새로 추가한 경우 <xref:System.Windows.Controls.Page> 를 사용 하 여 프로젝트 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]는 <xref:System.Windows.Controls.Page> 태그와 코드 숨김을 모두 사용 하 여 구현 됩니다으로 태그 및 코드 숨김 파일 간의 연결을 만들려면 필요한 구성을 포함 하 고 여기서 설명합니다.

만든 후를 <xref:System.Windows.Controls.Page>를 탐색할 수 있습니다. 첫 번째 지정할 <xref:System.Windows.Controls.Page> 으로 이동 하는 응용 프로그램을 시작 구성 해야 <xref:System.Windows.Controls.Page>합니다.

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>시작 페이지 구성

[!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]를 사용하려면 브라우저에 특정 규모의 응용 프로그램 인프라가 호스트되어야 합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]서 <xref:System.Windows.Application> 필요한 응용 프로그램 인프라를 설정 하는 응용 프로그램 정의의 일부인 클래스 (참조 [응용 프로그램 관리 개요](application-management-overview.md)).

응용 프로그램 정의 일반적으로 태그와 코드 숨김으로 구성 된 태그 파일과 함께 사용 하 여 구현 된 [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] `ApplicationDefinition` 항목입니다. 다음은 응용 프로그램에 대 한 정의 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]합니다.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

[!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 시작을 지정 하려면 해당 응용 프로그램 정의 사용할 수 <xref:System.Windows.Controls.Page>, 되는 <xref:System.Windows.Controls.Page> 때 자동으로 로드 되는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 시작 됩니다. 설정 하 여이 작업을 수행 합니다 <xref:System.Windows.Application.StartupUri%2A> 속성을 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 원하는 대 한 <xref:System.Windows.Controls.Page>.

> [!NOTE]
> 대부분의 경우에는 <xref:System.Windows.Controls.Page> 컴파일 중 하나 또는 응용 프로그램을 사용 하 여 배포 합니다. 이러한 경우에는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 식별 하는 <xref:System.Windows.Controls.Page> 는 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 를 준수 하는 *팩* 구성표입니다. 팩 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 설명에 대 한 자세한 [WPF의 Pack Uri](pack-uris-in-wpf.md)합니다. 아래에 설명된 http 체계를 사용하여 콘텐츠를 탐색할 수도 있습니다.

설정할 수 있습니다 <xref:System.Windows.Application.StartupUri%2A> 다음 예와에서 같이 태그에서 선언적으로 합니다.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

이 예제는 `StartupUri` 특성이 상대 pack으로 설정 된 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] HomePage.xaml을 식별 하는 합니다. 경우는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 은 시작 부분으로 구성 되어 자동으로 탐색 되 고 표시 합니다. 보여 주는 다음 그림에서 보여를 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 웹 서버에서 실행 된 합니다.

![XBAP 페이지](./media/navigation-overview/xbap-launched-from-a-web-server.png "웹 서버에서 시작 된 XBAP 보여 줍니다.")

> [!NOTE]
> 개발 및 배포에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]를 참조 하세요 [WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md) 하 고 [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)합니다.

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>호스트 창 제목, 너비 및 높이 구성

앞의 그림에서 알 수 있습니다 하는 것은 브라우저와 탭 패널의 제목을 합니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]합니다. 이 제목은 길이가 길며 모양이나 정보 제공 측면 모두에서 그다지 유용하지 않습니다. 이러한 이유로 <xref:System.Windows.Controls.Page> 설정 하 여 제목을 변경 하는 방법을 제공 합니다 <xref:System.Windows.Controls.Page.WindowTitle%2A> 속성입니다. 설정 하 여 브라우저 창의 높이 너비를 구성할 수는 또한 <xref:System.Windows.Controls.Page.WindowWidth%2A> 고 <xref:System.Windows.Controls.Page.WindowHeight%2A>, 각각.

<xref:System.Windows.Controls.Page.WindowTitle%2A>를 <xref:System.Windows.Controls.Page.WindowWidth%2A>, 및 <xref:System.Windows.Controls.Page.WindowHeight%2A> 설정할 수 있습니다 선언적 태그에서 다음 예와에서 같이 합니다.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

결과는 다음 그림에 나와 있습니다.

![창 제목, 높이, 너비](./media/navigation-overview/window-title-width-height.png "표시 창 제목, 높이 및 너비를 구성할 수 있습니다.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>하이퍼링크 탐색

일반적인 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 여러 페이지로 구성 됩니다. 다른 페이지 간에 탐색 하는 가장 간단한 방법은 사용 하는 것을 <xref:System.Windows.Documents.Hyperlink>입니다. 선언적으로 추가할 수 있습니다는 <xref:System.Windows.Documents.Hyperlink> 에 <xref:System.Windows.Controls.Page> 를 사용 하 여를 `Hyperlink` 다음 태그에 표시 되는 요소.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

`Hyperlink` 요소는 다음이 필요 합니다.

- Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 의 <xref:System.Windows.Controls.Page> 탐색할에 지정 된 대로 `NavigateUri` 특성.

- 텍스트 및 이미지와 같은 탐색을 시작 하는 사용자가 클릭할 수는 콘텐츠 (콘텐츠는 `Hyperlink` 요소 참조에 포함 될 수 <xref:System.Windows.Documents.Hyperlink>).

다음 그림에서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 사용 하 여는 <xref:System.Windows.Controls.Page> 있는 <xref:System.Windows.Documents.Hyperlink>입니다.

![하이퍼링크가 있는 페이지](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "하이퍼링크를 사용 하 여 페이지와 XBAP 보여 줍니다.")

짐작할 수를 클릭 하는 <xref:System.Windows.Documents.Hyperlink> 하면를 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 이동할 합니다 <xref:System.Windows.Controls.Page> 으로 식별 되는 `NavigateUri` 특성. 또한 합니다 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 이전에 대 한 항목을 추가 <xref:System.Windows.Controls.Page> 최근 페이지 목록에 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]입니다. 다음 그림에서 이를 확인할 수 있습니다.

![뒤로 및 앞으로 단추](./media/navigation-overview/back-and-forward-navigation.png "뒤로 및 앞으로 단추를 사용 하 여 탐색 합니다.")

탐색을 지원할 뿐만 아니라 <xref:System.Windows.Controls.Page> 간에 <xref:System.Windows.Documents.Hyperlink> 조각 탐색도 지원 합니다.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>조각 탐색

*조각 탐색* 중 하나에 있는 콘텐츠 조각 탐색은 현재 <xref:System.Windows.Controls.Page> 또는 다른 <xref:System.Windows.Controls.Page>합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 콘텐츠 조각은 명명된 된 요소에 포함 된 내용입니다. 명명 된 요소를 가진 요소는 해당 `Name` 특성이 설정 합니다. 다음 태그는 명명 된 표시 `TextBlock` 콘텐츠 조각이 포함 된 요소입니다.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

에 대 한는 <xref:System.Windows.Documents.Hyperlink> 콘텐츠 조각으로 이동 하는 `NavigateUri` 특성은 다음을 포함 해야 합니다.

- 합니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 의 <xref:System.Windows.Controls.Page> 탐색할 콘텐츠 조각이 있는 합니다.

- “#” 문자입니다.

- 요소의 이름을 <xref:System.Windows.Controls.Page> 콘텐츠 조각이 포함 된 합니다.

조각 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 형식은 다음과 같습니다.

*PageURI* `#` *ElementName*

다음 예제는 `Hyperlink` 콘텐츠 조각을 탐색 하도록 구성 된 합니다.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> 이 섹션에서는 설명의 기본 조각 탐색 구현 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 처리 해야 하는 자체 조각 탐색 체계를 구현할 수 있습니다는 <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> 이벤트입니다.

> [!IMPORTANT]
> 느슨한에서 조각을 탐색할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지 (태그만 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일을 `Page` 루트 요소로)를 통해 페이지를 찾아볼 수 있는 경우에 [!INCLUDE[TLA2#tla_http](../../../../includes/tla2sharptla-http-md.md)]합니다.
>
> 그러나 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지에서 자체 조각을 탐색할 수 있습니다.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>탐색 서비스

하는 동안 <xref:System.Windows.Documents.Hyperlink> 특정 탐색을 시작할 수 있습니다 <xref:System.Windows.Controls.Page>, 찾기 및 다운로드 페이지의 작업은 수행 된 <xref:System.Windows.Navigation.NavigationService> 클래스입니다. 기본적으로 <xref:System.Windows.Navigation.NavigationService> 와 같은 클라이언트 코드를 대신 하 여 탐색 요청을 처리 하는 기능을 제공 합니다 <xref:System.Windows.Documents.Hyperlink>합니다. 또한 <xref:System.Windows.Navigation.NavigationService> 추적 하 고 탐색 요청에 영향을 주는 높은 수준의 지원을 구현 합니다.

경우는 <xref:System.Windows.Documents.Hyperlink> 를 클릭 하면 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 호출 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 찾고 다운로드 하는 <xref:System.Windows.Controls.Page> 지정 팩 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다. 다운로드 한 <xref:System.Windows.Controls.Page> 트리 루트 개체가 다운로드 한 인스턴스의 개체를 변환할 <xref:System.Windows.Controls.Page>합니다. 루트에 대 한 참조가 <xref:System.Windows.Controls.Page> 개체에 저장 됩니다는 <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> 속성입니다. Pack [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 탐색 된 콘텐츠가 저장 됩니다에 대 한는 <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> 속성을 하는 동안는 <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> 팩이 저장 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 탐색 된 마지막 페이지에 대 한 합니다.

> [!NOTE]
> 에 대 한 수를 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 둘 이상의 현재 활성 <xref:System.Windows.Navigation.NavigationService>합니다. 자세한 내용은 [탐색 호스트](#Navigation_Hosts) 이 항목의에서 뒷부분에 있습니다.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>탐색 서비스를 사용하여 프로그래밍 방식으로 탐색

에 대해 알아야 할 필요가 없습니다 <xref:System.Windows.Navigation.NavigationService> 탐색 사용 하 여 태그에서 선언적으로 구현 된 경우 <xref:System.Windows.Documents.Hyperlink>이므로 <xref:System.Windows.Documents.Hyperlink> 사용 하는 <xref:System.Windows.Navigation.NavigationService> 귀하를 대신해 합니다. 즉, 평균적으로 직접 또는 간접 부모를 <xref:System.Windows.Documents.Hyperlink> 탐색 호스트 (참조 [탐색 호스트](#Navigation_Hosts)), <xref:System.Windows.Documents.Hyperlink> 찾고 탐색 호스트 탐색 서비스를 사용 하 여 처리 하는 일을 할 수는 탐색 요청입니다.

그러나 일부 경우에 사용 해야 할 <xref:System.Windows.Navigation.NavigationService> 직접 다음을 비롯 한:

- 인스턴스화해야 할 때를 <xref:System.Windows.Controls.Page> 기본이 아닌 생성자를 사용 합니다.

- 속성을 설정 해야 하는 경우는 <xref:System.Windows.Controls.Page> 탐색 하기 전에 합니다.

- 경우는 <xref:System.Windows.Controls.Page> 필요를 탐색할 수만 결정할 수 있도록 런타임 시.

이러한 상황에서는 프로그래밍 방식으로 호출 하 여 탐색을 시작 하는 코드를 작성 해야 합니다 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 메서드는 <xref:System.Windows.Navigation.NavigationService> 개체입니다. 에 대 한 참조 필요로 하는 <xref:System.Windows.Navigation.NavigationService>합니다.

#### <a name="getting-a-reference-to-the-navigationservice"></a>NavigationService에 대한 참조 가져오기

에 설명 되어 있는 이유로 합니다 [탐색 호스트](#Navigation_Hosts) 섹션을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 둘 이상의 <xref:System.Windows.Navigation.NavigationService>합니다. 이 코드를 찾는 방법을 해야 함을 의미는 <xref:System.Windows.Navigation.NavigationService>, 일반적으로 <xref:System.Windows.Navigation.NavigationService> 는 현재 탐색 <xref:System.Windows.Controls.Page>합니다. 에 대 한 참조를 가져올 수 있습니다는 <xref:System.Windows.Navigation.NavigationService> 를 호출 하 여 합니다 `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> 메서드. 가져올는 <xref:System.Windows.Navigation.NavigationService> 특정 탐색 하는 <xref:System.Windows.Controls.Page>에 대 한 참조를 전달 합니다 <xref:System.Windows.Controls.Page> 의 인수로 <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> 메서드. 다음 코드를 가져오는 방법을 보여 줍니다 합니다 <xref:System.Windows.Navigation.NavigationService> 현재 <xref:System.Windows.Controls.Page>합니다.

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

찾기에 대 한 바로 가기로 <xref:System.Windows.Navigation.NavigationService> 에 대 한는 <xref:System.Windows.Controls.Page>, <xref:System.Windows.Controls.Page> 구현 하는 <xref:System.Windows.Controls.Page.NavigationService%2A> 속성. 다음 예제에서 이를 확인할 수 있습니다.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> <xref:System.Windows.Controls.Page> 에 대 한 참조를 가져올 수만 해당 <xref:System.Windows.Navigation.NavigationService> 때 <xref:System.Windows.Controls.Page> 발생 시킵니다는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트.

#### <a name="programmatic-navigation-to-a-page-object"></a>프로그래밍 방식으로 Page 개체 탐색

다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Navigation.NavigationService> 프로그래밍 방식으로 이동할 수는 <xref:System.Windows.Controls.Page>합니다. 때문에 프로그래밍 방식으로 탐색이 필요를 <xref:System.Windows.Controls.Page> 즉 탐색 중인 인스턴스화할 수는 단일, 기본이 아닌 생성자를 사용 합니다. <xref:System.Windows.Controls.Page> 기본이 아닌 생성자를 사용 하 여 다음 마크업 및 코드에 표시 됩니다.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

<xref:System.Windows.Controls.Page> 를 탐색 하는 <xref:System.Windows.Controls.Page> 기본이 아닌 생성자를 사용 하 여 다음 마크업 및 코드에 표시 됩니다.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

때를 <xref:System.Windows.Documents.Hyperlink> 이 <xref:System.Windows.Controls.Page> 는 클릭 탐색 인스턴스화하여 시작 되는 <xref:System.Windows.Controls.Page> 기본값이 아닌 생성자를 사용 하 여 호출로 이동 하는 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 메서드. <xref:System.Windows.Navigation.NavigationService.Navigate%2A> 개체에 대 한 참조를 허용 하는 <xref:System.Windows.Navigation.NavigationService> 팩을 하는 대신,로 이동 됩니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]합니다.

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Pack URI를 사용하여 프로그래밍 방식으로 탐색

팩을 생성 하는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 프로그래밍 방식으로 (경우 pack만 확인할 수 있습니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 런타임에, 예를 들어)를 사용할 수는 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 메서드. 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>현재 페이지 새로 고침

A <xref:System.Windows.Controls.Page> 동일한 팩 있으면 다운로드 되지 않습니다 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 팩과 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 저장 된는 <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> 속성입니다. 강제로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 현재 페이지를 다시 다운로드 하려면 호출할 수 있습니다는 <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> 메서드를 다음 예제에서와 같이 합니다.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>탐색 수명

지금까지 본 것처럼 탐색을 시작하는 방법은 여러 가지가 있습니다. 탐색 시작 되 고 추적 하 고에서 구현 되는 다음 이벤트를 사용 하 여 탐색에 영향을 줄 수 탐색 진행에서 중일 때 <xref:System.Windows.Navigation.NavigationService>:

- <xref:System.Windows.Navigation.NavigationService.Navigating>. 새 탐색이 요청되면 발생합니다. 탐색을 취소하는 데 사용될 수 있습니다.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. 탐색 진행 정보를 제공하기 위해 다운로드하는 동안 정기적으로 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. 페이지를 찾아서 다운로드할 때 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. 탐색을 중지할 때 발생 (호출 하 여 <xref:System.Windows.Navigation.NavigationService.StopLoading%2A>), 또는 현재 탐색이 진행에서 되는 동안 새 탐색이 요청 하는 경우.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. 요청된 콘텐츠를 탐색하는 동안 오류가 있으면 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. 탐색된 콘텐츠가 로드 및 구문 분석되고 렌더링을 시작할 때 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. 다음과 같이 콘텐츠 조각에 대한 탐색이 시작될 때 발생합니다.

  - 원하는 조각이 현재 콘텐츠에 있는 경우 즉시

  - 소스 콘텐츠를 로드한 후 다른 콘텐츠에 원하는 조각이 있는 경우

탐색 이벤트는 다음 그림과 같이 순서대로 발생합니다.

![페이지 탐색 흐름 차트](./media/navigation-overview/order-of-navigation-events.png "페이지 탐색 이벤트 흐름 차트")

일반적으로 <xref:System.Windows.Controls.Page> 이러한 이벤트는 관련이 없습니다. 응용 프로그램은 관련를 따라서 이러한도에서이 이벤트가 발생 가능성이 높습니다는 <xref:System.Windows.Application> 클래스:

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

때마다 <xref:System.Windows.Navigation.NavigationService> 이벤트가 발생 된 <xref:System.Windows.Application> 클래스에는 해당 이벤트를 발생 시킵니다. <xref:System.Windows.Controls.Frame> 및 <xref:System.Windows.Navigation.NavigationWindow> 해당 범위 내에서 탐색을 검색할 동일한 이벤트를 제공 합니다.

일부 경우에는 <xref:System.Windows.Controls.Page> 이러한 이벤트에 관심이 있을 수 있습니다. 예를 들어를 <xref:System.Windows.Controls.Page> 처리할 수도 있습니다는 <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> 자체 탐색을 취소할지 여부를 결정 하는 이벤트입니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

탐색 이벤트로 처리기를 등록 하는 경우는 <xref:System.Windows.Controls.Page>, 앞의 예제와 마찬가지로, 또한 등록을 취소 해야 이벤트 처리기입니다. 그렇지 않으면 의도 하지 않은 방법이 있을 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 탐색 기억 <xref:System.Windows.Controls.Page> 저널을 사용 하 여 탐색 합니다.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>저널을 사용하여 탐색 기억

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 두 개의 스택(뒤로 스택 및 앞으로 스택)을 사용하여 탐색한 페이지를 기억합니다. 현재에서 이동 하면 <xref:System.Windows.Controls.Page> 새 <xref:System.Windows.Controls.Page> 앞쪽 이나 뒤쪽으로 기존 <xref:System.Windows.Controls.Page>, 현재 <xref:System.Windows.Controls.Page> 에 추가 되는 *백 스택*. 현재에서 이동 하는 경우 <xref:System.Windows.Controls.Page> 이전에 다시 <xref:System.Windows.Controls.Page>, 현재 <xref:System.Windows.Controls.Page> 에 추가 되는 *앞으로 스택*합니다. 뒤로 스택, 앞으로 스택 및 이들을 관리하는 기능을 총칭하여 저널이라고 합니다. 뒤로 스택 및 앞으로 스택의 각 항목은의 인스턴스를 <xref:System.Windows.Navigation.JournalEntry> 클래스 및 라고는 *업무 일지 항목*합니다.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Internet Explorer에서 저널 탐색

개념적으로 저널 작동 동일한 방식으로 **다시** 및 **전달** 단추의 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 수행 합니다. 다음 그림을 참조하세요.

![뒤로 및 앞으로 단추](./media/navigation-overview/back-and-forward-navigation.png "뒤로 및 앞으로 단추를 사용 하 여 탐색 합니다.")

에 대 한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 에서 호스팅되고 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]를 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 저널 탐색 통합 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 의 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]합니다. 따라서 사용자 페이지를 탐색할 수 있습니다는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 를 사용 하 여는 **다시**, **앞으로**, 및 **최근 페이지** 단추의 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]합니다. 저널에 통합 되어 있지 [!INCLUDE[TLA2#tla_ie6](../../../../includes/tla2sharptla-ie6-md.md)] 는 동일한 방식으로 [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)] 또는 Internet Explorer 8입니다. 대신 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 는 대체 탐색 렌더링 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.

> [!IMPORTANT]
> [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], 사용자에서 다른 위치로 이동 하면, 다시는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]를 활성 상태로 유지 된 페이지의 저널 항목만 저널에 유지 됩니다. 페이지를 활성 상태로 유지에 대 한 자세한 내용은 참조 하세요. [페이지 수명 및 저널](#PageLifetime) 이 항목의에서 뒷부분에 있습니다.

기본적으로 각각에 대 한 텍스트 <xref:System.Windows.Controls.Page> 에 나타나는 합니다 **최근 페이지** 목록을 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한는 <xref:System.Windows.Controls.Page>합니다. 대부분의 경우 이는 사용자에게 특히 의미가 없습니다. 다행히도 다음 옵션 중 하나를 사용하여 텍스트를 변경할 수 있습니다.

1. 연결 된 `JournalEntry.Name` 특성 값입니다.

2. `Page.Title` 특성 값입니다.

3. 합니다 `Page.WindowTitle` 특성 값 및 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 현재 <xref:System.Windows.Controls.Page>합니다.

4. 현재 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]에 대한 <xref:System.Windows.Controls.Page>입니다. (기본값)

옵션이 나열되는 순서는 텍스트를 찾는 우선 순위와 일치합니다. 예를 들어 경우 `JournalEntry.Name` 설정, 다른 값이 무시 됩니다.

다음 예제에서는 `Page.Title` 저널 항목에 표시 되는 텍스트를 변경 하는 특성입니다.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>WPF를 사용하여 저널 탐색

사용자를 사용 하 여 저널을 탐색할 수 있지만 합니다 **다시**, **전달**, 및 **최근 페이지** 에서 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], 둘 다를 사용 하 여 저널을 탐색할 수 있습니다 제공 하는 선언적 및 프로그래밍 방식 메커니즘 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다. 이렇게 하려면 한 가지 이유는 사용자 지정 탐색을 제공 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] 페이지에 있습니다.

에 의해 노출 되는 탐색 명령을 사용 하 여 저널 탐색 지원을 선언적으로 추가할 수 있습니다 <xref:System.Windows.Input.NavigationCommands>합니다. 다음 예제에서는 사용 하는 방법에 설명 합니다 `BrowseBack` 탐색 명령입니다.

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

다음 멤버 중 하나를 사용 하 여 프로그래밍 방식으로 저널을 탐색할 수 있습니다는 <xref:System.Windows.Navigation.NavigationService> 클래스:

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

저널을 프로그래밍 방식으로에 설명 된 대로 조작할 수도 있습니다 [탐색 기록을 사용 하 여 콘텐츠 상태 유지](#RetainingContentStateWithNavigationHistory) 이 항목의에서 뒷부분에 있습니다.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>페이지 수명 및 저널

고려해 야는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 풍부한 콘텐츠가 포함 된 여러 페이지를 사용 하 여 그래픽, 애니메이션 및 미디어를 포함 합니다. 이와 같은 페이지의 메모리 사용량은 특히 비디오 및 오디오 미디어가 사용될 경우 매우 클 수 있습니다. 저널 탐색 된 페이지 "기억" 하는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 꽤 많은 메모리를 신속 하 게 소비할 수 있습니다.

이 이유로 저널의 기본 동작을 저장 하는 <xref:System.Windows.Controls.Page> 메타 데이터에 대 한 참조가 아니라 각 저널 항목에는 <xref:System.Windows.Controls.Page> 개체입니다. 저널 항목을 탐색 하는 경우 해당 <xref:System.Windows.Controls.Page> 메타 데이터는 지정 된 새 인스턴스를 만드는 데 <xref:System.Windows.Controls.Page>합니다. 결과적으로 각 <xref:System.Windows.Controls.Page> 를 탐색 하는 다음 그림에 나와 있는 수명이 있습니다.

![페이지 수명](./media/navigation-overview/navigated-page-lifetime.png "페이지를 탐색 하는 경우 수명은 보여 줍니다.")

기본 저널링 동작을 사용 하 여 메모리 사용량에 대해 저장할 수, 있지만 페이지당 렌더링 성능이 저하 될 수 있습니다. 재초기화를 <xref:System.Windows.Controls.Page> 시간이 많이, 특히 콘텐츠가 많은 경우를 수 있습니다. 유지 해야 하는 경우는 <xref:System.Windows.Controls.Page> 인스턴스 저널, 이렇게 두 가지 기술을 그릴 수 있습니다. 먼저, 프로그래밍 방식으로 이동할 수는 <xref:System.Windows.Controls.Page> 를 호출 하 여 개체를 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 메서드.

둘째, 지정할 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 의 인스턴스를 보유를 <xref:System.Windows.Controls.Page> 설정 하 여 저널에는 <xref:System.Windows.Controls.Page.KeepAlive%2A> 속성을 `true` (기본값은 `false`). 설정할 수 있습니다 다음 예제에서와 같이 <xref:System.Windows.Controls.Page.KeepAlive%2A> 태그에서 선언적으로 합니다.

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

기간을 <xref:System.Windows.Controls.Page> 즉 활성 상태로 유지 하는 경우이 없는 약간 다릅니다. 처음으로 <xref:System.Windows.Controls.Page> 유지 되는 연결 유지가 탐색, 마찬가지로 인스턴스화될는 <xref:System.Windows.Controls.Page> 활성 상태로 유지 되지 않는 합니다. 그러나 때문에 인스턴스에 <xref:System.Windows.Controls.Page> 유지 됩니다 저널에 인스턴스화되지 않습니다 다시에 대 한 업무 일지에 보관으로 합니다. 결과적으로 경우는 <xref:System.Windows.Controls.Page> 때마다 호출 해야 하는 초기화 논리가 합니다 <xref:System.Windows.Controls.Page> 탐색할 해야에서 이동 하 고 생성자에 대 한 처리기를는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트. 다음 그림에 표시 된 대로 합니다 <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.FrameworkElement.Unloaded> 이벤트는 여전히 될 때마다 발생을 <xref:System.Windows.Controls.Page> 탐색할 각각.

![Loaded 및 Unloaded 이벤트 발생 시기](./media/navigation-overview/loaded-and-unloaded-events.png "Loaded 및 unloaded 이벤트 페이지를 탐색할 때 발생 합니다.")

경우는 <xref:System.Windows.Controls.Page> 은 활성 상태로 유지 되지 해야 다음 중 하나:

- 이 페이지 또는 이 페이지의 일부에 대한 참조 저장

- 이벤트 처리기를 이 페이지에서 구현되지 않는 이벤트에 등록

이 중 하나를 수행 하는 참조가 만들어집니다.는 <xref:System.Windows.Controls.Page> 저널에서 제거 된 후에 메모리에 보존 합니다.

일반적으로 기본 높여야 <xref:System.Windows.Controls.Page> 유지 하지 않는 동작을 <xref:System.Windows.Controls.Page> 유지 합니다. 그러나 이는 다음 절에서 설명하는 상태 의미와 관련이 있습니다.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>탐색 기록을 사용하여 콘텐츠 상태 유지

경우는 <xref:System.Windows.Controls.Page> 은 활성 상태로 유지 되지 사용자에서 다른 위치로 이동 하는 경우 그리고 다시 데이터에 어떻게 사용자 로부터 데이터를 수집 하는 컨트롤이 있는 및은 <xref:System.Windows.Controls.Page>? 경험을 바탕으로 사용자는 이전에 입력한 데이터가 표시될 것이라고 예상합니다. 아쉽게도 있으므로의 새 인스턴스를 <xref:System.Windows.Controls.Page> 각 탐색을 다시 인스턴스화되어 수집 된 데이터는 시간 및 데이터가 손실 되는 컨트롤을 사용 하 여 만들어집니다.

다행 스럽게도 저널 지에서 데이터를 기억 하기 위해 <xref:System.Windows.Controls.Page> 컨트롤 데이터를 포함 하 여 탐색 합니다. 각각에 대 한 업무 일지 항목 특히 <xref:System.Windows.Controls.Page> 연결 된 임시 컨테이너 역할을 <xref:System.Windows.Controls.Page> 상태입니다. 다음 단계에서는이 지원을 사용 하는 방법을 간략하게 설명 때를 <xref:System.Windows.Controls.Page> 에서 탐색:

1. 현재 항목 <xref:System.Windows.Controls.Page> 저널에 추가 됩니다.

2. 상태는 <xref:System.Windows.Controls.Page> 뒤로 스택에 추가 되는 페이지에 대 한 저널 항목과 함께 저장 됩니다.

3. 새 <xref:System.Windows.Controls.Page> 가 탐색 됩니다.

때 페이지 <xref:System.Windows.Controls.Page> 는 뒤로 탐색 하 여 저널을 사용 하 여 다음 단계를 수행 합니다.

1. <xref:System.Windows.Controls.Page> (뒤로 스택의 맨 위 저널 항목) 인스턴스화됩니다.

2. 합니다 <xref:System.Windows.Controls.Page> 에 대 한 저널 항목과 함께 저장 된 상태를 사용 하 여 새로 고쳐집니다는 <xref:System.Windows.Controls.Page>합니다.

3. <xref:System.Windows.Controls.Page> 가 다시 탐색 합니다.

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다음 컨트롤에서 사용 하는 경우이 지원을 자동으로 사용 된 <xref:System.Windows.Controls.Page>:

- <xref:System.Windows.Controls.CheckBox>

- <xref:System.Windows.Controls.ComboBox>

- <xref:System.Windows.Controls.Expander>

- <xref:System.Windows.Controls.Frame>

- <xref:System.Windows.Controls.ListBox>

- <xref:System.Windows.Controls.ListBoxItem>

- <xref:System.Windows.Controls.MenuItem>

- <xref:System.Windows.Controls.ProgressBar>

- <xref:System.Windows.Controls.RadioButton>

- <xref:System.Windows.Controls.Slider>

- <xref:System.Windows.Controls.TabControl>

- <xref:System.Windows.Controls.TabItem>

- <xref:System.Windows.Controls.TextBox>

경우는 <xref:System.Windows.Controls.Page> 사용 하 여 이러한 컨트롤을 해당 입력 데이터에서 기억 됩니다 <xref:System.Windows.Controls.Page> 탐색에 나타난 것 처럼 합니다 **좋아하는 색** <xref:System.Windows.Controls.ListBox> 다음 그림에 합니다.

![페이지 상태를 기억 하는 컨트롤로](./media/navigation-overview/data-remembered-across-page-navigations.png "입력 된 데이터 페이지 탐색 간에 기억 됩니다.")

경우는 <xref:System.Windows.Controls.Page> 위의 목록 이외의 컨트롤이 했거나 저널에서 상태를 기억 하도록 코드를 작성 해야 하는 상태는 사용자 지정 개체에 저장 하는 경우 <xref:System.Windows.Controls.Page> 탐색 합니다.

소량의 간에 상태를 기억해 야 하는 경우 <xref:System.Windows.Controls.Page> 탐색을 종속성 속성을 사용할 수 있습니다 (참조 <xref:System.Windows.DependencyProperty>)으로 구성 된는 <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> 메타 데이터 플래그입니다.

경우 상태는 사용자 <xref:System.Windows.Controls.Page> 탐색에서 기억해 야의 여러 가지 데이터를 구성 하는 경우가 더 적은 코드 집약적인 단일 클래스에서 상태를 캡슐화 하 고 구현 하는 <xref:System.Windows.Navigation.IProvideCustomContentState> 인터페이스입니다.

단일의 다양 한 상태를 탐색 해야 하는 경우 <xref:System.Windows.Controls.Page>에서 이동 하지 않고 합니다 <xref:System.Windows.Controls.Page> 자체를 사용할 수 <xref:System.Windows.Navigation.IProvideCustomContentState> 및 <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType>합니다.

<a name="Cookies"></a>

### <a name="cookies"></a>쿠키

다른 방식으로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 데이터를 저장할 수 있습니다 생성 되는 쿠키를 사용 하 여 업데이트 및를 사용 하 여 삭제 되는 <xref:System.Windows.Application.SetCookie%2A> 및 <xref:System.Windows.Application.GetCookie%2A> 메서드. 만들 수 있는 쿠키 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 와 같습니다. 쿠키는 다른 유형의 웹 응용 프로그램 사용은 쿠키는 임의의 응용 프로그램에서 클라이언트 컴퓨터는 동안 이나 응용 프로그램 세션 간에 저장 된 데이터 조각입니다. 쿠키 데이터는 일반적으로 다음과 같은 이름/값 쌍 형식을 사용합니다.

*이름* `=` *값*

데이터를 전달할 때 <xref:System.Windows.Application.SetCookie%2A>를 함께 <xref:System.Uri> 쿠키를 설정 해야 하는 위치, 쿠키를 메모리에 만들어지고 에서만 사용 가능 현재 응용 프로그램 세션 기간에 대 한 합니다. 이러한 종류의 쿠키 라고 하는 *세션 쿠키*합니다.

애플리케이션 세션 간에 쿠키를 저장하려면 다음 형식을 사용하여 쿠키에 만료 날짜를 추가해야 합니다.

*이름* `=` *값* `; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

만료 날짜가 있는 쿠키에에서 저장 됩니다 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 쿠키가 만료 될 때까지 설치의 Temporary Internet Files 폴더입니다. 이러한 쿠키 라고 한 *영구 쿠키* 응용 프로그램 세션 간에 지속 되기 때문에 있습니다.

호출 하 여 세션 및 영구 쿠키를 검색 합니다 <xref:System.Windows.Application.GetCookie%2A> 메서드를 전달를 <xref:System.Uri> 쿠키를 사용 하 여 여기서 설정한 위치는 <xref:System.Windows.Application.SetCookie%2A> 메서드.

다음은 일부의 쿠키에서 지원 되는 방법을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]:

- [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 독립 실행형 응용 프로그램 및 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 수 모두 만들고 쿠키를 관리 합니다.

- 만든 쿠키는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 브라우저에서 액세스할 수 있습니다.

- 동일한 도메인의 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]에서 쿠키를 만들고 공유할 수 있습니다.

- [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 및 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 도메인의 동일한 페이지에서에서 만들고 쿠키를 공유할 수 있습니다.

- 쿠키가 디스패치 됩니다 때 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 느슨한 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 웹 요청을 수행 합니다.

- 최상위 수준 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 고 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 에 호스트 된 IFRAME 쿠키에 액세스할 수 있습니다.

- 쿠키 지원을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 모든 지원 되는 브라우저에 대해 동일 합니다.

- [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)], 쿠키와 관련 된 P3P 정책은 따라 적용 됩니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 특히 관련 하 여 자사 및 타사 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>구조적 탐색

하나에서 데이터를 전달 해야 하는 경우 <xref:System.Windows.Controls.Page> 간에 전달할 수 있습니다 데이터 인수로 기본이 아닌 생성자를 <xref:System.Windows.Controls.Page>입니다. 이 기법을 사용 하면 유지 해야 한다는 점에 유의 합니다 <xref:System.Windows.Controls.Page> ; 연결 유지 하는 경우 다음 시간이 아닌, 이동할를 <xref:System.Windows.Controls.Page>, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 다시 인스턴스화합니다는 <xref:System.Windows.Controls.Page> 기본 생성자를 사용 하 여 합니다.

또는 사용자 <xref:System.Windows.Controls.Page> 전달 되어야 하는 데이터로 설정 된 속성을 구현할 수 있습니다. 하지만 항이 복잡 해질 경우는 <xref:System.Windows.Controls.Page> 해야 다시 데이터를 전달 하는 <xref:System.Windows.Controls.Page> 탐색 하는 합니다. 문제는 탐색을 보장 하기 위해 메커니즘을 지원 하지 않습니다 기본적으로 <xref:System.Windows.Controls.Page> 에서 탐색 한 후에 반환 됩니다. 기본적으로 탐색은 호출/반환 의미 체계를 지원하지 않습니다. 이 문제를 해결 하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 제공 합니다 <xref:System.Windows.Navigation.PageFunction%601> 되어 있는지 확인 하는 데 사용할 수 있는 클래스는 <xref:System.Windows.Controls.Page> 예측 가능 하 고 구조화 된 방식으로 돌아갑니다. 자세한 내용은 [구조적 탐색 개요](structured-navigation-overview.md)합니다.

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>NavigationWindow 클래스

지금까지 탐색 가능한 콘텐츠로 애플리케이션을 빌드하는 데 가장 많이 사용되는 탐색 서비스 영역을 살펴보았습니다. 이러한 서비스의 컨텍스트에서 설명한 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]제한 되지 않지만, [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]합니다. 최신 운영 체제 및 Windows 응용 프로그램은 독립 실행형 응용 프로그램에 브라우저 스타일 탐색을 통합 하는 최신 사용자의 브라우저 환경을 활용 합니다. 일반적인 예는 다음과 같습니다.

- **동의어 사전 단어**: 선택한 단어를 탐색 합니다.

- **파일 탐색기**: 파일 및 폴더를 이동 합니다.

- **마법사**: 간에 탐색할 수 있는 여러 페이지에 복잡 한 작업을 중단 합니다. 예에는 Windows 기능 추가 및 제거를 처리 하는 Windows 구성 요소 마법사입니다.

브라우저 스타일 탐색을 독립 실행형 응용 프로그램 통합을 사용할 수 있습니다는 <xref:System.Windows.Navigation.NavigationWindow> 클래스입니다. <xref:System.Windows.Navigation.NavigationWindow> 파생 <xref:System.Windows.Window> 확장 하 고 동일한 탐색 지원을 사용 하는 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 제공 합니다. 사용할 수 있습니다 <xref:System.Windows.Navigation.NavigationWindow> 독립 실행형 응용 프로그램의 주 창 또는 대화 상자와 같은 보조 창으로 합니다.

구현 하는 <xref:System.Windows.Navigation.NavigationWindow>의 최상위 클래스와 마찬가지로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] (<xref:System.Windows.Window>, <xref:System.Windows.Controls.Page>등), 태그 및 코드 숨김 조합을 사용 하 여 합니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

이 코드에서는 <xref:System.Windows.Navigation.NavigationWindow> 자동으로 이동 하는 <xref:System.Windows.Controls.Page> (HomePage.xaml) 때를 <xref:System.Windows.Navigation.NavigationWindow> 열립니다. 경우는 <xref:System.Windows.Navigation.NavigationWindow> 가 주 응용 프로그램 창 사용할 수는 `StartupUri` 응용 프로그램을 시작 하는 특성입니다. 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

다음 그림에서는 <xref:System.Windows.Navigation.NavigationWindow> 독립 실행형 응용 프로그램의 주 창으로 합니다.

![주 창이](./media/navigation-overview/navigation-window-as-main-window.png "주 창으로 탐색 창")

그림에서 볼 수 있습니다 합니다 <xref:System.Windows.Navigation.NavigationWindow> 에 설정 되지 않은 경우에 제목에는 <xref:System.Windows.Navigation.NavigationWindow> 앞의 예제에서 구현 코드. 대신 제목을 사용 하 여 설정 됩니다는 <xref:System.Windows.Controls.Page.WindowTitle%2A> 속성을 다음 코드에 표시 됩니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

설정 합니다 <xref:System.Windows.Controls.Page.WindowWidth%2A> 하 고 <xref:System.Windows.Controls.Page.WindowHeight%2A> 속성도 영향을 줍니다는 <xref:System.Windows.Navigation.NavigationWindow>합니다.

사용자 고유의 구현 일반적으로 <xref:System.Windows.Navigation.NavigationWindow> 동작 또는 모양을 사용자 지정 해야 합니다. 두 방법을 모두 사용하지 않으려면 바로 가기를 사용할 수 있습니다. 팩을 지정 하는 경우 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 의 <xref:System.Windows.Controls.Page> 으로 <xref:System.Windows.Application.StartupUri%2A> 독립 실행형 응용 프로그램에서는 <xref:System.Windows.Application> 자동으로 만듭니다는 <xref:System.Windows.Navigation.NavigationWindow> 호스트에는 <xref:System.Windows.Controls.Page>합니다. 다음 태그에서는 이 기능을 설정하는 방법을 보여 줍니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

되도록 대화 상자와 같은 보조 응용 프로그램 창 사용 하려는 경우는 <xref:System.Windows.Navigation.NavigationWindow>를 열려는 다음 예제에서 코드를 사용할 수 있습니다.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

다음 그림에서는 결과를 보여 줍니다.

![대화 상자가](./media/navigation-overview/navigation-window-as-dialog-box.png "대화 상자로 탐색 창")

알 수 있듯이 <xref:System.Windows.Navigation.NavigationWindow> 표시 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)]-스타일 **다시** 하 고 **앞으로** 저널을 탐색할 수 있도록 하는 단추입니다. 이러한 단추는 다음 그림에 나와 있는 것처럼 동일한 사용자 환경을 제공합니다.

![뒤로 및 앞으로 단추 NavigationWindow](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "뒤로 및 앞으로 탐색 창에서 단추")

페이지 자체 저널 탐색 지원 및 UI를 제공 하는 경우 숨길 수 있습니다는 **다시** 하 고 **앞으로** 표시 하는 단추 <xref:System.Windows.Navigation.NavigationWindow> 의 값을 설정 하 여는 <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> 속성`false`.

또는의 사용자 지정 지원을 사용할 수 있습니다 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 바꾸려면 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 의 <xref:System.Windows.Navigation.NavigationWindow> 자체입니다.

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Frame 클래스

두 브라우저 및 <xref:System.Windows.Navigation.NavigationWindow> 는 창 탐색 가능한 콘텐츠를 호스트 합니다. 애플리케이션의 콘텐츠가 전체 창에서 호스트될 필요가 없는 경우가 있습니다. 대신, 이러한 콘텐츠는 다른 콘텐츠 내에 호스트됩니다. 사용 하 여 다른 콘텐츠 탐색 가능한 콘텐츠를 삽입할 수 있습니다는 <xref:System.Windows.Controls.Frame> 클래스입니다. <xref:System.Windows.Controls.Frame> 동일한 기능을 제공할 <xref:System.Windows.Navigation.NavigationWindow> 고 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]입니다.

다음 예제에서는 추가 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.Frame> 에 <xref:System.Windows.Controls.Page> 사용 하 여 선언적으로 `Frame` 요소.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

이 태그를 설정 합니다 `Source` 특성을 `Frame` 팩을 사용 하 여 요소 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 에 대 한를 <xref:System.Windows.Controls.Page> 는 <xref:System.Windows.Controls.Frame> 로 처음 이동 해야 합니다. 다음 그림에서는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 사용 하 여는 <xref:System.Windows.Controls.Page> 있는 <xref:System.Windows.Controls.Frame> 여러 페이지 사이 탐색 하는 합니다.

![여러 페이지 간에 탐색 된 프레임](./media/navigation-overview/frame-navigation-between-multiple-pages.png "여러 페이지 간에 프레임 탐색을 보여 줍니다.")

사용 하 여만 필요가 <xref:System.Windows.Controls.Frame> 콘텐츠 내에서 <xref:System.Windows.Controls.Page>합니다. 호스트에 공통적으로 적용 이기도 한 <xref:System.Windows.Controls.Frame> 콘텐츠 내에서 <xref:System.Windows.Window>합니다.

기본적으로 <xref:System.Windows.Controls.Frame> 다른 저널이 없는 경우에만 자체 저널을 사용 합니다. 경우는 <xref:System.Windows.Controls.Frame> 중 어디에 호스트 되는 콘텐츠의 일부인를 <xref:System.Windows.Navigation.NavigationWindow> 또는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)], <xref:System.Windows.Controls.Frame> 속한 저널을 사용 합니다 <xref:System.Windows.Navigation.NavigationWindow> 또는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]합니다. 경우에 따라 그러나는 <xref:System.Windows.Controls.Frame> 자체 저널을 담당 해야 할 수 있습니다. 이렇게 하려면 이유 중 하나에서 호스팅되는 페이지 내에서 저널 탐색을 허용 하는 것을 <xref:System.Windows.Controls.Frame>입니다. 다음 그림에서 이를 확인할 수 있습니다.

![프레임 및 페이지 다이어그램](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "프레임에서 호스팅되는 페이지 내에서 저널 탐색 보여 줍니다.")

여기서 구성할 수 있습니다는 <xref:System.Windows.Controls.Frame> 설정 하 여 자체 저널을 사용 하는 <xref:System.Windows.Controls.Frame.JournalOwnership%2A> 의 속성을 <xref:System.Windows.Controls.Frame> 를 <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal>. 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

다음 그림에서는 내에서 탐색할 때의 영향을 <xref:System.Windows.Controls.Frame> 자체 저널을 사용 하는 합니다.

![자체 저널을 사용 하는 프레임](./media/navigation-overview/frame-uses-its-own-journal.png "이 자체 저널을 사용 하는 프레임 내에서 탐색의 결과 보여 줍니다.")

저널 항목을 탐색 하 여 표시 되는 통지 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 <xref:System.Windows.Controls.Frame>, 보다는 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)].

> [!NOTE]
> 경우는 <xref:System.Windows.Controls.Frame> 에서 호스트 되는 콘텐츠의 일부인를 <xref:System.Windows.Window>를 <xref:System.Windows.Controls.Frame> 자체 저널을 사용 하 여 결과적으로 자체적으로 탐색을 표시 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다.

사용자 환경을 요구 하는 경우는 <xref:System.Windows.Controls.Frame> 탐색을 표시 하지 않고 자체 저널을 제공 하기 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 탐색을 숨길 수 있습니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 설정 하 여를 <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> 에 <xref:System.Windows.Visibility.Hidden>합니다. 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>탐색 호스트

<xref:System.Windows.Controls.Frame> 및 <xref:System.Windows.Navigation.NavigationWindow> 은 탐색 호스트 라고 하는 클래스입니다. A *탐색 호스트* 로 이동 하 고 콘텐츠를 표시할 수 있는 클래스입니다. 이를 위해 각 탐색 호스트는 자체 <xref:System.Windows.Navigation.NavigationService> 및 저널입니다. 다음 그림은 탐색 호스트의 기본 구성을 보여 줍니다.

![탐색기 다이어그램](./media/navigation-overview/navigation-host-construction.png "탐색 호스트의 기본 생성")

따라서 기본적 <xref:System.Windows.Navigation.NavigationWindow> 및 <xref:System.Windows.Controls.Frame> 에서도 동일한를 탐색 하는 지원는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 브라우저에서 호스트 되는 경우 제공 합니다.

사용 하는 것 외에도 <xref:System.Windows.Navigation.NavigationService> 와 저널을 동일한 멤버를 구현 하는 탐색 호스트는 <xref:System.Windows.Navigation.NavigationService> 구현 합니다. 다음 그림에서 이를 확인할 수 있습니다.

![Frame 및 NavigationWindow의 저널](./media/navigation-overview/navigation-window-and-frame.png "탐색 창과 프레임")

이를 통해 직접 탐색 지원을 프로그래밍할 수 있습니다. 사용자 지정 탐색을 제공 하는 경우이 고려할 수 있습니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 에 대 한는 <xref:System.Windows.Controls.Frame> 에서 호스팅되는 <xref:System.Windows.Window>합니다. 두 형식 모두를 추가로 탐색 관련 멤버를 포함 하 여 구현 하는 또한 `BackStack` (<xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType>를 <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType>) 및 `ForwardStack` (<xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType>, <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType>), 복구에서 저널 항목을 열거할 수 있는 스택 및 앞으로 스택, 각각.

앞서 언급했듯이 애플리케이션에는 둘 이상의 저널이 있을 수 있습니다. 다음 그림은 이러한 상황이 발생할 수 있는 예제를 제공합니다.

![한 응용 프로그램 내의 여러 저널](./media/navigation-overview/multiple-journals-in-one-application.png "응용 프로그램에서 둘 이상의 저널이의 예제입니다.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>XAML 페이지 이외의 콘텐츠 탐색

이 항목 전반 <xref:System.Windows.Controls.Page> 및 pack [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 의 다양 한 탐색 기능을 보여 주기 위해 사용 된 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]합니다. 그러나를 <xref:System.Windows.Controls.Page> 즉, 탐색할 수 있는 콘텐츠 팩을 유일한 형식이 아닙니다는 응용 프로그램으로 컴파일되고 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 콘텐츠를 식별 하는 유일한 방법도 아닙니다.

이 섹션에서 설명 하는 대로 이동할 수 있습니다도 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일인 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 파일 및 개체입니다.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>XAML 사용 완화 파일 탐색

느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 다음 특성을 가진 파일:

- 포함 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (즉, 코드 없음).

- 적절한 네임스페이스 선언이 있습니다.

- .xaml 파일 이름 확장명이 있습니다.

예를 들어 느슨한으로 저장 되는 다음 내용이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 완화 파일인 Person.xaml 합니다.

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

파일을 두 번 클릭하면 브라우저가 열리고 콘텐츠를 탐색 및 표시합니다. 다음 그림에서 이를 확인할 수 있습니다.

![Person.XAML 파일의 콘텐츠 표시](./media/navigation-overview/contents-of-person-xaml-file.png "Person.XAML 파일의 내용을 보여 줍니다.")

느슨한 표시할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 다음에서 파일:

- 로컬 컴퓨터, 인트라넷 또는 인터넷의 웹 사이트

- [!INCLUDE[TLA#tla_unc](../../../../includes/tlasharptla-unc-md.md)] 파일 공유 합니다.

- 로컬 디스크

느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 브라우저의 즐겨찾기에 추가할 수 있습니다 또는 브라우저의 홈 페이지입니다.

> [!NOTE]
> 게시 및 느슨한 시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 참조 하세요 [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)합니다.

한 가지 제한 사항이 완화와 관련 된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 는 부분 신뢰에서 실행 되도록 안전한 콘텐츠만 호스트할 수 있습니다. 예를 들어 `Window` 완화의 루트 요소가 될 수 없습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일입니다. 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>프레임을 사용하여 HTML 파일 탐색

예상할 수 있듯이 이동할 수 있습니다도 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)]합니다. 제공 하기만 하면는 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] http 체계를 사용 하는 합니다. 예를 들어, 다음 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 표시는 <xref:System.Windows.Controls.Frame> 를 탐색 하는 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 페이지입니다.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

이동할 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 특별 권한이 필요 합니다. 예를 들어에서 탐색할 수 없습니다는 [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] 에서 인터넷 영역 부분 신뢰 보안 샌드박스에서 실행 되는 합니다. 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>WebBrowser 컨트롤을 사용하여 HTML 파일 탐색

합니다 <xref:System.Windows.Controls.WebBrowser> 지원 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 문서 호스팅, 탐색 및 스크립트/관리 코드 상호 운용성. 자세한 내용은 관련 하 여는 <xref:System.Windows.Controls.WebBrowser> 제어를 참조 하십시오 <xref:System.Windows.Controls.WebBrowser>합니다.

와 같은 <xref:System.Windows.Controls.Frame>로 이동 하면 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 사용 하 여 <xref:System.Windows.Controls.WebBrowser> 특별 권한이 필요 합니다. 예를 들어 부분 신뢰 응용 프로그램을 이동할 수 있습니다만 [!INCLUDE[TLA2#tla_html](../../../../includes/tla2sharptla-html-md.md)] 원본 사이트에 있는 합니다. 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>사용자 지정 개체 탐색

해당 데이터를 표시 하는 한 가지 방법은 만들 때 데이터를 사용자 지정 개체로 저장 되는 경우는 <xref:System.Windows.Controls.Page> 해당 개체에 바인딩되는 콘텐츠를 사용 하 여 (참조 [데이터 바인딩 개요](../data/data-binding-overview.md)). 개체를 표시하기 위해 전체 페이지를 만드는 오버헤드가 필요하지 않으면 페이지를 직접 탐색할 수 있습니다.

고려해 야 합니다 `Person` 다음 코드에서 구현 되는 클래스입니다.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

이 탐색 하려면 호출 하는 <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> 메서드를 다음 코드로 표시 된 것과 같이 합니다.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

다음 그림에서는 결과를 보여 줍니다.

![클래스에 탐색 하는 페이지](./media/navigation-overview/page-navigates-to-an-object.png "개체로 이동 하는 페이지의 예제입니다.")

이 그림에서 유용한 콘텐츠가 표시되지 않는 것을 볼 수 있습니다. 사실, 표시 되는 값은 반환 값을 `ToString` 에 대 한 메서드를 **사용자** 개체는 기본적으로이 경우에 값 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 개체를 나타내는 데 사용할 수. 재정의할 수 있습니다는 `ToString` 이지만 보다 의미 있는 정보를 반환 하는 메서드는 문자열 값 이어야 합니다. 프레젠테이션 기능을 활용 하는 사용할 수 있는 한 가지 방법은 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 데이터 템플릿을 사용 하는 것입니다. 데이터 템플릿을 구현할 수 있습니다는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 특정 형식의 개체를 사용 하 여 연결할 수 있습니다. 다음 코드에 대 한 데이터 템플릿을 보여 줍니다는 `Person` 개체입니다.

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

데이터 템플릿을 연관 여기에 `Person` 형식을 사용 하 여는 `x:Type` 에서 태그 확장을 `DataType` 특성입니다. 데이터 템플릿을 바인딩합니다 `TextBlock` 요소 (참조 <xref:System.Windows.Controls.TextBlock>)의 속성에는 `Person` 클래스입니다. 다음 그림에서는 업데이트 된 모양의 `Person` 개체입니다.

![데이터 템플릿이 있는 클래스로 탐색](./media/navigation-overview/navigating-to-a-class.png "데이터 템플릿이 있는 클래스를 탐색 합니다.")

이 기술의 장점은 데이터 템플릿을 다시 사용하여 애플리케이션의 어디에서든 일관적으로 개체를 표시할 수 있다는 점입니다.

데이터 템플릿에 대 한 자세한 내용은 참조 하세요. [데이터 템플릿 개요](../data/data-templating-overview.md)합니다.

<a name="Security"></a>

## <a name="security"></a>보안

[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 탐색 지원을 통해 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] 탐색할 수 인터넷 하며 타사 콘텐츠를 호스트 응용 프로그램을 허용 합니다. 응용 프로그램과 사용자를 해로운 동작 으로부터 보호 하기 위해 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에서 설명 하는 보안 기능의 다양 한 [보안](../security-wpf.md) 하 고 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [응용 프로그램 관리 개요](application-management-overview.md)
- [WPF의 Pack URI](pack-uris-in-wpf.md)
- [구조적 탐색 개요](structured-navigation-overview.md)
- [탐색 토폴로지 개요](navigation-topologies-overview.md)
- [방법 항목](navigation-how-to-topics.md)
- [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)
