---
title: 자동 레이아웃 사용 개요
ms.date: 03/30/2017
helpviewer_keywords:
- layout [WPF], automatic
- automatic layout [WPF]
ms.assetid: 6fed9264-18bb-4d05-8867-1fe356c6f687
ms.openlocfilehash: 2fe473da3eeabef3852e3003e61b3b9604332855
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291263"
---
# <a name="use-automatic-layout-overview"></a><span data-ttu-id="26cca-102">자동 레이아웃 사용 개요</span><span class="sxs-lookup"><span data-stu-id="26cca-102">Use Automatic Layout Overview</span></span>

<span data-ttu-id="26cca-103">이 항목에서는 지역화할 수 있는 Ui (사용자 인터페이스)로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 작성 하는 방법에 대 한 개발자를 위한 지침을 제공 합니다</span><span class="sxs-lookup"><span data-stu-id="26cca-103">This topic introduces guidelines for developers on how to write [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] applications with localizable user interfaces (UIs).</span></span> <span data-ttu-id="26cca-104">과거에는 UI를 지역화할 때 시간이 오래 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-104">In the past, localization of a UI was a time consuming process.</span></span> <span data-ttu-id="26cca-105">UI에 맞게 조정 된 각 언어 마다 픽셀 조정을 통해 픽셀을 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-105">Each language that the UI was adapted for required a pixel by pixel adjustment.</span></span> <span data-ttu-id="26cca-106">오늘날 올바른 디자인 및 올바른 코딩 표준을 사용 하 여 지역화 담당자가 크기 조정 하 고 위치를 조정할 수 있도록 Ui를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-106">Today with the right design and right coding standards, UIs can be constructed so that localizers have less resizing and repositioning to do.</span></span> <span data-ttu-id="26cca-107">보다 쉽게 크기를 조정 하 고 위치를 변경할 수 있는 응용 프로그램을 작성 하는 방법은 자동 레이아웃 이라고 하며, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 디자인을 사용 하 여 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-107">The approach to writing applications that can be more easily resized and repositioned is called automatic layout, and can be achieved by using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application design.</span></span>

<a name="advantages_of_autolayout"></a>

## <a name="advantages-of-using-automatic-layout"></a><span data-ttu-id="26cca-108">자동 레이아웃 사용의 이점</span><span class="sxs-lookup"><span data-stu-id="26cca-108">Advantages of Using Automatic Layout</span></span>

<span data-ttu-id="26cca-109">@No__t-0 프레젠테이션 시스템은 강력 하 고 유연 하므로 다양 한 언어의 요구 사항에 맞게 조정할 수 있는 응용 프로그램의 요소를 레이아웃 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-109">Because the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presentation system is powerful and flexible, it provides the ability to layout elements in an application that can be adjusted to fit the requirements of different languages.</span></span> <span data-ttu-id="26cca-110">다음 목록에서는 자동 레이아웃의 몇 가지 이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-110">The following list points out some of the advantages of automatic layout.</span></span>

- <span data-ttu-id="26cca-111">UI는 모든 언어에서 잘 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-111">UI displays well  in any language.</span></span>

- <span data-ttu-id="26cca-112">텍스트가 변환된 후 컨트롤의 위치 및 크기를 다시 조정할 필요가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-112">Reduces the need to readjust position and size of controls after text is translated.</span></span>

- <span data-ttu-id="26cca-113">창 크기를 다시 조정할 필요가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-113">Reduces the need to readjust window size.</span></span>

- <span data-ttu-id="26cca-114">UI 레이아웃은 모든 언어로 적절히 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-114">UI layout renders properly in any language.</span></span>

- <span data-ttu-id="26cca-115">지역화를 문자열 변환 정도의 수준으로 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-115">Localization can be reduced to the point that it is little more than string translation.</span></span>

<a name="autolayout_controls"></a>

## <a name="automatic-layout-and-controls"></a><span data-ttu-id="26cca-116">자동 레이아웃 및 컨트롤</span><span class="sxs-lookup"><span data-stu-id="26cca-116">Automatic Layout and Controls</span></span>

