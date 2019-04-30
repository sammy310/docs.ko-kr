---
title: ToolStripContainer 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
ms.openlocfilehash: c279316c2a372a1498707b27ec8658813306304b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009476"
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="ff778-102">ToolStripContainer 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ff778-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="ff778-103">A <xref:System.Windows.Forms.ToolStripContainer> 왼쪽, 오른쪽, 위쪽 및 아래쪽 면 배치 및 래프팅 할 패널이 있습니다 <xref:System.Windows.Forms.ToolStrip>를 <xref:System.Windows.Forms.MenuStrip>, 및 <xref:System.Windows.Forms.StatusStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="ff778-104">왼쪽 또는 오른쪽 <xref:System.Windows.Forms.ToolStripContainer>에 여러 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 배치하면 컨트롤이 세로로 쌓입니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="ff778-105">위쪽 또는 아래쪽 <xref:System.Windows.Forms.ToolStripContainer>에 배치하면 가로로 쌓입니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="ff778-106"><xref:System.Windows.Forms.ToolStripContainer>의 가운데 <xref:System.Windows.Forms.ToolStripContentPanel>을 사용하여 기존 컨트롤을 폼에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="ff778-107">임의 또는 모든 <xref:System.Windows.Forms.ToolStripContainer> 컨트롤은 디자인 타임에 직접 선택할 수 있고 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="ff778-108">각 패널을 <xref:System.Windows.Forms.ToolStripContainer> 는 확장명 및 축소 가능 하 고 포함 된 컨트롤을 사용 하 여 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="ff778-109">중요 한 ToolStripContainer 멤버</span><span class="sxs-lookup"><span data-stu-id="ff778-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="ff778-110">이름</span><span class="sxs-lookup"><span data-stu-id="ff778-110">Name</span></span>|<span data-ttu-id="ff778-111">설명</span><span class="sxs-lookup"><span data-stu-id="ff778-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="ff778-112">아래쪽 패널을 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="ff778-113">나타내는 값을 가져오거나 여부를의 아래쪽 패널을 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="ff778-114">왼쪽된 패널을 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="ff778-115">나타내는 값을 가져오거나 여부를의 왼쪽된 패널의 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="ff778-116">오른쪽 패널을 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="ff778-117">나타내는 값을 가져오거나 여부의 오른쪽 패널이 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="ff778-118">위쪽 패널을 가져옵니다는 <xref:System.Windows.Forms.ToolStripContainer>합니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="ff778-119">나타내는 값을 가져오거나 여부를의 위쪽 패널을 <xref:System.Windows.Forms.ToolStripContainer> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff778-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ff778-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="ff778-120">See also</span></span>

- <xref:System.Windows.Forms.ToolStripContainer>
- <xref:System.Windows.Forms.ToolStripContentPanel>
