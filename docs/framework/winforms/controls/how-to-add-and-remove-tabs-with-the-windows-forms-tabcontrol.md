---
title: '방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 938f1210eaa3479822e752327123737a3286fe9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624055"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="738e5-102">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="738e5-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="738e5-103">기본적으로 <xref:System.Windows.Forms.TabControl> 컨트롤에는 두 개의 <xref:System.Windows.Forms.TabPage> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="738e5-104">이러한 탭을 통해 액세스할 수 있습니다는 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="738e5-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="738e5-105">프로그래밍 방식으로 탭을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="738e5-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="738e5-106">사용 된 <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> 메서드를 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="738e5-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="738e5-107">프로그래밍 방식으로 탭을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="738e5-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="738e5-108">선택한 탭을 제거 하려면 사용 합니다 <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> 메서드는 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="738e5-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="738e5-109">또는</span><span class="sxs-lookup"><span data-stu-id="738e5-109">-or-</span></span>  
  
- <span data-ttu-id="738e5-110">모든 탭을 제거 하려면 사용 합니다 <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> 메서드는 <xref:System.Windows.Forms.TabControl.TabPages%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="738e5-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="738e5-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="738e5-111">See also</span></span>

- [<span data-ttu-id="738e5-112">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="738e5-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="738e5-113">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="738e5-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="738e5-114">방법: 탭 페이지를 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="738e5-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="738e5-115">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="738e5-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
