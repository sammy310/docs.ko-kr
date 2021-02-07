---
description: '다음에 대 한 자세한 정보: <requestCaching> 요소 (네트워크 설정)'
title: <requestCaching> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: d09da8ad7a38ac363aaa740cca4de25e33fa8c56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698559"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="52653-103">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="52653-103">\<requestCaching> Element (Network Settings)</span></span>

<span data-ttu-id="52653-104">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-104">Controls the caching mechanism for network requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requestCaching>**  
  
## <a name="syntax"></a><span data-ttu-id="52653-105">구문</span><span class="sxs-lookup"><span data-stu-id="52653-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52653-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52653-106">Attributes and Elements</span></span>  

 <span data-ttu-id="52653-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52653-108">특성</span><span class="sxs-lookup"><span data-stu-id="52653-108">Attributes</span></span>  
  
|<span data-ttu-id="52653-109">attribute</span><span class="sxs-lookup"><span data-stu-id="52653-109">Attribute</span></span>|<span data-ttu-id="52653-110">설명</span><span class="sxs-lookup"><span data-stu-id="52653-110">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="52653-111">캐시에서 다른 사용자의 정보를 격리 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-111">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="52653-112">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="52653-112">The default value is `true`.</span></span> <span data-ttu-id="52653-113">`false`중간 계층 응용 프로그램의 경우이 값은 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-113">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="52653-114">모든 웹 응답에 대해 캐싱이 사용 되지 않도록 지정 하 고 프로그래밍 방식으로 재정의할 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-114">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="52653-115"><xref:System.Net.Cache.RequestCacheLevel> 열거형에 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="52653-115">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="52653-116">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="52653-116">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="52653-117">콘텐츠가 만료 된 것으로 표시 되는 기본 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-117">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="52653-118">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="52653-118">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="52653-119">값</span><span class="sxs-lookup"><span data-stu-id="52653-119">Value</span></span>|<span data-ttu-id="52653-120">설명</span><span class="sxs-lookup"><span data-stu-id="52653-120">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="52653-121">리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-121">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="52653-122">서버에서 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-122">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="52653-123">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-123">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="52653-124">콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52653-124">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="52653-125">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되며 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52653-125">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="52653-126">서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-126">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="52653-127">캐시 된 리소스가 있으면 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52653-127">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="52653-128">리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52653-128">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="52653-129">타임 스탬프가 서버의 리소스 타임 스탬프와 동일한 경우 캐시 된 리소스 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 표시 되며 캐시에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52653-129">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52653-130">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52653-130">Child Elements</span></span>  
  
|<span data-ttu-id="52653-131">요소</span><span class="sxs-lookup"><span data-stu-id="52653-131">Element</span></span>|<span data-ttu-id="52653-132">설명</span><span class="sxs-lookup"><span data-stu-id="52653-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52653-133">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="52653-133">defaultHttpCachePolicy</span></span>](defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="52653-134">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52653-134">Optional element.</span></span><br /><br /> <span data-ttu-id="52653-135">HTTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-135">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="52653-136">\<defaultFtpCachePolicy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="52653-136">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="52653-137">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="52653-137">Optional element.</span></span><br /><br /> <span data-ttu-id="52653-138">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-138">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52653-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52653-139">Parent Elements</span></span>  
  
|<span data-ttu-id="52653-140">요소</span><span class="sxs-lookup"><span data-stu-id="52653-140">Element</span></span>|<span data-ttu-id="52653-141">설명</span><span class="sxs-lookup"><span data-stu-id="52653-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52653-142">system.net</span><span class="sxs-lookup"><span data-stu-id="52653-142">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="52653-143">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="52653-143">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="52653-144">예제</span><span class="sxs-lookup"><span data-stu-id="52653-144">Example</span></span>  

 <span data-ttu-id="52653-145">다음 예에서는 모든 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="52653-145">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="52653-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52653-146">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="52653-147">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="52653-147">Network Settings Schema</span></span>](index.md)
