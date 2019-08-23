---
title: MainMenu 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952130"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="664f3-102">MainMenu 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="664f3-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="664f3-103">및 <xref:System.Windows.Forms.MenuStrip> 는이전<xref:System.Windows.Forms.MainMenu> 버전 의및<xref:System.Windows.Forms.ContextMenu> 컨트롤에 기능을 추가 하 고 추가 하지만를 선택 하는 경우 이전 버전과의 호환성 및 향후 사용에 대해 모두 유지 됩니다.<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="664f3-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="664f3-104">Windows Forms <xref:System.Windows.Forms.MainMenu> 구성 요소에는 런타임에 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="664f3-105">주 메뉴와 개별 항목의 모든 하위 메뉴는 <xref:System.Windows.Forms.MenuItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="664f3-106">키 속성</span><span class="sxs-lookup"><span data-stu-id="664f3-106">Key Properties</span></span>  
 <span data-ttu-id="664f3-107"><xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을로 `true`설정 하 여 메뉴 항목을 기본 항목으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="664f3-108">메뉴를 클릭 하면 기본 항목이 굵은 텍스트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="664f3-109">메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성 `true` 은 또는 `false`이며 메뉴 항목이 선택 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="664f3-110">메뉴 항목 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 의 속성은 선택 된 항목의 모양을 사용자 지정 합니다. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 가로 `true`설정 된 경우 항목 옆에 라디오 단추가 표시 되 고, <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 가로 `false`설정 된 경우 항목 옆에 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="664f3-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664f3-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="664f3-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="664f3-112">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="664f3-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
