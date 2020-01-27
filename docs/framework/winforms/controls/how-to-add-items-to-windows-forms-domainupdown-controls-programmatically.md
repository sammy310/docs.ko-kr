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
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="e9977-102">방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="e9977-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="e9977-103">코드에서 Windows Forms <xref:System.Windows.Forms.DomainUpDown> 컨트롤에 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9977-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="e9977-104"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 클래스의 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 호출 하 여 컨트롤의 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9977-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="e9977-105"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가 하는 반면, <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드는 지정 된 위치에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9977-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="e9977-106">새 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="e9977-106">To add a new item</span></span>  
  
1. <span data-ttu-id="e9977-107">항목 목록의 끝에 항목을 추가 하려면 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9977-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="e9977-108">-또는-</span><span class="sxs-lookup"><span data-stu-id="e9977-108">-or-</span></span>  
  
2. <span data-ttu-id="e9977-109"><xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 사용 하 여 목록에서 지정 된 위치에 항목을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9977-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9977-110">참조</span><span class="sxs-lookup"><span data-stu-id="e9977-110">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e9977-111">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="e9977-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="e9977-112">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="e9977-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
