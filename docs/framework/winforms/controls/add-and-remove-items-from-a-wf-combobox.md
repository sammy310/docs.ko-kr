---
title: ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거
ms.date: 03/30/2017
description: 데이터 바인딩을 사용 하지 않고 Windows Forms ComboBox, ListBox 및 CheckedListBox 컨트롤을 추가 하 고 제거 하는 방법에 대해 알아봅니다.
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- combo boxes [Windows Forms], adding items
- list boxes [Windows Forms], removing items
- ComboBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], adding and removing items
- list boxes [Windows Forms], adding items
- combo boxes [Windows Forms], removing items
- CheckedListBox control [Windows Forms], adding and removing items
ms.assetid: 7224c8d2-4118-443e-ae1e-d7c17d1e69ee
ms.openlocfilehash: f3701257bbe410bf03c4c21700705e87b581bf2e
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904444"
---
# <a name="how-to-add-and-remove-items-from-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 항목 추가 및 제거
이러한 컨트롤은 다양 한 데이터 소스에 바인딩될 수 있으므로 Windows Forms 콤보 상자, 목록 상자 또는 선택 목록 상자에 항목을 추가할 수 있습니다. 그러나이 항목에서는 가장 간단한 방법을 보여 주고 데이터 바인딩이 필요 하지 않습니다. 표시 되는 항목은 일반적으로 문자열입니다. 그러나 모든 개체를 사용할 수 있습니다. 컨트롤에 표시 되는 텍스트는 개체의 메서드에서 반환 하는 값입니다 `ToString` .  
  
### <a name="to-add-items"></a>항목을 추가 하려면  
  
1. 클래스의 메서드를 사용 하 여 목록에 문자열 또는 개체를 추가 `Add` `ObjectCollection` 합니다. 컬렉션은 속성을 사용 하 여 참조 됩니다 `Items` .  
  
    ```vb  
    ComboBox1.Items.Add("Tokyo")  
    ```  
  
    ```csharp  
    comboBox1.Items.Add("Tokyo");  
    ```  
  
    ```cpp  
    comboBox1->Items->Add("Tokyo");  
    ```  
  
     - 또는  
  
2. 메서드를 사용 하 여 목록에서 원하는 지점에 문자열 또는 개체를 삽입 합니다 `Insert` .  
  
    ```vb  
    CheckedListBox1.Items.Insert(0, "Copenhagen")  
    ```  
  
    ```csharp  
    checkedListBox1.Items.Insert(0, "Copenhagen");  
    ```  
  
    ```cpp  
    checkedListBox1->Items->Insert(0, "Copenhagen");  
    ```  
  
     - 또는  
  
3. 전체 배열을 컬렉션에 할당 합니다 `Items` .  
  
    ```vb  
    Dim ItemObject(9) As System.Object  
    Dim i As Integer  
       For i = 0 To 9  
       ItemObject(i) = "Item" & i  
    Next i  
    ListBox1.Items.AddRange(ItemObject)  
    ```  
  
    ```csharp  
    System.Object[] ItemObject = new System.Object[10];  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = "Item" + i;  
    }  
    listBox1.Items.AddRange(ItemObject);  
    ```  
  
    ```cpp  
    Array<System::Object^>^ ItemObject = gcnew Array<System::Object^>(10);  
    for (int i = 0; i <= 9; i++)  
    {  
       ItemObject[i] = String::Concat("Item", i.ToString());  
    }  
    listBox1->Items->AddRange(ItemObject);  
    ```  
  
### <a name="to-remove-an-item"></a>항목을 제거 하려면  
  
1. `Remove`또는 메서드를 호출 `RemoveAt` 하 여 항목을 삭제 합니다.  
  
     `Remove`제거할 항목을 지정 하는 하나의 인수를 가집니다.`RemoveAt` 지정 된 인덱스 번호의 항목을 제거 합니다.  
  
    ```vb  
    ' To remove item with index 0:  
    ComboBox1.Items.RemoveAt(0)  
    ' To remove currently selected item:  
    ComboBox1.Items.Remove(ComboBox1.SelectedItem)  
    ' To remove "Tokyo" item:  
    ComboBox1.Items.Remove("Tokyo")  
    ```  
  
    ```csharp  
    // To remove item with index 0:  
    comboBox1.Items.RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1.Items.Remove(comboBox1.SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1.Items.Remove("Tokyo");  
    ```  
  
    ```cpp  
    // To remove item with index 0:  
    comboBox1->Items->RemoveAt(0);  
    // To remove currently selected item:  
    comboBox1->Items->Remove(comboBox1->SelectedItem);  
    // To remove "Tokyo" item:  
    comboBox1->Items->Remove("Tokyo");  
    ```  
  
### <a name="to-remove-all-items"></a>모든 항목을 제거 하려면  
  
1. 메서드를 호출 `Clear` 하 여 컬렉션에서 모든 항목을 제거 합니다.  
  
    ```vb  
    ListBox1.Items.Clear()  
    ```  
  
    ```csharp  
    listBox1.Items.Clear();  
    ```  
  
    ```cpp  
    listBox1->Items->Clear();  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 내용 정렬](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [ListBox 대신 Windows Forms ComboBox를 사용해야 하는 경우](when-to-use-a-windows-forms-combobox-instead-of-a-listbox.md)
- [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
