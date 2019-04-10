---
title: '방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 4d5cc91ca8bf71b2d5893f591652d777041e1a4d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304781"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="ac703-102">방법: Windows Forms BindingNavigator 컨트롤에 로드, 저장 및 취소 단추 추가</span><span class="sxs-lookup"><span data-stu-id="ac703-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="ac703-103">합니다 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 특수 한 용도의 <xref:System.Windows.Forms.ToolStrip> 컨트롤 이동 및 데이터에 바인딩된 폼의 컨트롤을 조작 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="ac703-104">이기 때문에 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 사용자에 대 한 추가 또는 대체 명령 포함 하도록 쉽게 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="ac703-105">다음 절차에는 <xref:System.Windows.Forms.TextBox> 컨트롤이 데이터에 바인딩되는 <xref:System.Windows.Forms.ToolStrip> 폼에 추가 되는 컨트롤 및 취소 단추를 저장, 로드를 포함 하도록 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="ac703-106">부하를 추가 하려면 저장 및 취소 단추가 BindingNavigator 구성 요소</span><span class="sxs-lookup"><span data-stu-id="ac703-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1. <span data-ttu-id="ac703-107">폼에 <xref:System.Windows.Forms.TextBox> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2. <span data-ttu-id="ac703-108">에 바인딩하는 <xref:System.Windows.Forms.BindingSource>, 데이터 원본에 바인딩된 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="ac703-109">예를 들어를 <xref:System.Windows.Forms.BindingSource> 데이터베이스에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3. <span data-ttu-id="ac703-110">데이터 집합 및 테이블 어댑터를 생성 한 후 끌어서를 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4. <span data-ttu-id="ac703-111">설정 된 <xref:System.Windows.Forms.BindingNavigator> 컨트롤의 <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> 속성을는 <xref:System.Windows.Forms.BindingSource> 폼에서 컨트롤에 바인딩되어 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5. <span data-ttu-id="ac703-112"><xref:System.Windows.Forms.BindingNavigator> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6. <span data-ttu-id="ac703-113">스마트 태그 문자 모양을 클릭 (![스마트 태그 문자 모양](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 하므로 **BindingNavigator 태스크** 대화 상자가 나타나고 선택 **항목편집**.</span><span class="sxs-lookup"><span data-stu-id="ac703-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="ac703-114">합니다 **항목 컬렉션 편집기** 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-114">The **Items Collection Editor** appears.</span></span>  
  
7. <span data-ttu-id="ac703-115">에 **항목 컬렉션 편집기**, 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="ac703-116">추가 <xref:System.Windows.Forms.ToolStripSeparator> 및 3 <xref:System.Windows.Forms.ToolStripButton> 적절 한 형식을 선택 하 여 항목 <xref:System.Windows.Forms.ToolStripItem> 를 클릭 하 고는 **추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="ac703-117">설정 된 <xref:System.Windows.Forms.ToolStripItem.Name%2A> 단추 중 속성 **LoadButton**, **저장 단추**, 및 **CancelButton**각각.</span><span class="sxs-lookup"><span data-stu-id="ac703-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="ac703-118">설정 합니다 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 단추 중 속성 **부하**를 **저장**, 및 **취소**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>  
  
    4.  <span data-ttu-id="ac703-119">설정 된 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 각 단추에 대 한 속성 **텍스트**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="ac703-120">또는이 속성 설정할 수 있습니다 **이미지** 또는 **ImageAndText**에 표시할 이미지를 설정 하 고는 <xref:System.Windows.Forms.ToolStripItem.Image%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="ac703-121">클릭 **확인** 대화 상자를 닫습니다. 단추에 추가 되는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8. <span data-ttu-id="ac703-122">폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="ac703-123">코드 편집기에서 데이터 테이블 어댑터를 로드 하는 코드 줄을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="ac703-124">이 코드는 2 단계에서 데이터 바인딩을 설정할 때 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="ac703-125">코드는 다음과 유사 해야 합니다.: `TableAdapterName.Fill(DataSetName.TableName)`합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="ac703-126">양식의 포함 될 가능성이 <xref:System.Windows.Forms.Form.Load> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="ac703-127">이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **부하** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든이 데이터 로딩 코드를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="ac703-128">이제 코드가 다음과 비슷하게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-128">Your code should now look similar to the following:</span></span>  
  
    ```vb  
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click  
        TableAdapterName.Fill(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void LoadButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Fill(DataSetName.TableName);  
    }  
    ```  
  
11. <span data-ttu-id="ac703-129">이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **저장** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든 및 테이블 컨트롤 내에서 데이터를 업데이트 하는 코드 작성에 바인딩되어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
    ```vb  
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click  
        TableAdapterName.Update(DataSetName.TableName)  
    End Sub  
    ```  
  
    ```csharp  
    private void SaveButton_Click(System.Object sender,   
        System.EventArgs e)  
    {  
        TableAdapterName.Update(DataSetName.TableName);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="ac703-130">일부 경우에는 <xref:System.Windows.Forms.BindingNavigator> 구성 요소는 이미를 **저장** 단추에만 코드 없이 생성 된 Windows Forms 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a **Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="ac703-131">이 경우에 앞의 코드를 배치할 수 있습니다 합니다 <xref:System.Windows.Forms.ToolStripItem.Click> 에서 새 단추를 만드는 대신 해당 단추에 대 한 이벤트 처리기는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="ac703-132">그러나 설정 해야 하므로 기본적으로 단추가 비활성화 되는 합니다 <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> 단추 속성 `true` 단추 함수를 올바르게 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>
  
12. <span data-ttu-id="ac703-133">이벤트 처리기를 만듭니다는 <xref:System.Windows.Forms.ToolStripItem.Click> 의 이벤트를 **취소** <xref:System.Windows.Forms.ToolStripButton> 이전에 만든 및 표시 되는 데이터 레코드의 모든 변경 내용을 취소 하는 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
    ```vb  
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click  
        BindingSourceName.CancelEdit()  
    End Sub  
    ```  
  
    ```csharp  
    private void CancelButton_Click(System.Object sender, System.EventArgs e)  
    {  
        BindingSourceName.CancelEdit();  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ac703-134"><xref:System.Windows.Forms.BindingSource.CancelEdit%2A> 메서드는 데이터의 행에 범위가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="ac703-135">다음 레코드로 이동 하기 전에 해당 개별 레코드를 보고 하는 동안 수행한 모든 변경 내용 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac703-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac703-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="ac703-136">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="ac703-137">BindingNavigator 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ac703-137">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="ac703-138">BindingSource 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="ac703-138">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
