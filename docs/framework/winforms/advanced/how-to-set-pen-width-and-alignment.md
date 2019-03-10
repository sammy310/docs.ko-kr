---
title: '방법: 집합 펜 굵기 및 맞춤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [Windows Forms], setting width
- pens [Windows Forms], setting alignment
ms.assetid: a202af36-4d31-4401-a126-b232f51db581
ms.openlocfilehash: e82f406b4fdca93df7a811eea5506846d56fda28
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703051"
---
# <a name="how-to-set-pen-width-and-alignment"></a><span data-ttu-id="6b5bc-102">방법: 집합 펜 굵기 및 맞춤</span><span class="sxs-lookup"><span data-stu-id="6b5bc-102">How to: Set Pen Width and Alignment</span></span>
<span data-ttu-id="6b5bc-103">만들 때를 <xref:System.Drawing.Pen>를 생성자에 인수 중 하나로 펜 굵기를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-103">When you create a <xref:System.Drawing.Pen>, you can supply the pen width as one of the arguments to the constructor.</span></span> <span data-ttu-id="6b5bc-104">펜 너비를 변경할 수도 있습니다는 <xref:System.Drawing.Pen.Width%2A> 의 속성을 <xref:System.Drawing.Pen> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-104">You can also change the pen width with the <xref:System.Drawing.Pen.Width%2A> property of the <xref:System.Drawing.Pen> class.</span></span>  
  
 <span data-ttu-id="6b5bc-105">이론적인 선의 너비를 0에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-105">A theoretical line has a width of 0.</span></span> <span data-ttu-id="6b5bc-106">1 픽셀 너비는 줄을 그릴 때 픽셀에 이론적인 선의 가운데 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-106">When you draw a line that is 1 pixel wide, the pixels are centered on the theoretical line.</span></span> <span data-ttu-id="6b5bc-107">둘 이상의 픽셀로 선에 그리면 픽셀 하거나 이론적인 선의에 주안점을 둡니다 또는 이론적인 선의 한쪽에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-107">If you draw a line that is more than one pixel wide, the pixels are either centered on the theoretical line or appear to one side of the theoretical line.</span></span> <span data-ttu-id="6b5bc-108">펜 맞춤 속성을 설정할 수는 <xref:System.Drawing.Pen> 이론적인 선을 기준으로 해당 펜을 사용 하 여 그린 픽셀을 배치 하는 방식을 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-108">You can set the pen alignment property of a <xref:System.Drawing.Pen> to determine how the pixels drawn with that pen will be positioned relative to theoretical lines.</span></span>  
  
 <span data-ttu-id="6b5bc-109">값 <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, 및 <xref:System.Drawing.Drawing2D.PenAlignment.Inset> 다음에 나타나는 코드 예제는의 멤버는 <xref:System.Drawing.Drawing2D.PenAlignment> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-109">The values <xref:System.Drawing.Drawing2D.PenAlignment.Center>, <xref:System.Drawing.Drawing2D.PenAlignment.Outset>, and <xref:System.Drawing.Drawing2D.PenAlignment.Inset> that appear in the following code examples are members of the <xref:System.Drawing.Drawing2D.PenAlignment> enumeration.</span></span>  
  
 <span data-ttu-id="6b5bc-110">다음 코드 예제에서는 두 번 줄을 그립니다: 한 번 너비가 10의 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-110">The following code example draws a line twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
### <a name="to-vary-the-width-of-a-pen"></a><span data-ttu-id="6b5bc-111">펜의 너비를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="6b5bc-111">To vary the width of a pen</span></span>  
  
-   <span data-ttu-id="6b5bc-112">값을 설정 합니다 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> (기본값)는 녹색 펜을 사용 하 여 그린 픽셀 중심에 위치 합니다 이론적인 선의 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-112">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> (the default) to specify that pixels drawn with the green pen will be centered on the theoretical line.</span></span> <span data-ttu-id="6b5bc-113">다음 그림에서는 결과 줄을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-113">The following illustration shows the resulting line.</span></span>  
  
     <span data-ttu-id="6b5bc-114">![펜](./media/pens1a.gif "pens1A")</span><span class="sxs-lookup"><span data-stu-id="6b5bc-114">![Pens](./media/pens1a.gif "pens1A")</span></span>  
  
     <span data-ttu-id="6b5bc-115">다음 코드 예제에서는 두 번 사각형을 그립니다: 한 번 너비가 10의 녹색 펜 너비 1의 검은색 펜으로 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-115">The following code example draws a rectangle twice: once with a black pen of width 1 and once with a green pen of width 10.</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#41)]
     [!code-vb[System.Drawing.UsingAPen#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#41)]  
  
### <a name="to-change-the-alignment-of-a-pen"></a><span data-ttu-id="6b5bc-116">펜의 맞춤을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="6b5bc-116">To change the alignment of a pen</span></span>  
  
-   <span data-ttu-id="6b5bc-117">값을 설정 합니다 <xref:System.Drawing.Pen.Alignment%2A> 속성을 <xref:System.Drawing.Drawing2D.PenAlignment.Center> 녹색 펜을 사용 하 여 그린 픽셀 사각형의 경계에서 가운데 맞춤 될는 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-117">Set the value of the <xref:System.Drawing.Pen.Alignment%2A> property to <xref:System.Drawing.Drawing2D.PenAlignment.Center> to specify that the pixels drawn with the green pen will be centered on the boundary of the rectangle.</span></span>  
  
     <span data-ttu-id="6b5bc-118">다음 그림에서는 결과 사각형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-118">The following illustration shows the resulting rectangle.</span></span>  
  
     <span data-ttu-id="6b5bc-119">![펜](./media/pens2.gif "pens2")</span><span class="sxs-lookup"><span data-stu-id="6b5bc-119">![Pens](./media/pens2.gif "pens2")</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#42)]
     [!code-vb[System.Drawing.UsingAPen#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#42)]  
  
### <a name="to-create-an-inset-pen"></a><span data-ttu-id="6b5bc-120">삽입 펜을 만들려면</span><span class="sxs-lookup"><span data-stu-id="6b5bc-120">To create an inset pen</span></span>  
  
-   <span data-ttu-id="6b5bc-121">앞의 코드 예제에서 세 번째 문은 다음과 같이 수정 하 여 녹색 펜의 맞춤을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-121">Change the green pen's alignment by modifying the third statement in the preceding code example as follows:</span></span>  
  
     [!code-csharp[System.Drawing.UsingAPen#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#43)]
     [!code-vb[System.Drawing.UsingAPen#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#43)]  
  
     <span data-ttu-id="6b5bc-122">이제 다음 그림과에서 같이 와이드 녹색 선은 픽셀 사각형의 내부에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6b5bc-122">Now the pixels in the wide green line appear on the inside of the rectangle as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="6b5bc-123">![펜](./media/pens3.gif "pens3")</span><span class="sxs-lookup"><span data-stu-id="6b5bc-123">![Pens](./media/pens3.gif "pens3")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b5bc-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b5bc-124">See also</span></span>
- [<span data-ttu-id="6b5bc-125">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="6b5bc-125">Using a Pen to Draw Lines and Shapes</span></span>](using-a-pen-to-draw-lines-and-shapes.md)
- [<span data-ttu-id="6b5bc-126">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="6b5bc-126">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
