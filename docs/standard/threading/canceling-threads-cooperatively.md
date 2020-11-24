---
title: 스레드 함께 취소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- threads, cancellation
ms.assetid: d2d6d5fd-e263-4fa0-847b-2fc3e0d82337
ms.openlocfilehash: 9e9224e9dc9ac57defe75e916dd6b9844bba7f12
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826614"
---
# <a name="canceling-threads-cooperatively"></a>스레드 함께 취소

.NET Framework 4 이전에 .NET은 시작된 후 스레드를 협조적으로 취소하는 기본 제공 방법을 제공하지 않았습니다. 그러나 .NET Framework 4부터는 <xref:System.Threading.CancellationToken?displayProperty=nameWithType>을 사용하여 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 PLINQ 쿼리를 취소하는 것처럼 스레드를 취소할 수 있습니다. <xref:System.Threading.Thread?displayProperty=nameWithType> 클래스는 취소 토큰에 대한 기본 제공 지원을 제공하지 않지만 <xref:System.Threading.Thread> 대리자를 받아들이는 <xref:System.Threading.ParameterizedThreadStart> 생성자를 사용하여 스레드 프로시저에 토큰을 전달할 수 있습니다. 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[Cancellation#14](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/CooperativeThreads.cs#14)]
 [!code-vb[Cancellation#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/CooperativeThreads.vb#14)]  
  
## <a name="see-also"></a>참고 항목

- [스레드 및 스레딩 사용](using-threads-and-threading.md)
