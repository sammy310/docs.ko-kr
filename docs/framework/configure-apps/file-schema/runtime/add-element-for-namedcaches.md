---
title: <namedCaches>에 대한 <add> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: fd6668a551663470a97b07ff131710dbe92a91f5
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659026"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="cde1d-102">\<namedcaches > 요소 \<를 추가 ></span><span class="sxs-lookup"><span data-stu-id="cde1d-102">\<add> Element for \<namedCaches></span></span>
<span data-ttu-id="cde1d-103">메모리 캐시 `namedCache` 의 `namedCaches` 컬렉션에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
 <span data-ttu-id="cde1d-104">\<system.runtime.caching></span><span class="sxs-lookup"><span data-stu-id="cde1d-104">\<system.runtime.caching></span></span>  
<span data-ttu-id="cde1d-105">\<memoryCache></span><span class="sxs-lookup"><span data-stu-id="cde1d-105">\<memoryCache></span></span>  
<span data-ttu-id="cde1d-106">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="cde1d-106">\<namedCaches></span></span>  
<span data-ttu-id="cde1d-107">\<add></span><span class="sxs-lookup"><span data-stu-id="cde1d-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cde1d-108">구문</span><span class="sxs-lookup"><span data-stu-id="cde1d-108">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="cde1d-109">형식</span><span class="sxs-lookup"><span data-stu-id="cde1d-109">Type</span></span>  
 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cde1d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cde1d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cde1d-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cde1d-112">특성</span><span class="sxs-lookup"><span data-stu-id="cde1d-112">Attributes</span></span>  
  
|<span data-ttu-id="cde1d-113">특성</span><span class="sxs-lookup"><span data-stu-id="cde1d-113">Attribute</span></span>|<span data-ttu-id="cde1d-114">설명</span><span class="sxs-lookup"><span data-stu-id="cde1d-114">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="cde1d-115">인스턴스를 확장할 <xref:System.Runtime.Caching.MemoryCache> 수 있는 최대 허용 크기 (mb)를 지정 하는 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-115">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="cde1d-116">기본값은 0 이며,이는 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-116">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="cde1d-117">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-117">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="cde1d-118">캐시에서 사용할 수 있는 물리적으로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-118">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="cde1d-119">기본값은 0 이며,이는 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-119">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="cde1d-120">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-120">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="cde1d-121">이 값은 "HH: MM: SS" 형식으로 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-121">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cde1d-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cde1d-122">Child Elements</span></span>  
 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="cde1d-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cde1d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cde1d-124">요소</span><span class="sxs-lookup"><span data-stu-id="cde1d-124">Element</span></span>|<span data-ttu-id="cde1d-125">설명</span><span class="sxs-lookup"><span data-stu-id="cde1d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cde1d-126">\<namedCaches></span><span class="sxs-lookup"><span data-stu-id="cde1d-126">\<namedCaches></span></span>](namedcaches-element-cache-settings.md)|<span data-ttu-id="cde1d-127">명명 <xref:System.Runtime.Caching.MemoryCache> 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-127">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cde1d-128">설명</span><span class="sxs-lookup"><span data-stu-id="cde1d-128">Remarks</span></span>  
 <span data-ttu-id="cde1d-129">요소 `add` 는 메모리 캐시의 `namedCaches` 컬렉션에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-129">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="cde1d-130">`add` 요소를 사용 하기 전에 [clear](clear-element-for-namedcaches.md) 요소를 사용 하 여 컬렉션에 다른 명명 된 캐시가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-130">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="cde1d-131">이 요소는 machine.config 파일 및 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-131">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cde1d-132">예제</span><span class="sxs-lookup"><span data-stu-id="cde1d-132">Example</span></span>  
 <span data-ttu-id="cde1d-133">다음 예제에서는 메모리 캐시의 `namedCache` `namedCaches` 컬렉션에 대 한 기본 항목에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cde1d-133">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cde1d-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="cde1d-134">See also</span></span>

- [<span data-ttu-id="cde1d-135">\<namedCaches > 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="cde1d-135">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
