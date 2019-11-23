---
title: WCF 개발자를 위한 부하 분산 gRPC-gRPC
description: GRPC 서비스를 사용할 부하 분산 장치 선택
ms.date: 09/02/2019
ms.openlocfilehash: 070fc7fda73988302d15c8cec12b1ac359641317
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967448"
---
# <a name="load-balancing-grpc"></a><span data-ttu-id="42bd8-103">부하 분산 gRPC</span><span class="sxs-lookup"><span data-stu-id="42bd8-103">Load balancing gRPC</span></span>

<span data-ttu-id="42bd8-104">GRPC 응용 프로그램의 일반적인 배포에는 복원 력 및 수평 확장 기능을 제공 하는 서비스의 여러 인스턴스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-104">A typical deployment of a gRPC application includes a number of identical instances of the service, providing resilience and horizontal scalability.</span></span> <span data-ttu-id="42bd8-105">이러한 인스턴스 간에 분산 된 들어오는 요청을 부하 분산 하 여 사용 가능한 모든 리소스의 전체 사용량을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-105">Load balancing distributed incoming requests across these instances to provide full usage of all available resources.</span></span> <span data-ttu-id="42bd8-106">이 부하 분산을 클라이언트에서 볼 수 없도록 하려면 프록시 부하 분산 장치 서버를 사용 하 여 클라이언트의 요청을 처리 하 고 백 엔드 인스턴스로 라우팅하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-106">To make this load balancing invisible to the client, it's common to use a proxy load balancer server to handle requests from clients and route them to back-end instances.</span></span>

<span data-ttu-id="42bd8-107">부하 분산 장치는 작동 하는 *계층* 에 따라 분류 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-107">Load balancers are classified according to the *layer* they operate on.</span></span> <span data-ttu-id="42bd8-108">계층 4 부하 분산 장치는 TCP 소켓, 연결 및 패킷과 같은 *전송* 수준에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-108">Layer 4 load balancers work on the *transport* level, for example, with TCP sockets, connections and packets.</span></span> <span data-ttu-id="42bd8-109">계층 7 부하 분산 장치는 *응용 프로그램* 수준에서 작동 하며 특히 grpc 응용 프로그램에 대 한 HTTP/2 요청을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-109">Layer 7 load balancers work at the *application* level, specifically handling HTTP/2 requests for gRPC applications.</span></span>

## <a name="l4-load-balancers"></a><span data-ttu-id="42bd8-110">L4 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="42bd8-110">L4 load balancers</span></span>

<span data-ttu-id="42bd8-111">L4 부하 분산 장치는 클라이언트에서 TCP 연결 요청을 수락 하 고, 백 엔드 인스턴스 중 하나에 대 한 다른 연결을 열고, 실제 처리 없이 두 연결 간에 데이터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-111">An L4 load balancer accepts a TCP connection request from a client, opens another connection to one of the back-end instances, and copies data between the two connections with no real processing.</span></span> <span data-ttu-id="42bd8-112">L4는 뛰어난 성능과 짧은 대기 시간을 제공 하지만 거의 제어 하거나 인텔리전스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-112">L4 offers excellent performance and low latency, but very little control or intelligence.</span></span> <span data-ttu-id="42bd8-113">클라이언트에서 연결이 열린 상태로 유지 되는 한 모든 요청은 동일한 백 엔드 인스턴스로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-113">As long as the client keeps the connection open, all requests will be directed to the same back-end instance.</span></span>

<span data-ttu-id="42bd8-114">L4 부하 분산 장치의 예는 [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/)입니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-114">An example of an L4 load balancer is the [Azure Load Balancer](https://azure.microsoft.com/services/load-balancer/).</span></span>

## <a name="l7-load-balancers"></a><span data-ttu-id="42bd8-115">L7 부하 분산 장치</span><span class="sxs-lookup"><span data-stu-id="42bd8-115">L7 load balancers</span></span>

