---
title: GlyphRun 개체 및 Glyphs 요소 소개
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], Glyphs element
- Glyphs elements [WPF]
- GlyphRun object [WPF]
- text [WPF], glyphs
- glyphs [WPF]
- typography [WPF], GlyphRun object
ms.assetid: 746ca769-a331-4435-9b95-f72a883b67c1
ms.openlocfilehash: 32e8ab7104b8ea2f985395065868ed154ca1e378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181960"
---
# <a name="introduction-to-the-glyphrun-object-and-glyphs-element"></a>GlyphRun 개체 및 Glyphs 요소 소개
이 항목에서는 <xref:System.Windows.Media.GlyphRun> 개체와 <xref:System.Windows.Documents.Glyphs> 요소를 설명합니다.  

<a name="text_glyphrunovw_intro"></a>
## <a name="introduction-to-glyphrun"></a>GlyphRun 소개  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]서식 을 지정한 후 텍스트를 가로채고 <xref:System.Windows.Documents.Glyphs> 유지하려는 고객을 위해 직접 액세스할 수 있는 문자 수준 태그를 비롯한 고급 텍스트 지원을 제공합니다. 이러한 기능을 통해 다음과 같은 각 시나리오의 다양한 텍스트 렌더링 요구 사항을 충족시킬 수 있습니다.  
  
1. 고정된 형식 문서의 화면 표시  
  
2. 인쇄 시나리오  
  
    - 디바이스 프린터 언어로서의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]  
  
    - 마이크로 소프트 XPS 문서 작성기.  
  
    - 이전 프린터 드라이버, Win32 응용 프로그램에서 고정 된 형식으로 출력합니다.  
  
    - 인쇄 스풀 형식  
  
3. 이전 버전의 Windows 및 기타 컴퓨팅 장치에 대한 클라이언트를 포함하여 고정 형식의 문서 표현입니다.  
  
> [!NOTE]
> <xref:System.Windows.Documents.Glyphs><xref:System.Windows.Media.GlyphRun> 고정 형식의 문서 프레젠테이션 및 인쇄 시나리오를 위해 설계되었습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]와 같은 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Label> 일반적인 레이아웃 및 시나리오에 대한 몇 가지 요소를 <xref:System.Windows.Controls.TextBlock>제공합니다. 레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 대한 자세한 내용은 [WPF의 타이포그래피를](typography-in-wpf.md)참조하십시오.  
  
<a name="text_glyphrunovw_glyphrunobject"></a>
## <a name="the-glyphrun-object"></a>GlyphRun 개체  
 <xref:System.Windows.Media.GlyphRun> 개체는 단일 표면에서 단일 크기 및 단일 렌더링 스타일을 사용 하 여 단일 글꼴에서 문자 모양의 시퀀스를 나타냅니다.  
  
 <xref:System.Windows.Media.GlyphRun>에는 문자 문양 <xref:System.Windows.Documents.Glyphs.Indices%2A> 및 개별 문자 위치와 같은 글꼴 세부 정보가 모두 포함됩니다. 또한 실행이 생성된 원래 유니코드 코드 포인트, 문자 간 버퍼 오프셋 매핑 정보, 문자별 및 글리프별 플래그가 포함됩니다.  
  
 <xref:System.Windows.Media.GlyphRun>해당 상위 수준이 <xref:System.Windows.FrameworkElement>있습니다. <xref:System.Windows.Documents.Glyphs> <xref:System.Windows.Documents.Glyphs>요소 트리와 마크업에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 출력을 나타내는 <xref:System.Windows.Media.GlyphRun> 데 사용할 수 있습니다.  
  
<a name="text_glyphrunovw_glyphselement"></a>
## <a name="the-glyphs-element"></a>문자 모양 요소  
 요소는 <xref:System.Windows.Documents.Glyphs> 에서의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]출력을 <xref:System.Windows.Media.GlyphRun> 나타냅니다. 다음 태그 구문은 <xref:System.Windows.Documents.Glyphs> 요소를 설명하는 데 사용됩니다.  
  
 [!code-xaml[GlyphsOvwSample1#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 다음 속성 정의는 샘플 태그의 처음 네 특성에 해당합니다.  
  
|속성|Description|  
|--------------|-----------------|  
|<xref:System.Windows.Documents.Glyphs.FontUri%2A>|리소스 식별자를 지정합니다: 파일 이름, 웹 균일 한 리소스 식별자 (URI) 또는 응용 프로그램 .exe 또는 컨테이너에서 리소스 참조.|  
|<xref:System.Windows.Documents.Glyphs.FontRenderingEmSize%2A>|글꼴 크기를 그리기 화면 단위로 지정합니다(기본값은 .96인치).|  
|<xref:System.Windows.Documents.Glyphs.StyleSimulations%2A>|굵게 및 기울임꼴 스타일에 대한 플래그를 지정합니다.|  
|<xref:System.Windows.Documents.Glyphs.BidiLevel%2A>|양방향 레이아웃 수준을 지정합니다. 짝수 및 0 값은 왼쪽에서 오른쪽 레이아웃을 나타내며, 홀수 값은 오른쪽에서 왼쪽 레이아웃을 나타냅니다.|  
  
<a name="text_glyphrunovw_indicesproperty"></a>
### <a name="indices-property"></a>Indices 속성  
 속성은 <xref:System.Windows.Documents.Glyphs.Indices%2A> 글리프 사양의 문자열입니다. 문자 모양의 시퀀스가 단일 클러스터를 구성하는 경우 클러스터 첫 번째 문자 모양의 사양 앞에 문자 모양의 개수와 클러스터를 구성하는 코드 포인트 수에 대한 사양이 있습니다. 속성은 <xref:System.Windows.Documents.Glyphs.Indices%2A> 다음 속성을 한 문자열로 수집합니다.  
  
- 문자 모양 인덱스  
  
- 문자 모양의 사전 너비  
  
- 문자 모양 첨부 벡터 조합  
  
- 코드 포인트에서 문자 모양으로 클러스터 매핑  
  
- 문자 모양 플래그  
  
 각 문자 모양 사양에는 다음 형식이 있습니다.  
  
 `[GlyphIndex][,[Advance][,[uOffset][,[vOffset][,[Flags]]]]]`  
  
<a name="text_glyphrunovw_glyphmetrics"></a>
## <a name="glyph-metrics"></a>문자 모양 메트릭  
 각 글리프는 다른 <xref:System.Windows.Documents.Glyphs>것과 정렬하는 방법을 지정하는 메트릭을 정의합니다. 다음 그래픽에서는 서로 다른 두 문자 모양 문자의 다양한 입력 체계의 품질을 정의합니다.  
  
 ![문자 모양 단위의 다이어그래프](./media/glyph-example.png "glyph_example")  
  
<a name="text_glyphrunovw_glyphsmarkup"></a>
## <a name="glyphs-markup"></a>문자 모양 태그  
 다음 코드 예제에서는 에서 <xref:System.Windows.Documents.Glyphs> 요소의 다양한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]속성을 사용하는 방법을 보여 주며 있습니다.  
  
 [!code-xaml[GlyphsOvwSamp2#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>참고 항목

- [WPF의 입력 체계](typography-in-wpf.md)
- [WPF의 문서](documents-in-wpf.md)
- [텍스트](optimizing-performance-text.md)
