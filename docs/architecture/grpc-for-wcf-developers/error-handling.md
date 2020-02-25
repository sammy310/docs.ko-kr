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
# <a name="error-handling"></a>오류 처리

WCF (Windows Communication Foundation)는 <xref:System.ServiceModel.FaultException%601> 및 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute) 를 사용 하 여 SOAP 오류 표준을 지 원하는 것을 비롯 한 자세한 오류 정보를 제공 합니다.

아쉽게도 현재 버전의 gRPC에는 WCF가 포함 된 복잡성이 없으며 간단한 상태 코드 및 메타 데이터를 기반으로 하는 제한 된 기본 제공 오류 처리만 있습니다. 다음 표에서는 가장 일반적으로 사용 되는 상태 코드에 대 한 간략 한 가이드입니다.

| 상태 코드 | 문제 |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | 메서드가 기록 되지 않았습니다. |
| `GRPC_STATUS_UNAVAILABLE` | 전체 서비스에 문제가 있습니다. |
| `GRPC_STATUS_UNKNOWN` | 응답이 잘못 되었습니다. |
| `GRPC_STATUS_INTERNAL` | 인코딩/디코딩에 문제가 있습니다. |
| `GRPC_STATUS_UNAUTHENTICATED` | 인증에 실패했습니다. |
| `GRPC_STATUS_PERMISSION_DENIED` | 권한 부여에 실패했습니다. |
| `GRPC_STATUS_CANCELLED` | 호출자가 일반적으로 호출을 취소 했습니다. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>ASP.NET Core gRPC에서 오류 발생

ASP.NET Core gRPC 서비스는 `RpcException`를 throw 하 여 오류 응답을 보낼 수 있습니다 .이는 클라이언트에서 동일한 프로세스에 있는 것 처럼 catch 할 수 있습니다. `RpcException`는 상태 코드 및 설명을 포함 해야 하며 필요에 따라 메타 데이터와 긴 예외 메시지를 포함할 수 있습니다. 메타 데이터를 사용 하 여 `FaultContract` 개체가 WCF 오류에 대 한 추가 데이터를 전달할 수 있는 방법과 유사 하 게 지원 데이터를 보낼 수 있습니다.

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

## <a name="catch-errors-in-grpc-clients"></a>GRPC 클라이언트에서 오류를 Catch 합니다.

WCF 클라이언트가 <xref:System.ServiceModel.FaultException%601> 오류를 catch 할 수 있는 것 처럼 gRPC 클라이언트는 `RpcException`를 catch 하 여 오류를 처리할 수 있습니다. `RpcException` 제네릭 형식이 아니기 때문에 다른 블록에서 다른 오류 형식을 catch 할 수 없습니다. 그러나 다음 예제와 C#같이의 *예외 필터* 기능을 사용 하 여 서로 다른 상태 코드에 대 한 별도의 `catch` 블록을 선언할 수 있습니다.

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

Google은 WCF의 [Faultcontract](xref:System.ServiceModel.FaultContractAttribute)와 유사한 C# [풍부한 오류 모델](https://cloud.google.com/apis/design/errors#error_model) 을 개발 했지만,이 모델은 아직 지원 되지 않습니다. 현재는 Go, Java, Python 및 C++에만 사용할 수 있습니다.

>[!div class="step-by-step"]
>[이전](metadata.md)
>[다음](ws-protocols.md)
