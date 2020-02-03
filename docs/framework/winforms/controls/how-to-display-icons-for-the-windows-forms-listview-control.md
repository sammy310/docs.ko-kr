---
title: ListView 컨트롤의 아이콘 표시
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
ms.openlocfilehash: 5fc54c448dae95cab50cdafa8403769fb421dffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744510"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="4f3d5-102">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="4f3d5-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="4f3d5-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤은 세 가지 이미지 목록에서 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="4f3d5-104">목록, 세부 정보 및 SmallIcon 보기는 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성에 지정 된 이미지 목록의 이미지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="4f3d5-105">LargeIcon view는 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성에 지정 된 이미지 목록의 이미지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="4f3d5-106">목록 뷰에는 <xref:System.Windows.Forms.ListView.StateImageList%2A> 속성에서 크거나 작은 아이콘 옆에 설정 된 추가 아이콘 집합이 표시 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="4f3d5-107">이미지 목록에 대 한 자세한 내용은 [Imagelist 구성 요소](imagelist-component-windows-forms.md) 및 [방법: Windows Forms imagelist 구성 요소를 사용 하 여 이미지 추가 또는 제거](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="4f3d5-108">목록 뷰에서 이미지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="4f3d5-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="4f3d5-109"><xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>또는 <xref:System.Windows.Forms.ListView.StateImageList%2A>등의 적절 한 속성을 사용 하려는 기존 <xref:System.Windows.Forms.ImageList> 구성 요소로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="4f3d5-110">이러한 속성은 디자이너에서 속성 창 또는 코드를 사용 하 여 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="4f3d5-111">연결 된 아이콘이 있는 각 목록 항목에 대해 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="4f3d5-112">이러한 속성은 코드 또는 **ListViewItem 컬렉션 편집기**내에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f3d5-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="4f3d5-113">**ListViewItem 컬렉션 편집기**를 열려면 **속성** 창의 <xref:System.Windows.Forms.ListView.Items%2A> 속성 옆에 있는 줄임표 단추 (...)를 클릭 하 여 줄임표 단추 (속성 창)를![클릭 합니다](./media/visual-studio-ellipsis-button.png).</span><span class="sxs-lookup"><span data-stu-id="4f3d5-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="4f3d5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f3d5-114">See also</span></span>

- [<span data-ttu-id="4f3d5-115">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="4f3d5-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="4f3d5-116">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="4f3d5-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4f3d5-117">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="4f3d5-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="4f3d5-118">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4f3d5-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="4f3d5-119">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4f3d5-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
