---
title: '방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 특정 항목 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ComboBox control [Windows Forms], accessing items
- ListBox control [Windows Forms], returning item information
- list boxes [Windows Forms], accessing items
- ListBox control [Windows Forms], accessing items
- combo boxes [Windows Forms], accessing items
- CheckedListBox control [Windows Forms], accessing items
ms.assetid: 1216742f-bcf9-4ff8-8a62-d7c9053c2b96
ms.openlocfilehash: 3d61a9b38f809d16e95b485893acaadcf04d826f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077214"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤에서 특정 항목 액세스
Windows Forms 콤보 상자, 목록 상자 또는 선택된 목록 상자에서 특정 항목에 액세스 하기 필수 작업입니다. 이 통해 프로그래밍 방식으로 지정된 된 위치에서 목록에는 무엇이 확인할 수 있습니다.  
  
### <a name="to-access-a-specific-item"></a>특정 항목에 액세스 하려면  
  
1.  쿼리는 `Items` 특정 항목의 인덱스를 사용 하 여 컬렉션:  
  
    ```vb  
    Private Function GetItemText(i As Integer) As String  
       ' Return the text of the item using the index:  
       Return ComboBox1.Items(i).ToString  
    End Function  
    ```  
  
    ```csharp  
    private string GetItemText(int i)  
    {  
       // Return the text of the item using the index:  
       return (comboBox1.Items[i].ToString());  
    }  
    ```  
  
    ```cpp  
    private:  
       String^ GetItemText(int i)  
       {  
          // Return the text of the item using the index:  
          return (comboBox1->Items->Item[i]->ToString());  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [옵션 목록 표시에 사용하는 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
