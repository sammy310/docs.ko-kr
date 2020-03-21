---
title: <namedCaches> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- namedCaches element
- caching [.NET Framework], configuration
- <namedCaches> element
ms.assetid: 6bd4fbc5-55a6-4dc4-998b-cdcc7e023330
ms.openlocfilehash: e0640ca18d386141f3c03135019eb4fe959b5bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153960"
---
# <a name="namedcaches-element-cache-settings"></a><span data-ttu-id="caf7c-102">\<명명된 캐시> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="caf7c-102">\<namedCaches> Element (Cache Settings)</span></span>
<span data-ttu-id="caf7c-103">명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스에 대한 구성 설정 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-103">Specifies a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span> <span data-ttu-id="caf7c-104">합니다 <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> 하나 이상의 구성 설정의 컬렉션을 참조 하는 속성 `namedCaches` 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-104">The <xref:System.Runtime.Caching.Configuration.MemoryCacheSection.NamedCaches%2A> property references the collection of configuration settings from one or more `namedCaches` elements of the configuration file.</span></span>  
  
<span data-ttu-id="caf7c-105">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="caf7c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="caf7c-106">&nbsp;&nbsp;[**\<system.runtime.캐싱>**](system-runtime-caching-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="caf7c-106">&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)</span></span>\
<span data-ttu-id="caf7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<메모리 캐시>**](memorycache-element-cache-settings.md)</span><span class="sxs-lookup"><span data-stu-id="caf7c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)</span></span>\
<span data-ttu-id="caf7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<명명된 캐시>**</span><span class="sxs-lookup"><span data-stu-id="caf7c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedCaches>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caf7c-109">구문</span><span class="sxs-lookup"><span data-stu-id="caf7c-109">Syntax</span></span>  
  
```xml  
<namedCaches>  
  <add name="default"/>
</namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="caf7c-110">Type</span><span class="sxs-lookup"><span data-stu-id="caf7c-110">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caf7c-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="caf7c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="caf7c-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caf7c-113">특성</span><span class="sxs-lookup"><span data-stu-id="caf7c-113">Attributes</span></span>  
  
|<span data-ttu-id="caf7c-114">attribute</span><span class="sxs-lookup"><span data-stu-id="caf7c-114">Attribute</span></span>|<span data-ttu-id="caf7c-115">Description</span><span class="sxs-lookup"><span data-stu-id="caf7c-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheMemoryLimitMegabytes`|<span data-ttu-id="caf7c-116">a 인스턴스가 증가할 <xref:System.Runtime.Caching.MemoryCache> 수 있는 최대 허용 크기(메가바이트)를 지정하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-116">An integer value that specifies the maximum allowable size, in megabytes, that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="caf7c-117">기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-117">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`name`|<span data-ttu-id="caf7c-118">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-118">The name of the cache.</span></span>|  
|`physicalMemoryLimitPercentage`|<span data-ttu-id="caf7c-119">캐시에서 사용할 수 있는 물리적으로 설치된 컴퓨터 메모리의 최대 백분율을 지정하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-119">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="caf7c-120">기본값은 0이며, 이는 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론이 기본적으로 사용된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-120">The default value is 0, which means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used by default.</span></span>|  
|`pollingInterval`|<span data-ttu-id="caf7c-121">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-121">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="caf7c-122">이 값은 "HH:MM:SS" 형식으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-122">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caf7c-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="caf7c-123">Child Elements</span></span>  
  
|<span data-ttu-id="caf7c-124">요소</span><span class="sxs-lookup"><span data-stu-id="caf7c-124">Element</span></span>|<span data-ttu-id="caf7c-125">Description</span><span class="sxs-lookup"><span data-stu-id="caf7c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caf7c-126">\<>추가</span><span class="sxs-lookup"><span data-stu-id="caf7c-126">\<add></span></span>](add-element-for-namedcaches.md)|<span data-ttu-id="caf7c-127">메모리 캐시용으로 명명된 캐시를 `namedCaches` 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-127">Adds a named cache to the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="caf7c-128">\<클리어></span><span class="sxs-lookup"><span data-stu-id="caf7c-128">\<clear></span></span>](clear-element-for-namedcaches.md)|<span data-ttu-id="caf7c-129">메모리 캐시에 대해 `namedCaches` 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-129">Clears the `namedCaches` collection for a memory cache.</span></span>|  
|[<span data-ttu-id="caf7c-130">\<>제거</span><span class="sxs-lookup"><span data-stu-id="caf7c-130">\<remove></span></span>](remove-element-for-namedcaches.md)|<span data-ttu-id="caf7c-131">메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-131">Removes a named cache entry from the `namedCaches` collection for a memory cache.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="caf7c-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="caf7c-132">Parent Elements</span></span>  
  
