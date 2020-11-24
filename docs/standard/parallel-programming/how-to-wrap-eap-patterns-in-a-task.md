---
title: '방법: EAP 패턴을 작업에 래핑'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: 2d6788634fe03bed7a380184c0e954954e224aec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826686"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>방법: EAP 패턴을 작업에 래핑
다음 예제에서는 <xref:System.Threading.Tasks.TaskCompletionSource%601>를 사용하여 EAP(이벤트 기반 비동기 패턴) 작업의 임의 시퀀스를 하나의 작업으로 노출하는 방법을 보여 줍니다. 이 예제에서는 <xref:System.Threading.CancellationToken>을 사용하여 <xref:System.Net.WebClient> 개체에서 기본 제공 취소 메서드를 호출하는 방법도 보여줍니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>참고 항목

- [TPL 및 일반적인 .NET 비동기 프로그래밍](tpl-and-traditional-async-programming.md)
