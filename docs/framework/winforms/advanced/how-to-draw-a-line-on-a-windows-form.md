---
title: '방법: Windows Form에서 선 그리기'
description: Paint 이벤트를 처리 하 여 폼에 선을 그린 다음 PaintEventArgs의 Graphics 속성을 사용 하 여 그리기를 수행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621628"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>방법: Windows Form에서 선 그리기
이 예제에서는 폼에 선을 그립니다. 일반적으로 폼에 그릴 때 다음 예제와 같이 폼의 이벤트를 처리 하 <xref:System.Windows.Forms.Control.Paint> 고 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 의 속성을 사용 하 여 그리기를 수행 합니다. <xref:System.Windows.Forms.PaintEventArgs>  
  
## <a name="example"></a>예제  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 항상 <xref:System.IDisposable.Dispose%2A> 개체와 같은 시스템 리소스를 사용 하는 개체에서를 호출 해야 합니다 <xref:System.Drawing.Pen> .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)
- [펜을 사용하여 선 및 도형 그리기](using-a-pen-to-draw-lines-and-shapes.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
