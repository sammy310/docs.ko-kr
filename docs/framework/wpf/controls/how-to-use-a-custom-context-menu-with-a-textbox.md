---
title: '방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: 805f5205a91f9b3da0c48c987f1f49f1d81892b7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358602"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="9a0ac-102">방법: TextBox에 사용자 지정 컨텍스트 메뉴 사용</span><span class="sxs-lookup"><span data-stu-id="9a0ac-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="9a0ac-103">정의 대 한 간단한 사용자 지정 상황에 맞는 메뉴를 구현 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a0ac-104">예제</span><span class="sxs-lookup"><span data-stu-id="9a0ac-104">Example</span></span>  
 <span data-ttu-id="9a0ac-105">다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 정의 하는 예제는 <xref:System.Windows.Controls.TextBox> 사용자 지정 상황에 맞는 메뉴를 포함 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="9a0ac-106">상황에 맞는 메뉴를 사용 하 여 정의 되는 <xref:System.Windows.Controls.ContextMenu> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="9a0ac-107">일련의 구성 자체 상황에 맞는 메뉴 <xref:System.Windows.Controls.MenuItem> 요소 및 <xref:System.Windows.Controls.Separator> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="9a0ac-108">각 <xref:System.Windows.Controls.MenuItem> 요소는 상황에 맞는 메뉴 명령을 정의 합니다 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 메뉴 명령에 대 한 표시 텍스트를 정의 하는 특성 및 <xref:System.Windows.Controls.MenuItem.Click> 특성 각 메뉴 항목에 대 한 처리기 메서드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="9a0ac-109"><xref:System.Windows.Controls.Separator> 요소 수행 하면 이전 및 이후의 메뉴 항목 사이 렌더링할지 줄을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="9a0ac-110">예제</span><span class="sxs-lookup"><span data-stu-id="9a0ac-110">Example</span></span>  
 <span data-ttu-id="9a0ac-111">다음 예제에서는 이전 상황에 맞는 메뉴 정의 대 한 구현 코드와 사용 하도록 설정 하 고 상황에 맞는 메뉴를 사용 하지 않도록 설정 하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="9a0ac-112">합니다 <xref:System.Windows.Controls.ContextMenu.Opened> 이벤트에 동적으로 사용 하도록 설정의 현재 상태에 따라 특정 명령을 사용 하지 않도록 설정 되는 <xref:System.Windows.Controls.TextBox>합니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="9a0ac-113">기본 상황에 맞는 메뉴를 복원 하려면 사용 합니다 <xref:System.Windows.DependencyObject.ClearValue%2A> 값의 선택을 취소 하는 방법의 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9a0ac-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="9a0ac-114">상황에 맞는 메뉴를 완전히 비활성화 하려면 설정 합니다 <xref:System.Windows.FrameworkElement.ContextMenu%2A> 속성을 null 참조 (`Nothing` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="9a0ac-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="9a0ac-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a0ac-115">See also</span></span>
- [<span data-ttu-id="9a0ac-116">상황에 맞는 메뉴로 맞춤법 검사 사용</span><span class="sxs-lookup"><span data-stu-id="9a0ac-116">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="9a0ac-117">TextBox 개요</span><span class="sxs-lookup"><span data-stu-id="9a0ac-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="9a0ac-118">RichTextBox 개요</span><span class="sxs-lookup"><span data-stu-id="9a0ac-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
