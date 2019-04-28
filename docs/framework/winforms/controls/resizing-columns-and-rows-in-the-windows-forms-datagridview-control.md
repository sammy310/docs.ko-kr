---
title: Windows Forms DataGridView 컨트롤에서 열 및 행 크기 조정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: e1fa2d57cfb2cd374d691fe03a0e0bdbd3ad7141
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903190"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="7521f-102">Windows Forms DataGridView 컨트롤에서 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="7521f-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="7521f-103">`DataGridView` 컨트롤의 열 및 행 크기 조정 동작을 사용자 지정에 대 한 다양 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="7521f-104">일반적으로 `DataGridView` 셀 크기가 조정 되지 않습니다 해당 내용을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="7521f-105">대신 된 셀 보다 크면 모든 표시 값을 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="7521f-106">콘텐츠를 문자열로 표시할 수 있는, 셀 도구 설명에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="7521f-107">기본적으로 사용자가 행, 열 및 머리글 구분선을 자세한 정보를 표시 하려면 마우스로 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="7521f-108">사용자를 내용에 따라 연결 된 행, 열 또는 헤더 밴드를 자동으로 조정 하려면 구분선을 두 번 클릭할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="7521f-109">`DataGridView` 컨트롤은 속성, 메서드 및 사용자 지정 하거나 이러한 모든 사용자 지정 동작을 비활성화할 수 있도록 하는 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="7521f-110">또한 프로그래밍 방식으로 크기를 조정할 수 행, 열 및 해당 내용에 맞게 머리글 또는 해당 내용이 변경 될 때마다 직접 자동으로 조정 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="7521f-111">또한 자동으로 지정 하는 비율에서 컨트롤의 사용 가능한 너비를 분할 하는 열을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7521f-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="7521f-112">In This Section</span></span>  
 [<span data-ttu-id="7521f-113">Windows Forms DataGridView 컨트롤의 크기 조정 옵션</span><span class="sxs-lookup"><span data-stu-id="7521f-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7521f-114">크기 조정 행, 열 및 헤더에 대 한 옵션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="7521f-115">또한 크기 조정 관련 속성 및 메서드 세부 정보를 제공 하 고 일반적인 사용 시나리오에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="7521f-116">Windows Forms DataGridView 컨트롤의 열 채우기 모드</span><span class="sxs-lookup"><span data-stu-id="7521f-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7521f-117">열 채우기 모드를 자세히 설명 하 고 열 채우기 모드와 다른 모드를 사용 하 여 실험에 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="7521f-118">방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정</span><span class="sxs-lookup"><span data-stu-id="7521f-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="7521f-119">일반적인 용도 대 한 크기 조정 모드를 구성 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="7521f-120">방법: 프로그래밍 방식으로 Windows Forms DataGridView 컨트롤의 내용에 맞게 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="7521f-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="7521f-121">프로그래밍 방식으로 크기 조정을 통한 실험 하는 데 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="7521f-122">방법: Windows Forms DataGridView 컨트롤에서 내용이 변경 될 때 자동으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="7521f-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="7521f-123">자동 크기 조정 모드를 사용 하 여 실험에 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7521f-124">참조</span><span class="sxs-lookup"><span data-stu-id="7521f-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="7521f-125"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7521f-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7521f-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="7521f-126">See also</span></span>

- [<span data-ttu-id="7521f-127">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="7521f-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
