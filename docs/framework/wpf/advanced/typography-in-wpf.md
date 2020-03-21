---
title: 입력 체계
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 501a4221c99d405484a2fb908641d27d1f38f266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187343"
---
# <a name="typography-in-wpf"></a>WPF의 입력 체계
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 주요 입력 체계 기능을 소개합니다. 이러한 기능에는 텍스트 렌더링의 품질 및 성능 향상, OpenType 타이포그래피 지원, 향상된 국제 텍스트, 향상된 글꼴 지원 및 새로운 텍스트 응용 프로그램 프로그래밍 인터페이스(API)가 포함됩니다.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>
## <a name="improved-quality-and-performance-of-text"></a>텍스트의 향상된 품질 및 성능  
 텍스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 의 선명도와 읽기 를 향상 시키는 Microsoft ClearType를 사용 하 여 텍스트 렌더링 됩니다. ClearType은 노트북 화면, 포켓 PC 화면 및 평면 패널 모니터와 같은 기존 LCD(액정 디스플레이)에서 텍스트의 가독성을 향상시키는 Microsoft에서 개발한 소프트웨어 기술입니다. ClearType은 픽셀의 소수 부분에 문자를 정렬하여 텍스트를 실제 모양에 더 충실하게 표시할 수 있는 하위 픽셀 렌더링을 사용합니다. 해상도를 더 세밀하게 지원할수록 텍스트의 미세한 부분까지 더 선명하게 표시되므로 오랫동안 더 쉽게 읽을 수 있습니다. ClearType의 또 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다른 개선 사항은 텍스트 문자에서 얕은 곡선의 위쪽과 아래쪽을 부드럽게 하는 y 방향 안티 앨리어싱입니다. ClearType 기능에 대한 자세한 내용은 [ClearType 개요를](cleartype-overview.md)참조하십시오.  
  
 ![ClearType y 방향 앤티 앨리어싱을 사용한 텍스트](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
ClearType y 방향 앤티 앨리어싱으로 표시된 텍스트  
  
 컴퓨터가 최소 수준의 하드웨어 요구를 충족하는 경우 전체 텍스트 렌더링 파이프라인은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 하드웨어 가속일 수 있습니다. 하드웨어를 사용하여 수행할 수 없는 렌더링은 소프트웨어 렌더링으로 대체됩니다. 하드웨어 가속은 개별 문자 표시 저장, 글리프 실행에 글리프 합성, 효과 적용, ClearType 혼합 알고리즘을 최종 표시된 출력에 적용하는 등 텍스트 렌더링 파이프라인의 모든 단계에 영향을 줍니다. 하드웨어 가속에 대한 자세한 내용은 [그래픽 렌더링 계층](graphics-rendering-tiers.md)을 참조하세요.  
  
 ![텍스트 렌더링 파이프라인의 다이어그램](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 또한 문자나 문자 모양으로 애니메이션된 텍스트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용되는 그래픽 하드웨어 기능을 최대한 활용합니다. 그 결과 부드러운 텍스트 애니메이션이 만들어집니다.  
  
<a name="Rich_Typography"></a>
## <a name="rich-typography"></a>풍부한 입력 체계  
 OpenType 글꼴 형식은 TrueType® 글꼴 형식의 확장입니다. OpenType 글꼴 형식은 마이크로소프트와 어도비에 의해 공동으로 개발 되었으며, 고급 타이포그래피 기능의 풍부한 구색을 제공 합니다. 개체는 <xref:System.Windows.Documents.Typography> 스타일 대체 및 스와시와 같은 OpenType 글꼴의 많은 고급 기능을 노출합니다. Windows SDK는 페리클및 페스카데로 글꼴과 같은 풍부한 기능으로 설계된 샘플 OpenType 글꼴 집합을 제공합니다. 자세한 내용은 [샘플 OpenType 글꼴 팩을](sample-opentype-font-pack.md)참조하십시오.  
  
 Pericles OpenType 글꼴 스타일 대체 문자 모양의 표준 집합을 제공 하는 추가 문자 모양이 포함 되어 있습니다. 다음 텍스트는 스타일 대체 문자 모양을 표시합니다.  
  
 ![OpenType 스타일 대체 문자 모양을 사용하는 텍스트](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "OpenType 스타일 대체 문자 모양을 사용하는 텍스트")  
  
 선단 장식은 종종 붓글씨와 관련된 정교한 장식을 사용하는 장식용 문자 모양입니다. 다음 텍스트는 Pescadero 글꼴의 표준 및 선단 장식 문자 모양을 표시합니다.  
  
 ![OpenType 표준 및 선단 장식 문자 모양을 사용하는 텍스트](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "OpenType 표준 및 선단 장식 문자 모양을 사용하는 텍스트")  
  
 OpenType 기능에 대한 자세한 내용은 [OpenType 글꼴 기능을](opentype-font-features.md)참조하십시오.  
  
<a name="Enhanced_International_Text_Support"></a>
## <a name="enhanced-international-text-support"></a>향상된 국가별 텍스트 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음과 같은 기능을 제공하여 향상된 국가별 텍스트를 지원합니다.  
  
- 모든 쓰기 시스템에서 적응형 단위를 사용하는 자동 줄 간격.  
  
- 광범위한 국가별 텍스트 지원. 자세한 내용은 [WPF의 세계화](globalization-for-wpf.md)를 참조하세요.  
  
- 언어 기반 줄 바꿈, 하이픈 및 양쪽 맞춤.  
  
<a name="Enhanced_Font_Support"></a>
## <a name="enhanced-font-support"></a>향상된 글꼴 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음과 같은 기능을 제공하여 향상된 글꼴을 지원합니다.  
  
- 모든 텍스트에 대한 유니코드. 글꼴 동작 및 선택에 문자 집합이나 코드 페이지가 더 이상 필요하지 않습니다.  
  
- 시스템 로캘과 같이 전역 설정에 독립적인 글꼴 동작.  
  
- 을 <xref:System.Windows.FontWeight> <xref:System.Windows.FontStretch>정의하는 <xref:System.Windows.FontStyle> 및 형식을 <xref:System.Windows.Media.FontFamily>구분합니다. 이는 기울임꼴과 굵게의 부울 조합이 글꼴 패밀리를 정의하는 데 사용되는 Win32 프로그래밍보다 더 큰 유연성을 제공합니다.  
  
- 글꼴 이름과 독립적으로 처리되는 쓰기 방향(가로 및 세로).  
  
- 복합 글꼴 기술을 사용하여 휴대용 XML 파일에서 글꼴 연결 및 글꼴 대체. 합성 글꼴은 모든 범위의 다국어 글꼴 생성을 허용합니다. 또한 합성 글꼴은 없는 문자 모양을 표시하지 않는 메커니즘을 제공합니다. 자세한 내용은 수업내 발언을 <xref:System.Windows.Media.FontFamily> 참조한다.  
  
- 단일 언어 글꼴 그룹을 사용하여 합성 글꼴에서 국가별 글꼴 작성. 따라서 여러 언어에 대한 글꼴을 개발할 때 리소스 비용이 절감됩니다.  
  
- 합성 글꼴을 문서에 포함하여 문서에 이식성 제공. 자세한 내용은 수업내 발언을 <xref:System.Windows.Media.FontFamily> 참조한다.  
  
<a name="New_Text_APIs"></a>
## <a name="new-text-application-programming-interfaces-apis"></a>새 텍스트 API(응용 프로그래밍 인터페이스)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]개발자가 응용 프로그램에 텍스트를 포함할 때 사용할 수 있는 몇 가지 텍스트 API를 제공합니다. 이러한 API는 다음 세 가지 범주로 그룹화됩니다.  
  
- **레이아웃 및 사용자 인터페이스**. 그래픽 사용자 인터페이스(GUI)에 대한 일반적인 텍스트 컨트롤입니다.  
  
- **경량 텍스트 그리기**. 개체에 직접 텍스트를 그릴 수 있습니다.  
  
- **고급 텍스트 서식**. 사용자 지정 텍스트 엔진을 구현할 수 있습니다.  
  
### <a name="layout-and-user-interface"></a>레이아웃 및 사용자 인터페이스  
 가장 높은 수준의 기능에서 텍스트 API는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] <xref:System.Windows.Controls.Label>및 <xref:System.Windows.Controls.TextBlock>및 <xref:System.Windows.Controls.TextBox>의 공통 컨트롤을 제공합니다. 이러한 컨트롤은 애플리케이션 내에서 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 제공하며, 텍스트를 제공하고 텍스트와 상호 작용하는 쉬운 방법을 제공합니다. 고급 또는 <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.PasswordBox> 특수 텍스트 처리를 가능하게 하는 컨트롤. 및 와 <xref:System.Windows.Documents.TextRange>같은 <xref:System.Windows.Documents.TextSelection>클래스는 <xref:System.Windows.Documents.TextPointer> 유용한 텍스트 조작을 활성화합니다. 이러한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤은 텍스트를 <xref:System.Windows.Controls.Control.FontFamily%2A> <xref:System.Windows.Controls.Control.FontSize%2A>렌더링하는 <xref:System.Windows.Controls.Control.FontStyle%2A>데 사용되는 글꼴을 제어할 수 있는 " 및 및 의 속성을 제공합니다.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>비트맵 효과, 변환 및 텍스트 효과 사용  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 비트맵 효과, 변환 및 텍스트 효과 같은 기능을 사용하여 시각적으로 흥미로운 텍스트를 만들 수 있습니다. 다음 예제에서는 일반적인 형식의 그림자 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![0.25&#61; 부드러움이 있는 텍스트 그림자](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
 다음 예제에서는 그림자 효과와 노이즈가 적용된 텍스트를 보여 줍니다.  
  
 ![노이즈가 있는 텍스트 그림자](./media/typography-in-wpf/drop-shadow-noise-text.jpg)
  
 다음 예제에서는 후광 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![OuterGlowBitmapEffect를 사용한 텍스트 그림자](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![BlurBitmapEffect를 사용한 텍스트 그림자](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 다음 예에서는 텍스트의 두 번째 라인은 x축을 따라 배율을 150% 조정하여 보여주고, 텍스트의 세 번째 라인은 y축을 따라 배율을 150% 조정하여 보여줍니다.  
  
 ![ScaleTransform을 사용하여 배율 조정된 텍스트](./media/typography-in-wpf/scaled-text-scaletransform.jpg)
  
 다음 예에서는 x축을 따라 기울어진 텍스트를 보여줍니다.  
  
 ![SkewTransform을 사용하여 기울인 텍스트](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 <xref:System.Windows.Media.TextEffect> 개체는 텍스트를 텍스트 문자열의 하나 이상의 문자 그룹으로 처리할 수 있는 도우미 개체입니다. 다음 예제에서는 개별 문자가 회전되는 것을 보여 줍니다. 각 문자는 1초 간격으로 개별적으로 회전합니다.  
  
 ![텍스트 효과 회전 텍스트의 스크린 샷](./media/typography-in-wpf/rotating-text-effect.jpg)
  
#### <a name="using-flow-documents"></a>유동 문서 사용  
 일반적인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤 외에도 텍스트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 요소의 레이아웃 컨트롤을 <xref:System.Windows.Documents.FlowDocument> 제공합니다. 요소는 <xref:System.Windows.Documents.FlowDocument> 요소와 함께 <xref:System.Windows.Controls.DocumentViewer> 다양한 레이아웃 요구 사항을 가진 많은 양의 텍스트에 대한 컨트롤을 제공합니다. 레이아웃 컨트롤은 다른 <xref:System.Windows.Documents.Typography> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤의 개체 및 글꼴 관련 속성을 통해 고급 타이포그래피에 대한 액세스를 제공합니다.  
  
 다음 예제에서는 검색, 탐색, 페이지 설정 및 콘텐츠 크기 조정 지원을 제공하는 <xref:System.Windows.Controls.FlowDocumentReader>에서 호스팅되는 텍스트 콘텐츠를 보여 주습니다.  
  
 ![OpenType 글꼴을 보여 주는 스크린샷입니다.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 자세한 내용은 [WPF의 문서](documents-in-wpf.md)를 참조하세요.  
  
### <a name="lightweight-text-drawing"></a>간단한 텍스트 그리기  
 개체의 메서드를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Media.DrawingContext.DrawText%2A> 사용하여 개체에 직접 텍스트를 그릴 수 있습니다. <xref:System.Windows.Media.DrawingContext> 이 메서드를 사용 하려면 <xref:System.Windows.Media.FormattedText> 개체를 만듭니다. 이 개체를 사용하면 여러 줄 텍스트를 그릴 수 있으며 이 텍스트에 있는 각 문자의 서식은 개별적으로 지정할 수 있습니다. <xref:System.Windows.Media.FormattedText> 개체의 기능에는 Windows API의 DrawText 플래그의 많은 기능이 포함되어 있습니다. 또한 <xref:System.Windows.Media.FormattedText> 개체에는 텍스트가 경계를 초과할 때 타원이 표시되는 타원 지원과 같은 기능이 포함되어 있습니다. 다음 예제에서는 두 번째와 세 번째 단어에 적용된 선형 그라데이션을 포함하여 여러 서식이 적용된 텍스트를 보여 줍니다.  
  
 ![FormattedText 개체를 사용하여 표시한 텍스트](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 서식이 지정된 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환하여 시각적으로 흥미로운 다른 유형의 텍스트를 만들 수 있습니다. 예를 들어 텍스트 문자열의 윤곽선을 기반으로 <xref:System.Windows.Media.Geometry> 개체를 만들 수 있습니다.  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 다음 예에서는 변환된 텍스트의 스트로크, 채우기 및 강조 표시를 수정하여 시각적으로 흥미로운 시각 효과를 만드는 여러 방법에 대해 설명합니다.  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![선및 강조 표시에 이미지 브러시가 적용된 텍스트](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 객체에 대한 자세한 내용은 [서식을 그리는 텍스트 그림을](drawing-formatted-text.md)참조하십시오. <xref:System.Windows.Media.FormattedText>  
  
### <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정  
 텍스트 API의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 가장 고급 수준에서 네임스페이스의 <xref:System.Windows.Media.TextFormatting.TextFormatter> 개체 및 기타 형식을 사용하여 사용자 지정 <xref:System.Windows.Media.TextFormatting> 텍스트 레이아웃을 만들 수 있습니다. 및 <xref:System.Windows.Media.TextFormatting.TextFormatter> 관련 클래스를 사용하면 문자 형식, 단락 스타일, 줄 바이탈 규칙 및 국제 텍스트에 대한 기타 레이아웃 기능에 대한 사용자 정의 정의를 지원하는 사용자 지정 텍스트 레이아웃을 구현할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 레이아웃 지원의 기본 구현을 재정의하려는 경우는 거의 없습니다. 그러나 텍스트 편집 컨트롤이나 애플리케이션을 만들려는 경우 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현이 아닌 다른 구현이 필요할 수 있습니다.  
  
 기존 텍스트 API와 <xref:System.Windows.Media.TextFormatting.TextFormatter> 달리 콜백 메서드 집합을 통해 텍스트 레이아웃 클라이언트와 상호 작용합니다. 구현에서 이러한 메서드를 제공 하기 위해 클라이언트 필요는 <xref:System.Windows.Media.TextFormatting.TextSource> 클래스입니다. 다음 다이어그램은 클라이언트 응용 프로그램과 <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![텍스트 레이아웃 클라이언트 및 TextFormatter의 다이어그램](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 사용자 지정 텍스트 레이아웃을 만드는 방법에 대한 자세한 내용은 [고급 텍스트 서식 지정](advanced-text-formatting.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [ClearType 개요](cleartype-overview.md)
- [OpenType 글꼴 기능](opentype-font-features.md)
- [서식 있는 텍스트 그리기](drawing-formatted-text.md)
- [고급 텍스트 서식 지정](advanced-text-formatting.md)
- [텍스트](optimizing-performance-text.md)
- [Microsoft 입력 체계](https://docs.microsoft.com/typography/)
