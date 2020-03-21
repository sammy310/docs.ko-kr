---
title: '방법: 경로 그라데이션 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- path gradients [Windows Forms], creating
- gradients [Windows Forms], creating path
- graphics paths [Windows Forms], creating gradient
ms.assetid: 1948e834-e104-481c-b71d-d8aa9e4d106e
ms.openlocfilehash: cf4dc558c008fb8adfc327a6a894a428e985df03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182640"
---
# <a name="how-to-create-a-path-gradient"></a>방법: 경로 그라데이션 만들기
이 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스를 사용하면 점차 적으로 변화하는 색상으로 셰이프를 채우는 방법을 사용자 정의 할 수 있습니다. 예를 들어 패스의 중심에 는 하나의 색상을, 다른 색상은 패스 경계에 지정할 수 있습니다. 패스 경계를 따라 각 점에 대해 별도의 색상을 지정할 수도 있습니다.  
  
> [!NOTE]
> GDI+에서 경로는 오브젝트가 유지 관리하는 선과 곡선의 시퀀스입니다. <xref:System.Drawing.Drawing2D.GraphicsPath> GDI+ 경로에 대한 자세한 내용은 [GDI+](graphics-paths-in-gdi.md) 및 [생성 및 그리기 경로의](constructing-and-drawing-paths.md)그래픽 경로를 참조하십시오.  

이 문서의 예제는 컨트롤의 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기에서 호출되는 메서드입니다.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>타원을 패스 그라데이션으로 채우려면  
  
