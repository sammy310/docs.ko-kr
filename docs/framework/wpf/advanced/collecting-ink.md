---
title: WPF 앱에서 잉크를 수집 합니다.
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
ms.openlocfilehash: 0d0796eae469f8a40e01e3de02c00149eb3f00c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051275"
---
# <a name="collect-ink"></a><span data-ttu-id="5d70e-102">잉크 수집</span><span class="sxs-lookup"><span data-stu-id="5d70e-102">Collect Ink</span></span>

<span data-ttu-id="5d70e-103">[Windows Presentation Foundation](../index.md) 플랫폼은 기능의 핵심 요소로서 디지털 잉크를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="5d70e-104">이 항목에서는 Windows Presentation Foundation (WPF)에서 잉크를 수집 하기 위한 메서드를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5d70e-105">전제 조건</span><span class="sxs-lookup"><span data-stu-id="5d70e-105">Prerequisites</span></span>

<span data-ttu-id="5d70e-106">다음 예제를 사용 하려면 먼저 설치 해야 Visual Studio 및 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="5d70e-107">WPF에 대 한 응용 프로그램을 작성 하는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="5d70e-108">WPF를 사용 하 여 시작 하는 방법에 대 한 자세한 내용은 참조 하세요. [연습: 내 첫 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="5d70e-109">InkCanvas 요소 사용</span><span class="sxs-lookup"><span data-stu-id="5d70e-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="5d70e-110"><xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> WPF에서 잉크를 수집 하는 가장 쉬운 방법은 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="5d70e-111">사용 하 여는 <xref:System.Windows.Controls.InkCanvas> 받고 잉크 입력을 표시 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="5d70e-112">일반적으로 스타일러스를 사용하여 잉크를 입력합니다.이 스타일러스는 디지타이저와 상호 작용하여 잉크 스트로크를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="5d70e-113">또한 스타일러스 대신 마우스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="5d70e-114">생성된 된 스트로크 표현 <xref:System.Windows.Ink.Stroke> , 이러한 개체를 프로그래밍 방식으로 및 사용자가 입력 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="5d70e-115">합니다 <xref:System.Windows.Controls.InkCanvas> 선택, 수정 또는 기존 삭제 하면 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5d70e-116">XAML을 사용 하 여 설정할 수 있습니다 잉크 컬렉션을 추가 하는 것 처럼 쉽게를 **InkCanvas** 트리에 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="5d70e-117">다음 예제에서는 추가 <xref:System.Windows.Controls.InkCanvas> Visual Studio에서 만든 기본 WPF 프로젝트에:</span><span class="sxs-lookup"><span data-stu-id="5d70e-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="5d70e-118">합니다 **InkCanvas** 요소는 거의 모든 형식의 XAML 요소에 잉크 주석 기능을 추가할 수 있도록 자식 요소를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="5d70e-119">예를 들어 텍스트 요소에 잉크 입력 기능을 추가 하려면 단순히 있도록 자식은 <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="5d70e-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="5d70e-120">잉크로 이미지를 표시 하기 위한 지원을 추가 하는 것은 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="5d70e-121">InkCollection 모드</span><span class="sxs-lookup"><span data-stu-id="5d70e-121">InkCollection Modes</span></span>

<span data-ttu-id="5d70e-122">합니다 <xref:System.Windows.Controls.InkCanvas> 모드를 통해 다양 한 입력에 대 한 지원을 제공 해당 <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="5d70e-123">잉크 조작</span><span class="sxs-lookup"><span data-stu-id="5d70e-123">Manipulate Ink</span></span>

<span data-ttu-id="5d70e-124"><xref:System.Windows.Controls.InkCanvas> 많은 잉크 편집 작업에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="5d70e-125">예를 들어 <xref:System.Windows.Controls.InkCanvas> 지원 펜 뒤쪽 지우기 및 요소에 기능을 추가 하려면 추가 코드 없이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="5d70e-126">선택</span><span class="sxs-lookup"><span data-stu-id="5d70e-126">Selection</span></span>

<span data-ttu-id="5d70e-127">선택 모드 설정 간단 하 게 설정 합니다 <xref:System.Windows.Controls.InkCanvasEditingMode> 속성을 **선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="5d70e-128">값에 따라 편집 모드를 설정 하는 다음 코드는 <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="5d70e-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="5d70e-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5d70e-129">DrawingAttributes</span></span>

<span data-ttu-id="5d70e-130">사용 된 <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> 잉크 스트로크의 모양을 변경 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="5d70e-131">예를 들어 합니다 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 소속 <xref:System.Windows.Ink.DrawingAttributes> 렌더링 된 색으로 설정 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="5d70e-132">다음 예제에서는 빨간색 선택한 스트로크의 색을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="5d70e-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="5d70e-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="5d70e-134">합니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 높이, 너비 및에서 만들 스트로크의 색 같은 속성에 대 한 액세스를 제공 하는 속성을 <xref:System.Windows.Controls.InkCanvas>입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5d70e-135">변경 하면 합니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, 이후 모든 스트로크를 입력 합니다 <xref:System.Windows.Controls.InkCanvas> 새 속성 값을 사용 하 여 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="5d70e-136">수정 하는 것 외에도 합니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 코드 숨김 파일에 XAML 구문을 지정 하는 데 사용할 수 있습니다 <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="5d70e-137">다음 예제에서는 설정 하는 방법에 설명 합니다 <xref:System.Windows.Ink.DrawingAttributes.Color%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="5d70e-138">이 코드를 사용 하려면 Visual Studio에서 "helloinkcanvas" 새 WPF 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="5d70e-139">코드를 대체 합니다 *MainWindow.xaml* 를 다음 코드로 파일:</span><span class="sxs-lookup"><span data-stu-id="5d70e-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="5d70e-140">MainWindow 클래스 내에서 파일의 코드를 다음에 다음 단추 이벤트 처리기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="5d70e-141">이 코드를 복사한 후 눌러 **F5** 디버거에서 프로그램을 실행 하려면 Visual Studio에서.</span><span class="sxs-lookup"><span data-stu-id="5d70e-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="5d70e-142">표시 하는 방법을 <xref:System.Windows.Controls.StackPanel> 위쪽에 단추를 배치 합니다 <xref:System.Windows.Controls.InkCanvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="5d70e-143">단추 위에 잉크로 채우려고 시도 합니다 <xref:System.Windows.Controls.InkCanvas> 수집 하 고 단추 뒤에서 잉크를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="5d70e-144">단추의 형제 이기 때문에 이것이 <xref:System.Windows.Controls.InkCanvas> 자식이 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="5d70e-145">또한 단추가 z 순서에서 더 앞서기 때문에 잉크가 단추 뒤에서 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d70e-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d70e-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d70e-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>