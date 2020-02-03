---
title: 디자이너를 사용 하 여 DataGridView 컨트롤의 기본 셀 스타일 및 데이터 형식 설정
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731363"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="bfce8-102">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정</span><span class="sxs-lookup"><span data-stu-id="bfce8-102">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="bfce8-103"><xref:System.Windows.Forms.DataGridView> 컨트롤을 사용 하 여 전체 컨트롤에 대 한 기본 셀 스타일 및 셀 데이터 형식을 지정 하 고, 행 및 열 머리글의 경우 행 및 열 머리글의 경우, 대체 행에 대해 원장 효과를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-103">The <xref:System.Windows.Forms.DataGridView> control lets you specify default cell styles and cell data formats for the entire control, for specific columns, for row and column headers, and for alternating rows to create a ledger effect.</span></span> <span data-ttu-id="bfce8-104">전체 컨트롤에 대해 설정 된 기본 스타일은 열 및 교대로 반복 되는 행에 대해 설정 된 기본 스타일에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-104">Default styles set for the entire control are overridden by default styles set for columns and alternating rows.</span></span> <span data-ttu-id="bfce8-105">또한 개별 행 및 셀에 대해 코드에서 설정한 스타일이 기본 스타일을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-105">Additionally, styles that you set in code for individual rows and cells override the default styles.</span></span>

