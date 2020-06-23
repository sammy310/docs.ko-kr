---
title: '방법: 비동기적으로 WCF 서비스 작업 호출'
description: 이벤트 기반 비동기 호출 모델을 사용 하 여 비동기적으로 서비스 작업에 액세스할 수 있는 WCF 클라이언트를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: aa31f64473111800f4cd01907a0446c94f368456
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247236"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="bda8f-103">방법: 비동기적으로 WCF 서비스 작업 호출</span><span class="sxs-lookup"><span data-stu-id="bda8f-103">How to: Call WCF Service Operations Asynchronously</span></span>

<span data-ttu-id="bda8f-104">이 문서에서는 클라이언트에서 서비스 작업에 비동기적으로 액세스할 수 있는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-104">This article covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="bda8f-105">이 문서의 서비스는 인터페이스를 구현 합니다 `ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="bda8f-105">The service in this article implements the `ICalculator` interface.</span></span> <span data-ttu-id="bda8f-106">클라이언트는 이벤트 구동 비동기 호출 모델을 사용하여 이 인터페이스에서 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-106">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="bda8f-107">이벤트 기반 비동기 호출 모델에 대 한 자세한 내용은 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda8f-107">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)).</span></span> <span data-ttu-id="bda8f-108">서비스에서 비동기적으로 작업을 구현 하는 방법을 보여 주는 예제는 [방법: 비동기 서비스 작업 구현](../how-to-implement-an-asynchronous-service-operation.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda8f-108">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="bda8f-109">동기 및 비동기 작업에 대 한 자세한 내용은 [동기 및 비동기 작업](../synchronous-and-asynchronous-operations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda8f-109">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bda8f-110"><xref:System.ServiceModel.ChannelFactory%601>를 사용하는 경우 이벤트 구동 비동기 호출 모델이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-110">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="bda8f-111">를 사용 하 여 비동기 호출을 수행 하는 방법에 대 한 자세한 내용은 <xref:System.ServiceModel.ChannelFactory%601> [방법: 채널 팩터리를 사용 하 여 비동기 작업 호출](how-to-call-operations-asynchronously-using-a-channel-factory.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda8f-111">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="bda8f-112">절차</span><span class="sxs-lookup"><span data-stu-id="bda8f-112">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="bda8f-113">WCF 서비스 작업을 비동기적으로 호출하려면</span><span class="sxs-lookup"><span data-stu-id="bda8f-113">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="bda8f-114">다음 명령에 나와 있는 것 처럼 및 명령 옵션을 함께 사용 하 여 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 도구를 실행 합니다 `/async` `/tcv:Version35` .</span><span class="sxs-lookup"><span data-stu-id="bda8f-114">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```console
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="bda8f-115">이렇게 하면 동기 및 표준 대리자 기반 비동기 작업 외에도 다음을 포함 하는 WCF 클라이언트 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-115">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    - <span data-ttu-id="bda8f-116">`operationName` > `Async` 이벤트 기반 비동기 호출 방법에 사용할 두 개의 <작업</span><span class="sxs-lookup"><span data-stu-id="bda8f-116">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bda8f-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bda8f-117">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    - <span data-ttu-id="bda8f-118">`operationName` > `Completed` 이벤트 기반 비동기 호출 방법에 사용할 <폼의 작업 완료 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-118">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bda8f-119">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bda8f-119">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    - <span data-ttu-id="bda8f-120"><xref:System.EventArgs?displayProperty=nameWithType>`operationName` > `CompletedEventArgs` 이벤트 기반 비동기 호출 방법에 사용할 각 작업 (폼 <)에 대 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-120"><xref:System.EventArgs?displayProperty=nameWithType> types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bda8f-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bda8f-121">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="bda8f-122">호출 애플리케이션은 다음 샘플 코드에서처럼 비동기 작업이 완료될 때 호출할 콜백 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-122">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="bda8f-123">작업을 호출 하기 전에 <형식의 새 제네릭를 사용 <xref:System.EventHandler%601?displayProperty=nameWithType> 하 여 `operationName` > `EventArgs` 이전 단계에서 만든 처리기 메서드를 <이벤트에 추가 합니다 `operationName` > `Completed` .</span><span class="sxs-lookup"><span data-stu-id="bda8f-123">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="bda8f-124">그런 다음 <메서드를 호출 `operationName` > `Async` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-124">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="bda8f-125">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="bda8f-125">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="bda8f-126">예제</span><span class="sxs-lookup"><span data-stu-id="bda8f-126">Example</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bda8f-127">이벤트 기반 비동기 모델에 대한 디자인 지침에 따르면 둘 이상의 값이 반환될 경우 그 중 하나는 `Result` 속성으로 반환되고 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-127">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="bda8f-128">따라서 클라이언트가 이벤트 기반 비동기 명령 옵션을 사용하여 메타데이터를 가져오고 작업이 둘 이상의 값을 반환할 경우 기본 <xref:System.EventArgs> 개체는 그 중 하나를 `Result` 속성으로 반환하고, 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다. 메시지 개체를 `Result` 속성으로 수신하고 반환된 값을 해당 개체의 속성으로 포함하려면 `/messageContract` 명령 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-128">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="bda8f-129">이렇게 하면 응답 메시지를 `Result` 개체의 <xref:System.EventArgs> 속성으로 반환하는 서명이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-129">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="bda8f-130">모든 내부 반환 값은 응답 메시지 개체의 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda8f-130">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="bda8f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda8f-131">See also</span></span>

- [<span data-ttu-id="bda8f-132">방법: 비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="bda8f-132">How to: Implement an Asynchronous Service Operation</span></span>](../how-to-implement-an-asynchronous-service-operation.md)
