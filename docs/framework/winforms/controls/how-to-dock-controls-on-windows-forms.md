---
title: '방법: Windows Forms에 컨트롤 도킹'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 82aef0ae9abacad33b21920f88591c0e4c33dfcb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460553"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="3cfad-102">방법: Windows Forms에 컨트롤 도킹</span><span class="sxs-lookup"><span data-stu-id="3cfad-102">How to: Dock controls on Windows Forms</span></span>

<span data-ttu-id="3cfad-103">컨트롤을 폼의 가장자리에 도킹 하거나 컨트롤의 컨테이너 (폼 또는 컨테이너 컨트롤)에 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="3cfad-104">예를 들어 Windows 탐색기는 창의 왼쪽에 <xref:System.Windows.Forms.TreeView> 컨트롤을 도킹 하 고 창의 오른쪽에 <xref:System.Windows.Forms.ListView> 컨트롤을 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="3cfad-105">표시 되는 모든 Windows Forms 컨트롤의 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용 하 여 도킹 모드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>

> [!NOTE]
> <span data-ttu-id="3cfad-106">컨트롤은 역방향 z 순서로 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-106">Controls are docked in reverse z-order.</span></span>

<span data-ttu-id="3cfad-107"><xref:System.Windows.Forms.Control.Dock%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성과 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="3cfad-108">자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3cfad-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>

## <a name="to-dock-a-control"></a><span data-ttu-id="3cfad-109">컨트롤을 도킹 하려면</span><span class="sxs-lookup"><span data-stu-id="3cfad-109">To dock a control</span></span>

1. <span data-ttu-id="3cfad-110">Visual Studio에서 도킹 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-110">In Visual Studio, select the control that you want to dock.</span></span>

2. <span data-ttu-id="3cfad-111">**속성** 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성의 오른쪽에 있는 화살표를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-111">In the **Properties** window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>

   <span data-ttu-id="3cfad-112">폼의 가장자리와 중심을 나타내는 일련의 상자가 표시 된 편집기가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>

3. <span data-ttu-id="3cfad-113">컨트롤을 도킹할 폼의 가장자리를 나타내는 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="3cfad-114">컨트롤의 폼 이나 컨테이너 컨트롤의 내용을 채우려면 가운데 상자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="3cfad-115">**(없음)** 을 클릭 하 여 도킹을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-115">Click **(none)** to disable docking.</span></span>

   <span data-ttu-id="3cfad-116">도킹 된 가장자리의 경계에 맞게 컨트롤의 크기가 자동으로 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3cfad-117">상속 된 컨트롤은 도킹할 수 있도록 `Protected` 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="3cfad-118">컨트롤의 액세스 수준을 변경 하려면 **속성** 창에서 해당 **Modifier** 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cfad-118">To change the access level of a control, set its **Modifier** property in the **Properties** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cfad-119">참조</span><span class="sxs-lookup"><span data-stu-id="3cfad-119">See also</span></span>

- [<span data-ttu-id="3cfad-120">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3cfad-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="3cfad-121">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="3cfad-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="3cfad-122">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3cfad-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="3cfad-123">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="3cfad-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="3cfad-124">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="3cfad-124">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="3cfad-125">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="3cfad-125">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="3cfad-126">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="3cfad-126">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="3cfad-127">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="3cfad-127">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
