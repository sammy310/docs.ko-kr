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
ms.openlocfilehash: a61031c36dea84449ad07175287bf834544df886
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129092"
---
# <a name="drawing-formatted-text"></a>서식 있는 텍스트 그리기
이 항목에서는의 기능 개요를 제공 합니다 <xref:System.Windows.Media.FormattedText> 개체입니다. 이 개체는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 애플리케이션에서 텍스트를 그리기 위한 하위 수준의 컨트롤을 제공합니다.  

## <a name="technology-overview"></a>기술 개요  
 <xref:System.Windows.Media.FormattedText> 개체는 각 문자를 텍스트에 서식을 지정할 수 개별적으로 여러 줄 텍스트를 그릴 수 있습니다. 다음 예에서는 여러 서식이 적용된 텍스트를 보여줍니다.  
  
 ![FormattedText 개체를 사용하여 표시한 텍스트](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
>  [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API에서 마이그레이션하는 개발자를 위해 [Win32 마이그레이션](#win32_migration) 섹션의 테이블에는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 플래그와 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 거의 동급 플래그가 나열되어 있습니다.  
  
### <a name="reasons-for-using-formatted-text"></a>서식 있는 텍스트를 사용하는 이유  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 화면에 텍스트를 그리기 위한 여러 컨트롤이 포함 되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다. 일반적으로 <xref:System.Windows.Controls.TextBlock> 제한 된 텍스트 지원이의 간략 한 문장과 같이 필요한 경우 요소를 사용 해야는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. <xref:System.Windows.Controls.Label> 최소 텍스트 지원이 필요할 때 사용할 수 있습니다. 자세한 내용은 [WPF의 문서](documents-in-wpf.md)를 참조하세요.  
  
 합니다 <xref:System.Windows.Media.FormattedText> 서식 지정 기능 보다 우수한 텍스트를 제공 하는 개체 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 텍스트 컨트롤 텍스트를 장식 요소로 사용 하려는 경우에 유용할 수 있습니다. 자세한 내용은 다음에 있는 [서식 있는 텍스트를 기하 도형으로 변환](#converting_formatted_text) 섹션을 참조하세요.  
  
 또한 합니다 <xref:System.Windows.Media.FormattedText> 개체는 텍스트 기반을 만드는 데 유용 <xref:System.Windows.Media.DrawingVisual>-파생 개체입니다. <xref:System.Windows.Media.DrawingVisual> 도형, 이미지 또는 텍스트를 렌더링 하는 데 사용 되는 경량 그리기 클래스. 자세한 내용은 [DrawingVisuals 샘플을 사용하는 적중 횟수 테스트](https://go.microsoft.com/fwlink/?LinkID=159994)를 참조하세요.  
  
## <a name="using-the-formattedtext-object"></a>FormattedText 개체 사용  
 서식 있는 텍스트를 만들려면 다음을 호출 합니다 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 만드는 생성자입니다는 <xref:System.Windows.Media.FormattedText> 개체입니다. 첫 서식 있는 텍스트 문자열을 만든 다음 다양한 서식 지정 스타일을 적용할 수 있습니다.  
  
 사용 된 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 속성 텍스트를 특정 너비로 제한 합니다. 지정된 너비를 초과하지 않도록 텍스트가 자동으로 래핑됩니다. 사용 된 <xref:System.Windows.Media.FormattedText.MaxTextHeight%2A> 속성 텍스트를 특정 높이로 제한 합니다. 지정된 높이를 초과하는 텍스트는 줄임표 “...”로 표시됩니다.  
  
 ![자동 줄 바꿈 및 줄임표 (...)를 사용 하 여 표시할 텍스트입니다.](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)    
  
 하나 이상의 문자에 여러 서식 지정 스타일을 적용할 수 있습니다. 예를 들어, 모두 호출할 수 있습니다 합니다 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 및 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 텍스트의 처음 5 개 문자 서식을 변경 하는 방법입니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 텍스트에 여러 서식 지정 스타일을 적용 합니다.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>글꼴 크기 측정 단위  
 다른 텍스트 개체와 마찬가지로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 <xref:System.Windows.Media.FormattedText> 개체 측정 단위로 장치 독립적 픽셀을 사용 합니다. 그러나 대부분의 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 애플리케이션에서는 포인트를 측정 단위로 사용합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램에서 포인트 단위의 표시 텍스트를 사용하려면 [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)]를 포인트로 변환해야 합니다. 다음 코드 예에서는 이 변환을 수행하는 방법을 보여줍니다.  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>서식 있는 텍스트를 기하 도형으로 변환  
 서식이 지정 된 텍스트를 변환할 수 있습니다 <xref:System.Windows.Media.Geometry> 개체를 다른 유형의 시각적으로 흥미로운 텍스트를 만들 수 있습니다. 예를 들어, 만들 수 있습니다는 <xref:System.Windows.Media.Geometry> 텍스트 문자열의 윤곽선을 기준으로 하는 개체입니다.  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](./media/typography-in-wpf/text-outline-linear-gradient.jpg)    
  
 다음 예에서는 변환된 텍스트의 스트로크, 채우기 및 강조 표시를 수정하여 시각적으로 흥미로운 시각 효과를 만드는 여러 방법에 대해 설명합니다.  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![스트로크를 강조 표시에 이미지 브러시가 적용 된 텍스트](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 텍스트 변환 되 면을 <xref:System.Windows.Media.Geometry> 개체를 더 이상 문자 컬렉션이-텍스트 문자열의에서 문자를 수정할 수 없습니다. 그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다. 스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다. 자세한 내용은 [윤곽선이 있는 텍스트 만들기](how-to-create-outlined-text.md)를 참조하세요.  
  
 서식이 지정 된 텍스트를 변환할 수도 있습니다는 <xref:System.Windows.Media.PathGeometry> 개체 및 개체를 사용 하 여 텍스트를 강조 표시 합니다. 예를 들어 애니메이션을 적용할 수 있습니다는 <xref:System.Windows.Media.PathGeometry> 애니메이션이 서식 있는 텍스트의 윤곽선을 따라 개체입니다.  
  
 다음 예제에서는 변환 된 서식 있는 텍스트를 <xref:System.Windows.Media.PathGeometry> 개체입니다. 애니메이션된 타원이 렌더링된 텍스트의 스트로크 경로를 따라 움직입니다.  
  
 ![텍스트의 PathGeometry를 따르는 구](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
텍스트의 PathGeometry를 따르는 구  
  
 자세한 내용은 [방법: 텍스트의 PathGeometry 애니메이션 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))합니다.  
  
 변환한 후 서식 있는 텍스트에 대 한 다른 흥미로운 사용을 만들 수 있습니다는 <xref:System.Windows.Media.PathGeometry> 개체입니다. 예를 들어 내부에 표시되도록 비디오를 클리핑할 수 있습니다.  
  
 ![텍스트의 PathGeometry에 표시되는 비디오](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Win32 마이그레이션  
 기능의 <xref:System.Windows.Media.FormattedText> 텍스트를 그리기 위한 비슷합니다의 기능에는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 함수입니다. [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API에서 마이그레이션하는 개발자를 위해 다음 테이블에는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 플래그와 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 거의 동급 플래그가 나열되어 있습니다.  
  
|DrawText 플래그|WPF 동급|노트|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|사용 된 <xref:System.Windows.Media.FormattedText.Height%2A> 속성을 적절 한 계산 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y' 위치입니다.|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|사용 된 <xref:System.Windows.Media.FormattedText.Height%2A> 및 <xref:System.Windows.Media.FormattedText.Width%2A> 출력 사각형을 계산 하는 속성입니다.|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|사용 된 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 속성에 설정 된 값을 사용 하 여 <xref:System.Windows.TextAlignment.Center>입니다.|  
|DT_EDITCONTROL|없음|필요하지 않음. 공간 너비와 마지막 줄 렌더링은 프레임워크 편집 컨트롤에서와 동일합니다.|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|사용 된 <xref:System.Windows.Media.FormattedText.Trimming%2A> 속성 값을 사용 하 여 <xref:System.Windows.TextTrimming.CharacterEllipsis>입니다.<br /><br /> 사용 하 여 <xref:System.Windows.TextTrimming.WordEllipsis> 가져오려는 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 모두를 사용 하 여 dt_end_ellipsis를 가져옵니다 종료 줄임표-이 경우 문자 줄임표에 발생 한 줄에 들어가지 않는 단어입니다.|  
|DT_EXPAND_TABS|없음|필요하지 않음. 약 8개의 언어 독립적 문자인 4ems마다 중지되도록 탭이 자동으로 확장됩니다.|  
|DT_EXTERNALLEADING|없음|필요하지 않음. 외부 줄 간격은 줄 간격에 항상 포함됩니다. 사용 하 여는 <xref:System.Windows.Media.FormattedText.LineHeight%2A> 속성을 사용자 정의 줄 간격을 만듭니다.|  
|DT_HIDEPREFIX|없음|지원되지 않습니다. 문자열에서 '&'를 생성 하기 전에 제거 된 <xref:System.Windows.Media.FormattedText> 개체입니다.|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|기본 텍스트 맞춤입니다. 사용 된 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 속성에 설정 된 값을 사용 하 여 <xref:System.Windows.TextAlignment.Left>입니다. (WPF만 해당)|  
|DT_MODIFYSTRING|없음|지원되지 않습니다.|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|클리핑은 자동으로 수행되지 않습니다. 텍스트를 클리핑하려면 하려는 경우 사용 된 <xref:System.Windows.Media.Visual.VisualClip%2A> 속성입니다.|  
|DT_NOFULLWIDTHCHARBREAK|없음|지원되지 않습니다.|  
|DT_NOPREFIX|없음|필요하지 않음. 문자열의 ‘&’ 문자는 항상 일반 문자로 처리됩니다.|  
|DT_PATHELLIPSIS|없음|사용 된 <xref:System.Windows.Media.FormattedText.Trimming%2A> 속성 값을 사용 하 여 <xref:System.Windows.TextTrimming.WordEllipsis>입니다.|  
|DT_PREFIX|없음|지원되지 않습니다. 액셀러레이터 키 또는 링크와 같은 텍스트에 밑줄을 사용 하려는 경우 사용 된 <xref:System.Windows.Media.FormattedText.SetTextDecorations%2A> 메서드.|  
|DT_PREFIXONLY|없음|지원되지 않습니다.|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|사용 된 <xref:System.Windows.Media.FormattedText.TextAlignment%2A> 속성에 설정 된 값을 사용 하 여 <xref:System.Windows.TextAlignment.Right>입니다. (WPF만 해당)|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|<xref:System.Windows.Media.FormattedText.FlowDirection%2A> 속성을 <xref:System.Windows.FlowDirection.RightToLeft>으로 설정합니다.|  
|DT_SINGLELINE|없음|필요하지 않음. <xref:System.Windows.Media.FormattedText> 하지 않는 한 개체를 단일 줄 컨트롤로 작동 중 하나는 <xref:System.Windows.Media.FormattedText.MaxTextWidth%2A> 속성을 설정 하거나 텍스트에 캐리지 리턴/줄 바꿈 (CR/LF).|  
|DT_TABSTOP|없음|사용자 정의 탭 중지 위치는 지원하지 않습니다.|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|필요하지 않음. 기본값은 위쪽 양쪽 맞춤입니다. 기타 세로 위치 지정 값을 사용 하 여 정의할 수 있습니다 합니다 <xref:System.Windows.Media.FormattedText.Height%2A> 속성을 적절 한 계산 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y' 위치입니다.|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|사용 된 <xref:System.Windows.Media.FormattedText.Height%2A> 속성을 적절 한 계산 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 'y' 위치입니다.|  
|DT_WORDBREAK|없음|필요하지 않음. 단어 분리를 사용 하 여 자동으로 이루어짐. <xref:System.Windows.Media.FormattedText> 개체입니다. 이 기능을 사용하지 않도록 설정할 수 없습니다.|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|사용 된 <xref:System.Windows.Media.FormattedText.Trimming%2A> 속성 값을 사용 하 여 <xref:System.Windows.TextTrimming.WordEllipsis>입니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Media.FormattedText>
- [WPF의 문서](documents-in-wpf.md)
- [WPF의 입력 체계](typography-in-wpf.md)
- [윤곽선이 있는 텍스트 만들기](how-to-create-outlined-text.md)
- [방법: 텍스트의 PathGeometry 애니메이션 만들기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
