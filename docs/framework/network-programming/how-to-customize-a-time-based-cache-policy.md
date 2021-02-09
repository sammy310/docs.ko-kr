---
description: '자세한 정보: 방법: 시간 기반 캐시 정책을 사용자 지정'
title: '방법: 시간 기반 캐시 정책을 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
ms.openlocfilehash: bb00faa5c2cd3170a0f56b74032867d489c1fb8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747454"
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="bc301-103">방법: 시간 기반 캐시 정책을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="bc301-103">How to: customize a time-based cache policy</span></span>

<span data-ttu-id="bc301-104">시간 기반 캐시 정책을 만들 경우 최대 기간, 최소 새로 고침, 최대 부실 또는 캐시 동기화 날짜에 대한 값을 지정하여 캐싱 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-104">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="bc301-105"><xref:System.Net.Cache.HttpRequestCachePolicy> 개체는 이러한 값의 유효한 조합을 지정할 수 있는 여러 가지 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-105">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>

## <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="bc301-106">캐시 동기화 날짜를 사용하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bc301-106">To create a time-based cache policy that uses a cache synchronization date</span></span>

<span data-ttu-id="bc301-107"><xref:System.DateTime> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 캐시 동기화 날짜를 사용하는 시간 기반 캐시 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-107">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)
{
    var policy = new HttpRequestCachePolicy(when);
    Console.WriteLine("When: {0}", when);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy([when])
    Console.WriteLine("When: {0}", [when])
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="bc301-108">다음과 유사하게 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-108">The output is similar to the following:</span></span>

```output
When: 1/14/2004 8:07:30 AM
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="bc301-109">최소 새로 고침을 기반으로 하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bc301-109">To create a time-based cache policy that is based on minimum freshness</span></span>

<span data-ttu-id="bc301-110"><xref:System.Net.Cache.HttpCacheAgeControl.MinFresh>를 `cacheAgeControl` 매개 변수 값으로 지정하고 <xref:System.TimeSpan> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 최소 새로 고침을 기반으로 하는 시간 기반 캐시 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-110">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor:</span></span>

```csharp
public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="bc301-111">다음 호출의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc301-111">For the following invocation:</span></span>

```csharp
CreateMinFreshPolicy(new TimeSpan(1,0,0));
```

<span data-ttu-id="bc301-112">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-112">The output is:</span></span>

```output
Level:Default MinFresh:3600
```

## <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="bc301-113">최소 새로 고침 및 최대 기간을 기반으로 하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="bc301-113">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>

<span data-ttu-id="bc301-114"><xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh>를 `cacheAgeControl` 매개 변수 값으로 지정하고 두 개의 <xref:System.TimeSpan> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 최소 새로 고침 및 최대 기간을 기반으로 하는 시간 기반 캐시 정책을 만듭니다. 하나의 개체는 리소스의 최대 기간을 지정하고 두 번째 개체는 캐시에서 반환된 개체에 허용되는 최소 새로 고침을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-114">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache:</span></span>

```csharp
public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)
{
    var policy = new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);
    Console.WriteLine(policy.ToString());
    return policy;
}
```

```vb
Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy
    Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)
    Console.WriteLine(policy.ToString())
    Return policy
End Function
```

<span data-ttu-id="bc301-115">다음 호출의 경우:</span><span class="sxs-lookup"><span data-stu-id="bc301-115">For the following invocation:</span></span>
  
```csharp
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  

<span data-ttu-id="bc301-116">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bc301-116">The output is:</span></span>
  
```output
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc301-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc301-117">See also</span></span>

- [<span data-ttu-id="bc301-118">네트워크 애플리케이션에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="bc301-118">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="bc301-119">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="bc301-119">Cache Policy</span></span>](cache-policy.md)
- [<span data-ttu-id="bc301-120">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="bc301-120">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="bc301-121">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="bc301-121">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="bc301-122">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="bc301-122">\<requestCaching> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)
