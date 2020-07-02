---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325245"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: 클라이언트 인증서 재협상을 기본적으로 사용 안 함

연결을 재협상하고 클라이언트 인증서를 요청하는 옵션이 기본적으로 사용되지 않습니다. 자세한 내용은 이슈 [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

ASP.NET Core 5.0

#### <a name="old-behavior"></a>이전 동작

연결을 재협상하여 클라이언트 인증서를 요청할 수 있습니다.

#### <a name="new-behavior"></a>새 동작

초기 연결 핸드셰이크 중에만 클라이언트 인증서를 요청할 수 있습니다. 자세한 내용은 끌어오기 요청 [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162)를 참조하세요.

#### <a name="reason-for-change"></a>변경 이유

재협상으로 인해 많은 성능 및 교착 상태 문제가 발생했습니다. 또한 재협상은 HTTP/2에서 지원되지 않습니다. 이 동작을 제어하는 옵션이 ASP.NET Core 3.1에서 도입된 시기의 자세한 상황 정보는 이슈 [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806)을 참조하세요.

#### <a name="recommended-action"></a>권장 조치

클라이언트 인증서가 필요한 앱은 *netsh.exe*를 사용하여 `clientcertnegotiation` 옵션을 `enabled`로 설정해야 합니다. 자세한 내용은 [netsh http 명령](/windows-server/networking/technologies/netsh/netsh-http)을 참조하세요.

앱의 일부에서만 클라이언트 인증서를 사용하도록 설정하려면 [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates)(선택적 클라이언트 인증서)의 참고 자료를 참조하세요.

이전 재협상 동작이 필요한 경우 `HttpSysOptions.ClientCertificateMethod`를 이전 값 `ClientCertificateMethod.AllowRenegotiate`로 설정합니다. 위 내용과 연결된 참고 자료에서 설명하는 이유 때문에 권장하지 않습니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
