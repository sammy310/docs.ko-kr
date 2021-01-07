---
title: 암호화 및 네트워크 보안-WCF 개발자를 위한 gRPC
description: GRPC의 네트워크 보안 및 암호화에 대 한 몇 가지 참고 사항
ms.date: 01/06/2021
ms.openlocfilehash: cf4d30ff862e64aadfeacf45ed3768fc14737800
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970143"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="7d2f9-103">암호화 및 네트워크 보안</span><span class="sxs-lookup"><span data-stu-id="7d2f9-103">Encryption and network security</span></span>

<span data-ttu-id="7d2f9-104">WCF (Windows Communication Foundation)의 네트워크 보안 모델은 광범위 하 고 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-104">The network security model for Windows Communication Foundation (WCF) is extensive and complex.</span></span> <span data-ttu-id="7d2f9-105">HTTPS 또는 TLS over TCP를 사용 하는 전송 수준 보안 및 WS-Security 사양을 사용 하 여 개별 메시지를 암호화 하는 메시지 수준 보안을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-105">It includes transport-level security by using HTTPS or TLS-over-TCP, and message-level security by using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="7d2f9-106">gRPC는 기본 HTTP/2 프로토콜에 대 한 보안 네트워킹을 유지 합니다 .이 프로토콜은 TLS 인증서를 사용 하 여 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-106">gRPC leaves secure networking to the underlying HTTP/2 protocol, which you can secure by using TLS certificates.</span></span>

<span data-ttu-id="7d2f9-107">웹 브라우저는 HTTP/2에 대 한 TLS 연결을 사용 하지만 대부분의 프로그래밍 클라이언트는를 포함 합니다. NET의 `HttpClient` 는 암호화 되지 않은 연결에 대해 HTTP/2를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-107">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span>

<span data-ttu-id="7d2f9-108">공용 Api의 경우 항상 TLS 연결을 사용 하 고 적절 한 SSL 기관에서 서비스에 대 한 유효한 인증서를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-108">For public APIs, you should always use TLS connections, and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="7d2f9-109">전체 기능 [을 제공 하는 통합](https://letsencrypt.org) SSL 인증서를 제공 하 고 대부분의 호스팅 인프라는 일반적인 플러그 인 또는 확장을 사용 하 여 사전에 암호화 표준을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-109">[LetsEncrypt](https://letsencrypt.org) provides free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="7d2f9-110">회사 네트워크에 있는 내부 서비스의 경우에도 TLS를 사용 하 여 gRPC 서비스로 들어오고 나가는 네트워크 트래픽을 보호 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="7d2f9-111">Kubernetes에서 실행 되는 서비스 간에 명시적 TLS를 사용 해야 하는 경우 클러스터 내 인증 기관 및 인증서 관리자 컨트롤러 (예: 인증서 관리자 [)](https://docs.cert-manager.io/en/latest/)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-111">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster certificate authority and a certificate manager controller like [cert-manager](https://docs.cert-manager.io/en/latest/).</span></span> <span data-ttu-id="7d2f9-112">그런 다음 배포 시 서비스에 인증서를 자동으로 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d2f9-112">You can then automatically assign certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7d2f9-113">[이전](channel-credentials.md)
>[다음](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="7d2f9-113">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
