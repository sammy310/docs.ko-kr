---
title: ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스
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
ms.openlocfilehash: 67673ec7f136f1466d4fd091e691324c53e7de06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746329"
---
# <a name="how-to-access-specific-items-in-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a>방법: Windows Forms ComboBox, ListBox 또는 CheckedListBox 컨트롤의 특정 항목에 액세스
Windows Forms 콤보 상자, 목록 상자 또는 선택 된 목록 상자의 특정 항목에 액세스 하는 작업은 필수 작업입니다. 지정 된 위치에서 목록에 있는 항목을 프로그래밍 방식으로 확인할 수 있습니다.  
  
### <a name="to-access-a-specific-item"></a>특정 항목에 액세스 하려면  
  
1. 특정 항목의 인덱스를 사용 하 여 `Items` 컬렉션을 쿼리 합니다.  
  
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
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- <xref:System.Windows.Forms.CheckedListBox>
- [옵션 목록 표시에 사용된 Windows Forms 컨트롤](windows-forms-controls-used-to-list-options.md)
