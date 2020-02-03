---
title: 프로그래밍 방식으로 DomainUpDown 컨트롤에 항목 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745585"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가
코드에서 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에 항목을 추가할 수 있습니다. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 호출 하 여 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에 항목을 추가 합니다. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가 하는 반면, <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드는 지정 된 위치에 항목을 추가 합니다.  
  
### <a name="to-add-a-new-item"></a>새 항목을 추가 하려면  
  
1. 항목 목록의 끝에 항목을 추가 하려면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드를 사용 합니다.  
  
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
  
2. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 사용 하 여 목록에서 지정 된 위치에 항목을 삽입 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown 컨트롤](domainupdown-control-windows-forms.md)
- [DomainUpDown 컨트롤 개요](domainupdown-control-overview-windows-forms.md)
