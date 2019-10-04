---
title: WPF의 양방향 기능 개요
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 2a599322ef955b9f702f8960f294f5d093ede74a
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834743"
---
# <a name="bidirectional-features-in-wpf-overview"></a>WPF의 양방향 기능 개요

다른 개발 플랫폼과 달리에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 는 양방향 콘텐츠를 신속 하 게 개발할 수 있는 많은 기능이 있습니다. 예를 들어, 왼쪽에서 오른쪽으로, 오른쪽에서 왼쪽으로의 데이터를 동일한 문서에 혼합할 수 있습니다. 동시에는 아랍어, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 히브리어 등의 양방향 기능을 필요로 하는 사용자에 게 뛰어난 환경을 만듭니다.

다음 섹션에서는 최상의 양방향 콘텐츠 표시를 수행하는 방법을 보여주는 예제와 함께 다양한 양방향 기능을 설명합니다. 대부분의 샘플에서는를 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]사용 하지만 또는 Microsoft Visual Basic 코드에 대 C# 한 개념을 쉽게 적용할 수 있습니다.

<a name="FlowDirection"></a>

## <a name="flowdirection"></a>FlowDirection

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서 콘텐츠 흐름 방향을 정의 하는 기본 속성은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>입니다. 이 속성은 두 열거형 값 <xref:System.Windows.FlowDirection.LeftToRight> 중 하나 또는 <xref:System.Windows.FlowDirection.RightToLeft>로 설정할 수 있습니다. 속성은에서 <xref:System.Windows.FrameworkElement>상속 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 모든 요소에 사용할 수 있습니다.

다음 예에서는 <xref:System.Windows.Controls.TextBox> 요소의 흐름 방향을 설정 합니다.

**왼쪽에서 오른쪽 흐름 방향**

[!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]

**오른쪽에서 왼쪽 흐름 방향**

[!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]

다음 그림에서는 이전 코드 렌더링 방법을 보여 줍니다.

![여러 흐름 방향을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)

