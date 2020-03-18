---
title: 시간 기반 캐시 정책
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- cache synchronization date policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- time, cached resources
- maximum age policy
- synchronization, cache
- staleness of cached resources
- default time-based cache policy
- maximum staleness policy
- content cache policies
- expired content
- minimum freshness policy
- age of cached resources
ms.assetid: 74f0bcaf-5c95-40c1-9967-f3bbf1d2360a
ms.openlocfilehash: 0edde8e716d5ce3b1444e994234def5835341475
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047121"
---
# <a name="time-based-cache-policies"></a><span data-ttu-id="6584a-102">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="6584a-102">Time-Based Cache Policies</span></span>
<span data-ttu-id="6584a-103">시간 기반 캐시 정책은 리소스가 검색된 시간, 리소스와 함께 반환된 헤더, 현재 시간을 사용하여 캐시된 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-103">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, the headers returned with the resource, and the current time.</span></span> <span data-ttu-id="6584a-104">시간 기반 캐시 정책을 설정하는 경우 <xref:System.Net.Cache.HttpRequestCacheLevel.Default> 시간 기반 정책을 사용하거나 사용자 지정 시간 기반 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-104">When setting a time-based cache policy, you can either use the <xref:System.Net.Cache.HttpRequestCacheLevel.Default> time-based policy or create a customized time-based policy.</span></span> <span data-ttu-id="6584a-105">HTTP(Hypertext Transfer Protocol)를 사용하여 얻은 리소스에 대한 기본 시간 기반 정책을 사용하는 경우 정확한 캐시 동작은 [IETF(Internet Engineering Task Force)](https://www.ietf.org/) 웹 사이트에 있는 RFC 2616의 섹션 13 및 14에 지정된 동작 및 캐시된 응답에 포함된 헤더에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-105">When using the default time-based policy for resources obtained using Hypertext Transfer Protocol (HTTP), the exact cache behavior is determined by the headers included in the cached response and by the behaviors specified in sections 13 and 14 of RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span> <span data-ttu-id="6584a-106">HTTP 리소스에 대한 기본 시간 기반 정책을 설정하는 방법을 보여 주는 코드 예제는 [방법: 애플리케이션에 대한 기본 시간 기반 캐시 정책 설정](how-to-set-the-default-time-based-cache-policy-for-an-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6584a-106">For a code example that demonstrates setting the default time-based policy for HTTP resources, see [How to: Set the Default Time-Based Cache Policy for an Application](how-to-set-the-default-time-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="6584a-107">캐시 정책을 만들고 사용하는 방법을 보여 주는 코드 예제는 [네트워크 애플리케이션에서 캐싱 구성](configuring-caching-in-network-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6584a-107">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="criteria-to-determine-freshness-of-cached-entries"></a><span data-ttu-id="6584a-108">캐시된 항목의 새로 고침을 결정하는 조건</span><span class="sxs-lookup"><span data-stu-id="6584a-108">Criteria to Determine Freshness of Cached Entries</span></span>  
 <span data-ttu-id="6584a-109">시간 기반 캐시 정책을 사용자 지정하려면 다음 조건 중 하나 이상을 사용하여 캐시된 항목의 새로 고침을 결정하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-109">To customize a time-based cache policy, you can specify that one or more of the following criteria be used to determine the freshness of cached entries:</span></span>  
  
- <span data-ttu-id="6584a-110">최대 보존 기간</span><span class="sxs-lookup"><span data-stu-id="6584a-110">Maximum age</span></span>  
  
- <span data-ttu-id="6584a-111">최대 부실</span><span class="sxs-lookup"><span data-stu-id="6584a-111">Maximum staleness</span></span>  
  
- <span data-ttu-id="6584a-112">최소 새로 고침</span><span class="sxs-lookup"><span data-stu-id="6584a-112">Minimum freshness</span></span>  
  
- <span data-ttu-id="6584a-113">캐시 동기화 날짜</span><span class="sxs-lookup"><span data-stu-id="6584a-113">Cache synchronization date</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6584a-114">기본 시간 기반 캐시 정책 사용과 애플리케이션에 대한 기본 캐시 정책 설정을 혼동하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-114">Using the default time-based cache policy should not be confused with setting a default cache policy for your application.</span></span> <span data-ttu-id="6584a-115">기본 시간 기반 정책은 요청 또는 애플리케이션 수준에서 사용할 수 있는 특정 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-115">The default time-based policy is a specific policy that can be used at the request or application level.</span></span> <span data-ttu-id="6584a-116">애플리케이션에 대한 기본 캐시 정책은 요청에 설정된 정책이 없는 경우 적용되는 정책(위치 기반 또는 시간 기반)입니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-116">The default cache policy for your application is a policy (location-based or time-based) that takes effect when no policy is set on a request.</span></span> <span data-ttu-id="6584a-117">애플리케이션에 대한 기본 캐시 정책을 설정하는 방법에 대한 자세한 내용은 <xref:System.Net.WebRequest.DefaultCachePolicy%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6584a-117">For details on setting a default cache policy for your application, see <xref:System.Net.WebRequest.DefaultCachePolicy%2A>.</span></span>  
  
### <a name="maximum-age"></a><span data-ttu-id="6584a-118">최대 보존 기간</span><span class="sxs-lookup"><span data-stu-id="6584a-118">Maximum Age</span></span>  
 <span data-ttu-id="6584a-119">최대 보존 기간 정책 조건은 리소스의 캐시된 복사본을 사용할 수 있는 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-119">The maximum age policy criterion specifies the amount of time a cached copy of a resource can be used.</span></span> <span data-ttu-id="6584a-120">리소스의 캐시된 복사본이 지정된 시간보다 오래된 경우 서버 콘텐츠와 비교해서 확인하여 리소스의 유효성을 재검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-120">If the cached copy of the resource is older than the amount of time specified, the resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="6584a-121">최대 보존 기간이 만료된 리소스를 사용할 수 있도록 허용하는 경우 최대 부실 값도 지정하지 않으면 이 조건은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-121">If the maximum age would allow the resource to be used after it expires, this criteria is not honored unless a maximum staleness value is also specified.</span></span>  
  
### <a name="maximum-staleness"></a><span data-ttu-id="6584a-122">최대 부실</span><span class="sxs-lookup"><span data-stu-id="6584a-122">Maximum Staleness</span></span>  
 <span data-ttu-id="6584a-123">최대 부실 정책 조건은 리소스의 캐시된 복사본을 사용할 수 있는 콘텐츠 만료 후의 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-123">The maximum staleness policy criterion specifies the length of time after content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="6584a-124">만료된 리소스를 사용할 수 있도록 허용하는 유일한 캐시 정책 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-124">This is the only cache policy criterion that permits resources to be used after they have expired.</span></span>  
  
### <a name="minimum-freshness"></a><span data-ttu-id="6584a-125">최소 새로 고침</span><span class="sxs-lookup"><span data-stu-id="6584a-125">Minimum Freshness</span></span>  
 <span data-ttu-id="6584a-126">최소 새로 고침 정책 조건은 리소스의 캐시된 복사본을 사용할 수 있는 콘텐츠 만료 전의 기간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-126">The minimum freshness policy criterion specifies the length of time before content expiration that the cached copy of the resource can be used.</span></span> <span data-ttu-id="6584a-127">이 정책은 캐시 항목이 만료 날짜 전에 만료되도록 하므로 최소 새로 고침 및 최대 부실 설정은 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-127">This policy has the effect of causing a cache entry to expire before its expiration date; therefore, the minimum freshness and maximum staleness settings are mutually exclusive.</span></span>  
  
## <a name="cache-synchronization-date"></a><span data-ttu-id="6584a-128">캐시 동기화 날짜</span><span class="sxs-lookup"><span data-stu-id="6584a-128">Cache Synchronization Date</span></span>  
 <span data-ttu-id="6584a-129">캐시 동기화 날짜 정책 조건은 서버 콘텐츠와 비교해서 확인하여 리소스의 캐시된 복사본 유효성을 재검사해야 하는 시기를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-129">The cache synchronization date policy criterion determines when a cached copy of a resource must be revalidated by checking it against the content on the server.</span></span> <span data-ttu-id="6584a-130">항목이 캐시된 이후 콘텐츠가 변경된 경우 서버에서 검색되어 캐시에 저장된 다음 애플리케이션에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-130">If the content has changed since the item was cached, it is retrieved from the server, stored in the cache, and returned to the application.</span></span> <span data-ttu-id="6584a-131">콘텐츠가 변경되지 않은 경우 해당 타임스탬프가 업데이트되고 애플리케이션이 캐시된 콘텐츠를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-131">If the content has not changed, its timestamp is updated and the application gets the cached content.</span></span>  
  
 <span data-ttu-id="6584a-132">캐시 동기화 날짜를 사용하면 캐시된 콘텐츠의 유효성을 검사해야 하는 절대 날짜를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-132">The cache synchronization date allows you to specify an absolute date when cached contents must be revalidated.</span></span> <span data-ttu-id="6584a-133">캐시 동기화 날짜 전에 새 캐시 항목의 유효성을 마지막으로 검사한 경우에도 서버와 유효성 검사가 다시 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-133">If a fresh cache entry was last revalidated prior to the cache synchronization date, revalidation with the server still occurs.</span></span> <span data-ttu-id="6584a-134">캐시 동기화 날짜 이후에 캐시 항목의 유효성이 재검사되었으며 캐시된 항목을 무효화하는 추가 새로 고침 또는 서버 유효성 재검사 요구 사항이 없는 경우 캐시의 항목이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-134">If the cache entry was revalidated after the cache synchronization date and there are no additional freshness or server revalidation requirements that invalidate the cached entry, the entry from the cache is used.</span></span> <span data-ttu-id="6584a-135">캐시 동기화 날짜가 미래의 특정 날짜로 설정된 경우 캐시 동기화 날짜가 지날 때까지 요청될 때마다 항목의 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-135">If the cache synchronization date is set to a future date, the entry is revalidated every time it is requested, until the cache synchronization date passes.</span></span>  
  
 <span data-ttu-id="6584a-136">다음 항목에서는 시간 기반 캐시 정책 조건을 결합한 결과에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6584a-136">The following topics provide information about the effects of combining time-based cache policy criteria:</span></span>  
  
- [<span data-ttu-id="6584a-137">캐시 정책 조작 -최대 사용 기간 및 최대 부실</span><span class="sxs-lookup"><span data-stu-id="6584a-137">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](cache-policy-interaction-maximum-age-and-maximum-staleness.md)  
  
- [<span data-ttu-id="6584a-138">캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침</span><span class="sxs-lookup"><span data-stu-id="6584a-138">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](cache-policy-interaction-maximum-age-and-minimum-freshness.md)  
  
## <a name="see-also"></a><span data-ttu-id="6584a-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6584a-139">See also</span></span>

- [<span data-ttu-id="6584a-140">네트워크 애플리케이션에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="6584a-140">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="6584a-141">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="6584a-141">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="6584a-142">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="6584a-142">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="6584a-143">네트워크 애플리케이션에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="6584a-143">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
- [<span data-ttu-id="6584a-144">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="6584a-144">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
