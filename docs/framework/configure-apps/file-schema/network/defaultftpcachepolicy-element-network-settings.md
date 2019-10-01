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
ms.openlocfilehash: fd1649edbf7a2c8546992019df667f27df68e02c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698324"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="6cc31-102">\<defaultFtpCachePolicy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6cc31-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="6cc31-103">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
[<span data-ttu-id="6cc31-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="6cc31-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="6cc31-105">&nbsp; @ no__t-1[ **@no__t -4c.net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6cc31-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="6cc31-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<requestCaching >** ](requestcaching-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="6cc31-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)</span></span>  
<span data-ttu-id="6cc31-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 **\<defaultFtpCachePolicy >**</span><span class="sxs-lookup"><span data-stu-id="6cc31-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc31-108">구문</span><span class="sxs-lookup"><span data-stu-id="6cc31-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cc31-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6cc31-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6cc31-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cc31-111">특성</span><span class="sxs-lookup"><span data-stu-id="6cc31-111">Attributes</span></span>  
  
|<span data-ttu-id="6cc31-112">특성</span><span class="sxs-lookup"><span data-stu-id="6cc31-112">Attribute</span></span>|<span data-ttu-id="6cc31-113">설명</span><span class="sxs-lookup"><span data-stu-id="6cc31-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="6cc31-114">FTP 캐싱 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="6cc31-115">기본값은 `Default`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="6cc31-116">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="6cc31-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="6cc31-117">값</span><span class="sxs-lookup"><span data-stu-id="6cc31-117">Value</span></span>|<span data-ttu-id="6cc31-118">설명</span><span class="sxs-lookup"><span data-stu-id="6cc31-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="6cc31-119">리소스 새로 고침, 콘텐츠 길이 정확 하 고, 이며 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="6cc31-120">서버에서 리소스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="6cc31-121">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="6cc31-122">콘텐츠 길이 제공 하는 크기와 일치 항목; 경우 캐시 된 리소스를 반환 합니다. 그렇지 않은 경우 리소스 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="6cc31-123">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="6cc31-124">서버에서 리소스를 다운로드, 캐시에 저장 하 고 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="6cc31-125">캐시 된 리소스가 있는 경우 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="6cc31-126">리소스는 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="6cc31-127">타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 리소스의 캐시 된 복사본을 사용 하 여 요청을 만족 시킵니다. 이 고, 그렇지 리소스는 서버에서 다운로드, 호출자에 게 표시 되 고 캐시에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6cc31-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6cc31-128">Child Elements</span></span>  
 <span data-ttu-id="6cc31-129">없음</span><span class="sxs-lookup"><span data-stu-id="6cc31-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6cc31-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6cc31-130">Parent Elements</span></span>  
  
|<span data-ttu-id="6cc31-131">요소</span><span class="sxs-lookup"><span data-stu-id="6cc31-131">Element</span></span>|<span data-ttu-id="6cc31-132">설명</span><span class="sxs-lookup"><span data-stu-id="6cc31-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cc31-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="6cc31-133">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="6cc31-134">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cc31-135">설명</span><span class="sxs-lookup"><span data-stu-id="6cc31-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cc31-136">예제</span><span class="sxs-lookup"><span data-stu-id="6cc31-136">Example</span></span>  
 <span data-ttu-id="6cc31-137">다음 예제에서는 `NoCacheNoStore`의 FTP 캐싱 정책을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cc31-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6cc31-138">참조</span><span class="sxs-lookup"><span data-stu-id="6cc31-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="6cc31-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6cc31-139">Network Settings Schema</span></span>](index.md)
