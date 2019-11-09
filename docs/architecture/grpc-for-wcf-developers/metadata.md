---
title: WCF 개발자를 위한 메타 데이터 gRPC
description: GRPC에서 메타 데이터를 사용 하 여 클라이언트와 서버 간에 추가 컨텍스트를 전달 하는 방법
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 32559b3404b12f366fc1624299d04cff9faad9d6
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841584"
---
# <a name="metadata"></a><span data-ttu-id="10710-103">메타데이터</span><span class="sxs-lookup"><span data-stu-id="10710-103">Metadata</span></span>

<span data-ttu-id="10710-104">"메타 데이터"는 요청 및 응답을 처리 하는 동안 유용할 수 있지만 실제 응용 프로그램 데이터에 포함 되지 않는 추가 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="10710-104">"Metadata" refers to additional data that may be useful while processing requests and responses but is not part of the actual application data.</span></span> <span data-ttu-id="10710-105">메타 데이터에는 모니터링 목적으로 사용할 수 있는 인증 토큰, 요청 식별자 및 태그 또는 데이터 집합의 레코드 수와 같은 데이터에 대 한 정보가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-105">Metadata might include authentication tokens, request identifiers and tags for monitoring purposes, or information about the data like the number of records in a dataset.</span></span>

<span data-ttu-id="10710-106"><xref:System.ServiceModel.OperationContextScope> 및 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> 속성을 사용 하 여 WCF 메시지에 제네릭 키/값 헤더를 추가 하 고 <xref:System.ServiceModel.Channels.MessageProperties>를 사용 하 여 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-106">It's possible to add generic key/value headers to WCF messages using an <xref:System.ServiceModel.OperationContextScope> and the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders?displayProperty=nameWithType> property, and handle them using <xref:System.ServiceModel.Channels.MessageProperties>.</span></span>

<span data-ttu-id="10710-107">gRPC 호출 및 응답은 HTTP 헤더와 유사한 메타 데이터를 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-107">gRPC calls and responses can also include metadata similar to HTTP headers.</span></span> <span data-ttu-id="10710-108">이러한 기능은 대부분 gRPC 자체에 표시 되지 않으며 응용 프로그램 코드 또는 미들웨어에서 처리 하기 위해 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10710-108">These are mostly invisible to gRPC itself and are passed through to be processed by your application code or middleware.</span></span> <span data-ttu-id="10710-109">메타 데이터는 키가 문자열인 키/값 쌍으로 표시 되 고 값은 문자열 또는 이진 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="10710-109">Metadata is represented as key/value pairs where the key is a string and the value is either a string or binary data.</span></span> <span data-ttu-id="10710-110">`.proto` 파일에서 메타 데이터를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-110">You don’t need to specify metadata in the `.proto` file.</span></span>

<span data-ttu-id="10710-111">메타 데이터는 [Grpc](https://www.nuget.org/packages/Grpc.Core.Api/) 의 `Metadata` 클래스를 사용 하 여 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10710-111">Metadata is handled using the `Metadata` class from the [Grpc.Core.Api](https://www.nuget.org/packages/Grpc.Core.Api/) NuGet package.</span></span> <span data-ttu-id="10710-112">이 클래스는 컬렉션 이니셜라이저 구문과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-112">This class can be used with collection initializer syntax.</span></span>

<span data-ttu-id="10710-113">다음 예제에서는 C# 클라이언트에서 호출에 메타 데이터를 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="10710-113">The following example shows how to add metadata to a call from a C# client:</span></span>

```csharp
var metadata = new Metadata
{
    { "Requester", _clientName }
};

var request = new GetPortfolioRequest
{
    Id = portfolioId
};

var response = await client.GetPortfolioAsync(request, metadata);
```

<span data-ttu-id="10710-114">gRPC 서비스는 `ServerCallContext` 인수의 `RequestHeaders` 속성에서 메타 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-114">gRPC services can access metadata from the `ServerCallContext` argument's `RequestHeaders` property:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var requesterHeader = context.RequestHeaders.FirstOrDefault(e => e.Key == "Requester");
    if (requesterHeader != null)
    {
        _logger.LogInformation($"Request from {requesterHeader.Value}");
    }
    // ...
}
```

<span data-ttu-id="10710-115">서비스는 `ServerCallContext`의 `ResponseTrailers` 속성을 사용 하 여 메타 데이터를 클라이언트로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10710-115">Services can send metadata to clients using the `ResponseTrailers` property of `ServerCallContext`:</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    // ...
    context.ResponseTrailers.Add("Responder", _serverName);
    // ...
}
```

>[!div class="step-by-step"]
><span data-ttu-id="10710-116">[이전](rpc-types.md)
>[다음](error-handling.md)</span><span class="sxs-lookup"><span data-stu-id="10710-116">[Previous](rpc-types.md)
[Next](error-handling.md)</span></span>
