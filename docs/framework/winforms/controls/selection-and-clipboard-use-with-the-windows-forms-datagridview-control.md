---
title: DataGridView 컨트롤에서 선택 및 클립보드 사용
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 6993f77e8ce532d8df1bdc7e6b6abc1cc3268e49
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743067"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="b0c5c-102">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="b0c5c-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b0c5c-103">`DataGridView` 컨트롤은 사용자가 셀, 행 및 열을 선택할 수 있는 방법을 구성 하는 다양 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="b0c5c-104">예를 들어, 사용자가 셀을 클릭할 때 전체 행 또는 열을 선택 하거나, 사용자가 머리글을 클릭 한 경우에만 전체 행 또는 열을 선택 하 여 셀 선택을 가능 하 게 하는 단일 또는 다중 선택을 가능 하 게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="b0c5c-105">사용자가 선택할 수 있는 사용자 인터페이스를 제공 하려는 경우 일반 선택을 사용 하지 않도록 설정 하 고 모든 선택 항목을 프로그래밍 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="b0c5c-106">또한 사용자가 선택한 값을 클립보드에 복사 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b0c5c-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b0c5c-107">In This Section</span></span>  
 [<span data-ttu-id="b0c5c-108">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="b0c5c-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b0c5c-109">컨트롤에서 사용자 및 프로그래밍 방식의 선택에 대 한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="b0c5c-110">방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정</span><span class="sxs-lookup"><span data-stu-id="b0c5c-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b0c5c-111">사용자가 셀을 클릭할 때 단일 행 선택에 대 한 컨트롤을 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="b0c5c-112">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="b0c5c-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="b0c5c-113">선택한 셀, 행 및 열 컬렉션을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="b0c5c-114">방법: Windows Forms DataGridView 컨트롤에서 사용자가 여러 셀을 클립보드에 복사할 수 있도록 설정</span><span class="sxs-lookup"><span data-stu-id="b0c5c-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="b0c5c-115">컨트롤에서 클립보드 지원을 사용 하도록 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b0c5c-116">참조</span><span class="sxs-lookup"><span data-stu-id="b0c5c-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="b0c5c-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="b0c5c-118"><xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="b0c5c-119"><xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 속성에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="b0c5c-120"><xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="b0c5c-121"><xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="b0c5c-122"><xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 클래스에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0c5c-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c5c-123">참조</span><span class="sxs-lookup"><span data-stu-id="b0c5c-123">See also</span></span>

- [<span data-ttu-id="b0c5c-124">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b0c5c-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="b0c5c-125">Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="b0c5c-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
