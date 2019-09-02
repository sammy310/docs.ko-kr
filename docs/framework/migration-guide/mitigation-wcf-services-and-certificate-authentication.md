---
title: '완화: WCF 서비스 및 인증서 인증'
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6ad11d4295be3a5bfd590d9cef1926f6676f2b1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043237"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="f91a6-102">완화: WCF 서비스 및 인증서 인증</span><span class="sxs-lookup"><span data-stu-id="f91a6-102">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="f91a6-103">.NET Framework 4.6은 WCF SSL 프로토콜 기본 목록에 TLS 1.1 및 TLS 1.2를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-103">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="f91a6-104">클라이언트와 서버 컴퓨터에.NET Framework 4.6 및 이후 버전이 설치되어 있으면 TLS 1.2가 협상에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-104">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="f91a6-105">영향</span><span class="sxs-lookup"><span data-stu-id="f91a6-105">Impact</span></span>

<span data-ttu-id="f91a6-106">TLS 1.2는 MD5 인증서 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-106">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="f91a6-107">결과적으로 고객이 해시 알고리즘에 대해 MD5를 사용하는 SSL 인증서를 사용 하는 경우 WCF 클라이언트에서 WCF 서비스에 연결하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-107">As a result, if a customer uses an SSL  certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="f91a6-108">자세한 내용은 [완화: WCF 서비스 및 인증서 인증](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f91a6-108">For more information, see [Mitigation: WCF Services and Certificate Authentication](../../../docs/framework/migration-guide/mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="f91a6-109">완화</span><span class="sxs-lookup"><span data-stu-id="f91a6-109">Mitigation</span></span>

<span data-ttu-id="f91a6-110">다음 중 하나를 수행하여 WCF 클라이언트가 WCF 서버에 연결할 수 있도록 함으로써 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-110">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="f91a6-111">MD5 알고리즘을 사용 하지 않도록 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-111">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="f91a6-112">이것은 권장되는 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-112">This is the recommended solution.</span></span>

- <span data-ttu-id="f91a6-113">소스 코드에서 바인딩이 동적으로 구성되지 않은 경우 TLS 1.1 또는 이전 버전의 프로토콜을 사용하도록 애플리케이션의 구성 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-113">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="f91a6-114">이렇게 하면 MD5 해시 알고리즘에서 인증서를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-114">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="f91a6-115">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-115">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="f91a6-116">다음 구성 파일에 이 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-116">The following configuration file does this:</span></span>

  ```xml
  <configuration>
      <system.serviceModel>
          <bindings>
              <netTcpBinding>
                  <binding>
                      <security mode= "None|Transport|Message|TransportWithMessageCredential" >
                          <transport clientCredentialType="None|Windows|Certificate"
                                              protectionLevel="None|Sign|EncryptAndSign"
                                              sslProtocols="Ssl3|Tls1|Tls11">
                          </transport>
                      </security>
                  </binding>
              </netTcpBinding>
          </bindings>
      </system.ServiceModel>
  </configuration>
  ```

- <span data-ttu-id="f91a6-117">소스 코드에서 바인딩이 동적으로 구성된 경우 소스 코드에서 TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) 또는 이전 버전의 프로토콜을 사용하도록 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> 속성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-117">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="f91a6-118">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91a6-118">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="f91a6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f91a6-119">See also</span></span>

- [<span data-ttu-id="f91a6-120">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="f91a6-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)
