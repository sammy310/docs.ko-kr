---
title: '방법: 열린 그림 채우기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- open figures [Windows Forms], filling
- figures [Windows Forms], filling
ms.assetid: 5a36b0e4-f1f4-46c0-a85a-22ae98491950
ms.openlocfilehash: e9743d3268a7a2acfb6266872c3346a05269c369
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702730"
---
# <a name="how-to-fill-open-figures"></a><span data-ttu-id="ad785-102">방법: 열린 그림 채우기</span><span class="sxs-lookup"><span data-stu-id="ad785-102">How to: Fill Open Figures</span></span>
<span data-ttu-id="ad785-103">전달 하 여 경로 채울 수는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 <xref:System.Drawing.Graphics.FillPath%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ad785-103">You can fill a path by passing a <xref:System.Drawing.Drawing2D.GraphicsPath> object to the <xref:System.Drawing.Graphics.FillPath%2A> method.</span></span> <span data-ttu-id="ad785-104"><xref:System.Drawing.Graphics.FillPath%2A> 메서드는 현재 경로 대해 설정 된 채우기 모드 (대체 또는 감기)에 따라 경로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-104">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the fill mode (alternate or winding) currently set for the path.</span></span> <span data-ttu-id="ad785-105">경로 모든 열린 그림 그림이 닫혀 있는 것 처럼 경로가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-105">If the path has any open figures, the path is filled as if those figures were closed.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="ad785-106">시작 지점으로 해당 끝점에서 직선 그리기 하 여 그림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-106">closes a figure by drawing a straight line from its ending point to its starting point.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad785-107">예제</span><span class="sxs-lookup"><span data-stu-id="ad785-107">Example</span></span>  
 <span data-ttu-id="ad785-108">다음 예제에서는 하나의 열린 그림 (호) 및 닫힌된 그림 하나 (타원)에 포함 된 경로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-108">The following example creates a path that has one open figure (an arc) and one closed figure (an ellipse).</span></span> <span data-ttu-id="ad785-109">합니다 <xref:System.Drawing.Graphics.FillPath%2A> 메서드는 기본 채우기 모드에 따라 경로 채우는 <xref:System.Drawing.Drawing2D.FillMode.Alternate>합니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-109">The <xref:System.Drawing.Graphics.FillPath%2A> method fills the path according to the default fill mode, which is <xref:System.Drawing.Drawing2D.FillMode.Alternate>.</span></span>  
  
 <span data-ttu-id="ad785-110">다음 그림에서는 예제 코드의 출력을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-110">The following illustration shows the output of the example code.</span></span> <span data-ttu-id="ad785-111">경로 채워지는지 확인 (에 따라 <xref:System.Drawing.Drawing2D.FillMode.Alternate>)를 시작 점으로 끝 지점에서 직선으로 열린 그림 닫힌 경우.</span><span class="sxs-lookup"><span data-stu-id="ad785-111">Note that the path is filled (according to <xref:System.Drawing.Drawing2D.FillMode.Alternate>) as if the open figure were closed by a straight line from its ending point to its starting point.</span></span>  
  
 <span data-ttu-id="ad785-112">![열린 경로 채우기](./media/fillopenpath.png "FillOpenPath")</span><span class="sxs-lookup"><span data-stu-id="ad785-112">![Fill Open Path](./media/fillopenpath.png "FillOpenPath")</span></span>  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad785-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ad785-113">Compiling the Code</span></span>  
 <span data-ttu-id="ad785-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ad785-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad785-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad785-115">See also</span></span>
- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [<span data-ttu-id="ad785-116">GDI+의 그래픽 경로</span><span class="sxs-lookup"><span data-stu-id="ad785-116">Graphics Paths in GDI+</span></span>](graphics-paths-in-gdi.md)
