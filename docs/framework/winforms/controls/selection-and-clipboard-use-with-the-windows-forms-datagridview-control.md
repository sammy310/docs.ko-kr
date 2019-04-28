---
title: Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], Clipboard use
- cells [Windows Forms], selecting in grids
- Clipboard [Windows Forms], in DataGridView control
- selection [Windows Forms], in DataGridView control
- data grids [Windows Forms], selecting cells
- DataGridView control [Windows Forms], selecting cells
ms.assetid: 82cffcad-8b30-4897-bddb-c3a79d751b83
ms.openlocfilehash: 1836fbc1887082ca685c49bef2bc42bdb167578f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902254"
---
# <a name="selection-and-clipboard-use-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="b4369-102">Windows Forms DataGridView 컨트롤에서 선택 및 클립보드 사용</span><span class="sxs-lookup"><span data-stu-id="b4369-102">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b4369-103">`DataGridView` 컨트롤에서는 다양 한 사용자가 셀, 행 및 열을 선택할 수는 방법을 구성 하기 위한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-103">The `DataGridView` control provides you with a variety of options for configuring how users can select cells, rows, and columns.</span></span> <span data-ttu-id="b4369-104">예를 들어, 설정할 수 있습니다. 단일 또는 여러 선택 영역, 전체 행 또는 열의 셀을 클릭할 때 선택 또는 전체 행 또는 열을 선택할 사용자가 머리글을 클릭할 경우에 셀 선택 영역도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-104">For example, you can enable single or multiple selection, selection of whole rows or columns when users click cells, or selection of whole rows or columns only when users click their headers, which enables cell selection as well.</span></span> <span data-ttu-id="b4369-105">선택에 대 한 고유한 사용자 인터페이스를 제공 하려는 경우에 일반적인 선택을 사용 하지 않도록 설정 하 고 모든 선택 항목을 프로그래밍 방식으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-105">If you want to provide your own user interface for selection, you can disable ordinary selection and handle all selection programmatically.</span></span> <span data-ttu-id="b4369-106">또한 사용자가 선택한 값을 클립보드에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-106">Additionally, you can enable users to copy the selected values to the Clipboard.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b4369-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="b4369-107">In This Section</span></span>  
 [<span data-ttu-id="b4369-108">Windows Forms DataGridView 컨트롤의 선택 모드</span><span class="sxs-lookup"><span data-stu-id="b4369-108">Selection Modes in the Windows Forms DataGridView Control</span></span>](selection-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b4369-109">사용자 및 컨트롤의 프로그래밍 선택 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-109">Describes the options for user and programmatic selection in the control.</span></span>  
  
 [<span data-ttu-id="b4369-110">방법: Windows Forms DataGridView 컨트롤의 선택 모드 설정</span><span class="sxs-lookup"><span data-stu-id="b4369-110">How to: Set the Selection Mode of the Windows Forms DataGridView Control</span></span>](how-to-set-the-selection-mode-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="b4369-111">사용자가 셀을 클릭 하면 단일 행 선택에 대 한 제어를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-111">Describes how to configure the control for single-row selection when a user clicks a cell.</span></span>  
  
 [<span data-ttu-id="b4369-112">방법: Windows Forms DataGridView 컨트롤에서 선택한 셀, 행 및 열 가져오기</span><span class="sxs-lookup"><span data-stu-id="b4369-112">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](selected-cells-rows-and-columns-datagridview.md)  
 <span data-ttu-id="b4369-113">선택한 셀, 행 및 열 컬렉션을 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-113">Describes how to work with the selected cell, row, and column collections.</span></span>  
  
 [<span data-ttu-id="b4369-114">방법: Windows Forms DataGridView 컨트롤에서 여러 셀을 클립보드에 복사 하는 사용자를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b4369-114">How to: Enable Users to Copy Multiple Cells to the Clipboard from the Windows Forms DataGridView Control</span></span>](enable-users-to-copy-multiple-cells-to-the-clipboard-datagridview.md)  
 <span data-ttu-id="b4369-115">컨트롤의 클립보드 지원을 사용 하도록 설정 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-115">Describes how to enable Clipboard support in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b4369-116">참조</span><span class="sxs-lookup"><span data-stu-id="b4369-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="b4369-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="b4369-118">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A>  
 <span data-ttu-id="b4369-119">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.ClipboardCopyMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection>  
 <span data-ttu-id="b4369-120">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedCellCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection>  
 <span data-ttu-id="b4369-121">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedRowCollection> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection>  
 <span data-ttu-id="b4369-122">에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4369-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewSelectedColumnCollection> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4369-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="b4369-123">See also</span></span>

- [<span data-ttu-id="b4369-124">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b4369-124">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="b4369-125">Windows Forms DataGridView 컨트롤에서의 기본 키보드 및 마우스 처리</span><span class="sxs-lookup"><span data-stu-id="b4369-125">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
