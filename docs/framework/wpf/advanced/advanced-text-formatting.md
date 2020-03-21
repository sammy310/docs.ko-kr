---
title: 고급 텍스트 서식 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185936"
---
# <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정
WPF(Windows 프레젠테이션 파운데이션)는 응용 프로그램에 텍스트를 포함하기 위한 강력한 API 집합을 제공합니다. 와 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 같은 <xref:System.Windows.Controls.TextBlock>레이아웃 및 API는 텍스트 프레젠테이션에 가장 일반적이고 일반적인 사용 요소를 제공합니다. 그리기 API(예: <xref:System.Windows.Media.GlyphRunDrawing> <xref:System.Windows.Media.FormattedText>및)는 도면에 서식이 지정된 텍스트를 포함하는 수단을 제공합니다. 가장 진보된 수준에서 WPF는 텍스트 저장소 관리, 텍스트 실행 서식 관리 및 포함된 개체 관리와 같은 텍스트 프레젠테이션의 모든 측면을 제어하는 확장 가능한 텍스트 서식 지정 엔진을 제공합니다.  
  
 이 항목에서는 WPF 텍스트 서식에 대해 소개합니다. 클라이언트 구현 및 WPF 텍스트 서식 지정 엔진의 사용에 중점을 둡니다.  
  
> [!NOTE]
> 이 문서내의 모든 코드 예제는 [고급 텍스트 서식 지정 샘플에서](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting)찾을 수 있습니다.  

