---
title: '방법: 이벤트를 사용하여 롤오버 효과 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 87740a215136863199d962a2704cf691f27fc3bc
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369099"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="3249d-102">방법: 이벤트를 사용하여 롤오버 효과 만들기</span><span class="sxs-lookup"><span data-stu-id="3249d-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="3249d-103">이 예제에서는 마우스 포인터가 요소에서 사용 하는 영역을 들어가고 대로 요소의 색을 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="3249d-104">이 예제는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3249d-105">이 예제에서는 이벤트를 사용 하는 방법에 설명 하지만이 동일한 효과 달성 하는 권장된 방법은 사용 하는 것을 <xref:System.Windows.Trigger> 스타일에서입니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="3249d-106">자세한 내용은 [스타일 지정 및 템플릿](../controls/styling-and-templating.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3249d-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3249d-107">예제</span><span class="sxs-lookup"><span data-stu-id="3249d-107">Example</span></span>  
 <span data-ttu-id="3249d-108">다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 구성 된 사용자 인터페이스를 만들고 <xref:System.Windows.Controls.Border> 주위를 <xref:System.Windows.Controls.TextBlock>를 연결 합니다 <xref:System.Windows.Input.Mouse.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기를를 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="3249d-109">다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.MouseEnter> 및 <xref:System.Windows.UIElement.MouseLeave> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="3249d-110">마우스 포인터가 내부로 들어갈 때 합니다 <xref:System.Windows.Controls.Border>, 배경의 <xref:System.Windows.Controls.Border> 빨간색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="3249d-111">마우스 포인터를 벗어날 때 합니다 <xref:System.Windows.Controls.Border>, 배경의 <xref:System.Windows.Controls.Border> 흰색으로 다시 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3249d-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
