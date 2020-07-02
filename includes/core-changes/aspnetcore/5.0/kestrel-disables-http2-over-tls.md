---
ms.openlocfilehash: 92210f6becb5a5a43893ee0fd51ef51e2ddd7f8d
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325224"
---
### <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a>Kestrel: 호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2 사용 안 함

Windows에서 TLS(전송 계층 보안)를 통한 HTTP/2를 사용하도록 설정하려면 다음 두 가지 요구 사항을 충족해야 합니다.

- ALPN(Application-Layer Protocol Negotiation) 지원 - Windows 8.1 및 Windows Server 2012 R2부터 제공됩니다.
- HTTP/2와 호환되는 암호 세트 - Windows 10 및 Windows Server 2016부터 제공됩니다.

따라서 TLS를 통한 HTTP/2가 구성된 경우 Kestrel의 동작이 다음과 같이 변경되었습니다.

- [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols)가 `Http1AndHttp2`로 설정된 경우 `Http1`로 다운그레이드하고 `Information` 수준에 메시지를 기록합니다. `Http1AndHttp2`는 `ListenOptions.HttpProtocols`에 대한 기본값입니다.
- `ListenOptions.HttpProtocols`가 `Http2`로 설정된 경우 `NotSupportedException`을 throw합니다.

자세한 내용은 이슈 [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

ASP.NET Core 5.0 미리 보기 7

#### <a name="old-behavior"></a>이전 동작

다음 표에서는 TLS를 통한 HTTP/2가 구성된 경우의 동작을 간략하게 설명합니다.

| 프로토콜 | Windows 7,<br />Windows Server 2008 R2<br />이하 | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016<br />이상 |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | `NotSupportedException` throw                   | TLS 핸드셰이크 중 오류 발생     | TLS 핸드셰이크 중 오류 발생 &ast;     | 오류 없음 |
| `Http1AndHttp2` | `Http1`로 다운그레이드                    | `Http1`로 다운그레이드     | TLS 핸드셰이크 중 오류 발생 &ast;     | 오류 없음 |

&ast; 이러한 시나리오를 사용하려면 호환되는 암호 도구 모음을 구성합니다.

#### <a name="new-behavior"></a>새 동작

다음 표에서는 TLS를 통한 HTTP/2가 구성된 경우의 동작을 간략하게 설명합니다.

| 프로토콜 | Windows 7,<br />Windows Server 2008 R2<br />이하 | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016<br />이상 |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | `NotSupportedException` throw                   | `NotSupportedException` throw     | `NotSupportedException` throw &ast;&ast;     | 오류 없음 |
| `Http1AndHttp2` | `Http1`로 다운그레이드                    | `Http1`로 다운그레이드     | `Http1`로 다운그레이드 &ast;&ast;     | 오류 없음 |

&ast;&ast; 이러한 시나리오를 사용하려면 호환되는 암호 도구 모음을 구성하고 앱 컨텍스트 스위치 `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`를 `true`로 설정합니다.

#### <a name="reason-for-change"></a>변경 이유

이 변경은 이전 Windows 버전에서 TLS를 통한 HTTP/2의 호환성 오류가 최대한 빨리 명확히 표시되도록 하기 위한 것입니다.

#### <a name="recommended-action"></a>권장 조치

호환되지 않는 Windows 버전에서 TLS를 통한 HTTP/2가 사용하지 않도록 설정되어 있는지 확인합니다. Windows 8.1 및 Windows Server 2012 R2는 기본적으로 필요한 암호가 없으므로 호환되지 않습니다. 그러나 HTTP/2 호환 암호를 사용하도록 컴퓨터 구성 설정을 업데이트할 수 있습니다. 자세한 내용은 [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1)(Windows 8.1의 TLS 암호 도구 모음)을 참조하세요. 구성한 경우 앱 컨텍스트 스위치 `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`를 설정하여 Kestrel에서 TLS를 통한 HTTP/2를 사용하도록 설정해야 합니다. 예를 들어:

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

기본 지원은 변경되지 않았습니다. 예를 들어 TLS를 통한 HTTP/2는 이전에도 Windows 8 또는 Windows Server 2012에서 작동하지 않았습니다. 이 변경으로 이러한 지원되지 않는 시나리오에서 오류가 표시되는 방법이 수정됩니다.

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

없음

<!--

#### Affected APIs

Not detectable via API analysis

-->
