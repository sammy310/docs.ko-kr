---
title: DomainUpDown 컨트롤에서 항목 제거
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735775"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거
<xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 호출 하 여 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 항목을 제거할 수 있습니다. <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드는 특정 항목을 제거 하는 반면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드는 위치에 따라 항목을 제거 합니다.  
  
### <a name="to-remove-an-item"></a>항목을 제거 하려면  
  
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드를 사용 하 여 이름을 기준으로 항목을 제거 합니다.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     -또는-  
  
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 사용 하 여 해당 위치로 항목을 제거 합니다.  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown 컨트롤](domainupdown-control-windows-forms.md)
- [DomainUpDown 컨트롤 개요](domainupdown-control-overview-windows-forms.md)
