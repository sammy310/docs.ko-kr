---
title: '성능 최적화: 텍스트'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
ms.openlocfilehash: 67549e75244790973554d08de8f4dac99d28bd80
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660770"
---
# <a name="optimizing-performance-text"></a>성능 최적화: 텍스트

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다양한 기능의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컨트롤을 사용하여 텍스트 콘텐츠를 표시할 수 있습니다. 일반적으로 세 가지 계층으로 텍스트 렌더링을 나눌 수 있습니다.

1. 사용 하 여 <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun> 개체를 직접.

2. 사용 하 여 <xref:System.Windows.Media.FormattedText> 개체입니다.

3. 와 같은 고급 컨트롤을 사용 하 여 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다.

이 항목에서는 텍스트 렌더링 성능 권장 사항을 제공합니다.

<a name="Glyph_Level"></a>

## <a name="rendering-text-at-the-glyph-level"></a>문자 모양 수준에서 텍스트 렌더링

[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 에 대 한 직접 액세스를 사용 하 여 문자 모양 수준 태그를 포함 한 고급 텍스트 지원을 제공 <xref:System.Windows.Documents.Glyphs> 가로채서 텍스트 서식 지정 후 유지 하려는 고객에 대 한 합니다. 이러한 기능을 통해 다음과 같은 각 시나리오의 다양한 텍스트 렌더링 요구 사항을 충족시킬 수 있습니다.

- 고정된 형식 문서의 화면 표시

- 인쇄 시나리오

  - 장치 프린터 언어로서의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

  - [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].

  - 이전 프린터 드라이버, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 애플리케이션에서 고정된 형식으로의 출력

  - 인쇄 스풀 형식

- 이전 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 및 기타 컴퓨팅 디바이스에 대한 클라이언트를 포함하는 고정된 형식 문서 표시

> [!NOTE]
> <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun> 고정 형식 문서 프레젠테이션과 인쇄 시나리오에 대 한 설계 되었습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 일반 레이아웃에 대 한 몇 가지 요소를 제공 하 고 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 와 같은 시나리오 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.TextBlock>합니다. 레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 대한 자세한 내용은 [WPF의 입력 체계](typography-in-wpf.md)를 참조하세요.

다음 예제에서는 속성을 정의 하는 방법을 보여는 <xref:System.Windows.Documents.Glyphs> 개체의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. 합니다 <xref:System.Windows.Documents.Glyphs> 개체의 출력을 나타냅니다는 <xref:System.Windows.Media.GlyphRun> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 이 예제에서는 로컬 컴퓨터의 **C:\WINDOWS\Fonts** 폴더에 Arial, Courier New 및 Times New Roman 글꼴이 설치되어 있다고 가정합니다.

[!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]

### <a name="using-drawglyphrun"></a>DrawGlyphRun 사용

사용자 지정 컨트롤을 했 고 문자 모양을 렌더링을 사용 하려는 경우는 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 메서드.

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 또한 사용자 지정 텍스트를 사용 하 여 서식 지정에 대 한 하위 수준 서비스를 제공 합니다 <xref:System.Windows.Media.FormattedText> 개체입니다. 텍스트를 렌더링 하는 가장 효율적인 방법은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하 여 문자 모양 수준에서 텍스트 콘텐츠를 생성 하는 것 <xref:System.Windows.Documents.Glyphs> 고 <xref:System.Windows.Media.GlyphRun>입니다. 그러나이 효율성의 비용은 기본 제공 기능인 사용 하기 쉬운 서식 있는 텍스트 서식이 손실의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 컨트롤과 같은 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument>합니다.

<a name="FormattedText_Object"></a>

## <a name="formattedtext-object"></a>FormattedText 개체

<xref:System.Windows.Media.FormattedText> 개체는 각 문자를 텍스트에 서식을 지정할 수 개별적으로 여러 줄 텍스트를 그릴 수 있습니다. 자세한 내용은 [서식 있는 텍스트 그리기](drawing-formatted-text.md)를 참조하세요.

서식 있는 텍스트를 만들려면 다음을 호출 합니다 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 만드는 생성자입니다는 <xref:System.Windows.Media.FormattedText> 개체입니다. 첫 서식 있는 텍스트 문자열을 만든 다음 다양한 서식 지정 스타일을 적용할 수 있습니다. 응용 프로그램에서 자체 레이아웃을 구현 하려는 경우 해당 <xref:System.Windows.Media.FormattedText> 개체가 같은 컨트롤을 사용 하 여 보다 더 나은 선택 <xref:System.Windows.Controls.TextBlock>합니다. 에 대 한 자세한 합니다 <xref:System.Windows.Media.FormattedText> 개체를 참조 하십시오 [서식 있는 텍스트 그리기](drawing-formatted-text.md) 합니다.

<xref:System.Windows.Media.FormattedText> 개체는 낮은 수준의 텍스트 서식 지정 기능을 제공 합니다. 하나 이상의 문자에 여러 서식 지정 스타일을 적용할 수 있습니다. 예를 들어, 모두 호출할 수 있습니다 합니다 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 및 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 텍스트의 처음 5 개 문자 서식을 변경 하는 방법입니다.

다음 코드 예제는 <xref:System.Windows.Media.FormattedText> 개체를 렌더링 합니다.

[!code-csharp[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
[!code-vb[formattedtextsnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]

<a name="FlowDocument_TextBlock_Label"></a>

## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock 및 Label 컨트롤

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 화면에 텍스트를 그리는 데 사용하는 여러 컨트롤이 포함되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다.

### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument가 TextBlock 또는 Label 이외의 성능에 미치는 영향

일반적으로 <xref:System.Windows.Controls.TextBlock> 제한 된 텍스트 지원이의 간략 한 문장과 같이 필요한 경우 요소를 사용 해야는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. <xref:System.Windows.Controls.Label> 최소 텍스트 지원이 필요할 때 사용할 수 있습니다. 합니다 <xref:System.Windows.Documents.FlowDocument> 요소는 콘텐츠의 풍부한 표현을 지 원하는 재배치 문서용 컨테이너 있고 따라서를 사용 하 여 보다 성능에 큰 영향을 <xref:System.Windows.Controls.TextBlock> 또는 <xref:System.Windows.Controls.Label> 컨트롤입니다.

에 대 한 자세한 <xref:System.Windows.Documents.FlowDocument>를 참조 하세요 [유동 문서 개요](flow-document-overview.md)합니다.

### <a name="avoid-using-textblock-in-flowdocument"></a>FlowDocument에서 TextBlock 사용 안 함

합니다 <xref:System.Windows.Controls.TextBlock> 요소에서 파생 됩니다 <xref:System.Windows.UIElement>합니다. <xref:System.Windows.Documents.Run> 요소에서 파생 됩니다 <xref:System.Windows.Documents.TextElement>에 보다 비용이 적게 듭니다를 <xref:System.Windows.UIElement>-파생 개체입니다. 사용 가능한 경우 <xref:System.Windows.Documents.Run> 대신 <xref:System.Windows.Controls.TextBlock> 텍스트의 콘텐츠 표시는 <xref:System.Windows.Documents.FlowDocument>합니다.

다음 태그 예제에서는 내에서 텍스트 콘텐츠를 설정 하는 두 가지는 <xref:System.Windows.Documents.FlowDocument>:

[!code-xaml[Performance#PerformanceSnippet13](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]

### <a name="avoid-using-run-to-set-text-properties"></a>텍스트 속성을 설정하여 실행 사용 방지

일반적으로 사용 하 여는 <xref:System.Windows.Documents.Run> 내에서 <xref:System.Windows.Controls.TextBlock> 은 더 높은 성능이 보다 명시적인를 사용 하지 않는 <xref:System.Windows.Documents.Run> 전혀 개체입니다. 사용 중인 경우는 <xref:System.Windows.Documents.Run> 텍스트 속성을 설정 하기 위해 해당 속성을 직접 설정 된 <xref:System.Windows.Controls.TextBlock> 대신 합니다.

다음 태그 예제에서는 예제의 경우 text 속성을 설정 하는 두 가지는 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 속성:

[!code-xaml[Performance#PerformanceSnippet12](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]

다음 표에서 1000을 표시 하는 비용을 보여 줍니다 <xref:System.Windows.Controls.TextBlock> 개체와 명시적인 없는 <xref:System.Windows.Documents.Run>합니다.

|**TextBlock 형식**|**만든 시간(ms)**|**렌더링 시간(ms)**|
|------------------------|------------------------------|----------------------------|
|Run 설정 텍스트 속성|146|540|
|TextBlock 설정 텍스트 속성|43|453|

### <a name="avoid-databinding-to-the-labelcontent-property"></a>Label.Content 속성에 데이터 바인딩 방지

있는 경우를 가정해를 <xref:System.Windows.Controls.Label> 에서 자주 업데이트 되는 개체는 <xref:System.String> 원본입니다. 경우 데이터 바인딩 합니다 <xref:System.Windows.Controls.Label> 요소의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을는 <xref:System.String> 원본 개체를 성능 저하를 발생할 수 있습니다. 될 때마다 원본 <xref:System.String> 업데이트 되 면 이전 <xref:System.String> 개체가 삭제 되 고 새 <xref:System.String> 만들어지는지-때문에 <xref:System.String> 개체를 변경할 수 없는, 수정할 수 없습니다. 이 인해 합니다 <xref:System.Windows.Controls.ContentPresenter> 의 합니다 <xref:System.Windows.Controls.Label> 이전 내용을 취소 하 고 새 표시할 새 콘텐츠를 다시 생성 하는 개체 <xref:System.String>합니다.

이 문제에 대한 해결책은 간단합니다. 경우는 <xref:System.Windows.Controls.Label> 사용자 지정으로 설정 되지 않은 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 값을 대체 합니다 <xref:System.Windows.Controls.Label> 사용 하 여를 <xref:System.Windows.Controls.TextBlock> 및 데이터 바인딩 해당 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 소스 문자열을 합니다.

|**데이터 바인딩된 속성**|**업데이트 시간(ms)**|
|-----------------------------|----------------------------|
|Label.Content|835|
|TextBlock.Text|242|

<a name="Hyperlink"></a>

## <a name="hyperlink"></a>하이퍼링크

<xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에서 하이퍼링크를 호스트할 수 있는 인라인 수준의 유동 콘텐츠 요소입니다.

### <a name="combine-hyperlinks-in-one-textblock-object"></a>하나의 TextBlock 개체에 대한 하이퍼링크 결합

여러 사용을 최적화할 수 있습니다 <xref:System.Windows.Documents.Hyperlink> 동일한 함께 그룹화 하 여 요소 <xref:System.Windows.Controls.TextBlock>합니다. 이렇게 하면 애플리케이션에서 만드는 개체의 수를 최소화할 수 있습니다. 예를 들어 다음과 같은 여러 개의 하이퍼링크를 표시할 수 있습니다.

MSN 홈 &#124; 내 MSN

다음 태그 예제에서는 여러 <xref:System.Windows.Controls.TextBlock> 하이퍼링크를 표시 하는 데 사용 되는 요소:

[!code-xaml[Performance#PerformanceSnippet9](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]

다음 태그 예제에서는 단일을 사용 하 여이 이번에는 하이퍼링크를 표시 하는 더 효율적으로 <xref:System.Windows.Controls.TextBlock>:

[!code-xaml[Performance#PerformanceSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]

### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>MouseEnter 이벤트에만 하이퍼링크에 밑줄 표시

<xref:System.Windows.TextDecoration> 개체 텍스트를 추가할 수 있는 시각적 장식 됩니다; 그러나 인스턴스화하는 데 성능 집중적 수 있습니다. 광범위 하 게 사용 한다면 <xref:System.Windows.Documents.Hyperlink> 요소와 같은 이벤트를 트리거하는 경우에 밑줄을 표시 하는 것이 좋습니다는 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다. 자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.

다음 이미지는 어떻게 MouseEnter 이벤트 트리거 밑줄이 그어진된 하이퍼링크를 보여줍니다.

![TextDecoration을 표시하는 하이퍼링크](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)

다음 태그 샘플은 <xref:System.Windows.Documents.Hyperlink> 와 밑줄 없이 정의 합니다.

[!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]

다음 표에서 1000을 표시 하는 성능 비용 <xref:System.Windows.Documents.Hyperlink> 와 밑줄이 있거나 없는 요소입니다.

|**하이퍼링크**|**만든 시간(ms)**|**렌더링 시간(ms)**|
|-------------------|------------------------------|----------------------------|
|밑줄 있음|289|1130|
|밑줄 없음|299|776|

<a name="Text_Formatting_Features"></a>

## <a name="text-formatting-features"></a>텍스트 서식 지정 기능

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 자동 하이픈 넣기 등 서식 있는 텍스트 서식 지정 서비스를 제공합니다. 이러한 서비스는 애플리케이션 성능에 영향을 줄 수 있으며 필요한 경우에만 사용해야 합니다.

### <a name="avoid-unnecessary-use-of-hyphenation"></a>불필요한 하이픈 넣기 사용 안 함

자동 하이픈 넣기가 줄의 텍스트에 대 한 하이픈 중단점을 찾아서 추가 중단 위치를 줄 수 있습니다 <xref:System.Windows.Controls.TextBlock> 고 <xref:System.Windows.Documents.FlowDocument> 개체입니다. 기본적으로 이러한 개체에서는 자동 하이픈 넣기 기능이 사용하지 않도록 설정됩니다. 개체의 IsHyphenationEnabled 속성을 `true`로 설정하여 이 기능을 사용하도록 설정할 수 있습니다. 그러나 이 기능을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] 상호 운용성이 시작되어 애플리케이션 성능에 영향을 미칠 수 있습니다. 꼭 필요한 경우가 아니면 자동 하이픈 넣기를 사용하지 않는 것이 좋습니다.

### <a name="use-figures-carefully"></a>신중하게 그림 사용

<xref:System.Windows.Documents.Figure> 요소 콘텐츠 페이지 내에서 절대적으로 배치 될 수 있는 흐름 콘텐츠의 일부를 나타냅니다. 일부 경우에는 <xref:System.Windows.Documents.Figure> 전체 페이지를 자동으로 해당 콘텐츠와 위치가 레이아웃이 이미 있는 경우 다시 포맷 하려면 발생할 수 있습니다. 가능성 하거나 그룹화 하 여 불필요 한 재포맷을 최소화할 수 있습니다 <xref:System.Windows.Documents.Figure> 고정된 페이지 크기 시나리오에서 콘텐츠 위쪽 선언 또는 서로 옆에 있는 요소입니다.

### <a name="optimal-paragraph"></a>최적 단락

최적 단락 기능은 <xref:System.Windows.Documents.FlowDocument> 개체 공백 최대한 균등 하 게 분포 되도록 단락을 배치 합니다. 기본적으로 최적 단락 기능은 사용하지 않도록 설정됩니다. 개체를 설정 하 여이 기능을 사용할 수 있습니다 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 속성을 `true`입니다. 그러나 이 기능을 사용하면 애플리케이션 성능에 영향을 미칩니다. 꼭 필요한 경우가 아니면 최적 단락 기능을 사용하지 않는 것이 좋습니다.

## <a name="see-also"></a>참고자료

- [WPF 응용 프로그램 성능 최적화](optimizing-wpf-application-performance.md)
- [애플리케이션 성능 계획](planning-for-application-performance.md)
- [하드웨어 이용](optimizing-performance-taking-advantage-of-hardware.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [2차원 그래픽 및 이미징](optimizing-performance-2d-graphics-and-imaging.md)
- [개체 동작](optimizing-performance-object-behavior.md)
- [응용 프로그램 리소스](optimizing-performance-application-resources.md)
- [데이터 바인딩](optimizing-performance-data-binding.md)
- [기타 성능 권장 사항](optimizing-performance-other-recommendations.md)
