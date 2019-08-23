---
title: '방법: 버퍼링된 그래픽 수동 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968595"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="9e1f9-102">방법: 버퍼링된 그래픽 수동 관리</span><span class="sxs-lookup"><span data-stu-id="9e1f9-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="9e1f9-103">고급 이중 버퍼링 시나리오의 경우 .NET Framework 클래스를 사용 하 여 사용자 고유의 더블 버퍼링 논리를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="9e1f9-104">개별 그래픽 버퍼 <xref:System.Drawing.BufferedGraphicsContext> 를 할당 하 고 관리 하는 클래스는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="9e1f9-105">모든 응용 프로그램에는 해당 <xref:System.Drawing.BufferedGraphicsContext> 응용 프로그램에 대 한 모든 기본 이중 버퍼링을 관리 하는 고유한 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="9e1f9-106">을 호출 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>하 여이 인스턴스에 대 한 참조를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="9e1f9-107">기본 System.drawing.bufferedgraphicscontext>에 대 한 참조를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="9e1f9-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="9e1f9-108">다음 코드 예제와 같이 속성을설정합니다.<xref:System.Drawing.BufferedGraphicsManager.Current%2A></span><span class="sxs-lookup"><span data-stu-id="9e1f9-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="9e1f9-109">클래스에서 <xref:System.Drawing.BufferedGraphicsContext> `Dispose` 받는참조에대해메서드를호출할필요가없습니다<xref:System.Drawing.BufferedGraphicsManager> .</span><span class="sxs-lookup"><span data-stu-id="9e1f9-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="9e1f9-110">는 <xref:System.Drawing.BufferedGraphicsManager> 기본<xref:System.Drawing.BufferedGraphicsContext> 인스턴스에 대 한 모든 메모리 할당과 배포를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="9e1f9-111">애니메이션 등 <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager>의 그래픽을 많이 사용 하는 응용 프로그램의 경우에서 제공하는대신전용를사용하여성능을향상시킬수있습니다.<xref:System.Drawing.BufferedGraphicsContext></span><span class="sxs-lookup"><span data-stu-id="9e1f9-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="9e1f9-112">이를 통해 응용 프로그램에서 사용 하는 메모리는 증가 하지만 응용 프로그램에 연결 된 다른 버퍼링 된 모든 그래픽을 관리 하는 성능 오버 헤드를 발생 시 키 지 않고 그래픽 버퍼를 개별적으로 만들고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="9e1f9-113">전용 System.drawing.bufferedgraphicscontext>를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9e1f9-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="9e1f9-114">다음 코드 예제와 같이 <xref:System.Drawing.BufferedGraphicsContext> 클래스의 새 인스턴스를 선언 하 고 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9e1f9-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="9e1f9-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="9e1f9-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="9e1f9-116">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="9e1f9-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="9e1f9-117">방법: 버퍼링 된 그래픽 수동 렌더링</span><span class="sxs-lookup"><span data-stu-id="9e1f9-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
