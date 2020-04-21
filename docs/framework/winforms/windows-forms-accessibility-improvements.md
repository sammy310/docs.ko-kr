---
title: Windows 양식 접근성 개선 사항
description: .NET 코어 Windows Forms에서 .NET 프레임워크 Windows 양식과 비교하여 접근성을 향상시키려는 방법에 대해 알아봅니다.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 30eb8b3bd0aaf646ea23f4f036e822f9bba78dc4
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739765"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a><span data-ttu-id="725d5-103">.NET 코어 3.0에 대한 Windows 양식 컨트롤의 접근성 향상</span><span class="sxs-lookup"><span data-stu-id="725d5-103">Accessibility improvements in Windows Forms controls for .NET Core 3.0</span></span>

<span data-ttu-id="725d5-104">Windows Forms는 Windows Forms 고객을 더 잘 지원하기 위해 내게 필요한 옵션 기술과 함께 작동하는 방식을 지속적으로 개선하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-104">Windows Forms is continuing to improve how it works with accessibility technologies to better support Windows Forms customers.</span></span> <span data-ttu-id="725d5-105">개선 사항에는 다음과 같은 변경 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-105">These improvements include the following changes:</span></span>

- <span data-ttu-id="725d5-106">내레이터를 포함하여 내게 필요한 옵션 클라이언트 응용 프로그램과의 다양한 상호 작용 영역의 변경</span><span class="sxs-lookup"><span data-stu-id="725d5-106">Changes in various areas of interaction with accessibility client applications, including Narrator.</span></span>
- <span data-ttu-id="725d5-107">액세스 가능한 계층 구조의 변경 내용(UI Automation 트리를 통한 탐색 개선).</span><span class="sxs-lookup"><span data-stu-id="725d5-107">Changes in the Accessible hierarchy (improving navigation through the UI Automation tree).</span></span>
- <span data-ttu-id="725d5-108">키보드 탐색의 변경 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-108">Changes in keyboard navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="725d5-109">.NET Framework 4.7.1에서 .NET Framework 4.8을 통해 변경한 액세스 가능 변경 사항은 .NET Core 3.0 이상에 포함되며 기본적으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-109">Accessibility changes made in .NET Framework 4.7.1 through .NET Framework 4.8 are included in .NET Core 3.0 and above, and are enabled by default.</span></span> <span data-ttu-id="725d5-110">.NET Framework는 응용 프로그램이 새 내게 필요한 옵션 동작을 옵트아웃할 수 있도록 하는 호환성 스위치를 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-110">The .NET Framework supported compatibility switches that allowed applications to opt out of the new accessibility behavior.</span></span> <span data-ttu-id="725d5-111">반면 .NET Core는 이러한 설정을 지원하지 않으며 응용 프로그램이 내게 필요한 옵션 동작을 옵트아웃할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-111">On the other hand, .NET Core doesn't support these settings and doesn't allow applications to opt out of accessibility behavior.</span></span>
  
<span data-ttu-id="725d5-112">.NET Core 3.0부터 Windows Forms 응용 프로그램은 추가 구성 없이 모든 새로운 내게 필요한 옵션 기능(.NET Framework 4.7.1 - 4.8에 도입)의 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-112">Starting with .NET Core 3.0, Windows Forms applications benefit from all the new accessibility features (introduced in .NET Framework 4.7.1 - 4.8) without additional configuration.</span></span>

## <a name="listbox-accessibility-support"></a><span data-ttu-id="725d5-113">리스트박스 접근성 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-113">ListBox Accessibility support</span></span>

<span data-ttu-id="725d5-114">컨트롤에는 다음 변경 <xref:System.Windows.Forms.ListBox> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-114">The following changes apply to the <xref:System.Windows.Forms.ListBox> control:</span></span>

- <span data-ttu-id="725d5-115">제어를 위한 `ListBox` UI 자동화 지원 지원.</span><span class="sxs-lookup"><span data-stu-id="725d5-115">Enabled UI Automation support for `ListBox` control.</span></span>
- <span data-ttu-id="725d5-116">항목에 추가하고 `ListBox` <xref:System.Windows.Automation.ScrollItemPattern> 항목을 통해 접근성 이벤트 올리기 및 처리 및 내레이터 탐색을 향상시켜 접근성 지원을 개선했습니다(캡 잠금 탐색이 올바르지 않으며 의도치 않게 컨트롤 외부로 탐색을 던지지 않습니다). `ListBox`</span><span class="sxs-lookup"><span data-stu-id="725d5-116">Improved `ListBox` accessibility support by adding the <xref:System.Windows.Automation.ScrollItemPattern> to `ListBox` items and by enhancing the accessibility event raising and handling and Narrator navigation through the items (caps lock navigation isn't correct and doesn't throw the navigation outside the control unintentionally).</span></span>

