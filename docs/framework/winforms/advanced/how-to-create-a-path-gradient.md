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
ms.openlocfilehash: a04465c31b160f97568ed88c434e7e3a5126ebb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "59975756"
---
# <a name="how-to-create-a-path-gradient"></a>방법: 경로 그라데이션 만들기
<xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스 점진적으로 색을 변경 하 여 셰이프를 입력 하는 방식을 사용자 지정할 수 있습니다. 예를 들어 경로의 센터에 대 한 한 가지 색 및 경로 경계에 다른 색을 지정할 수 있습니다. 또한 각 패스의 경계를 따라 여러 지점에 대 한 별도 색을 지정할 수 있습니다.  
  
> [!NOTE]
>  GDI +에서 경로 선 및 곡선에서 유지 관리의 시퀀스를 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다. GDI + 경로 대 한 자세한 내용은 참조 하세요. [GDI +의 그래픽 경로](graphics-paths-in-gdi.md) 하 고 [Constructing 및 그리기 경로](constructing-and-drawing-paths.md)합니다.  

이 문서의 예제에서는 컨트롤에서 호출 되는 메서드는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.  

### <a name="to-fill-an-ellipse-with-a-path-gradient"></a>타원을 채우도록 경로 그라데이션  
  
-   다음 예제에서는 경로 그라데이션 브러시를 사용 하 여 타원을 채웁니다. 가운데 색은 파랑으로 설정 하 고 경계 색 바다색으로 설정 됩니다. 다음 그림은 채워진된 타원을 보여 줍니다.  
  
     ![그라데이션 경로 타원을 채웁니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse.png)  
  
     기본적으로 경로 그라데이션 브러시를 경로의 경계 외부로 확장 되지 않습니다. 경로 그라데이션 브러시를 사용 하 여 경로 경계를 넘어 확장 하는 그림에 맞게 경로 외부 화면 영역의 채워지지 않습니다.  
  
     다음 그림에서는 변경 하는 경우 어떻게 되나요 합니다 <xref:System.Drawing.Graphics.FillEllipse%2A?displayProperty=nameWithType> 에 다음 코드에서 호출 `e.Graphics.FillRectangle(pthGrBrush, 0, 10, 200, 40)`:  
  
     ![그라데이션 경로 경로 경계를 벗어나 확장입니다.](./media/how-to-create-a-path-gradient/gradient-path-extended-beyond-boundary.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#11)]
     [!code-vb[System.Drawing.UsingaGradientBrush#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#11)]  
  
     앞의 코드 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요 합니다 <xref:System.Windows.Forms.PaintEventArgs> 매개 변수는 e의 <xref:System.Windows.Forms.PaintEventHandler>.  
  
### <a name="to-specify-points-on-the-boundary"></a>경계에 요소를 지정 하려면  
  
-   다음 예제에서는 별 모양 경로에서 경로 그라데이션 브러시를 생성합니다. 코드 집합을 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterColor%2A> 빨간색 별모양의 중심에서 색을 설정 하는 속성입니다. 코드 설정 하 여는 <xref:System.Drawing.Drawing2D.PathGradientBrush.SurroundColors%2A> 다양 한 색을 지정 하려면 속성 (에 저장 합니다 `colors` 배열) 개별 지점에는 `points` 배열. 코드의 마지막 문에서 경로 그라데이션 브러시를 사용 하 여 별 모양 경로 채웁니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#12)]
     [!code-vb[System.Drawing.UsingaGradientBrush#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#12)]  
  
-   다음 예제에서는 그립니다 없이 경로 그라데이션을 <xref:System.Drawing.Drawing2D.GraphicsPath> 코드에서이 개체입니다. 특정 <xref:System.Drawing.Drawing2D.PathGradientBrush.%23ctor%2A> 예제의 생성자 점의 배열을 받지만 필요 하지 않습니다는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체입니다. 또한는 <xref:System.Drawing.Drawing2D.PathGradientBrush> 경로가 아닌 사각형을 채우는 데 사용 됩니다. 사각형은 사각형의 일부 브러시에 의해 칠하지 않습니다 있도록 브러시를 정의 하는 데 닫힌된 경로 보다 큽니다. 다음 그림에서는 사각형 (점선) 및 경로 그라데이션 브러시로 칠하는 사각형의 일부를 보여 줍니다. 
  
     ![경로 그라데이션 브러시 그라데이션 부분입니다.](./media/how-to-create-a-path-gradient/gradient-painted-path-gradient-brush.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#13)]
     [!code-vb[System.Drawing.UsingaGradientBrush#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#13)]  
  
### <a name="to-customize-a-path-gradient"></a>경로 그라데이션 사용자 지정 하려면  
  
-   설정 하는 경로 그라데이션 브러시를 사용자 지정 하는 한 가지 방법은 해당 <xref:System.Drawing.Drawing2D.PathGradientBrush.FocusScales%2A> 속성입니다. 기본 경로 내에 있는 내부 경로 지정 합니다. 가운데 색 어디에서 나 내부 경로의 대신 중심점에만 표시 됩니다.  
  
     다음 예제에서는 타원형 경로 기반 경로 그라데이션 브러시를 만듭니다. 코드 경계 색을 파란색를 설정 하 고, 가운데 색을 바다색으로 설정 하는 원형 경로 맞게 경로 그라데이션 브러시를 사용 하 여 합니다.  
  
     그런 다음 코드는 포커스 범위의 경로 그라데이션 브러시를 설정합니다. X 포커스 확장 0.3 집합과 y 포커스 확장 0.8로 설정 합니다. 호출을 <xref:System.Drawing.Graphics.TranslateTransform%2A> 메서드를 <xref:System.Drawing.Graphics> 개체 있도록 후속 호출 <xref:System.Drawing.Graphics.FillPath%2A> 첫 번째 타원의 오른쪽에 있는 타원을 채웁니다.  
  
     포커스 눈금의 효과 보려면 주 타원을 중심을 공유 하는 작은 타원을 가정해 보겠습니다. 작은 (내부) 타원은 주 타원 (가운데를 중심으로)까지 가로로 크기가 조정 0.3에서 세로로 0.8의 비율로 합니다. 외부 타원의 경계에서 내부 타원의 경계를 이동 하면 색 변경 점진적으로 파랑에서을 바다색 됩니다. 공유 센터로 바다색 색 계속 내부 타원의 경계에서 이동 합니다.  
  
     다음 그림에서는 다음 코드의 출력을 보여 줍니다. 왼쪽 타원 바다색 중심점에만 있습니다. 오른쪽 타원 바다색 내부 경로 내 어디에서 나이입니다.  
  
 ![포커스 눈금의 그라데이션 효과](./media/how-to-create-a-path-gradient/focus-scales-aqua-inner-outer-ellipse.png)  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.UsingaGradientBrush#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#14)]  
  
### <a name="to-customize-with-interpolation"></a>보간을 사용 하 여 사용자 지정 하려면  
  
-   경로 그라데이션 브러시를 사용자 지정 하는 또 다른 방법은 보간 색의 배열 및 보간 위치 배열을 지정 하는 것입니다.  
  
     다음 예제에서는 삼각형을 기반으로 경로 그라데이션 브러시를 만듭니다. 코드 집합을 <xref:System.Drawing.Drawing2D.PathGradientBrush.InterpolationColors%2A> 보간 위치 (0, 0.25, 1)의 배열 및 보간 색 (진한 녹색, aqua, 파란색)의 배열을 지정 경로 그라데이션 브러시의 속성입니다. 중심점에 삼각형의 경계에서 이동 하면 색 변경 점진적으로 진한 녹색 바다색 이동한 다음 바다색에서 파랑으로 합니다. Aqua 진한 녹색 변경 진한 녹색에서 파란색 거리의 25%에서 발생 합니다.  
  
     다음 그림에서는 사용자 지정 경로 그라데이션 브러시를 사용 하 여 채운 삼각형을 보여 줍니다.  
  
     ![사용자 지정 경로 그라데이션 브러시를 사용 하 여 삼각형이 채워집니다.](./media/how-to-create-a-path-gradient/gradient-brush-filled-triangle.png)  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#15)]
     [!code-vb[System.Drawing.UsingaGradientBrush#15](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#15)]  
  
### <a name="to-set-the-center-point"></a>중심점을 설정 하려면  
  
-   기본적으로 경로 그라데이션 브러시의 중심점 브러시를 생성 하는 데 사용 되는 경로의 중심에는 합니다. 설정 하 여 중심점의 위치를 변경할 수는 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 의 속성을 <xref:System.Drawing.Drawing2D.PathGradientBrush> 클래스입니다.  
  
     다음 예제에서는 타원을 기반으로 경로 그라데이션 브러시를 만듭니다. 타원의 중심에는 (70, 35) 되지만 경로 그라데이션 브러시의 중심점 설정 됩니다 (120, 40).  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#16)]
     [!code-vb[System.Drawing.UsingaGradientBrush#16](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#16)]  
  
     다음 그림은 채워진된 타원 및 경로 그라데이션 브러시의 중심점을 보여 줍니다.  
  
     ![채워진 타원 및 센터 지점과 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-filled-ellipse-center-point.png)  
  
-   경로 브러시를 생성 하는 데 사용 된 외부 위치 경로 그라데이션 브러시의 중심점을 설정할 수 있습니다. 다음 예제에서는 대체 설정에 대 한 호출을 <xref:System.Drawing.Drawing2D.PathGradientBrush.CenterPoint%2A> 위의 코드에서 속성입니다.  
  
     [!code-csharp[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#17)]
     [!code-vb[System.Drawing.UsingaGradientBrush#17](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#17)]  
  
     다음 그림에서는이 변경으로 인해 출력을 보여 줍니다.  
  
     ![패스의 외부 영역 중심점을 사용 하 여 그라데이션 경로입니다.](./media/how-to-create-a-path-gradient/gradient-path-center-point-outside.png)  
  
     앞의 그림에서 타원의 오른쪽 끝에 있는 점 없는 순수 파란색 (근접 하지만). 그라데이션의 색 채우기 색 (0, 0, 255) 순수 파란색 수 없는 지점 (145, 35)에 도달 하는 경우에 따라 배치 됩니다. 채우기에 도달 하지 않습니다 하지만 (145, 35) 해당 경로 내 에서만 경로 그라데이션 브러시를 그리는 때문입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요할 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.  
  
## <a name="see-also"></a>참고자료

- [그라데이션 브러시를 사용하여 도형 채우기](using-a-gradient-brush-to-fill-shapes.md)
