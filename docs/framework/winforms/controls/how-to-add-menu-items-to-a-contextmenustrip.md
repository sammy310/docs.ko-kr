---
title: '방법: ContextMenuStrip에 메뉴 항목 추가'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ContextMenuStrips [Windows Forms], adding menu items
- shortcut menus [Windows Forms], adding items
- context menus [Windows Forms], adding menu items
ms.assetid: 1ec14776-3ea2-4752-bd22-4fae0fd19e1a
ms.openlocfilehash: 534bbd2c2edb68dca0f2a1c2997ff1ba762ef07c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135085"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="fbd10-102">방법: ContextMenuStrip에 메뉴 항목 추가</span><span class="sxs-lookup"><span data-stu-id="fbd10-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="fbd10-103">한 번에 하나의 메뉴 항목 또는 여러 항목을 추가할 수 있습니다는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd10-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="fbd10-104">ContextMenuStrip에 단일 메뉴 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fbd10-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="fbd10-105">사용 된 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 하나의 메뉴 항목을 추가 하는 방법을 <xref:System.Windows.Forms.ContextMenuStrip>입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd10-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="fbd10-106">ContextMenuStrip에 몇 가지 메뉴 항목을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="fbd10-106">To add several menu items to a ContextMenuStrip</span></span>  
  
-   <span data-ttu-id="fbd10-107">사용 된 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 몇 가지 메뉴 항목을 추가 하는 메서드를 <xref:System.Windows.Forms.ContextMenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="fbd10-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.AddRange(New _  
       System.Windows.Forms.ToolStripItem() {Me.toolStripMenuItem1, _  
          Me.toolStripMenuItem2})  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.AddRange(new   
       System.Windows.Forms.ToolStripItem[] {  
          this.toolStripMenuItem1, this.toolStripMenuItem2});  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fbd10-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="fbd10-108">See also</span></span>

- [<span data-ttu-id="fbd10-109">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fbd10-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
