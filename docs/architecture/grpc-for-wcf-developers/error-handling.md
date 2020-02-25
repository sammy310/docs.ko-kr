---
title: 오류 처리-WCF 개발자를 위한 gRPC
description: GRPC의 오류 처리와 관련 된 항목입니다. 가장 일반적으로 사용 되는 상태 코드의 테이블이 포함 되어 있습니다.
ms.date: 09/02/2019
ms.openlocfilehash: c380c651f854adc97e8b2ead36d30c3b83662aac
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542795"
---
# <a name="error-handling"></a><span data-ttu-id="032b1-104">오류 처리</span><span class="sxs-lookup"><span data-stu-id="032b1-104">Error handling</span></span>

<span data-ttu-id="032b1-105">WCF (Windows Communication Foundation)는 <xref:System.ServiceModel.FaultException%601> 및 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute) 를 사용 하 여 SOAP 오류 표준을 지 원하는 것을 비롯 한 자세한 오류 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="032b1-106">아쉽게도 현재 버전의 gRPC에는 WCF가 포함 된 복잡성이 없으며 간단한 상태 코드 및 메타 데이터를 기반으로 하는 제한 된 기본 제공 오류 처리만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="032b1-107">다음 표에서는 가장 일반적으로 사용 되는 상태 코드에 대 한 간략 한 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="032b1-108">상태 코드</span><span class="sxs-lookup"><span data-stu-id="032b1-108">Status code</span></span> | <span data-ttu-id="032b1-109">문제</span><span class="sxs-lookup"><span data-stu-id="032b1-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="032b1-110">메서드가 기록 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-110">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="032b1-111">전체 서비스에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="032b1-112">응답이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="032b1-113">인코딩/디코딩에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="032b1-114">인증에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="032b1-115">권한 부여에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="032b1-116">호출자가 일반적으로 호출을 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="032b1-117">ASP.NET Core gRPC에서 오류 발생</span><span class="sxs-lookup"><span data-stu-id="032b1-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="032b1-118">ASP.NET Core gRPC 서비스는 `RpcException`를 throw 하 여 오류 응답을 보낼 수 있습니다 .이는 클라이언트에서 동일한 프로세스에 있는 것 처럼 catch 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="032b1-119">`RpcException`는 상태 코드 및 설명을 포함 해야 하며 필요에 따라 메타 데이터와 긴 예외 메시지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="032b1-120">메타 데이터를 사용 하 여 `FaultContract` 개체가 WCF 오류에 대 한 추가 데이터를 전달할 수 있는 방법과 유사 하 게 지원 데이터를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

```csharp
public async Task<GetPortfolioResponse> GetPortfolio(GetPortfolioRequest request, ServerCallContext context)
{
    var user = context.GetHttpContext().User;
    if (!ValidateUser(user))
    {
        var metadata = new Metadata
        {
            { "User", user.Identity.Name }
        };
        throw new RpcException(new Status(StatusCode.PermissionDenied, "Permission denied"), metadata);
    }
}
```

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="032b1-121">GRPC 클라이언트에서 오류를 Catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="032b1-122">WCF 클라이언트가 <xref:System.ServiceModel.FaultException%601> 오류를 catch 할 수 있는 것 처럼 gRPC 클라이언트는 `RpcException`를 catch 하 여 오류를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="032b1-123">`RpcException` 제네릭 형식이 아니기 때문에 다른 블록에서 다른 오류 형식을 catch 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="032b1-124">그러나 다음 예제와 C#같이의 *예외 필터* 기능을 사용 하 여 서로 다른 상태 코드에 대 한 별도의 `catch` 블록을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

```csharp
try
{
    var portfolio = await client.GetPortfolioAsync(new GetPortfolioRequest { Id = id });
}
catch (RpcException ex) when (ex.StatusCode == StatusCode.PermissionDenied)
{
    var userEntry = ex.Trailers.FirstOrDefault(e => e.Key == "User");
    Console.WriteLine($"User '{userEntry.Value}' does not have permission to view this portfolio.");
}
catch (RpcException)
{
    // Handle any other error type ...
}
```

> [!IMPORTANT]
> <span data-ttu-id="032b1-125">오류에 대 한 추가 메타 데이터를 제공 하는 경우 API 설명서 또는 `.proto` 파일의 설명에 관련 키 및 값을 문서화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="032b1-126">gRPC 풍부한 오류 모델</span><span class="sxs-lookup"><span data-stu-id="032b1-126">gRPC richer error model</span></span>

<span data-ttu-id="032b1-127">Google은 WCF의 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute)와 유사한 C# [풍부한 오류 모델](https://cloud.google.com/apis/design/errors#error_model) 을 개발 했지만,이 모델은 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="032b1-128">현재는 Go, Java, Python 및 C++에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="032b1-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="032b1-129">[이전](metadata.md)
>[다음](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="032b1-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
