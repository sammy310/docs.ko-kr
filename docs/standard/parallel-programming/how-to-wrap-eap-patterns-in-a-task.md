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
ms.openlocfilehash: eab94ac91be0c755a1da74e2f2220e3b76cc4249
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290787"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="40b09-102">방법: EAP 패턴을 작업에 래핑</span><span class="sxs-lookup"><span data-stu-id="40b09-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="40b09-103">다음 예제에서는 <xref:System.Threading.Tasks.TaskCompletionSource%601>를 사용하여 EAP(이벤트 기반 비동기 패턴) 작업의 임의 시퀀스를 하나의 작업으로 노출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40b09-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="40b09-104">이 예제에서는 <xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Net.WebClient> 개체에서 기본 제공 취소 메서드를 호출하는 방법도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="40b09-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40b09-105">예제</span><span class="sxs-lookup"><span data-stu-id="40b09-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="40b09-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40b09-106">See also</span></span>

- [<span data-ttu-id="40b09-107">TPL 및 일반적인 .NET Framework 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="40b09-107">TPL and Traditional .NET Framework Asynchronous Programming</span></span>](tpl-and-traditional-async-programming.md)
