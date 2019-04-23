---
title: '방법: 도형이 있는 Windows Form 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 03fcbb97db180e71283810e2daeab9be272b9d5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59087257"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="e6544-102">방법: 도형이 있는 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="e6544-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="e6544-103">이 예제에서는 폼을 타원 양식을 사용 하 여 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6544-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6544-104">예제</span><span class="sxs-lookup"><span data-stu-id="e6544-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e6544-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e6544-105">Compiling the Code</span></span>  
 <span data-ttu-id="e6544-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e6544-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e6544-107"><xref:System.Windows.Forms> 및 <xref:System.Drawing> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e6544-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="e6544-108">이 예제에서는 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 폼의 모양을 변경 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e6544-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="e6544-109">이 코드를 사용 하려면 메서드 선언 뿐만 아니라 메서드 내에서 그리기 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6544-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6544-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="e6544-110">See also</span></span>

- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Drawing.Region>
- <xref:System.Drawing>
- <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>
- <xref:System.Windows.Forms.Control.Region%2A>
- [<span data-ttu-id="e6544-111">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="e6544-111">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
