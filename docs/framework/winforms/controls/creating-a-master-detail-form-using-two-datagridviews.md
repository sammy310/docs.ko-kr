---
title: '연습: 두 개의 DataGridView 컨트롤을 사용 하 여 마스터-세부 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: bb3da36430c7493b941f3711cb584b4517d5bd54
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740576"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="644d5-102">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="644d5-102">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>

<span data-ttu-id="644d5-103"><xref:System.Windows.Forms.DataGridView> 컨트롤 사용에 대 한 가장 일반적인 시나리오 중 하나는 두 데이터베이스 테이블 간의 부모/자식 관계가 표시 되는 *마스터/세부* 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-103">One of the most common scenarios for using the <xref:System.Windows.Forms.DataGridView> control is the *master/detail* form, in which a parent/child relationship between two database tables is displayed.</span></span> <span data-ttu-id="644d5-104">마스터 테이블에서 행을 선택 하면 세부 정보 테이블이 해당 자식 데이터로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-104">Selecting rows in the master table causes the detail table to update with the corresponding child data.</span></span>

<span data-ttu-id="644d5-105"><xref:System.Windows.Forms.DataGridView> 컨트롤과 <xref:System.Windows.Forms.BindingSource> 구성 요소 간의 상호 작용을 사용 하 여 마스터/세부 폼을 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-105">Implementing a master/detail form is easy using the interaction between the <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="644d5-106">이 연습에서는 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용 하 여 폼을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-106">In this walkthrough, you will build the form using two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="644d5-107">양식은 Northwind SQL Server 예제 데이터베이스에 두 개의 관련 테이블을 표시 합니다. `Customers` 및 `Orders`.</span><span class="sxs-lookup"><span data-stu-id="644d5-107">The form will show two related tables in the Northwind SQL Server sample database: `Customers` and `Orders`.</span></span> <span data-ttu-id="644d5-108">작업이 완료 되 면 데이터베이스의 모든 고객을 마스터 <xref:System.Windows.Forms.DataGridView>에 표시 하 고 선택한 고객에 대 한 모든 주문을 세부 <xref:System.Windows.Forms.DataGridView>에 표시 하는 양식이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-108">When you are finished, you will have a form that shows all the customers in the database in the master <xref:System.Windows.Forms.DataGridView> and all the orders for the selected customer in the detail <xref:System.Windows.Forms.DataGridView>.</span></span>

