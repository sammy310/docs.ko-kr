---
title: ContextMenuStrip 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ContextMenuStrip
helpviewer_keywords:
- context menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- shortcut menus [Windows Forms], ContextMenuStrip control [Windows Forms]
- ContextMenuStrip control [Windows Forms], about ContextMenuStrip control
ms.assetid: 9787cdb3-88f1-4198-972f-eefd9524ce39
ms.openlocfilehash: e4a6add5297ba7db606ca1891e9279141f8d6d20
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962153"
---
# <a name="contextmenustrip-control-overview"></a><span data-ttu-id="f874a-102">ContextMenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f874a-102">ContextMenuStrip Control Overview</span></span>
> [!NOTE]
> <span data-ttu-id="f874a-103">컨트롤은 기능을 대체 하 고 <xref:System.Windows.Forms.ContextMenu> 컨트롤에 기능을 추가 합니다 <xref:System.Windows.Forms.ContextMenu> . 그러나 선택 하는 경우 컨트롤은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="f874a-103">The <xref:System.Windows.Forms.ContextMenuStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ContextMenu> control; however, the <xref:System.Windows.Forms.ContextMenu> control is retained for backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="f874a-104">사용자가 마우스 오른쪽 단추를 클릭 하면 상황에 맞는 메뉴 라고도 하는 바로 가기 메뉴가 마우스 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-104">Shortcut menus, also called context menus, appear at the mouse position when the user clicks the right mouse button.</span></span> <span data-ttu-id="f874a-105">바로 가기 *메뉴* 는 클라이언트 영역 또는 마우스 포인터 위치에 있는 컨트롤에 대 한 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-105">Shortcut *menus* provide options for the client area or the control at the mouse pointer location.</span></span>  
  
 <span data-ttu-id="f874a-106">컨트롤은 새로운 <xref:System.Windows.Forms.ToolStrip> 및 관련 컨트롤과 원활 하 게 작동 하도록 설계 되었지만를 <xref:System.Windows.Forms.ContextMenuStrip> 다른 컨트롤과 쉽게 연결할 수 있습니다. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="f874a-106">The <xref:System.Windows.Forms.ContextMenuStrip> control is designed to work seamlessly with the new <xref:System.Windows.Forms.ToolStrip> and related controls, but you can associate a <xref:System.Windows.Forms.ContextMenuStrip> with other controls just as easily.</span></span>  
  
 <span data-ttu-id="f874a-107">다음 표에서는 중요 한 <xref:System.Windows.Forms.ContextMenuStrip> 도우미 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-107">The following table shows the important <xref:System.Windows.Forms.ContextMenuStrip> companion classes.</span></span>  
  
|<span data-ttu-id="f874a-108">클래스</span><span class="sxs-lookup"><span data-stu-id="f874a-108">Class</span></span>|<span data-ttu-id="f874a-109">설명</span><span class="sxs-lookup"><span data-stu-id="f874a-109">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|<span data-ttu-id="f874a-110">에 표시 된 선택 가능한 옵션을 나타내는 <xref:System.Windows.Forms.MenuStrip> 또는 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-110">Represents a selectable option displayed on a <xref:System.Windows.Forms.MenuStrip> or <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="f874a-111">사용자가 <xref:System.Windows.Forms.ToolStripDropDownButton> 또는 더 높은 수준의 메뉴 항목을 클릭할 때 표시 되는 목록에서 단일 항목을 선택할 수 있도록 하는 컨트롤을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-111">Represents a control that enables the user to select a single item from a list that is displayed when the user clicks a <xref:System.Windows.Forms.ToolStripDropDownButton> or a higher-level menu item.</span></span>|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|<span data-ttu-id="f874a-112">클릭 하면 드롭다운 항목을 표시 하 <xref:System.Windows.Forms.ToolStripItem> 는에서 파생 된 컨트롤에 대 한 기본 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f874a-112">Provides basic functionality for controls derived from <xref:System.Windows.Forms.ToolStripItem> that display drop-down items when clicked.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f874a-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f874a-113">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
