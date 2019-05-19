---
title: '방법: Windows Forms ListView 컨트롤에 대한 아이콘 표시'
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
ms.openlocfilehash: 80a827a88ac92008c7fe2a642d1d4b59a18f89da
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880404"
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="fb807-102">방법: Windows Forms ListView 컨트롤에 대한 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="fb807-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="fb807-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 3 개 이미지 목록에서 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="fb807-104">목록, 세부 정보 및 SmallIcon 보기에 지정 된 이미지 목록의 이미지에 표시 된 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="fb807-105">큰 아이콘 보기에 지정 된 이미지 목록의 이미지를 표시 합니다 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="fb807-106">목록 보기에서 설정 아이콘의 추가 집합을 표시할 수도 있습니다는 <xref:System.Windows.Forms.ListView.StateImageList%2A> 크고 작은 아이콘과 옆에 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="fb807-107">이미지 목록에 대 한 자세한 내용은 참조 하세요. [ImageList 구성 요소](imagelist-component-windows-forms.md) 고 [방법: 제거 이미지는 Windows Forms ImageList 구성 요소 추가 또는](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-107">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="fb807-108">목록 보기에 이미지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="fb807-108">To display images in a list view</span></span>  
  
1. <span data-ttu-id="fb807-109">적절 한 속성을 설정-<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, 또는 <xref:System.Windows.Forms.ListView.StateImageList%2A>-기존 <xref:System.Windows.Forms.ImageList> 사용 하려는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="fb807-110">속성 창 사용 하 여 디자이너에서 또는 코드에서 이러한 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2. <span data-ttu-id="fb807-111">설정 된 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 연결된 아이콘이 포함 된 각 목록 항목의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="fb807-112">또는 코드에서 이러한 속성을 설정할 수는 **ListViewItem 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="fb807-113">열려는 합니다 **ListViewItem 컬렉션 편집기**, 줄임표 단추를 클릭 (![의 줄임표 단추 (...)의 Visual Studio 속성 창에서](./media/visual-studio-ellipsis-button.png)) 옆에 <xref:System.Windows.Forms.ListView.Items%2A> 속성을 **속성** 창입니다.</span><span class="sxs-lookup"><span data-stu-id="fb807-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="fb807-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="fb807-114">See also</span></span>

- [<span data-ttu-id="fb807-115">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fb807-115">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="fb807-116">방법: Windows Forms ListView 컨트롤을 사용 하 여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="fb807-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="fb807-117">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="fb807-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [<span data-ttu-id="fb807-118">방법: TreeView 또는 ListView 컨트롤 (Windows Forms)에 사용자 지정 정보 추가</span><span class="sxs-lookup"><span data-stu-id="fb807-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [<span data-ttu-id="fb807-119">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fb807-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