<span data-ttu-id="26cca-117">자동 레이아웃을 사용하면 애플리케이션에서 컨트롤의 크기를 자동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-117">Automatic layout enables an application to adjust the size of a control automatically.</span></span> <span data-ttu-id="26cca-118">예를 들어 컨트롤이 문자열의 길이 맞게 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-118">For example, a control can change to accommodate the length of a string.</span></span> <span data-ttu-id="26cca-119">이 기능을 통해 로컬라이저는 문자열을 변환할 수 있으며, 더 이상 변환된 텍스트에 맞게 컨트롤의 크기를 조정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-119">This capability enables  localizers to translate the string; they no longer need to resize the control to fit the translated text.</span></span> <span data-ttu-id="26cca-120">다음 예제에서는 영어 콘텐츠가 있는 단추를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-120">The following example creates a button with English content.</span></span>

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]

<span data-ttu-id="26cca-121">이 예제에서 스페인어 단추를 만들려면 텍스트만 변경하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-121">In the example, all you have to do to make a Spanish button is change the text.</span></span> <span data-ttu-id="26cca-122">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-122">For example,</span></span>

[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]

<span data-ttu-id="26cca-123">다음 그림은 코드 샘플의 출력을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-123">The following graphic shows the output of the code samples:</span></span>

![텍스트가 여러 언어로 표시되는 동일한 단추](./media/use-automatic-layout-overview/auto-resizable-button.png)

<a name="autolayout_coding"></a>

## <a name="automatic-layout-and-coding-standards"></a><span data-ttu-id="26cca-125">자동 레이아웃 및 코딩 표준</span><span class="sxs-lookup"><span data-stu-id="26cca-125">Automatic Layout and Coding Standards</span></span>

<span data-ttu-id="26cca-126">자동 레이아웃 방법을 사용 하려면 코딩 및 디자인 표준 및 규칙 집합을 사용 하 여 완전히 지역화 가능한 UI를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-126">Using the automatic layout approach requires a set of coding and design standards and rules to produce a fully localizable UI.</span></span> <span data-ttu-id="26cca-127">다음은 자동 레이아웃 코딩에 도움이 되는 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-127">The following guidelines will aid your automatic layout coding.</span></span>

<span data-ttu-id="26cca-128">**절대 위치 사용 안 함**</span><span class="sxs-lookup"><span data-stu-id="26cca-128">**Do not use absolute positions**</span></span>

- <span data-ttu-id="26cca-129">요소를 절대적으로 배치 하므로 <xref:System.Windows.Controls.Canvas>을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="26cca-129">Do not use <xref:System.Windows.Controls.Canvas> because it positions elements absolutely.</span></span>

- <span data-ttu-id="26cca-130">@No__t-0, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Grid>를 사용 하 여 컨트롤을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-130">Use <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.StackPanel>, and <xref:System.Windows.Controls.Grid> to position controls.</span></span>

