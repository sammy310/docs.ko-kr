---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154142"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="34182-102">\<포스퍼포먼스카운터유니크공유메모리> 요소 읽기</span><span class="sxs-lookup"><span data-stu-id="34182-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="34182-103">PerfCounter.dll이 .NET Framework 버전 1.1 애플리케이션에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
<span data-ttu-id="34182-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34182-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34182-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="34182-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="34182-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<포스퍼포먼스카운터유니크공유메모리>**</span><span class="sxs-lookup"><span data-stu-id="34182-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34182-107">구문</span><span class="sxs-lookup"><span data-stu-id="34182-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34182-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34182-108">Attributes and Elements</span></span>  
 <span data-ttu-id="34182-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34182-110">특성</span><span class="sxs-lookup"><span data-stu-id="34182-110">Attributes</span></span>  
  
|<span data-ttu-id="34182-111">attribute</span><span class="sxs-lookup"><span data-stu-id="34182-111">Attribute</span></span>|<span data-ttu-id="34182-112">Description</span><span class="sxs-lookup"><span data-stu-id="34182-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34182-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="34182-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="34182-114">PerfCounter.dll이 카테고리별 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할지 여부를 결정하기 위해 CategoryOptions 레지스트리 설정을 사용하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34182-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="34182-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="34182-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="34182-116">값</span><span class="sxs-lookup"><span data-stu-id="34182-116">Value</span></span>|<span data-ttu-id="34182-117">Description</span><span class="sxs-lookup"><span data-stu-id="34182-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="34182-118">PerfCounter.dll 은 범주옵션 레지스트리를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="34182-119">PerfCounter.dll은 범주옵션 레지스트리 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34182-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34182-120">Child Elements</span></span>  
 <span data-ttu-id="34182-121">없음</span><span class="sxs-lookup"><span data-stu-id="34182-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34182-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34182-122">Parent Elements</span></span>  
  
|<span data-ttu-id="34182-123">요소</span><span class="sxs-lookup"><span data-stu-id="34182-123">Element</span></span>|<span data-ttu-id="34182-124">Description</span><span class="sxs-lookup"><span data-stu-id="34182-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34182-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34182-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34182-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34182-127">설명</span><span class="sxs-lookup"><span data-stu-id="34182-127">Remarks</span></span>  
 <span data-ttu-id="34182-128">.NET Framework 4 이전의 .NET Framework 버전에서는 로드된 PerfCounter.dll 버전이 프로세스에서 로드된 런타임에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="34182-129">컴퓨터에 .NET Framework 버전 1.1과 .NET Framework 2.0이 모두 설치된 경우 .NET Framework 1.1 응용 프로그램은 PerfCounter.dll의 .NET Framework 1.1 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="34182-130">.NET Framework 4부터 시작하여 PerfCounter.dll의 최신 설치 버전이 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="34182-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="34182-131">즉, .NET Framework 1.1 응용 프로그램은 .NET Framework 4가 컴퓨터에 설치된 경우 PerfCounter.dll의 .NET Framework 4 버전을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="34182-132">성능 카운터를 사용할 때 .NET Framework 4로 시작하여 PerfCounter.dll은 각 공급자에 대한 CategoryOptions 레지스트리 항목을 확인하여 범주별 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="34182-133">.NET Framework 1.1 PerfCounter.dll은 범주별 공유 메모리를 인식하지 못하기 때문에 해당 레지스트리 항목을 읽지 않습니다. 항상 전역 공유 메모리에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="34182-134">이전 버전과의 호환성을 위해 .NET Framework 4 PerfCounter.dll은 .NET Framework 1.1 응용 프로그램에서 실행할 때 CategoryOptions 레지스트리 항목을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="34182-135">.NET Framework 1.1 PerfCounter.dll과 마찬가지로 전역 공유 메모리를 사용하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34182-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="34182-136">그러나 .NET Framework 4 PerfCounter.dll요소를 사용하도록 설정하여 레지스트리 설정을 `<forcePerformanceCounterUniqueSharedMemoryReads>` 확인하도록 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34182-137">`<forcePerformanceCounterUniqueSharedMemoryReads>` 요소를 사용하도록 설정한다고 해서 범주별 공유 메모리가 사용될 것이라는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="34182-138">사용하도록 설정하면 `true` PerfCounter.dll이 범주옵션 레지스트리 설정을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="34182-139">범주옵션의 기본 설정은 범주별 공유 메모리를 사용하는 것입니다. 그러나 전역 공유 메모리를 사용해야 함을 나타내기 위해 CategoryOptions를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="34182-140">범주옵션 설정이 포함된 레지스트리 키는 HKEY_LOCAL_MACHINE\System\CurrentControlSet\서비스\\<\>범주이름 \성능입니다.</span><span class="sxs-lookup"><span data-stu-id="34182-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="34182-141">기본적으로 범주 옵션은 3으로 설정되어 PerfCounter.dll이 범주별 공유 메모리를 사용하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="34182-142">범주 옵션이 0으로 설정된 경우 PerfCounter.dll은 전역 공유 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34182-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="34182-143">인스턴스 데이터는 생성중인 인스턴스의 이름이 재사용되는 인스턴스와 동일한 경우에만 다시 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="34182-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="34182-144">모든 버전은 범주에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="34182-145">CategoryOptions가 1로 설정된 경우 전역 공유 메모리가 사용되지만 범주 이름이 재사용되는 범주와 동일한 길이인 경우 인스턴스 데이터를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="34182-146">설정 0과 1은 메모리 누수및 성능 카운터 메모리의 채우기로 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34182-147">예제</span><span class="sxs-lookup"><span data-stu-id="34182-147">Example</span></span>  
 <span data-ttu-id="34182-148">다음 예제에서는 PerfCounter.dll 범주별 공유 메모리를 사용해야 하는지 여부를 결정하기 위해 CategoryOptions 레지스트리 항목을 참조하도록 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34182-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34182-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34182-149">See also</span></span>

- [<span data-ttu-id="34182-150">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="34182-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34182-151">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="34182-151">Configuration File Schema</span></span>](../index.md)
