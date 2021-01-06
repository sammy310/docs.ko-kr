---
title: 네트워크 프로토콜-WCF 개발자를 위한 gRPC
description: GRPC 네트워크 프로토콜에 대 한 개요입니다.
ms.date: 09/02/2019
ms.openlocfilehash: 801d57c95aec748e5dcf667ca480775ff945b55c
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938561"
---
# <a name="network-protocols"></a><span data-ttu-id="1e71d-103">네트워크 프로토콜</span><span class="sxs-lookup"><span data-stu-id="1e71d-103">Network protocols</span></span>

<span data-ttu-id="1e71d-104">Windows Communication Foundation (WCF)와 달리 gRPC는 네트워킹의 기반으로 HTTP/2를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-104">Unlike Windows Communication Foundation (WCF), gRPC uses HTTP/2 as a base for its networking.</span></span> <span data-ttu-id="1e71d-105">이 프로토콜은 HTTP/1.1 에서만 작동 하는 WCF 및 SOAP에 비해 상당한 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-105">This protocol offers significant advantages over WCF and SOAP, which operate only on HTTP/1.1.</span></span> <span data-ttu-id="1e71d-106">GRPC를 사용 하려는 개발자에 게는 HTTP/2에 대 한 대안이 없다는 것을 알 수 있고, h t t p/2에 대 한 자세한 정보를 제공 하 고, gRPC 사용의 추가 혜택을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-106">For developers wanting to use gRPC, given that there's no alternative to HTTP/2, it would seem to be the ideal moment to explore HTTP/2 in more detail and identify additional benefits of using gRPC.</span></span>

<span data-ttu-id="1e71d-107">2015의 Internet 공학적 작업 Force에서 릴리스된 HTTP/2는 Google에서 이미 사용 중인 실험적 SPDY 프로토콜에서 파생 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-107">HTTP/2, released by Internet Engineering Task Force in 2015, was derived from the experimental SPDY protocol, which was already being used by Google.</span></span> <span data-ttu-id="1e71d-108">이는 HTTP/1.1 보다 더 효율적이 고, 더 빠르고, 안전 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-108">It was specifically designed to be more efficient, faster, and more secure than HTTP/1.1.</span></span>

## <a name="key-features-of-http2"></a><span data-ttu-id="1e71d-109">HTTP/2의 주요 기능</span><span class="sxs-lookup"><span data-stu-id="1e71d-109">Key features of HTTP/2</span></span>

<span data-ttu-id="1e71d-110">이 목록에는 HTTP/2의 주요 기능 및 장점 중 일부가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-110">This list shows some of the key features and advantages of HTTP/2:</span></span>

### <a name="binary-protocol"></a><span data-ttu-id="1e71d-111">이진 프로토콜</span><span class="sxs-lookup"><span data-stu-id="1e71d-111">Binary protocol</span></span>

<span data-ttu-id="1e71d-112">요청/응답 주기에는 더 이상 텍스트 명령이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-112">Request/response cycles no longer need text commands.</span></span> <span data-ttu-id="1e71d-113">이 활동은 명령의 구현을 간소화 하 고 속도를 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-113">This activity simplifies and speeds up the implementation of commands.</span></span> <span data-ttu-id="1e71d-114">특히 데이터를 구문 분석 하는 것이 더 빨라지고 메모리를 사용 하는 경우에는 성능 향상을 위해 네트워크 대기 시간이 줄어들고 네트워크 리소스를 전반적으로 더 효율적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-114">Specifically, parsing data is faster and uses less memory, network latency is reduced with obvious related improvements to speed, and there's an overall better use of network resources.</span></span>

### <a name="streams"></a><span data-ttu-id="1e71d-115">스트림</span><span class="sxs-lookup"><span data-stu-id="1e71d-115">Streams</span></span>

<span data-ttu-id="1e71d-116">스트림을 사용 하 여 송신자와 수신자 간에 수명이 긴 연결을 만들 수 있습니다 .이를 통해 여러 메시지나 프레임을 비동기적으로 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-116">Streams allow you to create long-lived connections between sender and receiver, over which multiple messages or frames can be sent asynchronously.</span></span> <span data-ttu-id="1e71d-117">다중 스트림은 단일 HTTP/2 연결을 통해 독립적으로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-117">Multiple streams can operate independently over a single HTTP/2 connection.</span></span>

### <a name="request-multiplexing-over-a-single-tcp-connection"></a><span data-ttu-id="1e71d-118">단일 TCP 연결에 대 한 요청 멀티플렉싱</span><span class="sxs-lookup"><span data-stu-id="1e71d-118">Request multiplexing over a single TCP connection</span></span>

<span data-ttu-id="1e71d-119">이 기능은 HTTP/2의 가장 중요 한 혁신 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-119">This feature is one of the most important innovations of HTTP/2.</span></span> <span data-ttu-id="1e71d-120">데이터에 대해 여러 병렬 요청을 허용 하기 때문에 이제 단일 서버에서 웹 파일을 동시에 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-120">Because it allows multiple parallel requests for data, it's now possible to download web files concurrently from a single server.</span></span> <span data-ttu-id="1e71d-121">Websites는 더 빠르게 로드 되며 최적화의 필요성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-121">Websites load faster, and the need for optimization is reduced.</span></span> <span data-ttu-id="1e71d-122">이전 요청이 완료 될 때까지 준비 된 응답이 전송 될 때까지 대기 해야 하는 줄의 (유월) 차단입니다 .이 차단으로 인해 TCP 전송 수준에서 유월 차단이 계속 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-122">Head-of-line (HOL) blocking, where responses that are ready must wait to be sent until an earlier request is completed, is also mitigated (although HOL blocking can still occur at the TCP-transport level).</span></span>

### <a name="nettcp-like-performance-cross-platform"></a><span data-ttu-id="1e71d-123">Net.tcp와 같은 성능, 플랫폼 간</span><span class="sxs-lookup"><span data-stu-id="1e71d-123">Net.TCP-like performance, cross-platform</span></span>

<span data-ttu-id="1e71d-124">기본적으로 gRPC와 HTTP/2의 조합은 개발자에 게 WCF에 대 한 Net.tcp 바인딩의 최소 속도와 효율성을 제공 하 고, 경우에 따라 속도와 효율성을 향상 시킬 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-124">Fundamentally, the combination of gRPC and HTTP/2 offers developers at least the equivalent speed and efficiency of Net.TCP bindings for WCF, and in some cases even greater speed and efficiency.</span></span> <span data-ttu-id="1e71d-125">하지만 Net.tcp와 달리 HTTP/2를 통한 gRPC는 .NET 응용 프로그램으로 제한 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e71d-125">But, unlike Net.TCP, gRPC over HTTP/2 isn't constrained to .NET applications.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1e71d-126">[이전](interface-definition-language.md)
>[다음](why-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="1e71d-126">[Previous](interface-definition-language.md)
[Next](why-grpc.md)</span></span>
