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
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="c8551-102">방법: 프로그래밍 방식으로 Windows Forms DomainUpDown 컨트롤에 항목 추가</span><span class="sxs-lookup"><span data-stu-id="c8551-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="c8551-103">Windows Forms에 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.DomainUpDown> 코드에서 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="c8551-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="c8551-104">호출을 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 또는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드를 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> 항목을 추가할 컨트롤의 클래스 <xref:System.Windows.Forms.DomainUpDown.Items%2A> 속성.</span><span class="sxs-lookup"><span data-stu-id="c8551-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="c8551-105">합니다 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 메서드는 컬렉션의 끝에 항목을 추가 하는 동안는 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 메서드는 지정된 된 위치에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8551-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="c8551-106">새 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="c8551-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="c8551-107">사용 된 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> 항목 목록의 끝에 항목을 추가 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c8551-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="c8551-108">또는</span><span class="sxs-lookup"><span data-stu-id="c8551-108">-or-</span></span>  
  
2.  <span data-ttu-id="c8551-109">사용 된 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> 지정된 된 위치에 있는 목록에 항목을 삽입 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c8551-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c8551-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="c8551-110">See also</span></span>
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c8551-111">DomainUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c8551-111">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="c8551-112">DomainUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="c8551-112">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
