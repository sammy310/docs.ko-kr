---
title: 인터넷 프로토콜 버전 6
description: IPv6 프로토콜 및 이 프로토콜이 IPv4와 어떻게 다른지 알아봅니다. .NET Framework 애플리케이션은 IPv6을 지원하지만 구성이 필요할 수도 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: c2b23705ae309436344513e54d6258e206d69da4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551467"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="70ba4-104">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="70ba4-104">Internet Protocol Version 6</span></span>
<span data-ttu-id="70ba4-105">IPv6(인터넷 프로토콜 버전 6)은 인터넷 네트워크 계층에 대한 새로운 표준 프로토콜 도구 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-105">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="70ba4-106">IPv6은 주소 고갈, 보안, 자동 구성, 확장성 등에 관련된 현재 버전 인터넷 프로토콜 도구 모음(IPv4라고 함)의 많은 문제를 해결하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-106">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="70ba4-107">IPv6은 피어 투 피어 및 모바일 애플리케이션을 포함한 새로운 종류의 애플리케이션을 구현하기 위해 인터넷 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-107">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="70ba4-108">현재 IPv4 프로토콜의 주요 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-108">The following are the main issues of the current IPv4 protocol:</span></span>  
  
- <span data-ttu-id="70ba4-109">주소 공간의 빠른 고갈.</span><span class="sxs-lookup"><span data-stu-id="70ba4-109">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="70ba4-110">이 문제로 인해 여러 개인 주소를 단일 공용 IP 주소에 매핑하는 NAT(Network Address Translator)를 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-110">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="70ba4-111">이 메커니즘에서 발생하는 주요 문제는 처리 오버헤드 및 엔드투엔드 연결 부족입니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-111">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
- <span data-ttu-id="70ba4-112">계층 구조 지원 없음.</span><span class="sxs-lookup"><span data-stu-id="70ba4-112">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="70ba4-113">고유의 미리 정의된 클래스 조직으로 인해 IPv4에는 실제 계층 구조 지원이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-113">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="70ba4-114">실제로 네트워크 토폴로지를 매핑하는 방식으로 IP 주소를 구조화할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-114">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="70ba4-115">이 중대한 설계 결함으로 인해 IPv4 패킷을 인터넷의 임의 위치에 전달하기 위해 큰 라우팅 테이블이 필요하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-115">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
- <span data-ttu-id="70ba4-116">복잡한 네트워크 구성.</span><span class="sxs-lookup"><span data-stu-id="70ba4-116">Complex network configuration.</span></span>  
  
     <span data-ttu-id="70ba4-117">IPv4를 사용할 경우 주소를 정적으로 할당하거나 주소에 DHCP 등의 구성 프로토콜을 사용 중이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-117">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="70ba4-118">이상적인 상황에서는 호스트가 DHCP 인프라의 관리에 의존할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-118">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="70ba4-119">대신에 호스트는 배치되어 있는 네트워크 세그먼트를 기반으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-119">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
- <span data-ttu-id="70ba4-120">기본 제공 인증 및 기밀성 없음.</span><span class="sxs-lookup"><span data-stu-id="70ba4-120">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="70ba4-121">IPv4의 경우 교환된 데이터에 대한 인증이나 암호화를 제공하는 메커니즘을 지원할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-121">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="70ba4-122">이 내용은 IPv6에서 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-122">This changes with IPv6.</span></span> <span data-ttu-id="70ba4-123">IPSec(인터넷 프로토콜 보안)는 IPv6 지원 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-123">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="70ba4-124">새로운 프로토콜 도구 모음은 다음 기본 요구 사항을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-124">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
- <span data-ttu-id="70ba4-125">낮은 오버헤드가 발생하는 대규모 라우팅 및 주소 지정.</span><span class="sxs-lookup"><span data-stu-id="70ba4-125">Large-scale routing and addressing with low overhead.</span></span>  
  
- <span data-ttu-id="70ba4-126">다양한 연결 상황에 대한 자동 구성.</span><span class="sxs-lookup"><span data-stu-id="70ba4-126">Auto-configuration for various connecting situations.</span></span>  
  
- <span data-ttu-id="70ba4-127">기본 제공 인증 및 기밀성.</span><span class="sxs-lookup"><span data-stu-id="70ba4-127">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="70ba4-128">자세한 내용은 [IPv6 주소 지정](ipv6-addressing.md), [IPv6 라우팅](ipv6-routing.md), [IPv6 자동 구성](ipv6-auto-configuration.md), [IPv6 사용 및 사용 안 함](enabling-and-disabling-ipv6.md) 및 [방법: IPv6 지원을 사용하도록 컴퓨터 구성 파일 수정](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70ba4-128">For more information, see [IPv6 Addressing](ipv6-addressing.md), [IPv6 Routing](ipv6-routing.md), [IPv6 Auto-Configuration](ipv6-auto-configuration.md), [Enabling and Disabling IPv6](enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="70ba4-129">참조 항목</span><span class="sxs-lookup"><span data-stu-id="70ba4-129">References</span></span>  
 <span data-ttu-id="70ba4-130">[IETF(Internet Engineering Task Force)](https://www.ietf.org/) 웹 사이트에서 찾을 수 있는 선택된 RFC 문서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-130">The following are selected RFC documents that you can find at the [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website:</span></span>  
  
- <span data-ttu-id="70ba4-131">RFC 1287, Towards the Future Internet Architecture.</span><span class="sxs-lookup"><span data-stu-id="70ba4-131">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
- <span data-ttu-id="70ba4-132">RFC 1454, Comparison of Proposals for Next Version of IP.</span><span class="sxs-lookup"><span data-stu-id="70ba4-132">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
- <span data-ttu-id="70ba4-133">RFC 2373, IP Version 6 Addressing Architecture.</span><span class="sxs-lookup"><span data-stu-id="70ba4-133">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
- <span data-ttu-id="70ba4-134">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span><span class="sxs-lookup"><span data-stu-id="70ba4-134">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="70ba4-135">또한 [IPv6(IP 버전 6)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498(v=ws.10))에서 IPv6 관련 정보를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70ba4-135">You can also find IPv6-related information on the [IP Version 6 (IPv6)](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70ba4-136">참조</span><span class="sxs-lookup"><span data-stu-id="70ba4-136">See also</span></span>

- <span data-ttu-id="70ba4-137">[IPv6 소켓 샘플](/previous-versions/dotnet/netframework-3.0/ms180981(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="70ba4-137">[IPv6 Sockets Sample](/previous-versions/dotnet/netframework-3.0/ms180981(v=vs.85))</span></span>
- [<span data-ttu-id="70ba4-138">네트워크 프로그래밍 샘플</span><span class="sxs-lookup"><span data-stu-id="70ba4-138">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="70ba4-139">소켓</span><span class="sxs-lookup"><span data-stu-id="70ba4-139">Sockets</span></span>](sockets.md)
