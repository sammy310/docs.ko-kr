---
title: '방법: Polyline 요소를 사용하여 다중선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 6698141bcaa3b0fd5f5b9cf66bcab1be1f4ea2f0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452963"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>방법: Polyline 요소를 사용하여 다중선 그리기
이 예제에서는 <xref:System.Windows.Shapes.Polyline> 요소를 사용 하 여 일련의 연결 된 선 인 다중선을 그리는 방법을 보여 줍니다.  
  
 다중선을 그리려면 <xref:System.Windows.Shapes.Polyline> 요소를 만들고 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 속성을 사용 하 여 도형 꼭 짓 점을 지정 합니다. 마지막으로, <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용 하 여 스트로크가 없는 선이 보이지 않기 때문에 다중선 윤곽선을 설명 합니다.  
  
> [!NOTE]
> <xref:System.Windows.Shapes.Polyline> 요소는 닫힌 모양이 아니기 때문에 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성은 모양 윤곽선을 의도적으로 닫는 경우에도 영향을 주지 않습니다. <xref:System.Windows.Shapes.Shape.Fill%2A>를 사용 하 여 닫힌 도형을 만들려면 <xref:System.Windows.Shapes.Polygon> 요소를 사용 합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>안에 두 개의 <xref:System.Windows.Shapes.Polyline> 요소를 그립니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 올바른 점에 대 한 구문은 쉼표로 구분 된 x 및 y 좌표 쌍을 공백으로 구분한 목록입니다.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Canvas> 사용 하 여 폴리라인을 포함 하지만 텍스트가 아닌 콘텐츠를 지 원하는 <xref:System.Windows.Controls.Panel> 나 <xref:System.Windows.Controls.Control>와 함께 폴리라인 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다.  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
