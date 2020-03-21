---
title: 목록보기 컨트롤에서 타일 보기 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 1478ba5e4f175cd7d9ec7ab5c3c4bc9050ce02fb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182161"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a><span data-ttu-id="ed56f-102">방법: Windows Forms ListView 컨트롤의 Tile 보기 사용</span><span class="sxs-lookup"><span data-stu-id="ed56f-102">How to: Enable Tile View in a Windows Forms ListView Control</span></span>
<span data-ttu-id="ed56f-103"><xref:System.Windows.Forms.ListView> 컨트롤의 바둑판식 뷰 기능을 통해 그래픽 정보와 텍스트 정보 간의 시각적 균형을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-103">With the tile view feature of the <xref:System.Windows.Forms.ListView> control, you can provide a visual balance between graphical and textual information.</span></span> <span data-ttu-id="ed56f-104">바둑판식 뷰에서 항목에 대해 표시되는 텍스트 정보는 세부 정보 뷰에 대해 정의된 열 정보와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-104">The textual information displayed for an item in tile view is the same as the column information defined for details view.</span></span> <span data-ttu-id="ed56f-105">바둑판식 뷰는 <xref:System.Windows.Forms.ListView> 컨트롤의 그룹화 또는 삽입 표시 기능과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-105">Tile view works in combination with either the grouping or insertion mark features in the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 <span data-ttu-id="ed56f-106">다음 이미지와 같이 바둑판식 뷰는 32 x 32 픽셀 아이콘과 여러 줄의 텍스트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-106">The tile view uses a 32 x 32 pixel icon and several lines of text, as shown in the following images.</span></span>  
  
 <span data-ttu-id="ed56f-107">![ListView 컨트롤의 타일 보기](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "바둑판식 뷰 아이콘 및 텍스트")</span><span class="sxs-lookup"><span data-stu-id="ed56f-107">![Tile View in a ListView Control](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "Tile view icons and text")</span></span>  

 <span data-ttu-id="ed56f-108">바둑판식 뷰를 사용하도록 설정하려면 <xref:System.Windows.Forms.ListView.View%2A> 속성을 <xref:System.Windows.Forms.View.Tile>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-108">To enable tile view, set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Tile>.</span></span> <span data-ttu-id="ed56f-109"><xref:System.Windows.Forms.ListView.TileSize%2A> 속성을 설정하여 타일 크기를 조정하고, <xref:System.Windows.Forms.ListView.Columns%2A> 컬렉션을 조정하여 타일에 표시되는 텍스트 줄 수를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-109">You can adjust the size of the tiles by setting the <xref:System.Windows.Forms.ListView.TileSize%2A> property, and the number of text lines displayed in the tile by adjusting the <xref:System.Windows.Forms.ListView.Columns%2A> collection.</span></span>  
  
### <a name="to-set-tile-view-programmatically"></a><span data-ttu-id="ed56f-110">프로그래밍 방식으로 바둑판식 뷰를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ed56f-110">To set tile view programmatically</span></span>  
  
1. <span data-ttu-id="ed56f-111"><xref:System.Windows.Forms.ListView> 컨트롤의 <xref:System.Windows.Forms.View> 열거형을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-111">Use the <xref:System.Windows.Forms.View> enumeration of the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a><span data-ttu-id="ed56f-112">예제</span><span class="sxs-lookup"><span data-stu-id="ed56f-112">Example</span></span>  
 <span data-ttu-id="ed56f-113">다음 전체 코드 예제에서는 타일이 3줄의 텍스트를 표시하도록 수정된 바둑판식 뷰를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-113">The following complete code example demonstrates Tile view with tiles modified to show three lines of text.</span></span> <span data-ttu-id="ed56f-114">줄 바꿈을 방지하기 위해 타일 크기가 조정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-114">The tile size has been adjusted to prevent line-wrapping.</span></span>  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed56f-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ed56f-115">Compiling the Code</span></span>  
 <span data-ttu-id="ed56f-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ed56f-116">This example requires:</span></span>  
  
- <span data-ttu-id="ed56f-117">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="ed56f-117">References to the System and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="ed56f-118">실행 파일과 동일한 디렉터리에 있는 book.ico로 명명된 아이콘 파일</span><span class="sxs-lookup"><span data-stu-id="ed56f-118">An icon file named book.ico in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed56f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed56f-119">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [<span data-ttu-id="ed56f-120">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="ed56f-120">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="ed56f-121">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="ed56f-121">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
