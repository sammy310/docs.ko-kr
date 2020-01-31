---
title: DataGridView 컨트롤의 열 및 행 크기 조정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], sizing rows and columns
- columns [Windows Forms], resizing in grids
- data grids [Windows Forms], resizing columns and rows
ms.assetid: 7532764d-e5c1-4943-a08b-6377a722d3b6
ms.openlocfilehash: 8f8394a837ccc11c469f9ad4feeb60464d0014fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742419"
---
# <a name="resizing-columns-and-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="fd450-102">Windows Forms DataGridView 컨트롤의 열 및 행 크기 조정</span><span class="sxs-lookup"><span data-stu-id="fd450-102">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fd450-103">`DataGridView` 컨트롤은 열 및 행의 크기 조정 동작을 사용자 지정 하는 다양 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-103">The `DataGridView` control provides numerous options for customizing the sizing behavior of its columns and rows.</span></span> <span data-ttu-id="fd450-104">일반적으로 `DataGridView` 셀은 내용에 따라 크기를 조정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-104">Typically, `DataGridView` cells do not resize based on their contents.</span></span> <span data-ttu-id="fd450-105">대신 셀 보다 큰 모든 표시 값을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-105">Instead, they clip any display value that is larger than the cell.</span></span> <span data-ttu-id="fd450-106">콘텐츠를 문자열로 표시할 수 있는 경우 셀에 도구 설명으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-106">If the content can be displayed as a string, the cell displays it in a ToolTip.</span></span>  
  
 <span data-ttu-id="fd450-107">기본적으로 사용자는 행, 열 및 헤더 구분선을 마우스로 끌어 추가 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-107">By default, users can drag row, column, and header dividers with the mouse to show more information.</span></span> <span data-ttu-id="fd450-108">또한 사용자는 구분선을 두 번 클릭 하 여 해당 내용에 따라 연결 된 행, 열 또는 헤더 밴드의 크기를 자동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-108">Users can also double-click a divider to automatically resize the associated row, column, or header band based on its contents.</span></span>  
  
 <span data-ttu-id="fd450-109">`DataGridView` 컨트롤은 이러한 모든 사용자 지정 동작을 사용자 지정 하거나 사용 하지 않도록 설정할 수 있는 속성, 메서드 및 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-109">The `DataGridView` control provides properties, methods, and events that enable you to customize or disable all of these user-directed behaviors.</span></span> <span data-ttu-id="fd450-110">또한 내용에 맞게 행, 열 및 머리글의 크기를 프로그래밍 방식으로 조정 하거나 내용이 변경 될 때마다 자동으로 크기를 조정 하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-110">Additionally, you can programmatically resize rows, columns, and headers to fit their contents, or you can configure them to automatically resize themselves whenever their contents change.</span></span> <span data-ttu-id="fd450-111">또한 사용자가 지정 하는 비율로 컨트롤의 사용 가능한 너비를 자동으로 나누려면 열을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-111">You can also configure columns to automatically divide the available width of the control in proportions that you specify.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd450-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="fd450-112">In This Section</span></span>  
 [<span data-ttu-id="fd450-113">Windows Forms DataGridView 컨트롤의 크기 조정 옵션</span><span class="sxs-lookup"><span data-stu-id="fd450-113">Sizing Options in the Windows Forms DataGridView Control</span></span>](sizing-options-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fd450-114">행, 열 및 머리글의 크기를 조정 하기 위한 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-114">Describes the options for sizing rows, columns, and headers.</span></span> <span data-ttu-id="fd450-115">또한 크기 조정 관련 속성 및 메서드에 대 한 세부 정보를 제공 하 고 일반적인 사용 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-115">Also provides details on sizing-related properties and methods, and describes common usage scenarios.</span></span>  
  
 [<span data-ttu-id="fd450-116">Windows Forms DataGridView 컨트롤의 열 채우기 모드</span><span class="sxs-lookup"><span data-stu-id="fd450-116">Column Fill Mode in the Windows Forms DataGridView Control</span></span>](column-fill-mode-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fd450-117">열 채우기 모드에 대해 자세히 설명 하 고 열 채우기 모드 및 기타 모드를 실험 하는 데 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-117">Describes column fill mode in detail, and provides demonstration code that you can use to experiment with column fill mode and other modes.</span></span>  
  
 [<span data-ttu-id="fd450-118">방법: Windows Forms DataGridView 컨트롤의 크기 조정 모드 설정</span><span class="sxs-lookup"><span data-stu-id="fd450-118">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>](how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="fd450-119">일반적인 용도로 크기 조정 모드를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-119">Describes how to configure the sizing modes for common purposes.</span></span>  
  
 [<span data-ttu-id="fd450-120">방법: Windows Forms DataGridView 컨트롤에서 내용에 맞게 프로그래밍 방식으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="fd450-120">How to: Programmatically Resize Cells to Fit Content in the Windows Forms DataGridView Control</span></span>](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)  
 <span data-ttu-id="fd450-121">프로그래밍 방식의 크기 조정을 실험 하는 데 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-121">Provides demonstration code that you can use to experiment with programmatic resizing.</span></span>  
  
 [<span data-ttu-id="fd450-122">방법: Windows Forms DataGridView 컨트롤에서 내용이 변경되는 경우 자동으로 셀 크기 조정</span><span class="sxs-lookup"><span data-stu-id="fd450-122">How to: Automatically Resize Cells When Content Changes in the Windows Forms DataGridView Control</span></span>](automatically-resize-cells-when-content-changes-in-the-datagrid.md)  
 <span data-ttu-id="fd450-123">자동 크기 조정 모드를 시험해 볼 때 사용할 수 있는 데모 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-123">Provides demonstration code that you can use to experiment with automatic sizing modes.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fd450-124">참조</span><span class="sxs-lookup"><span data-stu-id="fd450-124">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="fd450-125"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd450-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd450-126">참조</span><span class="sxs-lookup"><span data-stu-id="fd450-126">See also</span></span>

- [<span data-ttu-id="fd450-127">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fd450-127">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
