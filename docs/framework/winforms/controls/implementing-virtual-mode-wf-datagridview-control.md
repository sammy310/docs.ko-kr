---
title: '연습: DataGridView 컨트롤에서 가상 모드 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 5db97b321238bc371c94e627a387bd83ca31b58a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746521"
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="49d2a-102">연습: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="49d2a-102">Walkthrough: Implementing Virtual Mode in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="49d2a-103"><xref:System.Windows.Forms.DataGridView> 컨트롤에 매우 많은 양의 테이블 형식 데이터를 표시 하려는 경우 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> 속성을 `true`로 설정 하 고 컨트롤의 데이터 저장소와의 상호 작용을 명시적으로 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-103">When you want to display very large quantities of tabular data in a <xref:System.Windows.Forms.DataGridView> control, you can set the <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> property to `true` and explicitly manage the control's interaction with its data store.</span></span> <span data-ttu-id="49d2a-104">이렇게 하면이 상황에서 컨트롤의 성능을 세밀 하 게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-104">This lets you fine-tune the performance of the control in this situation.</span></span>  
  
 <span data-ttu-id="49d2a-105"><xref:System.Windows.Forms.DataGridView> 컨트롤은 사용자 지정 데이터 저장소와 상호 작용 하기 위해 처리할 수 있는 몇 가지 이벤트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-105">The <xref:System.Windows.Forms.DataGridView> control provides several events that you can handle to interact with a custom data store.</span></span> <span data-ttu-id="49d2a-106">이 연습에서는 이러한 이벤트 처리기를 구현 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-106">This walkthrough guides you through the process of implementing these event handlers.</span></span> <span data-ttu-id="49d2a-107">이 항목의 코드 예제에서는 매우 간단한 데이터 원본을 설명 하기 위해 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-107">The code example in this topic uses a very simple data source for illustration purposes.</span></span> <span data-ttu-id="49d2a-108">프로덕션 설정에서는 일반적으로 캐시에 표시 해야 하는 행만 로드 하 고 캐시를 상호 작용 하 고 업데이트 하는 <xref:System.Windows.Forms.DataGridView> 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-108">In a production setting, you will typically load only the rows you need to display into a cache, and handle <xref:System.Windows.Forms.DataGridView> events to interact with and update the cache.</span></span> <span data-ttu-id="49d2a-109">자세한 내용은 [Windows Forms DataGridView 컨트롤에서 Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d2a-109">For more information, see [Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)</span></span>  
  
 <span data-ttu-id="49d2a-110">이 항목의 코드를 단일 목록으로 복사 하려면 [방법: DataGridView 컨트롤 Windows Forms에서 가상 모드 구현](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d2a-110">To copy the code in this topic as a single listing, see [How to: Implement Virtual Mode in the Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="creating-the-form"></a><span data-ttu-id="49d2a-111">폼 만들기</span><span class="sxs-lookup"><span data-stu-id="49d2a-111">Creating the Form</span></span>  
  
#### <a name="to-implement-virtual-mode"></a><span data-ttu-id="49d2a-112">가상 모드를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="49d2a-112">To implement virtual mode</span></span>  
  
1. <span data-ttu-id="49d2a-113"><xref:System.Windows.Forms.Form>에서 파생 되 고 <xref:System.Windows.Forms.DataGridView> 컨트롤을 포함 하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-113">Create a class that derives from <xref:System.Windows.Forms.Form> and contains a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
     <span data-ttu-id="49d2a-114">다음 코드에는 몇 가지 기본 초기화가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-114">The following code contains some basic initialization.</span></span> <span data-ttu-id="49d2a-115">이후 단계에서 사용 되는 일부 변수를 선언 하 고, `Main` 메서드를 제공 하며, 클래스 생성자에서 간단한 양식 레이아웃을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-115">It declares some variables that will be used in later steps, provides a `Main` method, and provides a simple form layout in the class constructor.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2. <span data-ttu-id="49d2a-116"><xref:System.Windows.Forms.DataGridView> 컨트롤을 초기화 하 고 데이터 저장소를 샘플 값으로 채우는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-116">Implement a handler for your form's <xref:System.Windows.Forms.Form.Load> event that initializes the <xref:System.Windows.Forms.DataGridView> control and populates the data store with sample values.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3. <span data-ttu-id="49d2a-117">현재 편집 중인 데이터 저장소 또는 `Customer` 개체에서 요청 된 셀 값을 검색 하는 <xref:System.Windows.Forms.DataGridView.CellValueNeeded> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-117">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValueNeeded> event that retrieves the requested cell value from the data store or the `Customer` object currently in edit.</span></span>  
  
     <span data-ttu-id="49d2a-118">이 이벤트는 <xref:System.Windows.Forms.DataGridView> 컨트롤이 셀을 그려야 할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-118">This event occurs whenever the <xref:System.Windows.Forms.DataGridView> control needs to paint a cell.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4. <span data-ttu-id="49d2a-119">편집 된 행을 나타내는 `Customer` 개체에 편집 된 셀 값을 저장 하는 <xref:System.Windows.Forms.DataGridView.CellValuePushed> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-119">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CellValuePushed> event that stores an edited cell value in the `Customer` object representing the edited row.</span></span> <span data-ttu-id="49d2a-120">이 이벤트는 사용자가 셀 값 변경 내용을 커밋할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-120">This event occurs whenever the user commits a cell value change.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5. <span data-ttu-id="49d2a-121">새로 만든 행을 나타내는 새 `Customer` 개체를 만드는 <xref:System.Windows.Forms.DataGridView.NewRowNeeded> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-121">Implement a handler for the <xref:System.Windows.Forms.DataGridView.NewRowNeeded> event that creates a new `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="49d2a-122">이 이벤트는 사용자가 새 레코드에 대 한 행을 입력할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-122">This event occurs whenever the user enters the row for new records.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6. <span data-ttu-id="49d2a-123">새 행 또는 수정 된 행을 데이터 저장소에 저장 하는 <xref:System.Windows.Forms.DataGridView.RowValidated> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-123">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowValidated> event that saves new or modified rows to the data store.</span></span>  
  
     <span data-ttu-id="49d2a-124">이 이벤트는 사용자가 현재 행을 변경할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-124">This event occurs whenever the user changes the current row.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7. <span data-ttu-id="49d2a-125">사용자가 편집 모드에서 ESC 키를 두 번 누르거나 편집 모드 외부에서 변경할지 때 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트가 발생 하는지 여부를 나타내는 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-125">Implement a handler for the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event that indicates whether the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event will occur when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span>  
  
     <span data-ttu-id="49d2a-126">기본적으로 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성이 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 `true`로 설정 되지 않은 경우 현재 행의 셀이 수정 되 면 행 변경할지 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-126">By default, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> occurs upon row reversion when any cells in the current row have been modified unless the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property is set to `true` in the <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span> <span data-ttu-id="49d2a-127">이 이벤트는 커밋 범위가 런타임에 결정 되는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-127">This event is useful when the commit scope is determined at run time.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8. <span data-ttu-id="49d2a-128">현재 행을 나타내는 `Customer` 개체의 값을 삭제 하는 <xref:System.Windows.Forms.DataGridView.CancelRowEdit> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-128">Implement a handler for the <xref:System.Windows.Forms.DataGridView.CancelRowEdit> event that discards the values of the `Customer` object representing the current row.</span></span>  
  
     <span data-ttu-id="49d2a-129">사용자가 편집 모드에서 ESC 키를 두 번 누르거나 편집 모드 외부에서 변경할지 때이 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-129">This event occurs when the user signals row reversion by pressing ESC twice in edit mode or once outside of edit mode.</span></span> <span data-ttu-id="49d2a-130">현재 행의 셀이 수정 되지 않았거나 <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> 속성 값이 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> 이벤트 처리기에서 `false`로 설정 된 경우에는이 이벤트가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-130">This event does not occur if no cells in the current row have been modified or if the value of the <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> property has been set to `false` in a <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. <span data-ttu-id="49d2a-131">데이터 저장소에서 기존 `Customer` 개체를 삭제 하거나 새로 만든 행을 나타내는 저장 되지 않은 `Customer` 개체를 삭제 하는 <xref:System.Windows.Forms.DataGridView.UserDeletingRow> 이벤트에 대 한 처리기를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-131">Implement a handler for the <xref:System.Windows.Forms.DataGridView.UserDeletingRow> event that deletes an existing `Customer` object from the data store or discards an unsaved `Customer` object representing a newly created row.</span></span>  
  
     <span data-ttu-id="49d2a-132">이 이벤트는 사용자가 행 머리글을 클릭 하 고 DELETE 키를 눌러 행을 삭제할 때마다 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-132">This event occurs whenever the user deletes a row by clicking a row header and pressing the DELETE key.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. <span data-ttu-id="49d2a-133">이 코드 예제에서 사용 하는 데이터 항목을 나타내는 간단한 `Customers` 클래스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-133">Implement a simple `Customers` class to represent the data items used by this code example.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="49d2a-134">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="49d2a-134">Testing the Application</span></span>  
 <span data-ttu-id="49d2a-135">이제 폼을 테스트 하 여 예상 대로 동작 하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-135">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="49d2a-136">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="49d2a-136">To test the form</span></span>  
  
- <span data-ttu-id="49d2a-137">애플리케이션을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-137">Compile and run the application.</span></span>  
  
     <span data-ttu-id="49d2a-138">3 개의 고객 레코드로 채워진 <xref:System.Windows.Forms.DataGridView> 컨트롤이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-138">You will see a <xref:System.Windows.Forms.DataGridView> control populated with three customer records.</span></span> <span data-ttu-id="49d2a-139">행에서 여러 셀의 값을 수정 하 고 편집 모드에서 ESC 키를 두 번 누르고 편집 모드 외부에서 한 번을 눌러 전체 행을 원래 값으로 되돌릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-139">You can modify the values of multiple cells in a row and press ESC twice in edit mode and once outside of edit mode to revert the entire row to its original values.</span></span> <span data-ttu-id="49d2a-140">컨트롤에서 행을 수정, 추가 또는 삭제 하는 경우 데이터 저장소의 `Customer` 개체도 수정, 추가 또는 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-140">When you modify, add, or delete rows in the control, `Customer` objects in the data store are modified, added, or deleted as well.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="49d2a-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="49d2a-141">Next Steps</span></span>  
 <span data-ttu-id="49d2a-142">이 응용 프로그램은 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 가상 모드를 구현 하기 위해 처리 해야 하는 이벤트에 대 한 기본적인 이해를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-142">This application gives you a basic understanding of the events you must handle to implement virtual mode in the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="49d2a-143">여러 가지 방법으로이 기본 응용 프로그램을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-143">You can improve this basic application in a number of ways:</span></span>  
  
- <span data-ttu-id="49d2a-144">외부 데이터베이스의 값을 캐시 하는 데이터 저장소를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-144">Implement a data store that caches values from an external database.</span></span> <span data-ttu-id="49d2a-145">캐시는 클라이언트 컴퓨터에서 적은 양의 메모리를 사용 하는 동안 표시에 필요한 항목만 포함 하도록 필요에 따라 값을 검색 하 고 삭제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-145">The cache should retrieve and discard values as necessary so that it only contains what is necessary for display while consuming a small amount of memory on the client computer.</span></span>  
  
- <span data-ttu-id="49d2a-146">요구 사항에 따라 데이터 저장소의 성능을 미세 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-146">Fine-tune the performance of the data store depending on your requirements.</span></span> <span data-ttu-id="49d2a-147">예를 들어 더 큰 캐시 크기를 사용 하 고 데이터베이스 쿼리 수를 최소화 하 여 클라이언트 컴퓨터 메모리 제한 보다 저속 네트워크 연결을 보정 하려고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49d2a-147">For example, you might want to compensate for slow network connections rather than client-computer memory limitations by using a larger cache size and minimizing the number of database queries.</span></span>  
  
 <span data-ttu-id="49d2a-148">외부 데이터베이스에서 값을 캐싱하는 방법에 대 한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 Just-in-time 데이터 로드를 사용 하 여 가상 모드 구현](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49d2a-148">For more information about caching values from an external database, see [How to: Implement Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control](virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d2a-149">참조</span><span class="sxs-lookup"><span data-stu-id="49d2a-149">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>
- <xref:System.Windows.Forms.DataGridView.CellValueNeeded>
- <xref:System.Windows.Forms.DataGridView.CellValuePushed>
- <xref:System.Windows.Forms.DataGridView.NewRowNeeded>
- <xref:System.Windows.Forms.DataGridView.RowValidated>
- <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>
- <xref:System.Windows.Forms.DataGridView.CancelRowEdit>
- <xref:System.Windows.Forms.DataGridView.UserDeletingRow>
- [<span data-ttu-id="49d2a-150">Windows Forms DataGridView 컨트롤의 성능 조정</span><span class="sxs-lookup"><span data-stu-id="49d2a-150">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49d2a-151">Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="49d2a-151">Best Practices for Scaling the Windows Forms DataGridView Control</span></span>](best-practices-for-scaling-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="49d2a-152">Windows Forms DataGridView 컨트롤에서 Just-In-Time 데이터 로드를 사용하여 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="49d2a-152">Implementing Virtual Mode with Just-In-Time Data Loading in the Windows Forms DataGridView Control</span></span>](implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)
- [<span data-ttu-id="49d2a-153">방법: Windows Forms DataGridView 컨트롤에서 가상 모드 구현</span><span class="sxs-lookup"><span data-stu-id="49d2a-153">How to: Implement Virtual Mode in the Windows Forms DataGridView Control</span></span>](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
