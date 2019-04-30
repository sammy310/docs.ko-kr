---
title: WPF의 양방향 기능 개요
ms.date: 03/30/2017
helpviewer_keywords:
- Span elements [WPF]
- bidirectional features [WPF]
ms.assetid: fd850e25-7dba-408c-b521-8873e51dc968
ms.openlocfilehash: 575598f48b3cfdf636be78a9de6e0c9a7fd9c208
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032021"
---
# <a name="bidirectional-features-in-wpf-overview"></a>WPF의 양방향 기능 개요
다른 개발 플랫폼과 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 혼합된 왼쪽에서 오른쪽을 오른쪽으로 동일한 문서에 데이터를 유지 하는 예를 들어, 양방향 콘텐츠의 신속한 개발을 지 원하는 많은 기능이 있습니다. 동시에, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 아랍어 및 히브리어 사용자와 같은 양방향 기능이 필요한 사용자를 위한 뛰어난 경험을 만듭니다.  
  
 다음 섹션에서는 최상의 양방향 콘텐츠 표시를 수행하는 방법을 보여주는 예제와 함께 다양한 양방향 기능을 설명합니다. 대부분의 샘플 사용 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]개념을 쉽게 적용할 수 있지만, C# 또는 Microsoft Visual Basic 코드입니다.  

