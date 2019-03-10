---
title: '방법: 폼 및 컨트롤에 이중 버퍼링 사용 하 여 그래픽 깜빡임 줄이기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing in Windows Forms
- graphics [Windows Forms], reducing double-buffered flicker
ms.assetid: 91083d3a-653f-4f15-a467-0f37b2aa39d6
ms.openlocfilehash: 95f8bdd9c30533b35782971459bad887e145adfe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713364"
---
# <a name="how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls"></a><span data-ttu-id="2d517-102">방법: 폼 및 컨트롤에 이중 버퍼링 사용 하 여 그래픽 깜빡임 줄이기</span><span class="sxs-lookup"><span data-stu-id="2d517-102">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>
<span data-ttu-id="2d517-103">이중 버퍼링은 메모리 버퍼를 사용하여 여러 그리기 작업과 관련된 깜박임 문제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-103">Double buffering uses a memory buffer to address the flicker problems associated with multiple paint operations.</span></span> <span data-ttu-id="2d517-104">이중 버퍼링을 사용하면 모든 그리기 작업이 그리기 화면 대신 메모리 버퍼에 먼저 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-104">When double buffering is enabled, all paint operations are first rendered to a memory buffer instead of the drawing surface on the screen.</span></span> <span data-ttu-id="2d517-105">모든 그리기 작업이 완료되면 메모리 버퍼가 연결된 그리기 화면에 직접 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-105">After all paint operations are completed, the memory buffer is copied directly to the drawing surface associated with it.</span></span> <span data-ttu-id="2d517-106">하나의 그래픽 작업만 화면에서 수행 되므로 복잡 한 그리기 작업과 관련 된 이미지 깜빡임이 제거 됩니다. 대부분의 응용 프로그램에서 제공 하는 기본 이중 버퍼링을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 최상의 결과 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-106">Because only one graphics operation is performed on the screen, the image flickering associated with complex painting operations is eliminated.For most applications, the default double buffering provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] will provide the best results.</span></span> <span data-ttu-id="2d517-107">표준 Windows Forms 컨트롤은 기본적으로 버퍼링 된 double입니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-107">Standard Windows Forms controls are double buffered by default.</span></span> <span data-ttu-id="2d517-108">두 가지 방법으로 컨트롤을 작성 한 폼에서 기본 이중 버퍼링을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-108">You can enable default double buffering in your forms and authored controls in two ways.</span></span> <span data-ttu-id="2d517-109">설정 하거나 합니다 <xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`, 하거나 호출할 수 있습니다는 <xref:System.Windows.Forms.Control.SetStyle%2A> 설정 하는 방법을 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 플래그를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-109">You can either set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`, or you can call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span> <span data-ttu-id="2d517-110">두 방법 모두 양식이 나 컨트롤에 기본 이중 버퍼링을 사용 하도록 설정 되며 깜박임 그래픽 렌더링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-110">Both methods will enable default double buffering for your form or control and provide flicker-free graphics rendering.</span></span> <span data-ttu-id="2d517-111">호출 된 <xref:System.Windows.Forms.Control.SetStyle%2A> 메서드는 모든 렌더링 코드를 작성 하는 사용자 지정 컨트롤에만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-111">Calling the <xref:System.Windows.Forms.Control.SetStyle%2A> method is recommended only for custom controls for which you have written all the rendering code.</span></span>  
  
 <span data-ttu-id="2d517-112">애니메이션 또는 고급 메모리 관리와 같은 고급 이중 버퍼링 시나리오에 대 한 사용자 고유의 이중 버퍼링 논리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-112">For more advanced double buffering scenarios, such as animation or advanced memory management, you can implement your own double buffering logic.</span></span> <span data-ttu-id="2d517-113">자세한 내용은 [방법: 버퍼링 된 그래픽 수동 관리](how-to-manually-manage-buffered-graphics.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-113">For more information, see [How to: Manually Manage Buffered Graphics](how-to-manually-manage-buffered-graphics.md).</span></span>  
  
### <a name="to-reduce-flicker"></a><span data-ttu-id="2d517-114">깜빡임을 줄이기 위해</span><span class="sxs-lookup"><span data-stu-id="2d517-114">To reduce flicker</span></span>  
  
-   <span data-ttu-id="2d517-115"><xref:System.Windows.Forms.Control.DoubleBuffered%2A> 속성을 `true`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d517-115">Set the <xref:System.Windows.Forms.Control.DoubleBuffered%2A> property to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#31)]  
  
 <span data-ttu-id="2d517-116">\- 또는 -</span><span class="sxs-lookup"><span data-stu-id="2d517-116">\- or -</span></span>  
  
-   <span data-ttu-id="2d517-117">호출을 <xref:System.Windows.Forms.Control.SetStyle%2A> 설정 하는 메서드를 <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> 플래그를 `true`.</span><span class="sxs-lookup"><span data-stu-id="2d517-117">Call the <xref:System.Windows.Forms.Control.SetStyle%2A> method to set the <xref:System.Windows.Forms.ControlStyles.OptimizedDoubleBuffer> flag to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#32)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#32](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#32)]  
  
## <a name="see-also"></a><span data-ttu-id="2d517-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="2d517-118">See also</span></span>
- <xref:System.Windows.Forms.Control.DoubleBuffered%2A>
- <xref:System.Windows.Forms.Control.SetStyle%2A>
- [<span data-ttu-id="2d517-119">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="2d517-119">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="2d517-120">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="2d517-120">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
