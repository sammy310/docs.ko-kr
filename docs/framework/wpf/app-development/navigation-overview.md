---
title: 탐색 개요
description: Windows Presentation Foundation (WPF)의 독립 실행형 응용 프로그램 및 XAML 브라우저 응용 프로그램에서 사용 되는 브라우저 스타일 탐색 지원에 대해 알아봅니다.
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
ms.openlocfilehash: 2aac1b3a38b6240bfba1b90983fd9cbd18b31b6f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621706"
---
# <a name="navigation-overview"></a>탐색 개요

WPF (Windows Presentation Foundation)는 독립 실행형 응용 프로그램 및 Xbap (XAML 브라우저 응용 프로그램) 라는 두 가지 유형의 응용 프로그램에서 사용할 수 있는 브라우저 스타일 탐색을 지원 합니다. 탐색을 위해 콘텐츠를 패키징하는 WPF는 클래스를 제공 합니다 <xref:System.Windows.Controls.Page> . 를 사용 하거나를 사용 하 여 프로그래밍 방식으로 한 개에서 다른 방식으로 탐색할 수 있습니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> . WPF는 저널을 사용 하 여 탐색 된 페이지를 검색 하 고 다시 탐색 합니다.

<xref:System.Windows.Controls.Page>, <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Navigation.NavigationService> 및 저널은 WPF에서 제공 하는 탐색 지원의 핵심을 형성 합니다. 이 개요에서는 느슨한 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일, HTML 파일 및 개체에 대 한 탐색이 포함 된 고급 탐색 지원을 포함 하기 전에 이러한 기능을 자세히 설명 합니다.

> [!NOTE]
> 이 항목에서 "browser" 라는 용어는 현재 Microsoft Internet Explorer 및 Firefox를 포함 하는 WPF 응용 프로그램을 호스팅할 수 있는 브라우저만 나타냅니다. 특정 WPF 기능이 특정 브라우저 에서만 지원 되는 경우 브라우저 버전을 라고 합니다.

## <a name="navigation-in-wpf-applications"></a>WPF 애플리케이션에서 탐색

이 항목에서는 WPF의 주요 탐색 기능에 대 한 개요를 제공 합니다. 이러한 기능은 독립 실행형 응용 프로그램과 Xbap 모두에서 사용할 수 있지만이 항목에서는 XBAP 컨텍스트 내에서 이러한 기능을 제공 합니다.

> [!NOTE]
> 이 항목에서는 Xbap를 빌드하고 배포 하는 방법에 대해서는 설명 하지 않습니다. Xbap에 대 한 자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md)를 참조 하세요.

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

WPF에서 .NET Framework 개체, 사용자 지정 개체, 열거형 값, 사용자 컨트롤, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 및 HTML 파일을 포함 하는 여러 콘텐츠 형식으로 이동할 수 있습니다. 그러나를 사용 하 여 콘텐츠를 가장 일반적이 고 편리한 방식으로 패키지할 수 있습니다 <xref:System.Windows.Controls.Page> . 또한에서는 <xref:System.Windows.Controls.Page> 탐색 관련 기능을 구현 하 여 모양을 개선 하 고 개발을 간소화 합니다.

를 사용 하 여 <xref:System.Windows.Controls.Page> 다음과 같은 태그를 사용 하 여 탐색 가능한 콘텐츠 페이지를 선언적으로 구현할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

