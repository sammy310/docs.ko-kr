---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614758"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream이 TLS 경고를 지원

#### <a name="details"></a>설명

TLS 핸드셰이크가 실패하면 첫 번째 I/O 읽기/쓰기 작업에 의해 내부 <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> 예외가 있는 <xref:System.IO.IOException?displayProperty=fullName>이 throw됩니다. <xref:System.ComponentModel.Win32Exception?displayProperty=fullName>의 <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> 코드는 [TLS 및 SSL 경고에 대한 Schannel 오류 코드](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts)를 사용하여 원격 주체에서 TLS 경고로 매핑될 수 있습니다. 자세한 내용은 [RFC 2246: 섹션 7.2.2 오류 경고](https://tools.ietf.org/html/rfc2246#section-7.2.2)를 참조하세요. <br/>.NET Framework 4.6.2 및 이전 버전에서 동작은 상대방이 핸드셰이크를 실패한 후 즉시 연결을 거부한 경우 전송 채널(일반적으로 TCP 연결)이 읽기 또는 쓰기 동안 시간을 초과하게 되는 것입니다.

#### <a name="suggestion"></a>제안 해결 방법

<xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> 같은 네트워크 I/O API를 호출하는 애플리케이션은 <xref:System.IO.IOException> 또는 <xref:System.TimeoutException?displayProperty=fullName>를 처리해야 합니다.<br/>TLS 경고 기능은 기본적으로 .NET Framework 4.7부터 사용할 수 있습니다. .NET Framework 4.7 이상 시스템에서 실행되는 .NET Framework 4.0에서 4.6.2까지 버전을 대상으로 하는 애플리케이션은 호환성을 유지하기 위해 사용하지 못하도록 설정하는 기능이 있습니다. <br/>.NET Framework 4.7 이상에서 실행되는 .NET Framework 4.6 및 이상 애플리케이션에 대한 기능을 사용하거나 사용하지 못하도록 설정하려면 다음 구성 API를 사용할수 있습니다.

- 프로그래밍 방식으로:   ServicePointManager가 한 번만 초기화되기 때문에 애플리케이션이 가장 먼저 수행하는 작업이어야 합니다.

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- AppConfig:

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- 레지스트리 키(전역 컴퓨터):   값을 `false`로 설정하여 .NET Framework 4.6 - 4.6.2의 기능을 사용합니다.

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| 이름    | 값       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| 버전 | 4.7         |
| 형식    | 대상 변경 |

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
