---
description: '자세한 정보: <> 요소 (캐시 설정)'
title: <system.runtime.caching> 요소(캐시 설정)
ms.date: 03/30/2017
helpviewer_keywords:
- <system.runtime.caching> element
- caching [.NET Framework], configuration
- system.runtime.caching element
ms.assetid: 9b44daee-874a-4bd1-954e-83bf53565590
ms.openlocfilehash: 602d863caedef5c1334948b25b0caa2b0e35f685
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652733"
---
# <a name="systemruntimecaching-element-cache-settings"></a><span data-ttu-id="44e23-103">\<system.runtime.caching> 요소(캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="44e23-103">\<system.runtime.caching> Element (Cache Settings)</span></span>

<span data-ttu-id="44e23-104">구성 파일의 <xref:System.Runtime.Caching.ObjectCache> 항목을 통해 기본 메모리 내 `memoryCache` 구현을 위한 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-104">Provides configuration for the default in-memory <xref:System.Runtime.Caching.ObjectCache> implementation through the `memoryCache` entry in the configuration file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.runtime.caching>**  
  
## <a name="syntax"></a><span data-ttu-id="44e23-105">구문</span><span class="sxs-lookup"><span data-stu-id="44e23-105">Syntax</span></span>  
  
```xml  
<system.runtime.caching >  
   <!-- child elements -->  
</system.runtime.caching >  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44e23-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44e23-106">Attributes and Elements</span></span>

<span data-ttu-id="44e23-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44e23-108">특성</span><span class="sxs-lookup"><span data-stu-id="44e23-108">Attributes</span></span>

`None`  

### <a name="child-elements"></a><span data-ttu-id="44e23-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44e23-109">Child Elements</span></span>

|<span data-ttu-id="44e23-110">요소</span><span class="sxs-lookup"><span data-stu-id="44e23-110">Element</span></span>|<span data-ttu-id="44e23-111">설명</span><span class="sxs-lookup"><span data-stu-id="44e23-111">Description</span></span>|  
|-------------|-----------------|  
|[\<memoryCache>](memorycache-element-cache-settings.md)|<span data-ttu-id="44e23-112"><xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 하는 캐시 구성에 사용되는 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-112">Defines an element that is used to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="44e23-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44e23-113">Parent Elements</span></span>  
  
|<span data-ttu-id="44e23-114">요소</span><span class="sxs-lookup"><span data-stu-id="44e23-114">Element</span></span>|<span data-ttu-id="44e23-115">설명</span><span class="sxs-lookup"><span data-stu-id="44e23-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="44e23-116">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용 하는 모든 구성 파일의 루트 요소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44e23-117">설명</span><span class="sxs-lookup"><span data-stu-id="44e23-117">Remarks</span></span>

<span data-ttu-id="44e23-118">이 네임스페이스의 클래스는 ASP.NET에 있는 것 같은 캐싱 기능을 사용하는(그러나 `System.Web` 어셈블리에 의존하지 않음) 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-118">The classes in this namespace provide a way to use caching facilities like those in ASP.NET, but without a dependency on the `System.Web` assembly.</span></span> <span data-ttu-id="44e23-119">자세한 내용은 [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="44e23-119">For more information, see [Caching in .NET Framework Applications](../../../performance/caching-in-net-framework-applications.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44e23-120">네임 스페이스의 출력 캐싱 기능 및 형식은 <xref:System.Runtime.Caching> .NET Framework 4의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-120">The output caching functionality and types in the <xref:System.Runtime.Caching> namespace are new in .NET Framework 4.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e23-121">예제</span><span class="sxs-lookup"><span data-stu-id="44e23-121">Example</span></span>

<span data-ttu-id="44e23-122">다음 예제는 <xref:System.Runtime.Caching.MemoryCache> 클래스를 기반으로 캐시를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-122">The following example shows how to configure a cache that is based on the <xref:System.Runtime.Caching.MemoryCache> class.</span></span> <span data-ttu-id="44e23-123">또한 메모리 캐시를 위한 `namedCaches` 항목의 인스턴스를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-123">The example shows how to configure an instance of the `namedCaches` entry for memory cache.</span></span> <span data-ttu-id="44e23-124">`name`특성을 "기본값"으로 설정 하 여 캐시 이름이 기본 캐시 항목 이름으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-124">The name of the cache is set to the default cache entry name by setting the `name` attribute to "Default".</span></span>  
  
<span data-ttu-id="44e23-125">`cacheMemoryLimitMegabytes` 특성 및 `physicalMemoryPercentage` 특성은 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-125">The `cacheMemoryLimitMegabytes` attribute and the `physicalMemoryPercentage` attribute are set to zero.</span></span> <span data-ttu-id="44e23-126">이러한 특성을 0으로 설정하면 기본적으로 <xref:System.Runtime.Caching.MemoryCache> 자동 크기 조정 추론이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-126">Setting these attributes to zero means that the <xref:System.Runtime.Caching.MemoryCache> autosizing heuristics are used by default.</span></span> <span data-ttu-id="44e23-127">캐시 구현에서는 현재 메모리 로드가 절대 및 백분율 기반 메모리 제한과 2분마다 비교됩니다.</span><span class="sxs-lookup"><span data-stu-id="44e23-127">The cache implementation should compare the current memory load against the absolute and percentage-based memory limits every two minutes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="44e23-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44e23-128">See also</span></span>

- [<span data-ttu-id="44e23-129">\<memoryCache> 요소 (캐시 설정)</span><span class="sxs-lookup"><span data-stu-id="44e23-129">\<memoryCache> Element (Cache Settings)</span></span>](memorycache-element-cache-settings.md)
