---
title: 글꼴 및 텍스트 사용
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505115"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="02290-102">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="02290-102">Using Fonts and Text</span></span>
<span data-ttu-id="02290-103">Windows Forms에서 텍스트를 그리기 위한 GDI 및 GDI +에서 제공 하는 몇 가지 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02290-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="02290-104">GDI + <xref:System.Drawing.Graphics> 클래스에 여러 개의 <xref:System.Drawing.Graphics.DrawString%2A> 텍스트, 위치, 경계 사각형, 글꼴 및 형식 등의 다양 한 기능을 지정할 수 있도록 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="02290-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="02290-105">그릴 텍스트를 사용 하는 정적 GDI를 사용 하 여 측정 하는 또한 <xref:System.Windows.Forms.TextRenderer.DrawText%2A> 하 고 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> 에서 제공 하는 메서드를 `TextRenderer` 클래스.</span><span class="sxs-lookup"><span data-stu-id="02290-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="02290-106">GDI 메서드는 위치, 글꼴 및 서식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02290-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="02290-107">텍스트 렌더링;에 대 한 GDI 또는 GDI +를 선택할 수 있습니다. 그러나 GDI 더 나은 성능과 더 정확 하 게 텍스트 측정에 일반적으로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="02290-108">텍스트 렌더링에 영향을 주는 다른 클래스를 포함 `FontFamily`, `Font`를 <xref:System.Drawing.StringFormat>, 및 `TextFormatFlags`합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02290-109">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="02290-109">In This Section</span></span>  
 [<span data-ttu-id="02290-110">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="02290-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="02290-111">만드는 방법을 보여 줍니다 `Font` 고 `FontFamily` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="02290-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="02290-112">방법: 지정된 된 위치에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="02290-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="02290-113">GDI 및 GDI +를 사용 하 여 특정 위치에 텍스트를 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="02290-114">방법: 사각형 안에 줄 바꿈된 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="02290-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="02290-115">GDI 및 GDI +를 사용 하 여 사각형에서 텍스트를 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="02290-116">방법: GDI 사용 하 여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="02290-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="02290-117">텍스트를 그리기 위한 GDI를 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="02290-118">방법: 그린된 텍스트 맞추기</span><span class="sxs-lookup"><span data-stu-id="02290-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="02290-119">GDI 및 GDI +의 텍스트 서식을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02290-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="02290-120">방법: 세로 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="02290-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="02290-121">GDI +를 사용 하 여 세로로 정렬 된 텍스트를 그리는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="02290-122">방법: 그린된 텍스트에 탭 정지 설정</span><span class="sxs-lookup"><span data-stu-id="02290-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="02290-123">그리는 GDI +를 사용 하 여 탭 정지를 사용 하 여 텍스트 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02290-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="02290-124">방법: 설치 된 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="02290-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="02290-125">설치 된 글꼴의 이름을 나열 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="02290-126">방법: 개인 글꼴 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="02290-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="02290-127">만드는 방법에 설명 된 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="02290-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="02290-128">방법: 글꼴 메트릭 얻기</span><span class="sxs-lookup"><span data-stu-id="02290-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="02290-129">셀 상승을 등 하강 글꼴 메트릭을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02290-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="02290-130">방법: 텍스트에 앤티 앨리어싱 사용</span><span class="sxs-lookup"><span data-stu-id="02290-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="02290-131">텍스트를 그릴 때 앤티 앨리어싱을 사용 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="02290-132">참조</span><span class="sxs-lookup"><span data-stu-id="02290-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="02290-133">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="02290-134">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="02290-135">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="02290-136">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="02290-137">이 클래스를 설명 하 고 모든 해당 멤버에 대 한 링크를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="02290-137">Describes this class and contains links to all of its members.</span></span>
