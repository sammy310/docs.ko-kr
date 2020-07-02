---
title: '방법: Windows Form에서 채워진 사각형 그리기'
description: Windows Form에서 프로그래밍 방식으로 채워진 사각형을 그리는 방법에 대해 알아봅니다. 또한 코드를 컴파일하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621641"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>방법: Windows Form에서 채워진 사각형 그리기
이 예제에서는 폼에 채워진 사각형을 그립니다.  
  
## <a name="example"></a>예제  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이벤트 처리기에서이 메서드를 호출할 수 없습니다 <xref:System.Windows.Forms.Form.Load> . 폼의 크기를 조정 하거나 다른 폼으로 가려져 있는 경우에는 그려지는 콘텐츠가 다시 그려지지 않습니다. 콘텐츠를 자동으로 다시 그리게 하려면 메서드를 재정의 해야 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> .  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 항상 <xref:System.IDisposable.Dispose%2A> 및 개체와 같은 시스템 리소스를 사용 하는 개체에 대해를 호출 해야 합니다 <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [펜을 사용하여 선 및 도형 그리기](using-a-pen-to-draw-lines-and-shapes.md)
- [GDI+의 브러시 및 채워진 도형](brushes-and-filled-shapes-in-gdi.md)
