---
title: Graphics 개체의 상태 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182449"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Graphics 개체의 상태 관리
수업은 <xref:System.Drawing.Graphics> GDI+의 중심에 있습니다. 아무것도 그리려면 개체를 <xref:System.Drawing.Graphics> 가져오고, 해당 속성을 설정하고, <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A>해당 메서드를 <xref:System.Drawing.Graphics.DrawLine%2A>호출합니다.  
  
 다음 예제는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 개체의 <xref:System.Drawing.Graphics> 메서드를 호출합니다. 메서드에 전달된 <xref:System.Drawing.Graphics.DrawRectangle%2A> 첫 번째 <xref:System.Drawing.Pen> 인수는 개체입니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>그래픽 상태  
 객체는 <xref:System.Drawing.Graphics> <xref:System.Drawing.Graphics.DrawLine%2A> 및 와 <xref:System.Drawing.Graphics.DrawRectangle%2A>같은 그리기 방법을 제공하는 것 이상을 수행합니다. 또한 <xref:System.Drawing.Graphics> 개체는 다음과 같은 범주로 나눌 수 있는 그래픽 상태를 유지합니다.  
  
- 품질 설정  
  
- 변환  
  
- 클리핑 영역  
  
### <a name="quality-settings"></a>품질 설정  
 <xref:System.Drawing.Graphics> 개체에는 그려진 항목의 품질에 영향을 주는 여러 속성이 있습니다. 예를 들어 속성에서 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 텍스트에 적용된 안티앨리어싱(있는 경우)의 유형을 지정할 수 있습니다. 품질에 영향을 주는 <xref:System.Drawing.Graphics.SmoothingMode%2A> <xref:System.Drawing.Graphics.CompositingMode%2A>다른 <xref:System.Drawing.Graphics.CompositingQuality%2A>속성은 " 및 <xref:System.Drawing.Graphics.InterpolationMode%2A>  
  
 다음 예제에서는 두 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>개의 타원을 그립니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>변환  
 개체는 <xref:System.Drawing.Graphics> 해당 <xref:System.Drawing.Graphics> 개체에 의해 그려진 모든 항목에 적용되는 두 가지 변환(월드 및 페이지)을 유지 관리합니다. 모든 affine 변환은 세계 변환에 저장할 수 있습니다. Affine 변환에는 배율 조정, 회전, 반사, 기울이기 및 변환이 포함됩니다. 페이지 변환은 크기 조정 및 단위 변경(예: 픽셀에서 인치)에 사용할 수 있습니다. 자세한 내용은 [좌표계 및 변환 을](coordinate-systems-and-transformations.md)참조하십시오.  
  
 다음 예제는 개체의 월드 및 <xref:System.Drawing.Graphics> 페이지 변환을 설정합니다. 세계 변환은 30도 회전으로 설정됩니다. 두 번째로 <xref:System.Drawing.Graphics.DrawEllipse%2A> 전달된 좌표가 픽셀대신 밀리미터로 처리되도록 페이지 변환이 설정됩니다. 코드는 메서드에 대해 <xref:System.Drawing.Graphics.DrawEllipse%2A> 두 개의 동일한 호출을 합니다. 월드 변환은 첫 번째 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출에 적용되고 두 번째 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출에는 변환(월드 및 페이지)이 모두 적용됩니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 다음 그림에서는 두 타원을 보여 주십습니다. 30도 회전은 타원의 중심이 아니라 좌표계(클라이언트 영역의 왼쪽 위 모서리)의 원점에 관한 것입니다. 또한 펜 너비가 1이면 첫 번째 타원의 경우 1픽셀, 두 번째 타원의 경우 1mm를 의미합니다.  
  
 ![두 개의 타원을 보여 주는 그림: 회전 및 펜 너비입니다.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>클리핑 영역  
 개체는 <xref:System.Drawing.Graphics> 해당 개체에 의해 그려진 모든 항목에 <xref:System.Drawing.Graphics> 적용되는 클리핑 영역을 유지 관리합니다. 메서드를 호출하여 클리핑 영역을 <xref:System.Drawing.Graphics.SetClip%2A> 설정할 수 있습니다.  
  
 다음 예제는 두 사각형의 결합을 형성 하여 더하기 모양영역을 만듭니다. 해당 영역은 객체의 클리핑 <xref:System.Drawing.Graphics> 영역으로 지정됩니다. 그런 다음 코드는 클리핑 영역의 내부로 제한된 두 줄을 그립니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 다음 그림에서는 잘린 선을 보여 주었습니다.  
  
 ![제한된 클립 영역을 보여 주는 다이어그램입니다.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>참고 항목

- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [중첩된 Graphics 컨테이너 사용](using-nested-graphics-containers.md)
