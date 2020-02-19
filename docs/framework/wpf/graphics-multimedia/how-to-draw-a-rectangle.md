---
title: '방법: 사각형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
ms.openlocfilehash: 95191e9d90bc2ac32902399125d9a51192e897bf
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452937"
---
# <a name="how-to-draw-a-rectangle"></a>방법: 사각형 그리기
이 예제에서는 <xref:System.Windows.Shapes.Rectangle> 요소를 사용 하 여 사각형을 그리는 방법을 보여 줍니다.  
  
 사각형을 그리려면 <xref:System.Windows.Shapes.Rectangle> 요소를 만들고 해당 <xref:System.Windows.FrameworkElement.Width%2A>를 지정 하 고 <xref:System.Windows.FrameworkElement.Height%2A>합니다. 사각형 안에를 그리려면 해당 <xref:System.Windows.Shapes.Shape.Fill%2A>설정 합니다. 사각형에 윤곽선을 지정 하려면 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A>와 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용 합니다.  
  
 사각형의 모퉁이를 둥글게 지정 하려면 선택적 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성을 지정 합니다. <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성은 사각형의 모퉁이를 둥글게 하는 데 사용 되는 타원의 x 축과 y-축 반경을 설정 합니다.  
  
 다음 예제에서는 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소가 <xref:System.Windows.Controls.Canvas>에 그려집니다. 첫 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부가 있습니다. 두 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부, <xref:System.Windows.Media.Brushes.Black%2A> 윤곽선 및 모퉁이가 둥근 모퉁이가 있습니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#Rectangle1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Canvas> 사용 하 여 사각형을 포함 하지만, 텍스트가 아닌 콘텐츠를 지 원하는 모든 <xref:System.Windows.Controls.Panel> 나 <xref:System.Windows.Controls.Control>에서 사각형 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다. 실제로 사각형은 <xref:System.Windows.Controls.Grid> 패널의 일부에 대 한 배경을 제공 하는 데 특히 유용 합니다. 예는 [테이블 개요](../advanced/table-overview.md)를 참조 하세요.  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Shapes.Rectangle>
- [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
- [테이블 개요](../advanced/table-overview.md)
