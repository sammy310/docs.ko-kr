---
title: <namedCaches>에 대한 <add> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- add element for <namedCaches>
- <add> element for <namedCaches>
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
ms.openlocfilehash: cd920b58290050fcc30ea5d0a1ac113a333902fa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195365"
---
# <a name="add-element-for-namedcaches"></a><span data-ttu-id="1b8e0-102">\<namedCaches>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="1b8e0-102">\<add> Element for \<namedCaches></span></span>

<span data-ttu-id="1b8e0-103">`namedCache` `namedCaches` 메모리 캐시의 컬렉션에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-103">Adds a `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.caching>**](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<memoryCache>**](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedCaches>**](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="1b8e0-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b8e0-104">Syntax</span></span>  
  
```xml  
<namedCaches>  
    <add name="Default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a><span data-ttu-id="1b8e0-105">형식</span><span class="sxs-lookup"><span data-stu-id="1b8e0-105">Type</span></span>  

 `None`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b8e0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1b8e0-106">Attributes and Elements</span></span>  

 <span data-ttu-id="1b8e0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b8e0-108">특성</span><span class="sxs-lookup"><span data-stu-id="1b8e0-108">Attributes</span></span>  
  
|<span data-ttu-id="1b8e0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1b8e0-109">Attribute</span></span>|<span data-ttu-id="1b8e0-110">설명</span><span class="sxs-lookup"><span data-stu-id="1b8e0-110">Description</span></span>|  
|-|-|  
|`CacheMemoryLimitMegabytes`|<span data-ttu-id="1b8e0-111">인스턴스를 확장할 수 있는 최대 허용 크기 (mb)를 지정 하는 정수 값입니다 <xref:System.Runtime.Caching.MemoryCache> .</span><span class="sxs-lookup"><span data-stu-id="1b8e0-111">An integer value that specifies the maximum allowed size (in megabytes) that an instance of a <xref:System.Runtime.Caching.MemoryCache> can grow to.</span></span> <span data-ttu-id="1b8e0-112">기본값은 0 이며,이는 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-112">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`Name`|<span data-ttu-id="1b8e0-113">캐시의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-113">The name of the cache.</span></span>|  
|`PhysicalMemoryLimitPercentage`|<span data-ttu-id="1b8e0-114">캐시에서 사용할 수 있는 물리적으로 설치 된 컴퓨터 메모리의 최대 백분율을 지정 하는 0에서 100 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-114">An integer value between 0 and 100 that specifies the maximum percentage of physically installed computer memory that can be consumed by the cache.</span></span> <span data-ttu-id="1b8e0-115">기본값은 0 이며,이는 <xref:System.Runtime.Caching.MemoryCache> 기본적으로 클래스의 자동 크기 조정 추론을 사용 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-115">The default value is 0, which means that the <xref:System.Runtime.Caching.MemoryCache> class's autosizing heuristics are used by default.</span></span>|  
|`PollingInterval`|<span data-ttu-id="1b8e0-116">캐시 구현이 현재 메모리 로드를 캐시 인스턴스에 대해 설정된 절대 및 백분율 기반 메모리 제한과 비교하기까지의 시간 간격을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-116">A value that indicates the time interval after which the cache implementation compares the current memory load against the absolute and percentage-based memory limits that are set for the cache instance.</span></span> <span data-ttu-id="1b8e0-117">이 값은 "HH: MM: SS" 형식으로 입력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-117">This value is entered in "HH:MM:SS" format.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b8e0-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b8e0-118">Child Elements</span></span>  

 `None`  
  
### <a name="parent-elements"></a><span data-ttu-id="1b8e0-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b8e0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1b8e0-120">요소</span><span class="sxs-lookup"><span data-stu-id="1b8e0-120">Element</span></span>|<span data-ttu-id="1b8e0-121">설명</span><span class="sxs-lookup"><span data-stu-id="1b8e0-121">Description</span></span>|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|<span data-ttu-id="1b8e0-122">명명 된 인스턴스에 대 한 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-122">Contains a collection of configuration settings for the named <xref:System.Runtime.Caching.MemoryCache> instances.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b8e0-123">설명</span><span class="sxs-lookup"><span data-stu-id="1b8e0-123">Remarks</span></span>  

 <span data-ttu-id="1b8e0-124">`add`요소는 `namedCaches` 메모리 캐시의 컬렉션에 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-124">The `add` element adds an entry to the `namedCaches` collection for a memory cache.</span></span> <span data-ttu-id="1b8e0-125">요소를 사용 하기 전에 [clear](clear-element-for-namedcaches.md) 요소를 사용 하 여 `add` 컬렉션에 다른 명명 된 캐시가 없음을 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-125">You can use the [clear](clear-element-for-namedcaches.md) element before you use the `add` element to be certain that there are no other named caches in the collection.</span></span> <span data-ttu-id="1b8e0-126">이 요소는 machine.config 파일 및 Web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-126">This element can be used in the machine.config file and in the Web.config file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b8e0-127">예제</span><span class="sxs-lookup"><span data-stu-id="1b8e0-127">Example</span></span>  

 <span data-ttu-id="1b8e0-128">다음 예제에서는 `namedCache` `namedCaches` 메모리 캐시의 컬렉션에 대 한 기본 항목에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b8e0-128">The following example shows how to define settings for the default `namedCache` entry to the `namedCaches` collection for a memory cache.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b8e0-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b8e0-129">See also</span></span>

- [<span data-ttu-id="1b8e0-130">\<namedCaches> 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="1b8e0-130">\<namedCaches> Element (Cache Settings)</span></span>](namedcaches-element-cache-settings.md)
