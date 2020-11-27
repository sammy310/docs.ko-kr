---
title: '방법: 비동기 서비스 작업 구현'
description: WFC에서 비동기 서비스 작업의 구조에 대해 알아봅니다. 서비스 작업은 비동기식으로 또는 동기식으로 구현할 수 있습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: 157311f29b203e0c26be21a89d2d5b560543094b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267834"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="3316c-104">방법: 비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="3316c-104">How to: Implement an Asynchronous Service Operation</span></span>

<span data-ttu-id="3316c-105">WCF (Windows Communication Foundation) 응용 프로그램에서 클라이언트를 호출 하는 방법을 받아쓰기 하지 않고도 서비스 작업을 비동기적으로 또는 동기적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-105">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="3316c-106">예를 들어 비동기 서비스 작업을 동기적으로 호출할 수 있으며 동기 서비스 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-106">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="3316c-107">클라이언트 응용 프로그램에서 작업을 비동기적으로 호출 하는 방법을 보여 주는 예제는 [방법: 비동기적으로 서비스 작업 호출](./feature-details/how-to-call-wcf-service-operations-asynchronously.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3316c-107">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="3316c-108">동기 및 비동기 작업에 대 한 자세한 내용은 [서비스 계약 디자인](designing-service-contracts.md) 및 [동기 및 비동기 작업](synchronous-and-asynchronous-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3316c-108">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](designing-service-contracts.md) and [Synchronous and Asynchronous Operations](synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="3316c-109">이 항목에서는 비동기 서비스 작업의 기본 구조에 대해 설명하지만 코드가 완성되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-109">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="3316c-110">서비스 및 클라이언트 쪽의 전체 예제는 [비동기](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3316c-110">For a complete example of both the service and client sides, see [Asynchronous](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="3316c-111">비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="3316c-111">Implement a service operation asynchronously</span></span>  
  
1. <span data-ttu-id="3316c-112">서비스 계약에서 .NET 비동기 디자인 지침에 따라 비동기 메서드 쌍을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-112">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="3316c-113">`Begin` 메서드는 매개 변수, 콜백 개체 및 상태 개체를 가져와서 <xref:System.IAsyncResult?displayProperty=nameWithType> 및 `End`를 가져오는 일치하는 <xref:System.IAsyncResult?displayProperty=nameWithType> 메서드를 반환한 다음 반환 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-113">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="3316c-114">비동기 호출에 대 한 자세한 내용은 [비동기 프로그래밍 디자인 패턴](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3316c-114">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
2. <span data-ttu-id="3316c-115">`Begin` 특성을 가진 비동기 메서드 쌍의 <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> 메서드를 표시하고 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-115">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="3316c-116">예를 들어 다음 코드에서는 단계 1 및 2를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-116">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. <span data-ttu-id="3316c-117">비동기 디자인 지침에 따라 서비스 클래스에서 `Begin/End` 메서드 쌍을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-117">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="3316c-118">예를 들어 다음 코드 예제에서는 비동기 서비스 작업의 `Begin` 및 `End` 부분 모두의 콘솔에 기록된 문자열의 구현 및 `End` 작업의 반환 값이 클라이언트에 반환되는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-118">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="3316c-119">전체 코드 예제를 보려면 예제 단원을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3316c-119">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="3316c-120">예제</span><span class="sxs-lookup"><span data-stu-id="3316c-120">Example</span></span>  

 <span data-ttu-id="3316c-121">다음 코드 예제에서는 다음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-121">The following code examples show:</span></span>  
  
1. <span data-ttu-id="3316c-122">다음을 포함한 서비스 계약 인터페이스:</span><span class="sxs-lookup"><span data-stu-id="3316c-122">A service contract interface with:</span></span>  
  
    1. <span data-ttu-id="3316c-123">동기 `SampleMethod` 작업.</span><span class="sxs-lookup"><span data-stu-id="3316c-123">A synchronous `SampleMethod` operation.</span></span>  
  
    2. <span data-ttu-id="3316c-124">비동기 `BeginSampleMethod` 작업.</span><span class="sxs-lookup"><span data-stu-id="3316c-124">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3. <span data-ttu-id="3316c-125">비동기 `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` 작업 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="3316c-125">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2. <span data-ttu-id="3316c-126"><xref:System.IAsyncResult?displayProperty=nameWithType> 개체를 사용하여 서비스 구현.</span><span class="sxs-lookup"><span data-stu-id="3316c-126">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3316c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3316c-127">See also</span></span>

- [<span data-ttu-id="3316c-128">서비스 계약 디자인</span><span class="sxs-lookup"><span data-stu-id="3316c-128">Designing Service Contracts</span></span>](designing-service-contracts.md)
- [<span data-ttu-id="3316c-129">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="3316c-129">Synchronous and Asynchronous Operations</span></span>](synchronous-and-asynchronous-operations.md)