<span data-ttu-id="26cca-131">다양 한 패널 형식에 대 한 자세한 내용은 [패널 개요](../controls/panels-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26cca-131">For a discussion about various types of panels, see [Panels Overview](../controls/panels-overview.md).</span></span>

<span data-ttu-id="26cca-132">**창에 고정 크기를 설정 하지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="26cca-132">**Do not set a fixed size for a window**</span></span>

- <span data-ttu-id="26cca-133">대신 <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>를</span><span class="sxs-lookup"><span data-stu-id="26cca-133">Use <xref:System.Windows.Window.SizeToContent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="26cca-134">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-134">For example:</span></span>

  [!code-xaml[LocalizationGrid#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#2)]

<span data-ttu-id="26cca-135">**@No__t 추가-1**</span><span class="sxs-lookup"><span data-stu-id="26cca-135">**Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A>**</span></span>

- <span data-ttu-id="26cca-136">응용 프로그램의 루트 요소에 <xref:System.Windows.FrameworkElement.FlowDirection%2A>을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-136">Add a <xref:System.Windows.FrameworkElement.FlowDirection%2A> to the root element of your application.</span></span>

  <span data-ttu-id="26cca-137">WPF는 가로, 양방향 및 세로 레이아웃을 지 원하는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-137">WPF provides a convenient way to support horizontal, bidirectional, and vertical layouts.</span></span> <span data-ttu-id="26cca-138">프레젠테이션 프레임 워크에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성은 레이아웃을 정의 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-138">In presentation framework, the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property can be used to define layout.</span></span> <span data-ttu-id="26cca-139">흐름 방향 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-139">The flow-direction patterns are:</span></span>

  - <span data-ttu-id="26cca-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb)-라틴어, 동아시아 등의 가로 레이아웃.</span><span class="sxs-lookup"><span data-stu-id="26cca-140"><xref:System.Windows.FlowDirection.LeftToRight?displayProperty=nameWithType> (LrTb) — horizontal layout for Latin, East Asian, and so forth.</span></span>

  - <span data-ttu-id="26cca-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb)-아랍어, 히브리어 등의 경우 양방향입니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-141"><xref:System.Windows.FlowDirection.RightToLeft?displayProperty=nameWithType> (RlTb) — bidirectional for Arabic, Hebrew, and so forth.</span></span>

<span data-ttu-id="26cca-142">**실제 글꼴 대신 복합 글꼴 사용**</span><span class="sxs-lookup"><span data-stu-id="26cca-142">**Use composite fonts instead of physical fonts**</span></span>

- <span data-ttu-id="26cca-143">복합 글꼴을 사용 하는 경우 <xref:System.Windows.Controls.Control.FontFamily%2A> 속성을 지역화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-143">With composite fonts, the <xref:System.Windows.Controls.Control.FontFamily%2A> property does not need to be localized.</span></span>

- <span data-ttu-id="26cca-144">개발자는 다음 글꼴 중 하나를 사용하거나 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-144">Developers can use one of the following fonts or create their own.</span></span>

  - <span data-ttu-id="26cca-145">전역 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="26cca-145">Global User Interface</span></span>
  - <span data-ttu-id="26cca-146">전역 San Serif</span><span class="sxs-lookup"><span data-stu-id="26cca-146">Global San Serif</span></span>
  - <span data-ttu-id="26cca-147">전역 Serif</span><span class="sxs-lookup"><span data-stu-id="26cca-147">Global Serif</span></span>

<span data-ttu-id="26cca-148">**Xml 추가: lang**</span><span class="sxs-lookup"><span data-stu-id="26cca-148">**Add xml:lang**</span></span>

- <span data-ttu-id="26cca-149">UI의 루트 요소에 `xml:lang` 특성을 추가 합니다 (예: 영어 응용 프로그램의 경우 `xml:lang="en-US"`).</span><span class="sxs-lookup"><span data-stu-id="26cca-149">Add the `xml:lang` attribute in the root element of your UI, such as `xml:lang="en-US"` for an English application.</span></span>

- <span data-ttu-id="26cca-150">합성 글꼴은 `xml:lang`을 사용 하 여 사용할 글꼴을 결정 하므로 다국어 시나리오를 지원 하도록이 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-150">Because composite fonts use `xml:lang` to determine what font to use, set this property to support multilingual scenarios.</span></span>

<a name="autolay_grids"></a>

## <a name="automatic-layout-and-grids"></a><span data-ttu-id="26cca-151">자동 레이아웃 및 그리드</span><span class="sxs-lookup"><span data-stu-id="26cca-151">Automatic Layout and Grids</span></span>

<span data-ttu-id="26cca-152">@No__t-0 요소는 개발자가 요소를 배치할 수 있도록 자동 레이아웃에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-152">The <xref:System.Windows.Controls.Grid> element, is useful for automatic layout because it enables a developer to position elements.</span></span> <span data-ttu-id="26cca-153">@No__t-0 컨트롤은 열 및 행 정렬을 사용 하 여 사용 가능한 공간을 자식 요소 간에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-153">A <xref:System.Windows.Controls.Grid> control is capable of distributing the available space among its child elements, using a column and row arrangement.</span></span> <span data-ttu-id="26cca-154">UI 요소는 여러 셀에 걸쳐 있을 수 있으며 그리드 내에 표가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-154">The UI elements can span multiple cells, and it is possible to have grids within grids.</span></span> <span data-ttu-id="26cca-155">표를 사용 하면 복잡 한 UI를 만들고 배치할 수 있으므로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-155">Grids are useful because they enable you to create and position complex UI.</span></span> <span data-ttu-id="26cca-156">다음 예제에서는 그리드를 사용하여 몇 가지 단추 및 텍스트 위치를 지정하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-156">The following example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="26cca-157">셀의 높이와 너비가 <xref:System.Windows.GridUnitType.Auto>으로 설정 되어 있는지 확인 합니다. 따라서 이미지가 포함 된 단추가 포함 된 셀은 이미지에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-157">Notice that the height and width of the cells are set to <xref:System.Windows.GridUnitType.Auto>; therefore, the cell that contains the button with an image adjusts to fit the image.</span></span>

[!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]

<span data-ttu-id="26cca-158">다음 그래픽에서는 이전 코드로 생성된 그리드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-158">The following graphic shows the grid produced by the previous code.</span></span>

<span data-ttu-id="26cca-159">![표 형태 예](./media/glob-grid.png "glob_grid") grid</span><span class="sxs-lookup"><span data-stu-id="26cca-159">![Grid example](./media/glob-grid.png "glob_grid") Grid</span></span>

<a name="autolay_grids_issharedsizescope"></a>

## <a name="automatic-layout-and-grids-using-the-issharedsizescope-property"></a><span data-ttu-id="26cca-160">IsSharedSizeScope 속성을 사용하는 자동 레이아웃 및 그리드</span><span class="sxs-lookup"><span data-stu-id="26cca-160">Automatic Layout and Grids Using the IsSharedSizeScope Property</span></span>

<span data-ttu-id="26cca-161">@No__t-0 요소는 지역화할 수 있는 응용 프로그램에서 내용에 맞게 조정 되는 컨트롤을 만드는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-161">A <xref:System.Windows.Controls.Grid> element is useful in localizable applications to create controls that adjust to fit content.</span></span> <span data-ttu-id="26cca-162">그러나 경우에 따라 콘텐츠에 관계없이 컨트롤을 특정 크기로 유지하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-162">However, at times you want controls to maintain a particular size regardless of content.</span></span> <span data-ttu-id="26cca-163">예를 들어 "확인", "취소" 및 "찾아보기" 단추가 있는 경우 콘텐츠에 맞게 단추 크기를 조정하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-163">For example, if you have "OK", "Cancel" and "Browse" buttons you probably do not want the buttons sized to fit the content.</span></span> <span data-ttu-id="26cca-164">이 경우 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType>에 연결 된 속성은 여러 grid 요소에서 동일한 크기 조정을 공유 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-164">In this case the <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A?displayProperty=nameWithType> attached property is useful for sharing the same sizing among multiple grid elements.</span></span> <span data-ttu-id="26cca-165">다음 예에서는 여러 <xref:System.Windows.Controls.Grid> 요소 사이에서 열 및 행 크기 조정 데이터를 공유 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="26cca-165">The following example demonstrates how to share column and row sizing data between multiple <xref:System.Windows.Controls.Grid> elements.</span></span>

[!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]

> [!NOTE]
> <span data-ttu-id="26cca-166">전체 코드 샘플을 보려면 [모눈 간 크기 조정 속성 공유](../controls/how-to-share-sizing-properties-between-grids.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26cca-166">For the complete code sample, see [Share Sizing Properties Between Grids](../controls/how-to-share-sizing-properties-between-grids.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="26cca-167">참조</span><span class="sxs-lookup"><span data-stu-id="26cca-167">See also</span></span>

- [<span data-ttu-id="26cca-168">WPF의 전역화</span><span class="sxs-lookup"><span data-stu-id="26cca-168">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="26cca-169">자동 레이아웃을 사용하여 단추 만들기</span><span class="sxs-lookup"><span data-stu-id="26cca-169">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
- [<span data-ttu-id="26cca-170">자동 레이아웃에 그리드 사용</span><span class="sxs-lookup"><span data-stu-id="26cca-170">Use a Grid for Automatic Layout</span></span>](how-to-use-a-grid-for-automatic-layout.md)
