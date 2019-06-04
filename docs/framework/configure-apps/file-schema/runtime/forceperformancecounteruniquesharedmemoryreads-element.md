---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26fed0a10b9a25f25a580c7ac9a468cbedeb3671
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489477"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="b2762-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="b2762-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="b2762-103">PerfCounter.dll이 .NET Framework 버전 1.1 애플리케이션에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="b2762-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b2762-104">\<configuration></span></span>  
<span data-ttu-id="b2762-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="b2762-105">\<runtime></span></span>  
<span data-ttu-id="b2762-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="b2762-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2762-107">구문</span><span class="sxs-lookup"><span data-stu-id="b2762-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b2762-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2762-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b2762-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b2762-110">특성</span><span class="sxs-lookup"><span data-stu-id="b2762-110">Attributes</span></span>  
  
|<span data-ttu-id="b2762-111">특성</span><span class="sxs-lookup"><span data-stu-id="b2762-111">Attribute</span></span>|<span data-ttu-id="b2762-112">설명</span><span class="sxs-lookup"><span data-stu-id="b2762-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b2762-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b2762-114">Perfcounter.dll이 성능 카운터 데이터를 범주별 공유 메모리 또는 전역 메모리에서 로드할지 여부를 확인 하려면 CategoryOptions 레지스트리 설정을 사용 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b2762-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="b2762-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b2762-116">값</span><span class="sxs-lookup"><span data-stu-id="b2762-116">Value</span></span>|<span data-ttu-id="b2762-117">설명</span><span class="sxs-lookup"><span data-stu-id="b2762-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b2762-118">Perfcounter.dll이 CategoryOptions를 사용 하지 않는 레지스트리 설정의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="b2762-119">Perfcounter.dll이 CategoryOptions 레지스트리 설정을 사용 하 여지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b2762-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2762-120">Child Elements</span></span>  
 <span data-ttu-id="b2762-121">없음</span><span class="sxs-lookup"><span data-stu-id="b2762-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b2762-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2762-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b2762-123">요소</span><span class="sxs-lookup"><span data-stu-id="b2762-123">Element</span></span>|<span data-ttu-id="b2762-124">설명</span><span class="sxs-lookup"><span data-stu-id="b2762-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b2762-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b2762-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2762-127">설명</span><span class="sxs-lookup"><span data-stu-id="b2762-127">Remarks</span></span>  
 <span data-ttu-id="b2762-128">Perfcounter.dll이 로드 된 버전이 프로세스에서 로드 된 런타임에 해당 하는.NET Framework 4 이전의.NET Framework의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="b2762-129">컴퓨터는.NET Framework 버전 1.1 했습니다 및 [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] 설치 된.NET Framework 1.1 응용 프로그램을 로드 perfcounter.dll이.NET Framework 1.1 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-129">If a computer had both the .NET Framework version 1.1 and the [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="b2762-130">.NET Framework 4 부터는 perfcounter.dll이 설치 된 최신 버전이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="b2762-131">이 컴퓨터에.NET Framework 4를 설치 하는 경우.NET Framework 1.1 응용 프로그램을 perfcounter.dll이.NET Framework 4 버전이 로드 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="b2762-132">Perfcounter.dll이.NET Framework 4부터 성능 카운터를 사용 하는 경우, 범주별 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 확인 하려면 각 공급자에 대 한 CategoryOptions 레지스트리 항목을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="b2762-133">범주별 공유 메모리를 인식 하지 않기 때문에.NET Framework 1.1 perfcounter.dll이 해당 레지스트리 항목을 읽지 못하는 항상 전역 공유 메모리에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="b2762-134">이전 버전과 호환성을 위해.NET Framework 4 perfcounter.dll이 확인 하지 않습니다 CategoryOptions 레지스트리 항목에서.NET Framework 1.1 응용 프로그램을 실행 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="b2762-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="b2762-135">단순히.NET Framework 1.1 perfcounter.dll이 처럼 전역 공유 메모리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="b2762-136">그러나 사용 하 여 레지스트리 설정을 확인 하려면.NET Framework 4 perfcounter.dll이 지시할 수 있습니다는 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2762-137">사용 하도록 설정 된 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소 범주별 공유 메모리 사용 됨을 보장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="b2762-138">사용 하는 설정과 `true` 만 perfcounter.dll이 CategoryOptions 레지스트리 설정을 참조를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="b2762-139">CategoryOptions의 기본 설정은 범주별 공유 메모리를 사용 하는 것 그러나 전역 공유 메모리를 사용 해야 함을 나타내려면 CategoryOptions를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="b2762-140">CategoryOptions 설정을 포함 하는 레지스트리 키가 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="b2762-141">기본적으로 CategoryOptions은 3으로 설정, perfcounter.dll이 지시 범주별 공유 메모리를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="b2762-142">CategoryOptions을 0으로 설정 하는 경우 perfcounter.dll이 전역 공유 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="b2762-143">생성 되는 인스턴스의 이름을 다시 사용 되는 인스턴스와 동일한 경우에 인스턴스 데이터 집합이 재사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="b2762-144">모든 버전의 범주를 쓸 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="b2762-145">CategoryOptions가 1로 설정 된 경우 전역 공유 메모리 크기를 사용 하지만 범주 이름을 다시 사용 되는 범주와 길이가 같은 경우에 인스턴스 데이터를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="b2762-146">0과 1 설정을 메모리 누수 및 가득 찰 성능 카운터 메모리가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2762-147">예제</span><span class="sxs-lookup"><span data-stu-id="b2762-147">Example</span></span>  
 <span data-ttu-id="b2762-148">다음 예제에서는 perfcounter.dll이 범주별 공유 메모리를 사용 해야 하는지 여부를 확인 하려면 CategoryOptions 레지스트리 항목을 참조 해야 하는지 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b2762-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b2762-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="b2762-149">See also</span></span>

- [<span data-ttu-id="b2762-150">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b2762-150">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b2762-151">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b2762-151">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
