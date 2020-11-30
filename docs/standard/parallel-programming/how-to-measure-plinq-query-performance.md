---
title: '방법: PLINQ 쿼리 성능 측정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to measure performance
ms.assetid: 491ba43b-2c10-473d-9aab-e2cb96446711
ms.openlocfilehash: 2cbd178d5004d28120ab701a777a474a7e78e09e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734441"
---
# <a name="how-to-measure-plinq-query-performance"></a>방법: PLINQ 쿼리 성능 측정

다음 예제에서는 <xref:System.Diagnostics.Stopwatch> 클래스를 사용하여 PLINQ 쿼리를 실행하는 데 걸리는 시간을 측정하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  

 이 예제에서는 빈 `foreach` 루프(Visual Basic에서 `For Each`)를 사용하여 쿼리를 실행하는 데 걸리는 시간을 측정합니다. 실제 코드에서 루프는 일반적으로 전체 쿼리 실행 시간에 추가되는 추가 처리 단계를 포함합니다. 루프 바로 전까지 스톱워치를 시작하지 않습니다. 루프 바로 전은 쿼리 실행을 시작하는 시점이기 때문입니다. 보다 세밀한 측정이 필요한 경우 `ElapsedMilliseconds` 대신 `ElapsedTicks` 속성을 사용할 수 있습니다.  
  
 [!code-csharp[PLINQ#19](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/measure2.cs#19)]
 [!code-vb[PLINQ#19](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/measure2.vb#19)]  
  
 쿼리 구현을 실험하는 경우 총 실행 시간은 유용한 메트릭이지만 항상 전체적인 내용을 알려주지는 않습니다. 쿼리 스레드 간의 상호 작용 또는 다른 실행 중인 프로세스와 쿼리 스레드의 상호 작용을 자세히 보려면 [동시성 시각화 도우미](/visualstudio/profiling/concurrency-visualizer)를 사용합니다.  
  
## <a name="see-also"></a>참조

- [PLINQ(병렬 LINQ)](introduction-to-plinq.md)
