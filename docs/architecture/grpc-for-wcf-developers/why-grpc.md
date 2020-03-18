---
title: WCF 개발자를 위한 gRPC - WCF 개발자를 위한 gRPC를 권장하는 이유
description: gRPC가 현대 아키텍처 및 플랫폼으로 마이그레이션하려는 WCF 개발자에게 적합한 이유에 대해 설명합니다.
ms.date: 09/02/2019
ms.openlocfilehash: 664781e94c24c1796eafa6a70eb28d453b530d66
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147648"
---
# <a name="why-we-recommend-grpc-for-wcf-developers"></a><span data-ttu-id="d3b7c-103">WCF 개발자에게 gRPC를 권장하는 이유</span><span class="sxs-lookup"><span data-stu-id="d3b7c-103">Why we recommend gRPC for WCF developers</span></span>

<span data-ttu-id="d3b7c-104">gRPC의 언어와 기술에 대해 자세히 알아보기 전에 .NET Core로 마이그레이션하려는 WCF(Windows 통신 재단) 개발자에게 gRPC가 올바른 솔루션인 이유를 논의할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-104">Before we dive deeply into the language and techniques of gRPC, it's worth discussing why gRPC is the right solution for Windows Communication Foundation (WCF) developers who want to migrate to .NET Core.</span></span>

## <a name="similarity-to-wcf"></a><span data-ttu-id="d3b7c-105">WCF와 유사성</span><span class="sxs-lookup"><span data-stu-id="d3b7c-105">Similarity to WCF</span></span>

<span data-ttu-id="d3b7c-106">구현 및 gRPC에 대 한 접근 방식은 다르지만 gRPC를 사용 하 여 서비스를 개발 하 고 소비 하는 경험 WCF 개발자에 대 한 직관적이어야 한다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-106">Although the implementation and approach are different for gRPC, the experience of developing and consuming services with gRPC should be intuitive for WCF developers.</span></span> <span data-ttu-id="d3b7c-107">기본 목표는 클라이언트와 서버가 네트워킹에 대해 걱정할 필요 없이 동일한 플랫폼에 있는 것처럼 코딩할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-107">The underlying goal is the same: make it possible to code as though the client and server are on the same platform, without needing to worry about networking.</span></span>

<span data-ttu-id="d3b7c-108">두 플랫폼 모두 해당 인터페이스를 선언하는 프로세스가 다르더라도 인터페이스를 선언하고 구현한다는 원칙을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-108">Both platforms share the principle of declaring and then implementing an interface, even though the process for declaring that interface is different.</span></span> <span data-ttu-id="d3b7c-109">5장에서 볼 수 있듯이 gRPC가 지원하는 다양한 유형의 RPC 호출은 WCF 서비스에서 사용할 수 있는 바인딩에 맵을 잘 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-109">And as you'll see in chapter 5, the different types of RPC calls that gRPC supports map well to the bindings available to WCF services.</span></span>

## <a name="benefits-of-grpc"></a><span data-ttu-id="d3b7c-110">gRPC의 이점</span><span class="sxs-lookup"><span data-stu-id="d3b7c-110">Benefits of gRPC</span></span>

<span data-ttu-id="d3b7c-111">gRPC는 다음과 같은 이유로 다른 솔루션보다 위에 서 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-111">gRPC stands above other solutions for the following reasons.</span></span>

### <a name="performance"></a><span data-ttu-id="d3b7c-112">성능</span><span class="sxs-lookup"><span data-stu-id="d3b7c-112">Performance</span></span>

<span data-ttu-id="d3b7c-113">HTTP/1.1대신 HTTP/2를 사용하면 사람이 읽을 수 있는 메시지에 대한 요구 사항이 제거되고 대신 더 작고 빠른 이진 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-113">Using HTTP/2 rather than HTTP/1.1 removes the requirement for human-readable messages and instead uses the smaller, faster binary protocol.</span></span> <span data-ttu-id="d3b7c-114">이는 컴퓨터가 구문 분석하는 데 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-114">This is more efficient for computers to parse.</span></span> <span data-ttu-id="d3b7c-115">HTTP/2는 단일 연결을 통해 다중화 요청을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-115">HTTP/2 also supports multiplexing requests over a single connection.</span></span> <span data-ttu-id="d3b7c-116">이 지원을 통해 대기열에서 기다릴 필요 없이 응답이 준비되는 즉시 응답을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-116">This support enables responses to be sent as soon as they're ready without the need to wait in a queue.</span></span> <span data-ttu-id="d3b7c-117">(HTTP/1.1에서 이 문제를 "홀라인(HEAD-of-line) 차단"이라고 합니다.) gRPC를 사용할 때 는 더 적은 리소스가 필요하므로 모바일 장치및 느린 네트워크에서 사용하기에 좋은 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-117">(In HTTP/1.1, this issue is known as "head-of-line (HOL) blocking.") You need fewer resources when using gRPC, which makes it a good solution to use for mobile devices and over slower networks.</span></span>

