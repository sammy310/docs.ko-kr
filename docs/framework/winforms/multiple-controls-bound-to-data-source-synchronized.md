---
title: '방법: 여러 컨트롤을 확인 동일한 데이터 소스에 바인딩된 동기화 된 상태로 유지'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
ms.openlocfilehash: 01cec80c85beb64975648b2250c914fe04d3ac95
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721387"
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a><span data-ttu-id="cdba5-102">방법: 여러 컨트롤을 확인 동일한 데이터 소스에 바인딩된 동기화 된 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="cdba5-102">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>
<span data-ttu-id="cdba5-103">Windows Forms에서 데이터 바인딩을 사용 하 여 작업을 하는 경우에 종종 여러 컨트롤은 동일한 데이터 소스에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-103">Oftentimes when working with data binding in Windows Forms, multiple controls are bound to the same data source.</span></span> <span data-ttu-id="cdba5-104">일부 경우에는 컨트롤의 바인딩된 속성이 서로 데이터 소스를 사용 하 여 동기화 된 상태로 유지 되도록 추가 단계를 수행 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-104">In some cases, it may be necessary to take extra steps to ensure that the bound properties of the controls remain synchronized with each other and the data source.</span></span> <span data-ttu-id="cdba5-105">이러한 단계는 두 가지 상황에서 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-105">These steps are necessary in two situations:</span></span>  
  
-   <span data-ttu-id="cdba5-106">데이터 소스를 구현 하지 않는 경우 <xref:System.ComponentModel.IBindingList>를 생성 하므로 <xref:System.ComponentModel.IBindingList.ListChanged> 유형의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-106">If the data source does not implement <xref:System.ComponentModel.IBindingList>, and therefore generate <xref:System.ComponentModel.IBindingList.ListChanged> events of type <xref:System.ComponentModel.ListChangedType.ItemChanged>.</span></span>  
  
-   <span data-ttu-id="cdba5-107">데이터 원본 구현 <xref:System.ComponentModel.IEditableObject>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-107">If the data source implements <xref:System.ComponentModel.IEditableObject>.</span></span>  
  
 <span data-ttu-id="cdba5-108">전자의 경우에 사용할 수는 <xref:System.Windows.Forms.BindingSource> 데이터 소스 컨트롤에 바인딩할 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-108">In the former case, you can use a <xref:System.Windows.Forms.BindingSource> to bind the data source to the controls.</span></span> <span data-ttu-id="cdba5-109">후자의 경우 사용 하 여는 <xref:System.Windows.Forms.BindingSource> 하 고 처리 합니다 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트 및 호출 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 연결 된 <xref:System.Windows.Forms.BindingManagerBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-109">In the latter case, you use a <xref:System.Windows.Forms.BindingSource> and handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and call <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> on the associated <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdba5-110">예제</span><span class="sxs-lookup"><span data-stu-id="cdba5-110">Example</span></span>  
 <span data-ttu-id="cdba5-111">다음 코드 예제에서는 세 가지 컨트롤을 바인딩하는 방법을 보여 줍니다-두 개의 텍스트 상자 컨트롤 및 <xref:System.Windows.Forms.DataGridView> 컨트롤-동일한 열에 <xref:System.Data.DataSet> 사용 하 여를 <xref:System.Windows.Forms.BindingSource> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-111">The following code example demonstrates how to bind three controls—two text-box controls and a <xref:System.Windows.Forms.DataGridView> control—to the same column in a <xref:System.Data.DataSet> using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="cdba5-112">이 예제에서는 처리 하는 방법에 설명 합니다 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트 하나의 입력란의 텍스트 값 변경 되 면 추가 텍스트 상자를 확인 및 <xref:System.Windows.Forms.DataGridView> 컨트롤은 올바른 값으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-112">This example demonstrates how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event and ensure that when the text value of one text box is changed, the additional text box and the <xref:System.Windows.Forms.DataGridView> control are updated with the correct value.</span></span>  
  
 <span data-ttu-id="cdba5-113">이 예제에서는 사용을 <xref:System.Windows.Forms.BindingSource> 데이터 원본과 컨트롤을 바인딩할 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-113">The example uses a <xref:System.Windows.Forms.BindingSource> to bind the data source and the controls.</span></span> <span data-ttu-id="cdba5-114">또는 데이터 원본에 직접 컨트롤을 바인딩할 수를 검색 합니다 <xref:System.Windows.Forms.BindingManagerBase> 폼의 바인딩에 대 한 <xref:System.Windows.Forms.Control.BindingContext%2A> 처리 및를 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 에 대 한 이벤트는 <xref:System.Windows.Forms.BindingManagerBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-114">Alternatively, you can bind the controls directly to the data source and retrieve the <xref:System.Windows.Forms.BindingManagerBase> for the binding from the form's <xref:System.Windows.Forms.Control.BindingContext%2A> and then handle the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event for the <xref:System.Windows.Forms.BindingManagerBase>.</span></span> <span data-ttu-id="cdba5-115">이 작업을 수행 하는 방법의 예에 대 한 도움말 페이지를 참조 합니다 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 이벤트를 <xref:System.Windows.Forms.BindingManagerBase>입니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-115">For an example of how to do this, see the Help page about the <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> event of <xref:System.Windows.Forms.BindingManagerBase>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdba5-116">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="cdba5-116">Compiling the Code</span></span>  
  
-   <span data-ttu-id="cdba5-117">이 코드 예제에서는</span><span class="sxs-lookup"><span data-stu-id="cdba5-117">This code example requires</span></span>  
  
-   <span data-ttu-id="cdba5-118">
  <xref:System>, <xref:System.Windows.Forms> 및 <xref:System.Drawing> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="cdba5-118">References to the <xref:System>, <xref:System.Windows.Forms>, and <xref:System.Drawing> assemblies.</span></span>  
  
-   <span data-ttu-id="cdba5-119">사용 하 여 폼을 <xref:System.Windows.Forms.Form.Load> 이벤트를 처리 하 고 호출 하는 `InitializeControlsAndDataSource` 폼의 예제에서 메서드 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="cdba5-119">A form with the <xref:System.Windows.Forms.Form.Load> event handled and a call to the `InitializeControlsAndDataSource` method in the example from the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdba5-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="cdba5-120">See also</span></span>
- [<span data-ttu-id="cdba5-121">방법: BindingSource 구성 요소를 사용 하 여 양식 간에 바인딩된 데이터 공유</span><span class="sxs-lookup"><span data-stu-id="cdba5-121">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](./controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)
- [<span data-ttu-id="cdba5-122">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="cdba5-122">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="cdba5-123">데이터 바인딩과 관련된 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cdba5-123">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)
- [<span data-ttu-id="cdba5-124">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="cdba5-124">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
