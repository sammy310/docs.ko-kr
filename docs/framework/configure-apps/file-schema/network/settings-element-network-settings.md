---
title: <settings> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: a1733803d1f5a5bf64aeb69d0360cef3de3b3a69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674417"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="b0d2c-102">\<설정 > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b0d2c-102">\<settings> Element (Network Settings)</span></span>
<span data-ttu-id="b0d2c-103"><xref:System.Net?displayProperty=nameWithType> 네임스페이스에 대한 기본 네트워크 옵션을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="b0d2c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0d2c-104">\<configuration></span></span>  
<span data-ttu-id="b0d2c-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="b0d2c-105">\<system.net></span></span>  
<span data-ttu-id="b0d2c-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="b0d2c-106">\<settings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0d2c-107">구문</span><span class="sxs-lookup"><span data-stu-id="b0d2c-107">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0d2c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b0d2c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b0d2c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0d2c-110">특성</span><span class="sxs-lookup"><span data-stu-id="b0d2c-110">Attributes</span></span>  
 <span data-ttu-id="b0d2c-111">없음</span><span class="sxs-lookup"><span data-stu-id="b0d2c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0d2c-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b0d2c-112">Child Elements</span></span>  
  
|<span data-ttu-id="b0d2c-113">요소</span><span class="sxs-lookup"><span data-stu-id="b0d2c-113">Element</span></span>|<span data-ttu-id="b0d2c-114">설명</span><span class="sxs-lookup"><span data-stu-id="b0d2c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0d2c-115">httpListener</span><span class="sxs-lookup"><span data-stu-id="b0d2c-115">httpListener</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httplistener-element-network-settings.md)|<span data-ttu-id="b0d2c-116">매개 변수에서 사용 하는 사용자 지정을 <xref:System.Net.HttpListener> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-116">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="b0d2c-117">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="b0d2c-117">httpWebRequest</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)|<span data-ttu-id="b0d2c-118">웹 요청 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-118">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="b0d2c-119">ipv6</span><span class="sxs-lookup"><span data-stu-id="b0d2c-119">ipv6</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)|<span data-ttu-id="b0d2c-120">인터넷 프로토콜 버전 6(ipv6)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-120">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="b0d2c-121">\<performanceCounter > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b0d2c-121">\<performanceCounter> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/performancecounter-element-network-settings.md)|<span data-ttu-id="b0d2c-122">네트워크 성능 카운터를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-122">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="b0d2c-123">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="b0d2c-123">servicePointManager</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/servicepointmanager-element-network-settings.md)|<span data-ttu-id="b0d2c-124">네트워크 리소스에 대 한 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-124">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="b0d2c-125">socket</span><span class="sxs-lookup"><span data-stu-id="b0d2c-125">socket</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/socket-element-network-settings.md)|<span data-ttu-id="b0d2c-126">소켓 작업 완료 포트를 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-126">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="b0d2c-127">\<webProxyScript > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="b0d2c-127">\<webProxyScript> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webproxyscript-element-network-settings.md)|<span data-ttu-id="b0d2c-128">웹 프록시 검색에 사용 되는 스크립트의 특성을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-128">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0d2c-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b0d2c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b0d2c-130">요소</span><span class="sxs-lookup"><span data-stu-id="b0d2c-130">Element</span></span>|<span data-ttu-id="b0d2c-131">설명</span><span class="sxs-lookup"><span data-stu-id="b0d2c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0d2c-132">system.net</span><span class="sxs-lookup"><span data-stu-id="b0d2c-132">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="b0d2c-133">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-133">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0d2c-134">설명</span><span class="sxs-lookup"><span data-stu-id="b0d2c-134">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b0d2c-135">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b0d2c-135">Configuration Files</span></span>  
 <span data-ttu-id="b0d2c-136">이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d2c-136">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d2c-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="b0d2c-137">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="b0d2c-138">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b0d2c-138">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
