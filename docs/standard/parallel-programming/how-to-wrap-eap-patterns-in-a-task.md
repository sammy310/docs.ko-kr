---
title: '방법: EAP 패턴을 작업에 래핑'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: ac7436892c644340286bb4670bf75c9cd63a8ce5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106816"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="03e04-102">방법: EAP 패턴을 작업에 래핑</span><span class="sxs-lookup"><span data-stu-id="03e04-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="03e04-103">다음 예제에서는 <xref:System.Threading.Tasks.TaskCompletionSource%601>를 사용하여 EAP(이벤트 기반 비동기 패턴) 작업의 임의 시퀀스를 하나의 작업으로 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e04-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="03e04-104">이 예제에서는 <xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Net.WebClient> 개체에서 기본 제공 취소 메서드를 호출하는 방법도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="03e04-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03e04-105">예제</span><span class="sxs-lookup"><span data-stu-id="03e04-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="03e04-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="03e04-106">See also</span></span>

- [<span data-ttu-id="03e04-107">TPL 및 일반적인 .NET Framework 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="03e04-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md)
