---
title: <requestCaching> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: afee69eb894518b1c88483e34a1d64d452019244
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74802133"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="1555e-102">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="1555e-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="1555e-103">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-103">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="1555e-104">구문</span><span class="sxs-lookup"><span data-stu-id="1555e-104">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh:mm:ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1555e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1555e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1555e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1555e-107">특성</span><span class="sxs-lookup"><span data-stu-id="1555e-107">Attributes</span></span>  
  
|<span data-ttu-id="1555e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1555e-108">Attribute</span></span>|<span data-ttu-id="1555e-109">Description</span><span class="sxs-lookup"><span data-stu-id="1555e-109">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="1555e-110">캐시에서 다른 사용자의 정보를 격리 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-110">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="1555e-111">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-111">The default value is `true`.</span></span> <span data-ttu-id="1555e-112">`false`중간 계층 응용 프로그램의 경우이 값은 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-112">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="1555e-113">모든 웹 응답에 대해 캐싱이 사용 되지 않도록 지정 하 고 프로그래밍 방식으로 재정의할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-113">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="1555e-114"><xref:System.Net.Cache.RequestCacheLevel> 열거형에 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-114">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="1555e-115">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-115">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="1555e-116">콘텐츠가 만료 된 것으로 표시 되는 기본 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-116">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="1555e-117">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="1555e-117">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="1555e-118">값</span><span class="sxs-lookup"><span data-stu-id="1555e-118">Value</span></span>|<span data-ttu-id="1555e-119">Description</span><span class="sxs-lookup"><span data-stu-id="1555e-119">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="1555e-120">리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-120">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="1555e-121">서버에서 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-121">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="1555e-122">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-122">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="1555e-123">콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-123">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="1555e-124">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되며 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-124">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="1555e-125">서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-125">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="1555e-126">캐시 된 리소스가 있으면 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-126">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="1555e-127">리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-127">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="1555e-128">타임 스탬프가 서버의 리소스 타임 스탬프와 동일한 경우 캐시 된 리소스 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 표시 되며 캐시에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-128">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1555e-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1555e-129">Child Elements</span></span>  
  
|<span data-ttu-id="1555e-130">요소</span><span class="sxs-lookup"><span data-stu-id="1555e-130">Element</span></span>|<span data-ttu-id="1555e-131">Description</span><span class="sxs-lookup"><span data-stu-id="1555e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1555e-132">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="1555e-132">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="1555e-133">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-133">Optional element.</span></span><br /><br /> <span data-ttu-id="1555e-134">HTTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-134">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="1555e-135">\<defaultFtpCachePolicy>요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="1555e-135">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="1555e-136">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-136">Optional element.</span></span><br /><br /> <span data-ttu-id="1555e-137">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-137">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1555e-138">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1555e-138">Parent Elements</span></span>  
  
|<span data-ttu-id="1555e-139">요소</span><span class="sxs-lookup"><span data-stu-id="1555e-139">Element</span></span>|<span data-ttu-id="1555e-140">Description</span><span class="sxs-lookup"><span data-stu-id="1555e-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1555e-141">system.net</span><span class="sxs-lookup"><span data-stu-id="1555e-141">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="1555e-142">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-142">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1555e-143">예제</span><span class="sxs-lookup"><span data-stu-id="1555e-143">Example</span></span>  
 <span data-ttu-id="1555e-144">다음 예에서는 모든 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1555e-144">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1555e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1555e-145">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="1555e-146">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="1555e-146">Network Settings Schema</span></span>](index.md)
