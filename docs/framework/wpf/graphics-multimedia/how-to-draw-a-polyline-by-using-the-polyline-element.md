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
ms.openlocfilehash: 35981f6d5a47ea5d5e024efe714b52103938eddf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378182"
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>방법: Polyline 요소를 사용하여 다중선 그리기
이 예제에서는 사용 하 여 일련의 연결 된 줄은 다중선 그리기를 <xref:System.Windows.Shapes.Polyline> 요소입니다.  
  
 다중선 그리기를 만들려면를 <xref:System.Windows.Shapes.Polyline> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 셰이프 꼭 짓 점을 지정 하는 속성입니다. 마지막으로 사용 합니다 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 스트로크 없는 줄에 표시 되지 않으므로 간략하게 설명 하는 다중선을 설명 하는 속성입니다.  
  
> [!NOTE]
>  때문에 합니다 <xref:System.Windows.Shapes.Polyline> 요소는 닫힌된 셰이프는 <xref:System.Windows.Shapes.Shape.Fill%2A> 모양의 윤곽선을 의도적으로 닫은 경우에 속성에 적용 되지 않습니다. 사용 하 여 닫힌된 도형을 만들어야를 <xref:System.Windows.Shapes.Shape.Fill%2A>를 사용 하 여를 <xref:System.Windows.Shapes.Polygon> 요소입니다.  
  
 다음 예제에서는 두 개의 그립니다 <xref:System.Windows.Shapes.Polyline> 내부 요소는 <xref:System.Windows.Controls.Canvas>합니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 구문이 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 다중선을 포함 하려면 사용할 수 있습니다 폴리라인 요소 (및 다른 모든 도형 요소)와 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 더 큰 샘플;의 일부 전체 샘플을 참조 하세요 [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Shapes.Polygon>
- <xref:System.Windows.Shapes.Shape>
- [도형 요소 샘플](https://go.microsoft.com/fwlink/?LinkID=160037)
- [WPF에서 Shape 및 기본 그리기 개요](shapes-and-basic-drawing-in-wpf-overview.md)
