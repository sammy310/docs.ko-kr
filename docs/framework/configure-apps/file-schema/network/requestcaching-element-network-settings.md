---
title: <requestCaching> 요소 (네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: af290e4b9258a08425a15e297ff538502edea916
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164855"
---
# <a name="requestcaching-element-network-settings"></a><span data-ttu-id="6ca3a-102">\<requestCaching > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6ca3a-102">\<requestCaching> Element (Network Settings)</span></span>
<span data-ttu-id="6ca3a-103">네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-103">Controls the caching mechanism for network requests.</span></span>  
  
 <span data-ttu-id="6ca3a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6ca3a-104">\<configuration></span></span>  
<span data-ttu-id="6ca3a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="6ca3a-105">\<system.net></span></span>  
<span data-ttu-id="6ca3a-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="6ca3a-106">\<requestCaching></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ca3a-107">구문</span><span class="sxs-lookup"><span data-stu-id="6ca3a-107">Syntax</span></span>  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ca3a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6ca3a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6ca3a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ca3a-110">특성</span><span class="sxs-lookup"><span data-stu-id="6ca3a-110">Attributes</span></span>  
  
|<span data-ttu-id="6ca3a-111">특성</span><span class="sxs-lookup"><span data-stu-id="6ca3a-111">Attribute</span></span>|<span data-ttu-id="6ca3a-112">설명</span><span class="sxs-lookup"><span data-stu-id="6ca3a-112">Description</span></span>|  
|---------------|-----------------|  
|`isPrivateCache`|<span data-ttu-id="6ca3a-113">캐시에 서로 다른 사용자의 정보 간에 격리 제공 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-113">Specifies whether the cache provides isolation between the information of different users.</span></span> <span data-ttu-id="6ca3a-114">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-114">The default value is `true`.</span></span> <span data-ttu-id="6ca3a-115">이 값은 이어야 `false` 중간 계층 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-115">This value should be `false` for middle tier applications.</span></span>|  
|`disableAllCaching`|<span data-ttu-id="6ca3a-116">모든 웹 응답의 경우 사용 하지 않으면 캐싱을 프로그래밍 방식으로 재정의할 수 없습니다 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-116">Specifies that caching is disabled for all Web responses, and cannot be overridden programmatically.</span></span>|  
|`defaultPolicyLevel`|<span data-ttu-id="6ca3a-117"><xref:System.Net.Cache.RequestCacheLevel> 열거형에 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-117">One of the values in the <xref:System.Net.Cache.RequestCacheLevel> enumeration.</span></span> <span data-ttu-id="6ca3a-118">기본값은 `BypassCache`입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-118">The default value is `BypassCache`.</span></span>|  
|`unspecifiedMaximumAge`|<span data-ttu-id="6ca3a-119">콘텐츠 만료 되기까지의 표시 기본 시간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-119">Specifies the default time after which content is marked as expired.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="6ca3a-120">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="6ca3a-120">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="6ca3a-121">값</span><span class="sxs-lookup"><span data-stu-id="6ca3a-121">Value</span></span>|<span data-ttu-id="6ca3a-122">설명</span><span class="sxs-lookup"><span data-stu-id="6ca3a-122">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="6ca3a-123">리소스 새로 고침, 콘텐츠 길이 정확 하 고, 이며 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-123">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="6ca3a-124">서버에서 리소스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-124">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="6ca3a-125">콘텐츠 길이가 있는지와 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-125">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="6ca3a-126">콘텐츠 길이 제공 하는 크기와 일치 항목; 경우 캐시 된 리소스를 반환 합니다. 그렇지 않은 경우 리소스 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-126">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="6ca3a-127">캐시 된 리소스의 타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스 캐시에 저장 된 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-127">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and is returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="6ca3a-128">서버에서 리소스를 다운로드, 캐시에 저장 하 고 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-128">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="6ca3a-129">캐시 된 리소스가 있는 경우 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-129">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="6ca3a-130">리소스는 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-130">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="6ca3a-131">타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 리소스의 캐시 된 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 않으면 리소스 호출자에 게 표시 되는 서버에서 다운로드 되 고 캐시에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-131">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and is stored in the cache,</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6ca3a-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6ca3a-132">Child Elements</span></span>  
  
|<span data-ttu-id="6ca3a-133">요소</span><span class="sxs-lookup"><span data-stu-id="6ca3a-133">Element</span></span>|<span data-ttu-id="6ca3a-134">설명</span><span class="sxs-lookup"><span data-stu-id="6ca3a-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ca3a-135">defaultHttpCachePolicy</span><span class="sxs-lookup"><span data-stu-id="6ca3a-135">defaultHttpCachePolicy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|<span data-ttu-id="6ca3a-136">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-136">Optional element.</span></span><br /><br /> <span data-ttu-id="6ca3a-137">HTTP 캐싱을 활성화 되어 있는지 여부를 나타내고 기본 캐싱 정책은 설명 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-137">Describes whether HTTP caching is active and describes the default caching policy.</span></span>|  
|[<span data-ttu-id="6ca3a-138">\<defaultFtpCachePolicy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6ca3a-138">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|<span data-ttu-id="6ca3a-139">선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-139">Optional element.</span></span><br /><br /> <span data-ttu-id="6ca3a-140">FTP 캐싱 활성화 되어 있는지 여부를 나타내고 기본 캐싱 정책은 설명 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-140">Describes whether FTP caching is active and describes the default caching policy.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ca3a-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6ca3a-141">Parent Elements</span></span>  
  
|<span data-ttu-id="6ca3a-142">요소</span><span class="sxs-lookup"><span data-stu-id="6ca3a-142">Element</span></span>|<span data-ttu-id="6ca3a-143">설명</span><span class="sxs-lookup"><span data-stu-id="6ca3a-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ca3a-144">system.net</span><span class="sxs-lookup"><span data-stu-id="6ca3a-144">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="6ca3a-145">.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-145">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6ca3a-146">예제</span><span class="sxs-lookup"><span data-stu-id="6ca3a-146">Example</span></span>  
 <span data-ttu-id="6ca3a-147">다음 예제에서는 모든 캐시를 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ca3a-147">The following example shows how to disable all caching.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ca3a-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="6ca3a-148">See also</span></span>

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [<span data-ttu-id="6ca3a-149">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6ca3a-149">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
