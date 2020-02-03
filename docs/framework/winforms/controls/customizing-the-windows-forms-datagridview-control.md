---
title: DataGridView 컨트롤 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744031"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="78421-102">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="78421-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="78421-103">`DataGridView` 컨트롤은 셀, 행 및 열의 모양 및 기본 동작 (모양 및 느낌)을 조정 하는 데 사용할 수 있는 몇 가지 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="78421-104">그러나 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 기능 외에도 특별 한 요구 사항이 있는 경우 컨트롤에 대 한 소유자 그리기를 구현 하거나 사용자 지정 셀, 열 및 행을 만들어 해당 기능을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78421-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="78421-105">셀과 행을 직접 그리려면 다양 한 `DataGridView` 그리기 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78421-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="78421-106">기존 기능을 수정 하거나 새로운 기능을 제공 하기 위해 기존 `DataGridViewCell`, `DataGridViewColumn`및 `DataGridViewRow` 형식에서 파생 된 고유한 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78421-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="78421-107">셀이 편집 모드에 있을 때 선택한 컨트롤을 표시 하는 파생 형식을 만들어 새로운 편집 기능을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78421-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="78421-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="78421-108">In This Section</span></span>  
 [<span data-ttu-id="78421-109">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="78421-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="78421-110">셀을 수동으로 그리기 위해 <xref:System.Windows.Forms.DataGridView.CellPainting> 이벤트를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="78421-111">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="78421-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="78421-112">여러 열에 걸쳐 있는 사용자 지정, 그라데이션 배경 및 콘텐츠를 사용 하 여 행을 그리기 위해 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 이벤트를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="78421-113">방법: Windows Forms DataGridView 컨트롤에서 동작 및 모양을 확장하여 셀과 열 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="78421-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="78421-114">마우스 포인터가 위에 있을 때 셀을 강조 표시 하기 위해 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="78421-115">방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추 비활성화</span><span class="sxs-lookup"><span data-stu-id="78421-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="78421-116">단추 열에 비활성화 된 단추를 표시 하기 위해 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn>에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="78421-117">방법: Windows Forms DataGridView 셀에서 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="78421-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="78421-118">셀이 편집 모드에 있을 때 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 표시 하기 위해 `IDataGridViewEditingControl` 인터페이스를 구현 하 고 `DataGridViewCell` 및 `DataGridViewColumn`에서 파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="78421-119">참조</span><span class="sxs-lookup"><span data-stu-id="78421-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="78421-120"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="78421-121"><xref:System.Windows.Forms.DataGridViewCell> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="78421-122"><xref:System.Windows.Forms.DataGridViewRow> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="78421-123"><xref:System.Windows.Forms.DataGridViewColumn> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="78421-124"><xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="78421-125">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="78421-125">Related Sections</span></span>  
 [<span data-ttu-id="78421-126">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="78421-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="78421-127">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="78421-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78421-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78421-128">See also</span></span>

- [<span data-ttu-id="78421-129">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="78421-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="78421-130">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="78421-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
