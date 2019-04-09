---
title: '방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: e02a187edc1392f15fe98354bb2e5c43843e430c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094465"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="9ea3d-102">방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="9ea3d-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="9ea3d-103">추가 Windows Forms의 바로 가기 메뉴 항목을 제거 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="9ea3d-104">Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소는 선택한 개체에 관련 된 자주 사용 되는 명령의 메뉴를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="9ea3d-105">추가 하 여 바로 가기 메뉴 항목을 추가할 수 있습니다 <xref:System.Windows.Forms.MenuItem> 개체는 <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="9ea3d-106">영구적으로; 바로 가기 메뉴에서 항목을 제거할 수 있습니다. 그러나 런타임에 것 숨기 거 나 항목을 대신 사용 하지 않도록 설정 하는 것이 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ea3d-107">있지만 <xref:System.Windows.Forms.MenuStrip> 하 고 <xref:System.Windows.Forms.ContextMenuStrip> 바꾸고 기능을 추가 합니다 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하면 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="9ea3d-108">바로 가기 메뉴에서 항목을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="9ea3d-108">To remove items from a shortcut menu</span></span>  
  
1.  <span data-ttu-id="9ea3d-109">사용 하 여는 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 메서드의 <xref:System.Windows.Forms.Menu.MenuItems%2A> 의 컬렉션을 <xref:System.Windows.Forms.ContextMenu> 특정 메뉴 항목을 제거 하려면 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="9ea3d-110">또는</span><span class="sxs-lookup"><span data-stu-id="9ea3d-110">-or-</span></span>  
  
2.  <span data-ttu-id="9ea3d-111">사용 하 여를 `Clear` 메서드를 `MenuItems` 의 컬렉션을 <xref:System.Windows.Forms.ContextMenu> 메뉴에서 모든 항목을 제거 하려면 구성 요소.</span><span class="sxs-lookup"><span data-stu-id="9ea3d-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9ea3d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ea3d-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="9ea3d-113">ContextMenu 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9ea3d-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="9ea3d-114">ContextMenu 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="9ea3d-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
