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
# <a name="error-handling"></a>오류 처리

WCF(Windows 통신 재단)는 SOAP 오류 표준을 지원하는 등 자세한 오류 정보를 제공하기 위해 장애 <xref:System.ServiceModel.FaultException%601> [계약을](xref:System.ServiceModel.FaultContractAttribute) 사용합니다.

안타깝게도 현재 버전의 gRPC에는 WCF에서 찾을 수 있는 정교함이 부족하며 간단한 상태 코드 및 메타데이터에 기반한 기본 제공 오류 처리만 제한됩니다. 다음 표는 가장 일반적으로 사용되는 상태 코드에 대한 빠른 안내서입니다.

| 상태 코드 | 문제 |
| ----------- | ------- |
| `GRPC_STATUS_UNIMPLEMENTED` | 메서드가 작성되지 않았습니다. |
| `GRPC_STATUS_UNAVAILABLE` | 전체 서비스에 문제가 있습니다. |
| `GRPC_STATUS_UNKNOWN` | 잘못된 응답입니다. |
| `GRPC_STATUS_INTERNAL` | 인코딩/디코딩 문제. |
| `GRPC_STATUS_UNAUTHENTICATED` | 인증에 실패했습니다. |
| `GRPC_STATUS_PERMISSION_DENIED` | 권한 부여에 실패했습니다. |
| `GRPC_STATUS_CANCELLED` | 일반적으로 호출에 의해 호출이 취소되었습니다. |

## <a name="raise-errors-in-aspnet-core-grpc"></a>ASP.NET 코어 gRPC에서 오류 발생

ASP.NET Core gRPC 서비스는 클라이언트가 동일한 `RpcException`프로세스에 있는 것처럼 잡을 수 있는 오류 응답을 throw하여 보낼 수 있습니다. 상태 `RpcException` 코드 및 설명을 포함해야 하며 선택적으로 메타데이터와 더 긴 예외 메시지를 포함할 수 있습니다. 메타데이터는 개체가 WCF 오류에 대한 `FaultContract` 추가 데이터를 전송하는 방법과 유사하게 지원 데이터를 보내는 데 사용할 수 있습니다.

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

## <a name="catch-errors-in-grpc-clients"></a>gRPC 클라이언트에서 오류 catch

WCF 클라이언트가 오류를 <xref:System.ServiceModel.FaultException%601> 잡을 수 있는 것처럼 gRPC 클라이언트는 오류를 처리하는 방법을 `RpcException` 잡을 수 있습니다. 제네릭 형식이 아니므로 `RpcException` 다른 블록에서 다른 오류 유형을 잡을 수 없습니다. 그러나 다음 예제와 같이 C#의 *예외* `catch` 필터 기능을 사용하여 다른 상태 코드에 대해 별도의 블록을 선언할 수 있습니다.

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
> 오류에 대한 추가 메타데이터를 제공할 때는 API 설명서 또는 파일의 주석에 `.proto` 관련 키와 값을 문서화해야 합니다.

## <a name="grpc-richer-error-model"></a>gRPC 풍부한 오류 모델

Google은 WCF의 [FaultContract와](xref:System.ServiceModel.FaultContractAttribute)같은 [풍부한 오류 모델을](https://cloud.google.com/apis/design/errors#error_model) 개발했지만 이 모델은 아직 C# 에서 지원되지 않습니다. 현재 는 이동, 자바, 파이썬 및 C ++에서만 사용할 수 있습니다.

>[!div class="step-by-step"]
>[이전](metadata.md)
>[다음](ws-protocols.md)
