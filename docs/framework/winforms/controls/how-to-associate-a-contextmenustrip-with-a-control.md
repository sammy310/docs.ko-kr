---
title: '방법: 컨트롤에 ContextMenuStrip 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [Windows Forms], relating
- ContextMenuStrips [Windows Forms], associating with controls
- context menus [Windows Forms], associating with controls
- ContextMenuStrips [Windows Forms], relating
ms.assetid: 6fc40a42-5d69-427f-aa30-0a146193226b
ms.openlocfilehash: e1b2a49196d6da66d478a3d44eab64298cebe969
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586612"
---
# <a name="how-to-associate-a-contextmenustrip-with-a-control"></a><span data-ttu-id="9daff-102">방법: 컨트롤에 ContextMenuStrip 연결</span><span class="sxs-lookup"><span data-stu-id="9daff-102">How to: Associate a ContextMenuStrip with a Control</span></span>
<span data-ttu-id="9daff-103">컨트롤 및 바로 가기 메뉴를 만든 후 다음 절차를 따라 사용자가 컨트롤을 마우스 오른쪽 단추로 클릭할 때 지정된 바로 가기 메뉴를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-103">After creating your controls and shortcut menus, use the following procedures to display a given shortcut menu when the user right-clicks the control.</span></span> <span data-ttu-id="9daff-104">이러한 절차에서는 <xref:System.Windows.Forms.ContextMenuStrip>을 Windows Form 및 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-104">These procedures associate a <xref:System.Windows.Forms.ContextMenuStrip> with a Windows Form and with a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-windows-form"></a><span data-ttu-id="9daff-105">ContextMenuStrip을 Windows Form과 연결하려면</span><span class="sxs-lookup"><span data-stu-id="9daff-105">To associate a ContextMenuStrip with a Windows Form</span></span>  
  
1. <span data-ttu-id="9daff-106"><xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-106">Set the <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
### <a name="to-associate-a-contextmenustrip-with-a-toolstrip-control"></a><span data-ttu-id="9daff-107">ContextMenuStrip을 ToolStrip 컨트롤과 연결하려면</span><span class="sxs-lookup"><span data-stu-id="9daff-107">To associate a ContextMenuStrip with a ToolStrip control</span></span>  
  
1. <span data-ttu-id="9daff-108">컨트롤의 <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> 속성을 연결된 <xref:System.Windows.Forms.ContextMenuStrip>의 이름으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-108">Set the control's <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> property to the name of the associated <xref:System.Windows.Forms.ContextMenuStrip>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9daff-109">예제</span><span class="sxs-lookup"><span data-stu-id="9daff-109">Example</span></span>  
 <span data-ttu-id="9daff-110">다음 코드 예제에서는 Windows Form 및 <xref:System.Windows.Forms.ToolStrip>을 만들고 다른 <xref:System.Windows.Forms.ContextMenuStrip> 컨트롤을 각각에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-110">The following code example creates a Windows Form and a <xref:System.Windows.Forms.ToolStrip>, and associates a different <xref:System.Windows.Forms.ContextMenuStrip> control with each of them.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ContextMenuStrip#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ContextMenuStrip/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9daff-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9daff-111">Compiling the Code</span></span>  
 <span data-ttu-id="9daff-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9daff-112">This example requires:</span></span>  
  
- <span data-ttu-id="9daff-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="9daff-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9daff-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="9daff-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="9daff-115">방법: ContextMenuStrip에 메뉴 항목 추가</span><span class="sxs-lookup"><span data-stu-id="9daff-115">How to: Add Menu Items to a ContextMenuStrip</span></span>](how-to-add-menu-items-to-a-contextmenustrip.md)
- [<span data-ttu-id="9daff-116">ContextMenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9daff-116">ContextMenuStrip Control</span></span>](contextmenustrip-control.md)
