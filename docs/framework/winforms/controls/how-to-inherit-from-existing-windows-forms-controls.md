---
title: '방법: 기존 Windows Forms 컨트롤에서 상속'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 90008b00c95906ba43364c5a4ae3f85d9fdf0e22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087874"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="9e1e0-102">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="9e1e0-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="9e1e0-103">기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="9e1e0-104">기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="9e1e0-105">예를 들어에서 상속 된 컨트롤을 만들려는 <xref:System.Windows.Forms.Button>, 새 컨트롤 모양 및 act에는 정확히 표준 같은 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="9e1e0-106">그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="9e1e0-107">일부 컨트롤에서는 변경할 수 있습니다도 상속 된 컨트롤의 시각적 모양을 재정의 하 여 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e1e0-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9e1e0-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9e1e0-110">자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="9e1e0-111">상속된 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="9e1e0-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="9e1e0-112">새 **Windows Forms 애플리케이션** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="9e1e0-113">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="9e1e0-114">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="9e1e0-115">**새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="9e1e0-116">새 사용자 지정 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="9e1e0-117">Visual Basic을 사용하면 **솔루션 탐색기**의 맨 위에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="9e1e0-118">CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="9e1e0-119">C#을 사용하는 경우 코드 편집기에서 CustomControl1.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="9e1e0-120">상속 되는 클래스 선언을 찾습니다 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="9e1e0-121">기본 클래스를 상속하려는 컨트롤로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="9e1e0-122">예를 들어에서 상속 하려는 경우 <xref:System.Windows.Forms.Button>, 다음 클래스 선언을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="9e1e0-123">Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="9e1e0-124">코드 편집기에서 CustomControl1.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="9e1e0-125">컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="9e1e0-126">컨트롤의 그래픽 모양을 수정 하려는 경우 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9e1e0-127">재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 모든 컨트롤의 모양을 수정 하려는 허용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="9e1e0-128">모든 Windows 수행한 그리기가 있는 해당 컨트롤 (예를 들어 <xref:System.Windows.Forms.TextBox>)를 호출 하지 않습니다 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 따라서 사용 하지 것입니다 사용자 지정 코드 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="9e1e0-129">경우를 확인 하려면 수정 하려는 특정 컨트롤에 대 한 도움말 설명서를 참조 합니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 방법은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="9e1e0-130">모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](controls-to-use-on-windows-forms.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="9e1e0-131">컨트롤에 없는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 구성원 메서드로 나열 하 여 변경할 수 없습니다 모양을이 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="9e1e0-132">사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](custom-control-painting-and-rendering.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-132">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. <span data-ttu-id="9e1e0-133">컨트롤을 저장하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1e0-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1e0-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e1e0-134">See also</span></span>

- [<span data-ttu-id="9e1e0-135">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="9e1e0-135">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="9e1e0-136">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="9e1e0-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="9e1e0-137">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="9e1e0-137">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="9e1e0-138">방법: Windows Forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="9e1e0-138">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="9e1e0-139">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9e1e0-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="9e1e0-140">연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="9e1e0-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="9e1e0-141">연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="9e1e0-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
