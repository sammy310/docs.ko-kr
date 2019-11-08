---
title: WPF 앱에서 잉크 수집
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 8109e0d6a746d6ca23c25643c510014c1a1e656c
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740879"
---
# <a name="collect-ink"></a><span data-ttu-id="2e22a-102">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="2e22a-102">Collect Ink</span></span>

<span data-ttu-id="2e22a-103">[Windows Presentation Foundation](../index.md) 플랫폼은 기능의 핵심 요소로서 디지털 잉크를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="2e22a-104">이 항목에서는 Windows Presentation Foundation (WPF)에서 잉크를 수집 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2e22a-105">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="2e22a-105">Prerequisites</span></span>

<span data-ttu-id="2e22a-106">다음 예제를 사용 하려면 먼저 Visual Studio 및 Windows SDK를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="2e22a-107">WPF 용 응용 프로그램을 작성 하는 방법에 대해서도 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="2e22a-108">WPF를 시작 하는 방법에 대 한 자세한 내용은 [연습: 내 첫 wpf 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e22a-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="2e22a-109">InkCanvas 요소 사용</span><span class="sxs-lookup"><span data-stu-id="2e22a-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="2e22a-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> 요소는 WPF에서 잉크를 수집 하는 가장 쉬운 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="2e22a-111"><xref:System.Windows.Controls.InkCanvas> 요소를 사용 하 여 잉크 입력을 받고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="2e22a-112">일반적으로 스타일러스를 사용하여 잉크를 입력합니다.이 스타일러스는 디지타이저와 상호 작용하여 잉크 스트로크를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="2e22a-113">또한 스타일러스 대신 마우스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="2e22a-114">생성 된 스트로크는 <xref:System.Windows.Ink.Stroke> 개체로 표시 되 고 프로그래밍 방식으로 및 사용자 입력에 의해 조작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="2e22a-115">사용자는 <xref:System.Windows.Controls.InkCanvas>를 사용 하 여 기존 <xref:System.Windows.Ink.Stroke>를 선택, 수정 또는 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="2e22a-116">XAML을 사용 하 여 **InkCanvas** 요소를 트리에 추가 하는 것 처럼 잉크 컬렉션을 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="2e22a-117">다음 예제에서는 Visual Studio에서 만든 기본 WPF 프로젝트에 <xref:System.Windows.Controls.InkCanvas>를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="2e22a-118">**InkCanvas** 요소는 자식 요소를 포함할 수도 있으므로 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="2e22a-119">예를 들어 텍스트 요소에 잉크 기능을 추가 하려면 단순히 <xref:System.Windows.Controls.InkCanvas>의 자식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="2e22a-120">잉크를 사용 하 여 이미지를 표시 하기 위한 지원을 추가 하는 것은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="2e22a-121">InkCollection 모드</span><span class="sxs-lookup"><span data-stu-id="2e22a-121">InkCollection Modes</span></span>

<span data-ttu-id="2e22a-122"><xref:System.Windows.Controls.InkCanvas>은 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성을 통해 다양 한 입력 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="2e22a-123">잉크 조작</span><span class="sxs-lookup"><span data-stu-id="2e22a-123">Manipulate Ink</span></span>

<span data-ttu-id="2e22a-124"><xref:System.Windows.Controls.InkCanvas>에서는 많은 잉크 편집 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="2e22a-125">예를 들어 <xref:System.Windows.Controls.InkCanvas>는 펜 후면 지우기를 지원 하 고 요소에 기능을 추가 하는 데 필요한 추가 코드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="2e22a-126">선택 항목</span><span class="sxs-lookup"><span data-stu-id="2e22a-126">Selection</span></span>

<span data-ttu-id="2e22a-127">선택 모드를 설정 하는 것은 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **Select**로 설정 하는 것 만큼 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="2e22a-128">다음 코드는 <xref:System.Windows.Forms.CheckBox>값에 따라 편집 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="2e22a-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="2e22a-129">DrawingAttributes</span></span>

<span data-ttu-id="2e22a-130"><xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 속성을 사용 하 여 잉크 스트로크의 모양을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="2e22a-131">예를 들어 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> <xref:System.Windows.Ink.DrawingAttributes>의 멤버는 렌더링 된 <xref:System.Windows.Ink.Stroke>의 색을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="2e22a-132">다음 예제에서는 선택 된 스트로크의 색을 빨강으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="2e22a-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="2e22a-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="2e22a-134"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성은 <xref:System.Windows.Controls.InkCanvas>에서 만들 스트로크의 높이, 너비 및 색과 같은 속성에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="2e22a-135"><xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 변경한 후에는 <xref:System.Windows.Controls.InkCanvas>에 입력 된 모든 이후 스트로크가 새 속성 값으로 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="2e22a-136">코드 숨김이 파일의 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>를 수정 하는 것 외에도 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성을 지정 하는 데 XAML 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="2e22a-137">다음 예제에서는 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성을 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="2e22a-138">이 코드를 사용 하려면 Visual Studio에서 "HelloInkCanvas" 이라는 새 WPF 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="2e22a-139">*Mainwindow.xaml* 파일의 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="2e22a-140">다음으로, Mainwindow.xaml 클래스 내의 코드 뒤에 다음 단추 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="2e22a-141">이 코드를 복사한 후 Visual Studio에서 **f5** 키를 눌러 디버거에서 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="2e22a-142"><xref:System.Windows.Controls.StackPanel> <xref:System.Windows.Controls.InkCanvas>위에 단추를 배치 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="2e22a-143">단추 위쪽에서 잉크를 시도 하는 경우 <xref:System.Windows.Controls.InkCanvas>은 단추 뒤에 잉크를 수집 하 고 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="2e22a-144">이는 단추가 자식이 아닌 <xref:System.Windows.Controls.InkCanvas>의 형제 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="2e22a-145">또한 단추가 z 순서에서 더 앞서기 때문에 잉크가 단추 뒤에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e22a-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e22a-146">참조</span><span class="sxs-lookup"><span data-stu-id="2e22a-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
