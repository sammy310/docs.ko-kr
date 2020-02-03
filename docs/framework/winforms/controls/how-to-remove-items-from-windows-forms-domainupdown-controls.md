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
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="9c370-102">방법: Windows Forms DomainUpDown 컨트롤에서 항목 제거</span><span class="sxs-lookup"><span data-stu-id="9c370-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="9c370-103"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 호출 하 여 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에서 항목을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c370-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="9c370-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드는 특정 항목을 제거 하는 반면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드는 위치에 따라 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c370-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="9c370-105">항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="9c370-105">To remove an item</span></span>  
  
- <span data-ttu-id="9c370-106"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> 메서드를 사용 하 여 이름을 기준으로 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c370-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="9c370-107">또는</span><span class="sxs-lookup"><span data-stu-id="9c370-107">-or-</span></span>  
  
- <span data-ttu-id="9c370-108"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> 메서드를 사용 하 여 해당 위치로 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c370-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c370-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c370-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9c370-110">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9c370-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="9c370-111">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9c370-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
