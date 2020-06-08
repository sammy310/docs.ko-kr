---
title: '방법: 병렬 및 순차적 LINQ 쿼리 결합'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel queries, combine parallel and sequential
ms.assetid: 1167cfe6-c8aa-4096-94ba-c66c3a4edf4c
ms.openlocfilehash: 2bdf074bc2977dc501e0726a52e825c89828565f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289540"
---
# <a name="how-to-combine-parallel-and-sequential-linq-queries"></a>방법: 병렬 및 순차적 LINQ 쿼리 결합

이 예제는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 사용하여 쿼리의 모든 후속 연산자를 순차적으로 처리하도록 PLINQ에 지시하는 방법을 보여줍니다. 순차적 처리는 종종 병렬보다 느리지만 올바른 결과를 생성하는 데 필요한 경우도 있습니다.  
  
> [!NOTE]
> 이 예제는 사용법을 보여 주기 위한 것이며, 동일한 순차 LINQ to Objects 쿼리보다 빠르게 실행되지 않을 수도 있습니다. 속도 향상에 대한 자세한 내용은 [PLINQ의 속도 향상 이해](understanding-speedup-in-plinq.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 쿼리의 이전 절에서 설정된 순서를 유지하기 위해 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>이 필요한 하나의 시나리오를 보여줍니다.  
  
 [!code-csharp[PLINQ#24](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#24)]
 [!code-vb[PLINQ#24](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#24)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 코드를 컴파일하고 실행하려면 [PLINQ 데이터 샘플](plinq-data-sample.md) 프로젝트에 붙여넣고, `Main`에서 메서드를 호출하는 줄을 추가하고 **F5** 키를 누르세요.  
  
## <a name="see-also"></a>참조

- [PLINQ(병렬 LINQ)](introduction-to-plinq.md)