<a name="FlowDirection"></a>   
## <a name="flowdirection"></a>FlowDirection  
 콘텐츠 흐름 방향을 정의 하는 기본 속성을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다. 이 속성은 두 열거형 값 중 하나로 설정할 수 있습니다 <xref:System.Windows.FlowDirection.LeftToRight> 또는 <xref:System.Windows.FlowDirection.RightToLeft>합니다. 속성은 모든 사용 가능한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 상속 되는 요소 <xref:System.Windows.FrameworkElement>합니다.  
  
 다음 예제에서는 설정 흐름의 방향을 <xref:System.Windows.Controls.TextBox> 요소입니다.  
  
 **왼쪽에서 오른쪽 흐름 방향**  
  
 [!code-xaml[LTRRTL#LTR](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#ltr)]  
  
 **오른쪽에서 왼쪽 흐름 방향**  
  
 [!code-xaml[LTRRTL#RTL](~/samples/snippets/csharp/VS_Snippets_Wpf/LTRRTL/CS/Pane1.xaml#rtl)]  
  
 다음 그림에서는 이전 코드 렌더링 방법을 보여 줍니다.  
    
 ![여러 흐름 방향의 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/left-right-right-left.png)  
  
 내의 요소를 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 트리는 상속을 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 해당 컨테이너에서. 다음 예제에서는 <xref:System.Windows.Controls.TextBlock> 내부를 <xref:System.Windows.Controls.Grid>에 있는 <xref:System.Windows.Window>입니다. 설정 합니다 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 에 대 한는 <xref:System.Windows.Window> 설정에 대 한 의미를 <xref:System.Windows.Controls.Grid> 및 <xref:System.Windows.Controls.TextBlock> 도 합니다.  
  
 다음 예제에서는 설정 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다.  
  
 [!code-xaml[FlowDirection#FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirection/CS/Window1.xaml#flowdirection)]  
  
 최상위 <xref:System.Windows.Window> 에 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection>이므로 그 안에 포함 된 모든 요소는 또한 동일한 상속 <xref:System.Windows.FrameworkElement.FlowDirection%2A>합니다. 지정 된 재정의 하는 요소에 대 한 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 두 번째 같은 명시적 방향 변경을 추가 해야 합니다 <xref:System.Windows.Controls.TextBlock> 를 변경 하는 이전 예제의 <xref:System.Windows.FlowDirection.LeftToRight>합니다. 없는 경우 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 정의 된 기본 <xref:System.Windows.FlowDirection.LeftToRight> 적용 됩니다.  
  
 다음 그림에는 이전 예제의 출력이 표시 됩니다.

 ![명시적 흐름 방향 변경 내용을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/explicit-direction-change.png)  

<a name="FlowDocument"></a>   
## <a name="flowdocument"></a>FlowDocument  
 와 같은 다양 한 개발 플랫폼 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)], [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Java 양방향 콘텐츠 개발에 대 한 특별 한 지원을 제공 합니다. 같은 태그 언어 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 콘텐츠 작성자 예를 들어 필요한 모든 방향에서 텍스트를 표시 하는 데 필요한 태그를 제공 합니다 [!INCLUDE[TLA#tla_html](../../../../includes/tlasharptla-html-md.md)] 4.0 태그, 값으로 "rtl" 또는 "ltr"를 사용 하는 "dir"입니다. 이 태그는 비슷합니다는 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성인 하지만 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성 레이아웃 텍스트 콘텐츠를 좀 더 고급 방식으로 작동 하 고 텍스트 이외의 콘텐츠에 사용할 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], a <xref:System.Windows.Documents.FlowDocument> 는 다양 한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 텍스트, 테이블, 이미지 및 기타 요소의 조합을 호스트할 수 있는 요소입니다. 다음 섹션의 샘플은 이 요소를 사용합니다.  
  
 텍스트를 추가 <xref:System.Windows.Documents.FlowDocument> 하는 여러 방법이에서 수행할 수 있습니다. 이렇게 하는 간단한 방법을 통해 되는 <xref:System.Windows.Documents.Paragraph> 텍스트와 같은 그룹 콘텐츠를 사용 하는 블록 수준 요소는 합니다. 샘플을 사용 하는 인라인 수준 요소에 텍스트를 추가할 <xref:System.Windows.Documents.Span> 고 <xref:System.Windows.Documents.Run>입니다. <xref:System.Windows.Documents.Span> 다른 인라인 요소를 그룹화 하는 데 사용 되는 인라인 수준의 유동 콘텐츠 요소 인지 하는 동안는 <xref:System.Windows.Documents.Run> 는 인라인 수준의 유동 콘텐츠 요소는 서식 있는 텍스트 실행을 포함 하는 데는 합니다. A <xref:System.Windows.Documents.Span> 여러 개 포함할 수 있습니다 <xref:System.Windows.Documents.Run> 요소입니다.  
  
 다양 한 네트워크 이름을; 공유에 있는 문서를 포함 하는 첫 번째 문서 예제 예를 들어 `\\server1\folder\file.ext`합니다. 이 네트워크 링크가 아랍어나 영어 문서에 있는지 여부에 따라 같은 방식으로 항상 표시될 수 있습니다. 다음 그래픽 Span 요소를 사용 하 고는 아랍어 링크를 보여 줍니다 <xref:System.Windows.FlowDirection.RightToLeft> 문서:

 ![Span 요소를 사용 하 여 보여 주는 그래픽입니다. ](./media/bidirectional-features-in-wpf-overview/flow-direction-span-element.png "FlowDocument")  
  
 텍스트 이므로 <xref:System.Windows.FlowDirection.RightToLeft>모든 특수 같은 문자는 "\\", 오른쪽에서 왼쪽된 순서 텍스트를 구분 합니다. 결과는 올바른 순서 대로 표시 되지 않으며 링크, 따라서 문제를 해결 하기 위해 텍스트를 포함 해야 별도 유지 하기 위해 <xref:System.Windows.Documents.Run> 흐르는 <xref:System.Windows.FlowDirection.LeftToRight>합니다. 별도 분리 하는 대신 <xref:System.Windows.Documents.Run> 각 언어에 대 한 문제를 해결 하기 위해 더 나은 방법은 더 큰 아랍어를 덜 사용 되는 영어 텍스트를 포함할 수 것 <xref:System.Windows.Documents.Span>입니다.  
  
 다음 그림에서는 Span 요소에 포함 된 실행 요소를 사용 하 여이 보여 줍니다.

 ![Span 요소에 포함 된 실행 요소를 보여 주는 그래픽.](./media/bidirectional-features-in-wpf-overview/embedded-span-element.png)  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 <xref:System.Windows.Documents.Run> 고 <xref:System.Windows.Documents.Span> 문서의 요소입니다.  
  
 [!code-xaml[RunSpan#RunSpan](~/samples/snippets/csharp/VS_Snippets_Wpf/RunSpan/CS/Window1.xaml#runspan)]  
  
<a name="SpanElements"></a>   
## <a name="span-elements"></a>Span 요소  
 <xref:System.Windows.Documents.Span> 요소 여러 흐름 방향의 텍스트 사이의 경계 구분 기호로 작동 합니다.  도 <xref:System.Windows.Documents.Span> 동일한 흐름 방향 사용 하 여 요소 즉, 다른 양방향 범위 할 것으로 간주 됩니다 합니다 <xref:System.Windows.Documents.Span> 컨테이너의 요소를 정렬 하는 <xref:System.Windows.FlowDirection>, 내 콘텐츠만 <xref:System.Windows.Documents.Span> 요소 뒤의 <xref:System.Windows.FlowDirection> 의 <xref:System.Windows.Documents.Span>합니다.  
  
 다음 그래픽에서는 일부의 흐름 방향을 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
    
 ![여러 흐름 방향의 텍스트 블록을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/flow-direction-text-blocks.png)  
  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Documents.Run> 이전 그림에 표시 된 결과 생성 하는 요소입니다.  
  
 [!code-xaml[Span#Span](~/samples/snippets/csharp/VS_Snippets_Wpf/Span/CS/Window1.xaml#span)]  
  
 에 <xref:System.Windows.Controls.TextBlock> 샘플에서 요소를 <xref:System.Windows.Documents.Span> 요소에 따라 배치 됩니다는 <xref:System.Windows.FlowDirection> 부모 내의 각 텍스트의 <xref:System.Windows.Documents.Span> 자체에 따라 요소 흐름 <xref:System.Windows.FlowDirection>합니다. 라틴어와 아랍어 또는 다른 언어에 적용됩니다.  
  
### <a name="adding-xmllang"></a>Xml:lang 추가  
 다음 그래픽에서는 같은 숫자 및 산술 연산자를 사용 하는 또 다른 예로 `"200.0+21.4=221.4"`합니다. 멤버만 <xref:System.Windows.FlowDirection> 설정 됩니다.  
    
 ![FlowDirection만을 사용 하 여 숫자를 표시 하는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/numbers-flow-right-left.png)  
  
 이 응용 프로그램의 사용자는 출력에 만족 하지 않을 <xref:System.Windows.FlowDirection> 아랍어 숫자를 숫자 표시 되지 않으므로 정확 합니다.  
  
 XAML 요소를 포함할 수는 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 특성 (`xml:lang`) 각 요소의 언어를 정의 하는 합니다. XAML도 지원 합니다.는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 언어 원칙 가능해 집니다 `xml:lang` 트리의 부모 요소에 적용 되는 값이 자식 요소에 의해 사용 됩니다. 이전 예제에서는 언어에 대 한 정의 되지 않아 합니다 <xref:System.Windows.Documents.Run> 요소 또는 해당 최상위 수준 요소를 기본 `xml:lang` 사용 된는 `en-US` XAML에 대 한 합니다. 내부 숫자 셰이핑 알고리즘 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 이 경우, 영어 – 해당 언어의 숫자를 선택 합니다. 아랍어 숫자를 올바르게 렌더링 `xml:lang` 설정 해야 합니다.  
  
 다음 그림은 사용 하 여 예제 `xml:lang` 추가 합니다.  
    
 ![오른쪽에서 왼쪽으로 진행 되는 아랍어 숫자 보여 주는 그래픽.](./media/bidirectional-features-in-wpf-overview/arabic-numbers-flow-right-left.png)  
  
 다음 예제에서는 `xml:lang` 응용 프로그램입니다.  
  
 [!code-xaml[LangAttribute#LangAttribute](~/samples/snippets/csharp/VS_Snippets_Wpf/LangAttribute/CS/Window1.xaml#langattribute)]  
  
 여러 언어는 다른 주의 `xml:lang` 예를 들어, 대상된 지역에 따라 값 `"ar-SA"` 고 `"ar-EG"` 아랍어의 두 변형을 나타냅니다. 앞의 예제에서는 모두를 정의 해야 함을 설명 합니다 `xml:lang` 고 <xref:System.Windows.FlowDirection> 값입니다.  
  
<a name="FlowDirectionNontext"></a>   
## <a name="flowdirection-with-non-text-elements"></a>텍스트가 아닌 요소가 있는 FlowDirection  
 <xref:System.Windows.FlowDirection> 뿐만 아니라 텍스트 흐름 방식 텍스트 요소 뿐만 아니라 거의 모든 다른 흐름 방향을 정의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다. 다음 그래픽은 <xref:System.Windows.Controls.ToolBar> 가로 사용 하는 <xref:System.Windows.Media.LinearGradientBrush> left 사용 하 여 배경을 오른쪽 그라데이션을 그릴 합니다.  

 ![왼쪽에서 오른쪽 그라데이션 사용 하 여 도구 모음을 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/toolbar-left-right-gradient.png)  
  
 설정한 후는 <xref:System.Windows.FlowDirection> 를 <xref:System.Windows.FlowDirection.RightToLeft>뿐만 아니라, 합니다 <xref:System.Windows.Controls.ToolBar> 단추는 오른쪽에서 왼쪽으로도 있지만 정렬 <xref:System.Windows.Media.LinearGradientBrush> 해당 오프셋을 오른쪽에서 왼쪽으로 이동 합니다.  
  
 다음 그림의 재정렬을 <xref:System.Windows.Media.LinearGradientBrush>입니다.  
    
 ![오른쪽에서 왼쪽된 그라데이션 사용 하 여 도구 모음을 보여 주는 그래픽.](./media/bidirectional-features-in-wpf-overview/toolbar-right-left-gradient.png)  
  
 다음 예제에서는 그립니다를 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.Controls.ToolBar>합니다. (그릴이 왼쪽에서 오른쪽으로 제거 합니다 <xref:System.Windows.FlowDirection> 특성을 <xref:System.Windows.Controls.ToolBar>합니다.  
  
 [!code-xaml[Gradient#Gradient](~/samples/snippets/csharp/VS_Snippets_Wpf/Gradient/CS/Window1.xaml#gradient)]  
  
<a name="FlowDirectionExceptions"></a>   
### <a name="flowdirection-exceptions"></a>FlowDirection 예외  
 몇 가지 경우가 있는 <xref:System.Windows.FlowDirection> 예상 대로 작동 하지 않습니다. 이 섹션에서는 이러한 예외 중 두 가지를 설명합니다.  
  
 **Image**  
  
 <xref:System.Windows.Controls.Image> 이미지를 표시 하는 컨트롤을 나타냅니다. [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 사용 될 수 있습니다를 <xref:System.Windows.Controls.Image.Source%2A> 정의 하는 속성을 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 의 <xref:System.Windows.Controls.Image> 표시할.  
  
 달리 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소는 <xref:System.Windows.Controls.Image> 상속 하지 않습니다는 <xref:System.Windows.FlowDirection> 컨테이너에서. 그러나 경우 합니다 <xref:System.Windows.FlowDirection> 명시적으로 설정 됩니다 <xref:System.Windows.FlowDirection.RightToLeft>, <xref:System.Windows.Controls.Image> 좌우로 표시 됩니다. 양방향 콘텐츠의 개발자에게 편리한 기능으로 구현됩니다. 경우에 따라 이미지를 가로로 대칭 이동하면 원하는 효과가 나타나기 때문입니다.  
  
 다음 그림을 대칭 이동 된 <xref:System.Windows.Controls.Image>합니다.  
    
 ![대칭 이동 된 이미지를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/flipped-image-example.png)  
  
 다음 예제에서는 합니다 <xref:System.Windows.Controls.Image> 상속 하지 못했습니다 합니다 <xref:System.Windows.FlowDirection> 에서 <xref:System.Windows.Controls.StackPanel> 포함 된. **참고** 라는 파일이 있어야 **ms_logo.jpg** C:\에서 이 예제를 실행 하는 드라이브입니다.  
  
 [!code-xaml[Image#Image](~/samples/snippets/csharp/VS_Snippets_Wpf/Image/CS/Window1.xaml#image)]  
  
 **참고** 다운로드 파일에 포함 되는 **ms_logo.jpg** 파일입니다. 코드는 .jpg 파일이 프로젝트 내에 있지 않지만 C:\ 드라이브 어딘가에 있다고 가정합니다. 프로젝트 파일에서 C:\ 드라이브로 .jpg를 복사하거나 프로젝트 내부에서 파일을 찾도록 코드를 변경해야 합니다. 이 변경 작업을 수행 하 `Source="file://c:/ms_logo.jpg"` 에 `Source="ms_logo.jpg"`입니다.  
  
 **경로**  
  
 이외에 <xref:System.Windows.Controls.Image>, 다른 흥미로운 요소는 <xref:System.Windows.Shapes.Path>합니다. 경로는 일련의 연결된 선 및 곡선을 그릴 수 있는 개체입니다. 유사한 방식으로 동작 하는 <xref:System.Windows.Controls.Image> 에 대 한 해당 <xref:System.Windows.FlowDirection>예를 들어 해당 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> 의 가로 미러입니다 해당 <xref:System.Windows.FlowDirection.LeftToRight> 하나입니다. 그러나 달리를 <xref:System.Windows.Controls.Image>, <xref:System.Windows.Shapes.Path> 상속 해당 <xref:System.Windows.FlowDirection> 컨테이너 하나에서 않아도 명시적으로 지정 합니다.  
  
 다음 예제에서는 3개의 선을 사용하여 간단한 화살표를 그립니다. 첫 번째 화살표 상속 합니다 <xref:System.Windows.FlowDirection.RightToLeft> 흐름 방향을 <xref:System.Windows.Controls.StackPanel> 해당 시작점과 끝점은 오른쪽 루트에서 측정 됩니다 있도록 합니다. 명시적인 있는 두 번째 화살표 <xref:System.Windows.FlowDirection.RightToLeft> <xref:System.Windows.FlowDirection> 오른쪽 에서도 시작 합니다. 그러나 세 번째 화살표는 왼쪽에 시작 루트가 있습니다. 그리기 참조 하는 방법은 <xref:System.Windows.Media.LineGeometry> 고 <xref:System.Windows.Media.GeometryGroup>입니다.  
  
 [!code-xaml[Paths#Paths](~/samples/snippets/csharp/VS_Snippets_Wpf/Paths/CS/Window1.xaml#paths)]  
  
 사용 하 여 그린 화살표를 사용 하 여 이전 예의 출력을 표시 하는 다음 그림은 `Path` 요소:

 ![경로 요소를 사용 하 여 그린 화살표 보여 주는 그래픽.](./media/bidirectional-features-in-wpf-overview/arrows-drawn-path-element.png)  
  
 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Shapes.Path> 은 두 가지 예는 방식의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하 여 <xref:System.Windows.FlowDirection>입니다. 레이아웃 옆 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨테이너 내 특정 방향으로 요소 <xref:System.Windows.FlowDirection> 와 같은 요소를 사용 하 여 사용할 수 있습니다 <xref:System.Windows.Controls.InkPresenter> , 표면에 잉크를 렌더링 하 <xref:System.Windows.Media.LinearGradientBrush>, <xref:System.Windows.Media.RadialGradientBrush>합니다. 왼쪽에서 오른쪽 동작을 모방 하는 콘텐츠에 대 한 오른쪽에서 왼쪽된 동작이 필요할 때마다 또는 반대로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 해당 기능을 제공 합니다.  
  
<a name="NumberSubstitution"></a>   
## <a name="number-substitution"></a>숫자 대체  
 지금까지 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 예에서는 숫자는 저장에 대 한 서로 다른 로캘에서 통합 된이 숫자의 내부 저장소를 유지 하면서 동일한 숫자에 대 한 다양 한 문화권 도형 표시를 허용 하 여 숫자 대체를 지원 했습니다 해당 잘 알려진 16 진수 값, 0x40, 0x41로 되지만 선택한 언어에 따라 표시 합니다.  
  
 이 응용 프로그램에서 다른 언어로 변환할 필요 없이 숫자 값을 처리할 수 있었습니다, 예를 들어 사용자 열 수는 [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] 지역화 된 아랍어에서 스프레드시트 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 아랍어로 된 숫자를 참조 하며 엽니다 유럽 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 동일한 숫자의 유럽 표시를 표시 합니다. 보통 동일한 문서에서 숫자와 같이 표시되기 때문에 쉼표 구분 기호와 백분율 기호와 같은 다른 기호에도 필요합니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 동일한 기능을 계속 유지하며 대체가 사용되는 시기와 방법을 사용자가 더 많이 제어할 수 있도록 이 기능에 대한 지원을 추가합니다. 이 기능은 모든 언어를 대상으로 하지만, 애플리케이션을 실행하는 다양한 문화권 때문에 특정 언어에 대한 숫자 모양을 애플리케이션 개발자가 지정하기 어려운 양방향 콘텐츠에서 더욱 유용합니다.  
  
 작동 하는 방법을 숫자 대체를 제어 하는 핵심 속성 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 되는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 종속성 속성입니다. <xref:System.Windows.Media.NumberSubstitution> 클래스 텍스트의 숫자가 표시 하는 하는 방법을 지정 합니다. 동작을 정의하는 세 가지 공용 속성이 있습니다. 다음은 각 속성에 대한 요약입니다.  
  
 **CultureSource:**  
  
 이 속성은 숫자에 대한 문화권을 결정하는 방법을 지정합니다. 3 가지 걸리는 <xref:System.Windows.Media.NumberCultureSource> 열거형 값입니다.  
  
- 재정의: 숫자 문화권이 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성입니다.  
  
- 텍스트: 숫자 문화권이 텍스트 실행의 문화권입니다. 이 태그에서 것 `xml:lang`, 또는 해당 별칭인 `Language` 속성 (<xref:System.Windows.FrameworkElement.Language%2A> 또는 <xref:System.Windows.FrameworkContentElement.Language%2A>). 기본 클래스에서 파생 되는 것 또한 <xref:System.Windows.FrameworkContentElement>합니다. 이러한 클래스를 포함 <xref:System.Windows.Documents.Paragraph?displayProperty=nameWithType>하십시오 <xref:System.Windows.Documents.Table?displayProperty=nameWithType>, <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType> 등.  
  
- 사용자: 숫자 문화권이 현재 스레드의 문화권입니다. 이 속성의 모든 서브 클래스에 대 한 기본값은 <xref:System.Windows.FrameworkElement> 와 같은 <xref:System.Windows.Controls.Page>하십시오 <xref:System.Windows.Window> 및 <xref:System.Windows.Controls.TextBlock>합니다.  
  
 **CultureOverride**:  
  
 <xref:System.Windows.Media.NumberSubstitution.CultureOverride%2A> 속성은 경우에 사용 합니다 <xref:System.Windows.Media.NumberSubstitution.CultureSource%2A> 속성이 <xref:System.Windows.Media.NumberCultureSource.Override> 그렇지 않은 경우 무시 됩니다. 숫자 문화권을 지정합니다. 값 `null`, 기본값은 EN-US로 해석 됩니다.  
  
 **대체**:  
  
 이 속성에는 수행할 숫자 대체의 형식을 지정합니다. 다음 중 하나를 사용 <xref:System.Windows.Media.NumberSubstitutionMethod> 열거형 값입니다.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.AsCulture>: 대체 메서드가 숫자 문화권에 따라 결정 됩니다 <xref:System.Globalization.NumberFormatInfo.DigitSubstitution%2A?displayProperty=nameWithType> 속성입니다. 이 값이 기본값입니다.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Context>: 숫자 문화권은 아랍어 또는 페르시아어 문화권 인 경우 숫자가 컨텍스트에 따라 지정 합니다.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.European>: 숫자는 항상 유럽 숫자로 렌더링 됩니다.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>: 문화권에 의해 지정 된 대로 숫자 문화권에 대 한 국가별 숫자를 사용 하 여 숫자가 렌더링 되도록 <xref:System.Globalization.CultureInfo.NumberFormat%2A>합니다.  
  
- <xref:System.Windows.Media.NumberSubstitutionMethod.Traditional>: 숫자는 숫자 문화권에 대 한 전통 숫자를 사용 하 여 렌더링 됩니다. 대부분의 문화권에서 이것이 동일 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational>합니다. 그러나 <xref:System.Windows.Media.NumberSubstitutionMethod.NativeNational> 모든 아랍어 문화권에 대 한 아랍어 숫자가 결과이 값이 있는 반면 일부 아랍어 문화권에 대해 라틴 숫자가 결과입니다.  
  
 이 값은 양방향 콘텐츠 개발자에게 무슨 의미입니까? 대부분의 경우에서 개발자 정의에 필요할 <xref:System.Windows.FlowDirection> 및 각 텍스트 언어 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 예를 들어 요소 `Language="ar-SA"` 및 <xref:System.Windows.Media.NumberSubstitution> 논리에 따라 올바른 숫자를 표시 하므로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 다음 예제에서 아랍어와 영어 숫자를 사용 하는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아랍어 버전의에서 실행 하는 응용 프로그램 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)]합니다.  
  
 [!code-xaml[Numbers#Numbers](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers/CS/Window1.xaml#numbers)]  
  
 다음 그래픽에서는 표시 되는 아랍어와 영어 숫자를 사용 하 여 아랍어 버전의 Windows에서 실행 하는 경우 이전 샘플의 출력을 보여 줍니다.

 ![아랍어와 영어 숫자를 보여 주는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/arabic-english-numbers.png)  
  
 <xref:System.Windows.FlowDirection> 이어서 중요 한이 경우에 설정 합니다 <xref:System.Windows.FlowDirection> 에 <xref:System.Windows.FlowDirection.LeftToRight> 대신는 유럽 숫자가 생성 합니다. 다음 섹션에서는 문서 전체에서 숫자를 단일하게 표시하는 방법을 설명합니다. 이 예제에서 아랍어 창을 실행하지 않는 경우 모든 숫자는 유럽 숫자로 표시됩니다.  
  
 **대체 규칙 정의**  
  
 실제 애플리케이션에서, 언어를 프로그래밍 방식으로 설정해야 합니다. 설정 하려면 예를 들어를 `xml:lang` 특성을 시스템에서 사용 하는 것과 동일 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 또는 응용 프로그램 상태에 따라 언어를 변경할 수 있습니다.  
  
 확인 하려는 경우 응용 프로그램의 상태에 따라 변경에서 제공 하는 기타 기능 사용 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.  
  
 먼저, 응용 프로그램 구성 요소의 설정 `NumberSubstitution.CultureSource="Text"`합니다. 이 설정을 사용 하면 설정에서 제공 되지 않은 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 와 같은 기본적으로 "사용자"가 있는 텍스트 요소에 대 한 <xref:System.Windows.Controls.TextBlock>합니다.  
  
예를 들어:  

```xaml  
<TextBlock
   Name="text1" NumberSubstitution.CultureSource="Text">
   1234+5679=6913
</TextBlock>
```

해당 C# 코드를 설정 합니다 `Language` 속성에 예를 들어 `"ar-SA"`합니다.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage("ar-SA");
```

설정 하는 경우는 `Language` 속성에 현재 사용자의 UI 언어는 다음 코드를 사용 합니다.  
  
```csharp
text1.Language = System.Windows.Markup.XmlLanguage.GetLanguage(System.Globalization.CultureInfo.CurrentUICulture.IetfLanguageTag);
```

 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> 런타임 시 현재 스레드에서 사용 하는 현재 문화권을 나타냅니다.  
  
 최종 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 예제는 다음 예제와 유사 해야 합니다.  
  
 [!code-xaml[Numbers2#Numbers2](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers2/CS/Window1.xaml#numbers2)]  
  
 최종 C# 예제는 다음과 유사 해야 합니다.  
  
 [!code-csharp[NumbersCSharp#NumbersCSharp](~/samples/snippets/csharp/VS_Snippets_Wpf/NumbersCSharp/CSharp/Window1.xaml.cs#numberscsharp)]  
  
 다음 그래픽 아랍어 숫자를 표시 하거나 프로그래밍 언어에 대 한 창의 모양을 보여 줍니다.
     
 ![아랍어 숫자를 표시 하는 그래픽입니다.](./media/bidirectional-features-in-wpf-overview/displays-arabic-numbers.png)  
  
 **대체 속성 사용**  
  
 작동 하는 방식으로 숫자 대체가 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 요소의 언어에 따라 달라 집니다 고 <xref:System.Windows.FlowDirection>입니다. 경우는 <xref:System.Windows.FlowDirection> 는 왼쪽에서 오른쪽, 유럽 숫자가 렌더링 됩니다. 그러나 아랍어 텍스트가 앞에 또는 언어가 "ar"로 설정 하는 경우와 <xref:System.Windows.FlowDirection> 는 <xref:System.Windows.FlowDirection.RightToLeft>, 아랍어 숫자가 대신 렌더링 됩니다.  
  
 그러나 경우에 따라 모든 사용자에 대해 유럽 숫자 같이 단일하게 적용할 수 있습니다. 또는에서 아랍어 숫자가 <xref:System.Windows.Documents.Table> 특정 셀 <xref:System.Windows.Style>합니다. 쉬운 방법 중 하나 수행을 사용 하는 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 속성입니다.  
  
 다음 예에서 첫 번째 <xref:System.Windows.Controls.TextBlock> 되지 않은 <xref:System.Windows.Media.NumberSubstitution.Substitution%2A> 알고리즘 예상 대로 아랍어 숫자를 표시 하도록 속성을 설정 합니다. 그러나 두 번째에서 <xref:System.Windows.Controls.TextBlock>대체가 아랍어 숫자에 대 한 기본값을 재정의 유럽으로 설정 되 고 유럽 숫자가 표시 됩니다.  
  
 [!code-xaml[Numbers3#Numbers3](~/samples/snippets/csharp/VS_Snippets_Wpf/Numbers3/CS/Window1.xaml#numbers3)]
