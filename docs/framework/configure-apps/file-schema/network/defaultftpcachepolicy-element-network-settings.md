---
description: '다음에 대 한 자세한 정보: <defaultFtpCachePolicy> 요소 (네트워크 설정)'
title: <defaultFtpCachePolicy> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultFtpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultFtpCachePolicy
helpviewer_keywords:
- <defaultFtpCachePolicy> element
- defaultFtpCachePolicy element
ms.assetid: 0eb0c5cb-dd97-484d-8614-785e88877abb
ms.openlocfilehash: 77150ce0980e96dd949df4b5ad7e4557ed1b991a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740368"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="ba417-103">\<defaultFtpCachePolicy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="ba417-103">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>

<span data-ttu-id="ba417-104">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-104">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="ba417-105">구문</span><span class="sxs-lookup"><span data-stu-id="ba417-105">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba417-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ba417-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ba417-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba417-108">특성</span><span class="sxs-lookup"><span data-stu-id="ba417-108">Attributes</span></span>  
  
|<span data-ttu-id="ba417-109">attribute</span><span class="sxs-lookup"><span data-stu-id="ba417-109">Attribute</span></span>|<span data-ttu-id="ba417-110">설명</span><span class="sxs-lookup"><span data-stu-id="ba417-110">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="ba417-111">FTP 캐싱 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-111">Specifies the FTP caching policy.</span></span> <span data-ttu-id="ba417-112">기본값은 `Default`입니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-112">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="ba417-113">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="ba417-113">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="ba417-114">값</span><span class="sxs-lookup"><span data-stu-id="ba417-114">Value</span></span>|<span data-ttu-id="ba417-115">설명</span><span class="sxs-lookup"><span data-stu-id="ba417-115">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="ba417-116">리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-116">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="ba417-117">서버에서 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-117">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="ba417-118">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-118">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="ba417-119">콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-119">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="ba417-120">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-120">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="ba417-121">서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-121">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="ba417-122">캐시 된 리소스가 있으면 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-122">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="ba417-123">리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-123">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="ba417-124">캐시된 리소스 복사본의 타임스탬프가 서버에 있는 리소스의 타임스탬프와 동일하면 캐시된 리소스 복사본을 사용하여 요청을 만족시키고, 그렇지 않으면 서버에서 리소스를 다운로드하여 호출자에게 제공한 다음 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-124">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba417-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ba417-125">Child Elements</span></span>  

 <span data-ttu-id="ba417-126">없음</span><span class="sxs-lookup"><span data-stu-id="ba417-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba417-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ba417-127">Parent Elements</span></span>  
  
|<span data-ttu-id="ba417-128">요소</span><span class="sxs-lookup"><span data-stu-id="ba417-128">Element</span></span>|<span data-ttu-id="ba417-129">설명</span><span class="sxs-lookup"><span data-stu-id="ba417-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba417-130">requestCaching</span><span class="sxs-lookup"><span data-stu-id="ba417-130">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="ba417-131">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba417-131">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba417-132">설명</span><span class="sxs-lookup"><span data-stu-id="ba417-132">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba417-133">예제</span><span class="sxs-lookup"><span data-stu-id="ba417-133">Example</span></span>  

 <span data-ttu-id="ba417-134">다음 예에서는의 FTP 캐싱 정책을 지정 하는 방법을 보여 줍니다 `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="ba417-134">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba417-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba417-135">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="ba417-136">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ba417-136">Network Settings Schema</span></span>](index.md)
