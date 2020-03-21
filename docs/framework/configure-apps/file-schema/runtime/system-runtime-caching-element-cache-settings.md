---
title: <system.runtime.caching> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: df4887c8801dcf8af06b3826673a03cbc7dbc9b5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153856"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="33511-102">\<system.runtime.캐싱> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="33511-102">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="33511-103">구성 파일의 <xref:System.Runtime.Caching.ObjectCache> 항목을 통해 기본 메모리 내 `memoryCache` 구현을 위한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33511-103">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
<span data-ttu-id="33511-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33511-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33511-105">&nbsp;&nbsp;**\<system.runtime.캐싱>**</span><span class="sxs-lookup"><span data-stu-id="33511-105">&nbsp;&nbsp;**\<system.runtime.caching>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33511-106">구문</span><span class="sxs-lookup"><span data-stu-id="33511-106">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33511-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33511-107">Attributes and Elements</span></span>

<span data-ttu-id="33511-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33511-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33511-109">특성</span><span class="sxs-lookup"><span data-stu-id="33511-109">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="33511-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33511-110">Child Elements</span></span>

|<span data-ttu-id="33511-111">요소</span><span class="sxs-lookup"><span data-stu-id="33511-111">Element</span></span>|<span data-ttu-id="33511-112">Description</span><span class="sxs-lookup"><span data-stu-id="33511-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33511-113">\<메모리 캐시></span><span class="sxs-lookup"><span data-stu-id="33511-113">\<memoryCache></span></span>](memorycache-element-cache-settings.md)|<span data-ttu-id="33511-114"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="33511-114">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33511-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33511-115">Parent Elements</span></span>  
  
|<span data-ttu-id="33511-116">요소</span><span class="sxs-lookup"><span data-stu-id="33511-116">Element</span></span>|<span data-ttu-id="33511-117">Description</span><span class="sxs-lookup"><span data-stu-id="33511-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33511-118">\<구성></span><span class="sxs-lookup"><span data-stu-id="33511-118">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="33511-119">공통 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33511-119">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33511-120">설명</span><span class="sxs-lookup"><span data-stu-id="33511-120">Remarks</span></span>

<span data-ttu-id="33511-121">이 네임스페이스의 클래스는 ASP.NET에 있는 것 같은 캐싱 기능을 사용하는(그러나 `System.Web` 어셈블리에 의존하지 않음) 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="33511-121">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="33511-122">자세한 내용은 [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="33511-122">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="33511-123">네임스페이스의 <xref:System.Runtime.Caching> 출력 캐싱 기능 및 형식은 .NET Framework 4의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="33511-123">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33511-124">예제</span><span class="sxs-lookup"><span data-stu-id="33511-124">Example</span></span>

<span data-ttu-id="33511-125">다음 예제는 <xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 캐시를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33511-125">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="33511-126">또한 메모리 캐시를 위한 `namedCaches` 항목의 인스턴스를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33511-126">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="33511-127">캐시 의 이름은 `name` 특성을 "기본값"으로 설정하여 기본 캐시 항목 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33511-127">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="33511-128">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="33511-128">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="33511-129">이러한 특성을 0으로 설정하면 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 자동 크기 조정 추론이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33511-129">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="33511-130">캐시 구현에서는 현재 메모리 로드가 절대 및 백분율 기반 메모리 제한과 2분마다 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="33511-130">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
```xml  
<configuration>  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="Default"
               cacheMemoryLimitMegabytes="0"
               physicalMemoryLimitPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33511-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33511-131">See also</span></span>

- [<span data-ttu-id="33511-132">\<메모리캐시> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="33511-132">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
