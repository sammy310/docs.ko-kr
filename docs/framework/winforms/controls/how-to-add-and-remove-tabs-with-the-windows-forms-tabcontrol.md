---
title: TabControl을 사용 하 여 탭 추가 및 제거
description: 두 개의 TabPage 컨트롤을 포함 하는 Windows Forms TabControl 컨트롤을 사용 하 여 탭을 추가 하 고 제거 하는 방법을 알아봅니다. TabPages 속성을 통해 이러한 탭에 액세스 합니다.
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
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618079"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="3664c-104">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="3664c-104">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="3664c-105">기본적으로 컨트롤에는 <xref:System.Windows.Forms.TabControl> 두 개의 컨트롤이 포함 되어 있습니다 <xref:System.Windows.Forms.TabPage> .</span><span class="sxs-lookup"><span data-stu-id="3664c-105">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="3664c-106">이러한 탭은 속성을 통해 액세스할 수 있습니다 <xref:System.Windows.Forms.TabControl.TabPages%2A> .</span><span class="sxs-lookup"><span data-stu-id="3664c-106">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="3664c-107">프로그래밍 방식으로 탭을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="3664c-107">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="3664c-108"><xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>속성의 메서드를 사용 합니다 <xref:System.Windows.Forms.TabControl.TabPages%2A> .</span><span class="sxs-lookup"><span data-stu-id="3664c-108">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="3664c-109">프로그래밍 방식으로 탭을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="3664c-109">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="3664c-110">선택한 탭을 제거 하려면 <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> 속성의 메서드를 사용 합니다 <xref:System.Windows.Forms.TabControl.TabPages%2A> .</span><span class="sxs-lookup"><span data-stu-id="3664c-110">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="3664c-111">또는</span><span class="sxs-lookup"><span data-stu-id="3664c-111">-or-</span></span>  
  
- <span data-ttu-id="3664c-112">모든 탭을 제거 하려면 <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> 속성의 메서드를 사용 합니다 <xref:System.Windows.Forms.TabControl.TabPages%2A> .</span><span class="sxs-lookup"><span data-stu-id="3664c-112">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3664c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3664c-113">See also</span></span>

- [<span data-ttu-id="3664c-114">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="3664c-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="3664c-115">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="3664c-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="3664c-116">방법: 탭 페이지를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="3664c-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="3664c-117">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="3664c-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
