---
title: <namedCaches>에 대한 <add> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: c1345022b79df371ad9c89a39a0a8b625e26608c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154507"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="8a296-102">\<명명 된 \<캐시> 대 한> 요소 추가</span><span class="sxs-lookup"><span data-stu-id="8a296-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="8a296-103">메모리 `namedCache` 캐시에 `namedCaches` 대한 항목을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
<span data-ttu-id="8a296-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8a296-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8a296-105">&nbsp;&nbsp;[**\<system.runtime.캐싱>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a296-105">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="8a296-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<메모리 캐시>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a296-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="8a296-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<명명된 캐시>**](namedcaches-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8a296-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)</span></span>\
<span data-ttu-id="8a296-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="8a296-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a296-109">구문</span><span class="sxs-lookup"><span data-stu-id="8a296-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="8a296-110">Type</span><span class="sxs-lookup"><span data-stu-id="8a296-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a296-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8a296-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a296-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a296-113">특성</span><span class="sxs-lookup"><span data-stu-id="8a296-113">Attributes</span></span>  
  
|<span data-ttu-id="8a296-114">attribute</span><span class="sxs-lookup"><span data-stu-id="8a296-114">Attribute</span></span>|<span data-ttu-id="8a296-115">Description</span><span class="sxs-lookup"><span data-stu-id="8a296-115">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="8a296-116">인스턴스가 증가할 <xref:System.Runtime.Caching.MemoryCache> 수 있는 최대 허용 크기(메가바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-116">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="8a296-117">기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 기본적으로 사용된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-117">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="8a296-118">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-118">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="8a296-119">캐시에서 사용할 수 있는 물리적으로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="8a296-120">기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 기본적으로 사용된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-120">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="8a296-121">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="8a296-122">이 값은 "HH:MM:SS" 형식으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a296-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8a296-123">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="8a296-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8a296-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8a296-125">요소</span><span class="sxs-lookup"><span data-stu-id="8a296-125">Element</span></span>|<span data-ttu-id="8a296-126">Description</span><span class="sxs-lookup"><span data-stu-id="8a296-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a296-127">\<명명된 캐시></span><span class="sxs-lookup"><span data-stu-id="8a296-127">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="8a296-128">명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스에 대한 구성 설정 컬렉션이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-128">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a296-129">설명</span><span class="sxs-lookup"><span data-stu-id="8a296-129">Remarks</span></span>  
 <span data-ttu-id="8a296-130">요소는 `add` 메모리 캐시에 `namedCaches` 대 한 컬렉션에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-130">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="8a296-131">컬렉션에 명명된 다른 캐시가 없는지 확인하기 위해 요소를 사용하기 전에 clear 요소를 사용할 수 있습니다. [clear](clear-element-for-namedcaches.md) `add`</span><span class="sxs-lookup"><span data-stu-id="8a296-131">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="8a296-132">이 요소는 machine.config 파일 및 Web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-132">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a296-133">예제</span><span class="sxs-lookup"><span data-stu-id="8a296-133">Example</span></span>  
 <span data-ttu-id="8a296-134">다음 예제에서는 메모리 캐시에 대한 `namedCache` `namedCaches` 컬렉션의 기본 항목에 대한 설정을 정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a296-134">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a296-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a296-135">See also</span></span>

- [<span data-ttu-id="8a296-136">\<명명된 캐시> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="8a296-136">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
