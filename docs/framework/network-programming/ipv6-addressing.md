---
title: IPv6 주소 지정
description: 텍스트 표현 및 주소 유형을 포함하여 IPv6(인터넷 프로토콜 버전 6) 주소에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- Internet Protocol version 6, addresses in
- Neighbor Discovery
- IPv6, enabling
- IPv6, mobility and
- Internet Protocol version 6, anycast addresses
- IPv6, Neighbor Discovery
- Internet Protocol version 6, auto-configuring
- Internet Protocol version 6, enabling
- IPv6, unicast addresses
- IPv6, auto-configuring
- Internet Protocol version 6, routing
- IPv6, RFC documents
- IPv6, routing
- Internet Protocol version 6, disabling
- Internet Protocol version 6, unicast addresses
- IPv6, multicast addresses
- Internet Protocol version 6, mobility and
- Internet Protocol version 6, RFC documents
- Internet Protocol version 6, Neighbor Discovery
- IPv6, anycast addresses
- Internet Protocol version 6, multicast addresses
- IPv6, addresses in
- IPv6, disabling
ms.assetid: 20a104ae-1649-4649-a005-531a5cf74c93
ms.openlocfilehash: fbf68cb5f40450c2f9ecf4900801ee55e326fcb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502342"
---
# <a name="ipv6-addressing"></a><span data-ttu-id="2fec0-103">IPv6 주소 지정</span><span class="sxs-lookup"><span data-stu-id="2fec0-103">IPv6 Addressing</span></span>

<span data-ttu-id="2fec0-104">IPv6(인터넷 프로토콜 버전 6)에서 주소의 길이는 128비트입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-104">In the Internet Protocol version 6 (IPv6), addresses are 128 bits long.</span></span> <span data-ttu-id="2fec0-105">주소 공간이 이렇게 큰 하나의 이유는 사용 가능한 주소를 인터넷 토폴로지를 반영하는 라우팅 도메인 계층 구조로 세분화하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-105">One reason for such a large address space is to subdivide the available addresses into a hierarchy of routing domains that reflect the Internet's topology.</span></span> <span data-ttu-id="2fec0-106">또 다른 이유는 디바이스를 네트워크에 연결하는 네트워크 어댑터(또는 인터페이스)의 주소를 매핑하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-106">Another reason is to map the addresses of network adapters (or interfaces) that connect devices to the network.</span></span> <span data-ttu-id="2fec0-107">IPv6은 최하위 수준인 네트워크 인터페이스 수준에서 주소를 확인하는 고유한 기능과 자동 구성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-107">IPv6 features an inherent capability to resolve addresses at their lowest level, which is at the network interface level, and also has auto-configuration capabilities.</span></span>

## <a name="text-representation"></a><span data-ttu-id="2fec0-108">텍스트 표현</span><span class="sxs-lookup"><span data-stu-id="2fec0-108">Text Representation</span></span>

<span data-ttu-id="2fec0-109">IPv6 주소를 텍스트 문자열로 표현하는 데 사용되는 세 가지 기존 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-109">The following are the three conventional forms used to represent the IPv6 addresses as text strings:</span></span>

- <span data-ttu-id="2fec0-110">**콜론-16진수 형식**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-110">**Colon-hexadecimal form**.</span></span> <span data-ttu-id="2fec0-111">권장되는 형식인 n:n:n:n:n:n:n:n입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-111">This is the preferred form n:n:n:n:n:n:n:n.</span></span> <span data-ttu-id="2fec0-112">각 n은 주소를 구성하는 8개의 16비트 요소 중 하나에 대한 16진수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-112">Each n represents the hexadecimal value of one of the eight 16-bit elements of the address.</span></span> <span data-ttu-id="2fec0-113">예를 들어 `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2fec0-113">For example: `3FFE:FFFF:7654:FEDA:1245:BA98:3210:4562`.</span></span>

