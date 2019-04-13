---
title: '방법: 줄 또는 세그먼트의 끝 모양 수정'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 462e32520393a1c23809cce8eb3c130c13bc882f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091306"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>방법: 줄 또는 세그먼트의 끝 모양 수정
이 예제에는 시작 또는 끝 개방적이 고의 모양을 수정 하는 방법을 보여 줍니다 <xref:System.Windows.Shapes.Shape> 요소입니다. 개방적이 고 시작 부분에도 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> 속성입니다. 개방적이 고 끝에도 변경 하려면 <xref:System.Windows.Shapes.Shape>를 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> 속성입니다. 사용할 수 있는 선 끝이 보려면 참조는 <xref:System.Windows.Media.PenLineCap> 열거형입니다.  
  
> [!NOTE]
>  이 속성이 영향을 주는지는 열린 모양을 같은 <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, 또는 열린 <xref:System.Windows.Shapes.Path> 요소입니다.  
  
 다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Polyline> 요소 각각의 끝에 다양 한 셰이프를 사용 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