[!code-xaml[NavigationOverviewSnippets#Page1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page1.xaml#page1xaml)]

<xref:System.Windows.Controls.Page>태그에서 구현 되는은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `Page` 루트 요소로 되어 있고 WPF XML 네임 스페이스 선언이 필요 합니다. `Page`요소는 탐색 하 고 표시 하려는 콘텐츠를 포함 합니다. 다음 태그와 같이 property 요소를 설정 하 여 콘텐츠를 추가 `Page.Content` 합니다.

[!code-xaml[NavigationOverviewSnippets#Page2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page2.xaml#page2xaml)]

`Page.Content`는 하나의 자식 요소만 포함할 수 있습니다. 앞의 예제에서 콘텐츠는 단일 문자열 “Hello, Page!”입니다. 실제로 레이아웃 컨트롤을 자식 요소 ( [레이아웃](../advanced/layout.md)참조)로 사용 하 여 콘텐츠를 포함 하 고 작성 하는 것이 일반적입니다.

요소의 자식 요소는 `Page` 의 콘텐츠로 간주 되며, <xref:System.Windows.Controls.Page> 따라서 명시적 선언을 사용할 필요가 없습니다 `Page.Content` . 다음 태그는 이전 샘플을 선언적으로 구현한 것입니다.

[!code-xaml[NavigationOverviewSnippets#Page3XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Page3.xaml#page3xaml)]

이 경우 `Page.Content` 는 요소의 자식 요소를 사용 하 여 자동으로 설정 됩니다 `Page` . 자세한 내용은 [WPF 콘텐츠 모델](../controls/wpf-content-model.md)을 참조 하세요.

태그 전용은 콘텐츠를 표시 하는 데 <xref:System.Windows.Controls.Page> 유용 합니다. 그러나은 <xref:System.Windows.Controls.Page> 사용자가 페이지와 상호 작용할 수 있도록 하는 컨트롤을 표시할 수도 있으며, 이벤트를 처리 하 고 응용 프로그램 논리를 호출 하 여 사용자 상호 작용에 응답할 수 있습니다. 대화형 <xref:System.Windows.Controls.Page> 은 다음 예제에 표시 된 것과 같이 태그와 코드 숨김으로 이루어진 조합을 사용 하 여 구현 됩니다.

[!code-xaml[XBAPAppDefSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml#homepagemarkup)]

[!code-csharp[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/HomePage.xaml.cs#homepagecodebehind)]
[!code-vb[XBAPAppDefSnippets#HomePageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/HomePage.xaml.vb#homepagecodebehind)]

태그 파일 및 코드 숨김 파일을 함께 사용하려면 다음과 같은 구성이 필요합니다.

- 태그에서 요소는 `Page` 특성을 포함 해야 합니다 `x:Class` . 응용 프로그램을 빌드할 때 `x:Class` 태그 파일에가 있으면 MSBuild (Microsoft build engine)가 `partial` 에서 파생 되 <xref:System.Windows.Controls.Page> 고 특성으로 지정 된 이름을 가진 클래스를 만듭니다 `x:Class` . 이렇게 하려면 스키마에 대 한 XML 네임 스페이스 선언을 추가 해야 합니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] ( `xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"` ). 생성 된 `partial` 클래스는 `InitializeComponent` 이벤트를 등록 하 고 태그에 구현 된 속성을 설정 하기 위해 호출 되는를 구현 합니다.

- 코드를 사용할 때 클래스는 `partial` 태그의 특성으로 지정 되는 동일한 이름의 클래스 여야 `x:Class` 하며에서 파생 되어야 합니다 <xref:System.Windows.Controls.Page> . 이렇게 하면 `partial` 응용 프로그램을 빌드할 때 태그 파일에 대해 생성 되는 클래스와 코드 숨김이 연결 될 수 있습니다 ( [WPF 응용 프로그램 빌드](building-a-wpf-application-wpf.md)참조).

- 코드 숨김으로 클래스는 메서드를 <xref:System.Windows.Controls.Page> 호출 하는 생성자를 구현 해야 합니다 `InitializeComponent` . `InitializeComponent`는 태그 파일의 생성 된 클래스에 의해 구현 되어 `partial` 이벤트를 등록 하 고 태그에 정의 된 속성을 설정 합니다.

> [!NOTE]
> Visual Studio를 사용 하 여 프로젝트에 새를 추가 하는 경우 <xref:System.Windows.Controls.Page> 는 <xref:System.Windows.Controls.Page> 태그와 코드 숨김으로 모두 사용 하 여 구현 되며 여기에 설명 된 대로 태그와 코드 숨김이 연결을 만드는 데 필요한 구성이 포함 되어 있습니다.

가 있으면 <xref:System.Windows.Controls.Page> 해당 위치로 이동할 수 있습니다. 응용 프로그램이 탐색 하는 첫 번째를 지정 하려면 <xref:System.Windows.Controls.Page> 시작을 구성 해야 합니다 <xref:System.Windows.Controls.Page> .

<a name="Configuring_a_Start_Page"></a>

### <a name="configuring-a-start-page"></a>시작 페이지 구성

Xbap는 브라우저에서 호스트 되는 응용 프로그램 인프라의 특정 크기를 요구 합니다. WPF에서 클래스는 <xref:System.Windows.Application> 필요한 응용 프로그램 인프라를 설정 하는 응용 프로그램 정의의 일부입니다 ( [응용 프로그램 관리 개요](application-management-overview.md)참조).

응용 프로그램 정의는 일반적으로 태그와 코드를 모두 사용 하 여 구현 되며 마크업 파일은 MSBuild 항목으로 구성 됩니다 `ApplicationDefinition` . 다음은 XBAP에 대 한 응용 프로그램 정의입니다.

[!code-xaml[XBAPAppDefSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

[!code-csharp[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppDefSnippets/CSharp/App.xaml.cs#xbapapplicationdefinitioncodebehind)]
[!code-vb[XBAPAppDefSnippets#XBAPApplicationDefinitionCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppDefSnippets/VisualBasic/Application.xaml.vb#xbapapplicationdefinitioncodebehind)]

XBAP는 응용 프로그램 정의를 사용 하 여 시작 <xref:System.Windows.Controls.Page> ( <xref:System.Windows.Controls.Page> xbap를 시작할 때 자동으로 로드 되는)을 지정할 수 있습니다. 이렇게 하려면 <xref:System.Windows.Application.StartupUri%2A> 원하는에 대 한 URI (uniform resource identifier)를 사용 하 여 속성을 설정 <xref:System.Windows.Controls.Page> 합니다.

> [!NOTE]
> 대부분의 경우는 <xref:System.Windows.Controls.Page> 응용 프로그램으로 컴파일되거나 응용 프로그램으로 배포 됩니다. 이러한 경우를 식별 하는 URI는 pack <xref:System.Windows.Controls.Page> 체계를 준수 하는 uri 인 PACK uri입니다. *pack* Pack Uri는 [WPF의 Pack uri](pack-uris-in-wpf.md)에 자세히 설명 되어 있습니다. 아래에 설명된 http 체계를 사용하여 콘텐츠를 탐색할 수도 있습니다.

<xref:System.Windows.Application.StartupUri%2A>다음 예제와 같이 태그에서 선언적으로 설정할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#XBAPApplicationDefinitionMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/App.xaml#xbapapplicationdefinitionmarkup)]

이 예제에서 특성은 `StartupUri` 홈페이지를 식별 하는 상대 PACK URI로 설정 됩니다. XBAP를 시작 하면 .xaml이 자동으로 탐색 되 고 표시 됩니다. 이는 웹 서버에서 시작 된 XBAP를 보여 주는 다음 그림에 나와 있습니다.

![XBAP 페이지](./media/navigation-overview/xbap-launched-from-a-web-server.png "웹 서버에서 시작 된 XBAP를 표시 합니다.")

> [!NOTE]
> Xbap의 개발 및 배포에 대 한 자세한 내용은 [WPF XAML 브라우저 응용 프로그램 개요](wpf-xaml-browser-applications-overview.md) 및 [Wpf 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)를 참조 하세요.

<a name="ConfiguringAXAMLPage"></a>

### <a name="configuring-the-host-windows-title-width-and-height"></a>호스트 창 제목, 너비 및 높이 구성

위의 그림에서 알 수 있는 한 가지 사항은 브라우저와 탭 패널의 제목이 XBAP의 URI 임을 나타내는 것입니다. 이 제목은 길이가 길며 모양이나 정보 제공 측면 모두에서 그다지 유용하지 않습니다. 이러한 이유로는 <xref:System.Windows.Controls.Page> 속성을 설정 하 여 제목을 변경 하는 방법을 제공 합니다 <xref:System.Windows.Controls.Page.WindowTitle%2A> . 또한 <xref:System.Windows.Controls.Page.WindowWidth%2A> 각각 및를 설정 하 여 브라우저 창의 너비와 높이를 구성할 수 있습니다 <xref:System.Windows.Controls.Page.WindowHeight%2A> .

<xref:System.Windows.Controls.Page.WindowTitle%2A>, <xref:System.Windows.Controls.Page.WindowWidth%2A> 및 <xref:System.Windows.Controls.Page.WindowHeight%2A> 은 다음 예제와 같이 태그에서 선언적으로 설정할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#HomePageMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/HomePage.xaml#homepagemarkup)]

결과는 다음 그림에 나와 있습니다.

![창 제목, 높이, 너비](./media/navigation-overview/window-title-width-height.png "그러면 구성할 수 있는 창 제목, 높이 및 너비가 표시 됩니다.")

<a name="NavigatingBetweenXAMLPages"></a>

### <a name="hyperlink-navigation"></a>하이퍼링크 탐색

일반적인 XBAP는 여러 페이지로 구성 됩니다. 한 페이지에서 다른 페이지로 이동 하는 가장 간단한 방법은를 사용 하는 것입니다 <xref:System.Windows.Documents.Hyperlink> . <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Controls.Page> `Hyperlink` 다음 태그에 표시 된 요소를 사용 하 여를에 선언적으로 추가할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml1)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml2)]
[!code-xaml[NavigationOverviewSnippets#HyperlinkXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithHyperlink.xaml#hyperlinkxaml3)]

`Hyperlink`요소에는 다음이 필요 합니다.

- <xref:System.Windows.Controls.Page>특성에 지정 된 대로 탐색할의 PACK URI입니다 `NavigateUri` .

- 텍스트 및 이미지와 같이 사용자가 탐색을 시작 하기 위해 클릭할 수 있는 콘텐츠 (요소에 포함 될 수 있는 내용에 대 한 `Hyperlink` 참조 <xref:System.Windows.Documents.Hyperlink> )입니다.

다음 그림에서는이 있는의 XBAP를 보여 줍니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Documents.Hyperlink> .

![하이퍼링크가 있는 페이지](./media/navigation-overview/xbap-with-a-page-with-a-hyperlink.png "그러면 하이퍼링크가 있는 페이지가 포함 된 XBAP가 표시 됩니다.")

짐작할 수 있듯이을 클릭 하면 <xref:System.Windows.Documents.Hyperlink> XBAP가 <xref:System.Windows.Controls.Page> 특성으로 식별 된로 이동 합니다 `NavigateUri` . 또한 XBAP는 <xref:System.Windows.Controls.Page> Internet Explorer의 최근 페이지 목록에 이전에 대 한 항목을 추가 합니다. 다음 그림에서 이를 확인할 수 있습니다.

![뒤로 및 앞으로 단추](./media/navigation-overview/back-and-forward-navigation.png "뒤로 및 앞으로 단추를 사용 하 여 탐색 합니다.")

또한에서 다른 항목으로의 탐색 <xref:System.Windows.Controls.Page> 을 지원할 뿐만 아니라 <xref:System.Windows.Documents.Hyperlink> 조각 탐색도 지원 합니다.

<a name="FragmentNavigation"></a>

### <a name="fragment-navigation"></a>조각 탐색

*조각 탐색* 은 현재 또는 다른의 콘텐츠 조각 탐색입니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> . WPF에서 콘텐츠 조각은 명명 된 요소에 포함 된 콘텐츠입니다. 명명 된 요소는 해당 특성 집합이 있는 요소입니다 `Name` . 다음 태그는 `TextBlock` 콘텐츠 조각이 포함 된 명명 된 요소를 보여 줍니다.

[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup2)]
[!code-xaml[NavigationOverviewSnippets#PageWithContentFragmentsMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithFragments.xaml#pagewithcontentfragmentsmarkup3)]

에서 <xref:System.Windows.Documents.Hyperlink> 콘텐츠 조각으로 이동 하려면 특성에 다음이 `NavigateUri` 포함 되어야 합니다.

- 콘텐츠 조각이 탐색 될의 URI입니다 <xref:System.Windows.Controls.Page> .

- “#” 문자입니다.

- <xref:System.Windows.Controls.Page>콘텐츠 조각이 포함 된의 요소 이름입니다.

조각 URI는 다음과 같은 형식입니다.

*PageURI* `#` *ElementName*

다음은 `Hyperlink` 콘텐츠 조각으로 이동 하도록 구성 된의 예제를 보여 줍니다.

[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml1)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml2)]
[!code-xaml[NavigationOverviewSnippets#PageThatNavigatesXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageThatNavigatesToFragment.xaml#pagethatnavigatesxaml3)]

> [!NOTE]
> 이 단원에서는 WPF의 기본 조각 탐색 구현에 대해 설명 합니다. WPF를 사용 하면 이벤트를 처리 해야 하는 사용자 고유의 조각 탐색 구성표를 구현할 수도 있습니다 <xref:System.Windows.Navigation.NavigationService.FragmentNavigation?displayProperty=nameWithType> .

> [!IMPORTANT]
> [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] `Page` HTTP를 통해 페이지를 검색할 수 있는 경우에만 느슨한 페이지 (루트 요소로 된 태그 전용 파일)의 조각으로 이동할 수 있습니다.
>
> 그러나 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지에서 자체 조각을 탐색할 수 있습니다.

<a name="NavigationService"></a>

### <a name="navigation-service"></a>탐색 서비스

<xref:System.Windows.Documents.Hyperlink>사용자는 특정에 대 한 탐색을 시작할 수 있지만 <xref:System.Windows.Controls.Page> , 페이지를 찾고 다운로드 하는 작업은 클래스를 통해 수행 됩니다 <xref:System.Windows.Navigation.NavigationService> . 기본적으로 <xref:System.Windows.Navigation.NavigationService> 는와 같은 클라이언트 코드를 대신 하 여 탐색 요청을 처리 하는 기능을 제공 합니다 <xref:System.Windows.Documents.Hyperlink> . 또한에서는 <xref:System.Windows.Navigation.NavigationService> 탐색 요청을 추적 하 고 영향을 주는 높은 수준의 지원을 구현 합니다.

을 클릭 하면 WPF가를 <xref:System.Windows.Documents.Hyperlink> 호출 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> 하 여 <xref:System.Windows.Controls.Page> 지정 된 pack URI에서을 찾아서 다운로드 합니다. 다운로드 된는 <xref:System.Windows.Controls.Page> 루트 개체가 다운로드 된 인스턴스인 개체 트리로 변환 됩니다 <xref:System.Windows.Controls.Page> . 루트 개체에 대 한 참조는 <xref:System.Windows.Controls.Page> 속성에 저장 됩니다 <xref:System.Windows.Navigation.NavigationService.Content%2A?displayProperty=nameWithType> . 탐색 한 콘텐츠에 대 한 pack URI는 속성에 저장 되는 <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> 반면는 <xref:System.Windows.Navigation.NavigationService.CurrentSource%2A?displayProperty=nameWithType> 탐색 된 마지막 페이지의 pack uri를 저장 합니다.

> [!NOTE]
> WPF 응용 프로그램에는 현재 활성 상태가 둘 이상 있을 수 있습니다 <xref:System.Windows.Navigation.NavigationService> . 자세한 내용은이 항목의 뒷부분에 나오는 [탐색 호스트](#Navigation_Hosts) 를 참조 하십시오.

<a name="Programmatic_Navigation_with_the_Navigation_Service"></a>

### <a name="programmatic-navigation-with-the-navigation-service"></a>탐색 서비스를 사용하여 프로그래밍 방식으로 탐색

사용자를 대신 하 여 <xref:System.Windows.Navigation.NavigationService> 탐색이 태그에서 선언적으로 구현 되는지 여부를 알 필요가 없습니다 <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Documents.Hyperlink> <xref:System.Windows.Navigation.NavigationService> . 즉,의 직접 또는 간접 부모가 탐색 <xref:System.Windows.Documents.Hyperlink> 호스트 ( [탐색](#Navigation_Hosts)호스트 참조) 이면 탐색 <xref:System.Windows.Documents.Hyperlink> 호스트의 탐색 서비스를 찾아서 사용 하 여 탐색 요청을 처리할 수 있습니다.

그러나 다음을 포함 하 여를 직접 사용 해야 하는 경우도 있습니다 <xref:System.Windows.Navigation.NavigationService> .

- <xref:System.Windows.Controls.Page>매개 변수가 없는 생성자를 사용 하 여를 인스턴스화해야 하는 경우

- 로 이동 하기 전에에서 속성을 설정 해야 하는 경우 <xref:System.Windows.Controls.Page>

- 탐색 해야 하 <xref:System.Windows.Controls.Page> 는를 런타임에만 확인할 수 있는 경우

이러한 경우 개체의 메서드를 호출 하 여 프로그래밍 방식으로 탐색을 시작 하는 코드를 작성 해야 <xref:System.Windows.Navigation.NavigationService.Navigate%2A> <xref:System.Windows.Navigation.NavigationService> 합니다. 이는에 대 한 참조를 가져오는 데 필요 <xref:System.Windows.Navigation.NavigationService> 합니다.

#### <a name="getting-a-reference-to-the-navigationservice"></a>NavigationService에 대한 참조 가져오기

[탐색 호스트](#Navigation_Hosts) 섹션에서 설명 하는 이유로 WPF 응용 프로그램에는 둘 이상의를 사용할 수 있습니다 <xref:System.Windows.Navigation.NavigationService> . 즉, 코드에서를 찾는 방법이 필요 <xref:System.Windows.Navigation.NavigationService> 합니다 .이는 일반적으로 현재를 <xref:System.Windows.Navigation.NavigationService> 탐색 하는입니다 <xref:System.Windows.Controls.Page> . <xref:System.Windows.Navigation.NavigationService>메서드를 호출 하 여에 대 한 참조를 가져올 수 있습니다 `static` <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A?displayProperty=nameWithType> . 특정를 탐색 하는를 가져오려면에 <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page> 대 한 참조를 <xref:System.Windows.Controls.Page> 메서드의 인수로 전달 합니다 <xref:System.Windows.Navigation.NavigationService.GetNavigationService%2A> . 다음 코드에서는 현재에 대 한를 가져오는 방법을 보여 줍니다 <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page> .

[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPage.xaml.cs#getnscodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPage.xaml.vb#getnscodebehind2)]

에 대 한를 찾기 위한 바로 가기로는 <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page> 속성을 구현 합니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page.NavigationService%2A> . 다음 예제에서 이를 확인할 수 있습니다.

[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind1)]
[!code-csharp[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/GetNSPageShortCut.xaml.cs#getnsshortcutcodebehind2)]
[!code-vb[NavigationOverviewSnippets#GetNSShortcutCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/GetNSPageShortCut.xaml.vb#getnsshortcutcodebehind2)]

> [!NOTE]
> 는가 <xref:System.Windows.Controls.Page> 이벤트를 발생 시킬 때만에 대 한 참조를 가져올 수 있습니다 <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page> <xref:System.Windows.FrameworkElement.Loaded> .

#### <a name="programmatic-navigation-to-a-page-object"></a>프로그래밍 방식으로 Page 개체 탐색

다음 예제에서는를 사용 하 여 프로그래밍 방식으로로 이동 하는 방법을 보여 줍니다 <xref:System.Windows.Navigation.NavigationService> <xref:System.Windows.Controls.Page> . 로 탐색 되는를 <xref:System.Windows.Controls.Page> 매개 변수가 없는 단일 생성자를 사용 하 여 인스턴스화할 수 있으므로 프로그래밍 방식이 필요 합니다. <xref:System.Windows.Controls.Page>매개 변수가 없는 생성자가 있는는 다음 태그와 코드에 표시 됩니다.

[!code-xaml[NavigationOverviewSnippets#PageWithNonDefaultConstructorXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml#pagewithnondefaultconstructorxaml)]

[!code-csharp[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithNonDefaultConstructor.xaml.cs#pagewithnondefaultconstructorcodebehind)]
[!code-vb[NavigationOverviewSnippets#PageWithNonDefaultConstructorCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithNonDefaultConstructor.xaml.vb#pagewithnondefaultconstructorcodebehind)]

<xref:System.Windows.Controls.Page>매개 변수가 없는 생성자를 사용 하 여를 탐색 하는는 <xref:System.Windows.Controls.Page> 다음 태그와 코드에 표시 됩니다.

[!code-xaml[NavigationOverviewSnippets#NSNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml#nsnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSNavigationPage.xaml.cs#nsnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSNavigationPage.xaml.vb#nsnavigationpagecodebehind)]

이를 <xref:System.Windows.Documents.Hyperlink> 클릭 하면를 <xref:System.Windows.Controls.Page> 인스턴스화하여에서 <xref:System.Windows.Controls.Page> 매개 변수가 없는 생성자를 사용 하 고 메서드를 호출 하 여 탐색을 시작 합니다 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> . <xref:System.Windows.Navigation.NavigationService.Navigate%2A>가 pack URI가 아닌에서 탐색 하는 개체에 대 한 참조를 허용 합니다 <xref:System.Windows.Navigation.NavigationService> .

#### <a name="programmatic-navigation-with-a-pack-uri"></a>Pack URI를 사용하여 프로그래밍 방식으로 탐색

Pack uri를 프로그래밍 방식으로 생성 해야 하는 경우 (예: 런타임에 pack URI를 결정할 수 있는 경우) 메서드를 사용할 수 있습니다 <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> . 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#NSUriNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml#nsurinavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSUriNavigationPage.xaml.cs#nsurinavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#NSUriNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSUriNavigationPage.xaml.vb#nsurinavigationpagecodebehind)]

#### <a name="refreshing-the-current-page"></a>현재 페이지 새로 고침

<xref:System.Windows.Controls.Page>속성에 저장 된 PACK uri와 동일한 PACK uri가 있는 경우이 다운로드 되지 않습니다 <xref:System.Windows.Navigation.NavigationService.Source%2A?displayProperty=nameWithType> . WPF가 현재 페이지를 다시 다운로드 하도록 하려면 <xref:System.Windows.Navigation.NavigationService.Refresh%2A?displayProperty=nameWithType> 다음 예제와 같이 메서드를 호출 하면 됩니다.

[!code-xaml[NavigationOverviewSnippets#NSRefreshNavigationPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml#nsrefreshnavigationpagexaml1)]

[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind1)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NSRefreshNavigationPage.xaml.cs#nsrefreshnavigationpagecodebehind2)]
[!code-vb[NavigationOverviewSnippets#NSRefreshNavigationPageCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/NSRefreshNavigationPage.xaml.vb#nsrefreshnavigationpagecodebehind2)]

<a name="Navigation_Lifetime"></a>

### <a name="navigation-lifetime"></a>탐색 수명

지금까지 본 것처럼 탐색을 시작하는 방법은 여러 가지가 있습니다. 탐색을 시작 하 고 탐색을 진행 하는 동안에서 구현 하는 다음 이벤트를 사용 하 여 탐색을 추적 하 고 영향을 줄 수 있습니다 <xref:System.Windows.Navigation.NavigationService> .

- <xref:System.Windows.Navigation.NavigationService.Navigating>. 새 탐색이 요청되면 발생합니다. 탐색을 취소하는 데 사용될 수 있습니다.

- <xref:System.Windows.Navigation.NavigationService.NavigationProgress>. 탐색 진행 정보를 제공하기 위해 다운로드하는 동안 정기적으로 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.Navigated>. 페이지를 찾아서 다운로드할 때 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.NavigationStopped>. 을 호출 하 여 탐색이 중지 <xref:System.Windows.Navigation.NavigationService.StopLoading%2A> 되거나 현재 탐색이 진행 되는 동안 새 탐색이 요청 될 때 발생 합니다.

- <xref:System.Windows.Navigation.NavigationService.NavigationFailed>. 요청된 콘텐츠를 탐색하는 동안 오류가 있으면 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.LoadCompleted>. 탐색된 콘텐츠가 로드 및 구문 분석되고 렌더링을 시작할 때 발생합니다.

- <xref:System.Windows.Navigation.NavigationService.FragmentNavigation>. 다음과 같이 콘텐츠 조각에 대한 탐색이 시작될 때 발생합니다.

  - 원하는 조각이 현재 콘텐츠에 있는 경우 즉시

  - 소스 콘텐츠를 로드한 후 다른 콘텐츠에 원하는 조각이 있는 경우

탐색 이벤트는 다음 그림과 같이 순서대로 발생합니다.

![페이지 탐색 흐름 차트](./media/navigation-overview/order-of-navigation-events.png "페이지 탐색 이벤트 흐름 차트")

일반적으로는 <xref:System.Windows.Controls.Page> 이러한 이벤트에 대해 염려 하지 않습니다. 응용 프로그램에 관심이 있을 가능성이 더 높습니다. 이러한 이벤트는 클래스에 의해 발생 하기도 합니다 <xref:System.Windows.Application> .

- <xref:System.Windows.Application.Navigating?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationProgress?displayProperty=nameWithType>

- <xref:System.Windows.Application.Navigated?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationFailed?displayProperty=nameWithType>

- <xref:System.Windows.Application.NavigationStopped?displayProperty=nameWithType>

- <xref:System.Windows.Application.LoadCompleted?displayProperty=nameWithType>

- <xref:System.Windows.Application.FragmentNavigation?displayProperty=nameWithType>

<xref:System.Windows.Navigation.NavigationService>이벤트가 발생할 때마다 <xref:System.Windows.Application> 클래스는 해당 이벤트를 발생 시킵니다. <xref:System.Windows.Controls.Frame>및 <xref:System.Windows.Navigation.NavigationWindow> 는 각각의 범위 내에서 탐색을 검색 하는 동일한 이벤트를 제공 합니다.

경우에 따라 <xref:System.Windows.Controls.Page> 이 이벤트에 관심이 있을 수 있습니다. 예를 들어는 <xref:System.Windows.Controls.Page> 이벤트를 처리 <xref:System.Windows.Navigation.NavigationService.Navigating?displayProperty=nameWithType> 하 여 자체 탐색을 취소할지 여부를 결정할 수 있습니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#CancelNavigationPageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml#cancelnavigationpagexaml)]

[!code-csharp[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/CancelNavigationPage.xaml.cs#cancelnavigationpagecodebehind)]
[!code-vb[NavigationOverviewSnippets#CancelNavigationPageCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/CancelNavigationPage.xaml.vb#cancelnavigationpagecodebehind)]

앞의 예제와 같이의 탐색 이벤트를 사용 하 여 처리기를 등록 하는 경우에는 <xref:System.Windows.Controls.Page> 이벤트 처리기의 등록도 취소 해야 합니다. 그렇지 않으면 WPF 탐색에서 <xref:System.Windows.Controls.Page> 저널을 사용 하 여 탐색을 기억 하는 방법과 관련 하 여 부작용이 발생할 수 있습니다.

<a name="NavigationHistory"></a>

### <a name="remembering-navigation-with-the-journal"></a>저널을 사용하여 탐색 기억

WPF에서는 두 개의 스택을 사용 하 여 탐색 한 페이지 (뒤로 스택 및 앞으로 스택)를 기억할 수 있습니다. 현재에서 <xref:System.Windows.Controls.Page> 새 또는 기존로 이동 하는 경우 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> 현재 <xref:System.Windows.Controls.Page> 가 *뒤로 스택에*추가 됩니다. 현재에서 <xref:System.Windows.Controls.Page> 이전으로 다시 이동 하면 <xref:System.Windows.Controls.Page> 현재 <xref:System.Windows.Controls.Page> 가 *전방 스택에*추가 됩니다. 뒤로 스택, 앞으로 스택 및 이들을 관리하는 기능을 총칭하여 저널이라고 합니다. 뒤로 스택 및 전달 스택의 각 항목은 클래스의 인스턴스이고 <xref:System.Windows.Navigation.JournalEntry> , *저널 항목*이라고 합니다.

#### <a name="navigating-the-journal-from-internet-explorer"></a>Internet Explorer에서 저널 탐색

개념적으로 저널은 Internet Explorer의 **뒤로** 및 **앞으로** 단추와 동일한 방식으로 작동 합니다. 다음 그림을 참조하세요.

![뒤로 및 앞으로 단추](./media/navigation-overview/back-and-forward-navigation.png "뒤로 및 앞으로 단추를 사용 하 여 탐색 합니다.")

Internet Explorer에서 호스팅되는 Xbap의 경우 WPF는 저널을 Internet Explorer 탐색에 통합 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] . 이를 통해 사용자는 Internet Explorer의 **뒤로**, **앞**으로 및 **최근 페이지** 단추를 사용 하 여 XBAP의 페이지를 탐색할 수 있습니다.

> [!IMPORTANT]
> Internet Explorer에서 사용자가 XBAP로 이동 하 여 다시 XBAP로 이동 하면 활성 상태로 유지 되지 않은 페이지의 저널 항목만 저널에 유지 됩니다. 페이지를 활성 상태로 유지 하는 방법에 대 한 설명은이 항목의 뒷부분에 나오는 [페이지 수명 및 저널](#PageLifetime) 을 참조 하세요.

기본적으로 <xref:System.Windows.Controls.Page> Internet Explorer의 **최근 페이지** 목록에 표시 되는 각에 대 한 텍스트는에 대 한 URI입니다 <xref:System.Windows.Controls.Page> . 대부분의 경우 이는 사용자에게 특히 의미가 없습니다. 다행히도 다음 옵션 중 하나를 사용하여 텍스트를 변경할 수 있습니다.

1. 연결 된 `JournalEntry.Name` 특성 값입니다.

2. `Page.Title`특성 값입니다.

3. `Page.WindowTitle`특성 값 및 현재에 대 한 URI <xref:System.Windows.Controls.Page> 입니다.

4. 현재에 대 한 URI <xref:System.Windows.Controls.Page> 입니다. (기본값)

옵션이 나열되는 순서는 텍스트를 찾는 우선 순위와 일치합니다. 예를 들어 `JournalEntry.Name` 가 설정 된 경우 다른 값은 무시 됩니다.

다음 예제에서는 특성을 사용 하 여 `Page.Title` 저널 항목에 대해 표시 되는 텍스트를 변경 합니다.

[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup1)]
[!code-xaml[NavigationOverviewSnippets#PageTitleMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml#pagetitlemarkup2)]

[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind1)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind1)]
[!code-csharp[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/PageWithTitle.xaml.cs#pagetitlecodebehind2)]
[!code-vb[NavigationOverviewSnippets#PageTitleCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigationOverviewSnippets/VisualBasic/PageWithTitle.xaml.vb#pagetitlecodebehind2)]

#### <a name="navigating-the-journal-using-wpf"></a>WPF를 사용하여 저널 탐색

사용자는 Internet Explorer에서 **뒤로**, **앞**으로 및 **최근 페이지** 를 사용 하 여 저널을 탐색할 수 있지만 WPF에서 제공 하는 선언적 및 프로그래밍 방식 메커니즘을 사용 하 여 저널을 탐색할 수도 있습니다. 이 작업을 수행 하는 한 가지 이유는 페이지에서 사용자 지정 탐색 Ui를 제공 하는 것입니다.

에 의해 노출 된 탐색 명령을 사용 하 여 선언적으로 저널 탐색 지원을 추가할 수 있습니다 <xref:System.Windows.Input.NavigationCommands> . 다음 예제에서는 탐색 명령을 사용 하는 방법을 보여 줍니다 `BrowseBack` .

[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml1)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml2)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml3)]
[!code-xaml[NavigationOverviewSnippets#NavigationCommandsPageXAML4](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/NavigationCommandsPage.xaml#navigationcommandspagexaml4)]

클래스의 다음 멤버 중 하나를 사용 하 여 프로그래밍 방식으로 저널을 탐색할 수 있습니다 <xref:System.Windows.Navigation.NavigationService> .

- <xref:System.Windows.Navigation.NavigationService.GoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.GoForward%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoBack%2A>

- <xref:System.Windows.Navigation.NavigationService.CanGoForward%2A>

이 항목의 뒷부분에 나오는 [탐색 기록을 사용 하 여 콘텐츠 상태 유지](#RetainingContentStateWithNavigationHistory) 에 설명 된 대로 저널을 프로그래밍 방식으로 조작할 수도 있습니다.

<a name="PageLifetime"></a>

### <a name="page-lifetime-and-the-journal"></a>페이지 수명 및 저널

그래픽, 애니메이션 및 미디어를 포함 하 여 풍부한 콘텐츠가 포함 된 여러 페이지가 포함 된 XBAP를 생각해 보세요. 이와 같은 페이지의 메모리 사용량은 특히 비디오 및 오디오 미디어가 사용될 경우 매우 클 수 있습니다. 저널에서 탐색 된 페이지를 "기억" 하는 경우 이러한 XBAP는 크고 많은 양의 메모리를 빠르게 소비할 수 있습니다.

이러한 이유로 저널의 기본 동작은 <xref:System.Windows.Controls.Page> 개체에 대 한 참조가 아니라 각 업무 일지 항목에 메타 데이터를 저장 하는 것입니다 <xref:System.Windows.Controls.Page> . 저널 항목을 탐색 하는 경우 해당 <xref:System.Windows.Controls.Page> 메타 데이터는 지정 된의 새 인스턴스를 만드는 데 사용 됩니다 <xref:System.Windows.Controls.Page> . 결과적으로 탐색 되는 각에는 <xref:System.Windows.Controls.Page> 다음 그림에 나와 있는 수명이 있습니다.

![페이지 수명](./media/navigation-overview/navigated-page-lifetime.png "그러면 페이지를 탐색할 때 수명이 표시 됩니다.")

기본 업무 일지 동작을 사용 하면 메모리 사용을 줄일 수 있지만 페이지당 렌더링 성능이 저하 될 수 있습니다. <xref:System.Windows.Controls.Page>특히 많은 콘텐츠가 있는 경우를 다시 인스턴스화하면 시간이 많이 걸릴 수 있습니다. 저널에서 인스턴스를 유지 해야 하는 경우에는 <xref:System.Windows.Controls.Page> 두 가지 방법으로 그릴 수 있습니다. 먼저 메서드를 호출 하 여 프로그래밍 방식으로 개체를 탐색할 수 있습니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Navigation.NavigationService.Navigate%2A?displayProperty=nameWithType> .

둘째, 속성을로 설정 하 여 WPF가 저널에서의 인스턴스를 유지 하도록 지정할 수 있습니다 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page.KeepAlive%2A> `true` (기본값은 `false` ). 다음 예제와 같이 태그에서 선언적으로 설정할 수 있습니다 <xref:System.Windows.Controls.Page.KeepAlive%2A> .

[!code-xaml[NavigationOverviewSnippets#KeepAlivePageXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/KeepAlivePage.xaml#keepalivepagexaml)]

활성 상태를 유지 하는의 수명은 <xref:System.Windows.Controls.Page> 이 아닌 것과 약간 다릅니다. 활성 상태로 유지 되는를 처음으로 탐색 하는 경우에는 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> 활성 상태로 유지 되지 않는와 마찬가지로 인스턴스화됩니다. 그러나의 인스턴스가 <xref:System.Windows.Controls.Page> 저널에 유지 되므로 저널에 유지 되는 동안에는 다시 인스턴스화되지 않습니다. 따라서가 탐색 될 <xref:System.Windows.Controls.Page> 때마다를 호출 해야 하는 초기화 논리가 있는 경우 <xref:System.Windows.Controls.Page> 이를 생성자에서 이벤트 처리기로 이동 해야 합니다 <xref:System.Windows.FrameworkElement.Loaded> . 다음 그림에 표시 된 것 처럼 <xref:System.Windows.FrameworkElement.Loaded> 및 <xref:System.Windows.FrameworkElement.Unloaded> 이벤트는 <xref:System.Windows.Controls.Page> 각각이 및에서 탐색 될 때마다 발생 합니다.

![Loaded 및 Unloaded 이벤트 발생 시](./media/navigation-overview/loaded-and-unloaded-events.png "로드 및 언로드된 이벤트는 페이지를 탐색할 때 발생 합니다.")

<xref:System.Windows.Controls.Page>가 활성 상태로 유지 되지 않으면 다음 중 하나를 수행 하면 안 됩니다.

- 이 페이지 또는 이 페이지의 일부에 대한 참조 저장

- 이벤트 처리기를 이 페이지에서 구현되지 않는 이벤트에 등록

이러한 작업 중 하나를 수행 하면가 <xref:System.Windows.Controls.Page> 저널에서 제거 된 후에도 메모리에 유지 되도록 하는 참조가 생성 됩니다.

일반적으로 <xref:System.Windows.Controls.Page> 활성 상태를 유지 하지 않는 기본 동작을 사용 하는 것이 좋습니다 <xref:System.Windows.Controls.Page> . 그러나 이는 다음 절에서 설명하는 상태 의미와 관련이 있습니다.

<a name="RetainingContentStateWithNavigationHistory"></a>

### <a name="retaining-content-state-with-navigation-history"></a>탐색 기록을 사용하여 콘텐츠 상태 유지

<xref:System.Windows.Controls.Page>이 활성 상태로 유지 되지 않고 사용자 로부터 데이터를 수집 하는 컨트롤이 있는 경우 사용자가로 이동 하 여 다시 이동 하는 경우 데이터는 어떻게 되나요 <xref:System.Windows.Controls.Page> ? 경험을 바탕으로 사용자는 이전에 입력한 데이터가 표시될 것이라고 예상합니다. 불행 하 게도 각 탐색을 사용 하 여의 새 인스턴스가 <xref:System.Windows.Controls.Page> 만들어지므로 데이터를 수집 하는 컨트롤이 다시 인스턴스화되고 데이터가 손실 됩니다.

다행히 저널은 컨트롤 데이터를 포함 하 여 탐색 간에 데이터를 기억할 수 있도록 지원 합니다 <xref:System.Windows.Controls.Page> . 특히 각의 저널 항목은 <xref:System.Windows.Controls.Page> 연결 된 상태에 대 한 임시 컨테이너 역할을 <xref:System.Windows.Controls.Page> 합니다. 다음 단계에서는을 탐색할 때이 지원이 사용 되는 방법을 간략하게 설명 합니다 <xref:System.Windows.Controls.Page> .

1. 현재에 대 한 항목이 <xref:System.Windows.Controls.Page> 저널에 추가 됩니다.

2. 의 상태는 <xref:System.Windows.Controls.Page> 해당 페이지에 대 한 업무 일지 항목과 함께 저장 되며,이 항목은 백 스택에 추가 됩니다.

3. 새를 <xref:System.Windows.Controls.Page> 탐색 합니다.

저널을 사용 하 여 페이지를 <xref:System.Windows.Controls.Page> 다시 탐색 하면 다음 단계가 수행 됩니다.

1. <xref:System.Windows.Controls.Page>(뒤로 스택의 맨 위 저널 항목)가 인스턴스화됩니다.

2. 는에 <xref:System.Windows.Controls.Page> 대 한 저널 항목과 함께 저장 된 상태로 새로 고쳐집니다 <xref:System.Windows.Controls.Page> .

3. 를 <xref:System.Windows.Controls.Page> 다시 탐색 합니다.

WPF는에서 다음 컨트롤이 사용 되는 경우이 지원을 자동으로 사용 합니다 <xref:System.Windows.Controls.Page> .

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

에서 <xref:System.Windows.Controls.Page> 이러한 컨트롤을 사용 하는 경우에는 <xref:System.Windows.Controls.Page> 다음 그림에 **표시 된** 것 처럼 탐색 전체에 데이터를 입력 합니다 <xref:System.Windows.Controls.ListBox> .

![상태를 기억하는 컨트롤이 있는 페이지](./media/navigation-overview/data-remembered-across-page-navigations.png "입력 한 데이터는 페이지 탐색 사이에 저장 됩니다.")

에 <xref:System.Windows.Controls.Page> 앞의 목록에 있는 컨트롤이 아닌 다른 컨트롤이 있거나 상태가 사용자 지정 개체에 저장 된 경우에는 탐색 사이에서 저널의 상태가 기억나지 않게 코드를 작성 해야 합니다 <xref:System.Windows.Controls.Page> .

여러 탐색에서 작은 상태를 기억할 필요가 있는 경우 <xref:System.Windows.Controls.Page> <xref:System.Windows.DependencyProperty> 메타 데이터 플래그로 구성 된 종속성 속성 (참조)을 사용할 수 있습니다 <xref:System.Windows.FrameworkPropertyMetadata.Journal%2A?displayProperty=nameWithType> .

여러 탐색에서 기억할 필요가 있는 상태가 여러 데이터를 구성 하는 경우에는 <xref:System.Windows.Controls.Page> 단일 클래스에서 상태를 캡슐화 하 고 인터페이스를 구현 하는 코드를 적게 사용 하는 것을 알 수 있습니다 <xref:System.Windows.Navigation.IProvideCustomContentState> .

자체에서 이동 하지 않고 단일의 다양 한 상태를 탐색 해야 하는 경우 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Page> 및를 사용할 수 있습니다 <xref:System.Windows.Navigation.IProvideCustomContentState> <xref:System.Windows.Navigation.NavigationService.AddBackEntry%2A?displayProperty=nameWithType> .

<a name="Cookies"></a>

### <a name="cookies"></a>쿠키

WPF 응용 프로그램에서 데이터를 저장할 수 있는 또 다른 방법은 및 메서드를 사용 하 여 생성, 업데이트 및 삭제 되는 쿠키를 사용 하는 것입니다 <xref:System.Windows.Application.SetCookie%2A> <xref:System.Windows.Application.GetCookie%2A> . WPF에서 만들 수 있는 쿠키는 다른 유형의 웹 응용 프로그램에서 사용 하는 쿠키와 동일 합니다. 쿠키는 응용 프로그램이 나 응용 프로그램 세션 중에 클라이언트 컴퓨터의 응용 프로그램에 의해 저장 되는 임의의 데이터 부분입니다. 쿠키 데이터는 일반적으로 다음과 같은 이름/값 쌍 형식을 사용합니다.

*이름* `=` *값*

데이터가에 전달 될 때 쿠키가 설정 되어야 하는 <xref:System.Windows.Application.SetCookie%2A> 위치의와 함께 <xref:System.Uri> 쿠키는 메모리 내에서 만들어지며 현재 응용 프로그램 세션 기간 동안만 사용할 수 있습니다. 이 유형의 쿠키를 *세션 쿠키*라고 합니다.

애플리케이션 세션 간에 쿠키를 저장하려면 다음 형식을 사용하여 쿠키에 만료 날짜를 추가해야 합니다.

*이름* `=` *값*`; expires=DAY, DD-MMM-YYYY HH:MM:SS GMT`

만료 날짜가 있는 쿠키는 쿠키가 만료 될 때까지 현재 Windows 설치의 임시 인터넷 파일 폴더에 저장 됩니다. 이러한 쿠키는 응용 프로그램 세션 간에 지속 되므로 *영구 쿠키* 라고 합니다.

메서드를 호출 하 여 <xref:System.Windows.Application.GetCookie%2A> <xref:System.Uri> 쿠키를 메서드로 설정한 위치의를 전달 하 여 세션과 영구 쿠키를 모두 검색할 수 있습니다 <xref:System.Windows.Application.SetCookie%2A> .

다음은 WPF에서 쿠키를 지 원하는 몇 가지 방법입니다.

- WPF 독립 실행형 응용 프로그램 및 Xbap는 모두 쿠키를 만들고 관리할 수 있습니다.

- XBAP에서 만든 쿠키는 브라우저에서 액세스할 수 있습니다.

- 동일한 도메인의 Xbap에서 쿠키를 만들고 공유할 수 있습니다.

- 동일한 도메인의 Xbap 및 HTML 페이지에서 쿠키를 만들고 공유할 수 있습니다.

- Xbap 및 느슨한 페이지에서 웹 요청을 만들 때 쿠키가 디스패치 됩니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

- IFRAME에서 호스트 되는 최상위 Xbap와 Xbap는 모두 쿠키에 액세스할 수 있습니다.

- WPF의 쿠키 지원은 지원 되는 모든 브라우저에 대해 동일 합니다.

- Internet Explorer에서 쿠키와 관련 된 P3P 정책은 특히 자사 및 타사 Xbap와 관련 하 여 WPF에서 적용 됩니다.

<a name="Structured_Navigation"></a>

### <a name="structured-navigation"></a>구조적 탐색

간에 데이터를 전달 해야 하는 경우 <xref:System.Windows.Controls.Page> 데이터를의 매개 변수가 없는 생성자에 인수로 전달할 수 있습니다 <xref:System.Windows.Controls.Page> . 이 방법을 사용 하는 경우 활성 상태를 유지 해야 합니다 <xref:System.Windows.Controls.Page> . 그렇지 않은 경우 다음에로 이동할 때 <xref:System.Windows.Controls.Page> WPF는 <xref:System.Windows.Controls.Page> 매개 변수가 없는 생성자를 사용 하 여를 다시 인스턴스화합니다.

또는에서 <xref:System.Windows.Controls.Page> 전달 해야 하는 데이터로 설정 된 속성을 구현할 수 있습니다. 그러나 <xref:System.Windows.Controls.Page> 이 데이터를 탐색 하는에 데이터를 다시 전달 해야 하는 경우에는 복잡 해질 수 <xref:System.Windows.Controls.Page> 있습니다. 문제는 탐색이 탐색 된 후에이 반환 되도록 하는 메커니즘이 기본적으로 지원 되지 않는다는 것입니다 <xref:System.Windows.Controls.Page> . 기본적으로 탐색은 호출/반환 의미 체계를 지원하지 않습니다. 이 문제를 해결 하기 위해 WPF는이 <xref:System.Windows.Navigation.PageFunction%601> 예측 가능 하 고 구조화 된 방식으로로 반환 되도록 하는 데 사용할 수 있는 클래스를 제공 합니다 <xref:System.Windows.Controls.Page> . 자세한 내용은 [구조적 탐색 개요](structured-navigation-overview.md)를 참조 하세요.

<a name="The_NavigationWindow_Class"></a>

## <a name="the-navigationwindow-class"></a>NavigationWindow 클래스

지금까지 탐색 가능한 콘텐츠로 애플리케이션을 빌드하는 데 가장 많이 사용되는 탐색 서비스 영역을 살펴보았습니다. 이러한 서비스는 xbap로 국한 되지 않지만 Xbap의 컨텍스트에서 설명 했습니다. 최신 운영 체제 및 Windows 응용 프로그램은 최신 사용자의 브라우저 환경을 활용 하 여 브라우저 스타일 탐색을 독립 실행형 응용 프로그램에 통합 합니다. 일반적인 예제는 다음을 포함합니다.

- **단어 동의어 사전**: 선택한 단어를 탐색합니다.

- **파일 탐색기**: 파일 및 폴더를 탐색합니다.

- **마법사**: 복잡한 작업을 여러 페이지로 나누어 탐색할 수 있습니다. Windows 기능 추가 및 제거를 처리 하는 Windows 구성 요소 마법사를 예로 들 수 있습니다.

브라우저 스타일 탐색을 독립 실행형 응용 프로그램에 통합 하려면 클래스를 사용할 수 있습니다 <xref:System.Windows.Navigation.NavigationWindow> . <xref:System.Windows.Navigation.NavigationWindow>는에서 파생 <xref:System.Windows.Window> 되며 xbap에서 제공 하는 탐색에 대해 동일한 지원으로 확장 됩니다. <xref:System.Windows.Navigation.NavigationWindow>독립 실행형 응용 프로그램의 주 창 또는 대화 상자와 같은 보조 창으로를 사용할 수 있습니다.

<xref:System.Windows.Navigation.NavigationWindow>WPF (, 등)에서 대부분의 최상위 클래스와 마찬가지로를 구현 <xref:System.Windows.Window> 하려면 <xref:System.Windows.Controls.Page> 태그와 코드 숨김으로 이루어진 조합을 사용 합니다. 다음 예제에서 이를 확인할 수 있습니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#NavigationWindowMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml#navigationwindowmarkup)]

[!code-csharp[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/MainWindow.xaml.cs#navigationwindowcodebehind)]
[!code-vb[IntroToNavNavigationWindowSnippets#NavigationWindowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/MainWindow.xaml.vb#navigationwindowcodebehind)]

이 코드는 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Page> 가 열릴 때 (page.xaml)를 자동으로 탐색 하는를 만듭니다. <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow>가 주 응용 프로그램 창인 경우 특성을 사용 하 여 시작할 수 있습니다 `StartupUri` . 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchNavWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/App.xaml#applaunchnavwindow)]

다음 그림에서는을 <xref:System.Windows.Navigation.NavigationWindow> 독립 실행형 응용 프로그램의 주 창으로 보여 줍니다.

![주 창](./media/navigation-overview/navigation-window-as-main-window.png "주 창으로 서의 탐색 창")

이 그림에서는 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow> 앞의 예제에서 구현 코드에 설정 되지 않은 경우에도에 제목이 있음을 볼 수 있습니다. 대신, <xref:System.Windows.Controls.Page.WindowTitle%2A> 다음 코드에 표시 된 속성을 사용 하 여 제목을 설정 합니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup1)]
[!code-xaml[IntroToNavNavigationWindowSnippets#HomePageMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/HomePage.xaml#homepagemarkup2)]

<xref:System.Windows.Controls.Page.WindowWidth%2A>및 속성을 설정 <xref:System.Windows.Controls.Page.WindowHeight%2A> 하면에도 영향을 줍니다 <xref:System.Windows.Navigation.NavigationWindow> .

일반적으로 <xref:System.Windows.Navigation.NavigationWindow> 동작 또는 해당 모양을 사용자 지정 해야 하는 경우 사용자 고유의을 구현 합니다. 두 방법을 모두 사용하지 않으려면 바로 가기를 사용할 수 있습니다. 독립 실행형 응용 프로그램에서의 pack URI를로 지정 하면에서 <xref:System.Windows.Controls.Page> <xref:System.Windows.Application.StartupUri%2A> <xref:System.Windows.Application> 자동으로를 만들어를 <xref:System.Windows.Navigation.NavigationWindow> 호스팅합니다 <xref:System.Windows.Controls.Page> . 다음 태그에서는 이 기능을 설정하는 방법을 보여 줍니다.

[!code-xaml[IntroToNavNavigationWindowSnippets#AppLaunchPage](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/AnotherApp.xaml#applaunchpage)]

대화 상자와 같은 보조 응용 프로그램 창을으로 <xref:System.Windows.Navigation.NavigationWindow> 사용 하려면 다음 예제의 코드를 사용 하 여 열 수 있습니다.

[!code-csharp[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/csharp/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/CSharp/DialogOwnerWindow.xaml.cs#createnwdialogbox)]
[!code-vb[IntroToNavNavigationWindowSnippets#CreateNWDialogBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/IntroToNavNavigationWindowSnippets/VisualBasic/DialogOwnerWindow.xaml.vb#createnwdialogbox)]

다음 그림에서는 결과를 보여 줍니다.

![대화 상자](./media/navigation-overview/navigation-window-as-dialog-box.png "대화 상자로 서의 탐색 창")

여기에서 볼 수 있듯이 <xref:System.Windows.Navigation.NavigationWindow> 은 사용자가 저널을 탐색할 수 있는 Internet Explorer 스타일의 **뒤로** 및 **앞으로** 단추를 표시 합니다. 이러한 단추는 다음 그림에 나와 있는 것처럼 동일한 사용자 환경을 제공합니다.

![NavigationWindow의 뒤로 및 앞으로 단추](./media/navigation-overview/back-and-forward-buttons-in-navigation-window.png "탐색 창의 뒤로 및 앞으로 단추")

페이지에서 자체 저널 탐색 지원 및 UI를 제공 하는 경우 속성의 값을로 설정 하 여에 표시 되는 **뒤로** 및 **앞으로** 단추를 숨길 수 있습니다 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Navigation.NavigationWindow.ShowsNavigationUI%2A> `false` .

또는 WPF의 사용자 지정 지원을 사용 하 여 자체의를 바꿀 수 있습니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Navigation.NavigationWindow> .

<a name="Frame_in_Standalone_Applications"></a>

## <a name="the-frame-class"></a>Frame 클래스

브라우저와는 모두 <xref:System.Windows.Navigation.NavigationWindow> 탐색 가능한 콘텐츠를 호스트 하는 창입니다. 애플리케이션의 콘텐츠가 전체 창에서 호스트될 필요가 없는 경우가 있습니다. 대신, 이러한 콘텐츠는 다른 콘텐츠 내에 호스트됩니다. 클래스를 사용 하 여 탐색 가능한 콘텐츠를 다른 콘텐츠에 삽입할 수 있습니다 <xref:System.Windows.Controls.Frame> . <xref:System.Windows.Controls.Frame>및 Xbap와 동일한 지원을 제공 합니다 <xref:System.Windows.Navigation.NavigationWindow> .

다음 예제에서는 요소를 사용 하 여를 선언적으로에 추가 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.Frame> <xref:System.Windows.Controls.Page> `Frame` .

[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPage.xaml#framehostpagexaml3)]

이 태그는 `Source` `Frame` <xref:System.Windows.Controls.Page> 가 <xref:System.Windows.Controls.Frame> 처음으로 탐색 해야 하는에 대 한 pack URI를 사용 하 여 요소의 특성을 설정 합니다. 다음 그림에서는 <xref:System.Windows.Controls.Page> <xref:System.Windows.Controls.Frame> 여러 페이지 간에 탐색 된가 있는의 XBAP를 보여 줍니다.

![여러 페이지 간에 탐색된 프레임](./media/navigation-overview/frame-navigation-between-multiple-pages.png "그러면 여러 페이지 간의 프레임 탐색이 표시 됩니다.")

콘텐츠 내에서를 사용 해야 하는 것은 <xref:System.Windows.Controls.Frame> 아닙니다 <xref:System.Windows.Controls.Page> . 의 콘텐츠 내에서을 호스트 하는 것도 일반적입니다 <xref:System.Windows.Controls.Frame> <xref:System.Windows.Window> .

기본적으로에서는 <xref:System.Windows.Controls.Frame> 다른 저널이 없는 경우에만 자체 저널을 사용 합니다. <xref:System.Windows.Controls.Frame>이 또는 xbap 내에서 호스팅되는 콘텐츠의 일부인 경우는 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame> 또는 xbap에 속한 저널을 사용 합니다 <xref:System.Windows.Navigation.NavigationWindow> . 그러나 경우에 따라 <xref:System.Windows.Controls.Frame> 자체 저널을 담당 해야 할 수도 있습니다. 한 가지 이유는에서 호스팅하는 페이지 내에서 저널 탐색을 허용 하는 것입니다 <xref:System.Windows.Controls.Frame> . 다음 그림에서 이를 확인할 수 있습니다.

![프레임 및 페이지 다이어그램](./media/navigation-overview/journal-navigation-within-pages-hosted-by-a-frame.png "프레임에서 호스트 되는 페이지 내에서 저널 탐색을 표시 합니다.")

이 경우 <xref:System.Windows.Controls.Frame> 의 속성을로 설정 하 여 자체의 저널을 사용 하도록를 구성할 수 있습니다 <xref:System.Windows.Controls.Frame.JournalOwnership%2A> <xref:System.Windows.Controls.Frame> <xref:System.Windows.Navigation.JournalOwnership.OwnsJournal> . 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageOwnJournalXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnJournal.xaml#framehostpageownjournalxaml3)]

다음 그림에서는 <xref:System.Windows.Controls.Frame> 자체 저널을 사용 하는 내에서 탐색 하는 경우의 효과를 보여 줍니다.

![자체 저널을 사용하는 프레임](./media/navigation-overview/frame-uses-its-own-journal.png "이는 자체 저널을 사용 하는 프레임 내에서 탐색의 효과를 보여 줍니다.")

저널 항목은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Internet Explorer가 아닌의 탐색에서 표시 됩니다 <xref:System.Windows.Controls.Frame> .

> [!NOTE]
> <xref:System.Windows.Controls.Frame>이에서 호스팅되는 콘텐츠의 일부인 경우는 자체 저널을 <xref:System.Windows.Window> <xref:System.Windows.Controls.Frame> 사용 하므로 자체 탐색을 표시 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 합니다.

사용자 환경에서 <xref:System.Windows.Controls.Frame> 탐색을 표시 하지 않고 자체 업무 일지를 제공 해야 하는 경우 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 를로 설정 하 여 탐색을 숨길 수 있습니다 <xref:System.Windows.Controls.Frame.NavigationUIVisibility%2A> <xref:System.Windows.Visibility.Hidden> . 다음 태그에서 이를 확인할 수 있습니다.

[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml1)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml2)]
[!code-xaml[NavigationOverviewSnippets#FrameHostPageHidesUIXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHostPageOwnHiddenJournal.xaml#framehostpagehidesuixaml3)]

<a name="Navigation_Hosts"></a>

## <a name="navigation-hosts"></a>탐색 호스트

<xref:System.Windows.Controls.Frame>및 <xref:System.Windows.Navigation.NavigationWindow> 는 탐색 호스트 라고 하는 클래스입니다. *탐색 호스트* 는 콘텐츠를 탐색 하 고 표시할 수 있는 클래스입니다. 이를 위해 각 탐색 호스트는 자체 <xref:System.Windows.Navigation.NavigationService> 및 저널을 사용 합니다. 다음 그림은 탐색 호스트의 기본 구성을 보여 줍니다.

![탐색기 다이어그램](./media/navigation-overview/navigation-host-construction.png "탐색 호스트의 기본 생성")

기본적으로 <xref:System.Windows.Navigation.NavigationWindow> 및 <xref:System.Windows.Controls.Frame> 는 브라우저에서 호스팅될 때 XBAP에서 제공 하는 것과 동일한 탐색 지원 기능을 제공 합니다.

<xref:System.Windows.Navigation.NavigationService>및 저널을 사용 하는 것 외에도 탐색 호스트는을 구현 하는 동일한 멤버를 구현 <xref:System.Windows.Navigation.NavigationService> 합니다. 다음 그림에서 이를 확인할 수 있습니다.

![프레임 및 탐색 창의 저널](./media/navigation-overview/navigation-window-and-frame.png "탐색 창 및 프레임")

이를 통해 직접 탐색 지원을 프로그래밍할 수 있습니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에서 호스트 되는에 대 한 사용자 지정 탐색을 제공 해야 하는 경우이를 고려할 수 있습니다 <xref:System.Windows.Controls.Frame> <xref:System.Windows.Window> . 또한 두 형식은 모두 (,) 및 (,)를 포함 하 여 추가 탐색 관련 멤버를 구현 하며,이 `BackStack` <xref:System.Windows.Navigation.NavigationWindow.BackStack%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Frame.BackStack%2A?displayProperty=nameWithType> `ForwardStack` <xref:System.Windows.Navigation.NavigationWindow.ForwardStack%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.Frame.ForwardStack%2A?displayProperty=nameWithType> 를 통해 뒤로 스택 및 전달 스택의 저널 항목을 열거할 수 있습니다.

앞서 언급했듯이 애플리케이션에는 둘 이상의 저널이 있을 수 있습니다. 다음 그림은 이러한 상황이 발생할 수 있는 예제를 제공합니다.

![한 응용 프로그램 내의 여러 저널](./media/navigation-overview/multiple-journals-in-one-application.png "응용 프로그램에서 둘 이상의 저널에 대 한 예제입니다.")

<a name="Navigating_to_Content_Other_than_Pages"></a>

## <a name="navigating-to-content-other-than-xaml-pages"></a>XAML 페이지 이외의 콘텐츠 탐색

이 항목 전체에서 <xref:System.Windows.Controls.Page> 및 Pack xbap는 WPF의 다양 한 탐색 기능을 보여 주기 위해 사용 되었습니다. 그러나 <xref:System.Windows.Controls.Page> 응용 프로그램으로 컴파일되는는 탐색할 수 있는 유일한 콘텐츠 형식이 아닙니다 .이를 Pack xbap는 콘텐츠를 식별 하는 유일한 방법이 아닙니다.

이 단원에서 설명 하는 것 처럼 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일, HTML 파일 및 개체로 이동할 수도 있습니다.

<a name="Navigating_to_Loose_XAML_Files"></a>

### <a name="navigating-to-loose-xaml-files"></a>XAML 사용 완화 파일 탐색

느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 다음과 같은 특징이 있는 파일입니다.

- 에는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] (즉, 코드 없음)만 포함 됩니다.

- 적절한 네임스페이스 선언이 있습니다.

- .xaml 파일 이름 확장명이 있습니다.

예를 들어 느슨한 파일인 Person으로 저장 된 다음 콘텐츠를 살펴보겠습니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]

[!code-xaml[NavigationOverviewSnippets#LooseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/Person.xaml#loosexaml)]

파일을 두 번 클릭하면 브라우저가 열리고 콘텐츠를 탐색 및 표시합니다. 다음 그림에서 이를 확인할 수 있습니다.

![Person.XAML 파일의 콘텐츠 표시](./media/navigation-overview/contents-of-person-xaml-file.png "Person .XAML 파일의 내용을 표시 합니다.")

다음에서 느슨한 파일을 표시할 수 있습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] .

- 로컬 컴퓨터, 인트라넷 또는 인터넷의 웹 사이트

- UNC (범용 명명 규칙) 파일 공유

- 로컬 디스크

느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 브라우저의 즐겨찾기에 추가 하거나 브라우저의 홈 페이지에 추가할 수 있습니다.

> [!NOTE]
> 느슨한 페이지를 게시 하 고 시작 하는 방법에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [WPF 응용 프로그램 배포](deploying-a-wpf-application-wpf.md)를 참조 하세요.

느슨한 사용에 대 한 제한 사항 중 하나는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 부분 신뢰로 실행 하기에 안전한 콘텐츠만 호스트할 수 있다는 것입니다. 예를 들어는 `Window` 느슨한 파일의 루트 요소가 될 수 없습니다 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] . 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_HTML_Files_Using_Frame"></a>

### <a name="navigating-to-html-files-by-using-frame"></a>프레임을 사용하여 HTML 파일 탐색

짐작할 수 있듯이 HTML로 이동할 수도 있습니다. Http 체계를 사용 하는 URI를 제공 하기만 하면 됩니다. 예를 들어 다음은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Frame> HTML 페이지로 이동 하는을 보여 줍니다.

[!code-xaml[NavigationOverviewSnippets#FrameHtmlNavMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigationOverviewSnippets/CSharp/FrameHTMLNavPage.xaml#framehtmlnavmarkup)]

HTML로 이동 하려면 특수 권한이 필요 합니다. 예를 들어 인터넷 영역 부분 신뢰 보안 샌드박스에서 실행 되는 XBAP에서 이동할 수 없습니다. 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_HTML_Files_Using_WebBrowser"></a>

### <a name="navigating-to-html-files-by-using-the-webbrowser-control"></a>WebBrowser 컨트롤을 사용하여 HTML 파일 탐색

<xref:System.Windows.Controls.WebBrowser>컨트롤은 HTML 문서 호스팅, 탐색 및 스크립트/관리 코드 상호 운용성을 지원 합니다. 컨트롤에 대 한 자세한 내용은 <xref:System.Windows.Controls.WebBrowser> 을 참조 하십시오 <xref:System.Windows.Controls.WebBrowser> .

와 마찬가지로 <xref:System.Windows.Controls.Frame> 를 사용 하 여 HTML로 이동 하려면 <xref:System.Windows.Controls.WebBrowser> 특수 권한이 필요 합니다. 예를 들어 부분 신뢰 응용 프로그램에서는 원본 사이트에 있는 HTML로만 이동할 수 있습니다. 자세한 내용은 [WPF 부분 신뢰 보안](../wpf-partial-trust-security.md)을 참조하세요.

<a name="Navigating_to_Objects"></a>

### <a name="navigating-to-custom-objects"></a>사용자 지정 개체 탐색

사용자 지정 개체로 저장 되는 데이터가 있는 경우 해당 데이터를 표시 하는 한 가지 방법은 해당 개체에 바인딩되는 콘텐츠를 사용 하 여를 만드는 것입니다 <xref:System.Windows.Controls.Page> ( [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)참조). 개체를 표시하기 위해 전체 페이지를 만드는 오버헤드가 필요하지 않으면 페이지를 직접 탐색할 수 있습니다.

`Person`다음 코드에서 구현 된 클래스를 살펴보겠습니다.

[!code-csharp[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/Person.cs#personclasscode)]
[!code-vb[NavigateToObjectSnippets#PersonClassCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/Person.vb#personclasscode)]

이로 이동 하려면 <xref:System.Windows.Navigation.NavigationWindow.Navigate%2A?displayProperty=nameWithType> 다음 코드에서 보여 주는 것 처럼 메서드를 호출 합니다.

[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject1](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject1)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject2](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject2)]
[!code-xaml[NavigateToObjectSnippets#PageThatNavsToObject3](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml#pagethatnavstoobject3)]

[!code-csharp[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/HomePage.xaml.cs#pagethatnavstoobjectcodebehind)]
[!code-vb[NavigateToObjectSnippets#PageThatNavsToObjectCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/NavigateToObjectSnippets/VisualBasic/HomePage.xaml.vb#pagethatnavstoobjectcodebehind)]

다음 그림에서는 결과를 보여 줍니다.

![클래스로 탐색하는 페이지](./media/navigation-overview/page-navigates-to-an-object.png "개체를 탐색 하는 페이지의 예입니다.")

이 그림에서 유용한 콘텐츠가 표시되지 않는 것을 볼 수 있습니다. 실제로 표시 되는 값은 `ToString` **Person** 개체에 대 한 메서드의 반환 값입니다. 기본적으로이 값은 WPF에서 개체를 나타내는 데 사용할 수 있는 유일한 값입니다. `ToString`보다 의미 있는 정보를 반환 하도록 메서드를 재정의할 수 있지만 여전히 문자열 값입니다. WPF의 프레젠테이션 기능을 활용 하는 데 사용할 수 있는 방법 중 하나는 데이터 템플릿을 사용 하는 것입니다. WPF에서 특정 형식의 개체와 연결할 수 있는 데이터 템플릿을 구현할 수 있습니다. 다음 코드는 개체에 대 한 데이터 템플릿을 보여 줍니다 `Person` .

[!code-xaml[NavigateToObjectSnippets#DataTemplateMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/NavigateToObjectSnippets/CSharp/App.xaml#datatemplatemarkup)]

여기서 데이터 템플릿은 `Person` `x:Type` 특성에서 태그 확장을 사용 하 여 형식과 연결 됩니다 `DataType` . 그런 다음 데이터 템플릿은 `TextBlock` 요소 (참조 <xref:System.Windows.Controls.TextBlock> )를 클래스의 속성에 바인딩합니다 `Person` . 다음 그림은 개체의 업데이트 된 모양을 보여 줍니다 `Person` .

![데이터 템플릿이 있는 클래스로 탐색](./media/navigation-overview/navigating-to-a-class.png "데이터 템플릿이 있는 클래스로 이동 합니다.")

이 기술의 장점은 데이터 템플릿을 다시 사용하여 애플리케이션의 어디에서든 일관적으로 개체를 표시할 수 있다는 점입니다.

데이터 템플릿에 대 한 자세한 내용은 [데이터 템플릿 개요](../data/data-templating-overview.md)를 참조 하세요.

<a name="Security"></a>

## <a name="security"></a>보안

WPF 탐색 지원을 사용 하면 인터넷을 통해 Xbap를 탐색할 수 있으며 응용 프로그램에서 타사 콘텐츠를 호스트할 수 있습니다. 응용 프로그램과 사용자를 유해한 동작 으로부터 보호 하기 위해 WPF는 [보안](../security-wpf.md) 및 [Wpf 부분 신뢰 보안](../wpf-partial-trust-security.md)에 설명 된 다양 한 보안 기능을 제공 합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Application.SetCookie%2A>
- <xref:System.Windows.Application.GetCookie%2A>
- [응용 프로그램 관리 개요](application-management-overview.md)
- [WPF의 Pack URI](pack-uris-in-wpf.md)
- [구조적 탐색 개요](structured-navigation-overview.md)
- [탐색 토폴로지 개요](navigation-topologies-overview.md)
- [방법 도움말 항목](navigation-how-to-topics.md)
- [WPF 애플리케이션 배포](deploying-a-wpf-application-wpf.md)
