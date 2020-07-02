---
ms.openlocfilehash: fb9436ec9e525afb497033775e34b6b636ced22d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621350"
---
### <a name="wcf-services-that-use-nettcp-with-ssl-security-and-md5-certificate-authentication"></a><span data-ttu-id="57b10-101">SSL 보안 및 MD5 인증서 인증과 함께 NETTCP를 사용하는 WCF 서비스</span><span class="sxs-lookup"><span data-stu-id="57b10-101">WCF services that use NETTCP with SSL security and MD5 certificate authentication</span></span>

#### <a name="details"></a><span data-ttu-id="57b10-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="57b10-102">Details</span></span>

<span data-ttu-id="57b10-103">.NET Framework 4.6은 WCF SSL 기본 프로토콜 목록에 TLS 1.1 및 TLS 1.2를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL default protocol list.</span></span> <span data-ttu-id="57b10-104">클라이언트와 서버 컴퓨터 모두에 .NET Framework 4.6 이상이 설치되어 있으면 TLS 1.2가 협상에 사용됩니다. TLS 1.2는 MD5 인증서 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-104">When both client and server machines have the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="57b10-105">결과적으로, 고객이 MD5 인증서를 사용하는 경우 WCF 클라이언트는 WCF 서비스에 연결하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-105">As a result, if a customer uses an MD5 certificate, the WCF client will fail to connect to the WCF service.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="57b10-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="57b10-106">Suggestion</span></span>

<span data-ttu-id="57b10-107">다음 중 하나를 수행하여 WCF 클라이언트가 WCF 서버에 연결할 수 있도록 함으로써 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-107">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="57b10-108">MD5 알고리즘을 사용 하지 않도록 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-108">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="57b10-109">이것은 권장되는 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-109">This is the recommended solution.</span></span>
- <span data-ttu-id="57b10-110">소스 코드에서 바인딩이 동적으로 구성되지 않은 경우 TLS 1.1 또는 이전 버전의 프로토콜을 사용하도록 애플리케이션의 구성 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-110">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="57b10-111">이렇게 하면 MD5 해시 알고리즘에서 인증서를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-111">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

> [!WARNING]
> <span data-ttu-id="57b10-112">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-112">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

<span data-ttu-id="57b10-113">다음 구성 파일에 이 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-113">The following configuration file does this:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <netTcpBinding>
        <binding>
          <security mode= "None/Transport/Message/TransportWithMessageCredential" >
            <transport clientCredentialType="None/Windows/Certificate"
                       protectionLevel="None/Sign/EncryptAndSign"
                       sslProtocols="Ssl3/Tls1/Tls11">
            </transport>
          </security>
        </binding>
      </netTcpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

- <span data-ttu-id="57b10-114">소스 코드에서 바인딩이 동적으로 구성된 경우 소스 코드에서 TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) 또는 이전 버전의 프로토콜을 사용하도록 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> 속성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-114">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType> or an earlier version of the protocol in the source code.</span></span>

> [!WARNING]
> <span data-ttu-id="57b10-115">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57b10-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

| <span data-ttu-id="57b10-116">이름</span><span class="sxs-lookup"><span data-stu-id="57b10-116">Name</span></span>    | <span data-ttu-id="57b10-117">값</span><span class="sxs-lookup"><span data-stu-id="57b10-117">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="57b10-118">Scope</span><span class="sxs-lookup"><span data-stu-id="57b10-118">Scope</span></span>   | <span data-ttu-id="57b10-119">부</span><span class="sxs-lookup"><span data-stu-id="57b10-119">Minor</span></span>   |
| <span data-ttu-id="57b10-120">버전</span><span class="sxs-lookup"><span data-stu-id="57b10-120">Version</span></span> | <span data-ttu-id="57b10-121">4.6</span><span class="sxs-lookup"><span data-stu-id="57b10-121">4.6</span></span>     |
| <span data-ttu-id="57b10-122">형식</span><span class="sxs-lookup"><span data-stu-id="57b10-122">Type</span></span>    | <span data-ttu-id="57b10-123">런타임</span><span class="sxs-lookup"><span data-stu-id="57b10-123">Runtime</span></span> |
