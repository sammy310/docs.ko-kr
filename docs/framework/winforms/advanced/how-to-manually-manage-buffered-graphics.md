---
title: '방법: 버퍼링 된 그래픽 수동 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 013118ea15184ee4dfbbcd5dcaff054a2cf6a9ba
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57702934"
---
# <a name="how-to-manually-manage-buffered-graphics"></a>방법: 버퍼링 된 그래픽 수동 관리
고급 이중 버퍼링 시나리오에서는 사용할 수 있습니다는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 고유의 이중 버퍼링 논리를 구현 하는 클래스입니다. 클래스가 할당 하 고 개별 그래픽 버퍼를 관리 하는 일을 담당 합니다 <xref:System.Drawing.BufferedGraphicsContext> 클래스입니다. 모든 응용 프로그램에는 자체 기본 <xref:System.Drawing.BufferedGraphicsContext> 관리 하는 모든 기본 이중 버퍼링 해당 응용 프로그램에 대 한 합니다. 호출 하 여이 인스턴스에 대 한 참조를 검색할 수 있습니다는 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>합니다.  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a>BufferedGraphicsContext 기본값에 대 한 참조를 가져오려면  
  
-   설정 된 <xref:System.Drawing.BufferedGraphicsManager.Current%2A> 속성을 다음 코드 예제에 표시 된 대로 합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    >  호출할 필요가 없습니다를 `Dispose` 메서드를 <xref:System.Drawing.BufferedGraphicsContext> 에서 수신 하는 참조는 <xref:System.Drawing.BufferedGraphicsManager> 클래스입니다. 합니다 <xref:System.Drawing.BufferedGraphicsManager> 메모리 할당 및 기본값에 대 한 배포의 모든 처리 <xref:System.Drawing.BufferedGraphicsContext> 인스턴스.  
  
     애니메이션 같은 그래픽 위주 응용 프로그램에 대 한 경우에 따라 성능을 향상 시킬 수 전용을 사용 하 여 <xref:System.Drawing.BufferedGraphicsContext> 대신 합니다 <xref:System.Drawing.BufferedGraphicsContext> 제공한는 <xref:System.Drawing.BufferedGraphicsManager>합니다. 이 통해 만들고 응용 프로그램에서 사용 하는 메모리는 클 수 있지만 모든 다른 버퍼링 된 그래픽 응용 프로그램을 사용 하 여 연결을 관리 하는 성능 오버 헤드를 초래 하지 않고 그래픽 버퍼를 개별적으로 관리할 수 있습니다.  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a>전용된 BufferedGraphicsContext를 만들려면  
  
-   새 인스턴스를 만들고 선언는 <xref:System.Drawing.BufferedGraphicsContext> 클래스에 다음 코드 예제에 표시 된 대로 합니다.  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Drawing.BufferedGraphicsContext>
- [이중 버퍼링 그래픽](double-buffered-graphics.md)
- [방법: 버퍼링 된 그래픽 수동 렌더링](how-to-manually-render-buffered-graphics.md)
