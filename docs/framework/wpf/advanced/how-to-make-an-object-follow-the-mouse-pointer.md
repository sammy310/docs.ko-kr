---
title: '방법: 마우스 포인터를 따라 개체 이동'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- following the mouse pointer (cursor)
- mouse pointer (cursor), making objects follow
- cursor (mouse pointer), making objects follow
ms.assetid: 50b20415-14bc-405c-baf3-2fb254fffde3
ms.openlocfilehash: 4ef3028b6c71b94a593d168ad6570c4aec12b86b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005072"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="0367e-102">방법: 마우스 포인터를 따라 개체 이동</span><span class="sxs-lookup"><span data-stu-id="0367e-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="0367e-103">이 예제에서는 마우스 포인터가 화면에서 이동할 때 개체의 크기를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0367e-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="0367e-104">이 예제에는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]을 만드는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일과 이벤트 처리기를 만드는 코드를 만드는 파일이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0367e-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0367e-105">예제</span><span class="sxs-lookup"><span data-stu-id="0367e-105">Example</span></span>  
 <span data-ttu-id="0367e-106">다음 XAML은 <xref:System.Windows.Controls.StackPanel> 내의 <xref:System.Windows.Shapes.Ellipse>로 구성 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]을 만들고 <xref:System.Windows.UIElement.MouseMove> 이벤트에 대 한 이벤트 처리기를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0367e-106">The following XAML creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="0367e-107">다음 코드는 <xref:System.Windows.UIElement.MouseMove> 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0367e-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="0367e-108">마우스 포인터를 움직이면 <xref:System.Windows.Shapes.Ellipse>의 높이와 너비가 증가 하 고 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0367e-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="0367e-109">참조</span><span class="sxs-lookup"><span data-stu-id="0367e-109">See also</span></span>

- [<span data-ttu-id="0367e-110">입력 개요</span><span class="sxs-lookup"><span data-stu-id="0367e-110">Input Overview</span></span>](input-overview.md)
