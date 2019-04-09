---
title: '방법: Windows Forms에 컨트롤 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 72b5931a79284a93a4e0fdf3cb2cc3b03157f5f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106485"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="47035-102">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="47035-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="47035-103">대부분의 폼은 사용자 인터페이스 (UI)를 정의 하도록 폼의 화면에 컨트롤을 추가 하 여 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="47035-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="47035-104">A *제어* 정보를 표시 하거나 사용자 입력을 허용 하는 데 양식의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="47035-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="47035-105">컨트롤에 대 한 자세한 내용은 참조 하세요. [Windows Forms 컨트롤](index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47035-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47035-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="47035-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="47035-108">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47035-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="47035-109">폼에서 컨트롤을 그리려면</span><span class="sxs-lookup"><span data-stu-id="47035-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="47035-110">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47035-110">Open the form.</span></span> <span data-ttu-id="47035-111">자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-111">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="47035-112">에 **도구 상자**, 폼에 추가 하려는 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="47035-113">폼에 배치 될 컨트롤의 왼쪽 위 모퉁이 위치를 클릭 하 고 찾을 컨트롤의 오른쪽 아래 모서리를 원하는 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="47035-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="47035-114">컨트롤의 지정 된 위치와 크기를 사용 하 여 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47035-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47035-115">각 컨트롤의 기본 크기는 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-115">Each control has a default size defined.</span></span> <span data-ttu-id="47035-116">끌어 오지 여 컨트롤의 기본 크기의 폼에 컨트롤을 추가할 수 있습니다 합니다 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="47035-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="47035-117">폼에 컨트롤을 끌기</span><span class="sxs-lookup"><span data-stu-id="47035-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="47035-118">폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="47035-118">Open the form.</span></span> <span data-ttu-id="47035-119">자세한 내용은 [방법: Windows Forms 디자이너에서 표시할](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-119">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="47035-120">에 **도구 상자**, 클릭 컨트롤을 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="47035-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="47035-121">컨트롤의 기본 크기로 지정된 된 위치에서 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47035-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47035-122">컨트롤을 두 번 클릭 수를 **도구 상자** 기본 크기의 폼의 왼쪽 위 모퉁이에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="47035-123">또한 컨트롤 추가할 수 있습니다 동적으로 폼에 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="47035-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="47035-124">다음 코드 예제에서를 <xref:System.Windows.Forms.TextBox> 컨트롤이 폼에 추가 될 때를 <xref:System.Windows.Forms.Button> 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47035-125">다음 절차에 사용 하 여 폼의 존재 여부 필요는 **단추** 컨트롤 `Button1`, 이미 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="47035-126">프로그래밍 방식으로 폼에 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="47035-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="47035-127">단추를 처리 하는 방법에 `Click` 이벤트 클래스 폼의 컨트롤 변수에 대 한 참조를 추가 하려면 다음과 비슷한 삽입 코드 내에서 컨트롤의 설정 `Location`, 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="47035-128">또한 컨트롤의 다른 속성을 초기화 하는 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47035-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="47035-129">악성 참조 하 여 로컬 컴퓨터가 네트워크를 통해 보안 위험에 노출 될 수 있습니다 `UserControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="47035-130">이 악의적인 사용자 실수로 프로젝트에 추가 하 여 사용자가 팔 로우 하는 손상을 일으킬 수 있는 사용자 지정 컨트롤을 만드는 경우 문제가 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47035-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47035-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="47035-131">See also</span></span>

- [<span data-ttu-id="47035-132">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="47035-132">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="47035-133">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="47035-133">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="47035-134">방법: Windows Forms에서 컨트롤 크기 조정</span><span class="sxs-lookup"><span data-stu-id="47035-134">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="47035-135">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="47035-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="47035-136">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="47035-136">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
