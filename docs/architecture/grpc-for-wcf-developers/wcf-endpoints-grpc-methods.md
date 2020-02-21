---
title: Wcf 끝점 및 gRPC 메서드-WCF 개발자를 위한 gRPC
description: ServiceContract 및 OperationContract 특성을 사용 하 여 선언 된 WCF 끝점과 Protobuf에 선언 된 gRPC 메서드 비교
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503425"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="21fba-103">WCF 끝점 및 gRPC 메서드</span><span class="sxs-lookup"><span data-stu-id="21fba-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="21fba-104">WCF (Windows Communication Foundation)에서 응용 프로그램 코드를 작성 하는 경우 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="21fba-105">클래스에 응용 프로그램 코드를 작성 하 고 [OperationContract](xref:System.ServiceModel.OperationContractAttribute) 특성을 사용 하 여 메서드를 장식 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="21fba-106">서비스에 대 한 인터페이스를 선언 하 고 인터페이스에 [OperationContract](xref:System.ServiceModel.OperationContractAttribute) 특성을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="21fba-107">예를 들어 `greet.proto` Greeter 서비스에 해당 하는 WCF는 다음과 같이 작성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="21fba-108">3 장에서는 Protobuf 메시지 정의가 데이터 클래스를 생성 하는 데 사용 됨을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="21fba-109">서비스 및 메서드 선언은 서비스를 구현 하기 위해 상속 하는 기본 클래스를 생성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="21fba-110">`.proto` 파일에서 구현 되는 메서드를 선언 하기만 하면 컴파일러는 재정의 해야 하는 가상 메서드를 사용 하 여 기본 클래스를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="21fba-111">OperationContract 속성</span><span class="sxs-lookup"><span data-stu-id="21fba-111">OperationContract properties</span></span>

<span data-ttu-id="21fba-112">[OperationContract](xref:System.ServiceModel.OperationContractAttribute) 특성에는 작동 방식을 제어 하거나 구체화 하는 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="21fba-113">gRPC 메서드는 이러한 종류의 컨트롤을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="21fba-114">다음 표에서는 이러한 `OperationContract` 속성을 나열 하 고 해당 속성을 지정 하는 기능이 gRPC에서 처리 되는 (또는 아님) 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="21fba-115">`OperationContract` 속성</span><span class="sxs-lookup"><span data-stu-id="21fba-115">`OperationContract` property</span></span> | <span data-ttu-id="21fba-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="21fba-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="21fba-117">URI는 작업을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-117">A URI identifies the operation.</span></span> <span data-ttu-id="21fba-118">gRPC는 `.proto` 파일의 `package`, `service`및 `rpc` 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="21fba-119">모든 gRPC 서비스 메서드는 `Task` 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="21fba-120">이 표 다음에 나오는 단락을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="21fba-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="21fba-121">단방향 gRPC 메서드는 `Empty` 결과를 반환 하거나 클라이언트 스트리밍을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="21fba-122">이 표 다음에 나오는 단락을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="21fba-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="21fba-123">이 속성은 SOAP와 관련 되어 있으며 gRPC에서 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="21fba-124">메시지 암호화가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-124">There's no message encryption.</span></span> <span data-ttu-id="21fba-125">네트워크 암호화는 전송 계층 (HTTP/2 over TLS)에서 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="21fba-126">이 속성은 SOAP와 관련 되어 있으며 gRPC에서 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="21fba-127">`IsInitiating` 속성을 사용 하면 [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) 내의 메서드가 세션의 일부로 호출 되는 첫 번째 메서드가 될 수 없음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="21fba-128">`IsTerminating` 속성을 사용 하면 작업을 호출한 후 서버에서 세션을 닫을 수 있습니다. 또는 속성이 콜백 클라이언트에서 사용 되는 경우 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="21fba-129">GRPC에서 스트림은 단일 메서드에 의해 생성 되 고 명시적으로 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="21fba-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="21fba-130">[Grpc 스트리밍](rpc-types.md#grpc-streaming)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21fba-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="21fba-131">GRPC 보안 및 암호화에 대 한 자세한 내용은 [6 장](security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21fba-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="21fba-132">[이전](wcf-services-to-grpc-comparison.md)
>[다음](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="21fba-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
