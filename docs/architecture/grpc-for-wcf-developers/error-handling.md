---
title: 오류 처리 - WCF 개발자를 위한 gRPC
description: gRPC의 오류 처리와 관련된 항목입니다. 가장 일반적으로 사용되는 상태 코드의 테이블을 포함합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 64a2355a8bd608c074f9bc420312b23aba0c1fb2
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988949"
---
# <a name="error-handling"></a><span data-ttu-id="aed9a-104">오류 처리</span><span class="sxs-lookup"><span data-stu-id="aed9a-104">Error handling</span></span>

<span data-ttu-id="aed9a-105">WCF(Windows 통신 재단)는 SOAP 오류 표준을 지원하는 등 자세한 오류 정보를 제공하기 위해 장애 <xref:System.ServiceModel.FaultException%601> [계약을](xref:System.ServiceModel.FaultContractAttribute) 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-105">Windows Communication Foundation (WCF) uses <xref:System.ServiceModel.FaultException%601> and [FaultContract](xref:System.ServiceModel.FaultContractAttribute) to provide detailed error information, including supporting the SOAP Fault standard.</span></span>

<span data-ttu-id="aed9a-106">안타깝게도 현재 버전의 gRPC에는 WCF에서 찾을 수 있는 정교함이 부족하며 간단한 상태 코드 및 메타데이터에 기반한 기본 제공 오류 처리만 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-106">Unfortunately, the current version of gRPC lacks the sophistication found with WCF, and only has limited built-in error handling based on simple status codes and metadata.</span></span> <span data-ttu-id="aed9a-107">다음 표는 가장 일반적으로 사용되는 상태 코드에 대한 빠른 안내서입니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-107">The following table is a quick guide to the most commonly used status codes:</span></span>

| <span data-ttu-id="aed9a-108">상태 코드</span><span class="sxs-lookup"><span data-stu-id="aed9a-108">Status code</span></span> | <span data-ttu-id="aed9a-109">문제</span><span class="sxs-lookup"><span data-stu-id="aed9a-109">Problem</span></span> |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | <span data-ttu-id="aed9a-110">메서드가 작성되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-110">Method hasn't been written.</span></span> |
| `GRPC_STATUS_UNAVAILABLE` | <span data-ttu-id="aed9a-111">전체 서비스에 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-111">Problem with the whole service.</span></span> |
| `GRPC_STATUS_UNKNOWN` | <span data-ttu-id="aed9a-112">잘못된 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-112">Invalid response.</span></span> |
| `GRPC_STATUS_INTERNAL` | <span data-ttu-id="aed9a-113">인코딩/디코딩 문제.</span><span class="sxs-lookup"><span data-stu-id="aed9a-113">Problem with encoding/decoding.</span></span> |
| `GRPC_STATUS_UNAUTHENTICATED` | <span data-ttu-id="aed9a-114">인증에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-114">Authentication failed.</span></span> |
| `GRPC_STATUS_PERMISSION_DENIED` | <span data-ttu-id="aed9a-115">권한 부여에 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-115">Authorization failed.</span></span> |
| `GRPC_STATUS_CANCELLED` | <span data-ttu-id="aed9a-116">일반적으로 호출에 의해 호출이 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-116">Call was canceled, usually by the caller.</span></span> |

## <a name="raise-errors-in-aspnet-core-grpc"></a><span data-ttu-id="aed9a-117">ASP.NET 코어 gRPC에서 오류 발생</span><span class="sxs-lookup"><span data-stu-id="aed9a-117">Raise errors in ASP.NET Core gRPC</span></span>

<span data-ttu-id="aed9a-118">ASP.NET Core gRPC 서비스는 클라이언트가 동일한 `RpcException`프로세스에 있는 것처럼 잡을 수 있는 오류 응답을 throw하여 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-118">An ASP.NET Core gRPC service can send an error response by throwing an `RpcException`, which can be caught by the client as if it were in the same process.</span></span> <span data-ttu-id="aed9a-119">상태 `RpcException` 코드 및 설명을 포함해야 하며 선택적으로 메타데이터와 더 긴 예외 메시지를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-119">The `RpcException` must include a status code and description, and can optionally include metadata and a longer exception message.</span></span> <span data-ttu-id="aed9a-120">메타데이터는 개체가 WCF 오류에 대한 `FaultContract` 추가 데이터를 전송하는 방법과 유사하게 지원 데이터를 보내는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-120">The metadata can be used to send supporting data, similar to how `FaultContract` objects can carry additional data for WCF errors.</span></span>

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

## <a name="catch-errors-in-grpc-clients"></a><span data-ttu-id="aed9a-121">gRPC 클라이언트에서 오류 catch</span><span class="sxs-lookup"><span data-stu-id="aed9a-121">Catch errors in gRPC clients</span></span>

<span data-ttu-id="aed9a-122">WCF 클라이언트가 오류를 <xref:System.ServiceModel.FaultException%601> 잡을 수 있는 것처럼 gRPC 클라이언트는 오류를 처리하는 방법을 `RpcException` 잡을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-122">Just like WCF clients can catch <xref:System.ServiceModel.FaultException%601> errors, a gRPC client can catch an `RpcException` to handle errors.</span></span> <span data-ttu-id="aed9a-123">제네릭 형식이 아니므로 `RpcException` 다른 블록에서 다른 오류 유형을 잡을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-123">Because `RpcException` isn't a generic type, you can't catch different error types in different blocks.</span></span> <span data-ttu-id="aed9a-124">그러나 다음 예제와 같이 C#의 *예외* `catch` 필터 기능을 사용하여 다른 상태 코드에 대해 별도의 블록을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-124">But you can use C#'s *exception filters* feature to declare separate `catch` blocks for different status codes, as shown in the following example:</span></span>

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
> <span data-ttu-id="aed9a-125">오류에 대한 추가 메타데이터를 제공할 때는 API 설명서 또는 파일의 주석에 `.proto` 관련 키와 값을 문서화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-125">When you provide additional metadata for errors, be sure to document the relevant keys and values in your API documentation, or in comments in your `.proto` file.</span></span>

## <a name="grpc-richer-error-model"></a><span data-ttu-id="aed9a-126">gRPC 풍부한 오류 모델</span><span class="sxs-lookup"><span data-stu-id="aed9a-126">gRPC richer error model</span></span>

<span data-ttu-id="aed9a-127">Google은 WCF의 [FaultContract와](xref:System.ServiceModel.FaultContractAttribute)같은 [풍부한 오류 모델을](https://cloud.google.com/apis/design/errors#error_model) 개발했지만 이 모델은 아직 C# 에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-127">Google has developed a [richer error model](https://cloud.google.com/apis/design/errors#error_model) that's more like WCF's [FaultContract](xref:System.ServiceModel.FaultContractAttribute), but this model isn't supported in C# yet.</span></span> <span data-ttu-id="aed9a-128">현재 는 이동, 자바, 파이썬 및 C ++에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed9a-128">Currently, it's only available for Go, Java, Python, and C++.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="aed9a-129">[이전](metadata.md)
>[다음](ws-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="aed9a-129">[Previous](metadata.md)
[Next](ws-protocols.md)</span></span>
