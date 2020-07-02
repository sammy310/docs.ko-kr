---
title: IPv6 사용 및 사용 안 함
description: 다음 구성 단계에 따라 컴퓨터 또는 애플리케이션용 구성 파일을 수정하는 등 IPv6 프로토콜을 사용하도록 설정합니다.
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 7729647b09df20a98d5d639a641cb0a31f557330
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502615"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="d3852-103">IPv6 사용 및 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d3852-103">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="d3852-104">IPv6 프로토콜을 사용하려면 IPv6을 지원하는 운영 체제 버전을 실행 중인지 확인하고 운영 체제와 네트워킹 클래스가 제대로 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-104">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="d3852-105">구성 단계</span><span class="sxs-lookup"><span data-stu-id="d3852-105">Configuration Steps</span></span>  
 <span data-ttu-id="d3852-106">다음 표에는 다양한 구성이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-106">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="d3852-107">운영 체제 IPv6 사용?</span><span class="sxs-lookup"><span data-stu-id="d3852-107">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="d3852-108">네트워킹 클래스 IPv6 사용?</span><span class="sxs-lookup"><span data-stu-id="d3852-108">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="d3852-109">설명</span><span class="sxs-lookup"><span data-stu-id="d3852-109">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="d3852-110">아니요</span><span class="sxs-lookup"><span data-stu-id="d3852-110">No</span></span>|<span data-ttu-id="d3852-111">아니요</span><span class="sxs-lookup"><span data-stu-id="d3852-111">No</span></span>|<span data-ttu-id="d3852-112">IPv6 주소를 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-112">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="d3852-113">아니요</span><span class="sxs-lookup"><span data-stu-id="d3852-113">No</span></span>|<span data-ttu-id="d3852-114">예</span><span class="sxs-lookup"><span data-stu-id="d3852-114">Yes</span></span>|<span data-ttu-id="d3852-115">IPv6 주소를 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-115">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="d3852-116">예</span><span class="sxs-lookup"><span data-stu-id="d3852-116">Yes</span></span>|<span data-ttu-id="d3852-117">아니요</span><span class="sxs-lookup"><span data-stu-id="d3852-117">No</span></span>|<span data-ttu-id="d3852-118">IPv6 주소를 구문 분석하고 사용되지 않음으로 표시된 이름 확인 메서드로 IPv6 주소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-118">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="d3852-119">예</span><span class="sxs-lookup"><span data-stu-id="d3852-119">Yes</span></span>|<span data-ttu-id="d3852-120">예</span><span class="sxs-lookup"><span data-stu-id="d3852-120">Yes</span></span>|<span data-ttu-id="d3852-121">사용되지 않음으로 표시된 항목이 포함된 모든 메서드를 사용하여 IPv6 주소를 구문 분석 및 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-121">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="d3852-122">System.Net 네임스페이스의 모든 클래스에 대한 IPv6 지원을 사용하도록 설정하려면 컴퓨터 구성 파일 또는 애플리케이션 구성 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-122">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="d3852-123">애플리케이션 구성 파일이 컴퓨터 구성 파일보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-123">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="d3852-124">컴퓨터 구성 파일 *machine.config*를 수정하여 Ipv6 지원을 활성화하는 방법에 대한 예는 [방법: Ipv6 지원을 사용하도록 컴퓨터 구성 파일 수정](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3852-124">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="d3852-125">또한 운영 체제에 대한 IPv6 지원이 사용하도록 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-125">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="d3852-126">.NET Framework의 경우 구성 파일에 구성 스위치가 다음과 같이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-126">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="d3852-127">.NET Framework 버전 1.1 이하의 경우 **ipv6 enabled** 구성 스위치 값은 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버가 IPv6 주소를 반환하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-127">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="d3852-128">.NET Framework 버전 2.0 이상의 경우 Windows에서 IPv6을 지원하면 <xref:System.Net.Dns?displayProperty=nameWithType> 클래스의 멤버(예: <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> 메서드)는 한 가지 제한과 함께 IPv6 주소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-128">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="d3852-129">DNS <xref:System.Net.Dns?displayProperty=nameWithType>의 사용되지 않는 멤버(예: <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> 메서드)는 구성 파일에서 ipv6 enabled 설정에 대한 값을 읽고 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="d3852-129">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3852-130">참조</span><span class="sxs-lookup"><span data-stu-id="d3852-130">See also</span></span>

- [<span data-ttu-id="d3852-131">인터넷 프로토콜 버전 6</span><span class="sxs-lookup"><span data-stu-id="d3852-131">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="d3852-132">소켓</span><span class="sxs-lookup"><span data-stu-id="d3852-132">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="d3852-133">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d3852-133">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="d3852-134">\<ipv6> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="d3852-134">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
