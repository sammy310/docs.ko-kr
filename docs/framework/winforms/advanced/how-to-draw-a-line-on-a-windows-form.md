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
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="bebf6-103">방법: Windows Form에서 선 그리기</span><span class="sxs-lookup"><span data-stu-id="bebf6-103">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="bebf6-104">이 예제에서는 폼에 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="bebf6-104">This example draws a line on a form.</span></span> <span data-ttu-id="bebf6-105">일반적으로 폼에 그릴 때 다음 예제와 같이 폼의 이벤트를 처리 하 <xref:System.Windows.Forms.Control.Paint> 고 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 의 속성을 사용 하 여 그리기를 수행 합니다. <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="bebf6-105">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="bebf6-106">예제</span><span class="sxs-lookup"><span data-stu-id="bebf6-106">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bebf6-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="bebf6-107">Compiling the Code</span></span>  
 <span data-ttu-id="bebf6-108">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="bebf6-108">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bebf6-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bebf6-109">Robust Programming</span></span>  
 <span data-ttu-id="bebf6-110">항상 <xref:System.IDisposable.Dispose%2A> 개체와 같은 시스템 리소스를 사용 하는 개체에서를 호출 해야 합니다 <xref:System.Drawing.Pen> .</span><span class="sxs-lookup"><span data-stu-id="bebf6-110">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bebf6-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bebf6-111">See also</span></span>

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="bebf6-112">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="bebf6-112">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="bebf6-113">펜을 사용하여 선 및 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="bebf6-113">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="bebf6-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="bebf6-114">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
