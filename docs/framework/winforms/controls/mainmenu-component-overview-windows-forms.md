---
title: MainMenu 구성 요소 개요
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745122"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="a6243-102">MainMenu 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="a6243-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="a6243-103"><xref:System.Windows.Forms.MenuStrip> 및 <xref:System.Windows.Forms.ContextMenuStrip> 대체 하 고 이전 버전의 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 기능을 추가 하는 경우에도, <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu>은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="a6243-104">Windows Forms <xref:System.Windows.Forms.MainMenu> 구성 요소에는 런타임에 메뉴가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="a6243-105">주 메뉴와 개별 항목의 모든 하위 메뉴는 <xref:System.Windows.Forms.MenuItem> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="a6243-106">키 속성</span><span class="sxs-lookup"><span data-stu-id="a6243-106">Key Properties</span></span>  
 <span data-ttu-id="a6243-107"><xref:System.Windows.Forms.MenuItem.DefaultItem%2A> 속성을 `true`설정 하 여 메뉴 항목을 기본 항목으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="a6243-108">메뉴를 클릭 하면 기본 항목이 굵은 텍스트로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="a6243-109">메뉴 항목의 <xref:System.Windows.Forms.MenuItem.Checked%2A> 속성은 `true` 또는 `false`이며 메뉴 항목이 선택 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="a6243-110">메뉴 항목의 <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> 속성은 선택한 항목의 모양을 사용자 지정 합니다. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>를 `true`로 설정 하면 항목 옆에 라디오 단추가 표시 됩니다. <xref:System.Windows.Forms.MenuItem.RadioCheck%2A>을 `false`로 설정 하면 항목 옆에 확인 표시가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a6243-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6243-111">참조</span><span class="sxs-lookup"><span data-stu-id="a6243-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="a6243-112">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="a6243-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
