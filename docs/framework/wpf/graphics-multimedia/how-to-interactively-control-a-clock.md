---
title: '방법: 대화형 시계 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 05989b6a03e03fb5723a70c9c36d5e32f9117049
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186591"
---
# <a name="how-to-interactively-control-a-clock"></a>방법: 대화형 시계 제어
A <xref:System.Windows.Media.Animation.Clock> 개체의 <xref:System.Windows.Media.Animation.ClockController> 속성을 사용 하면 대화형으로 시작, 일시 중지, 다시 시작, 검색, 채우기 기간이 시계를 이동 하 고 시계를 중지 합니다. 타이밍 트리의 루트 클록만 대화형으로 제어할 수 있습니다.  
  
> [!NOTE]
>  대화식으로 클록에 직접 작업할 필요 하지 않은 컨트롤 애니메이션에 대 한 가지 다른: 스토리 보드를 사용할 수도 있습니다. 스토리 보드는 태그와 코드 모두에서 지원 됩니다. 예를 들어 참조 [Storyboard를 사용 하 여 속성에 애니메이션 효과](how-to-animate-a-property-by-using-a-storyboard.md) 또는 [애니메이션 개요](animation-overview.md)합니다.  
  
 다음 예에서 애니메이션 클록을 대화형으로 제어 하는 여러 단추 사용 됩니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>참고자료

- [Storyboard를 사용하여 속성에 애니메이션 효과 주기](how-to-animate-a-property-by-using-a-storyboard.md)
- [애니메이션 개요](animation-overview.md)
