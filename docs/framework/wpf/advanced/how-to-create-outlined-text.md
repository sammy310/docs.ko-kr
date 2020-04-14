---
title: '방법: 윤곽선이 있는 텍스트 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 86bfa396a2aa44eb511c014687501d60e170a396
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81278927"
---
# <a name="how-to-create-outlined-text"></a>방법: 윤곽이 있는 텍스트 만들기

대부분의 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 텍스트 문자열에 장식을 추가할 때 개별 문자 또는 문자 모음의 측면에서 텍스트를 사용하고 있습니다. 예를 들어 선형 그라데이션 브러시를 만들어 오브젝트의 속성에 <xref:System.Windows.Controls.Control.Foreground%2A> 적용할 수 있습니다. <xref:System.Windows.Controls.TextBox> 텍스트 상자를 표시하거나 편집하면 선형 그라데이션 브러시가 텍스트 문자열의 현재 문자 집합에 자동으로 적용됩니다.  
  
 ![선형 그라데이션 브러시로 표시된 텍스트](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 그러나 텍스트를 개체로 <xref:System.Windows.Media.Geometry> 변환하여 시각적으로 풍부한 다른 유형의 텍스트를 만들 수도 있습니다. 예를 들어 텍스트 문자열의 윤곽선을 기반으로 <xref:System.Windows.Media.Geometry> 개체를 만들 수 있습니다.  
  
 ![선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 텍스트가 <xref:System.Windows.Media.Geometry> 개체로 변환되면 더 이상 문자 컬렉션이 아니므로 텍스트 문자열의 문자를 수정할 수 없습니다. 그러나 스트로크와 채우기 속성을 수정하여 변환된 텍스트의 모양에 영향을 줄 수 있습니다. 스트로크는 변환된 텍스트의 윤곽선을 나타내고, 채우기는 변환된 텍스트의 윤곽선 내부에 있는 영역을 나타냅니다.  
  
 다음 예제에서는 변환된 텍스트의 스트로크 및 채우기를 수정하여 시각적 효과를 만드는 몇 가지 방법을 보여 줍니다.  
  
 ![채우기와 스트로크에 다른 색을 사용하는 텍스트](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![스트로크에 이미지 브러시가 적용된 텍스트](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 변환된 텍스트의 경계 상자 사각형 또는 강조 표시를 수정할 수도 있습니다. 다음 예제에서는 변환된 텍스트의 스트로크 및 강조 표시를 수정하여 시각적 효과를 만드는 방법을 보여 줍니다.  
  
 ![선및 강조 표시에 이미지 브러시가 적용된 텍스트](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>예제  
 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환하는 핵심은 개체를 <xref:System.Windows.Media.FormattedText> 사용하는 것입니다. 이 개체를 만든 후에는 <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> 및 <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> 메서드를 사용하여 텍스트를 <xref:System.Windows.Media.Geometry> 개체로 변환할 수 있습니다. 첫 번째 메서드는 서식이 지정된 텍스트의 형상을 반환합니다. 두 번째 메서드는 서식이 지정된 텍스트의 경계 상자의 형상을 반환합니다. 다음 코드 예제에서는 <xref:System.Windows.Media.FormattedText> 개체를 만들고 서식이 지정된 텍스트와 해당 경계 상자의 형상을 검색하는 방법을 보여 주며 있습니다.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 검색된 개체를 <xref:System.Windows.Media.Geometry> 표시하려면 변환된 텍스트를 표시하는 <xref:System.Windows.Media.DrawingContext> 개체에 액세스해야 합니다. 이러한 코드 예제에서는 사용자 정의 렌더링을 지원하는 클래스에서 파생된 사용자 지정 제어 개체를 만들어 이 액세스권한을 얻을 수 있습니다.  
  
 사용자 <xref:System.Windows.Media.Geometry> 지정 컨트롤에 개체를 표시하려면 메서드에 대한 재정의를 <xref:System.Windows.UIElement.OnRender%2A> 제공합니다. 재정의 된 메서드는 <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> 메서드를 사용하여 <xref:System.Windows.Media.Geometry> 개체를 그려야 합니다.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  예제 사용자 제어 개체의 소스는 [C#](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) 및 [Visual Basic에 대한 개요TextControl.vb에 대한](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb)OutlineTextControl.cs 를 참조하십시오.
  
## <a name="see-also"></a>참고 항목

- [서식 있는 텍스트 그리기](drawing-formatted-text.md)
