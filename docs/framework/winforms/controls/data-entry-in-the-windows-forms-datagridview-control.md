---
title: DataGridView 컨트롤의 데이터 입력
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], data entry
- data entry [Windows Forms], dataGridView control
- data grids [Windows Forms], data entry
ms.assetid: 4a6d4676-d4e7-4b0e-9c22-50ce65ffe0d6
ms.openlocfilehash: e95095624f45cc1507735083a87293730e9133e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744005"
---
# <a name="data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="801e6-102">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="801e6-102">Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="801e6-103">`DataGridView` 컨트롤은 사용자가 컨트롤의 데이터를 추가 하거나 수정 하는 방법을 변경할 수 있는 몇 가지 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-103">The `DataGridView` control provides several features that let you change how users add or modify data in the control.</span></span> <span data-ttu-id="801e6-104">예를 들어 새 행에 대 한 기본값을 제공 하 고 오류가 발생할 때 사용자에 게 경고 하 여 데이터 입력을 보다 효율적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-104">For example, you can make data entry more efficient by providing default values for new rows and by alerting users when errors occur.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="801e6-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="801e6-105">In This Section</span></span>  
 [<span data-ttu-id="801e6-106">방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정</span><span class="sxs-lookup"><span data-stu-id="801e6-106">How to: Specify the Edit Mode for the Windows Forms DataGridView Control</span></span>](how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="801e6-107">사용자가 셀 편집을 시작 하는 방법을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-107">Describes how to change the way users start editing cells.</span></span>  
  
 [<span data-ttu-id="801e6-108">방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정</span><span class="sxs-lookup"><span data-stu-id="801e6-108">How to: Specify Default Values for New Rows in the Windows Forms DataGridView Control</span></span>](specify-default-values-for-new-rows-in-the-datagrid.md)  
 <span data-ttu-id="801e6-109">새 레코드의 행을 미리 채우고 데이터 입력 시간을 저장 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-109">Describes how to prepopulate the row for new records to save data-entry time.</span></span>  
  
 [<span data-ttu-id="801e6-110">Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용</span><span class="sxs-lookup"><span data-stu-id="801e6-110">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="801e6-111">새 레코드에 대 한 행을 숨기는 방법, 모양을 사용자 지정 하는 방법 및 <xref:System.Windows.Forms.DataGridView.Rows%2A> 컬렉션과의 관계에 대 한 정보를 포함 하 여 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-111">Describes the row for new records in detail, including information on hiding it, on customizing its appearance, and on how it relates to the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span>  
  
 [<span data-ttu-id="801e6-112">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="801e6-112">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="801e6-113">데이터 입력 형식 오류를 방지 하기 위해 사용자 입력의 유효성을 검사 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-113">Describes how to validate user input to prevent data-entry formatting errors.</span></span>  
  
 [<span data-ttu-id="801e6-114">연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="801e6-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 <span data-ttu-id="801e6-115">사용자가 새 값을 커밋하려고 할 때 데이터 소스에서 시작 되는 데이터 입력 오류를 처리 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-115">Describes how to handle data-entry errors that originate from the data source when the user attempts to commit a new value.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="801e6-116">참조</span><span class="sxs-lookup"><span data-stu-id="801e6-116">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="801e6-117"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-117">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 <span data-ttu-id="801e6-118"><xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-118">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.EditMode%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 <span data-ttu-id="801e6-119"><xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-119">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataError?displayProperty=nameWithType>  
 <span data-ttu-id="801e6-120"><xref:System.Windows.Forms.DataGridView.DataError> 이벤트에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataError> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellValidating?displayProperty=nameWithType>  
 <span data-ttu-id="801e6-121"><xref:System.Windows.Forms.DataGridView.CellValidating> 이벤트에 대 한 참조 설명서를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellValidating> event.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="801e6-122">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="801e6-122">Related Sections</span></span>  
 [<span data-ttu-id="801e6-123">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="801e6-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="801e6-124">수동으로 또는 외부 데이터 원본에서 컨트롤에 데이터를 채우는 방법을 설명 하는 항목을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="801e6-124">Provides topics that describe how to populate the control with data either manually or from an external data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="801e6-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="801e6-125">See also</span></span>

- [<span data-ttu-id="801e6-126">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="801e6-126">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="801e6-127">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="801e6-127">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
