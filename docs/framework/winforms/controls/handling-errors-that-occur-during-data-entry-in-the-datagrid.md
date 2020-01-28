---
title: '연습: DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738728"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="0fe2d-102">연습: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="0fe2d-102">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>

<span data-ttu-id="0fe2d-103">데이터 입력 응용 프로그램의 경우 기본 데이터 저장소에서 발생 하는 오류를 처리 하는 기능이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-103">Handling errors from the underlying data store is a required feature for a data-entry application.</span></span> <span data-ttu-id="0fe2d-104">Windows Forms <xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 저장소에서 제약 조건 위반 또는 손상 된 비즈니스 규칙을 검색할 때 발생 하는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트를 노출 하 여 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-104">The Windows Forms <xref:System.Windows.Forms.DataGridView> control makes this easy by exposing the <xref:System.Windows.Forms.DataGridView.DataError> event, which is raised when the data store detects a constraint violation or a broken business rule.</span></span>

<span data-ttu-id="0fe2d-105">이 연습에서는 Northwind 샘플 데이터베이스의 `Customers` 테이블에서 행을 검색 하 여 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-105">In this walkthrough, you will retrieve rows from the `Customers` table in the Northwind sample database and display them in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0fe2d-106">새 행 또는 편집 된 기존 행에서 중복 `CustomerID` 값이 검색 되 면 예외를 설명 하는 <xref:System.Windows.Forms.MessageBox>를 표시 하 여 처리 되는 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-106">When a duplicate `CustomerID` value is detected in a new row or an edited existing row, the <xref:System.Windows.Forms.DataGridView.DataError> event will occur, which will be handled by displaying a <xref:System.Windows.Forms.MessageBox> that describes the exception.</span></span>

<span data-ttu-id="0fe2d-107">이 항목의 코드를 단일 목록으로 복사 하려면 [방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생 하는 오류 처리를](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-107">To copy the code in this topic as a single listing, see [How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0fe2d-108">전제 조건</span><span class="sxs-lookup"><span data-stu-id="0fe2d-108">Prerequisites</span></span>

<span data-ttu-id="0fe2d-109">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-109">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="0fe2d-110">Northwind SQL Server 예제 데이터베이스가 있는 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-110">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="0fe2d-111">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="0fe2d-111">Creating the Form</span></span>

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a><span data-ttu-id="0fe2d-112">DataGridView 컨트롤에서 데이터 입력 오류를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="0fe2d-112">To handle data-entry errors in the DataGridView control</span></span>

1. <span data-ttu-id="0fe2d-113"><xref:System.Windows.Forms.Form>에서 파생 되 고 <xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소를 포함 하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control and a <xref:System.Windows.Forms.BindingSource> component.</span></span>

    <span data-ttu-id="0fe2d-114">다음 코드 예제에서는 기본 초기화를 제공 하며 `Main` 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-114">The following code example provides basic initialization and includes a `Main` method.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. <span data-ttu-id="0fe2d-115">데이터베이스 연결에 대 한 세부 정보를 처리 하기 위해 폼의 클래스 정의에 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-115">Implement a method in your form's class definition for handling the details of connecting to the database.</span></span>

    <span data-ttu-id="0fe2d-116">이 코드 예제에서는 채워진 <xref:System.Data.DataTable> 개체를 반환 하는 `GetData` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-116">This code example uses a `GetData` method that returns a populated <xref:System.Data.DataTable> object.</span></span> <span data-ttu-id="0fe2d-117">`connectionString` 변수를 데이터베이스에 적합 한 값으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-117">Be sure that you set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0fe2d-118">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="0fe2d-119">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="0fe2d-120">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. <span data-ttu-id="0fe2d-121"><xref:System.Windows.Forms.DataGridView>를 초기화 하 고 데이터 바인딩을 <xref:System.Windows.Forms.BindingSource> 하 고 설정 하는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-121">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> and <xref:System.Windows.Forms.BindingSource> and sets up the data binding.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. <span data-ttu-id="0fe2d-122"><xref:System.Windows.Forms.DataGridView>에서 <xref:System.Windows.Forms.DataGridView.DataError> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-122">Handle the <xref:System.Windows.Forms.DataGridView.DataError> event on the <xref:System.Windows.Forms.DataGridView>.</span></span>

    <span data-ttu-id="0fe2d-123">오류에 대 한 컨텍스트가 커밋 작업 인 경우 오류를 <xref:System.Windows.Forms.MessageBox>표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-123">If the context for the error is a commit operation, display the error in a <xref:System.Windows.Forms.MessageBox>.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a><span data-ttu-id="0fe2d-124">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="0fe2d-124">Testing the Application</span></span>

<span data-ttu-id="0fe2d-125">이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-125">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="0fe2d-126">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="0fe2d-126">To test the form</span></span>

- <span data-ttu-id="0fe2d-127">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-127">Press F5 to run the application.</span></span>

  <span data-ttu-id="0fe2d-128">Customers 테이블의 데이터로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-128">You will see a <xref:System.Windows.Forms.DataGridView> control filled with data from the Customers table.</span></span> <span data-ttu-id="0fe2d-129">`CustomerID`에 중복 값을 입력 하 고 편집 내용을 커밋하면 셀 값이 자동으로 되돌아가고 데이터 입력 오류를 표시 하는 <xref:System.Windows.Forms.MessageBox> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-129">If you enter a duplicate value for `CustomerID` and commit the edit, the cell value will revert automatically and you will see a <xref:System.Windows.Forms.MessageBox> that displays the data entry error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0fe2d-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0fe2d-130">Next Steps</span></span>

<span data-ttu-id="0fe2d-131">이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대 한 기본적인 이해를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-131">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="0fe2d-132">여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-132">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="0fe2d-133">테두리 및 머리글 스타일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-133">Change border and header styles.</span></span> <span data-ttu-id="0fe2d-134">자세한 내용은 [방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-134">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="0fe2d-135">사용자 입력을 <xref:System.Windows.Forms.DataGridView> 컨트롤로 설정 하거나 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-135">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0fe2d-136">자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 행 추가 및 삭제 방지](prevent-row-addition-and-deletion-datagridview.md)및 [방법: Windows Forms Datagridview 컨트롤에서 열을 읽기 전용으로 설정](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-136">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="0fe2d-137"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대 한 사용자 입력의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-137">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0fe2d-138">자세한 내용은 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-138">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="0fe2d-139">가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-139">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="0fe2d-140">자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-140">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="0fe2d-141">셀의 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-141">Customize the appearance of cells.</span></span> <span data-ttu-id="0fe2d-142">자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms Datagridview 컨트롤의 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0fe2d-142">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0fe2d-143">참조</span><span class="sxs-lookup"><span data-stu-id="0fe2d-143">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="0fe2d-144">Windows Forms DataGridView 컨트롤의 데이터 입력</span><span class="sxs-lookup"><span data-stu-id="0fe2d-144">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0fe2d-145">방법: Windows Forms DataGridView 컨트롤에서 데이터 입력 중에 발생하는 오류 처리</span><span class="sxs-lookup"><span data-stu-id="0fe2d-145">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="0fe2d-146">연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="0fe2d-146">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="0fe2d-147">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="0fe2d-147">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
