---
title: '방법: 선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452950"
---
# <a name="how-to-draw-a-line"></a>방법: 선 그리기
이 예제에서는 <xref:System.Windows.Shapes.Line> 요소를 사용 하 여 선을 그리는 방법을 보여 줍니다.  
  
 선을 그리려면 <xref:System.Windows.Shapes.Line> 요소를 만듭니다. 해당 <xref:System.Windows.Shapes.Line.X1%2A> 및 <xref:System.Windows.Shapes.Line.Y1%2A> 속성을 사용 하 여 시작점을 설정 합니다. <xref:System.Windows.Shapes.Line.X2%2A> 및 <xref:System.Windows.Shapes.Line.Y2%2A> 속성을 사용 하 여 끝점을 설정 합니다. 마지막으로, 스트로크가 없는 줄이 보이지 않기 때문에 <xref:System.Windows.Shapes.Shape.Stroke%2A>를 설정 하 고 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 합니다.  
  
 선에는 <xref:System.Windows.Shapes.Shape.Fill%2A> 요소를 설정 해도 아무런 효과가 없습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 요소 안에 3 개의 줄을 그립니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Shapes.Line>
- [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
