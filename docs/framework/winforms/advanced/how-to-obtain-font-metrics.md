---
title: '방법: 글꼴 메트릭 얻기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], obtaining metrics
- font metrics [Windows Forms], obtaining
ms.assetid: ff7c0616-67f7-4fa2-84ee-b8d642f2b09b
ms.openlocfilehash: c1701b07958509e663f0ac651471e82a60120618
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723376"
---
# <a name="how-to-obtain-font-metrics"></a><span data-ttu-id="63e25-102">방법: 글꼴 메트릭 얻기</span><span class="sxs-lookup"><span data-stu-id="63e25-102">How to: Obtain Font Metrics</span></span>
<span data-ttu-id="63e25-103"><xref:System.Drawing.FontFamily> 클래스는 특정 제품군/스타일 조합에 대 한 다양 한 메트릭을 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-103">The <xref:System.Drawing.FontFamily> class provides the following methods that retrieve various metrics for a particular family/style combination:</span></span>  
  
-   <span data-ttu-id="63e25-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="63e25-104"><xref:System.Drawing.FontFamily.GetEmHeight%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="63e25-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="63e25-105"><xref:System.Drawing.FontFamily.GetCellAscent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="63e25-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="63e25-106"><xref:System.Drawing.FontFamily.GetCellDescent%2A>(FontStyle)</span></span>  
  
-   <span data-ttu-id="63e25-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span><span class="sxs-lookup"><span data-stu-id="63e25-107"><xref:System.Drawing.FontFamily.GetLineSpacing%2A>(FontStyle)</span></span>  
  
 <span data-ttu-id="63e25-108">크기 및 특정 단위의 독립 되므로 이러한 메서드에서 반환 되는 숫자를 글꼴 디자인 단위로 있는 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-108">The numbers returned by these methods are in font design units, so they are independent of the size and units of a particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="63e25-109">다음 그림에는 다양 한 메트릭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-109">The following illustration shows the various metrics.</span></span>  
  
 <span data-ttu-id="63e25-110">![글꼴 텍스트](./media/fontstext7a.png "fontstext7A")</span><span class="sxs-lookup"><span data-stu-id="63e25-110">![Fonts Text](./media/fontstext7a.png "fontstext7A")</span></span>  
  
## <a name="example"></a><span data-ttu-id="63e25-111">예제</span><span class="sxs-lookup"><span data-stu-id="63e25-111">Example</span></span>  
 <span data-ttu-id="63e25-112">다음 예제에서는 Arial 글꼴 패밀리의 일반 스타일에 대 한 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-112">The following example displays the metrics for the regular style of the Arial font family.</span></span> <span data-ttu-id="63e25-113">코드는 또한 만듭니다는 <xref:System.Drawing.Font> 16 픽셀 크기 및 표시 (픽셀 단위)는 특정 메트릭 사용 하 여 개체 (Arial 패밀리에 따라) <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-113">The code also creates a <xref:System.Drawing.Font> object (based on the Arial family) with size 16 pixels and displays the metrics (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="63e25-114">다음 그림에서는 예제 코드의 출력을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-114">The following illustration shows the output of the example code.</span></span>  
  
 <span data-ttu-id="63e25-115">![글꼴 텍스트](./media/csfontstext8.png "csFontsText8")</span><span class="sxs-lookup"><span data-stu-id="63e25-115">![Fonts Text](./media/csfontstext8.png "csFontsText8")</span></span>  
  
 <span data-ttu-id="63e25-116">앞의 그림에서 출력의 처음 두 줄을 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-116">Note the first two lines of output in the preceding illustration.</span></span> <span data-ttu-id="63e25-117"><xref:System.Drawing.Font> 개체의 크기가 16 반환 하며 <xref:System.Drawing.FontFamily> 2,048는 em 높이 반환 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-117">The <xref:System.Drawing.Font> object returns a size of 16, and the <xref:System.Drawing.FontFamily> object returns an em height of 2,048.</span></span> <span data-ttu-id="63e25-118">이러한 두 값 (16 및 2,048)는 키 글꼴 디자인 단위로 및 단위 (이 예제의 경우 픽셀)의 사이 변환로 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-118">These two numbers (16 and 2,048) are the key to converting between font design units and the units (in this case pixels) of the <xref:System.Drawing.Font> object.</span></span>  
  
 <span data-ttu-id="63e25-119">예를 들어, 변환할 수 있습니다 어센더 디자인 단위로에서 픽셀을 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-119">For example, you can convert the ascent from design units to pixels as follows:</span></span>  
  
 <span data-ttu-id="63e25-120">![글꼴 텍스트](./media/fontstext9.png "FontsText9")</span><span class="sxs-lookup"><span data-stu-id="63e25-120">![Fonts Text](./media/fontstext9.png "FontsText9")</span></span>  
  
 <span data-ttu-id="63e25-121">다음 코드는 텍스트를 세로로 배치 설정 하 여 합니다 <xref:System.Drawing.PointF.Y%2A> 의 데이터 멤버는 <xref:System.Drawing.PointF> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-121">The following code positions text vertically by setting the <xref:System.Drawing.PointF.Y%2A> data member of a <xref:System.Drawing.PointF> object.</span></span> <span data-ttu-id="63e25-122">에 대 한 y-좌표 증분됩니다 `font.Height` 각 새 텍스트 줄에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-122">The y-coordinate is increased by `font.Height` for each new line of text.</span></span> <span data-ttu-id="63e25-123">합니다 <xref:System.Drawing.Font.Height%2A> 의 속성을 <xref:System.Drawing.Font> 개체는 특정 줄 간격 (픽셀)를 반환 합니다. <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-123">The <xref:System.Drawing.Font.Height%2A> property of a <xref:System.Drawing.Font> object returns the line spacing (in pixels) for that particular <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="63e25-124">이 예제에서는 반환 되는 수 여 <xref:System.Drawing.Font.Height%2A> 은 19입니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-124">In this example, the number returned by <xref:System.Drawing.Font.Height%2A> is 19.</span></span> <span data-ttu-id="63e25-125">이 줄 간격 메트릭 픽셀로 변환 하 여 얻은 (정수로 반올림) 수와 동일 하 게 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-125">Note that this is the same as the number (rounded up to an integer) obtained by converting the line-spacing metric to pixels.</span></span>  
  
 <span data-ttu-id="63e25-126">Em 높이 (크기나 em 크기 라고도 함)는 기준선 위와의 합계가 아닙니다 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-126">Note that the em height (also called size or em size) is not the sum of the ascent and the descent.</span></span> <span data-ttu-id="63e25-127">위와 어센더 합계 셀 높이 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-127">The sum of the ascent and the descent is called the cell height.</span></span> <span data-ttu-id="63e25-128">내부 앞에 오는 빼기 셀 높이 em 높이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-128">The cell height minus the internal leading is equal to the em height.</span></span> <span data-ttu-id="63e25-129">셀 높이 외부 앞에 오는 줄 간격으로 같습니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-129">The cell height plus the external leading is equal to the line spacing.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#71](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.FontsAndText#71](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="63e25-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="63e25-130">Compiling the Code</span></span>  
 <span data-ttu-id="63e25-131">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="63e25-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e25-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="63e25-132">See also</span></span>
- [<span data-ttu-id="63e25-133">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="63e25-133">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="63e25-134">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="63e25-134">Using Fonts and Text</span></span>](using-fonts-and-text.md)
