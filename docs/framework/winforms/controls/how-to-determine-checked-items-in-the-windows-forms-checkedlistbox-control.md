---
title: 체크리스트박스 컨트롤에서 선택된 항목 확인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: 5d93a63e9c1c6aae91ecfe83590c59450a565afe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182199"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a><span data-ttu-id="94a67-102">방법: Windows Forms CheckedListBox 컨트롤에서 선택된 항목 확인</span><span class="sxs-lookup"><span data-stu-id="94a67-102">How to: Determine Checked Items in the Windows Forms CheckedListBox Control</span></span>
<span data-ttu-id="94a67-103">Windows Forms <xref:System.Windows.Forms.CheckedListBox> 컨트롤에서 데이터를 표시할 때 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 속성에 저장된 컬렉션을 반복하거나 메서드를 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 사용하여 목록을 단계별로 검사할 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-103">When presenting data in a Windows Forms <xref:System.Windows.Forms.CheckedListBox> control, you can either iterate through the collection stored in the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> property, or step through the list using the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method to determine which items are checked.</span></span> <span data-ttu-id="94a67-104">메서드는 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 항목 인덱스 번호를 인수로 `true` 사용하여 `false`반환하거나 .</span><span class="sxs-lookup"><span data-stu-id="94a67-104">The <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method takes an item index number as its argument and returns `true` or `false`.</span></span> <span data-ttu-id="94a67-105">예상할 수 있는 <xref:System.Windows.Forms.ListBox.SelectedItems%2A> 항목과 <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 달리 및 속성은 검사할 항목을 결정하지 않습니다. 강조 표시할 항목을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-105">Contrary to what you might expect, the <xref:System.Windows.Forms.ListBox.SelectedItems%2A> and <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> properties do not determine which items are checked; they determine which items are highlighted.</span></span>  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a><span data-ttu-id="94a67-106">체크리스트Box 컨트롤에서 선택된 항목을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="94a67-106">To determine checked items in a CheckedListBox control</span></span>  
  
1. <span data-ttu-id="94a67-107">컬렉션이 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 0부터 시작되므로 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-107">Iterate through the <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> collection, starting at 0 since the collection is zero-based.</span></span> <span data-ttu-id="94a67-108">이 메서드는 전체 목록이 아니라 확인된 항목 목록의 항목 번호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-108">Note that this method will give you the item number in the list of checked items, not the overall list.</span></span> <span data-ttu-id="94a67-109">따라서 목록의 첫 번째 항목을 선택하지 않고 두 번째 항목을 선택하면 아래 코드에 "선택된 항목 1 = MyListItem2"와 같은 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-109">So if the first item in the list is not checked and the second item is checked, the code below will display text like "Checked Item 1 = MyListItem2".</span></span>  
  
    ```vb  
    ' Determine if there are any items checked.  
    If CheckedListBox1.CheckedItems.Count <> 0 Then  
       ' If so, loop through all checked items and print results.  
       Dim x As Integer  
       Dim s As String = ""  
       For x = 0 To CheckedListBox1.CheckedItems.Count - 1  
          s = s & "Checked Item " & (x + 1).ToString & " = " & CheckedListBox1.CheckedItems(x).ToString & ControlChars.CrLf  
       Next x  
       MessageBox.Show(s)  
    End If  
    ```  
  
    ```csharp  
    // Determine if there are any items checked.  
    if(checkedListBox1.CheckedItems.Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       string s = "";  
       for(int x = 0; x < checkedListBox1.CheckedItems.Count ; x++)  
       {  
          s = s + "Checked Item " + (x+1).ToString() + " = " + checkedListBox1.CheckedItems[x].ToString() + "\n";  
       }  
       MessageBox.Show(s);  
    }  
    ```  
  
    ```cpp  
    // Determine if there are any items checked.  
    if(checkedListBox1->CheckedItems->Count != 0)  
    {  
       // If so, loop through all checked items and print results.  
       String ^ s = "";  
       for(int x = 0; x < checkedListBox1->CheckedItems->Count; x++)  
       {  
          s = String::Concat(s, "Checked Item ", (x+1).ToString(),  
             " = ", checkedListBox1->CheckedItems[x]->ToString(),  
             "\n");  
       }  
       MessageBox::Show(s);  
    }  
    ```  
  
     - <span data-ttu-id="94a67-110">또는-</span><span class="sxs-lookup"><span data-stu-id="94a67-110">or -</span></span>  
  
2. <span data-ttu-id="94a67-111">컬렉션이 <xref:System.Windows.Forms.CheckedListBox.Items%2A> 0부터 0부터 시작하여 컬렉션을 단계별로 시작하고 각 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 항목에 대한 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-111">Step through the <xref:System.Windows.Forms.CheckedListBox.Items%2A> collection, starting at 0 since the collection is zero-based, and call the <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> method for each item.</span></span> <span data-ttu-id="94a67-112">이 메서드는 전체 목록에서 항목 번호를 제공 하므로 목록의 첫 번째 항목을 선택 하지 않고 두 번째 항목을 선택 하는 경우 "항목 2 = MyListItem2"와 같은 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a67-112">Note that this method will give you the item number in the overall list, so if the first item in the list is not checked and the second item is checked, it will display something like "Item 2 = MyListItem2".</span></span>  
  
    ```vb  
    Dim i As Integer  
    Dim s As String  
    s = "Checked Items:" & ControlChars.CrLf  
    For i = 0 To (CheckedListBox1.Items.Count - 1)  
       If CheckedListBox1.GetItemChecked(i) = True Then  
          s = s & "Item " & (i + 1).ToString & " = " & CheckedListBox1.Items(i).ToString & ControlChars.CrLf  
       End If  
    Next  
    MessageBox.Show(s)  
    ```  
  
    ```csharp  
    int i;  
    string s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1.Items.Count-1); i++)  
    {  
       if (checkedListBox1.GetItemChecked(i))  
       {  
          s = s + "Item " + (i+1).ToString() + " = " + checkedListBox1.Items[i].ToString() + "\n";  
       }  
    }  
    MessageBox.Show (s);  
    ```  
  
    ```cpp  
    int i;  
    String ^ s;
    s = "Checked items:\n" ;  
    for (i = 0; i <= (checkedListBox1->Items->Count-1); i++)  
    {  
       if (checkedListBox1->GetItemChecked(i))  
       {  
          s = String::Concat(s, "Item ", (i+1).ToString(), " = ",  
             checkedListBox1->Item[i]->ToString(), "\n");  
       }  
    }  
    MessageBox::Show(s);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="94a67-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94a67-113">See also</span></span>

- [<span data-ttu-id="94a67-114">옵션 목록 표시에 사용하는 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="94a67-114">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
