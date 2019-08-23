---
title: <forcePerformanceCounterUniqueSharedMemoryReads> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29fbe951b955c97e39ebaf80885729a45c1a3fd7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927389"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a><span data-ttu-id="3c26f-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span><span class="sxs-lookup"><span data-stu-id="3c26f-102">\<forcePerformanceCounterUniqueSharedMemoryReads> Element</span></span>
<span data-ttu-id="3c26f-103">PerfCounter.dll이 .NET Framework 버전 1.1 애플리케이션에서 CategoryOptions 레지스트리 설정을 사용하여 성능 카운터 데이터를 범주별 공유 메모리에서 로드할지 또는 전역 메모리에서 로드할지를 결정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-103">Specifies whether PerfCounter.dll uses the CategoryOptions registry setting in a .NET Framework version 1.1 application to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>  
  
 <span data-ttu-id="3c26f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3c26f-104">\<configuration></span></span>  
<span data-ttu-id="3c26f-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="3c26f-105">\<runtime></span></span>  
<span data-ttu-id="3c26f-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span><span class="sxs-lookup"><span data-stu-id="3c26f-106">\<forcePerformanceCounterUniqueSharedMemoryReads></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c26f-107">구문</span><span class="sxs-lookup"><span data-stu-id="3c26f-107">Syntax</span></span>  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c26f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3c26f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3c26f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c26f-110">특성</span><span class="sxs-lookup"><span data-stu-id="3c26f-110">Attributes</span></span>  
  
