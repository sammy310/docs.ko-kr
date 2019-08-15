---
title: '방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 타일 보기 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- tile view feature
- ListView control [Windows Forms], tile view
- tiling [Windows Forms], Windows Forms, controls
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
ms.openlocfilehash: 8a45a8a484bd373f53585b1b113a51e59b30fca2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040359"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="05e01-102">방법: 디자이너를 사용하여 Windows Forms ListView 컨트롤에서 타일 보기 사용</span><span class="sxs-lookup"><span data-stu-id="05e01-102">How to: Enable Tile View in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="05e01-103"><xref:System.Windows.Forms.ListView> 컨트롤의 바둑판식 뷰 기능을 사용 하면 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-103">The tile view feature of the <xref:System.Windows.Forms.ListView> control enables you to provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="05e01-104">바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="05e01-105"><xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 또는 삽입 표시 기능과 함께 바둑판식 뷰 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-105">Tile view functions in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>

 <span data-ttu-id="05e01-106">다음 그림에 표시 된 것 처럼 타일 보기는 32 x 32 아이콘과 여러 줄의 텍스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-106">The tile view uses a 32 x 32 icon and several lines of text, as shown in the following image.</span></span>

 <span data-ttu-id="05e01-107">![ListView 컨트롤의 Tile 보기](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "바둑판식 뷰 아이콘 및 텍스트")</span><span class="sxs-lookup"><span data-stu-id="05e01-107">![Tile View in a ListView Control](./media/enable-tile-view-in-a-wf-listview-control-using-the-designer/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>

 <span data-ttu-id="05e01-108">바둑판식 뷰 속성 및 메서드를 사용 하면 각 항목에 대해 표시할 열 필드를 지정 하 고 타일 보기 창에서 모든 항목의 크기와 모양을 전체적으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-108">Tile view properties and methods enable you to specify which column fields to display for each item, and to collectively control the size and appearance of all items within a tile view window.</span></span> <span data-ttu-id="05e01-109">쉽게 이해할 수 있도록 타일에서 텍스트의 첫 번째 줄은 항상 항목의 이름입니다. 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-109">For clarity, the first line of text in a tile is always the item's name; it cannot be changed.</span></span>

 <span data-ttu-id="05e01-110">다음 절차에는 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 폼을 포함 하는 **Windows 응용 프로그램** 프로젝트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="05e01-111">이러한 프로젝트 [를 설정 하는 방법에 대 한 자세한 내용은 방법: Windows Forms 응용 프로그램 프로젝트](/visualstudio/ide/step-1-create-a-windows-forms-application-project) [를 만들고 방법: Windows Forms](how-to-add-controls-to-windows-forms.md)에 컨트롤을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

> [!NOTE]
> <span data-ttu-id="05e01-112">바둑판식 뷰는 애플리케이션이 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 메서드를 호출할 때 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-112">The tile view is available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05e01-113">이전 운영 체제에서는 바둑판식 뷰와 관련된 코드가 아무 효과도 없으며, <xref:System.Windows.Forms.ListView> 컨트롤이 큰 아이콘 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-113">On earlier operating systems, any code related to the tile view has no effect, and the <xref:System.Windows.Forms.ListView> control displays in the large icon view.</span></span> <span data-ttu-id="05e01-114">자세한 내용은 <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05e01-114">For more information, see <xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>.</span></span>

## <a name="to-set-tile-view-in-the-designer"></a><span data-ttu-id="05e01-115">디자이너에서 바둑판식 뷰를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="05e01-115">To set tile view in the designer</span></span>

1. <span data-ttu-id="05e01-116">Visual Studio의 폼에서 <xref:System.Windows.Forms.ListView> 컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-116">In Visual Studio, select the <xref:System.Windows.Forms.ListView> control on your form.</span></span>

2. <span data-ttu-id="05e01-117">**속성** 창에서 <xref:System.Windows.Forms.ListView.View%2A> 속성을 선택 하 고 **타일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05e01-117">In the **Properties** window, select the <xref:System.Windows.Forms.ListView.View%2A> property and choose **Tile**.</span></span>

## <a name="see-also"></a><span data-ttu-id="05e01-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="05e01-118">See also</span></span>

- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="05e01-119">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="05e01-119">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