<span data-ttu-id="bfce8-106">셀 스타일에 대 한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](cell-styles-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfce8-106">For more information about cell styles, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="bfce8-107">교대로 반복 되는 행에 대 한 스타일을 설정 하려면 [방법: 디자이너를 사용 하 여 Windows Forms DataGridView 컨트롤의 교대로 반복 되는 행 스타일 설정](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfce8-107">To set styles for alternating rows, see [How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).</span></span>

<span data-ttu-id="bfce8-108"><xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성을 사용 하 여 컨트롤에 추가 되는 모든 행에 영향을 주는 스타일을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-108">You can also set styles using the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property to affect all rows that will be added to the control.</span></span> <span data-ttu-id="bfce8-109">행 템플릿에 대 한 자세한 내용은 [방법: 행 템플릿을 사용 하 여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정](use-the-row-template-to-customize-rows-in-the-datagrid.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfce8-109">For more information about the row template, see [How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control](use-the-row-template-to-customize-rows-in-the-datagrid.md).</span></span>

<span data-ttu-id="bfce8-110">다음 절차에는 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 폼이 포함 된 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-110">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bfce8-111">이러한 프로젝트를 설정 하는 방법에 대 한 자세한 내용은 [방법: Windows Forms 응용 프로그램 프로젝트 만들기](/visualstudio/ide/step-1-create-a-windows-forms-application-project) 및 [방법: Windows Forms에 컨트롤 추가](how-to-add-controls-to-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bfce8-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a><span data-ttu-id="bfce8-112">컨트롤의 모든 셀에 대 한 기본 스타일을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bfce8-112">To set default styles for all cells in the control</span></span>

1. <span data-ttu-id="bfce8-113">디자이너에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-113">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="bfce8-114">**속성** 창에서 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여 Visual](./media/visual-studio-ellipsis-button.png)Studio의 속성 창에 있는 줄임표 단추 (...)를![합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-114">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property.</span></span> <span data-ttu-id="bfce8-115">**CellStyle 작성기** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-115">The **CellStyle Builder** dialog box appears.</span></span>

3. <span data-ttu-id="bfce8-116">**미리 보기** 창을 사용 하 여 선택 내용을 확인 하 고 속성을 설정 하 여 스타일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-116">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

> [!NOTE]
> <span data-ttu-id="bfce8-117">비주얼 스타일을 사용 하는 경우 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>를 제외 하 고 행 및 열 머리글은 현재 테마에 의해 자동으로 스타일 지정 되어 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-117">If visual styles are enabled, the row and column headers (except for the <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) are automatically styled by the current theme, overriding the <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> property values.</span></span>
>
> <span data-ttu-id="bfce8-118">디자이너를 사용 하 여 선택한 여러 <xref:System.Windows.Forms.DataGridView> 컨트롤의 셀 스타일을 설정할 수 있지만 수정할 셀 스타일 속성에 대해 동일한 값이 있는 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-118">You can set cell styles for multiple selected <xref:System.Windows.Forms.DataGridView> controls using the designer, but only if they have identical values for the cell style property you want to modify.</span></span> <span data-ttu-id="bfce8-119">해당 속성에 대 한 셀 스타일이 다른 경우에는 **CellStyle 작성기** 대화 상자의 **속성** 창이 비어 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-119">If any cell styles differ for that property, the **Properties** windows of the **CellStyle Builder** dialog box will be blank.</span></span>

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a><span data-ttu-id="bfce8-120">개별 열의 셀에 대 한 기본 스타일을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="bfce8-120">To set default styles for cells in individual columns</span></span>

1. <span data-ttu-id="bfce8-121">디자이너에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 마우스 오른쪽 단추로 클릭 하 고 **열 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-121">Right-click the <xref:System.Windows.Forms.DataGridView> control in the designer and choose **Edit Columns**.</span></span>

2. <span data-ttu-id="bfce8-122">**선택한 열** 목록에서 열을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-122">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="bfce8-123">**열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여 Visual](./media/visual-studio-ellipsis-button.png)Studio의 속성 창에 있는 줄임표 단추 (...)를![합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-123">In the **Column Properties** grid, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> property.</span></span> <span data-ttu-id="bfce8-124">**CellStyle 작성기** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-124">The **CellStyle Builder** dialog box appears.</span></span>

4. <span data-ttu-id="bfce8-125">**미리 보기** 창을 사용 하 여 선택 내용을 확인 하 고 속성을 설정 하 여 스타일을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-125">Define the style by setting the properties, using the **Preview** pane to confirm your choices.</span></span>

### <a name="to-format-data-in-cells"></a><span data-ttu-id="bfce8-126">셀의 데이터에 서식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="bfce8-126">To format data in cells</span></span>

1. <span data-ttu-id="bfce8-127">위의 절차 중 하나를 사용 하 여 기본 셀 스타일 속성과 관련 된 **CellStyle 작성기** 대화 상자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-127">Use one of the preceding procedures to display a **CellStyle Builder** dialog box related to a default cell style property.</span></span>

2. <span data-ttu-id="bfce8-128">**CellStyle 작성기** 대화 상자에서 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여 Visual](./media/visual-studio-ellipsis-button.png)Studio의 속성 창에 있는 줄임표 단추 (...)를![합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-128">In the **CellStyle Builder** dialog box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> property.</span></span> <span data-ttu-id="bfce8-129">**형식 문자열** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-129">The **Format String** dialog box appears.</span></span>

3. <span data-ttu-id="bfce8-130">서식 유형을 선택한 다음 **샘플** 상자를 사용 하 여 선택 항목을 확인 하는 유형의 세부 정보 (예: 표시할 소수 자릿수)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-130">Select a format type, then modify the details of the type (such as the number of decimal places to display), using the **Sample** box to confirm your choices.</span></span>

4. <span data-ttu-id="bfce8-131"><xref:System.Windows.Forms.DataGridView> 컨트롤을 null 값이 포함 될 수 있는 데이터 소스에 바인딩하는 경우 **Null 값** 텍스트 상자에 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-131">If you are binding the <xref:System.Windows.Forms.DataGridView> control to a data source that is likely to contain null values, fill in the **Null Value** text box.</span></span> <span data-ttu-id="bfce8-132">이 값은 셀 값이 null 참조 (Visual Basic의`Nothing`)와 같거나 <xref:System.DBNull.Value?displayProperty=nameWithType>경우에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfce8-132">This value is displayed when the cell value is equal to a null reference (`Nothing` in Visual Basic) or <xref:System.DBNull.Value?displayProperty=nameWithType>.</span></span>

## <a name="see-also"></a><span data-ttu-id="bfce8-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfce8-133">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [<span data-ttu-id="bfce8-134">Windows Forms DataGridView 컨트롤의 셀 스타일</span><span class="sxs-lookup"><span data-stu-id="bfce8-134">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="bfce8-135">방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정</span><span class="sxs-lookup"><span data-stu-id="bfce8-135">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="bfce8-136">방법: Windows Forms 응용 프로그램 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="bfce8-136">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="bfce8-137">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="bfce8-137">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
