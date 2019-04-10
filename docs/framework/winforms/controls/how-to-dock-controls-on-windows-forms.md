---
title: '방법: Windows Forms에서 컨트롤 도킹'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 61ccad615eec81eb1aa77e6a99d48ef29ecb5be2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231528"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="1b917-102">방법: Windows Forms에서 컨트롤 도킹</span><span class="sxs-lookup"><span data-stu-id="1b917-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="1b917-103">폼의 가장자리에 컨트롤을 도킹 하거나 컨트롤의 컨테이너 (폼 또는 컨테이너 컨트롤)을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="1b917-104">Windows 탐색기 창을 도킹 하는 예를 들어, 해당 <xref:System.Windows.Forms.TreeView> 창의 왼쪽에는 컨트롤 및 해당 <xref:System.Windows.Forms.ListView> 창의 왼쪽에서 오른쪽으로 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="1b917-105">사용 된 <xref:System.Windows.Forms.Control.Dock%2A> 표시 하는 모든 Windows Forms 컨트롤 도킹 모드를 정의 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b917-106">역방향 z 순서에 컨트롤 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="1b917-107">합니다 <xref:System.Windows.Forms.Control.Dock%2A> 상호 작용 하는 속성을 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="1b917-108">자세한 내용은 [AutoSize 속성 개요](autosize-property-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="1b917-109">컨트롤을 도킹 하려면</span><span class="sxs-lookup"><span data-stu-id="1b917-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="1b917-110">도킹 하려는 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="1b917-111">속성 창에서 오른쪽의 화살표를 클릭 합니다 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="1b917-112">편집기에는 일련의 가장자리와 폼의 중심을 나타내는 상자를 보여 주는 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="1b917-113">컨트롤을 도킹 하려면 폼의 가장자리를 나타내는 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="1b917-114">컨트롤의 폼 이나 컨테이너 컨트롤의 내용을 채울 가운데 상자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="1b917-115">클릭 **(없음)** 도킹을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="1b917-116">컨트롤 크기가 자동으로 도킹된 된 가장자리의 경계에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1b917-117">상속 된 컨트롤 해야 `Protected` 도킹 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="1b917-118">컨트롤의 액세스 수준을 변경 하려면 해당 **한정자** 속성 창에서 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="1b917-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b917-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="1b917-119">See also</span></span>

- [<span data-ttu-id="1b917-120">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1b917-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="1b917-121">Windows Forms에서 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="1b917-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="1b917-122">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="1b917-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="1b917-123">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1b917-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="1b917-124">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1b917-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="1b917-125">방법: FlowLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="1b917-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="1b917-126">방법: TableLayoutPanel 컨트롤에서 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="1b917-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="1b917-127">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="1b917-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="1b917-128">방법: Windows Forms에서 컨트롤 고정</span><span class="sxs-lookup"><span data-stu-id="1b917-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
