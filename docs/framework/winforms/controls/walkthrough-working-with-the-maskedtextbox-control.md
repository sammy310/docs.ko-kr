---
title: '연습: MaskedTextBox 컨트롤 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: 7f25e21008c77ebf5e55e7affbb4cf07db377c5d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623262"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="68e35-102">연습: MaskedTextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="68e35-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="68e35-103">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-103">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="68e35-104">초기화는 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="68e35-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
- <span data-ttu-id="68e35-105">사용 하는 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 문자 마스크에 맞지 않는 경우 사용자 경고를 발생 시 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="68e35-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
- <span data-ttu-id="68e35-106">에 형식을 할당 합니다 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성과 사용 하는 <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 커밋하려고 시도 하는 값 형식에 대해 유효 하지 않을 때 사용자를 경고 하도록 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="68e35-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="68e35-107">프로젝트 만들기 및 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="68e35-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="68e35-108">MaskedTextBox 컨트롤을 폼에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="68e35-108">To add a MaskedTextBox control to your form</span></span>  
  
1. <span data-ttu-id="68e35-109">배치 하려는 폼을 엽니다는 <xref:System.Windows.Forms.MaskedTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2. <span data-ttu-id="68e35-110">끌어서를 <xref:System.Windows.Forms.MaskedTextBox> 에서 제어 합니다 **도구 상자** 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3. <span data-ttu-id="68e35-111">선택한 컨트롤을 마우스 오른쪽 단추로 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="68e35-112">에 **속성** 창에서 합니다 **마스크** 속성을 클릭 합니다 **...**  속성 이름 옆에 있는 (줄임표) 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4. <span data-ttu-id="68e35-113">에 **입력 마스크** 대화 상자에서를 **짧은 날짜** 마스크 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5. <span data-ttu-id="68e35-114">에 **속성** 창 집합 합니다 <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="68e35-115">이 사용자가 마스크 정의 위반 하는 문자를 입력 하려고 할 때마다 사운드를 짧은 경고음을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="68e35-116">마스크 속성을 지 원하는 문자 요약이의 설명 섹션을 참조 하세요.를 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="68e35-117">오류를 입력 하 여 경으십시오</span><span class="sxs-lookup"><span data-stu-id="68e35-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="68e35-118">거부 된 마스크 입력에 대 한 풍선 추가</span><span class="sxs-lookup"><span data-stu-id="68e35-118">Add a balloon tip for rejected mask input</span></span>  
  
1. <span data-ttu-id="68e35-119">반환 합니다 **도구 상자** 추가 <xref:System.Windows.Forms.ToolTip> 폼에.</span><span class="sxs-lookup"><span data-stu-id="68e35-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2. <span data-ttu-id="68e35-120">이벤트 처리기를 만들 합니다 <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> 이벤트를 발생 시키는 <xref:System.Windows.Forms.ToolTip> 입력된 오류가 발생 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="68e35-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="68e35-121">풍선 5 초 또는 사용자가 클릭 될 때까지 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="68e35-122">잘못 된 형식으로 사용자 경으십시오</span><span class="sxs-lookup"><span data-stu-id="68e35-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="68e35-123">잘못 된 데이터 형식에 대 한 풍선 추가</span><span class="sxs-lookup"><span data-stu-id="68e35-123">Add a balloon tip for invalid data types</span></span>  
  
1. <span data-ttu-id="68e35-124">폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기를 할당을 <xref:System.Type> 나타내는 개체입니다는 <xref:System.DateTime> 를 입력 합니다 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 속성:</span><span class="sxs-lookup"><span data-stu-id="68e35-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2. <span data-ttu-id="68e35-125"><xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> 이벤트에 대한 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e35-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68e35-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="68e35-126">See also</span></span>

- <xref:System.Windows.Forms.MaskedTextBox>
- [<span data-ttu-id="68e35-127">MaskedTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="68e35-127">MaskedTextBox Control</span></span>](maskedtextbox-control-windows-forms.md)
