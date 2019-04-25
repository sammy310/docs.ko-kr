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
ms.openlocfilehash: 36d174beea58ff96674bd873bfbcb8be89591669
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674560"
---
# <a name="defaultftpcachepolicy-element-network-settings"></a><span data-ttu-id="5a611-102">\<defaultFtpCachePolicy > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="5a611-102">\<defaultFtpCachePolicy> Element (Network Settings)</span></span>
<span data-ttu-id="5a611-103">FTP 캐싱 활성화 되어 있는지 여부를 나타내고 기본 캐싱 정책은 설명 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-103">Describes whether FTP caching is active and describes the default caching policy.</span></span>  
  
 <span data-ttu-id="5a611-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5a611-104">\<configuration></span></span>  
<span data-ttu-id="5a611-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5a611-105">\<system.net></span></span>  
<span data-ttu-id="5a611-106">\<requestCaching></span><span class="sxs-lookup"><span data-stu-id="5a611-106">\<requestCaching></span></span>  
<span data-ttu-id="5a611-107">\<defaultFtpCachePolicy></span><span class="sxs-lookup"><span data-stu-id="5a611-107">\<defaultFtpCachePolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a611-108">구문</span><span class="sxs-lookup"><span data-stu-id="5a611-108">Syntax</span></span>  
  
```xml  
<defaultFtpCachePolicy  
  policyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a611-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a611-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5a611-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a611-111">특성</span><span class="sxs-lookup"><span data-stu-id="5a611-111">Attributes</span></span>  
  
|<span data-ttu-id="5a611-112">특성</span><span class="sxs-lookup"><span data-stu-id="5a611-112">Attribute</span></span>|<span data-ttu-id="5a611-113">설명</span><span class="sxs-lookup"><span data-stu-id="5a611-113">Description</span></span>|  
|---------------|-----------------|  
|`policyLevel`|<span data-ttu-id="5a611-114">FTP 캐싱 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-114">Specifies the FTP caching policy.</span></span> <span data-ttu-id="5a611-115">기본값은 `Default`입니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-115">The default value is `Default`.</span></span>|  
  
## <a name="policylevel-attribute"></a><span data-ttu-id="5a611-116">policyLevel 특성</span><span class="sxs-lookup"><span data-stu-id="5a611-116">policyLevel Attribute</span></span>  
  
|<span data-ttu-id="5a611-117">값</span><span class="sxs-lookup"><span data-stu-id="5a611-117">Value</span></span>|<span data-ttu-id="5a611-118">설명</span><span class="sxs-lookup"><span data-stu-id="5a611-118">Description</span></span>|  
|-----------|-----------------|  
|`Default`|<span data-ttu-id="5a611-119">리소스 새로 고침, 콘텐츠 길이 정확 하 고, 이며 만료, 수정 및 콘텐츠 길이 특성이 있는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-119">Returns the cached resource if the resource is fresh, the content length is accurate, and the expiration, modification, and content length attributes are present.</span></span>|  
|`BypassCache`|<span data-ttu-id="5a611-120">서버에서 리소스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-120">Returns the resource from the server.</span></span>|  
|`CacheOnly`|<span data-ttu-id="5a611-121">콘텐츠 길이가 있는지와 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-121">Returns the cached resource if the content length is present and matches the entry size.</span></span>|  
|`CacheIfAvailable`|<span data-ttu-id="5a611-122">콘텐츠 길이 제공 하는 크기와 일치 항목; 경우 캐시 된 리소스를 반환 합니다. 그렇지 않은 경우 리소스 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-122">Returns the cached resource if the content length is provided and matches the entry size; otherwise, the resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5a611-123">캐시 된 리소스의 타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 이 고, 그렇지 리소스 다운로드 서버에서 캐시에 저장 되어 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-123">Returns the cached resource if the timestamp of the cached resource is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, stored in the cache, and returned to the caller.</span></span>|  
|`Reload`|<span data-ttu-id="5a611-124">서버에서 리소스를 다운로드, 캐시에 저장 하 고 호출자에 게 리소스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-124">Downloads the resource from the server, stores it in the cache, and returns the resource to the caller.</span></span>|  
|`NoCacheNoStore`|<span data-ttu-id="5a611-125">캐시 된 리소스가 있는 경우 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-125">If a cached resource exists, it is deleted.</span></span> <span data-ttu-id="5a611-126">리소스는 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-126">The resource is downloaded from the server and is returned to the caller.</span></span>|  
|`Revalidate`|<span data-ttu-id="5a611-127">타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 리소스의 캐시 된 복사본을 사용 하 여 요청을 만족 시킵니다. 이 고, 그렇지 리소스는 서버에서 다운로드, 호출자에 게 표시 되 고 캐시에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-127">Satisfies a request by using the cached copy of the resource if the timestamp is the same as the timestamp of the resource on the server; otherwise, the resource is downloaded from the server, presented to the caller, and stored in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a611-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a611-128">Child Elements</span></span>  
 <span data-ttu-id="5a611-129">없음</span><span class="sxs-lookup"><span data-stu-id="5a611-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a611-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a611-130">Parent Elements</span></span>  
  
|<span data-ttu-id="5a611-131">요소</span><span class="sxs-lookup"><span data-stu-id="5a611-131">Element</span></span>|<span data-ttu-id="5a611-132">설명</span><span class="sxs-lookup"><span data-stu-id="5a611-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a611-133">requestCaching</span><span class="sxs-lookup"><span data-stu-id="5a611-133">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="5a611-134">네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-134">Controls the caching mechanism for network requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a611-135">설명</span><span class="sxs-lookup"><span data-stu-id="5a611-135">Remarks</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a611-136">예제</span><span class="sxs-lookup"><span data-stu-id="5a611-136">Example</span></span>  
 <span data-ttu-id="5a611-137">다음 예제에서는 캐싱 정책 FTP를 지정 하는 방법을 보여 줍니다 `NoCacheNoStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="5a611-137">The following example shows how to specify an FTP caching policy of `NoCacheNoStore`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5a611-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="5a611-138">See also</span></span>

- <xref:System.Net.Cache>
- <xref:System.Net.WebRequest>
- <xref:System.Net.Cache.RequestCacheLevel>
- [<span data-ttu-id="5a611-139">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5a611-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