## <a name="checkedlistbox-accessibility-support"></a><span data-ttu-id="725d5-117">선택 목록상자 접근성 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-117">CheckedListBox Accessibility support</span></span>

<span data-ttu-id="725d5-118">컨트롤에는 다음 변경 <xref:System.Windows.Forms.CheckedListBox> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-118">The following changes apply to the <xref:System.Windows.Forms.CheckedListBox> control:</span></span>

- <span data-ttu-id="725d5-119">항목에 `CheckedListBox` 대한 내게 필요한 옵션 속성에서 제공하는 수정된 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-119">Corrected `CheckedListBox` Bounds provided by accessibility properties for entries.</span></span>
- <span data-ttu-id="725d5-120">전반적인 `ListBox` `CheckedListBox` 및 접근성 개선: 속성 값 및 이벤트 모델 수정.</span><span class="sxs-lookup"><span data-stu-id="725d5-120">Improved overall `ListBox` and `CheckedListBox` accessibility: corrected property values and event model.</span></span>

## <a name="combobox-accessibility-support"></a><span data-ttu-id="725d5-121">콤보박스 접근성 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-121">ComboBox Accessibility support</span></span>

<span data-ttu-id="725d5-122">컨트롤에는 다음 변경 <xref:System.Windows.Forms.ComboBox> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-122">The following changes apply to the <xref:System.Windows.Forms.ComboBox> control:</span></span>

- <span data-ttu-id="725d5-123">함수가 재정의될 경우 안전하지 않을 수 있는 항목에서 해시 코드를 가져오는 대신 항목에 대한 암호를 생성할 수 있도록 항목의 접근성 개체를 가져오는 `ComboBox` 프로세스를 <xref:System.Object.GetHashCode%2A> 업데이트했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-123">Updated the process of getting `ComboBox` items' accessibility objects to enable generating IDs for items instead of getting hash codes from items, which may be unsafe in case the <xref:System.Object.GetHashCode%2A> function is overridden.</span></span>

## <a name="datagridview-accessibility-support"></a><span data-ttu-id="725d5-124">데이터그리드뷰 접근성 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-124">DataGridView Accessibility support</span></span>

<span data-ttu-id="725d5-125">컨트롤에는 다음 변경 <xref:System.Windows.Forms.DataGridView> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-125">The following changes apply to the <xref:System.Windows.Forms.DataGridView> control:</span></span>

- <span data-ttu-id="725d5-126">열, `DataGridView.Bounds` 행, 셀 및 해당 헤더에 대한 내게 필요한 옵션 속성에서 제공하는 수정, 경계 사각형 계산의 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="725d5-126">Corrected `DataGridView.Bounds` provided by accessibility properties for columns, rows, cells and corresponding headers, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="725d5-127">모든 접근성 경계는 뷰포트와 함께 전체 컨트롤의 경계를 고려하여 올바르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-127">All accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="725d5-128">액세스 `Value.IsReadOnly` 가능한 클라이언트 응용 프로그램에 대해 제공하는 속성 값을 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-128">Corrected `Value.IsReadOnly` property value providing for accessible client applications.</span></span> <span data-ttu-id="725d5-129">이제 속성에 `IsReadOnly` 셀에 대 한 올바른 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-129">The property now shows correct `IsReadOnly` status for cells.</span></span>
- <span data-ttu-id="725d5-130">첫 번째 <xref:System.Windows.Forms.DataGridView.CellParsing> 셀 변경에 대한 이벤트 발생 문제를 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-130">Fixed the issue with <xref:System.Windows.Forms.DataGridView.CellParsing> event raising for the first cell change.</span></span> <span data-ttu-id="725d5-131">셀 값은 제1 `DataGridView` 대조군 상호작용을 포함하는 어떠한 문제도 없이 변경될 수 있다.</span><span class="sxs-lookup"><span data-stu-id="725d5-131">Cell value can be changed without any issues including the first `DataGridView` control interaction.</span></span>
- <span data-ttu-id="725d5-132">Windows `DataGridView` 고대비 테마를 사용할 때 배경 색 대비가 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-132">Improved `DataGridView` background color contrast when using Windows High Contrast themes.</span></span> <span data-ttu-id="725d5-133">HC#1, HC#2 및 HC 검정 테마를 사용할 때 기본 백 색상을 변경했습니다. `DataGridView`</span><span class="sxs-lookup"><span data-stu-id="725d5-133">Changed `DataGridView` default back color when using HC#1, HC#2, and HC Black themes.</span></span>

