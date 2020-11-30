---
title: 캐시 정책
description: 요청된 리소스의 캐시된 복사본을 통해 요청을 충족할 수 있는지 여부를 결정하는 규칙인 캐시 정책에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
ms.openlocfilehash: 5492fd9f7b27f7546b951710e4b3e099a1d6664d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250595"
---
# <a name="cache-policy"></a><span data-ttu-id="94b25-103">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="94b25-103">Cache Policy</span></span>

<span data-ttu-id="94b25-104">캐시 정책이 요청된 리소스의 캐시된 복사본을 통해 요청을 충족할 수 있는지 여부를 결정하는 데 사용되는 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-104">A cache policy defines rules that are used to determine whether a request can be satisfied using a cached copy of the requested resource.</span></span> <span data-ttu-id="94b25-105">애플리케이션에서 새로 고침에 대한 클라이언트 캐시 요구 사항을 지정하지만, 유효한 캐시 정책은 클라이언트 캐시 요구 사항, 서버의 콘텐츠 만료 요구 사항 및 서버의 유효성 재검사 요구 사항에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-105">Applications specify client cache requirements for freshness, but the effective cache policy is determined by the client cache requirements, the server's content expiration requirements, and the server's revalidation requirements.</span></span> <span data-ttu-id="94b25-106">최신 콘텐츠가 클라이언트 애플리케이션에 반환되도록 돕기 위해 클라이언트 캐시 정책 및 서버 요구 사항의 상호 작용 결과로 항상 가장 보수적인 캐시 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-106">The interaction of client cache policy and server requirements always results in the most conservative cache policy, to help ensure that the freshest content is returned to the client application.</span></span>  
  
 <span data-ttu-id="94b25-107">캐시 정책은 위치 기반 또는 시간 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-107">Cache policies are either location-based or time-based.</span></span> <span data-ttu-id="94b25-108">위치 기반 캐시 정책은 요청한 리소스를 가져올 수 있는 위치를 기준으로 캐시된 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-108">A location-based cache policy defines the freshness of cached entries based on where the requested resource can be taken from.</span></span> <span data-ttu-id="94b25-109">시간 기반 캐시 정책은 리소스가 검색된 시간, 리소스와 함께 반환된 헤더, 현재 시간을 사용하여 캐시된 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-109">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, headers returned with the resource, and the current time.</span></span> <span data-ttu-id="94b25-110">대부분의 애플리케이션은 [IETF(Internet Engineering Task Force)](https://www.ietf.org/) 웹 사이트에 있는 RFC 2616에 지정된 캐싱 정책을 구현하는 기본 시간 기반 캐시 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-110">Most applications can use the default time-based cache policy, which implements the caching policy specified in RFC 2616, available at [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website.</span></span>  
  
 <span data-ttu-id="94b25-111">다음 표에 설명된 클래스는 캐시 정책을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-111">The classes described in the following table are used to specify cache policies.</span></span>  
  
|<span data-ttu-id="94b25-112">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="94b25-112">Class name</span></span>|<span data-ttu-id="94b25-113">설명</span><span class="sxs-lookup"><span data-stu-id="94b25-113">Description</span></span>|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|<span data-ttu-id="94b25-114"><xref:System.Net.HttpWebRequest> 개체를 사용하여 요청된 리소스에 대한 위치 기반 및 시간 기반 캐시 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-114">Represents location-based and time-based cache policies for resources requested using <xref:System.Net.HttpWebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCachePolicy>|<span data-ttu-id="94b25-115"><xref:System.Net.Cache.RequestCacheLevel.Default> 개체를 사용하여 요청된 리소스에 대한 위치 기반 캐시 정책 또는 <xref:System.Net.WebRequest> 시간 기반 캐시 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-115">Represents location-based cache policies or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based cache policy for resources requested using <xref:System.Net.WebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|<span data-ttu-id="94b25-116">시간 기반 <xref:System.Net.Cache.HttpRequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-116">Specifies values used to create time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|<span data-ttu-id="94b25-117">위치 기반 및 시간 기반 <xref:System.Net.Cache.HttpRequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-117">Specifies values used to create location-based and time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCacheLevel>|<span data-ttu-id="94b25-118">위치 기반 또는 <xref:System.Net.Cache.RequestCacheLevel.Default> 시간 기반 <xref:System.Net.Cache.RequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-118">Specifies values used to create location-based or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based <xref:System.Net.Cache.RequestCachePolicy> objects.</span></span>|  
  
 <span data-ttu-id="94b25-119">애플리케이션에서 만든 모든 요청 또는 개별 요청에 대한 캐시 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-119">You can define a cache policy for all requests made by your application or for individual requests.</span></span> <span data-ttu-id="94b25-120">애플리케이션 수준 캐시 정책과 요청 수준 캐시 정책을 둘 다 지정하는 경우 요청 수준 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-120">When you specify both an application-level cache policy and a request-level cache policy, the request-level policy is used.</span></span> <span data-ttu-id="94b25-121">프로그래밍 방식으로 또는 애플리케이션 또는 컴퓨터 구성 파일을 사용하여 애플리케이션 수준 캐시 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-121">You can specify an application-level cache policy programmatically or by using the application or machine configuration files.</span></span> <span data-ttu-id="94b25-122">자세한 내용은 [\<requestCaching> 요소(네트워크 설정)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94b25-122">For more information, see [\<requestCaching> Element (Network Settings)](../configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
 <span data-ttu-id="94b25-123">캐시 정책을 만들려면 <xref:System.Net.Cache.RequestCachePolicy> 또는 <xref:System.Net.Cache.HttpRequestCachePolicy> 클래스 인스턴스를 만들어 정책 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-123">To create a cache policy, you must create a policy object by creating an instance of the <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> class.</span></span> <span data-ttu-id="94b25-124">요청에 정책을 지정하려면 요청의 <xref:System.Net.WebRequest.CachePolicy%2A> 속성을 정책 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-124">To specify the policy on a request, set the request's <xref:System.Net.WebRequest.CachePolicy%2A> property to the policy object.</span></span> <span data-ttu-id="94b25-125">프로그래밍 방식으로 애플리케이션 수준 정책을 설정하는 경우 <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> 속성을 정책 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="94b25-125">When setting an application-level policy programmatically, set the <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> property to the policy object.</span></span>  
  
 <span data-ttu-id="94b25-126">캐시 정책을 만들고 사용하는 방법을 보여 주는 코드 예제는 [네트워크 애플리케이션에서 캐싱 구성](configuring-caching-in-network-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94b25-126">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b25-127">참조</span><span class="sxs-lookup"><span data-stu-id="94b25-127">See also</span></span>

- [<span data-ttu-id="94b25-128">네트워크 애플리케이션에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="94b25-128">Cache Management for Network Applications</span></span>](cache-management-for-network-applications.md)
- [<span data-ttu-id="94b25-129">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="94b25-129">Location-Based Cache Policies</span></span>](location-based-cache-policies.md)
- [<span data-ttu-id="94b25-130">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="94b25-130">Time-Based Cache Policies</span></span>](time-based-cache-policies.md)
- [<span data-ttu-id="94b25-131">네트워크 애플리케이션에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="94b25-131">Configuring Caching in Network Applications</span></span>](configuring-caching-in-network-applications.md)
