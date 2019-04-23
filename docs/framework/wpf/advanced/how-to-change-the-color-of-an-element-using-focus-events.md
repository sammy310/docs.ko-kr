---
title: '방법: 포커스 이벤트를 사용하여 요소의 색 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 744963cc543110121a777e1d4c3cdcb3cec40d9e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217642"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="39b73-102">방법: 포커스 이벤트를 사용하여 요소의 색 변경</span><span class="sxs-lookup"><span data-stu-id="39b73-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="39b73-103">얻거나를 사용 하 여 포커스를 잃을 때 요소의 색을 변경 하는 방법을 보여 주는이 예제는 <xref:System.Windows.UIElement.GotFocus> 고 <xref:System.Windows.UIElement.LostFocus> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="39b73-104">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39b73-105">예제</span><span class="sxs-lookup"><span data-stu-id="39b73-105">Example</span></span>  
 <span data-ttu-id="39b73-106">다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 두 개의 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.Controls.Button> 개체 및 연결에 대 한 이벤트 처리기를 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트는 <xref:System.Windows.Controls.Button> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="39b73-107">다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="39b73-108">경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 얻으면을 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 빨간색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="39b73-109">경우는 <xref:System.Windows.Controls.Button> 키보드 포커스를 잃을 합니다 <xref:System.Windows.Controls.Control.Background%2A> 의 <xref:System.Windows.Controls.Button> 흰색으로 다시 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="39b73-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="39b73-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="39b73-110">See also</span></span>

- [<span data-ttu-id="39b73-111">입력 개요</span><span class="sxs-lookup"><span data-stu-id="39b73-111">Input Overview</span></span>](input-overview.md)
