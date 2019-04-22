---
title: '방법: 끌어온 GridView 열 머리글에 대한 스타일 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090097"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="4cf93-102">방법: 끌어온 GridView 열 머리글에 대한 스타일 만들기</span><span class="sxs-lookup"><span data-stu-id="4cf93-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="4cf93-103">이 예제는 끌어 온된 모양의 변경 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.GridViewColumnHeader> 사용자가 열의 위치를 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="4cf93-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cf93-104">예제</span><span class="sxs-lookup"><span data-stu-id="4cf93-104">Example</span></span>  
 <span data-ttu-id="4cf93-105">다른 위치로 열 머리글을 끌면를 <xref:System.Windows.Controls.ListView> 를 사용 하는 <xref:System.Windows.Controls.GridView> 보기 모드에 대 한 열을 새 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="4cf93-106">열 머리글을 끄는 동안 헤더의 움직이는 복사본이 원래 머리글 외에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="4cf93-107">열 머리글을 <xref:System.Windows.Controls.GridView> 으로 표시 됩니다는 <xref:System.Windows.Controls.GridViewColumnHeader> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="4cf93-108">부동 및 원래 머리글 모두의 모양을 사용자 지정 하려면 설정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 수정 하는 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="4cf93-109">이러한 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 때 적용 되는 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 `true` 하며 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 값이 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="4cf93-110">사용자의 마우스 단추를 누를 누르고 위에 마우스를 일시 중지할 경우 합니다 <xref:System.Windows.Controls.GridViewColumnHeader>의 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 변경 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="4cf93-111">마찬가지로, 사용자가 시작할 때 끌기 작업을 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 변경 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="4cf93-112">다음 예제에서는 설정 하는 방법을 보여 줍니다 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 변경 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.Background%2A> 사용자가 열을 새 위치로 끌 때 원래 머리글과 부동 머리글의 색입니다.</span><span class="sxs-lookup"><span data-stu-id="4cf93-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="4cf93-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="4cf93-113">See also</span></span>

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="4cf93-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="4cf93-114">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="4cf93-115">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="4cf93-115">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="4cf93-116">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="4cf93-116">GridView Overview</span></span>](gridview-overview.md)
