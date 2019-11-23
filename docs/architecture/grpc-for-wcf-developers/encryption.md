---
title: 암호화 및 네트워크 보안-WCF 개발자를 위한 gRPC
description: GRPC의 네트워크 보안 및 암호화에 대 한 몇 가지 참고 사항
ms.date: 09/02/2019
ms.openlocfilehash: fd993a2d75e97011c6c92cee02c24c5358a211ad
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967772"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="e0f20-103">암호화 및 네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="e0f20-103">Encryption and network security</span></span>

<span data-ttu-id="e0f20-104">WCF의 네트워크 보안 모델은 HTTPS 또는 TLS over TCP를 사용 하는 전송 수준 보안 및 WS-SECURITY 사양을 사용 하 여 개별 메시지를 암호화 하는 메시지 수준 보안을 비롯 하 여 광범위 하 고 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="e0f20-105">gRPC는 일반 TLS 인증서를 사용 하 여 보안을 설정할 수 있는 기본 HTTP/2 프로토콜에 대 한 보안 네트워킹을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="e0f20-106">웹 브라우저는 HTTP/2에 대 한 TLS 연결을 사용 하지만 대부분의 프로그래밍 클라이언트는를 포함 합니다. NET의 `HttpClient`는 암호화 되지 않은 연결에 대해 HTTP/2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="e0f20-107">`HttpClient` *는* 기본적으로 암호화가 필요 하지만 <xref:System.AppContext> 스위치를 사용 하 여이를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="e0f20-108">공용 Api의 경우 항상 TLS 연결을 사용 하 고 적절 한 SSL 기관에서 서비스에 대 한 유효한 인증서를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="e0f20-109">전체 기능을 제공 하는 무료 SSL 인증서를 제공 하 고 대부분의 호스팅 인프라에서는 일반적인 플러그 인 또는 확장을 사용 하 여 사전 [에 암호화 표준](https://letsencrypt.org) 을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="e0f20-110">회사 네트워크에 있는 내부 서비스의 경우에도 TLS를 사용 하 여 gRPC 서비스로 들어오고 나가는 네트워크 트래픽을 보호 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="e0f20-111">Kubernetes 또는 Docker Swarm와 같은 클러스터의 마이크로 서비스 간 통신은 일반적으로 컨테이너 네트워킹 계층에 의해 자동으로 암호화 되므로 이러한 클러스터에서 독점적으로 실행 되는 서비스에서 TLS를 구현 하는 것은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="e0f20-112">이 주제에 대 한 자세한 내용은 다음 장의 "서비스 메시" 섹션에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="e0f20-113">Kubernetes에서 실행 되는 서비스 간에 명시적 TLS를 사용 해야 하는 경우 클러스터 내 인증 기관과 인증서 관리자 컨트롤러 (인증서 관리자 [)](https://docs.cert-manager.io/en/latest/) 를 사용 하 여 배포 시 서비스에 자동으로 인증서를 할당 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e0f20-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e0f20-114">[이전](channel-credentials.md)
>[다음](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="e0f20-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
