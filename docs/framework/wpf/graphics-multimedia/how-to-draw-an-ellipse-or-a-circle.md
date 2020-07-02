---
title: '방법: 타원 또는 원 그리기'
description: Windows Presentation Foundation (WPF)에서 윤곽선 두께 및 내부 색에 대 한 선택 항목으로 타원이 나 원을 그리는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
ms.openlocfilehash: afa0e7d2af42aaee39dca164f23b1a1cacf430ca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853567"
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>방법: 타원 또는 원 그리기
이 예제에서는 요소를 사용 하 여 타원과 원을 그리는 방법을 보여 줍니다 <xref:System.Windows.Shapes.Ellipse> . 타원을 그리려면 요소를 만들고 <xref:System.Windows.Shapes.Ellipse> 해당 및를 지정 <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> 합니다. 해당 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 사용 하 여 <xref:System.Windows.Media.Brush> 타원의 내부를 그리는 데 사용 되는를 지정 합니다. 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 사용 하 여 <xref:System.Windows.Media.Brush> 타원의 윤곽선을 그리는 데 사용 되는를 지정 합니다. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>속성은 타원 윤곽선의 두께를 지정 합니다.  
  
 원을 그리려면 <xref:System.Windows.FrameworkElement.Width%2A> 요소의 및를 <xref:System.Windows.FrameworkElement.Height%2A> <xref:System.Windows.Shapes.Ellipse> 서로 동일 하 게 설정 합니다.  
  
 다음 예제에서는 내에 4 개의 <xref:System.Windows.Shapes.Ellipse> 요소를 그립니다 <xref:System.Windows.Controls.Canvas> .  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 이 예제에서는를 사용 하 여 <xref:System.Windows.Controls.Canvas> 줄임표를 포함 하지만, <xref:System.Windows.Controls.Panel> <xref:System.Windows.Controls.Control> 텍스트가 아닌 콘텐츠를 지 원하는 또는와 함께 타원 요소 (및 다른 모든 셰이프 요소)를 사용할 수 있습니다.  
  
 이 예제는 더 큰 샘플의 일부입니다. 전체 샘플은 [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Shapes.Ellipse>
- <xref:System.Windows.Shapes.Shape>
- [셰이프 요소 샘플](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