- 다음 예제는 타원을 경로 그라데이션 브러시로 채웁니다. 중심 색상은 파란색으로 설정되고 경계 색상은 아쿠아로 설정됩니다. 다음 그림에서는 채워진 타원을 보여 주었습니다.  
  
     ![그라데이션 패스는 타원을 채웁니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     기본적으로 경로 그라데이션 브러시는 패스 경계 외부로 확장되지 않습니다. 경로 그라데이션 브러시를 사용하여 패스 경계를 넘어 확장되는 그림을 채우면 경로 외부의 화면 영역이 채워지지 않습니다.  
  
     다음 그림에서는 다음 코드에서 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> 호출을 다음과 같은 `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`코드로 변경하면 어떻게 되는지 보여 주며 다음과 같은 방법을 보여 주며 있습니다.  
  
     ![그라데이션 경로는 패스의 경계를 넘어 확장되었습니다.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     앞의 코드 예제는 Windows Forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 e가 필요합니다.  
  
### <a name="to-specify-points-on-the-boundary"></a>경계에 점을 지정하려면  
  
- 다음 예제는 별 모양 의 경로에서 경로 그라데이션 브러시를 구성합니다. 이 코드는 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 별의 중심에 있는 색상을 빨간색으로 설정하는 속성을 설정합니다. 그런 다음 코드는 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> `colors` `points` 배열의 개별 지점에서 다양한 색상(배열에 저장됨)을 지정하도록 속성을 설정합니다. 마지막 코드 문은 별 모양의 경로를 경로 그라데이션 브러시로 채웁니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
- 다음 예제에서는 코드에 개체가 <xref:System.Drawing.Drawing2D.GraphicsPath> 없는 경로 그라데이션을 그립니다. 예제의 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> 특정 생성자는 점 배열을 수신하지만 개체가 <xref:System.Drawing.Drawing2D.GraphicsPath> 필요하지 않습니다. 또한 경로가 <xref:System.Drawing.Drawing2D.PathGradientBrush> 아닌 사각형을 채우는 데 사용됩니다. 사각형은 브러시를 정의하는 데 사용되는 닫힌 경로보다 크므로 일부 사각형은 브러시로 페인팅되지 않습니다. 다음 그림에서는 사각형(점선)과 경로 그라데이션 브러시로 페인팅된 사각형 부분을 보여 주며 다음과 같은 그림을 보여 주며 다음과 같은 그림을 보여 주며 다음과 같은 그림을 보여줍니다.
  
     ![경로 그라데이션 브러시로 페인팅된 그라데이션 부분입니다.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>경로 그라데이션을 사용자 지정하려면  
  
- 경로 그라데이션 브러시를 사용자 지정하는 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 한 가지 방법은 해당 속성을 설정하는 것입니다. 포커스 배율 조정은 주 경로 내부에 있는 내부 경로를 지정합니다. 중심 색상은 중심점만이 아니라 내부 경로 내부의 모든 곳에 표시됩니다.  
  
     다음 예제는 타원형 경로를 기반으로 경로 그라데이션 브러시를 만듭니다. 코드는 경계 색상을 파란색으로 설정하고 중심 색상을 아쿠아로 설정한 다음 경로 그라데이션 브러시를 사용하여 타원형 경로를 채웁니다.  
  
     다음으로 코드는 경로 그라데이션 브러시의 포커스 축척을 설정합니다. x 포커스 배율은 0.3으로 설정되고 y 포커스 배율은 0.8로 설정됩니다. 이 코드는 <xref:System.Drawing.Graphics.TranslateTransform%2A> 개체의 <xref:System.Drawing.Graphics> 메서드를 호출하여 <xref:System.Drawing.Graphics.FillPath%2A> 첫 번째 타원의 오른쪽에 있는 타원을 채우기 위한 후속 호출을 합니다.  
  
     포커스 스케일의 효과를 보려면 중심을 주 타원과 공유하는 작은 타원을 상상해 보십시오. 작은(내부) 타원은 0.3의 비율로 수평으로 배율(중심 참조)되고 수직으로 0.8배배 배율로 배율조정된 주 타원입니다. 외부 타원의 경계에서 내부 타원의 경계로 이동하면 색상이 파란색에서 아쿠아로 점차 변경됩니다. 내부 타원의 경계에서 공유 중심으로 이동하면 색상이 아쿠아로 유지됩니다.  
  
     다음 그림에서는 다음 코드의 출력을 보여 줍니다. 왼쪽의 타원은 중심점에만 아쿠아입니다. 오른쪽의 타원은 내부 경로 내부의 모든 곳에서 아쿠아입니다.  
  
 ![초점 스케일의 그라데이션 효과](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>보간으로 사용자 지정하려면  
  
- 경로 그라데이션 브러시를 사용자 지정하는 또 다른 방법은 보간 색상 배열과 보간 위치 배열을 지정하는 것입니다.  
  
     다음 예제는 삼각형을 기반으로 경로 그라데이션 브러시를 만듭니다. 코드는 보간 색상(진한 녹색, 아쿠아, 파란색)과 보간 위치 배열(0, 0.25, 1)의 배열을 지정하도록 경로 그라데이션 브러시의 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 속성을 설정합니다. 삼각형의 경계에서 중심점으로 이동하면 색상이 진한 녹색에서 아쿠아로, 그 다음에 아쿠아에서 파란색으로 점차 변합니다. 진한 녹색에서 아쿠아로의 변화는 진한 녹색에서 파란색까지의 거리의 25 %에서 발생합니다.  
  
     다음 그림에서는 사용자 지정 경로 그라데이션 브러시로 채워진 삼각형을 보여 주었습니다.  
  
     ![사용자 지정 경로 그라데이션 브러시로 채워진 삼각형입니다.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>중심점을 설정하려면  
  
- 기본적으로 경로 그라데이션 브러시의 중심점은 브러시를 구성하는 데 사용되는 경로의 중심에 있습니다. 클래스의 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 속성을 설정하여 중심점의 위치를 변경할 <xref:System.Drawing.Drawing2D.PathGradientBrush> 수 있습니다.  
  
     다음 예제는 타원을 기반으로 경로 그라데이션 브러시를 만듭니다. 타원의 중심은 (70, 35)에 있지만 경로 그라데이션 브러시의 중심점은 (120, 40)로 설정됩니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     다음 그림에서는 채워진 타원과 경로 그라데이션 브러시의 중심점을 보여 주었습니다.  
  
     ![채워진 타원과 중심점이 있는 그라데이션 패스입니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
- 경로 그라데이션 브러시의 중심점을 브러시를 구성하는 데 사용된 경로 외부 위치로 설정할 수 있습니다. 다음 예제에서는 이전 코드에서 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 속성을 설정 하는 호출을 대체 합니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     다음 그림에서는 이 변경 사항으로 출력을 보여 주며 다음과 같은 작업을 수행합니다.  
  
     ![패스 외부의 중심점이 있는 그라데이션 패스입니다.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     앞의 그림에서 타원의 맨 오른쪽에 있는 점은 순파가 아닙니다(매우 가깝지만). 그라데이션의 색상은 채우기가 순수한 파란색(0, 0, 255)인 점(145, 35)에 도달한 것처럼 배치됩니다. 그러나 경로 그라데이션 브러시가 경로 내부에만 페인트하기 때문에 채우기(145, 35)에 도달하지 않습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows Forms와 함께 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> `e` <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 이 요구됩니다.  
  
## <a name="see-also"></a>참고 항목

- [그라데이션 브러시를 사용하여 도형 채우기](using-a-gradient-brush-to-fill-shapes.md)