## <a name="propertygrid-accessibility-support"></a><span data-ttu-id="725d5-134">속성 그리드 내게 필요한 옵션 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-134">PropertyGrid Accessibility support</span></span>

<span data-ttu-id="725d5-135">컨트롤에는 다음 변경 <xref:System.Windows.Forms.PropertyGrid> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-135">The following changes apply to the <xref:System.Windows.Forms.PropertyGrid> control:</span></span>

- <span data-ttu-id="725d5-136">그리드 `PropertyGrid.Bounds` 항목에 대한 내게 필요한 옵션 속성에서 제공하는 수정, 경계 사각형 계산의 성능 향상.</span><span class="sxs-lookup"><span data-stu-id="725d5-136">Corrected `PropertyGrid.Bounds` provided by accessibility properties for grid entries, improved performance of bounding rectangle calculation.</span></span> <span data-ttu-id="725d5-137">지금은 모든 접근성 경계가 뷰포트와 함께 전체 컨트롤의 경계를 고려하여 올바르게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-137">For now all accessibility bounds are represented correctly taking into account the bounds of entire control, along with its viewport.</span></span>
- <span data-ttu-id="725d5-138">컨트롤 형식 이름을 포함하지 않고 컨트롤 형식 이름에 대한 이중 발표를 피하기 위해 액세스 가능한 이름 및 하위 컨트롤 설명을 수정했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-138">Corrected accessible names and descriptions of subcontrols to not include control type names and to avoid double announcement for control type names.</span></span>

## <a name="toolstrip-accessibility-support"></a><span data-ttu-id="725d5-139">툴스트립 접근성 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-139">ToolStrip Accessibility support</span></span>

<span data-ttu-id="725d5-140">컨트롤에는 다음 변경 <xref:System.Windows.Forms.ToolStrip> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-140">The following changes apply to the <xref:System.Windows.Forms.ToolStrip> control:</span></span>

- <span data-ttu-id="725d5-141">을 `ToolStrip` `MenuStrip`통한 탐색이 `StatusStrip` 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-141">Improved navigation through `ToolStrip`, `MenuStrip`, and `StatusStrip` items.</span></span> <span data-ttu-id="725d5-142">`ToolStrip` 시프트 탭 위쪽 화살표를 누르면 메뉴 항목을 뒤로 반복하여 아래쪽 메뉴 요소로 이동합니다. `MenuStrip`</span><span class="sxs-lookup"><span data-stu-id="725d5-142">Corrected `ToolStrip` and `MenuStrip` shift-tab navigation, back-looping the menu items when shift-tab up-arrow is pressed, which navigates to the bottom menu element.</span></span>
- <span data-ttu-id="725d5-143">'MenuItem' 대신 '메뉴'의 하위 메뉴를 만들기 위해 하위 메뉴에 대한 접근성 탐색, 수정된 메뉴 접근 형 제어 유형이 개선되었습니다. `MenuStrip`</span><span class="sxs-lookup"><span data-stu-id="725d5-143">Improved `MenuStrip` accessible navigation, corrected menu accessible control types for submenus to make submenus of type 'Menu' instead of 'MenuItem'.</span></span>

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a><span data-ttu-id="725d5-144">PrintPreviewControl 및 인쇄미리보기대화언성 액세스 가능 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-144">PrintPreviewControl and PrintPreviewDialog Accessibility support</span></span>

<span data-ttu-id="725d5-145">다음 변경 사항은 인쇄 컨트롤에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-145">The following changes apply to the print controls:</span></span>

- <span data-ttu-id="725d5-146">메뉴 항목을 통해 액세스 가능한 탐색(내레이터 탐색 포함)이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-146">Improved accessible navigation (including Narrator navigation) through menu items.</span></span>
- <span data-ttu-id="725d5-147">향상된 고대비 테마 지원 및 컨트롤 요소를 더욱 대조적으로 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-147">Improved High Contrast themes support and made the control element more contrasted.</span></span>

## <a name="stringcollectioneditor-accessibility-support"></a><span data-ttu-id="725d5-148">스트링컬렉션편집기 내게 필요한 옵션 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-148">StringCollectionEditor Accessibility support</span></span>

