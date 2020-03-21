---
title: 서식 있는 텍스트 그리기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186556"
---
# <a name="drawing-formatted-text"></a>서식 있는 텍스트 그리기
이 항목에서는 개체의 기능에 대한 <xref:System.Windows.Media.FormattedText> 개요를 제공합니다. 이 개체는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 애플리케이션에서 텍스트를 그리기 위한 하위 수준의 컨트롤을 제공합니다.  

## <a name="technology-overview"></a>기술 개요  
 개체를 <xref:System.Windows.Media.FormattedText> 사용하면 텍스트의 각 문자를 개별적으로 서식을 지정할 수 있는 여러 줄 텍스트를 그릴 수 있습니다. 다음 예에서는 여러 서식이 적용된 텍스트를 보여줍니다.  
  
 ![FormattedText 개체를 사용하여 표시한 텍스트](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> Win32 API에서 마이그레이션하는 개발자의 경우 [Win32 마이그레이션](#win32_migration) 섹션의 테이블에는 Win32 DrawText 플래그와 에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]해당하는 대략적인 플래그가 나열되어 있습니다.  
  
### <a name="reasons-for-using-formatted-text"></a>서식 있는 텍스트를 사용하는 이유  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 화면에 텍스트를 그리는 데 사용하는 여러 컨트롤이 포함되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다. 일반적으로 <xref:System.Windows.Controls.TextBlock> 요소는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 간단한 문장과 같이 제한된 텍스트 지원이 필요한 경우에 사용해야 합니다. <xref:System.Windows.Controls.Label>최소한의 텍스트 지원이 필요한 경우에 사용할 수 있습니다. 자세한 내용은 [WPF의 문서](documents-in-wpf.md)를 참조하세요.  
  
 개체는 <xref:System.Windows.Media.FormattedText> 텍스트 컨트롤보다 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 더 큰 텍스트 서식 지정 기능을 제공하며 텍스트를 장식 요소로 사용하려는 경우에 유용할 수 있습니다. 자세한 내용은 다음에 있는 [서식 있는 텍스트를 기하 도형으로 변환](#converting_formatted_text) 섹션을 참조하세요.  
  
 또한 <xref:System.Windows.Media.FormattedText> 개체는 텍스트 지향 <xref:System.Windows.Media.DrawingVisual>-파생 개체를 만드는 데 유용합니다. <xref:System.Windows.Media.DrawingVisual> 도형, 이미지 또는 텍스트를 렌더링 하는 데 사용 되는 경량 그리기 클래스. 자세한 내용은 [DrawingVisuals 샘플을 사용하는 적중 횟수 테스트](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)를 참조하세요.  
  
## <a name="using-the-formattedtext-object"></a>FormattedText 개체 사용  
 서식이 지정된 텍스트를 만들려면 생성자호출을 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 사용하여 개체를 <xref:System.Windows.Media.FormattedText> 만듭니다. 첫 서식 있는 텍스트 문자열을 만든 다음 다양한 서식 지정 스타일을 적용할 수 있습니다.  
  
 속성을 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 사용하여 텍스트를 특정 너비로 제한합니다. 지정된 너비를 초과하지 않도록 텍스트가 자동으로 래핑됩니다. 속성을 <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> 사용하여 텍스트를 특정 높이로 제한합니다. 지정된 높이를 초과하는 텍스트는 줄임표 “...”로 표시됩니다.  
  
 ![단어 줄 바꿈 및 타원으로 표시되는 텍스트입니다.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 하나 이상의 문자에 여러 서식 지정 스타일을 적용할 수 있습니다. 예를 들어 텍스트에서 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 처음 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 다섯 문자의 서식을 변경하는 메서드와 메서드를 모두 호출할 수 있습니다.  
  
 다음 코드 예제에서 <xref:System.Windows.Media.FormattedText> 개체를 만들고 텍스트에 여러 서식 스타일을 적용합니다.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>글꼴 크기 측정 단위  
 응용 프로그램의 다른 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 개체와 <xref:System.Windows.Media.FormattedText> 마찬가지로 개체는 장치 독립적인 픽셀을 측정 단위로 사용합니다. 그러나 대부분의 Win32 응용 프로그램은 측정 단위로 포인트를 사용합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 점 단위로 표시 텍스트를 사용하려면 장치 독립 단위(단위당 1/96인치)를 점으로 변환해야 합니다. 다음 코드 예에서는 이 변환을 수행하는 방법을 보여줍니다.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>서식 있는 텍스트를 기하 도형으로 변환  
 서식이 지정된 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환하여 시각적으로 흥미로운 다른 유형의 텍스트를 만들 수 있습니다. 예를 들어 텍스트 문자열의 윤곽선을 기반으로 <xref:System.Windows.Media.Geometry> 개체를 만들 수 있습니다.  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 다음 예에서는 변환된 텍스트의 스트로크, 채우기 및 강조 표시를 수정하여 시각적으로 흥미로운 시각 효과를 만드는 여러 방법에 대해 설명합니다.  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![선및 강조 표시에 이미지 브러시가 적용된 텍스트](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 텍스트가 <xref:System.Windows.Media.Geometry> 개체로 변환되면 더 이상 문자 컬렉션이 아니므로 텍스트 문자열의 문자를 수정할 수 없습니다. 그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다. 스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다. 자세한 내용은 [윤곽선이 있는 텍스트 만들기](how-to-create-outlined-text.md)를 참조하세요.  
  
 서식이 지정된 텍스트를 <xref:System.Windows.Media.PathGeometry> 개체로 변환하고 텍스트를 강조 표시하기 위해 개체를 사용할 수도 있습니다. 예를 들어 애니메이션이 서식이 <xref:System.Windows.Media.PathGeometry> 지정된 텍스트의 윤곽선을 따르도록 오브젝트에 애니메이션을 적용할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.PathGeometry> 개체로 변환된 서식이 지정된 텍스트를 보여 주며 있습니다. 애니메이션된 타원이 렌더링된 텍스트의 스트로크 경로를 따라 움직입니다.  
  
 ![텍스트의 PathGeometry를 따르는 구](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
텍스트의 PathGeometry를 따르는 구  
  
 자세한 내용은 [방법: 텍스트의 PathGeometry 애니메이션 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))를 참조하세요.  
  
 서식이 지정된 텍스트가 객체로 변환되면 다른 흥미로운 <xref:System.Windows.Media.PathGeometry> 용도를 만들 수 있습니다. 예를 들어 내부에 표시되도록 비디오를 클리핑할 수 있습니다.  
  
 ![텍스트의 PathGeometry에 표시되는 비디오](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Win32 마이그레이션  
 그리기 텍스트의 <xref:System.Windows.Media.FormattedText> 기능은 Win32 DrawText 함수의 피처와 유사합니다. Win32 API에서 마이그레이션하는 개발자의 경우 다음 표에는 Win32 DrawText 플래그와 에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]해당하는 대략적인 플래그가 나열되어 있습니다.  
  
|DrawText 플래그|WPF 동급|메모|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|속성을 <xref:System.Windows.Media.FormattedText.Height%2A> 사용하여 적절한 Win32 DrawText 'y' 위치를 계산합니다.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|<xref:System.Windows.Media.FormattedText.Height%2A> 및 <xref:System.Windows.Media.FormattedText.Width%2A> 속성과 속성을 사용하여 출력 사각형을 계산합니다.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|<xref:System.Windows.Media.FormattedText.TextAlignment%2A> 값을 로 설정한 속성을 <xref:System.Windows.TextAlignment.Center>사용합니다.|  
|DT_EDITCONTROL|None|필요하지 않습니다. 공간 너비와 마지막 줄 렌더링은 프레임워크 편집 컨트롤에서와 동일합니다.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|값을 <xref:System.Windows.Media.FormattedText.Trimming%2A> <xref:System.Windows.TextTrimming.CharacterEllipsis>사용하여 속성을 사용합니다.<br /><br /> DT_WORD_ELIPSIS <xref:System.Windows.TextTrimming.WordEllipsis> 끝 타원이 있는 Win32 DT_END_ELLIPSIS 얻는 데 사용합니다.이 경우 문자 타원은 한 줄에 맞지 않는 단어에서만 발생합니다.|  
|DT_EXPAND_TABS|None|필요하지 않습니다. 약 8개의 언어 독립적 문자인 4ems마다 중지되도록 탭이 자동으로 확장됩니다.|  
|DT_EXTERNALLEADING|None|필요하지 않습니다. 외부 줄 간격은 줄 간격에 항상 포함됩니다. 속성을 <xref:System.Windows.Media.FormattedText.LineHeight%2A> 사용하여 사용자 정의 줄 간격을 만듭니다.|  
|DT_HIDEPREFIX|None|지원되지 않습니다. 개체를 생성하기 전에 문자열에서 '&'을 제거합니다. <xref:System.Windows.Media.FormattedText>|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|기본 텍스트 맞춤입니다. <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 값을 로 설정한 속성을 <xref:System.Windows.TextAlignment.Left>사용합니다. (WPF만 해당)|  
|DT_MODIFYSTRING|None|지원되지 않습니다.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|클리핑은 자동으로 수행되지 않습니다. 텍스트를 잘라내려면 <xref:System.Windows.Media.Visual.VisualClip%2A> 속성을 사용합니다.|  
|DT_NOFULLWIDTHCHARBREAK|None|지원되지 않습니다.|  
|DT_NOPREFIX|None|필요하지 않습니다. 문자열의 ‘&’ 문자는 항상 일반 문자로 처리됩니다.|  
|DT_PATHELLIPSIS|None|값을 <xref:System.Windows.Media.FormattedText.Trimming%2A> <xref:System.Windows.TextTrimming.WordEllipsis>사용하여 속성을 사용합니다.|  
|DT_PREFIX|None|지원되지 않습니다. 액셀러레이터 키 또는 링크와 같은 텍스트에 밑줄을 사용하려면 메서드를 <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> 사용합니다.|  
|DT_PREFIXONLY|None|지원되지 않습니다.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|<xref:System.Windows.Media.FormattedText.TextAlignment%2A> 값을 로 설정한 속성을 <xref:System.Windows.TextAlignment.Right>사용합니다. (WPF만 해당)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|<xref:System.Windows.Media.FormattedText.FlowDirection%2A> 속성을 <xref:System.Windows.FlowDirection.RightToLeft>로 설정합니다.|  
|DT_SINGLELINE|None|필요하지 않습니다. <xref:System.Windows.Media.FormattedText><xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 속성이 설정되었거나 텍스트에 캐리지 반환/줄 바운드(CR/LF)가 포함되어 있는 경우를 제외하면 개체는 단일 줄 컨트롤로 사용됩니다.|  
|DT_TABSTOP|None|사용자 정의 탭 중지 위치는 지원하지 않습니다.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|필요하지 않습니다. 기본값은 위쪽 양쪽 맞춤입니다. 다른 수직 위치 지정 값은 <xref:System.Windows.Media.FormattedText.Height%2A> 속성을 사용하여 적절한 Win32 DrawText 'y' 위치를 계산하여 정의할 수 있습니다.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|속성을 <xref:System.Windows.Media.FormattedText.Height%2A> 사용하여 적절한 Win32 DrawText 'y' 위치를 계산합니다.|  
|DT_WORDBREAK|None|필요하지 않습니다. 단어 나누기는 <xref:System.Windows.Media.FormattedText> 개체에서 자동으로 수행됩니다. 이 기능을 사용하지 않도록 설정할 수 없습니다.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|값을 <xref:System.Windows.Media.FormattedText.Trimming%2A> <xref:System.Windows.TextTrimming.WordEllipsis>사용하여 속성을 사용합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Media.FormattedText>
- [WPF의 문서](documents-in-wpf.md)
- [WPF의 입력 체계](typography-in-wpf.md)
- [윤곽선이 있는 텍스트 만들기](how-to-create-outlined-text.md)
- [방법: 텍스트의 PathGeometry 애니메이션 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
