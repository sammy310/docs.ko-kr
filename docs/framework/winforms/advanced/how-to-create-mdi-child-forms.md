---
title: '방법: MDI 자식 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: b49d43e0e1123921cb3800f0d60193d0ea7b3924
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338591"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="2fb48-102">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="2fb48-102">How to: Create MDI child forms</span></span>

<span data-ttu-id="2fb48-103">MDI 자식 폼은 [mdi (다중 문서 인터페이스) 응용 프로그램](multiple-document-interface-mdi-applications.md)의 필수적인 요소 이며, 이러한 폼은 사용자 상호 작용의 중심입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="2fb48-104">다음 절차에서는 Visual Studio를 사용 하 여 대부분의 단어 처리 응용 프로그램과 비슷하게 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 표시 하는 MDI 자식 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-104">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="2fb48-105"><xref:System.Windows.Forms> 컨트롤을 <xref:System.Windows.Forms.DataGridView> 컨트롤, 컨트롤 혼합 등의 다른 컨트롤로 대체 하 여 다양 한 가능성을 가진 MDI 자식 창 (및 확장, MDI 응용 프로그램)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-105">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="2fb48-106">MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="2fb48-106">Create MDI child forms</span></span>

1. <span data-ttu-id="2fb48-107">Visual Studio에서 새 Windows Forms 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-107">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="2fb48-108">폼의 **속성** 창에서 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정 하 고 `WindowsState` 속성을 `Maximized`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-108">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="2fb48-109">그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-109">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="2fb48-110">`Toolbox`에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-110">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="2fb48-111">해당 `Text` 속성을 **File**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-111">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="2fb48-112">**항목** 속성 옆에 있는 줄임표 (...)를 클릭 하 고 **추가** 를 클릭 하 여 두 개의 자식 도구 스트립 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-112">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="2fb48-113">이러한 항목에 대 한 `Text` 속성을 **새** 및 **창**으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-113">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="2fb48-114">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-114">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="2fb48-115">**새 항목 추가** 대화 상자에서 **템플릿** 창에서 **Windows Form** (Visual Basic 또는 시각적 개체 C#) 또는 **Windows Forms 응용 프로그램 (.net)** (visual C++)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-115">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="2fb48-116">**이름** 상자에서 폼의 이름을 **Form2**로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-116">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="2fb48-117">**열기** 를 선택 하 여 프로젝트에 양식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-117">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fb48-118">이 단계에서 만든 MDI 자식 폼은 표준 Windows Form입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-118">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="2fb48-119">따라서 폼의 투명도를 제어할 수 있는 <xref:System.Windows.Forms.Form.Opacity%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-119">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="2fb48-120">그러나 <xref:System.Windows.Forms.Form.Opacity%2A> 속성은 최상위 창에 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-120">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="2fb48-121">그리기 문제가 발생할 수 있으므로 MDI 자식 폼에는 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2fb48-121">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="2fb48-122">이 폼은 MDI 자식 폼에 대한 템플릿이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-122">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="2fb48-123">**Windows Forms 디자이너** 열리고 **Form2**가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-123">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="2fb48-124">**도구 상자**에서 **RichTextBox** 컨트롤을 폼으로 끌어 옵니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-124">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="2fb48-125">**속성** 창에서 `Anchor` 속성을 **Top, Left** 로 설정 하 고 `Dock` 속성을 **Fill**로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-125">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="2fb48-126">이렇게 하면 폼의 크기를 조정하는 경우에도 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 MDI 자식 폼의 영역을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-126">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="2fb48-127">**새** 메뉴 항목을 두 번 클릭 하 여 해당 항목에 대 한 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-127">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="2fb48-128">사용자가 **새** 메뉴 항목을 클릭할 때 새 MDI 자식 폼을 만들기 위해 다음과 유사한 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-128">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2fb48-129">다음 예제에서는 이벤트 처리기가 `MenuItem2`에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-129">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="2fb48-130">응용 프로그램 아키텍처의 세부 사항에 따라 **새** 메뉴 항목이 `MenuItem2`되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-130">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

    ```vb
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click
       Dim NewMDIChild As New Form2()
       'Set the Parent Form of the Child window.
       NewMDIChild.MdiParent = Me
       'Display the new form.
       NewMDIChild.Show()
    End Sub
    ```

    ```csharp
    protected void MDIChildNew_Click(object sender, System.EventArgs e){
       Form2 newMDIChild = new Form2();
       // Set the Parent Form of the Child window.
       newMDIChild.MdiParent = this;
       // Display the new form.
       newMDIChild.Show();
    }
    ```

    ```cpp
    private:
       void menuItem2_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          Form2^ newMDIChild = gcnew Form2();
          // Set the Parent Form of the Child window.
          newMDIChild->MdiParent = this;
          // Display the new form.
          newMDIChild->Show();
       }
    ```

   <span data-ttu-id="2fb48-131">에서 C++Form1의 맨 위에 다음 `#include` 지시어를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-131">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="2fb48-132">**속성** 창의 맨 위에 있는 드롭다운 목록에서 **파일** 메뉴 스트립에 해당 하는 메뉴 스트립을 선택 하 고 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 창 <xref:System.Windows.Forms.ToolStripMenuItem>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-132">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="2fb48-133">이렇게 하면 **창** 메뉴에서 활성 자식 창 옆에 확인 표시가 있는 열려 있는 MDI 자식 창 목록을 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-133">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="2fb48-134">**F5** 키를 눌러 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-134">Press **F5** to run the application.</span></span> <span data-ttu-id="2fb48-135">**파일** 메뉴에서 **새로** 만들기를 선택 하 여 **창** 메뉴 항목에서 추적 되는 새 MDI 자식 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-135">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2fb48-136">MDI 자식 폼이 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)를 포함하고 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)가 있는 MDI 부모 폼 내에서 열린 경우 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성(및 필요에 따라 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성)을 설정했으면 메뉴 항목이 자동으로 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-136">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="2fb48-137">두 <xref:System.Windows.Forms.MainMenu> 구성 요소와 자식 폼의 모든 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성을 <xref:System.Windows.Forms.MenuMerge.MergeItems>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-137">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="2fb48-138">또한 두 메뉴의 메뉴 항목이 원하는 순서대로 표시되도록 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-138">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="2fb48-139">MDI 부모 폼을 닫을 경우 MDI 부모에 대한 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하기 전에 각 MDI 자식 폼에서 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-139">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="2fb48-140">MDI 자식의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 취소해도 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하지 않도록 방지되지는 않습니다. 그러나 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 <xref:System.ComponentModel.CancelEventArgs> 인수가 이제 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-140">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="2fb48-141"><xref:System.ComponentModel.CancelEventArgs> 인수를 `false`로 설정하여 MDI 부모 및 모든 MDI 자식 폼을 강제로 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb48-141">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fb48-142">참조</span><span class="sxs-lookup"><span data-stu-id="2fb48-142">See also</span></span>

- [<span data-ttu-id="2fb48-143">MDI(다중 문서 인터페이스) 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="2fb48-143">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="2fb48-144">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="2fb48-144">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="2fb48-145">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="2fb48-145">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="2fb48-146">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="2fb48-146">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="2fb48-147">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="2fb48-147">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
