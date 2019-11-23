---
title: 오류 처리-WCF 개발자를 위한 gRPC
description: 작성할 항목
ms.date: 09/02/2019
ms.openlocfilehash: 2c44bd9264c877a7c7a86c115b6da9f759006016
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967788"
---
# <a name="error-handling"></a>오류 처리

WCF는 `FaultException<T>` 및 `FaultContract`를 사용 하 여 SOAP 오류 표준을 지 원하는 것을 포함 하 여 자세한 오류 정보를 제공 합니다.

아쉽게도 현재 버전의 gRPC에는 WCF가 포함 된 복잡성이 없고 간단한 상태 코드 및 메타 데이터를 기반으로 하는 제한 된 기본 제공 오류 처리만 있습니다. 다음 표에서는 가장 일반적으로 사용 되는 상태 코드에 대 한 간략 한 가이드입니다.

| 상태 코드 | 문제점 |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | 메서드가 기록 되지 않았습니다. |
| `GRPC_STATUS_UNAVAILABLE` | 전체 서비스에 문제가 있습니다. |
| `GRPC_STATUS_UNKNOWN` | 응답이 잘못 되었습니다. |
| `GRPC_STATUS_INTERNAL` | 인코딩/디코딩에 문제가 있습니다. |
| `GRPC_STATUS_UNAUTHENTICATED` | 인증에 실패했습니다. |
| `GRPC_STATUS_PERMISSION_DENIED` | 권한 부여에 실패 했습니다. |
| `GRPC_STATUS_CANCELLED` | 호출자가 일반적으로 호출을 취소 했습니다. |

## <a name="raising-errors-in-aspnet-core-grpc"></a>ASP.NET Core gRPC에서 오류 발생

ASP.NET Core gRPC 서비스는 `RpcException`를 throw 하 여 오류 응답을 보낼 수 있습니다 .이는 클라이언트에서 동일한 프로세스에 있는 것 처럼 catch 할 수 있습니다. `RpcException`는 상태 코드 및 설명을 포함 해야 하며 필요에 따라 메타 데이터와 긴 예외 메시지를 포함할 수 있습니다. 메타 데이터는 `FaultContract` 개체가 WCF 오류에 대 한 추가 데이터를 전달할 수 있는 방법과 유사 하 게 지원 데이터를 보내는 데 사용할 수 있습니다.

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

## <a name="catching-errors-in-grpc-clients"></a>GRPC 클라이언트에서 오류 catch

WCF 클라이언트가 <xref:System.ServiceModel.FaultException%601> 오류를 catch 할 수 있는 것 처럼 gRPC 클라이언트는 `RpcException`를 catch 하 여 오류를 처리할 수 있습니다. `RpcException` 제네릭 형식이 아니기 때문에 다른 블록에서 다른 오류 형식을 catch 할 수는 없지만, 다음 예제와 C#같이의 *예외 필터* 기능을 사용 하 여 서로 다른 상태 코드에 대 한 별도의 `catch` 블록을 선언할 수 있습니다.

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
> 오류에 대 한 추가 메타 데이터를 제공 하는 경우 API 설명서 또는 `.proto` 파일의 설명에 관련 키 및 값을 문서화 해야 합니다.

## <a name="grpc-richer-error-model"></a>gRPC 풍부한 오류 모델

앞서 살펴본 Google은 WCF의 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute)와 매우 유사한 C# [보다 풍부한 오류 모델](https://cloud.google.com/apis/design/errors#error_model) 을 개발 했지만 아직 지원 되지 않습니다. 현재는 Go, Java, Python 및 C++에만 사용할 수 있지만에 대 한 C# 지원은 다음 해로 제공 될 것으로 예상 됩니다.

>[!div class="step-by-step"]
>[이전](metadata.md)
>[다음](ws-protocols.md)
