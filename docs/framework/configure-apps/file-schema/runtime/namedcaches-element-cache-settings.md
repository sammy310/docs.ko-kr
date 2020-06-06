---
title: <namedCaches> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153960"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="6c71b-102">\<namedCaches> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="6c71b-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="6c71b-103">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 지정 합니다 <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6c71b-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="6c71b-104">합니다 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 하나 이상의 구성 설정의 컬렉션을 참조 하는 속성 `namedCaches` 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**  
  
## <a name="syntax"></a><span data-ttu-id="6c71b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6c71b-105">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="6c71b-106">Type</span><span class="sxs-lookup"><span data-stu-id="6c71b-106">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c71b-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6c71b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6c71b-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c71b-109">특성</span><span class="sxs-lookup"><span data-stu-id="6c71b-109">Attributes</span></span>  
  
|<span data-ttu-id="6c71b-110">attribute</span><span class="sxs-lookup"><span data-stu-id="6c71b-110">Attribute</span></span>|<span data-ttu-id="6c71b-111">Description</span><span class="sxs-lookup"><span data-stu-id="6c71b-111">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="6c71b-112">인스턴스를 확장할 수 있는 최대 허용 크기 (mb)를 지정 하는 정수 값입니다 <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6c71b-112">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="6c71b-113">기본값은 0입니다. 즉, 클래스의 자동 크기 조정 추론은 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-113">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="6c71b-114">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-114">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="6c71b-115">캐시에서 사용할 수 있는 물리적으로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-115">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="6c71b-116">기본값은 0입니다. 즉, 클래스의 자동 크기 조정 추론은 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-116">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="6c71b-117">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-117">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="6c71b-118">이 값은 "HH: MM: SS" 형식으로 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-118">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c71b-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6c71b-119">Child Elements</span></span>  
  
|<span data-ttu-id="6c71b-120">요소</span><span class="sxs-lookup"><span data-stu-id="6c71b-120">Element</span></span>|<span data-ttu-id="6c71b-121">Description</span><span class="sxs-lookup"><span data-stu-id="6c71b-121">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-namedcaches.md)|<span data-ttu-id="6c71b-122">메모리 캐시용으로 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-122">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[\<clear>](clear-element-for-namedcaches.md)|<span data-ttu-id="6c71b-123">메모리 캐시에 대해 `namedCaches` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-123">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[\<remove>](remove-element-for-namedcaches.md)|<span data-ttu-id="6c71b-124">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-124">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c71b-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6c71b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="6c71b-126">요소</span><span class="sxs-lookup"><span data-stu-id="6c71b-126">Element</span></span>|<span data-ttu-id="6c71b-127">Description</span><span class="sxs-lookup"><span data-stu-id="6c71b-127">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="6c71b-128">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용 하는 모든 구성 파일의 루트 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-128">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="6c71b-129"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-129">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[\<system.runtime.caching>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="6c71b-130">.NET Framework에 기본 제공 되는 응용 프로그램에서 출력 캐싱을 구현할 수 있는 형식을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-130">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c71b-131">설명</span><span class="sxs-lookup"><span data-stu-id="6c71b-131">Remarks</span></span>  
 <span data-ttu-id="6c71b-132">Web.config 파일의 메모리 캐시 구성 섹션에는 `add` `remove` `clear` 컬렉션에 대 한, 및 특성을 포함할 수 있습니다 `namedCaches` .</span><span class="sxs-lookup"><span data-stu-id="6c71b-132">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="6c71b-133">각 `namedCaches` 항목은 특성에 의해 고유 하 게 식별 됩니다 `name` .</span><span class="sxs-lookup"><span data-stu-id="6c71b-133">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="6c71b-134">응용 프로그램 구성 파일의 정보를 참조 하 여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-134">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="6c71b-135">기본적으로 기본 캐시 인스턴스만 구성 파일에 항목을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-135">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="6c71b-136">기본 캐시 인스턴스는 속성에서 반환 되는 인스턴스입니다 <xref:System.Runtime.Caching.MemoryCache.Default%2A> .</span><span class="sxs-lookup"><span data-stu-id="6c71b-136">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="6c71b-137">Name 특성을 "default"로 설정 하는 경우 요소는 기본 메모리 캐시 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-137">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c71b-138">예제</span><span class="sxs-lookup"><span data-stu-id="6c71b-138">Example</span></span>  
 <span data-ttu-id="6c71b-139">다음 예제에서는 `name` 특성을 "기본값"으로 설정 하 여 캐시 이름을 기본 캐시 항목 이름으로 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-139">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="6c71b-140">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-140">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="6c71b-141">이러한 특성을 0으로 설정 하면 클래스의 자동 크기 조정 추론을 사용 하는 것입니다 <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="6c71b-141">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="6c71b-142">캐시 구현에서는 현재 메모리 부하가 절대 및 백분율 기반 메모리 제한과 2 분 마다 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c71b-142">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c71b-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c71b-143">See also</span></span>

- [<span data-ttu-id="6c71b-144">\<memoryCache>요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="6c71b-144">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