- <span data-ttu-id="2fec0-114">**압축된 형식**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-114">**Compressed form**.</span></span> <span data-ttu-id="2fec0-115">주소 길이 때문에 일반적으로 0으로 구성된 긴 문자열이 있는 주소를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-115">Due to the address length, it is common to have addresses containing a long string of zeros.</span></span> <span data-ttu-id="2fec0-116">이러한 주소 작성을 간소화하려면 0 블록의 단일 연속 시퀀스를 이중 콜론 기호(::)로 표현하는 압축된 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-116">To simplify writing these addresses, use the compressed form, in which a single contiguous sequence of 0 blocks are represented by a double-colon symbol (::).</span></span> <span data-ttu-id="2fec0-117">이 기호는 주소에서 한 번만 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-117">This symbol can appear only once in an address.</span></span> <span data-ttu-id="2fec0-118">예를 들어 압축된 형식의 멀티캐스트 주소 `FFED:0:0:0:0:BA98:3210:4562`는 `FFED::BA98:3210:4562`입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-118">For example, the multicast address `FFED:0:0:0:0:BA98:3210:4562` in compressed form is `FFED::BA98:3210:4562`.</span></span> <span data-ttu-id="2fec0-119">압축된 형식의 유니캐스트 주소 `3FFE:FFFF:0:0:8:800:20C4:0`은 `3FFE:FFFF::8:800:20C4:0`입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-119">The unicast address `3FFE:FFFF:0:0:8:800:20C4:0` in compressed form is `3FFE:FFFF::8:800:20C4:0`.</span></span> <span data-ttu-id="2fec0-120">압축된 형식의 루프백 주소 `0:0:0:0:0:0:0:1`은 `::`1입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-120">The loopback address `0:0:0:0:0:0:0:1` in compressed form is `::`1.</span></span> <span data-ttu-id="2fec0-121">압축된 형식의 지정되지 않은 주소 `0:0:0:0:0:0:0:0`은 `::`입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-121">The unspecified address `0:0:0:0:0:0:0:0` in compressed form is `::`.</span></span>

- <span data-ttu-id="2fec0-122">**혼합된 형식**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-122">**Mixed form**.</span></span> <span data-ttu-id="2fec0-123">이 형식은 IPv4 주소와 IPv6 주소를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-123">This form combines IPv4 and IPv6 addresses.</span></span> <span data-ttu-id="2fec0-124">이 경우 주소 형식은 n:n:n:n:n:n:d.d.d.d입니다. 여기서 각 n은 6개의 IPv6 높은 순서 16비트 주소 요소의 16진수 값을 나타내고 각 d는 IPv4 주소의 10진수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-124">In this case, the address format is n:n:n:n:n:n:d.d.d.d, where each n represents the hexadecimal values of the six IPv6 high-order 16-bit address elements, and each d represents the decimal value of an IPv4 address.</span></span>

## <a name="address-types"></a><span data-ttu-id="2fec0-125">주소 형식</span><span class="sxs-lookup"><span data-stu-id="2fec0-125">Address Types</span></span>

<span data-ttu-id="2fec0-126">주소의 선행 비트는 특정 IPv6 주소 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-126">The leading bits in the address define the specific IPv6 address type.</span></span> <span data-ttu-id="2fec0-127">이러한 선행 비트가 포함된 가변 길이 필드를 FP(Format Prefix)라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-127">The variable-length field containing these leading bits is called a Format Prefix (FP).</span></span>

<span data-ttu-id="2fec0-128">IPv6 유니캐스트 주소는 두 부분으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-128">An IPv6 unicast address is divided into two parts.</span></span> <span data-ttu-id="2fec0-129">첫 번째 부분에는 주소 접두사가 포함되고 두 번째 부분에는 인터페이스 식별자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-129">The first part contains the address prefix, and the second part contains the interface identifier.</span></span> <span data-ttu-id="2fec0-130">IPv6 주소/접두사 조합을 표시하는 간결한 방법은 다음과 같습니다. ipv6-address/prefix-length.</span><span class="sxs-lookup"><span data-stu-id="2fec0-130">A concise way to express an IPv6 address/prefix combination is as follows: ipv6-address/prefix-length.</span></span>