<a name="prereq"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 텍스트 프레젠테이션에 사용되는 상위 수준의 API에 익숙하다고 가정합니다. 대부분의 사용자 시나리오에서는 이 항목에서 설명하는 고급 텍스트 서식 API가 필요하지 않습니다. 다른 텍스트 API에 대한 소개는 [WPF의 문서를](documents-in-wpf.md)참조하십시오.  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정  
 WPF의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 텍스트 레이아웃 및 컨트롤은 응용 프로그램에 서식이 지정된 텍스트를 쉽게 포함할 수 있는 서식 속성을 제공합니다. 이러한 컨트롤은 텍스트의 표현을 처리하는 다양한 속성을 표시하며 서체, 크기 및 색을 포함합니다. 일반적인 상황에서 이러한 컨트롤은 애플리케이션에서 대부분의 텍스트 표현을 처리할 수 있습니다. 그러나 일부 고급 시나리오는 텍스트 표현 뿐만 아니라 텍스트 스토리지 컨트롤이 필요합니다. WPF는 이 목적을 위해 확장 가능한 텍스트 서식 지정 엔진을 제공합니다.  
  
 WPF에 있는 고급 텍스트 서식 지정 기능은 텍스트 서식 지정 엔진, 텍스트 저장소, 텍스트 실행 및 서식 속성으로 구성됩니다. 텍스트 서식 지정 <xref:System.Windows.Media.TextFormatting.TextFormatter>엔진은 프레젠테이션에 사용할 텍스트 줄을 만듭니다. 이는 줄 서식 지정 프로세스를 시작하고 텍스트 formatter의 를 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>호출하여 달성됩니다. 텍스트 formatter는 저장소의 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드를 호출하여 텍스트 저장소에서 실행되는 텍스트를 검색합니다. 그런 <xref:System.Windows.Media.TextFormatting.TextRun> 다음 객체는 <xref:System.Windows.Media.TextFormatting.TextLine> 텍스트 포터에 의해 객체로 형성되고 검사 또는 표시를 위해 응용 프로그램에 제공됩니다.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>텍스트 포맷터 사용  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>은 WPF 텍스트 서식 지정 엔진이며 텍스트 줄서식 지정 및 끊기 서비스를 제공합니다. 텍스트 포맷터는 다양한 텍스트 문자 서식과 단락 스타일을 처리할 수 있으며 국제 텍스트 레이아웃에 대한 지원을 포함합니다.  
  
 기존 텍스트 API와 <xref:System.Windows.Media.TextFormatting.TextFormatter> 달리 콜백 메서드 집합을 통해 텍스트 레이아웃 클라이언트와 상호 작용합니다. 구현에서 이러한 메서드를 제공 하기 위해 클라이언트 필요는 <xref:System.Windows.Media.TextFormatting.TextSource> 클래스입니다. 다음 다이어그램은 클라이언트 응용 프로그램과 <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![텍스트 레이아웃 클라이언트 및 TextFormatter의 다이어그램](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 텍스트 formatter는 <xref:System.Windows.Media.TextFormatting.TextSource>의 구현인 텍스트 저장소에서 서식이 지정된 텍스트 줄을 검색하는 데 사용됩니다. 이 방법은 먼저 메서드를 사용하여 텍스트 포물질의 <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> 인스턴스를 만들어 수행됩니다. 이 메서드는 텍스트 포맷터의 인스턴스를 생성하고 최대 선 높이 및 너비 값을 설정합니다. 텍스트 포물질의 인스턴스가 만들어지자마자 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 메서드를 호출하여 선 만들기 프로세스가 시작됩니다. <xref:System.Windows.Media.TextFormatting.TextFormatter>텍스트 원본을 호출하여 줄을 형성하는 텍스트 실행에 대한 텍스트 및 서식 매개 변수를 검색합니다.  
  
 다음 예제에서는 텍스트 저장소의 서식 지정 프로세스가 표시됩니다. 개체는 <xref:System.Windows.Media.TextFormatting.TextFormatter> 텍스트 저장소에서 텍스트 줄을 검색한 다음 에 그리기 위해 <xref:System.Windows.Media.DrawingContext>텍스트 줄을 서식을 지정하는 데 사용됩니다.  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>클라이언트 텍스트 저장소 구현  
 텍스트 서식 지정 엔진을 확장하는 경우 텍스트 저장소의 모든 측면을 구현하고 관리해야 합니다. 간단한 작업이 아닙니다. 텍스트 저장소는 텍스트 실행 속성, 단락 속성, 포함된 개체 및 이와 비슷한 콘텐츠를 추적합니다. 또한 텍스트 formatter가 객체를 만드는 <xref:System.Windows.Media.TextFormatting.TextRun> <xref:System.Windows.Media.TextFormatting.TextLine> 데 사용하는 개별 개체와 함께 텍스트 포터(formatter)를 제공합니다.  
  
 텍스트 저장소의 가상화를 처리하려면 텍스트 저장소를 에서 <xref:System.Windows.Media.TextFormatting.TextSource>파생해야 합니다. <xref:System.Windows.Media.TextFormatting.TextSource>텍스트 포matter가 텍스트 저장소에서 텍스트 실행을 검색하는 데 사용하는 방법을 정의합니다. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>는 텍스트 포맷터에서 줄 서식에 사용되는 텍스트 실행을 검색하는 데 사용되는 방법입니다. 다음 조건 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 중 하나가 발생할 때까지 텍스트 formatter에 의해 반복적으로 호출됩니다.  
  
- A <xref:System.Windows.Media.TextFormatting.TextEndOfLine> 또는 하위 클래스가 반환됩니다.  
  
- 누적된 텍스트 실행 너비는 텍스트 formatter를 만들거나 텍스트 formatter 메서드에 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 대한 호출을 만드는 호출에 지정된 최대 줄 너비를 초과합니다.  
  
- "CF", "LF" 또는 "CRLF"와 같은 유니코드 줄 바호 시퀀스가 반환됩니다.  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>텍스트 실행 제공  
 텍스트 서식 지정 프로세스의 핵심은 텍스트 포맷터와 텍스트 저장소 간의 상호 작용입니다. 구현은 <xref:System.Windows.Media.TextFormatting.TextSource> 텍스트 포맷터와 <xref:System.Windows.Media.TextFormatting.TextRun> 텍스트 실행의 서식을 지정할 속성이 제공됩니다. 이 상호 작용은 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드에 의해 처리되며, 이 메서드는 텍스트 formatter에 의해 호출됩니다.  
  
 다음 표에서는 미리 정의된 <xref:System.Windows.Media.TextFormatting.TextRun> 일부 개체를 보여 주며 있습니다.  
  
|TextRun 유형|사용|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|문자 모양의 표현을 텍스트 포맷터로 다시 전달하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|측정, 적중 테스트 및 그리기가 텍스트 내 이미지나 단추에서와 같이 전체적으로 수행되는 컨텐츠를 제공하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|선의 끝을 표시하는 데 사용되는 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|단락의 끝을 표시하는 데 사용되는 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|이전 <xref:System.Windows.Media.TextFormatting.TextModifier> 실행의 영향을 받는 범위를 종료하는 등 세그먼트의 끝을 표시하는 데 사용되는 특수 텍스트 실행입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|숨겨진 문자 범위를 표시하는 데 사용된 특수 텍스트 실행.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|해당 범위에서 텍스트 실행의 속성을 수정하는 데 사용된 특수 텍스트 실행. 범위는 다음 일치하는 <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> 텍스트 실행 또는 다음 <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>으로 확장됩니다.|  
  
 미리 정의된 <xref:System.Windows.Media.TextFormatting.TextRun> 모든 개체는 하위 클래스로 분류할 수 있습니다. 이렇게 하면 텍스트 소스가 사용자 지정 데이터를 포함하는 텍스트 포맷터와 텍스트 실행을 제공할 수 있습니다.  
  
 다음 예제에서는 메서드를 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 보여 줍니다. 이 텍스트 <xref:System.Windows.Media.TextFormatting.TextRun> 저장소는 처리를 위해 텍스트를 포터에 반환합니다.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> 이 예제에서 텍스트 저장소는 모든 텍스트에 동일한 텍스트 속성을 제공합니다. 고급 텍스트 저장소는 자신의 범위 관리를 구현하여 개별 문자가 다른 속성을 가질 수 있도록 해야 합니다.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>서식 속성 지정  
 <xref:System.Windows.Media.TextFormatting.TextRun>개체는 텍스트 저장소에서 제공하는 속성을 사용하여 서식이 지정됩니다. 이러한 속성은 두 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 가지 <xref:System.Windows.Media.TextFormatting.TextRunProperties>유형과 . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties><xref:System.Windows.TextAlignment> 와 <xref:System.Windows.FlowDirection>같은 단락 포함 속성을 처리합니다. <xref:System.Windows.Media.TextFormatting.TextRunProperties>는 전경 브러시 및 <xref:System.Windows.Media.Typeface>글꼴 크기와 같이 단락 내에서 실행되는 각 텍스트마다 다를 수 있는 속성입니다. 사용자 지정 단락 및 사용자 지정 텍스트 run 속성 형식을 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties> 구현 하려면 응용 프로그램에서 파생 된 클래스를 만들어야 합니다.  
  
## <a name="see-also"></a>참고 항목

- [WPF의 입력 체계](typography-in-wpf.md)
- [WPF의 문서](documents-in-wpf.md)
