---
title: '방법: 펜 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating pens
- pens [Windows Forms], creating
- Pen object
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
ms.openlocfilehash: 3d88824845bf357dd9ee5f1ee8fd02f095aee605
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716922"
---
# <a name="how-to-create-a-pen"></a><span data-ttu-id="193ff-102">방법: 펜 만들기</span><span class="sxs-lookup"><span data-stu-id="193ff-102">How to: Create a Pen</span></span>
<span data-ttu-id="193ff-103">이 예제에서는 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="193ff-103">This example creates a <xref:System.Drawing.Pen> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="193ff-104">예제</span><span class="sxs-lookup"><span data-stu-id="193ff-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## <a name="robust-programming"></a><span data-ttu-id="193ff-105">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="193ff-105">Robust Programming</span></span>  
 <span data-ttu-id="193ff-106">와 같은 시스템 리소스를 사용 하는 개체 사용을 마치면 <xref:System.Drawing.Pen> 개체를 호출 해야 <xref:System.Drawing.Pen.Dispose%2A> 에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="193ff-106">After you have finished using objects that consume system resources, such as <xref:System.Drawing.Pen> objects, you should call <xref:System.Drawing.Pen.Dispose%2A> on them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="193ff-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="193ff-107">See also</span></span>
- <xref:System.Drawing.Pen>
- [<span data-ttu-id="193ff-108">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="193ff-108">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="193ff-109">GDI+의 펜, 선 및 사각형</span><span class="sxs-lookup"><span data-stu-id="193ff-109">Pens, Lines, and Rectangles in GDI+</span></span>](pens-lines-and-rectangles-in-gdi.md)
