---
title: SplitContainer 컨트롤(Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: 504a2396902fecf2ac17c2db434fef68ff2ece45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009723"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="6e846-102">SplitContainer 컨트롤(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6e846-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="6e846-103">Windows Forms `SplitContainer` 컨트롤은 복합으로 간주될 수 있습니다. 이동 가능한 막대로 구분된 두 개의 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="6e846-104">마우스 포인터가 막대 위에 있으면 포인터 모양이 변경되어 막대를 이동할 수 있음을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e846-105">에 **도구 상자**이 대체를 제어 합니다 <xref:System.Windows.Forms.Splitter> 이전 버전의 Visual Studio에 있던 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="6e846-106">`SplitContainer` 컨트롤이 <xref:System.Windows.Forms.Splitter> 컨트롤보다 훨씬 선호됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="6e846-107">기존 응용 프로그램과의 호환성을 위해 <xref:System.Windows.Forms.Splitter> 클래스도 .NET Framework에 여전히 포함되어 있지만 새 프로젝트에는 `SplitContainer` 컨트롤을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="6e846-108">`SplitContainer` 컨트롤을 통해 복잡한 사용자 인터페이스를 만들 수 있습니다. 한 패널에서 선택한 항목에 따라 다른 패널에 표시되는 개체가 결정되는 경우도 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="6e846-109">이 정렬은 정보를 표시하고 찾는 데 매우 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="6e846-110">두 개의 패널이 있으므로 영역의 정보를 집계할 수 있으며, 막대 또는 "분할자"를 통해 사용자가 쉽게 패널 크기를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6e846-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6e846-111">In This Section</span></span>  
 [<span data-ttu-id="6e846-112">SplitContainer 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="6e846-112">SplitContainer Control Overview</span></span>](splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="6e846-113">`SplitContainer` 컨트롤을 소개하고 일반적으로 사용되는 속성, 메서드 및 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="6e846-114">방법: 크기 조정 및 분할 창에서 위치 지정 동작 정의</span><span class="sxs-lookup"><span data-stu-id="6e846-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="6e846-115">`SplitContainer` 컨트롤 내에서 분할자를 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="6e846-116">방법: 가로로 창 분합니다</span><span class="sxs-lookup"><span data-stu-id="6e846-116">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="6e846-117">`SplitContainer` 컨트롤 내에서 분할자의 방향을 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="6e846-118">방법: Windows Forms로 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="6e846-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="6e846-119">Microsoft Outlook에서 사용되는 것과 비슷한 다중 창 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="6e846-120">또한 참조 [방법: 디자이너를 사용 하 여 가로로 창 분할](how-to-split-a-window-horizontally-using-the-designer.md), [방법: Windows Form에 Windows 탐색기 스타일 인터페이스 만들기](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [방법: 디자이너를 사용 하 여 Windows Forms로 다중 창 사용자 인터페이스 만들기](create-a-multipane-user-interface-with-wf-using-the-designer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](how-to-create-a-windows-explorer-style-interface-on-a-windows-form.md), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6e846-121">참조</span><span class="sxs-lookup"><span data-stu-id="6e846-121">Reference</span></span>  
 <span data-ttu-id="6e846-122"><xref:System.Windows.Forms.SplitContainer> 클래스</span><span class="sxs-lookup"><span data-stu-id="6e846-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="6e846-123">이 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6e846-124">관련 단원</span><span class="sxs-lookup"><span data-stu-id="6e846-124">Related Sections</span></span>  
 [<span data-ttu-id="6e846-125">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6e846-125">Windows Forms Controls</span></span>](index.md)  
 <span data-ttu-id="6e846-126">Windows Forms에서 작동하도록 특별히 설계된 컨트롤에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="6e846-127">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="6e846-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="6e846-128">사용 방법에 대한 정보 링크를 포함하는 Windows Forms 컨트롤의 전체 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e846-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
