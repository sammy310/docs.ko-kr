---
title: Wcf 개발자를 위한 gRPC를 wcf 개발자에 게 권장 하는 이유
description: 최신 아키텍처 및 플랫폼으로 마이그레이션하기 위해 gRPC가 WCF 개발자에 게 적합 한 이유에 대 한 설명입니다.
ms.date: 09/02/2019
ms.openlocfilehash: da712e1ceee92f0a1a2661252dcda602f5dde9a0
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966940"
---
# <a name="why-grpc-is-recommended-for-wcf-developers"></a><span data-ttu-id="8e777-103">gRPC가 WCF 개발자에게 권장되는 이유</span><span class="sxs-lookup"><span data-stu-id="8e777-103">Why gRPC is recommended for WCF developers</span></span>

<span data-ttu-id="8e777-104">GRPC의 언어와 기술에 대해 자세히 살펴보기 전에 gRPC가 .NET Core로 마이그레이션하려는 WCF 개발자를 위한 적절 한 솔루션인 경우 사용 가능한 대안이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-104">Before diving deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for WCF developers who want to migrate to .NET Core, given there are alternatives available.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="8e777-105">WCF와 유사성</span><span class="sxs-lookup"><span data-stu-id="8e777-105">Similarity to WCF</span></span>

<span data-ttu-id="8e777-106">구현 및 접근 방식은 서로 다르지만, gRPC를 사용 하 여 서비스를 개발 하 고 사용 하는 실제 환경은 WCF 개발자에 게 매우 직관적입니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-106">Although its implementation and approach is different, the actual experience of developing and consuming services with gRPC should be very intuitive for WCF developers.</span></span> <span data-ttu-id="8e777-107">네트워킹에 대해 걱정할 필요 없이 클라이언트와 서버가 동일한 플랫폼에 있는 것 처럼 코딩할 수 있도록 하는 기본 목표는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-107">The underlying goal of making it possible to code as though the client and server were on the same platform, without needing to worry about networking, is the same.</span></span> <span data-ttu-id="8e777-108">두 플랫폼 모두 인터페이스를 선언 하는 프로세스는 서로 다르므로 인터페이스를 선언 하 고 구현 하는 원칙을 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="8e777-109">또한 5 장에서 볼 수 있듯이 gRPC 맵에서 지원 되는 다양 한 유형의 RPC 호출은 WCF 서비스에 사용할 수 있는 다른 바인딩에 매우 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-109">And as you'll see in chapter 5, the different types of RPC calls supported by gRPC map very well to the different bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="8e777-110">GRPC의 이점</span><span class="sxs-lookup"><span data-stu-id="8e777-110">Benefits of gRPC</span></span>

<span data-ttu-id="8e777-111">GRPC가 다른 솔루션 위에 표시 되는 추가 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-111">Additional reasons why gRPC stands above other solutions are:</span></span>

### <a name="performance"></a><span data-ttu-id="8e777-112">성능</span><span class="sxs-lookup"><span data-stu-id="8e777-112">Performance</span></span>

<span data-ttu-id="8e777-113">앞서 설명한 것 처럼 http/1.1 대신 HTTP/2를 사용 하면 사람이 읽을 수 있는 메시지에 대 한 요구 사항이 제거 되 고 대신 더 작은 크기의 이진 프로토콜을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-113">As already discussed, using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller faster binary protocol.</span></span> <span data-ttu-id="8e777-114">이 방법은 컴퓨터를 구문 분석 하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="8e777-115">또한 h t t p/2는 단일 연결에 대 한 멀티플렉싱 요청을 지원 하 여 큐에서 대기할 필요 없이 응답을 보낼 수 있도록 합니다. HTTP/1.1의 문제 (예를 들어, "줄 간 (유월) 차단").</span><span class="sxs-lookup"><span data-stu-id="8e777-115">HTTP/2 also supports multiplexing requests over a single connection enabling responses to be sent as soon as they're ready without the need to wait in a queue (an issue in HTTP/1.1 known as "head-of-line (HOL) blocking").</span></span> <span data-ttu-id="8e777-116">GRPC를 사용 하는 경우 더 많은 리소스가 필요 하며,이를 통해 모바일 장치와 느린 네트워크에서 사용할 수 있는 좋은 솔루션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-116">Fewer resources are needed when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="8e777-117">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="8e777-117">Interoperability</span></span>

<span data-ttu-id="8e777-118">.NET, Java, Python, Go, C++Node.js, Swift, Dart, RUBY 및 PHP를 비롯 한 모든 주요 프로그래밍 언어 및 플랫폼에 대 한 grpc 도구 및 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-118">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="8e777-119">프로토콜을 통해 이진 통신 형식 및 각 플랫폼에 대 한 효율적인 코드 생성 덕분에 개발자는 전체 플랫폼 간 지원을 제공 하면서도 고성능 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-119">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="8e777-120">유용성 및 생산성</span><span class="sxs-lookup"><span data-stu-id="8e777-120">Usability and productivity</span></span>

<span data-ttu-id="8e777-121">gRPC는 포괄적인 RPC 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-121">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="8e777-122">이는 여러 언어 및 플랫폼에서 일관 되 게 작동 하며, 필요한 모든 상용구 코드를 자동으로 생성 하는 뛰어난 도구를 제공 하므로 많은 개발자 시간을 비즈니스 논리에 초점을 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-122">It works consistently across multiple languages and platforms, and provides excellent tooling, with much of the necessary boilerplate code auto-generated, so more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="8e777-123">스트리밍</span><span class="sxs-lookup"><span data-stu-id="8e777-123">Streaming</span></span>

<span data-ttu-id="8e777-124">gRPC에는 WCF의 전이중 서비스와 매우 유사한 기능을 제공 하는 전체 양방향 스트리밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-124">gRPC has full bidirectional streaming, which provides very similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="8e777-125">gRPC 스트리밍은 일반적인 인터넷 연결, 부하 분산 장치 및 서비스 메시를 통해 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-125">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="8e777-126">최종 기한/시간 제한 및 취소</span><span class="sxs-lookup"><span data-stu-id="8e777-126">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="8e777-127">gRPC는 클라이언트가 RPC를 완료 하는 최대 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-127">gRPC allows clients to specify a maximum time for an RPC to complete.</span></span> <span data-ttu-id="8e777-128">지정 된 최종 기한이 초과 된 경우 서버에서 클라이언트와 별개로 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-128">If the specified deadline is exceeded the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="8e777-129">마감일 및 취소는 리소스 사용 제한을 적용 하는 데 도움이 되도록 추가 gRPC 호출을 통해 전파 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-129">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="8e777-130">클라이언트는 최종 기한이 초과 되거나 필요한 경우 이전 (예: 사용자 상호 작용으로 인 한 경우)에 작업을 중단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-130">Clients may also abort operations when a deadline is exceeded, or earlier if necessary (e.g. due to a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="8e777-131">보안</span><span class="sxs-lookup"><span data-stu-id="8e777-131">Security</span></span>

<span data-ttu-id="8e777-132">gRPC는 TLS 종단 간 암호화 된 연결에 대해 HTTP/2를 사용 하는 경우 암시적으로 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-132">gRPC is implicitly secure when using HTTP/2 over an TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="8e777-133">클라이언트 인증서 인증에 대 한 지원 (6 장 참조)은 클라이언트와 서버 간의 보안 및 신뢰를 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e777-133">Support for Client Certificate authentication (see chapter 6) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8e777-134">[이전](network-protocols.md)
>[다음](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="8e777-134">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
