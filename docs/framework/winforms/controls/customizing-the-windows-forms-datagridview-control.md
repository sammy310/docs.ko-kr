---
title: Windows Forms DataGridView 컨트롤 사용자 지정
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: ab8d1f07c608aca4f14f5e73860f8c3e263a4610
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091384"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="2cbf6-102">Windows Forms DataGridView 컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2cbf6-103">`DataGridView` 컨트롤 모양과 해당 셀, 행 및 열의 기본 동작 (모양 및 느낌)을 조정 하는 데 사용할 수 있는 몇 가지 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="2cbf6-104">그러나 기능 보다 우수한 특별 한 요구 사항이 있는 경우는 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스, 소유자 컨트롤에 대 한 그리기를 구현 하거나 수도 사용자 지정 셀, 열 및 행 키를 만들어 해당 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="2cbf6-105">그릴 셀 및 행 직접, 다양 한 처리할 수 있습니다 `DataGridView` 그리기 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="2cbf6-106">를 기존 기능을 수정 하거나 새 기능을 제공 하려면 기존에서 파생 된 고유한 형식을 만들 수 있습니다 `DataGridViewCell`, `DataGridViewColumn`, 및 `DataGridViewRow` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="2cbf6-107">또한 선택한 셀이 편집 모드일 때 컨트롤을 표시 하는 파생된 형식을 생성 하 여 새로운 편집 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cbf6-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2cbf6-108">In This Section</span></span>  
 [<span data-ttu-id="2cbf6-109">방법: Windows Forms DataGridView 컨트롤에서 셀 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="2cbf6-110">처리 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DataGridView.CellPainting> 그리기 위해 이벤트 셀을 수동으로.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="2cbf6-111">방법: Windows Forms DataGridView 컨트롤에서 행 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="2cbf6-112">처리 하는 방법에 설명 합니다 <xref:System.Windows.Forms.DataGridView.RowPrePaint> 및 <xref:System.Windows.Forms.DataGridView.RowPostPaint> 여러 열으로 확장 하기 위해 사용자 지정, 그라데이션 배경이 있는 행을 그리기 및 콘텐츠는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="2cbf6-113">방법: Windows Forms DataGridView 컨트롤에서 셀 및 열은 동작과 모양을 확장 하 여 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="2cbf6-114">파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다 `DataGridViewCell` 고 `DataGridViewColumn` 에 마우스 포인터가 있을 때 셀을 강조 표시 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="2cbf6-115">방법: Windows Forms DataGridView 컨트롤의 단추 열에서 단추를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="2cbf6-116">파생 된 사용자 지정 형식을 만드는 방법을 설명 합니다 <xref:System.Windows.Forms.DataGridViewButtonCell> 및 <xref:System.Windows.Forms.DataGridViewButtonColumn> 단추 열에서 비활성화 된 단추를 표시 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="2cbf6-117">방법: Windows Forms DataGridView 셀에서 컨트롤을 호스트</span><span class="sxs-lookup"><span data-stu-id="2cbf6-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="2cbf6-118">구현 하는 방법에 설명 합니다 `IDataGridViewEditingControl` 인터페이스에서 파생 된 사용자 지정 형식을 만들고 `DataGridViewCell` 및 `DataGridViewColumn` 표시 하기 위해를 <xref:System.Windows.Forms.DateTimePicker> 셀 편집 모드에 있을 때이 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2cbf6-119">참조</span><span class="sxs-lookup"><span data-stu-id="2cbf6-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2cbf6-120"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="2cbf6-121">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewCell> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="2cbf6-122">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewRow> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="2cbf6-123">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewColumn> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="2cbf6-124">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.IDataGridViewEditingControl> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cbf6-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2cbf6-125">Related Sections</span></span>  
 [<span data-ttu-id="2cbf6-126">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="2cbf6-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2cbf6-127">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cbf6-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbf6-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="2cbf6-128">See also</span></span>

- [<span data-ttu-id="2cbf6-129">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="2cbf6-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2cbf6-130">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="2cbf6-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
