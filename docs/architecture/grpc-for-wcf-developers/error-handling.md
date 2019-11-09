---
title: 오류 처리-WCF 개발자를 위한 gRPC
description: 작성할 항목
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 91f5789d8ed0f01f3ce2f3f9a6c6ccf14f245290
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73842004"
---
# <a name="error-handling"></a><span data-ttu-id="1293b-103">오류 처리</span><span class="sxs-lookup"><span data-stu-id="1293b-103">Error handling</span></span>

<span data-ttu-id="1293b-104">WCF는 `FaultException<T>` 및 `FaultContract`를 사용 하 여 SOAP 오류 표준을 지 원하는 것을 포함 하 여 자세한 오류 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-104">WCF uses `FaultException<T>` and `FaultContract` to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="1293b-105">아쉽게도 현재 버전의 gRPC에는 WCF가 포함 된 복잡성이 없고 간단한 상태 코드 및 메타 데이터를 기반으로 하는 제한 된 기본 제공 오류 처리만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-105">Unfortunately, the current version of gRPC lacks the sophistication found with WCF and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="1293b-106">다음 표에서는 가장 일반적으로 사용 되는 상태 코드에 대 한 간략 한 가이드입니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-106">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="1293b-107">상태 코드</span><span class="sxs-lookup"><span data-stu-id="1293b-107">Status Code</span></span> | <span data-ttu-id="1293b-108">문제점</span><span class="sxs-lookup"><span data-stu-id="1293b-108">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="1293b-109">메서드가 기록 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-109">Method hasn’t been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="1293b-110">전체 서비스에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-110">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="1293b-111">응답이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-111">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="1293b-112">인코딩/디코딩에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-112">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="1293b-113">인증에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-113">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="1293b-114">권한 부여에 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-114">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="1293b-115">호출자가 일반적으로 호출을 취소 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-115">Call was canceled, usually by the caller.</span></span> |

## <a name="raising-errors-in-aspnet-core-grpc"></a><span data-ttu-id="1293b-116">ASP.NET Core gRPC에서 오류 발생</span><span class="sxs-lookup"><span data-stu-id="1293b-116">Raising errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="1293b-117">ASP.NET Core gRPC 서비스는 `RpcException`를 throw 하 여 오류 응답을 보낼 수 있습니다 .이는 클라이언트에서 동일한 프로세스에 있는 것 처럼 catch 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-117">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="1293b-118">`RpcException`는 상태 코드 및 설명을 포함 해야 하며 필요에 따라 메타 데이터와 긴 예외 메시지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-118">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="1293b-119">메타 데이터는 `FaultContract` 개체가 WCF 오류에 대 한 추가 데이터를 전달할 수 있는 방법과 유사 하 게 지원 데이터를 보내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-119">The metadata can be used to send supporting data, similar to how `FaultContract` objects could carry additional data for WCF errors.</span></span>

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

## <a name="catching-errors-in-grpc-clients"></a><span data-ttu-id="1293b-120">GRPC 클라이언트에서 오류 catch</span><span class="sxs-lookup"><span data-stu-id="1293b-120">Catching errors in gRPC clients</span></span>

<span data-ttu-id="1293b-121">WCF 클라이언트가 <xref:System.ServiceModel.FaultException%601> 오류를 catch 할 수 있는 것 처럼 gRPC 클라이언트는 `RpcException`를 catch 하 여 오류를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-121">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="1293b-122">`RpcException` 제네릭 형식이 아니기 때문에 다른 블록에서 다른 오류 형식을 catch 할 수는 없지만, 다음 예제와 C#같이의 *예외 필터* 기능을 사용 하 여 서로 다른 상태 코드에 대 한 별도의 `catch` 블록을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-122">Since `RpcException` isn't a generic type, you can't catch different error types in different blocks, but you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="1293b-123">오류에 대 한 추가 메타 데이터를 제공 하는 경우 API 설명서 또는 `.proto` 파일의 설명에 관련 키 및 값을 문서화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-123">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="1293b-124">gRPC 풍부한 오류 모델</span><span class="sxs-lookup"><span data-stu-id="1293b-124">gRPC Richer Error Model</span></span>

<span data-ttu-id="1293b-125">앞서 살펴본 Google은 WCF의 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute)와 매우 유사한 C# [보다 풍부한 오류 모델](https://cloud.google.com/apis/design/errors#error_model) 을 개발 했지만 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-125">Looking ahead, Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that is more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but isn't supported in C# yet.</span></span> <span data-ttu-id="1293b-126">현재는 Go, Java, Python 및 C++에만 사용할 수 있지만에 대 한 C# 지원은 다음 해로 제공 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1293b-126">Currently, it's only available for Go, Java, Python and C++, but support for C# is expected to come next year.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1293b-127">[이전](metadata.md)
>[다음](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="1293b-127">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
