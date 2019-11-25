---
title: <defaultFtpCachePolicy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 9261a430642cb4d5ac4507835bd0fd3561bd8c02
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088435"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="4a6a2-102">\<defaultFtpCachePolicy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4a6a2-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="4a6a2-103">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

<span data-ttu-id="4a6a2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4a6a2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4a6a2-105">&nbsp;[ **\<.net >를**](system-net-element-network-settings.md) &nbsp;</span><span class="sxs-lookup"><span data-stu-id="4a6a2-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="4a6a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4a6a2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>\
<span data-ttu-id="4a6a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultFtpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="4a6a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>

## <a name="syntax"></a><span data-ttu-id="4a6a2-108">구문</span><span class="sxs-lookup"><span data-stu-id="4a6a2-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a6a2-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4a6a2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4a6a2-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a6a2-111">특성</span><span class="sxs-lookup"><span data-stu-id="4a6a2-111">Attributes</span></span>  
  
|<span data-ttu-id="4a6a2-112">특성</span><span class="sxs-lookup"><span data-stu-id="4a6a2-112">Attribute</span></span>|<span data-ttu-id="4a6a2-113">설명</span><span class="sxs-lookup"><span data-stu-id="4a6a2-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="4a6a2-114">FTP 캐싱 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="4a6a2-115">기본값은 `Default`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="4a6a2-116">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="4a6a2-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="4a6a2-117">값</span><span class="sxs-lookup"><span data-stu-id="4a6a2-117">Value</span></span>|<span data-ttu-id="4a6a2-118">설명</span><span class="sxs-lookup"><span data-stu-id="4a6a2-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="4a6a2-119">리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="4a6a2-120">서버에서 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="4a6a2-121">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="4a6a2-122">콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="4a6a2-123">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="4a6a2-124">서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="4a6a2-125">캐시 된 리소스가 있으면 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="4a6a2-126">리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="4a6a2-127">타임 스탬프가 서버의 리소스 타임 스탬프와 동일한 경우 캐시 된 리소스 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 표시 되며 캐시에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a6a2-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4a6a2-128">Child Elements</span></span>  
 <span data-ttu-id="4a6a2-129">없음.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a6a2-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4a6a2-130">Parent Elements</span></span>  
  
|<span data-ttu-id="4a6a2-131">요소</span><span class="sxs-lookup"><span data-stu-id="4a6a2-131">Element</span></span>|<span data-ttu-id="4a6a2-132">설명</span><span class="sxs-lookup"><span data-stu-id="4a6a2-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a6a2-133">Requestcaching></span><span class="sxs-lookup"><span data-stu-id="4a6a2-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="4a6a2-134">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a6a2-135">주의</span><span class="sxs-lookup"><span data-stu-id="4a6a2-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a6a2-136">예제</span><span class="sxs-lookup"><span data-stu-id="4a6a2-136">Example</span></span>  
 <span data-ttu-id="4a6a2-137">다음 예에서는 `NoCacheNoStore`FTP 캐싱 정책을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a6a2-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultFtpCachePolicy  
        policyLevel="NoCacheNoStore">  
      </defaultFtpCachePolicy>  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a6a2-138">참조</span><span class="sxs-lookup"><span data-stu-id="4a6a2-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="4a6a2-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4a6a2-139">Network Settings Schema</span></span>](index.md)