|<span data-ttu-id="3c26f-111">특성</span><span class="sxs-lookup"><span data-stu-id="3c26f-111">Attribute</span></span>|<span data-ttu-id="3c26f-112">설명</span><span class="sxs-lookup"><span data-stu-id="3c26f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="3c26f-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="3c26f-114">PerfCounter가 CategoryOptions 레지스트리 설정을 사용 하 여 범주 특정 공유 메모리 또는 전역 메모리에서 성능 카운터 데이터를 로드할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-114">Indicates whether PerfCounter.dll uses the CategoryOptions registry setting to determine whether to load performance counter data from category-specific shared memory or global memory.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3c26f-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="3c26f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="3c26f-116">값</span><span class="sxs-lookup"><span data-stu-id="3c26f-116">Value</span></span>|<span data-ttu-id="3c26f-117">설명</span><span class="sxs-lookup"><span data-stu-id="3c26f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="3c26f-118">PerfCounter는 CategoryOptions 레지스트리 설정을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-118">PerfCounter.dll does not use the CategoryOptions registry setting This is the default.</span></span>|  
|`true`|<span data-ttu-id="3c26f-119">PerfCounter는 CategoryOptions 레지스트리 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-119">PerfCounter.dll does use the CategoryOptions registry setting.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c26f-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3c26f-120">Child Elements</span></span>  
 <span data-ttu-id="3c26f-121">없음</span><span class="sxs-lookup"><span data-stu-id="3c26f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c26f-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3c26f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3c26f-123">요소</span><span class="sxs-lookup"><span data-stu-id="3c26f-123">Element</span></span>|<span data-ttu-id="3c26f-124">설명</span><span class="sxs-lookup"><span data-stu-id="3c26f-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3c26f-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3c26f-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c26f-127">설명</span><span class="sxs-lookup"><span data-stu-id="3c26f-127">Remarks</span></span>  
 <span data-ttu-id="3c26f-128">.NET Framework 4 이전의 .NET Framework 버전에서는 로드 된 PerfCounter의 버전이 프로세스에 로드 된 런타임으로 속하는지를.</span><span class="sxs-lookup"><span data-stu-id="3c26f-128">In versions of the .NET Framework before the .NET Framework 4, the version of PerfCounter.dll that was loaded corresponded to the runtime that was loaded in the process.</span></span> <span data-ttu-id="3c26f-129">컴퓨터에 .NET Framework 버전 1.1 및 .NET Framework 2.0이 모두 설치 되어 있는 경우 .NET Framework 1.1 응용 프로그램은 .NET Framework 1.1 버전의 PerfCounter를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-129">If a computer had both the .NET Framework version 1.1 and the .NET Framework 2.0 installed, a .NET Framework 1.1 application would load the .NET Framework 1.1 version of PerfCounter.dll.</span></span> <span data-ttu-id="3c26f-130">.NET Framework 4부터 설치 된 PerfCounter의 최신 버전이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-130">Starting with the .NET Framework 4, the newest installed version of PerfCounter.dll is loaded.</span></span> <span data-ttu-id="3c26f-131">즉, 컴퓨터에 .NET Framework 4가 설치 된 경우 .NET Framework 1.1 응용 프로그램에서 PerfCounter의 .NET Framework 4 버전이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-131">This means that a .NET Framework 1.1 application will load the .NET Framework 4 version of PerfCounter.dll if the .NET Framework 4 is installed on the computer.</span></span>  
  
 <span data-ttu-id="3c26f-132">.NET Framework 4부터 성능 카운터를 사용할 때 PerfCounter는 각 공급자에 대 한 CategoryOptions 레지스트리 항목을 확인 하 여 범주 특정 공유 메모리 또는 전역 공유 메모리에서 읽어야 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-132">Starting with the .NET Framework 4, when consuming performance counters, PerfCounter.dll checks the CategoryOptions registry entry for each provider to determine whether it should read from category-specific shared memory or global shared memory.</span></span> <span data-ttu-id="3c26f-133">.NET Framework 1.1 PerfCounter는 범주 관련 공유 메모리를 인식 하지 못하기 때문에 해당 레지스트리 항목을 읽지 않습니다. 전역 공유 메모리에서 항상 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-133">The .NET Framework 1.1 PerfCounter.dll does not read that registry entry, because it is not aware of category-specific shared memory; it always reads from global shared memory.</span></span>  
  
 <span data-ttu-id="3c26f-134">이전 버전과의 호환성을 위해 .NET Framework 4 PerfCounter는 .NET Framework 1.1 응용 프로그램에서 실행 될 때 CategoryOptions 레지스트리 항목을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-134">For backward compatibility, the .NET Framework 4 PerfCounter.dll does not check the CategoryOptions registry entry when running in a .NET Framework 1.1 application.</span></span> <span data-ttu-id="3c26f-135">.NET Framework 1.1 PerfCounter와 마찬가지로 전역 공유 메모리를 사용 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-135">It simply uses global shared memory, just like the .NET Framework 1.1 PerfCounter.dll.</span></span> <span data-ttu-id="3c26f-136">그러나 `<forcePerformanceCounterUniqueSharedMemoryReads>` 요소를 사용 하도록 설정 하 여 레지스트리 설정을 확인 하도록 .NET Framework 4 PerfCounter에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-136">However, you can instruct the .NET Framework 4 PerfCounter.dll to check the registry setting by enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3c26f-137">요소를 `<forcePerformanceCounterUniqueSharedMemoryReads>` 사용 하도록 설정 해도 범주 관련 공유 메모리가 사용 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-137">Enabling the `<forcePerformanceCounterUniqueSharedMemoryReads>` element does not guarantee that category-specific shared memory will be used.</span></span> <span data-ttu-id="3c26f-138">Enabled를로 `true` 설정 하면 PerfCounter가 categoryoptions 레지스트리 설정을 참조 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-138">Setting enabled to `true` only causes PerfCounter.dll to reference the CategoryOptions registry setting.</span></span> <span data-ttu-id="3c26f-139">CategoryOptions의 기본 설정은 범주 관련 공유 메모리를 사용 하는 것입니다. 그러나 CategoryOptions를 변경 하 여 전역 공유 메모리를 사용 해야 함을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-139">The default setting for CategoryOptions is to use category-specific shared memory; however, you can change CategoryOptions to indicate that global shared memory should be used.</span></span>  
  
 <span data-ttu-id="3c26f-140">Categoryoptions 설정이 포함 된 레지스트리 키는 HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< 범주 \Performance.\></span><span class="sxs-lookup"><span data-stu-id="3c26f-140">The registry key that contains the CategoryOptions setting is HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\<categoryName\>\Performance.</span></span> <span data-ttu-id="3c26f-141">기본적으로 CategoryOptions는 3으로 설정 되며,이는 PerfCounter에 범주 관련 공유 메모리를 사용 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-141">By default, CategoryOptions is set to 3, which instructs PerfCounter.dll to use category-specific shared memory.</span></span> <span data-ttu-id="3c26f-142">CategoryOptions가 0으로 설정 된 경우 PerfCounter는 전역 공유 메모리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-142">If CategoryOptions is set to 0, PerfCounter.dll uses global shared memory.</span></span> <span data-ttu-id="3c26f-143">인스턴스 데이터는 생성 중인 인스턴스의 이름이 다시 사용 중인 인스턴스와 동일한 경우에만 다시 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-143">Instance data will be reused only if the name of the instance being created is identical to the instance being reused.</span></span> <span data-ttu-id="3c26f-144">모든 버전은 범주에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-144">All versions will be able to write to the category.</span></span> <span data-ttu-id="3c26f-145">CategoryOptions를 1로 설정 하면 전역 공유 메모리가 사용 되지만 범주 이름이 다시 사용 하는 범주와 동일한 경우 인스턴스 데이터를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-145">If CategoryOptions is set to 1, global shared memory is used, but instance data can be reused if the category name is the same length as the category being reused.</span></span>  
  
 <span data-ttu-id="3c26f-146">설정 0 및 1은 메모리 누수를 야기 하 고 성능 카운터 메모리를 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-146">The settings 0 and 1 can lead to memory leaks and the filling up of performance counter memory.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c26f-147">예제</span><span class="sxs-lookup"><span data-stu-id="3c26f-147">Example</span></span>  
 <span data-ttu-id="3c26f-148">다음 예제에서는 PerfCounter에서 CategoryOptions 레지스트리 항목을 참조 하 여 범주 관련 공유 메모리를 사용 해야 하는지 여부를 확인 하도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3c26f-148">The following example shows how to specify that PerfCounter.dll should reference the CategoryOptions registry entry to determine whether it should use category-specific shared memory.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c26f-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="3c26f-149">See also</span></span>

- [<span data-ttu-id="3c26f-150">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3c26f-150">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3c26f-151">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3c26f-151">Configuration File Schema</span></span>](../index.md)
