---
title: CheckedListBox 컨트롤에서 선택 된 항목 확인
description: CheckedItems 속성에 저장 된 컬렉션을 반복 하 여 Windows Forms CheckedListBox 컨트롤에서 선택 된 항목을 확인 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- check boxes [Windows Forms], determining checked state
- CheckedListBox control [Windows Forms], determining checked state
ms.assetid: 178b477d-27c9-489c-8914-44a9623a4d41
ms.openlocfilehash: fd8845ef83da7406ff4f1468506a23e3f4d386a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618352"
---
# <a name="how-to-determine-checked-items-in-the-windows-forms-checkedlistbox-control"></a>방법: Windows Forms CheckedListBox 컨트롤에서 선택한 항목 확인
Windows Forms 컨트롤에 데이터를 제공 하는 경우 <xref:System.Windows.Forms.CheckedListBox> 속성에 저장 된 컬렉션을 반복 <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A> 하거나 메서드를 사용 하 여 목록을 단계별로 실행 하 여 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 선택 된 항목을 확인할 수 있습니다. <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A>메서드는 항목 인덱스 번호를 인수로 사용 하 고 또는를 반환 합니다 `true` `false` . 예상과 달리 <xref:System.Windows.Forms.ListBox.SelectedItems%2A> 및 속성은 선택 된 항목을 <xref:System.Windows.Forms.ListBox.SelectedIndices%2A> 확인 하지 않으며 강조 표시 되는 항목을 결정 합니다.  
  
### <a name="to-determine-checked-items-in-a-checkedlistbox-control"></a>CheckedListBox 컨트롤에서 선택 된 항목을 확인 하려면  
  
1. <xref:System.Windows.Forms.CheckedListBox.CheckedItems%2A>컬렉션은 0부터 시작 하므로 0부터 시작 하 여 컬렉션을 반복 합니다. 이 메서드는 전체 목록이 아니라 선택한 항목 목록에 있는 항목 번호를 제공 합니다. 따라서 목록의 첫 번째 항목을 선택 하지 않고 두 번째 항목을 선택 하는 경우 아래 코드는 "Checked Item 1 = MyListItem2"와 같은 텍스트를 표시 합니다.  
  
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
  
     - 또는  
  
2. 컬렉션은 0부터 시작 하 여 컬렉션을 한 단계씩 실행 하 <xref:System.Windows.Forms.CheckedListBox.Items%2A> 고 <xref:System.Windows.Forms.CheckedListBox.GetItemChecked%2A> 각 항목에 대해 메서드를 호출 합니다. 이 메서드는 전체 목록에서 항목 번호를 제공 하므로 목록의 첫 번째 항목을 확인 하지 않고 두 번째 항목을 선택 하면 "Item 2 = MyListItem2"와 같이 표시 됩니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
