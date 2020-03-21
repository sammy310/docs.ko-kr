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
ms.openlocfilehash: 7e3480c5a56170ce94d5b5bde0208542c82e7702
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182305"
---
# <a name="how-to-add-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="08eaa-102">방법: ContextMenuStrip에 메뉴 항목 추가</span><span class="sxs-lookup"><span data-stu-id="08eaa-102">How to: Add Menu Items to a ContextMenuStrip</span></span>
<span data-ttu-id="08eaa-103"><xref:System.Windows.Forms.ContextMenuStrip>에 한 번에 하나의 메뉴 항목 또는 여러 항목을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08eaa-103">You can add just one menu item or several items at a time to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-add-a-single-menu-item-to-a-contextmenustrip"></a><span data-ttu-id="08eaa-104">컨텍스트 메뉴스트립에 단일 메뉴 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="08eaa-104">To add a single menu item to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="08eaa-105">메서드를 <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> 사용하여 에 하나의 메뉴 <xref:System.Windows.Forms.ContextMenuStrip>항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08eaa-105">Use the <xref:System.Windows.Forms.ToolStripItemCollection.Add%2A> method to add one menu item to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
    ```vb  
    Me.contextMenuStrip1.Items.Add(Me.toolStripMenuItem1)  
    ```  
  
    ```csharp  
    this.contextMenuStrip1.Items.Add(toolStripMenuItem1);  
    ```  
  
### <a name="to-add-several-menu-items-to-a-contextmenustrip"></a><span data-ttu-id="08eaa-106">컨텍스트 메뉴스트립에 여러 메뉴 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="08eaa-106">To add several menu items to a ContextMenuStrip</span></span>  
  
- <span data-ttu-id="08eaa-107">메서드를 <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> 사용하여 <xref:System.Windows.Forms.ContextMenuStrip>여러 메뉴 항목을 에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08eaa-107">Use the <xref:System.Windows.Forms.ToolStripItemCollection.AddRange%2A> method to add several menu items to a <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="08eaa-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08eaa-108">See also</span></span>

- [<span data-ttu-id="08eaa-109">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="08eaa-109">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