|<span data-ttu-id="caf7c-133">요소</span><span class="sxs-lookup"><span data-stu-id="caf7c-133">Element</span></span>|<span data-ttu-id="caf7c-134">Description</span><span class="sxs-lookup"><span data-stu-id="caf7c-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caf7c-135">\<구성></span><span class="sxs-lookup"><span data-stu-id="caf7c-135">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="caf7c-136">공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-136">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="caf7c-137">\<메모리 캐시></span><span class="sxs-lookup"><span data-stu-id="caf7c-137">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="caf7c-138"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-138">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
|[<span data-ttu-id="caf7c-139">\<system.runtime.캐싱></span><span class="sxs-lookup"><span data-stu-id="caf7c-139">\<system.runtime.caching></span></span>](system-runtime-caching-element-cache-settings.md)|<span data-ttu-id="caf7c-140">.NET Framework에 기본 제공 된 응용 프로그램에서 출력 캐싱을 구현할 수 있는 형식을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-140">Contains types that let you implement output caching in applications that are built into the .NET Framework.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caf7c-141">설명</span><span class="sxs-lookup"><span data-stu-id="caf7c-141">Remarks</span></span>  
 <span data-ttu-id="caf7c-142">Web.config 파일의 메모리 캐시 구성 `add`섹션에는 컬렉션에 대한 및 `remove` `clear` 특성이 `namedCaches` 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-142">The memory cache configuration section of the Web.config file can contain `add`, `remove`, and `clear` attributes for the `namedCaches` collection.</span></span> <span data-ttu-id="caf7c-143">각 `namedCaches` 항목은 `name` 특성에 의해 고유하게 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-143">Each `namedCaches` entry is uniquely identified by the `name` attribute.</span></span>  
  
 <span data-ttu-id="caf7c-144">응용 프로그램 구성 파일의 정보를 참조하여 메모리 캐시 항목의 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-144">You can retrieve instances of memory cache entries by referencing the information in the application configuration files.</span></span> <span data-ttu-id="caf7c-145">기본적으로 기본 캐시 인스턴스만 구성 파일에 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-145">By default, only the default cache instance has an entry in the configuration file.</span></span> <span data-ttu-id="caf7c-146">기본 캐시 인스턴스는 속성에서 반환되는 <xref:System.Runtime.Caching.MemoryCache.Default%2A> 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-146">The default cache instance is the instance that is returned from the <xref:System.Runtime.Caching.MemoryCache.Default%2A> property.</span></span>  
  
 <span data-ttu-id="caf7c-147">이름 특성을 "기본값"으로 설정하면 요소는 기본 메모리 캐시 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-147">If you set the name attribute to "default", the element uses the default memory cache instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf7c-148">예제</span><span class="sxs-lookup"><span data-stu-id="caf7c-148">Example</span></span>  
 <span data-ttu-id="caf7c-149">다음 예제에서는 `name` 특성을 "기본값"으로 설정하여 캐시 이름을 기본 캐시 항목 이름으로 설정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-149">The following example shows how to set the name of the cache to the default cache entry name by setting the `name` attribute to "default".</span></span>  
  
 <span data-ttu-id="caf7c-150">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-150">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="caf7c-151">이러한 특성을 0으로 설정하면 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 휴리스틱이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-151">Setting these attributes to zero means that the autosizing heuristics of the <xref:System.Runtime.Caching.MemoryCache> class are used.</span></span> <span data-ttu-id="caf7c-152">캐시 구현은 현재 메모리 로드를 2분마다 절대 및 백분율 기반 메모리 제한과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="caf7c-152">The cache implementation compares the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="caf7c-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="caf7c-153">See also</span></span>

- [<span data-ttu-id="caf7c-154">\<메모리캐시> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="caf7c-154">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
