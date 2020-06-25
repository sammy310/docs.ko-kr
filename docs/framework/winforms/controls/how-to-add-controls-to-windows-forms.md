---
title: 컨트롤 추가
description: Windows Form에 컨트롤을 그리는 방법에 대해 알아봅니다. 컨트롤은 정보를 표시 하거나 사용자 입력을 수락 하는 데 사용할 수 있는 폼의 구성 요소입니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: d9ab0d78fa0153cce20fb17d22f6e9e781229ece
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325885"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="5b836-104">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5b836-104">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="5b836-105">대부분의 폼은 UI (사용자 인터페이스)를 정의 하기 위해 폼의 화면에 컨트롤을 추가 하 여 디자인 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-105">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="5b836-106">*컨트롤* 은 정보를 표시 하거나 사용자 입력을 수락 하는 데 사용 되는 폼의 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-106">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="5b836-107">컨트롤에 대 한 자세한 내용은 [Windows Forms controls](index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b836-107">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="5b836-108">폼에 컨트롤을 그리려면</span><span class="sxs-lookup"><span data-stu-id="5b836-108">To draw a control on a form</span></span>

1. <span data-ttu-id="5b836-109">양식을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-109">Open the form.</span></span> <span data-ttu-id="5b836-110">자세한 내용은 [방법: 디자이너에서 Windows Forms 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b836-110">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="5b836-111">**도구 상자**에서 폼에 추가 하려는 컨트롤을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-111">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="5b836-112">폼에서 컨트롤의 왼쪽 위 모퉁이를 배치할 위치를 클릭 하 고 컨트롤의 오른쪽 아래 모퉁이를 배치할 위치를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-112">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="5b836-113">지정 된 위치와 크기를 사용 하 여 컨트롤이 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-113">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b836-114">각 컨트롤에는 기본 크기가 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-114">Each control has a default size defined.</span></span> <span data-ttu-id="5b836-115">컨트롤을 **도구 상자** 에서 폼으로 끌어서 컨트롤의 기본 크기로 폼에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-115">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="5b836-116">컨트롤을 폼으로 끌려면</span><span class="sxs-lookup"><span data-stu-id="5b836-116">To drag a control to a form</span></span>

1. <span data-ttu-id="5b836-117">양식을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-117">Open the form.</span></span> <span data-ttu-id="5b836-118">자세한 내용은 [방법: 디자이너에서 Windows Forms 표시](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b836-118">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="5b836-119">**도구 상자**에서 원하는 컨트롤을 클릭 하 여 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-119">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="5b836-120">컨트롤이 기본 크기의 지정 된 위치에 폼에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-120">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b836-121">**도구 상자** 에서 컨트롤을 두 번 클릭 하 여 기본 크기로 폼의 왼쪽 위 모퉁이에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-121">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="5b836-122">런타임에 컨트롤을 폼에 동적으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-122">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="5b836-123">다음 코드 예제에서는 컨트롤을 <xref:System.Windows.Forms.TextBox> 클릭할 때 폼에 컨트롤이 추가 됩니다 <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="5b836-123">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5b836-124">다음 절차를 수행 하려면 **단추** 컨트롤이 있는 폼 `Button1` 이 이미 배치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-124">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="5b836-125">프로그래밍 방식으로 폼에 컨트롤을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="5b836-125">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="5b836-126">`Click`폼의 클래스 내에서 단추의 이벤트를 처리 하는 메서드에서 다음과 비슷한 코드를 삽입 하 여 컨트롤 변수에 대 한 참조를 추가 하 고 컨트롤의를 설정 하 `Location` 고 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-126">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

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
    > <span data-ttu-id="5b836-127">컨트롤의 다른 속성을 초기화 하는 코드를 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-127">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5b836-128">악의적인을 참조 하 여 네트워크를 통해 로컬 컴퓨터를 보안 위험에 노출 시킬 수 있습니다 `UserControl` .</span><span class="sxs-lookup"><span data-stu-id="5b836-128">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="5b836-129">악의적인 사용자가 손상 된 사용자 지정 컨트롤을 만든 다음 실수로 프로젝트에 추가 하는 경우에만이 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b836-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b836-130">참조</span><span class="sxs-lookup"><span data-stu-id="5b836-130">See also</span></span>

- [<span data-ttu-id="5b836-131">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5b836-131">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5b836-132">방법: Windows Forms에서 컨트롤의 크기 조정</span><span class="sxs-lookup"><span data-stu-id="5b836-132">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="5b836-133">방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정</span><span class="sxs-lookup"><span data-stu-id="5b836-133">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="5b836-134">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5b836-134">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