<span data-ttu-id="644d5-109">이 항목의 코드를 단일 목록으로 복사 하려면 [방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터/세부 폼 만들기](create-a-master-detail-form-using-two-datagridviews.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-109">To copy the code in this topic as a single listing, see [How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls](create-a-master-detail-form-using-two-datagridviews.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="644d5-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="644d5-110">Prerequisites</span></span>

<span data-ttu-id="644d5-111">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="644d5-112">Northwind SQL Server 예제 데이터베이스가 있는 서버에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-112">Access to a server that has the Northwind SQL Server sample database.</span></span>

## <a name="creating-the-form"></a><span data-ttu-id="644d5-113">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="644d5-113">Creating the form</span></span>

#### <a name="to-create-a-masterdetail-form"></a><span data-ttu-id="644d5-114">마스터/세부 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="644d5-114">To create a master/detail form</span></span>

1. <span data-ttu-id="644d5-115"><xref:System.Windows.Forms.Form>에서 파생 되 고 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤과 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소를 포함 하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-115">Create a class that derives from <xref:System.Windows.Forms.Form> and contains two <xref:System.Windows.Forms.DataGridView> controls and two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="644d5-116">다음 코드는 기본 폼 초기화를 제공 하며 `Main` 메서드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-116">The following code provides basic form initialization and includes a `Main` method.</span></span> <span data-ttu-id="644d5-117">Visual Studio 디자이너를 사용 하 여 폼을 만드는 경우이 코드 대신 디자이너에서 생성 한 코드를 사용할 수 있지만 여기에 변수 선언에 표시 된 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-117">If you use the Visual Studio designer to create your form, you can use the designer generated code instead of this code, but be sure to use the names shown in the variable declarations here.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. <span data-ttu-id="644d5-118">데이터베이스에 연결 하는 세부 정보를 처리 하기 위해 폼의 클래스 정의에 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-118">Implement a method in your form's class definition for handling the detail of connecting to the database.</span></span> <span data-ttu-id="644d5-119">이 예제에서는 <xref:System.Data.DataSet> 개체를 채우고 <xref:System.Data.DataRelation> 개체를 데이터 집합에 추가 하 고 <xref:System.Windows.Forms.BindingSource> 구성 요소를 바인딩하는 `GetData` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-119">This example uses a `GetData` method that populates a <xref:System.Data.DataSet> object, adds a <xref:System.Data.DataRelation> object to the data set, and binds the <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="644d5-120">`connectionString` 변수를 사용자의 데이터베이스에 적합한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-120">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="644d5-121">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-121">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="644d5-122">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-122">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="644d5-123">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-123">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. <span data-ttu-id="644d5-124"><xref:System.Windows.Forms.DataGridView> 컨트롤을 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩하고 `GetData` 메서드를 호출 하는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-124">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that binds the <xref:System.Windows.Forms.DataGridView> controls to the <xref:System.Windows.Forms.BindingSource> components and calls the `GetData` method.</span></span> <span data-ttu-id="644d5-125">다음 예제에는 표시 된 데이터에 맞게 <xref:System.Windows.Forms.DataGridView> 열의 크기를 조정 하는 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-125">The following example includes code that resizes <xref:System.Windows.Forms.DataGridView> columns to fit the displayed data.</span></span>

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a><span data-ttu-id="644d5-126">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="644d5-126">Testing the Application</span></span>

<span data-ttu-id="644d5-127">이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-127">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="644d5-128">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="644d5-128">To test the form</span></span>

- <span data-ttu-id="644d5-129">애플리케이션을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-129">Compile and run the application.</span></span>

  <span data-ttu-id="644d5-130">두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤 중 하나를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-130">You will see two <xref:System.Windows.Forms.DataGridView> controls, one above the other.</span></span> <span data-ttu-id="644d5-131">위쪽은 Northwind `Customers` 테이블의 고객이 고 하단에는 선택한 고객에 해당 하는 `Orders`입니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-131">On top are the customers from the Northwind `Customers` table, and at the bottom are the `Orders` corresponding to the selected customer.</span></span> <span data-ttu-id="644d5-132">위쪽 <xref:System.Windows.Forms.DataGridView>에서 다른 행을 선택 하면 그에 따라 아래쪽의 내용이 변경 <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="644d5-132">As you select different rows in the upper <xref:System.Windows.Forms.DataGridView>, the contents of the lower <xref:System.Windows.Forms.DataGridView> change accordingly.</span></span>

## <a name="next-steps"></a><span data-ttu-id="644d5-133">다음 단계</span><span class="sxs-lookup"><span data-stu-id="644d5-133">Next Steps</span></span>

<span data-ttu-id="644d5-134">이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤의 기능에 대 한 기본적인 이해를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-134">This application gives you a basic understanding of the <xref:System.Windows.Forms.DataGridView> control's capabilities.</span></span> <span data-ttu-id="644d5-135">여러 가지 방법으로 <xref:System.Windows.Forms.DataGridView> 컨트롤의 모양과 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-135">You can customize the appearance and behavior of the <xref:System.Windows.Forms.DataGridView> control in several ways:</span></span>

- <span data-ttu-id="644d5-136">테두리 및 머리글 스타일을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-136">Change border and header styles.</span></span> <span data-ttu-id="644d5-137">자세한 내용은 [방법: 테두리 및 Windows Forms DataGridView 컨트롤의 모눈선 스타일 변경](change-the-border-and-gridline-styles-in-the-datagrid.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-137">For more information, see [How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).</span></span>

- <span data-ttu-id="644d5-138">사용자 입력을 <xref:System.Windows.Forms.DataGridView> 컨트롤로 설정 하거나 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-138">Enable or restrict user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="644d5-139">자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 행 추가 및 삭제 방지](prevent-row-addition-and-deletion-datagridview.md)및 [방법: Windows Forms Datagridview 컨트롤에서 열을 읽기 전용으로 설정](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-139">For more information, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), and [How to: Make Columns Read-Only in the Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="644d5-140"><xref:System.Windows.Forms.DataGridView> 컨트롤에 대 한 사용자 입력의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-140">Validate user input to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="644d5-141">자세한 내용은 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-141">For more information, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>

- <span data-ttu-id="644d5-142">가상 모드를 사용 하 여 매우 큰 데이터 집합을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-142">Handle very large data sets using virtual mode.</span></span> <span data-ttu-id="644d5-143">자세한 내용은 [연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현](implementing-virtual-mode-wf-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-143">For more information, see [Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control](implementing-virtual-mode-wf-datagridview-control.md).</span></span>

- <span data-ttu-id="644d5-144">셀의 모양을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="644d5-144">Customize the appearance of cells.</span></span> <span data-ttu-id="644d5-145">자세한 내용은 [방법: Datagridview 컨트롤 Windows Forms에서 셀 모양 사용자 지정](customize-the-appearance-of-cells-in-the-datagrid.md) 및 [방법: Windows Forms Datagridview 컨트롤의 기본 셀 스타일 설정](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="644d5-145">For more information, see [How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control](customize-the-appearance-of-cells-in-the-datagrid.md) and [How to: Set Default Cell Styles for the Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="644d5-146">참조</span><span class="sxs-lookup"><span data-stu-id="644d5-146">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="644d5-147">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="644d5-147">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="644d5-148">방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="644d5-148">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](create-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="644d5-149">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="644d5-149">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