### <a name="interoperability"></a><span data-ttu-id="d3b7c-118">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="d3b7c-118">Interoperability</span></span>

<span data-ttu-id="d3b7c-119">.NET, Java, 파이썬, 이동, C++, Node.js, 스위프트, 다트, 루비 및 PHP를 포함한 모든 주요 프로그래밍 언어 및 플랫폼에 대한 gRPC 도구 및 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-119">There are gRPC tools and libraries for all major programming languages and platforms, including .NET, Java, Python, Go, C++, Node.js, Swift, Dart, Ruby, and PHP.</span></span> <span data-ttu-id="d3b7c-120">프로토콜 버퍼스 바이너리 와이어 형식과 각 플랫폼의 효율적인 코드 생성 덕분에 개발자는 완전한 플랫폼 간 지원을 즐기면서 성능이 뛰어난 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-120">Thanks to the Protocol Buffers binary wire format and the efficient code generation for each platform, developers can build performant apps while still enjoying full cross-platform support.</span></span>

### <a name="usability-and-productivity"></a><span data-ttu-id="d3b7c-121">유용성 및 생산성</span><span class="sxs-lookup"><span data-stu-id="d3b7c-121">Usability and productivity</span></span>

<span data-ttu-id="d3b7c-122">gRPC는 포괄적인 RPC 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-122">gRPC is a comprehensive RPC solution.</span></span> <span data-ttu-id="d3b7c-123">그것은 여러 언어와 플랫폼에서 일관되게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-123">It works consistently across multiple languages and platforms.</span></span> <span data-ttu-id="d3b7c-124">또한 필요한 상용구 코드가 자동으로 생성되는 우수한 툴링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-124">It also provides excellent tooling, with much of the necessary boilerplate code automatically generated.</span></span> <span data-ttu-id="d3b7c-125">따라서 비즈니스 논리에 집중할 수 있는 개발자 시간이 늘어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-125">So more developer time is freed up to focus on business logic.</span></span>

### <a name="streaming"></a><span data-ttu-id="d3b7c-126">스트리밍</span><span class="sxs-lookup"><span data-stu-id="d3b7c-126">Streaming</span></span>

<span data-ttu-id="d3b7c-127">gRPC에는 WCF의 전체 이중 서비스와 유사한 기능을 제공하는 전체 양방향 스트리밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-127">gRPC has full bidirectional streaming, which provides similar functionality to WCF's full duplex services.</span></span> <span data-ttu-id="d3b7c-128">gRPC 스트리밍은 일반 인터넷 연결, 로드 밸러버 및 서비스 메시(service meshes)를 통해 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-128">gRPC streaming can operate over regular internet connections, load balancers, and service meshes.</span></span>

### <a name="deadlinetimeouts-and-cancellation"></a><span data-ttu-id="d3b7c-129">마감일/시간 시간 및 취소</span><span class="sxs-lookup"><span data-stu-id="d3b7c-129">Deadline/timeouts and cancellation</span></span>

<span data-ttu-id="d3b7c-130">gRPC를 사용하면 클라이언트가 RPC가 완료될 때까지 최대 시간을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-130">gRPC allows clients to specify a maximum time for an RPC to finish.</span></span> <span data-ttu-id="d3b7c-131">지정된 기한을 초과하면 서버는 클라이언트와 독립적으로 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-131">If the specified deadline is exceeded, the server can cancel the operation independently of the client.</span></span> <span data-ttu-id="d3b7c-132">추가 gRPC 호출을 통해 기한 및 취소를 전파하여 리소스 사용 제한을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-132">Deadlines and cancellations can be propagated through further gRPC calls to help enforce resource usage limits.</span></span> <span data-ttu-id="d3b7c-133">클라이언트는 기한을 초과하거나 필요한 경우 더 일찍(예: 사용자 상호 작용으로 인해) 작업을 중지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-133">Clients can also stop operations when a deadline is exceeded, or earlier if necessary (for example, because of a user interaction).</span></span>

### <a name="security"></a><span data-ttu-id="d3b7c-134">보안</span><span class="sxs-lookup"><span data-stu-id="d3b7c-134">Security</span></span>

<span data-ttu-id="d3b7c-135">gRPC는 TLS 종단 간 암호화 된 연결을 통해 HTTP/2를 사용하는 경우 암시적으로 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-135">gRPC is implicitly secure when it's using HTTP/2 over a TLS end-to-end encrypted connection.</span></span> <span data-ttu-id="d3b7c-136">클라이언트 인증서 인증 [지원(6장](security.md)참조)은 클라이언트와 서버 간의 보안 및 신뢰도를 더욱 높입니다.</span><span class="sxs-lookup"><span data-stu-id="d3b7c-136">Support for client certificate authentication (see [chapter 6](security.md)) further increases security and trust between client and server.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d3b7c-137">[이전](network-protocols.md)
>[다음](protocol-buffers.md)</span><span class="sxs-lookup"><span data-stu-id="d3b7c-137">[Previous](network-protocols.md)
[Next](protocol-buffers.md)</span></span>
