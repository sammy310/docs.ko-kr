---
title: '방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 06c2c83ddfba67aaff775065cc2aa4515978bf81
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722713"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가
Windows Forms에 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다. 호출을 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 항목을 추가할 컨트롤의 클래스 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성. 합니다 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가 하는 동안는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드는 지정된 된 위치에 항목을 추가 합니다.  
  
### <a name="to-add-a-new-item"></a>새 항목을 추가 하려면  
  
1.  사용 된 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 항목 목록의 끝에 항목을 추가 하는 방법입니다.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     또는  
  
2.  사용 된 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 지정된 된 위치에 있는 목록에 항목을 삽입 하는 방법입니다.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown 컨트롤](domainupdown-control-windows-forms.md)
- [DomainUpDown 컨트롤 개요](domainupdown-control-overview-windows-forms.md)