<span data-ttu-id="2fec0-131">64비트 접두사가 포함된 주소의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-131">The following is an example of an address with a 64-bit prefix.</span></span>

<span data-ttu-id="2fec0-132">`3FFE:FFFF:0:CD30:0:0:0:0/64`.</span><span class="sxs-lookup"><span data-stu-id="2fec0-132">`3FFE:FFFF:0:CD30:0:0:0:0/64`.</span></span>

<span data-ttu-id="2fec0-133">이 예의 접두사는 `3FFE:FFFF:0:CD30`입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-133">The prefix in this example is `3FFE:FFFF:0:CD30`.</span></span> <span data-ttu-id="2fec0-134">주소는 압축된 형식으로 기록될 수도 있습니다(예: `3FFE:FFFF:0:CD30::/64`).</span><span class="sxs-lookup"><span data-stu-id="2fec0-134">The address can also be written in a compressed form, as `3FFE:FFFF:0:CD30::/64`.</span></span>

<span data-ttu-id="2fec0-135">IPv6은 다음 주소 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-135">IPv6 defines the following address types:</span></span>

- <span data-ttu-id="2fec0-136">**유니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-136">**Unicast address**.</span></span> <span data-ttu-id="2fec0-137">단일 인터페이스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-137">An identifier for a single interface.</span></span> <span data-ttu-id="2fec0-138">이 주소에 전송된 패킷은 식별된 인터페이스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-138">A packet sent to this address is delivered to the identified interface.</span></span> <span data-ttu-id="2fec0-139">유니캐스트 주소는 높은 순서 8진수 값으로 멀티캐스트 주소와 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-139">The unicast addresses are distinguished from the multicast addresses by the value of the high-order octet.</span></span> <span data-ttu-id="2fec0-140">멀티캐스트 주소의 높은 순서 8진수에는 16진수 값 FF가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-140">The multicast addresses' high-order octet has the hexadecimal value of FF.</span></span> <span data-ttu-id="2fec0-141">이 8진수 식별자의 다른 값은 유니캐스트 주소를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-141">Any other value for this octet identifies a unicast address.</span></span> <span data-ttu-id="2fec0-142">다양한 형식의 유니캐스트 주소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-142">The following are different types of unicast addresses:</span></span>

  - <span data-ttu-id="2fec0-143">**링크-로컬 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-143">**Link-local addresses**.</span></span> <span data-ttu-id="2fec0-144">이러한 주소는 단일 링크에서 사용되고 다음 형식을 사용합니다. FE80::*InterfaceID*.</span><span class="sxs-lookup"><span data-stu-id="2fec0-144">These addresses are used on a single link and have the following format: FE80::*InterfaceID*.</span></span> <span data-ttu-id="2fec0-145">링크-로컬 주소는 자동 주소 구성, 네트워크 환경 검색을 위해 또는 라우터가 없는 경우 링크에서 노드 간에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-145">Link-local addresses are used between nodes on a link for auto-address configuration, neighbor discovery, or when no routers are present.</span></span> <span data-ttu-id="2fec0-146">링크-로컬 주소는 주로 시작 시 사용되고 시스템이 더 큰 범위의 주소를 아직 획득하지 못한 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-146">A link-local address is used primarily at startup and when the system has not yet acquired addresses of larger scope.</span></span>

  - <span data-ttu-id="2fec0-147">**사이트-로컬 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-147">**Site-local addresses**.</span></span> <span data-ttu-id="2fec0-148">이러한 주소는 단일 사이트에서 사용되고 다음 형식을 사용합니다. FEC0::*SubnetID*:*InterfaceID*.</span><span class="sxs-lookup"><span data-stu-id="2fec0-148">These addresses are used on a single site and have the following format: FEC0::*SubnetID*:*InterfaceID*.</span></span> <span data-ttu-id="2fec0-149">사이트-로컬 주소는 전역 접두사를 사용할 필요 없이 사이트 내에서 주소 지정에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-149">The site-local addresses are used for addressing inside a site without the need for a global prefix.</span></span>

  - <span data-ttu-id="2fec0-150">**전역 IPv6 유니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-150">**Global IPv6 unicast addresses**.</span></span> <span data-ttu-id="2fec0-151">이러한 주소는 인터넷을 통해 사용할 수 있으며 다음 형식을 사용합니다. 010(FP, 3비트) TLA ID(13비트) Reserved(8비트) NLA ID(24비트) SLA ID(16비트) *InterfaceID*(64비트).</span><span class="sxs-lookup"><span data-stu-id="2fec0-151">These addresses can be used across the Internet and have the following format: 010(FP, 3 bits) TLA ID (13 bits) Reserved (8 bits) NLA ID (24 bits) SLA ID (16 bits) *InterfaceID* (64 bits).</span></span>

