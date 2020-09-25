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
ms.openlocfilehash: 4120c57fbb65da1c124414cbe9cfba7ae64388f8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190321"
---
# <a name="defaulthttpcachepolicy-element-network-settings"></a><span data-ttu-id="87e74-102">\<defaultHttpCachePolicy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="87e74-102">\<defaultHttpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="87e74-103">HTTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-103">Describes whether HTTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultHttpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="87e74-104">구문</span><span class="sxs-lookup"><span data-stu-id="87e74-104">Syntax</span></span>  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87e74-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="87e74-105">Attributes and Elements</span></span>  

 <span data-ttu-id="87e74-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87e74-107">특성</span><span class="sxs-lookup"><span data-stu-id="87e74-107">Attributes</span></span>  
  
|<span data-ttu-id="87e74-108">attribute</span><span class="sxs-lookup"><span data-stu-id="87e74-108">Attribute</span></span>|<span data-ttu-id="87e74-109">설명</span><span class="sxs-lookup"><span data-stu-id="87e74-109">Description</span></span>|  
|---------------|-----------------|  
|`maximumAge`|<span data-ttu-id="87e74-110">캐시 된 개체가 만료 된 것으로 표시 되기 전의 최대 시간 간격을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-110">Specifies the maximum time interval before a cached object is marked as expired.</span></span>|  
|`maximumStale`|<span data-ttu-id="87e74-111">캐시 된 개체가 만료 된 것으로 표시 되기 전까지 계산 된 새로 고침 시간 이후의 최대 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-111">Specifies the maximum time past the computed freshness time before a cached object is marked as expired.</span></span>|  
|`minimumFresh`|<span data-ttu-id="87e74-112">캐시 된 개체가 최신 상태로 간주 되는 최소 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-112">Specifies the minimum time for a cached object to be considered fresh.</span></span>|  
|`policyLevel`|<span data-ttu-id="87e74-113">캐싱 정책이 자동 인지 여부 또는 캐시가 바이패스 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-113">Specifies whether the caching policy is automatic, or whether the cache is bypassed.</span></span> <span data-ttu-id="87e74-114">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-114">The default value is `BypassCache`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87e74-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="87e74-115">Child Elements</span></span>  

 <span data-ttu-id="87e74-116">없음</span><span class="sxs-lookup"><span data-stu-id="87e74-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87e74-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="87e74-117">Parent Elements</span></span>  
  
|<span data-ttu-id="87e74-118">요소</span><span class="sxs-lookup"><span data-stu-id="87e74-118">Element</span></span>|<span data-ttu-id="87e74-119">설명</span><span class="sxs-lookup"><span data-stu-id="87e74-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87e74-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="87e74-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="87e74-121">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-121">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87e74-122">설명</span><span class="sxs-lookup"><span data-stu-id="87e74-122">Remarks</span></span>  

 <span data-ttu-id="87e74-123">특성의 값 `policyLevel` 이 `BypassCache` 또는 `Default` 입니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-123">The value for the `policyLevel` attribute is either `BypassCache` or `Default`.</span></span>  
  
 <span data-ttu-id="87e74-124">`maximumAge`, `maximumStale` 및 `minimumFresh` 요소의 값은 형식이 *d*인 명시적 시간 간격입니다.\* hh*:*mm*:*ss\* (일, 시간, 분 및 초) 또는 상수 `minValue` 또는 (해당 하는 경우) `maxValue` .</span><span class="sxs-lookup"><span data-stu-id="87e74-124">Values for the `maximumAge`, `maximumStale`, and `minimumFresh` elements are either an explicit time interval with a format of *d*.*hh*:*mm*:*ss* (days, hours, minutes, and seconds), or the constants `minValue` or `maxValue`, as appropriate.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="87e74-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="87e74-125">Configuration Files</span></span>  

 <span data-ttu-id="87e74-126">이 요소는 애플리케이션 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="87e74-127">예제</span><span class="sxs-lookup"><span data-stu-id="87e74-127">Example</span></span>  

 <span data-ttu-id="87e74-128">다음 예제에서는 최소 새로 고침 시간을 6 시간으로 지정 하 고, 최대 기간을 2 일로 지정 하 고, 최대 만료 시간을 4 시간으로 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87e74-128">The following example shows how to specify a minimum fresh time of six hours, a maximum age time of two days, and a maximum stale time of four hours.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87e74-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87e74-129">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="87e74-130">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="87e74-130">Network Settings Schema</span></span>](index.md)
