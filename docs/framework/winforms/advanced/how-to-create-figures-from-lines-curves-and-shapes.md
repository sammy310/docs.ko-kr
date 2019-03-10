---
title: '방법: 선, 곡선 및 도형으로 그림 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: 1977f1c9efe2c379ef6039870aade300efca2bdd
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709499"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a><span data-ttu-id="2816c-102">방법: 선, 곡선 및 도형으로 그림 만들기</span><span class="sxs-lookup"><span data-stu-id="2816c-102">How to: Create Figures from Lines, Curves, and Shapes</span></span>
<span data-ttu-id="2816c-103">그림을 만들려면 생성을 <xref:System.Drawing.Drawing2D.GraphicsPath>와 같은 메서드를 호출 하 고 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>기본 경로에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-103">To create a figure, construct a <xref:System.Drawing.Drawing2D.GraphicsPath>, and then call methods, such as <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> and <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, to add primitives to the path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2816c-104">예제</span><span class="sxs-lookup"><span data-stu-id="2816c-104">Example</span></span>  
 <span data-ttu-id="2816c-105">다음 코드 예제에서는 그림이 포함 된 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-105">The following code examples create paths that have figures:</span></span>  
  
-   <span data-ttu-id="2816c-106">첫 번째 예제에서는 단일 그림 포함 된 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-106">The first example creates a path that has a single figure.</span></span> <span data-ttu-id="2816c-107">그림은 단일 호 이루어져 있습니다. 호에는 기본 좌표계에서 시계 반대 방향으로 180도 스윕 각도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-107">The figure consists of a single arc. The arc has a sweep angle of –180 degrees, which is counterclockwise in the default coordinate system.</span></span>  
  
-   <span data-ttu-id="2816c-108">두 번째 예제에서는 두 그림에 포함 된 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-108">The second example creates a path that has two figures.</span></span> <span data-ttu-id="2816c-109">첫 번째 그림에는 뒤에 줄 호입니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-109">The first figure is an arc followed by a line.</span></span> <span data-ttu-id="2816c-110">두 번째 그림은 뒤에 줄 뒤에 곡선을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-110">The second figure is a line followed by a curve followed by a line.</span></span> <span data-ttu-id="2816c-111">첫 번째 그림을 남겨 하 고 두 번째 그림 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-111">The first figure is left open, and the second figure is closed.</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2816c-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2816c-112">Compiling the Code</span></span>  
 <span data-ttu-id="2816c-113">앞의 예제에서는 Windows Forms에서 사용 하도록 설계 되었으며 필요할 <xref:System.Windows.Forms.PaintEventArgs> `e`의 매개 변수는 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="2816c-113">The previous examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2816c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2816c-114">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="2816c-115">경로 구성 및 그리기</span><span class="sxs-lookup"><span data-stu-id="2816c-115">Constructing and Drawing Paths</span></span>](constructing-and-drawing-paths.md)
- [<span data-ttu-id="2816c-116">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="2816c-116">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
