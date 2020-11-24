---
title: ConcurrentBag을 사용하여 개체 풀 만들기
ms.date: 05/01/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object pool, in .NET Framework
ms.assetid: 0480e7ff-b6f9-480e-a889-2ed4264d8372
ms.openlocfilehash: c593c9b2011814c49563939f1094b62cd252879c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94822908"
---
# <a name="create-an-object-pool-by-using-a-concurrentbag"></a>ConcurrentBag을 사용하여 개체 풀 만들기

이 예제에서는 <xref:System.Collections.Concurrent.ConcurrentBag%601>를 사용하여 개체 풀을 구현하는 방법을 보여 줍니다. 클래스에 여러 인스턴스가 필요하고 클래스를 만들거나 삭제하는 데 비용이 많이 드는 경우 개체 풀을 사용하면 애플리케이션 성능을 향상시킬 수 있습니다. 클라이언트 프로그램에서 새 개체를 요청하면 먼저 개체 풀이 이미 풀에 만들어져 반환된 개체를 제공하려고 시도합니다. 제공될 개체가 없는 경우에만 새 개체가 만들어집니다.

<xref:System.Collections.Concurrent.ConcurrentBag%601>는 특히 한 스레드에서 항목의 추가와 제거를 모두 수행할 때 추가하고 제거하는 속도가 빠르기 때문에 개체를 저장하는 데 사용됩니다. <xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601>와 같이 모음 데이터 구조가 구현하는 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601>를 중심으로 구축되도록 이 예제를 강화할 수 있습니다.

> [!TIP]
> 이 문서에서는 다시 사용할 개체를 저장하기 위해 기본 동시 형식으로 개체 풀의 고유한 구현을 작성하는 방법을 정의합니다. 그러나 <xref:Microsoft.Extensions.ObjectPool.ObjectPool%601?displayProperty=nameWithType> 형식은 이미 <xref:Microsoft.Extensions.ObjectPool?displayProperty=fullName> 네임스페이스에 있습니다. 다양한 추가 기능을 포함하는 자체 구현을 만들기 전에 제공된 형식을 사용하는 것이 좋습니다.

## <a name="example"></a>예제

[!code-csharp[CDS#04](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/objectpool.cs#04)]
[!code-vb[CDS#04](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/objectpool04.vb#04)]

## <a name="see-also"></a>참조

- [스레드로부터 안전한 컬렉션](index.md)
