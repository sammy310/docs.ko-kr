---
title: '방법: ToolStripMenuItems 숨기기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
ms.openlocfilehash: 64c0f093063357c1e8db5933c035cc8295ad4f1e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623049"
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="6fa51-102">방법: ToolStripMenuItems 숨기기</span><span class="sxs-lookup"><span data-stu-id="6fa51-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="6fa51-103">메뉴 항목 숨기기는 응용 프로그램의 사용자 인터페이스를 제어 하 고 사용자 명령을 제한 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa51-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="6fa51-104">종종 전체 메뉴에 메뉴 항목을 모두 사용할 수 없는 경우 숨기려면 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa51-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="6fa51-105">이 사용자에 대해 더 적은 방해 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa51-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="6fa51-106">또한 하려는 숨기고 메뉴 또는 메뉴 항목을 사용 하지 않도록 설정으로 숨기는 것 만으로도 사용자 바로 가기 키를 사용 하 여 메뉴 명령에 액세스 하는 것을 금지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa51-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="6fa51-107">프로그래밍 방식으로 모든 메뉴 항목을 숨기려면</span><span class="sxs-lookup"><span data-stu-id="6fa51-107">To hide any menu item programmatically</span></span>  
  
- <span data-ttu-id="6fa51-108">메뉴 항목의 속성을 설정한 메서드 내에서 설정 하는 코드를 추가 합니다 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa51-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6fa51-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fa51-109">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- [<span data-ttu-id="6fa51-110">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6fa51-110">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="6fa51-111">방법: ToolStripMenuItems 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="6fa51-111">How to: Disable ToolStripMenuItems</span></span>](how-to-disable-toolstripmenuitems.md)