<span data-ttu-id="725d5-149">이제 Windows Forms 디자이너는 향상된 접근성 지원을 통해 문자열 컬렉션 편집기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-149">Windows Forms designer now uses the string collection editor with improved accessibility support.</span></span>

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a><span data-ttu-id="725d5-150">월별 캘린더 내게 필요한 옵션 지원(.NET 코어 3.1에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="725d5-150">MonthCalendar Accessibility support (available in .NET Core 3.1)</span></span>

<span data-ttu-id="725d5-151">컨트롤에는 다음 변경 <xref:System.Windows.Forms.MonthCalendar> 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-151">The following changes apply to the <xref:System.Windows.Forms.MonthCalendar> control:</span></span>

- <span data-ttu-id="725d5-152">제어할 UI 자동화 `MonthCalendar` 서버 공급자를 추가하고 UI 자동화 그리드 패턴 및 테이블 패턴 공급자를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-152">Added UI Automation server providers to `MonthCalendar` control, added UI Automation Grid pattern and Table pattern providers.</span></span>
- <span data-ttu-id="725d5-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span><span class="sxs-lookup"><span data-stu-id="725d5-153">Changed _table_ accessible control type to _calendar_ accessible control type for `MonthCalendar` except the case when the control has a preceding label control that defines `MonthCalendar` control accessible name, in this specific case accessible control type becomes _table_.</span></span>
- <span data-ttu-id="725d5-154">제어를 위해 선택한 `MonthCalendar` 날짜의 공지가 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-154">Improved announcement of selected date for `MonthCalendar` control.</span></span>
- <span data-ttu-id="725d5-155">화면 `MonthCalendar` 판독기 및 기타 내게 필요한 옵션 도구에 대한 향상된 제어 지원.</span><span class="sxs-lookup"><span data-stu-id="725d5-155">Improved `MonthCalendar` control support for screen readers and other accessibility tools.</span></span> <span data-ttu-id="725d5-156">이 시점에서 사용자는 컨트롤 요소를 탐색하고 키보드 전용 입력을 사용하여 이러한 요소와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-156">At this moment, users can navigate the control elements and interact with these elements using keyboard-only input.</span></span> <span data-ttu-id="725d5-157">내레이터를 사용하면 CAPS + 화살표 키를 사용하여 컨트롤 요소를 탐색하고 CAPS + Enter를 사용하여 요소 기본 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-157">With Narrator, use CAPS + arrow keys to navigation through the control elements and CAPS + Enter to invoke element default action.</span></span>
- <span data-ttu-id="725d5-158">내레이터의 파란색 `MonthCalendar` 초점 사각형인 포커스 사각형이 있는 자식 요소 에서 화살표 키 탐색이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-158">Improved arrow key navigation across `MonthCalendar` child elements with a focusing rectangle: blue focus rectangle for Narrator.</span></span>
- <span data-ttu-id="725d5-159">제공된 좌표로 자식 액세스 요소를 `MonthCalendar` 얻을 수 있도록 컨트롤 요소에 대한 적중 테스트 작업에 대한 `MonthCalendar` 접근성이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-159">Improved accessibility for hit test action for `MonthCalendar` control elements to allow getting `MonthCalendar` child accessible element by provided coordinates.</span></span>

## <a name="tooltips-accessibility-available-in-net-core-31"></a><span data-ttu-id="725d5-160">도구 팁 내게 필요한 옵션(.NET 코어 3.1에서 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="725d5-160">ToolTips accessibility (available in .NET Core 3.1)</span></span>

- <span data-ttu-id="725d5-161">NVDA 및 내레이터와 같은 화면 판독기 응용 프로그램에서 도구 설명 텍스트를 발표할 수 있는 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-161">Added ability to announce a tooltip text by screen reader applications such as NVDA and Narrator.</span></span> <span data-ttu-id="725d5-162">이제 화면 판독기 응용 프로그램은 도구 설명팁을 표시하도록 구성된 Windows Forms 컨트롤의 키보드 또는 마우스 도구 설명의 텍스트를 발표할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-162">Screen reader application can now announce the text of keyboard or mouse tooltip of any Windows Forms control that configured to show tooltips.</span></span>

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a><span data-ttu-id="725d5-163">DataGridView, 속성 그리드, 리스트 박스, 콤보 박스, 도구 스트립 및 기타 컨트롤에 대한 UI 자동화 지원</span><span class="sxs-lookup"><span data-stu-id="725d5-163">UI automation support for DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip, and other controls</span></span>

<span data-ttu-id="725d5-164">UI 자동화 지원은 런타임에 컨트롤에 사용할 수 있지만 디자인 타임에는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="725d5-164">UI Automation support is enabled for controls at runtime but isn't used during design time.</span></span> <span data-ttu-id="725d5-165">UI 자동화 개요는 [UI Automation 개요](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="725d5-165">For an overview of UI automation, see the [UI Automation Overview](https://docs.microsoft.com/dotnet/framework/ui-automation/ui-automation-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="725d5-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="725d5-166">See also</span></span>

- <span data-ttu-id="725d5-167">[내게 필요한 옵션 모범 사례.](../ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="725d5-167">[Accessibility Best Practices](../ui-automation/accessibility-best-practices.md).</span></span>