- <span data-ttu-id="2fec0-152">**멀티캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-152">**Multicast address**.</span></span> <span data-ttu-id="2fec0-153">인터페이스 집합의 식별자입니다(일반적으로 서로 다른 노드에 속함).</span><span class="sxs-lookup"><span data-stu-id="2fec0-153">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="2fec0-154">이 주소에 전송된 패킷은 주소로 식별되는 모든 인터페이스에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-154">A packet sent to this address is delivered to all the interfaces identified by the address.</span></span> <span data-ttu-id="2fec0-155">멀티캐스트 주소 형식이 IPv4 브로드캐스트 주소보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-155">The multicast address types supersede the IPv4 broadcast addresses.</span></span>

- <span data-ttu-id="2fec0-156">**애니캐스트 주소**.</span><span class="sxs-lookup"><span data-stu-id="2fec0-156">**Anycast address**.</span></span> <span data-ttu-id="2fec0-157">인터페이스 집합의 식별자입니다(일반적으로 서로 다른 노드에 속함).</span><span class="sxs-lookup"><span data-stu-id="2fec0-157">An identifier for a set of interfaces (typically belonging to different nodes).</span></span> <span data-ttu-id="2fec0-158">이 주소에 전송된 패킷은 주소로 식별되는 하나의 인터페이스에만 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-158">A packet sent to this address is delivered to only one interface identified by the address.</span></span> <span data-ttu-id="2fec0-159">이 주소는 라우팅 메트릭으로 식별되는 가장 가까운 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-159">This is the nearest interface as identified by routing metrics.</span></span> <span data-ttu-id="2fec0-160">애니캐스트 주소는 유니캐스트 주소 공간에서 가져오고 구문상 구별할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-160">Anycast addresses are taken from the unicast address space and are not syntactically distinguishable.</span></span> <span data-ttu-id="2fec0-161">주소 지정된 인터페이스는 유니캐스트 주소와 애니캐스트 주소를 구성 함수로 구별합니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-161">The addressed interface performs the distinction between unicast and anycast addresses as a function of its configuration.</span></span>

<span data-ttu-id="2fec0-162">일반적으로 노드에는 항상 링크-로컬 주소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-162">In general, a node always has a link-local address.</span></span> <span data-ttu-id="2fec0-163">사이트-로컬 주소 및 하나 이상의 전역 주소가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fec0-163">It might have a site-local address and one or more global addresses.</span></span>

## <a name="see-also"></a><span data-ttu-id="2fec0-164">참조</span><span class="sxs-lookup"><span data-stu-id="2fec0-164">See also</span></span>

- [<span data-ttu-id="2fec0-165">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="2fec0-165">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="2fec0-166">소켓</span><span class="sxs-lookup"><span data-stu-id="2fec0-166">Sockets</span></span>](sockets.md)