<span data-ttu-id="42bd8-116">L7 부하 분산 장치는 들어오는 HTTP/2 요청을 구문 분석 하 고 클라이언트에서 연결을 유지 하는 데 걸리는 시간에 관계 없이 요청 별로 요청 별로 백 엔드 인스턴스에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-116">An L7 load balancer parses incoming HTTP/2 requests and passes them on to back-end instances on a request-by-request basis, no matter how long the connection is held by the client.</span></span>

<span data-ttu-id="42bd8-117">L7 부하 분산 장치의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-117">Examples of L7 load balancers include:</span></span>

- [<span data-ttu-id="42bd8-118">Nginx</span><span class="sxs-lookup"><span data-stu-id="42bd8-118">Nginx</span></span>](https://www.nginx.com/)
- [<span data-ttu-id="42bd8-119">HAproxy</span><span class="sxs-lookup"><span data-stu-id="42bd8-119">HAproxy</span></span>](https://www.haproxy.com/)
- [<span data-ttu-id="42bd8-120">Traefik</span><span class="sxs-lookup"><span data-stu-id="42bd8-120">Traefik</span></span>](https://traefik.io/)

<span data-ttu-id="42bd8-121">이에 대 한 규칙으로, L7 부하 분산 장치는 gRPC 및 기타 HTTP/2 응용 프로그램 (일반적으로 HTTP 응용 프로그램의 경우)에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-121">As a rule of thumb, L7 load balancers are the best choice for gRPC and other HTTP/2 applications (and for HTTP applications generally, in fact).</span></span> <span data-ttu-id="42bd8-122">L4 부하 분산 장치는 gRPC 응용 프로그램에서 *작동* 하지만, 짧은 대기 시간 및 낮은 오버 헤드가 가장 중요 한 경우에 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-122">L4 load balancers will *work* with gRPC applications, but are primarily useful when low latency and low overhead are of paramount importance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42bd8-123">이 문서를 작성 하는 시점에서 모든 L7 부하 분산 장치는 후행 헤더와 같은 gRPC 서비스에 필요한 모든 HTTP/2 사양의 일부를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-123">At the time of this writing, not all L7 load balancers support all parts of the HTTP/2 specification required by gRPC services, such as trailing headers.</span></span>

<span data-ttu-id="42bd8-124">TLS 암호화를 사용 하는 경우 부하 분산 장치는 TLS 연결을 종료 하 고 암호화 되지 않은 요청을 백 엔드 응용 프로그램에 전달 하거나 암호화 된 요청을 함께 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-124">When using TLS encryption, load balancers can terminate the TLS connection and pass unencrypted requests to the back-end application, or pass the encrypted request along.</span></span> <span data-ttu-id="42bd8-125">어느 쪽이 든, 부하 분산 장치를 서버의 공개 키와 개인 키로 구성 하 여 처리 요청을 해독할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42bd8-125">Either way, the load balancer will need to be configured with the server's public and private key, so that it can decrypt requests for processing.</span></span>

<span data-ttu-id="42bd8-126">백 엔드 서비스를 사용 하 여 HTTP/2 요청을 처리 하도록 구성 하는 방법을 알아보려면 기본 부하 분산 장치에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="42bd8-126">Refer to the documentation for your preferred load balancer to find out how to configure it to handle HTTP/2 requests with your back-end services.</span></span>

## <a name="load-balancing-within-kubernetes"></a><span data-ttu-id="42bd8-127">Kubernetes 내의 부하 분산</span><span class="sxs-lookup"><span data-stu-id="42bd8-127">Load balancing within Kubernetes</span></span>

<span data-ttu-id="42bd8-128">Kubernetes의 내부 서비스 간 부하 분산에 대 한 자세한 내용은 [서비스 메시의 섹션](service-mesh.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="42bd8-128">See [the section on Service Meshes](service-mesh.md) for a discussion of load balancing across internal services on Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="42bd8-129">[이전](service-mesh.md)
>[다음](application-performance-management.md)</span><span class="sxs-lookup"><span data-stu-id="42bd8-129">[Previous](service-mesh.md)
[Next](application-performance-management.md)</span></span>