[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 트리 내의 요소는 해당 컨테이너에서를 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 상속 합니다. 다음 예제 <xref:System.Windows.Controls.TextBlock> 에서는에 있는 <xref:System.Windows.Controls.Grid>내 <xref:System.Windows.Window>에 있습니다. <xref:System.Windows.FrameworkElement.FlowDirection%2A> 에 대해를<xref:System.Windows.Controls.Grid> 설정 하면 및 <xref:System.Windows.Controls.TextBlock> 에 대 한 설정도 암시됩니다.<xref:System.Windows.Window>

다음 예에서는를 설정 <xref:System.Windows.FrameworkElement.FlowDirection%2A>하는 방법을 보여 줍니다.

[!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]

최상위 수준 <xref:System.Windows.Window> 에는 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>가 있으므로 그 안에 포함 된 모든 요소도 동일한 <xref:System.Windows.FrameworkElement.FlowDirection%2A>를 상속 합니다. 지정 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 된를 재정의 하는 요소에 대해를 <xref:System.Windows.FlowDirection.LeftToRight>변경 하는 이전 예제의 두 번째 <xref:System.Windows.Controls.TextBlock> 와 같은 명시적 방향 변경을 추가 해야 합니다. 를 정의 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 하지 않으면 기본값이 <xref:System.Windows.FlowDirection.LeftToRight> 적용 됩니다.

다음 그림에서는 이전 예제의 출력을 보여 줍니다.

![명시적 흐름 방향 변경을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)

<a name="FlowDocument"></a>

## <a name="flowdocument"></a>FlowDocument

HTML, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Java 등의 많은 개발 플랫폼은 양방향 콘텐츠 개발에 대 한 특별 한 지원을 제공 합니다. HTML과 같은 태그 언어는 필요한 모든 방향으로 텍스트를 표시 하는 데 필요한 태그를 콘텐츠 작성기에 제공 합니다. 예를 들어, "rtl" 또는 "ltr"을 값으로 사용 하는 HTML 4.0 태그, "dir"입니다. 이 태그는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성과 유사 하지만 속성은 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 텍스트 내용을 레이아웃 하는 고급 방법으로 작동 하며 텍스트 이외의 내용에 사용할 수 있습니다.

에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 는 <xref:System.Windows.Documents.FlowDocument> 텍스트, 테이블, 이미지 및 기타 요소의 조합을 호스트할 수 있는 다목적 요소입니다. 다음 섹션의 샘플은 이 요소를 사용합니다.

텍스트를에 추가 <xref:System.Windows.Documents.FlowDocument> 하는 것이 한 가지 방법으로 수행 될 수 있습니다. 이 작업을 수행 하는 간단한 방법은 텍스트 <xref:System.Windows.Documents.Paragraph> 와 같은 콘텐츠를 그룹화 하는 데 사용 되는 블록 수준 요소인를 사용 하는 것입니다. 인라인 수준 요소에 텍스트를 추가 하려면 샘플에서 및 <xref:System.Windows.Documents.Span> <xref:System.Windows.Documents.Run>를 사용 합니다. <xref:System.Windows.Documents.Span>는 다른 인라인 요소를 그룹화 하는 데 사용 되는 인라인 수준의 유동 콘텐츠 요소 <xref:System.Windows.Documents.Run> 이 고,는 서식이 지정 되지 않은 텍스트의 실행을 포함 하기 위한 인라인 수준 유동 콘텐츠 요소입니다. 에 <xref:System.Windows.Documents.Span> 는 여러 <xref:System.Windows.Documents.Run> 요소가 포함 될 수 있습니다.

첫 번째 문서 예제에는 여러 네트워크 공유 이름을 포함 하는 문서가 포함 되어 있습니다. 예를 `\\server1\folder\file.ext`들면입니다. 이 네트워크 링크가 아랍어나 영어 문서에 있는지 여부에 따라 같은 방식으로 항상 표시될 수 있습니다. 다음 그림에서는 Span 요소를 사용 하는 방법을 보여 주고 아랍어 <xref:System.Windows.FlowDirection.RightToLeft> 문서의 링크를 보여 줍니다.

![Span 요소를 사용 하는 방법을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")

텍스트는 "\\" <xref:System.Windows.FlowDirection.RightToLeft>와 같은 모든 특수 문자는 오른쪽에서 왼쪽 순서로 텍스트를 구분 합니다. 이렇게 하면 링크가 올바른 순서로 표시 되지 않으므로 문제를 해결 하기 위해 텍스트를 포함 하 여 별도의 <xref:System.Windows.Documents.Run> 흐름 <xref:System.Windows.FlowDirection.LeftToRight>을 유지 해야 합니다. 각 언어에 대해 별도 <xref:System.Windows.Documents.Run> 의를 사용 하는 대신, 문제를 해결 하는 더 좋은 방법은 덜 자주 사용 되는 영어 텍스트를 더 <xref:System.Windows.Documents.Span>큰 아랍어에 포함 하는 것입니다.

다음 그림에서는 Span 요소에 포함 된 Run 요소를 사용 하 여이를 보여 줍니다.

![Span 요소에 포함 된 실행 요소를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)

다음 예제에서는 문서에서 <xref:System.Windows.Documents.Run> 및 <xref:System.Windows.Documents.Span> 요소를 사용 하는 방법을 보여 줍니다.

[!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]

<a name="SpanElements"></a>

## <a name="span-elements"></a>Span 요소

요소 <xref:System.Windows.Documents.Span> 는 흐름 방향이 다른 텍스트 간의 경계 구분 기호로 사용 됩니다.  흐름 방향이 동일한 <xref:System.Windows.Documents.Span> <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span> 요소도 서로 다른 양방향 범위를 사용 하는 것으로 간주 됩니다. 즉, 요소가 컨테이너에서 정렬 되 고 요소 내의 콘텐츠만 <xref:System.Windows.Documents.Span> 의를 <xref:System.Windows.FlowDirection>따릅니다. <xref:System.Windows.Documents.Span>

다음 그림에서는 여러 <xref:System.Windows.Controls.TextBlock> 요소의 흐름 방향을 보여 줍니다.

![서로 다른 흐름 방향을 사용 하 여 텍스트 블록을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)

다음 예제에서는 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run> 요소를 사용 하 여 이전 그래픽에 표시 된 결과를 생성 하는 방법을 보여 줍니다.

[!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]

<xref:System.Windows.FlowDirection> <xref:System.Windows.FlowDirection> <xref:System.Windows.Documents.Span> 샘플의 <xref:System.Windows.Documents.Span> 요소에서 요소는 해당 부모의에 따라 배치 되지만 각 요소 내의 텍스트는 자체에 따라 흐릅니다. <xref:System.Windows.Controls.TextBlock> 라틴어와 아랍어 또는 다른 언어에 적용됩니다.

### <a name="adding-xmllang"></a>Xml:lang 추가

다음 그림에서는와 `"200.0+21.4=221.4"`같은 숫자 및 산술 식을 사용 하는 또 다른 예를 보여 줍니다. 만 설정 된 <xref:System.Windows.FlowDirection> 것을 볼 수 있습니다.

![FlowDirection만 사용 하 여 숫자를 표시 하는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)

가 올바른 경우에 <xref:System.Windows.FlowDirection> 도이 응용 프로그램의 사용자는 출력에 의해 실망 됩니다. 숫자는 아라비아 숫자로 모양이 지정 되지 않습니다.

XAML 요소에는 각 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 요소의 언어`xml:lang`를 정의 하는 특성 ()이 포함 될 수 있습니다. XAML은 트리의 부모 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 요소에 적용 `xml:lang` 된 값이 자식 요소에 사용 되는 언어 원칙도 지원 합니다. 이전 예제에서는 <xref:System.Windows.Documents.Run> 요소 또는 최상위 요소 중 하나에 대해 언어가 정의 되어 있지 않기 때문에 기본값이 `xml:lang` 사용 되었습니다 .이 `en-US` 는 XAML 용입니다. 의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 내부 숫자 셰이핑 알고리즘은 해당 언어의 숫자를 선택 합니다 .이 경우에는 영어입니다. 아랍어 숫자를 정확 `xml:lang` 하 게 렌더링 하려면를 설정 해야 합니다.

다음 그림에서는이 추가 된 `xml:lang` 예제를 보여 줍니다.

![오른쪽에서 왼쪽으로 흐르는 아랍어 숫자를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)

다음 예제에서는 응용 `xml:lang` 프로그램에를 추가 합니다.

[!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]

예를 들어,와 `xml:lang` `"ar-EG"` 같이 `"ar-SA"` 대상 영역에 따라 여러 언어의 값이 달라 지는 것을 알 수 있습니다. 이전 예제에서는 `xml:lang` 및 <xref:System.Windows.FlowDirection> 값을 모두 정의 해야 함을 보여 줍니다.

<a name="FlowDirectionNontext"></a>

## <a name="flowdirection-with-non-text-elements"></a>텍스트가 아닌 요소가 있는 FlowDirection

<xref:System.Windows.FlowDirection>텍스트 요소의 텍스트 흐름과 거의 모든 다른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소의 흐름 방향을 정의 합니다. 다음 그림에서는 가로 <xref:System.Windows.Controls.ToolBar> <xref:System.Windows.Media.LinearGradientBrush> 를 사용 하 여 왼쪽에서 오른쪽 그라데이션으로 배경을 그리는을 보여 줍니다.

![왼쪽에서 오른쪽으로 향하는 도구 모음을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)

<xref:System.Windows.FlowDirection> 을로 <xref:System.Windows.FlowDirection.RightToLeft>설정한 후에는 <xref:System.Windows.Controls.ToolBar> 단추가 오른쪽에서 왼쪽으로 정렬 되는 것이 아니라 realigns의 <xref:System.Windows.Media.LinearGradientBrush> 오프셋이 오른쪽에서 왼쪽으로 이동 합니다.

다음 그림에서는의 <xref:System.Windows.Media.LinearGradientBrush>재정렬 보여 줍니다.

![오른쪽에서 왼쪽으로 향하는 도구 모음을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)

다음 예제에서는을 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>그립니다. 왼쪽에서 오른쪽으로 그리려면에서 <xref:System.Windows.FlowDirection> 특성 <xref:System.Windows.Controls.ToolBar>을 제거 합니다.

[!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]

<a name="FlowDirectionExceptions"></a>

### <a name="flowdirection-exceptions"></a>FlowDirection 예외

<xref:System.Windows.FlowDirection> 가 예상 대로 작동 하지 않는 경우가 있습니다. 이 섹션에서는 이러한 예외 중 두 가지를 설명합니다.

**이미지**

는 <xref:System.Windows.Controls.Image> 이미지를 표시 하는 컨트롤을 나타냅니다. 에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 표시할의를 <xref:System.Windows.Controls.Image.Source%2A> [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 정의 하는속성과함께사용할수있습니다<xref:System.Windows.Controls.Image> .

다른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소와 달리는 <xref:System.Windows.Controls.Image> 컨테이너에서를 <xref:System.Windows.FlowDirection> 상속 하지 않습니다. 그러나 <xref:System.Windows.FlowDirection> 이 명시적으로로 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.Image> 설정 되어 있으면가 가로로 대칭 이동 되어 표시 됩니다. 양방향 콘텐츠의 개발자에게 편리한 기능으로 구현됩니다. 경우에 따라 이미지를 가로로 대칭 이동하면 원하는 효과가 나타나기 때문입니다.

다음 그림에서는 대칭 이동 <xref:System.Windows.Controls.Image>을 보여 줍니다.

![대칭 이동 된 이미지를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)

다음 예제에서는가 <xref:System.Windows.Controls.Image> 이를 포함 <xref:System.Windows.Controls.StackPanel> 하는 <xref:System.Windows.FlowDirection> 에서를 상속 하지 못하는 것을 보여 줍니다.

> [!NOTE]
> C:\에 ms_logo 라는 파일이 있어야 합니다 **.** 이 예를 실행 하는 드라이브입니다.

[!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]

> [!NOTE]
> 다운로드 파일에 포함 된 파일은 **ms_logo** 파일입니다. 코드는 .jpg 파일이 프로젝트 내에 있지 않지만 C:\ 드라이브 어딘가에 있다고 가정합니다. 프로젝트 파일에서 C:\ 드라이브로 .jpg를 복사하거나 프로젝트 내부에서 파일을 찾도록 코드를 변경해야 합니다. 이렇게 하려면을로 `Source="file://c:/ms_logo.jpg"` `Source="ms_logo.jpg"`변경 합니다.

**경로**

외 <xref:System.Windows.Controls.Image>에도 또 다른 흥미로운 요소는 <xref:System.Windows.Shapes.Path>입니다. 경로는 일련의 연결된 선 및 곡선을 그릴 수 있는 개체입니다. <xref:System.Windows.Controls.Image> <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> 와관련<xref:System.Windows.FlowDirection.LeftToRight> 된와 유사한 방식으로 동작 합니다. 예를 들어 ,는해당항목의가로미러입니다.<xref:System.Windows.FlowDirection> 그러나와 달리는 <xref:System.Windows.Controls.Image>컨테이너 <xref:System.Windows.Shapes.Path> <xref:System.Windows.FlowDirection> 에서를 상속 하며,이를 명시적으로 지정할 필요는 없습니다.

다음 예제에서는 3개의 선을 사용하여 간단한 화살표를 그립니다. 첫 번째 화살표는의 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.StackPanel> 흐름 방향을 상속 하므로 시작점과 끝점은 우변에 있는 루트에서 측정 됩니다. <xref:System.Windows.FlowDirection.RightToLeft> 명시적<xref:System.Windows.FlowDirection> 이 있는 두 번째 화살표는 우변에도 시작 됩니다. 그러나 세 번째 화살표는 왼쪽에 시작 루트가 있습니다. 그리기에 대 한 자세한 내용은 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.GeometryGroup>을 참조 하십시오.

[!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]

다음 그림은 요소를 `Path` 사용 하 여 화살표가 그려진 이전 예제의 출력을 보여 줍니다.

![Path 요소를 사용 하 여 그린 화살표를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)

및 <xref:System.Windows.Controls.Image> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 은에서 사용<xref:System.Windows.FlowDirection>하는 방법의 두 가지 예입니다. <xref:System.Windows.Shapes.Path> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.InkPresenter> <xref:System.Windows.Media.LinearGradientBrush> 컨테이너내<xref:System.Windows.Media.RadialGradientBrush>에서 특정 방향으로 요소를 배치 하는 것 외에도,, 화면에서 잉크를 렌더링 하는 등의 요소와 함께 사용할 수있습니다.<xref:System.Windows.FlowDirection> 왼쪽에서 오른쪽으로의 동작을 모방 하는 콘텐츠에 대 한 오른쪽에서 왼쪽 동작이 필요 하거나 그 반대의 경우에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 는에서 해당 기능을 제공 합니다.

<a name="NumberSubstitution"></a>

## <a name="number-substitution"></a>숫자 대체

지금까지 Windows는 동일한 숫자에 대해 다양 한 문화권 셰이프를 표현할 수 있도록 허용 하는 동시에 숫자 대체를 지원 합니다. 예를 들어 숫자는 서로 다른 로캘 간에 통합 되어 있습니다. 잘 알려진 16 진수 값 0x40, 0x41, 선택한 언어에 따라 표시 됩니다.

이렇게 하면 응용 프로그램에서 한 언어에서 다른 언어로 변환할 필요 없이 숫자 값을 처리할 수 있습니다. 예를 들어 사용자가 지역화 된 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] 아랍어 창에서 스프레드시트를 열고 아랍어로 표시 된 숫자를 볼 수 있지만에서 열 수 있습니다. 유럽 버전의 Windows를 통해 동일한 숫자의 유럽 표현을 볼 수 있습니다. 보통 동일한 문서에서 숫자와 같이 표시되기 때문에 쉼표 구분 기호와 백분율 기호와 같은 다른 기호에도 필요합니다.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 동일한 기능을 계속 유지하며 대체가 사용되는 시기와 방법을 사용자가 더 많이 제어할 수 있도록 이 기능에 대한 지원을 추가합니다. 이 기능은 모든 언어를 대상으로 하지만, 애플리케이션을 실행하는 다양한 문화권 때문에 특정 언어에 대한 숫자 모양을 애플리케이션 개발자가 지정하기 어려운 양방향 콘텐츠에서 더욱 유용합니다.

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 에서<xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 숫자 대체가 작동 하는 방식을 제어 하는 핵심 속성은 종속성 속성입니다. <xref:System.Windows.Media.NumberSubstitution> 클래스 텍스트의 숫자가 표시 하는 하는 방법을 지정 합니다. 동작을 정의하는 세 가지 공용 속성이 있습니다. 다음은 각 속성에 대 한 요약입니다.

**CultureSource:**

이 속성은 숫자에 대한 문화권을 결정하는 방법을 지정합니다. 이 클래스는 세 가지 <xref:System.Windows.Media.NumberCultureSource> 열거형 값 중 하나를 사용 합니다.

- 덮어쓸 Number 문화권이 속성의 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 입니다.

- 본문 Number culture는 텍스트 실행의 문화권입니다. 태그 `xml:lang`에서, 또는 별칭 `Language` 속성 (<xref:System.Windows.FrameworkElement.Language%2A> 또는 <xref:System.Windows.FrameworkContentElement.Language%2A>)입니다. 또한에서 <xref:System.Windows.FrameworkContentElement>파생 되는 클래스에 대 한 기본값입니다. 이러한 클래스 <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType> 에는<xref:System.Windows.Documents.Table?displayProperty=nameWithType>, 및등이있습니다.<xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>

- 사용자: Number culture는 현재 스레드의 문화권입니다. <xref:System.Windows.FrameworkElement> 이 속성은, <xref:System.Windows.Controls.Page> <xref:System.Windows.Window> 및 와같은의모든서브클래스에대한기본값입니다.<xref:System.Windows.Controls.TextBlock>

**CultureOverride**:

속성은 <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> 속성이로 설정 된 경우에 <xref:System.Windows.Media.NumberCultureSource.Override> 만 사용 되 고 그렇지 않은 경우에는 무시 됩니다. <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 숫자 문화권을 지정합니다. 기본값인 값 `null`은 en-us로 해석 됩니다.

**대체**:

이 속성에는 수행할 숫자 대체의 형식을 지정합니다. 다음 <xref:System.Windows.Media.NumberSubstitutionMethod> 열거형 값 중 하나를 사용 합니다.

- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: 대체 메서드는 숫자 문화권의 <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> 속성에 따라 결정 됩니다. 이 값이 기본값입니다.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: 숫자 문화권이 아랍어 또는 이란어 문화권이 면 해당 숫자는 컨텍스트에 따라 달라 집니다.

- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: 숫자는 항상 유럽 숫자로 렌더링 됩니다.

- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: 숫자는 문화권의 <xref:System.Globalization.CultureInfo.NumberFormat%2A>에 지정 된 대로 숫자 문화권에 대 한 국가별 숫자를 사용 하 여 렌더링 됩니다.

- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: 숫자는 숫자 문화권에 대 한 기존 숫자를 사용 하 여 렌더링 됩니다. 대부분의 문화권에서이는와 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>동일 합니다. 그러나는 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> 일부 아랍어 문화권의 경우 라틴 숫자를 반환 하는 반면,이 값을 사용할 경우 모든 아랍어 문화권에 대해 아랍어 숫자가 생성 됩니다.

이 값은 양방향 콘텐츠 개발자에게 무슨 의미입니까? 대부분의 경우 개발자는와 <xref:System.Windows.FlowDirection> 각 텍스트 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소의 언어를 정의 하기만 하면 됩니다. 예 `Language="ar-SA"` 를 들어 논리는 <xref:System.Windows.Media.NumberSubstitution> 올바른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]에 따라 숫자를 표시 합니다. 다음 예제에서는 아랍어 버전의 Windows에서 실행 되는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 아랍어 및 영어 숫자를 사용 하는 방법을 보여 줍니다.

[!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]

다음 그림은 아랍어 및 영어 숫자가 표시 된 아랍어 버전의 Windows에서 실행 중인 경우 이전 샘플의 출력을 보여 줍니다.

![아랍어 및 영어 숫자를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)

이 경우 <xref:System.Windows.FlowDirection> 를로 <xref:System.Windows.FlowDirection.LeftToRight> 설정 하면 유럽 숫자가 생성 되기 때문에이 중요 했습니다.<xref:System.Windows.FlowDirection> 다음 섹션에서는 문서 전체에서 숫자를 단일하게 표시하는 방법을 설명합니다. 이 예제에서 아랍어 창을 실행하지 않는 경우 모든 숫자는 유럽 숫자로 표시됩니다.

**대체 규칙 정의**

실제 애플리케이션에서, 언어를 프로그래밍 방식으로 설정해야 합니다. 예를 들어, `xml:lang` 특성을 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]시스템에서 사용 하는 것과 동일 하 게 설정 하거나 응용 프로그램 상태에 따라 언어를 변경할 수 있습니다.

