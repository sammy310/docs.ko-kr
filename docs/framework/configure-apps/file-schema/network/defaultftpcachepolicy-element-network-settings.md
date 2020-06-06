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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088435"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="9b401-102">\<defaultFtpCachePolicy> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="9b401-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="9b401-103">FTP 캐싱이 활성 상태 인지 여부를 설명 하 고 기본 캐싱 정책을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<requestCaching>**](requestcaching-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultFtpCachePolicy>**

## <a name="syntax"></a><span data-ttu-id="9b401-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b401-104">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b401-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9b401-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9b401-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b401-107">특성</span><span class="sxs-lookup"><span data-stu-id="9b401-107">Attributes</span></span>  
  
|<span data-ttu-id="9b401-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9b401-108">Attribute</span></span>|<span data-ttu-id="9b401-109">Description</span><span class="sxs-lookup"><span data-stu-id="9b401-109">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="9b401-110">FTP 캐싱 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-110">Specifies the FTP caching policy.</span></span> <span data-ttu-id="9b401-111">기본값은 `Default`입니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-111">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="9b401-112">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="9b401-112">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="9b401-113">값</span><span class="sxs-lookup"><span data-stu-id="9b401-113">Value</span></span>|<span data-ttu-id="9b401-114">Description</span><span class="sxs-lookup"><span data-stu-id="9b401-114">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="9b401-115">리소스가 최신이 고, 콘텐츠 길이가 정확 하며, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-115">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="9b401-116">서버에서 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-116">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="9b401-117">콘텐츠 길이가 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-117">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="9b401-118">콘텐츠 길이가 제공 되 고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-118">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="9b401-119">캐시 된 리소스의 타임 스탬프가 서버에 있는 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스가 서버에서 다운로드 되어 캐시에 저장 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-119">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="9b401-120">서버에서 리소스를 다운로드 하 여 캐시에 저장 한 다음 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-120">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="9b401-121">캐시 된 리소스가 있으면 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-121">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="9b401-122">리소스가 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-122">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="9b401-123">캐시된 리소스 복사본의 타임스탬프가 서버에 있는 리소스의 타임스탬프와 동일하면 캐시된 리소스 복사본을 사용하여 요청을 만족시키고, 그렇지 않으면 서버에서 리소스를 다운로드하여 호출자에게 제공한 다음 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-123">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b401-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9b401-124">Child Elements</span></span>  
 <span data-ttu-id="9b401-125">없음</span><span class="sxs-lookup"><span data-stu-id="9b401-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b401-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9b401-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9b401-127">요소</span><span class="sxs-lookup"><span data-stu-id="9b401-127">Element</span></span>|<span data-ttu-id="9b401-128">Description</span><span class="sxs-lookup"><span data-stu-id="9b401-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b401-129">requestCaching</span><span class="sxs-lookup"><span data-stu-id="9b401-129">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="9b401-130">네트워크 요청에 대 한 캐싱 메커니즘을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b401-130">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b401-131">설명</span><span class="sxs-lookup"><span data-stu-id="9b401-131">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b401-132">예제</span><span class="sxs-lookup"><span data-stu-id="9b401-132">Example</span></span>  
 <span data-ttu-id="9b401-133">다음 예에서는의 FTP 캐싱 정책을 지정 하는 방법을 보여 줍니다 `NoCacheNoStore` .</span><span class="sxs-lookup"><span data-stu-id="9b401-133">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9b401-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b401-134">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="9b401-135">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9b401-135">Network Settings Schema</span></span>](index.md)
