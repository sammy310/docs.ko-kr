---
title: ContextMenu 구성 요소를 사용 하 여 메뉴 항목 추가 및 제거
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
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746276"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>방법: Windows Forms ContextMenu 구성 요소를 사용하여 메뉴 항목 추가 및 제거
Windows Forms에서 바로 가기 메뉴 항목을 추가 하 고 제거 하는 방법을 설명 합니다.  
  
 Windows Forms <xref:System.Windows.Forms.ContextMenu> 구성 요소는 선택한 개체와 관련 된 자주 사용 되는 명령 메뉴를 제공 합니다. <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션에 <xref:System.Windows.Forms.MenuItem> 개체를 추가 하 여 바로 가기 메뉴에 항목을 추가할 수 있습니다.  
  
 바로 가기 메뉴에서 항목을 영구적으로 제거할 수 있습니다. 그러나 런타임에 항목을 숨기 거 나 사용 하지 않도록 설정 하는 것이 더 적합할 수 있습니다.  
  
> [!IMPORTANT]
> <xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 하 고 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 기능을 추가 하는 경우에도, <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다.  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>바로 가기 메뉴에서 항목을 제거 하려면  
  
1. <xref:System.Windows.Forms.ContextMenu> 구성 요소의 <xref:System.Windows.Forms.Menu.MenuItems%2A> 컬렉션에 대 한 <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> 또는 <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> 메서드를 사용 하 여 특정 메뉴 항목을 제거 합니다.  
  
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
  
     -또는-  
  
2. <xref:System.Windows.Forms.ContextMenu> 구성 요소의 `MenuItems` 컬렉션에 `Clear` 메서드를 사용 하 여 메뉴에서 모든 항목을 제거 합니다.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu 구성 요소](contextmenu-component-windows-forms.md)
- [ContextMenu 구성 요소 개요](contextmenu-component-overview-windows-forms.md)
