---
title: WS-* 프로토콜-WCF 개발자를 위한 gRPC
description: WCF에서 지원 되는 WS-* 프로토콜 및 gRPC에서 사용할 수 있는 대체 항목의 검토
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 4e7b80df182fb69cc51e14738e59ad87efaf5dd2
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841314"
---
# <a name="ws--protocols"></a><span data-ttu-id="ca28e-103">WS\* 프로토콜</span><span class="sxs-lookup"><span data-stu-id="ca28e-103">WS-\* protocols</span></span>

<span data-ttu-id="ca28e-104">WCF (Windows Communication Foundation)를 사용 하는 경우의 실질적인 이점 중 하나는 기존 _WS-\*_ 표준 프로토콜을 많이 지원 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-104">One of the real benefits of working with Windows Communication Foundation (WCF) was that it supported many of the existing _WS-\*_ standard protocols.</span></span> <span data-ttu-id="ca28e-105">이 섹션에서는 gRPC가 동일한 WS\* 프로토콜을 관리 하는 방법에 대해 간략하게 설명 하 고 대안이 없을 때 사용할 수 있는 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-105">This section will briefly cover how gRPC manages the same WS-\* protocols and discuss what options are available when there's no alternative.</span></span>

## <a name="metadata-exchange---ws-policy-ws-discovery-and-so-on"></a><span data-ttu-id="ca28e-106">메타 데이터 교환-정책, WS-검색 등</span><span class="sxs-lookup"><span data-stu-id="ca28e-106">Metadata Exchange - WS-Policy, WS-Discovery, and so on</span></span>

<span data-ttu-id="ca28e-107">SOAP 서비스는 데이터 형식, 작업 또는 통신 옵션과 같은 정보를 사용 하 여 WSDL (웹 서비스 기술 언어) 스키마 문서를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-107">SOAP services expose Web Services Description Language (WSDL) schema documents with information such as data formats, operations, or communication options.</span></span> <span data-ttu-id="ca28e-108">이 스키마는 클라이언트 코드를 생성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-108">This schema could be used to generate the client code.</span></span>

<span data-ttu-id="ca28e-109">gRPC는 동일한 `.proto` 파일에서 서버 및 클라이언트를 생성할 때 가장 잘 작동 하지만 서버 리플렉션 선택적 확장 프로그램은 실행 중인 서버에서 동적 정보를 노출 하는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-109">gRPC works best when servers and clients are generated from the same `.proto` files, but a server reflection optional extension does provide a way to expose dynamic information from a running server.</span></span> <span data-ttu-id="ca28e-110">자세한 내용은 [grpc. 리플렉션](https://nuget.org/packages/Grpc.Reflection) NuGet 패키지 및 [Grpc C# 서버 리플렉션](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca28e-110">For more information, see the [Grpc.Reflection](https://nuget.org/packages/Grpc.Reflection) NuGet package and the [gRPC C# Server Reflection](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) article.</span></span>

<span data-ttu-id="ca28e-111">WS 검색 프로토콜은 로컬 네트워크에서 서비스를 찾는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-111">The WS-Discovery protocol is used to locate services on a local network.</span></span> <span data-ttu-id="ca28e-112">gRPC 서비스는 일반적으로 DNS 또는 Consul 또는 사육 사와 같은 서비스 레지스트리를 사용 하 여 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-112">gRPC services are generally located using DNS or a service registry such as Consul or ZooKeeper.</span></span>

## <a name="security--ws-security-ws-federation-xml-encryption-and-so-on"></a><span data-ttu-id="ca28e-113">보안 – WS-SECURITY, WS-FEDERATION, XML 암호화 등</span><span class="sxs-lookup"><span data-stu-id="ca28e-113">Security – WS-Security, WS-Federation, XML Encryption, and so on</span></span>

<span data-ttu-id="ca28e-114">보안, 인증 및 권한 부여에 대 한 자세한 내용은 [6 장](security.md)에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-114">Security, authentication, and authorization are covered in much more detail in [Chapter 6](security.md).</span></span> <span data-ttu-id="ca28e-115">그러나 WCF와는 달리 gRPC는 WS-SECURITY, WS 페더레이션 또는 XML 암호화를 지원 하지 않는다는 점을 기억해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-115">But it's worth noting here that, unlike WCF, gRPC doesn't support WS-Security, WS Federation, or XML Encryption.</span></span> <span data-ttu-id="ca28e-116">그러나 gRPC는 뛰어난 보안 기능을 제공 합니다. TLS를 통한 HTTP/2를 사용 하는 경우 모든 gRPC 네트워크 트래픽이 자동으로 암호화 되며, 상호 클라이언트/서버 인증에 X509 인증서를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-116">Even so, gRPC provides excellent security; all gRPC network traffic is automatically encrypted when using HTTP/2 over TLS, and X509 certificates may be used for mutual client/server authentication.</span></span>

## <a name="ws-reliablemessaging"></a><span data-ttu-id="ca28e-117">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="ca28e-117">WS-ReliableMessaging</span></span>

<span data-ttu-id="ca28e-118">gRPC는 WS-RELIABLEMESSAGING에 해당 하는 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-118">gRPC does not provide an equivalent to WS-ReliableMessaging.</span></span> <span data-ttu-id="ca28e-119">재시도 의미 체계가 같은 라이브러리를 사용 하 여 코드에서 처리 되어야 [합니다.](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="ca28e-119">Retry semantics should be handled in code, possibly with a library like [Polly](https://github.com/App-vNext/Polly).</span></span> <span data-ttu-id="ca28e-120">Kubernetes 또는 유사한 오케스트레이션 환경에서 실행 하는 경우 [서비스 메시](service-mesh.md) 는 서비스 간에 신뢰할 수 있는 메시징을 제공 하는 데도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-120">When running in Kubernetes or similar orchestration environments, [service meshes](service-mesh.md) can also help to provide reliable messaging between services.</span></span>

## <a name="ws-transaction-ws-coordination"></a><span data-ttu-id="ca28e-121">WS 트랜잭션, WS 조정</span><span class="sxs-lookup"><span data-stu-id="ca28e-121">WS-Transaction, WS-Coordination</span></span>

<span data-ttu-id="ca28e-122">WCF의 분산 트랜잭션 구현에서는 Windows의 Microsoft DTC(Distributed Transaction Coordinator) 또는 MSDTC를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-122">WCF's implementation of distributed transactions uses Windows’ Microsoft Distributed Transaction Coordinator or MSDTC.</span></span> <span data-ttu-id="ca28e-123">SQL Server, MSMQ 또는 Windows 파일 시스템과 같이 구체적으로 지 원하는 리소스 관리자와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-123">It works with resource managers that specifically support it, like SQL Server, MSMQ, or Windows file systems.</span></span> <span data-ttu-id="ca28e-124">최신 마이크로 서비스 세계에서 사용 되는 광범위 한 기술 덕분에 아직 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca28e-124">In the modern microservices world, in part due to the wider range of technologies in use, there is no equivalent as yet.</span></span> <span data-ttu-id="ca28e-125">트랜잭션에 대 한 설명은 [부록 a](appendix.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca28e-125">For a discussion of transactions, see [Appendix A](appendix.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ca28e-126">[이전](error-handling.md)
>[다음](migrate-wcf-to-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="ca28e-126">[Previous](error-handling.md)
[Next](migrate-wcf-to-grpc.md)</span></span>
