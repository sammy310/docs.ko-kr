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
ms.openlocfilehash: 6b86cadba19e82c487be88bcfb08edb51f93c540
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358303"
---
# <a name="how-to-make-an-object-follow-the-mouse-pointer"></a><span data-ttu-id="deb12-102">방법: 마우스 포인터를 따라 개체 이동</span><span class="sxs-lookup"><span data-stu-id="deb12-102">How to: Make an Object Follow the Mouse Pointer</span></span>
<span data-ttu-id="deb12-103">이 예제에서는 화면에서 마우스 포인터를 움직이면 개체의 크기를 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="deb12-103">This example shows how to change the dimensions of an object when the mouse pointer moves on the screen.</span></span>  
  
 <span data-ttu-id="deb12-104">예제에 포함 됩니다는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 만들어지는 파일의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 및 이벤트 처리기를 만드는 코드 숨김 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="deb12-104">The example includes an [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] and a code-behind file that creates the event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="deb12-105">예제</span><span class="sxs-lookup"><span data-stu-id="deb12-105">Example</span></span>  
 <span data-ttu-id="deb12-106">다음 [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] 만듭니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 되는 <xref:System.Windows.Shapes.Ellipse> 내에 <xref:System.Windows.Controls.StackPanel>에 대 한 이벤트 처리기를 연결 하 고는 <xref:System.Windows.UIElement.MouseMove> 이벤트.</span><span class="sxs-lookup"><span data-stu-id="deb12-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], which consists of an <xref:System.Windows.Shapes.Ellipse> inside of a <xref:System.Windows.Controls.StackPanel>, and attaches the event handler for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
 [!code-xaml[mouseMoveWithPointer#MouseMoveWithPointerXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml#mousemovewithpointerxaml)]  
  
 <span data-ttu-id="deb12-107">다음 코드 숨김 만듭니다는 <xref:System.Windows.UIElement.MouseMove> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="deb12-107">The following code behind creates the <xref:System.Windows.UIElement.MouseMove> event handler.</span></span>  <span data-ttu-id="deb12-108">마우스 포인터를 이동 하면, 높이 및 너비는 <xref:System.Windows.Shapes.Ellipse> 증가 및 감소 됩니다.</span><span class="sxs-lookup"><span data-stu-id="deb12-108">When the mouse pointer moves, the height and the width of the <xref:System.Windows.Shapes.Ellipse> are increased and decreased.</span></span>  
  
 [!code-csharp[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseMoveWithPointer/CSharp/Window1.xaml.cs#mousemovepointergetposition)]
 [!code-vb[mouseMoveWithPointer#MouseMovePointerGetPosition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseMoveWithPointer/VisualBasic/Window1.xaml.vb#mousemovepointergetposition)]  
  
## <a name="see-also"></a><span data-ttu-id="deb12-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="deb12-109">See also</span></span>
- [<span data-ttu-id="deb12-110">입력 개요</span><span class="sxs-lookup"><span data-stu-id="deb12-110">Input Overview</span></span>](input-overview.md)