응용 프로그램의 상태에 따라 변경 하려면에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]제공 하는 다른 기능을 사용 합니다.

먼저 응용 프로그램 구성 요소의 `NumberSubstitution.CultureSource="Text"`를 설정 합니다. 이 설정을 사용 하면와 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] <xref:System.Windows.Controls.TextBlock>같이 "User"를 기본값으로 사용 하는 텍스트 요소에 대 한 설정이에서 제공 되지 않습니다.

예를 들어 다음과 같은 가치를 제공해야 합니다.

```xaml
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

해당 C# 코드에서 `Language` 속성을로 `"ar-SA"`설정 합니다 (예:).

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

`Language` 속성을 현재 사용자의 UI 언어로 설정 해야 하는 경우 다음 코드를 사용 합니다.

```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

<xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>런타임에 현재 스레드에서 사용 하는 현재 문화권을 나타냅니다.

최종 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 예제는 다음 예제와 비슷해야 합니다.

[!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]

최종 C# 예제는 다음과 유사 합니다.

[!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]

다음 그림은 두 프로그래밍 언어에 대해 창이 표시 되는 모양을 보여 줍니다. 아랍어 숫자를 표시 합니다.

![아랍어 숫자를 표시 하는 그래픽](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)

**대체 속성 사용**

에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 숫자 대체가 작동 하는 방식은 텍스트 요소와 해당 <xref:System.Windows.FlowDirection>의 언어에 따라 달라 집니다. <xref:System.Windows.FlowDirection> 가 왼쪽에서 오른쪽 이면 유럽 숫자가 렌더링 됩니다. 그러나 아랍어 텍스트가 앞에 있거나 언어가 "ar"로 설정 되어 있고 <xref:System.Windows.FlowDirection> 가 인 <xref:System.Windows.FlowDirection.RightToLeft>경우 아라비아 숫자가 렌더링 됩니다.

그러나 경우에 따라 모든 사용자에 대해 유럽 숫자 같이 단일하게 적용할 수 있습니다. <xref:System.Windows.Documents.Table> 특정<xref:System.Windows.Style>를 사용 하는 셀의 경우 아라비아 숫자가 사용 됩니다. 이 작업을 수행 하는 한 가지 쉬운 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 방법은 속성을 사용 하는 것입니다.

다음 예제에서 첫 번째 <xref:System.Windows.Controls.TextBlock> 에는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 속성이 설정 되어 있지 않으므로 알고리즘은 예상 대로 아랍어 숫자를 표시 합니다. 그러나 두 번째 <xref:System.Windows.Controls.TextBlock>는 아랍어 숫자에 대 한 기본 대체를 재정의 하는 유럽으로 설정 되 고, 유럽 숫자가 표시 됩니다.

[!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
