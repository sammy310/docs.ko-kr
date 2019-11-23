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
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004828"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="873f9-102">방법: 포커스 이벤트를 사용하여 요소의 색 변경</span><span class="sxs-lookup"><span data-stu-id="873f9-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="873f9-103">이 예제에서는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트를 사용 하 여 포커스를 얻거나 잃을 때 요소의 색을 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="873f9-104">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일 및 코드 숨김으로 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="873f9-105">예제</span><span class="sxs-lookup"><span data-stu-id="873f9-105">Example</span></span>  
 <span data-ttu-id="873f9-106">다음 XAML에서는 두 개의 <xref:System.Windows.Controls.Button> 개체로 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트의 이벤트 처리기를 <xref:System.Windows.Controls.Button> 개체에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="873f9-107">다음 코드는 <xref:System.Windows.UIElement.GotFocus> 및 <xref:System.Windows.UIElement.LostFocus> 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="873f9-108"><xref:System.Windows.Controls.Button>에서 키보드 포커스를 얻으면 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A> 빨강으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="873f9-109"><xref:System.Windows.Controls.Button> 키보드 포커스를 잃으면 <xref:System.Windows.Controls.Button>의 <xref:System.Windows.Controls.Control.Background%2A> 다시 흰색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="873f9-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="873f9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="873f9-110">See also</span></span>

- [<span data-ttu-id="873f9-111">입력 개요</span><span class="sxs-lookup"><span data-stu-id="873f9-111">Input Overview</span></span>](input-overview.md)
