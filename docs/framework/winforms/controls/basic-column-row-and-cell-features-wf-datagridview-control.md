---
title: Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 4c755d5f0c2e134b83beb27ebbd06080bad620b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115234"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="8180b-102">Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능</span><span class="sxs-lookup"><span data-stu-id="8180b-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="8180b-103">많은 기본 동작을 `DataGridView` 단일 속성을 설정 하 여 셀, 행 및 열을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="8180b-104">이 섹션의에서 항목에서는 이러한 기능 중 가장 많이 사용의 몇 가지를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8180b-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8180b-105">In This Section</span></span>  
 [<span data-ttu-id="8180b-106">방법: Windows Forms DataGridView 컨트롤에서 열 숨기기</span><span class="sxs-lookup"><span data-stu-id="8180b-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-107">특정 열의 컨트롤에 표시 되는 것을 방지 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="8180b-108">방법: Windows Forms DataGridView 컨트롤에서 열 머리글 숨기기</span><span class="sxs-lookup"><span data-stu-id="8180b-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-109">컨트롤에서 열 머리글 표시 되지 않게 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="8180b-110">방법: Windows Forms DataGridView 컨트롤에서 열 다시 정렬 사용</span><span class="sxs-lookup"><span data-stu-id="8180b-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-111">사용자가 컨트롤에서 열을 다시 정렬할 수 있게 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="8180b-112">방법: Windows Forms DataGridView 컨트롤에서 열 고정</span><span class="sxs-lookup"><span data-stu-id="8180b-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-113">설명 스크롤에서 하나 이상의 인접 한 열을 방지 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="8180b-114">방법: Windows Forms DataGridView 컨트롤의 읽기 전용으로 열 만들기</span><span class="sxs-lookup"><span data-stu-id="8180b-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-115">사용자 컨트롤의 특정 열을 편집 하지 못하도록 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="8180b-116">방법: Windows Forms DataGridView 컨트롤에서 행 추가 및 삭제를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="8180b-117">행을 추가 하지 못하게 하려면 컨트롤의 맨 아래에 새 레코드에 대 한 행을 제거 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="8180b-118">또한 사용자가 행을 삭제 하지 못하도록 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="8180b-119">방법: 가져오기 및 Windows Forms DataGridView 컨트롤에서 현재 셀 설정</span><span class="sxs-lookup"><span data-stu-id="8180b-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="8180b-120">컨트롤에서 현재 포커스가 있는 셀에 액세스 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="8180b-121">방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시</span><span class="sxs-lookup"><span data-stu-id="8180b-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-122">모든 셀에 아이콘을 표시 하는 이미지 열을 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8180b-123">참조</span><span class="sxs-lookup"><span data-stu-id="8180b-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="8180b-124">컨트롤에 대 한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8180b-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8180b-125">Related Sections</span></span>  
 [<span data-ttu-id="8180b-126">Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="8180b-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="8180b-127">컨트롤의 기본 모양과 셀 데이터의 표시 형식을 수정하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="8180b-128">Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="8180b-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="8180b-129">셀, 행 및 열 개체를 사용하여 프로그래밍하는 방법을 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8180b-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8180b-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="8180b-130">See also</span></span>

- [<span data-ttu-id="8180b-131">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8180b-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="8180b-132">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="8180b-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
