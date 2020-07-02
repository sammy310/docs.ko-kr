---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614758"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="3a24a-101">SslStream이 TLS 경고를 지원</span><span class="sxs-lookup"><span data-stu-id="3a24a-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="3a24a-102">설명</span><span class="sxs-lookup"><span data-stu-id="3a24a-102">Details</span></span>

<span data-ttu-id="3a24a-103">TLS 핸드셰이크가 실패하면 첫 번째 I/O 읽기/쓰기 작업에 의해 내부 <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> 예외가 있는 <xref:System.IO.IOException?displayProperty=fullName>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="3a24a-104"><xref:System.ComponentModel.Win32Exception?displayProperty=fullName>의 <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> 코드는 [TLS 및 SSL 경고에 대한 Schannel 오류 코드](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts)를 사용하여 원격 주체에서 TLS 경고로 매핑될 수 있습니다. 자세한 내용은 [RFC 2246: 섹션 7.2.2 오류 경고](https://tools.ietf.org/html/rfc2246#section-7.2.2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a24a-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="3a24a-105">.NET Framework 4.6.2 및 이전 버전에서 동작은 상대방이 핸드셰이크를 실패한 후 즉시 연결을 거부한 경우 전송 채널(일반적으로 TCP 연결)이 읽기 또는 쓰기 동안 시간을 초과하게 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3a24a-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="3a24a-106">Suggestion</span></span>

<span data-ttu-id="3a24a-107"><xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> 같은 네트워크 I/O API를 호출하는 애플리케이션은 <xref:System.IO.IOException> 또는 <xref:System.TimeoutException?displayProperty=fullName>를 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="3a24a-108">TLS 경고 기능은 기본적으로 .NET Framework 4.7부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="3a24a-109">.NET Framework 4.7 이상 시스템에서 실행되는 .NET Framework 4.0에서 4.6.2까지 버전을 대상으로 하는 애플리케이션은 호환성을 유지하기 위해 사용하지 못하도록 설정하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="3a24a-110">.NET Framework 4.7 이상에서 실행되는 .NET Framework 4.6 및 이상 애플리케이션에 대한 기능을 사용하거나 사용하지 못하도록 설정하려면 다음 구성 API를 사용할수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="3a24a-111">프로그래밍 방식으로:   ServicePointManager가 한 번만 초기화되기 때문에 애플리케이션이 가장 먼저 수행하는 작업이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="3a24a-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="3a24a-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="3a24a-113">레지스트리 키(전역 컴퓨터):   값을 `false`로 설정하여 .NET Framework 4.6 - 4.6.2의 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3a24a-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="3a24a-114">이름</span><span class="sxs-lookup"><span data-stu-id="3a24a-114">Name</span></span>    | <span data-ttu-id="3a24a-115">값</span><span class="sxs-lookup"><span data-stu-id="3a24a-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3a24a-116">Scope</span><span class="sxs-lookup"><span data-stu-id="3a24a-116">Scope</span></span>   | <span data-ttu-id="3a24a-117">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="3a24a-117">Edge</span></span>        |
| <span data-ttu-id="3a24a-118">버전</span><span class="sxs-lookup"><span data-stu-id="3a24a-118">Version</span></span> | <span data-ttu-id="3a24a-119">4.7</span><span class="sxs-lookup"><span data-stu-id="3a24a-119">4.7</span></span>         |
| <span data-ttu-id="3a24a-120">형식</span><span class="sxs-lookup"><span data-stu-id="3a24a-120">Type</span></span>    | <span data-ttu-id="3a24a-121">대상 변경</span><span class="sxs-lookup"><span data-stu-id="3a24a-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="3a24a-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3a24a-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
