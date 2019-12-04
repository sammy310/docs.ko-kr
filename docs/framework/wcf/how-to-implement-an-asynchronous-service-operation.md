---
title: '방법: 비동기 서비스 작업 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: fd7a1399dd575ad1a4b6c95e0e0510670eb13b51
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802301"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a>방법: 비동기 서비스 작업 구현
WCF (Windows Communication Foundation) 응용 프로그램에서 클라이언트를 호출 하는 방법을 받아쓰기 하지 않고도 서비스 작업을 비동기적으로 또는 동기적으로 구현할 수 있습니다. 예를 들어 비동기 서비스 작업을 동기적으로 호출할 수 있으며 동기 서비스 작업을 비동기적으로 호출할 수 있습니다. 클라이언트 응용 프로그램에서 작업을 비동기적으로 호출 하는 방법을 보여 주는 예제는 [방법: 비동기적으로 서비스 작업 호출](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)을 참조 하세요. 동기 및 비동기 작업에 대 한 자세한 내용은 [서비스 계약 디자인](designing-service-contracts.md) 및 [동기 및 비동기 작업](synchronous-and-asynchronous-operations.md)을 참조 하세요. 이 항목에서는 비동기 서비스 작업의 기본 구조에 대해 설명하지만 코드가 완성되지 않았습니다. 서비스 및 클라이언트 쪽의 전체 예제는 [비동기](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100))를 참조 하세요.  
  
### <a name="implement-a-service-operation-asynchronously"></a>비동기 서비스 작업 구현  
  
1. 서비스 계약에서 .NET 비동기 디자인 지침에 따라 비동기 메서드 쌍을 선언합니다. `Begin` 메서드는 매개 변수, 콜백 개체 및 상태 개체를 가져와서 <xref:System.IAsyncResult?displayProperty=nameWithType> 및 `End`를 가져오는 일치하는 <xref:System.IAsyncResult?displayProperty=nameWithType> 메서드를 반환한 다음 반환 값을 반환합니다. 비동기 호출에 대 한 자세한 내용은 [비동기 프로그래밍 디자인 패턴](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)을 참조 하세요.  
  
2. `Begin` 특성을 가진 비동기 메서드 쌍의 <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> 메서드를 표시하고 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다. 예를 들어 다음 코드에서는 단계 1 및 2를 수행합니다.  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. 비동기 디자인 지침에 따라 서비스 클래스에서 `Begin/End` 메서드 쌍을 구현합니다. 예를 들어 다음 코드 예제에서는 비동기 서비스 작업의 `Begin` 및 `End` 부분 모두의 콘솔에 기록된 문자열의 구현 및 `End` 작업의 반환 값이 클라이언트에 반환되는 것을 보여 줍니다. 전체 코드 예제를 보려면 예제 단원을 참조하십시오.  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 다음을 보여 줍니다.  
  
1. 다음을 포함한 서비스 계약 인터페이스:  
  
    1. 동기 `SampleMethod` 작업.  
  
    2. 비동기 `BeginSampleMethod` 작업.  
  
    3. 작업 쌍 `EndServiceAsyncMethod` 비동기 `BeginServiceAsyncMethod`/입니다.  
  
2. <xref:System.IAsyncResult?displayProperty=nameWithType> 개체를 사용하여 서비스 구현.  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a>참조

- [서비스 계약 디자인](designing-service-contracts.md)
- [동기 및 비동기 작업](synchronous-and-asynchronous-operations.md)
