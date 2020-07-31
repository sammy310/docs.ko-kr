---
title: '완화: WCF 서비스 및 인증서 인증'
description: .NET Framework 4.6의 WCF SSL 프로토콜 기본 목록 변경에서 인증서 인증 문제를 완화하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: ef19c91a-b9df-4bf0-a28e-eb1e99c4bc95
ms.openlocfilehash: b6460e58bb32151003430d6573c4bcf1b514081b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475374"
---
# <a name="mitigation-wcf-services-and-certificate-authentication"></a><span data-ttu-id="30463-103">완화: WCF 서비스 및 인증서 인증</span><span class="sxs-lookup"><span data-stu-id="30463-103">Mitigation: WCF Services and Certificate Authentication</span></span>

<span data-ttu-id="30463-104">.NET Framework 4.6은 WCF SSL 프로토콜 기본 목록에 TLS 1.1 및 TLS 1.2를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="30463-104">The .NET Framework 4.6 adds TLS 1.1 and TLS 1.2 to the WCF SSL protocol default list.</span></span> <span data-ttu-id="30463-105">클라이언트와 서버 컴퓨터에.NET Framework 4.6 및 이후 버전이 설치되어 있으면 TLS 1.2가 협상에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30463-105">When both client and server machines have  the .NET Framework 4.6 or later installed, TLS 1.2 is used for negotiation.</span></span>

## <a name="impact"></a><span data-ttu-id="30463-106">영향</span><span class="sxs-lookup"><span data-stu-id="30463-106">Impact</span></span>

<span data-ttu-id="30463-107">TLS 1.2는 MD5 인증서 인증을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-107">TLS 1.2 does not support MD5 certificate authentication.</span></span> <span data-ttu-id="30463-108">결과적으로 고객이 해시 알고리즘에 대해 MD5를 사용하는 SSL 인증서를 사용하는 경우 WCF 클라이언트에서 WCF 서비스에 연결하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="30463-108">As a result, if a customer uses an SSL certificate which uses MD5 for the hash algorithm, the WCF client fails to connect to the WCF service.</span></span> <span data-ttu-id="30463-109">자세한 내용은 [완화: WCF 서비스 및 인증서 인증](mitigation-wcf-services-and-certificate-authentication.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="30463-109">For more information, see [Mitigation: WCF Services and Certificate Authentication](mitigation-wcf-services-and-certificate-authentication.md).</span></span>

## <a name="mitigation"></a><span data-ttu-id="30463-110">완화</span><span class="sxs-lookup"><span data-stu-id="30463-110">Mitigation</span></span>

<span data-ttu-id="30463-111">다음 중 하나를 수행하여 WCF 클라이언트가 WCF 서버에 연결할 수 있도록 함으로써 이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-111">You can work around this issue so that a WCF client can connect to a WCF server by doing any of the following:</span></span>

- <span data-ttu-id="30463-112">MD5 알고리즘을 사용 하지 않도록 인증서를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30463-112">Update the certificate to not use the MD5 algorithm.</span></span> <span data-ttu-id="30463-113">이것은 권장되는 해결 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="30463-113">This is the recommended solution.</span></span>

- <span data-ttu-id="30463-114">소스 코드에서 바인딩이 동적으로 구성되지 않은 경우 TLS 1.1 또는 이전 버전의 프로토콜을 사용하도록 애플리케이션의 구성 파일을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30463-114">If the binding is not dynamically configured in source code, update the application's configuration file to use TLS 1.1 or an earlier version of the protocol.</span></span> <span data-ttu-id="30463-115">이렇게 하면 MD5 해시 알고리즘에서 인증서를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-115">This allows you to continue to use a certificate with the MD5 hash algorithm.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="30463-116">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-116">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

  <span data-ttu-id="30463-117">다음 구성 파일에 이 내용이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-117">The following configuration file does this:</span></span>

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
      </system.serviceModel>
  </configuration>
  ```

- <span data-ttu-id="30463-118">소스 코드에서 바인딩이 동적으로 구성된 경우 소스 코드에서 TLS 1.1(<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) 또는 이전 버전의 프로토콜을 사용하도록 <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> 속성을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="30463-118">If the binding is dynamically configured in source code, update the <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols%2A?displayProperty=nameWithType> property to use TLS 1.1 (<xref:System.Security.Authentication.SslProtocols.Tls11?displayProperty=nameWithType>) or an  earlier version of the protocol in the source code.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="30463-119">MD5 해시 알고리즘을 사용하는 인증서는 안전하지 않은 것으로 간주되므로 이 해결 방법은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="30463-119">This workaround is not recommended, since a certificate with the MD5 hash algorithm is considered insecure.</span></span>

## <a name="see-also"></a><span data-ttu-id="30463-120">참조</span><span class="sxs-lookup"><span data-stu-id="30463-120">See also</span></span>

- [<span data-ttu-id="30463-121">애플리케이션 호환성</span><span class="sxs-lookup"><span data-stu-id="30463-121">Application compatibility</span></span>](application-compatibility.md)
