---
title: GCHeapCount 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283080"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="de365-102">\<GCHeapCount > 요소</span><span class="sxs-lookup"><span data-stu-id="de365-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="de365-103">서버 가비지 수집에 사용할 힙/스레드 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

<span data-ttu-id="de365-104">\<구성 > </span><span class="sxs-lookup"><span data-stu-id="de365-104">\<configuration></span></span>\
<span data-ttu-id="de365-105">&nbsp;&nbsp;\<런타임 > </span><span class="sxs-lookup"><span data-stu-id="de365-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="de365-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount ></span><span class="sxs-lookup"><span data-stu-id="de365-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount></span></span>

## <a name="syntax"></a><span data-ttu-id="de365-107">구문</span><span class="sxs-lookup"><span data-stu-id="de365-107">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="de365-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="de365-108">Attributes and elements</span></span>

<span data-ttu-id="de365-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="de365-110">특성</span><span class="sxs-lookup"><span data-stu-id="de365-110">Attributes</span></span>

|<span data-ttu-id="de365-111">특성</span><span class="sxs-lookup"><span data-stu-id="de365-111">Attribute</span></span>|<span data-ttu-id="de365-112">설명</span><span class="sxs-lookup"><span data-stu-id="de365-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="de365-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="de365-113">Required attribute.</span></span><br /><br /><span data-ttu-id="de365-114">서버 가비지 수집에 사용할 힙 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-114">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="de365-115">실제 힙 수는 사용자가 지정 하는 힙 수와 프로세스에서 사용할 수 있는 프로세서 수의 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="de365-115">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="de365-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="de365-116">enabled attribute</span></span>

|<span data-ttu-id="de365-117">값</span><span class="sxs-lookup"><span data-stu-id="de365-117">Value</span></span>|<span data-ttu-id="de365-118">설명</span><span class="sxs-lookup"><span data-stu-id="de365-118">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="de365-119">서버 GC에 사용할 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="de365-119">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="de365-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="de365-120">Child elements</span></span>

<span data-ttu-id="de365-121">없음</span><span class="sxs-lookup"><span data-stu-id="de365-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="de365-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="de365-122">Parent elements</span></span>

|<span data-ttu-id="de365-123">요소</span><span class="sxs-lookup"><span data-stu-id="de365-123">Element</span></span>|<span data-ttu-id="de365-124">설명</span><span class="sxs-lookup"><span data-stu-id="de365-124">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="de365-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="de365-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="de365-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-126">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="de365-127">설명</span><span class="sxs-lookup"><span data-stu-id="de365-127">Remarks</span></span>

<span data-ttu-id="de365-128">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de365-128">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="de365-129">.NET Framework 4.6.2부터 **GCHeapCount** 요소를 사용 하 여 응용 프로그램에서 서버 GC에 사용 하는 힙 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de365-129">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="de365-130">서버 GC에 사용 되는 힙 수를 제한 하는 것은 서버 응용 프로그램의 여러 인스턴스를 실행 하는 시스템에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-130">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="de365-131">**GCHeapCount** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de365-131">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="de365-132">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-132">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="de365-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)-cpu를 사용 하 여 GC 스레드/힙의 선호도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-133">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="de365-134">**GCHeapCount** 를 설정 하 고 **GCNoAffinitize** 를 사용 하지 않도록 설정 하면 (기본 설정) *nn* GC 스레드/힙과 첫 번째 *nn* 프로세서 간에 선호도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de365-134">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="de365-135">**GCHeapAffinitizeMask** 요소를 사용 하 여 프로세스의 서버 GC 힙에서 사용 되는 프로세서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de365-135">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="de365-136">그렇지 않으면 여러 서버 프로세스가 시스템에서 실행 되는 경우 프로세서 사용이 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="de365-136">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="de365-137">**GCHeapCount** 이 설정 되 고 **GCNoAffinitize** 가 설정 된 경우 가비지 수집기는 서버 gc에 사용 되는 프로세서 수를 제한 하지만 gc 힙과 프로세서를 선호도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de365-137">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="de365-138">예제</span><span class="sxs-lookup"><span data-stu-id="de365-138">Example</span></span>

<span data-ttu-id="de365-139">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de365-139">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="de365-140">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de365-140">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="de365-141">다음 예에서는 서버 GC 스레드를 선호도 하 고 GC 힙/스레드 수를 10으로 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de365-141">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="de365-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="de365-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="de365-143">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="de365-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="de365-144">GCHeapAffinitizeMask 요소</span><span class="sxs-lookup"><span data-stu-id="de365-144">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="de365-145">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="de365-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="de365-146">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="de365-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="de365-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="de365-147">Configuration File Schema</span></span>](../index.md)
