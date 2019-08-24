---
title: <defaultHttpCachePolicy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
ms.openlocfilehash: 1dd31884a072d16ed004c0b49be61e8cee399787
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664144"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="f5547-102">\<defaultHttpCachePolicy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="f5547-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="f5547-103">HTTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="f5547-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f5547-104">\<configuration></span></span>  
<span data-ttu-id="f5547-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="f5547-105">\<system.net></span></span>  
<span data-ttu-id="f5547-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="f5547-106">\<requestCaching></span></span>  
<span data-ttu-id="f5547-107">\<defaultHttpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="f5547-107">\<defaultHttpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5547-108">구문</span><span class="sxs-lookup"><span data-stu-id="f5547-108">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5547-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f5547-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f5547-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5547-111">특성</span><span class="sxs-lookup"><span data-stu-id="f5547-111">Attributes</span></span>  
  
|<span data-ttu-id="f5547-112">특성</span><span class="sxs-lookup"><span data-stu-id="f5547-112">Attribute</span></span>|<span data-ttu-id="f5547-113">Description</span><span class="sxs-lookup"><span data-stu-id="f5547-113">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="f5547-114">캐시 된 개체가 만료 된 것으로 표시 되기 전의 최대 시간 간격을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-114">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="f5547-115">캐시 된 개체가 만료 된 것으로 표시 되기 전까지 계산 된 새로 고침 시간 이후의 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-115">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="f5547-116">캐시 된 개체가 최신 상태로 간주 되는 최소 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-116">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="f5547-117">캐싱 정책이 자동 인지 여부 또는 캐시가 바이패스 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-117">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="f5547-118">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-118">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5547-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f5547-119">Child Elements</span></span>  
 <span data-ttu-id="f5547-120">없음</span><span class="sxs-lookup"><span data-stu-id="f5547-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5547-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f5547-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f5547-122">요소</span><span class="sxs-lookup"><span data-stu-id="f5547-122">Element</span></span>|<span data-ttu-id="f5547-123">Description</span><span class="sxs-lookup"><span data-stu-id="f5547-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5547-124">requestCaching</span><span class="sxs-lookup"><span data-stu-id="f5547-124">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="f5547-125">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-125">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5547-126">설명</span><span class="sxs-lookup"><span data-stu-id="f5547-126">Remarks</span></span>  
 <span data-ttu-id="f5547-127">`policyLevel` 특성의 값 `BypassCache` 이 또는 `Default`입니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-127">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="f5547-128">, 및 요소의 값은 형식이 d 인 명시적 시간 간격입니다. `maximumAge` `maximumStale` `minimumFresh`  *hh*:*mm*:*ss* (일, 시간, 분 및 초) 또는 상수 `minValue` 또는 `maxValue`(해당 하는 경우).</span><span class="sxs-lookup"><span data-stu-id="f5547-128">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f5547-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f5547-129">Configuration Files</span></span>  
 <span data-ttu-id="f5547-130">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-130">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5547-131">예제</span><span class="sxs-lookup"><span data-stu-id="f5547-131">Example</span></span>  
 <span data-ttu-id="f5547-132">다음 예제에서는 최소 새로 고침 시간을 6 시간으로 지정 하 고, 최대 기간을 2 일로 지정 하 고, 최대 만료 시간을 4 시간으로 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5547-132">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5547-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5547-133">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="f5547-134">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f5547-134">Network Settings Schema</span></span>](index.md)
