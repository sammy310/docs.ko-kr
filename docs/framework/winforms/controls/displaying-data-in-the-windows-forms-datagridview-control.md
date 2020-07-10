---
title: DataGridView 컨트롤에서 데이터 표시
description: Windows Forms DataGridView 컨트롤을 사용 하 여 다양 한 외부 데이터 원본의 데이터를 표시 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], displaying in tabular format
- data grids [Windows Forms], displaying data
- displaying data [Windows Forms], data grids
- DataGridView control [Windows Forms], displaying data
ms.assetid: b170b52a-2ebd-4948-ac2f-e52d494cebb2
ms.openlocfilehash: a0f3e6627290521b8c10477c31459f1486e79162
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174577"
---
# <a name="displaying-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="21258-103">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="21258-103">Displaying Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="21258-104">`DataGridView`컨트롤은 다양 한 외부 데이터 원본의 데이터를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21258-104">The `DataGridView` control is used to display data from a variety of external data sources.</span></span> <span data-ttu-id="21258-105">또는 컨트롤에 행과 열을 추가 하 고 데이터를 사용 하 여 수동으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21258-105">Alternatively, you can add rows and columns to the control and manually populate it with data.</span></span>  
  
 <span data-ttu-id="21258-106">컨트롤을 데이터 소스에 바인딩하는 경우 데이터 원본의 스키마를 기반으로 열을 자동으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21258-106">When you bind the control to a data source, you can generate columns automatically based on the schema of the data source.</span></span> <span data-ttu-id="21258-107">이러한 열이 원하는 대로 표시 되지 않으면 해당 열을 숨기 거 나 제거 하거나 다시 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21258-107">If these columns do not appear just as you want them to, you can hide, remove, or rearrange them.</span></span> <span data-ttu-id="21258-108">바인딩되지 않은 열을 추가 하 여 데이터 원본에서 제공 되지 않는 추가 데이터를 표시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21258-108">You can also add unbound columns to display supplemental data that does not come from the data source.</span></span>  
  
 <span data-ttu-id="21258-109">또한 표준 형식 (예: 통화 형식)을 사용 하 여 데이터를 표시 하거나, 필요한 데이터를 표시 하도록 표시 형식을 사용자 지정 (예: 음수의 배경색 변경 또는 문자열 값을 해당 이미지로 대체) 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21258-109">Additionally, you can display your data using standard formats (such as currency format), or you can customize the display formatting to present your data however you need to (such as changing the background color for negative numbers, or replacing string values with corresponding images).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="21258-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="21258-110">In This Section</span></span>  
 [<span data-ttu-id="21258-111">Windows Forms DataGridView 컨트롤의 데이터 디스플레이 모드</span><span class="sxs-lookup"><span data-stu-id="21258-111">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-112">컨트롤을 데이터로 채우는 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-112">Describes the options for populating the control with data.</span></span>  
  
 [<span data-ttu-id="21258-113">Windows Forms DataGridView 컨트롤에서 데이터 형식 지정</span><span class="sxs-lookup"><span data-stu-id="21258-113">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-114">셀 표시 값의 서식을 지정 하기 위한 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-114">Describes the options for formatting cell display values.</span></span>  
  
 [<span data-ttu-id="21258-115">연습: 바인딩되지 않은 Windows Forms DataGridView 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="21258-115">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-116">컨트롤을 데이터를 사용 하 여 수동으로 채우는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-116">Describes how to manually populate the control with data.</span></span>  
  
 [<span data-ttu-id="21258-117">방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="21258-117">How to: Bind Data to the Windows Forms DataGridView Control</span></span>](how-to-bind-data-to-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-118">`BindingSource`데이터베이스에서 가져온 정보를 포함 하는에 바인딩하여 컨트롤을 데이터로 채우는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-118">Describes how to populate the control with data by binding it to a `BindingSource` that contains information pulled from a database.</span></span>  
  
 [<span data-ttu-id="21258-119">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에서 열 자동 생성</span><span class="sxs-lookup"><span data-stu-id="21258-119">How to: Autogenerate Columns in a Data-Bound Windows Forms DataGridView Control</span></span>](autogenerate-columns-in-a-data-bound-wf-datagridview-control.md)  
 <span data-ttu-id="21258-120">바인딩된 데이터 소스를 기반으로 열을 자동으로 생성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-120">Describes how to automatically generate columns based on a bound data source.</span></span>  
  
 [<span data-ttu-id="21258-121">방법: Windows Forms DataGridView 컨트롤에서 자동으로 생성된 열 제거</span><span class="sxs-lookup"><span data-stu-id="21258-121">How to: Remove Autogenerated Columns from a Windows Forms DataGridView Control</span></span>](remove-autogenerated-columns-from-a-wf-datagridview-control.md)  
 <span data-ttu-id="21258-122">바인딩된 데이터 원본에서 자동으로 생성 된 열을 숨기 거 나 삭제 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-122">Describes how to hide or delete columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="21258-123">방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경</span><span class="sxs-lookup"><span data-stu-id="21258-123">How to: Change the Order of Columns in the Windows Forms DataGridView Control</span></span>](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-124">바인딩된 데이터 원본에서 자동으로 생성 된 열을 다시 정렬 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-124">Describes how to rearrange columns generated automatically from a bound data source.</span></span>  
  
 [<span data-ttu-id="21258-125">방법: 데이터 바인딩된 Windows Forms DataGridView 컨트롤에 바인딩되지 않은 열 추가</span><span class="sxs-lookup"><span data-stu-id="21258-125">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>](unbound-column-to-a-data-bound-datagridview.md)  
 <span data-ttu-id="21258-126">바인딩되지 않은 추가 열을 표시 하 여 바인딩된 데이터 원본의 데이터를 보완 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-126">Describes how to supplement data from a bound data source by displaying additional, unbound columns.</span></span>  
  
 [<span data-ttu-id="21258-127">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="21258-127">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)  
 <span data-ttu-id="21258-128">각 개체가 자체 행에 표시 되도록 컨트롤을 임의의 개체의 컬렉션에 바인딩하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-128">Describes how to bind the control to a collection of arbitrary objects so that each object is displayed in its own row.</span></span>  
  
 [<span data-ttu-id="21258-129">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="21258-129">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)  
 <span data-ttu-id="21258-130">컨트롤의 특정 행에 바인딩된 개체를 검색 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-130">Describes how to retrieve an object bound to a particular row of the control.</span></span>  
  
 [<span data-ttu-id="21258-131">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="21258-131">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)  
 <span data-ttu-id="21258-132">한 컨트롤에 표시 된 값이 `DataGridView` 다른 컨트롤에서 현재 선택 된 행에 따라 달라 지도록 관련 된 두 데이터베이스 테이블의 데이터를 표시 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-132">Describes how to display data from two related database tables so that the values shown in one `DataGridView` control depend on the currently selected row in another control.</span></span>  
  
 [<span data-ttu-id="21258-133">방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="21258-133">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-134">이벤트를 처리 하 여 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> 값에 따라 셀의 모양을 변경 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-134">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event to change the appearance of cells depending on their values.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="21258-135">참조</span><span class="sxs-lookup"><span data-stu-id="21258-135">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="21258-136"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-136">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <span data-ttu-id="21258-137">속성에 대 한 참조 설명서를 제공 합니다 <xref:System.Windows.Forms.DataGridView.DataSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="21258-137">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="21258-138"><xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-138">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="21258-139">관련 단원</span><span class="sxs-lookup"><span data-stu-id="21258-139">Related Sections</span></span>  
 [<span data-ttu-id="21258-140">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="21258-140">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="21258-141">사용자가 컨트롤에서 데이터를 추가 및 수정하는 방법을 변경하는 방법에 대해 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21258-141">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21258-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21258-142">See also</span></span>

- [<span data-ttu-id="21258-143">DataGridView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="21258-143">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="21258-144">Windows Forms DataGridView 컨트롤의 열 형식</span><span class="sxs-lookup"><span data-stu-id="21258-144">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
