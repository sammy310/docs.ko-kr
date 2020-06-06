---
title: GCHeapCount 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 3d6cac4185af182758cb82e6bfd9d96ed24869b4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74283080"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="27333-102">\<GCHeapCount> 요소</span><span class="sxs-lookup"><span data-stu-id="27333-102">\<GCHeapCount> element</span></span>

<span data-ttu-id="27333-103">서버 가비지 수집에 사용할 힙/스레드 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-103">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="27333-104">구문</span><span class="sxs-lookup"><span data-stu-id="27333-104">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="27333-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="27333-105">Attributes and elements</span></span>

<span data-ttu-id="27333-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="27333-107">특성</span><span class="sxs-lookup"><span data-stu-id="27333-107">Attributes</span></span>

|<span data-ttu-id="27333-108">attribute</span><span class="sxs-lookup"><span data-stu-id="27333-108">Attribute</span></span>|<span data-ttu-id="27333-109">Description</span><span class="sxs-lookup"><span data-stu-id="27333-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="27333-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="27333-110">Required attribute.</span></span><br /><br /><span data-ttu-id="27333-111">서버 가비지 수집에 사용할 힙 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-111">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="27333-112">실제 힙 수는 사용자가 지정 하는 힙 수와 프로세스에서 사용할 수 있는 프로세서 수의 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="27333-112">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="27333-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="27333-113">enabled attribute</span></span>

|<span data-ttu-id="27333-114">값</span><span class="sxs-lookup"><span data-stu-id="27333-114">Value</span></span>|<span data-ttu-id="27333-115">Description</span><span class="sxs-lookup"><span data-stu-id="27333-115">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="27333-116">서버 GC에 사용할 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="27333-116">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="27333-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="27333-117">Child elements</span></span>

<span data-ttu-id="27333-118">없음</span><span class="sxs-lookup"><span data-stu-id="27333-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="27333-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="27333-119">Parent elements</span></span>

|<span data-ttu-id="27333-120">요소</span><span class="sxs-lookup"><span data-stu-id="27333-120">Element</span></span>|<span data-ttu-id="27333-121">Description</span><span class="sxs-lookup"><span data-stu-id="27333-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="27333-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="27333-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="27333-123">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="27333-124">설명</span><span class="sxs-lookup"><span data-stu-id="27333-124">Remarks</span></span>

<span data-ttu-id="27333-125">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27333-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="27333-126">.NET Framework 4.6.2부터 **GCHeapCount** 요소를 사용 하 여 응용 프로그램에서 서버 GC에 사용 하는 힙 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27333-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="27333-127">서버 GC에 사용 되는 힙 수를 제한 하는 것은 서버 응용 프로그램의 여러 인스턴스를 실행 하는 시스템에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-127">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="27333-128">**GCHeapCount** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27333-128">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="27333-129">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-129">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="27333-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)-cpu를 사용 하 여 GC 스레드/힙의 선호도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-130">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="27333-131">**GCHeapCount** 를 설정 하 고 **GCNoAffinitize** 를 사용 하지 않도록 설정 하면 (기본 설정) *nn* GC 스레드/힙과 첫 번째 *nn* 프로세서 간에 선호도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27333-131">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="27333-132">**GCHeapAffinitizeMask** 요소를 사용 하 여 프로세스의 서버 GC 힙에서 사용 되는 프로세서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27333-132">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="27333-133">그렇지 않으면 여러 서버 프로세스가 시스템에서 실행 되는 경우 프로세서 사용이 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="27333-133">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="27333-134">**GCHeapCount** 이 설정 되 고 **GCNoAffinitize** 가 설정 된 경우 가비지 수집기는 서버 gc에 사용 되는 프로세서 수를 제한 하지만 gc 힙과 프로세서를 선호도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27333-134">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="27333-135">예제</span><span class="sxs-lookup"><span data-stu-id="27333-135">Example</span></span>

<span data-ttu-id="27333-136">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27333-136">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="27333-137">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27333-137">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="27333-138">다음 예에서는 서버 GC 스레드를 선호도 하 고 GC 힙/스레드 수를 10으로 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27333-138">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="27333-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27333-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="27333-140">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="27333-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="27333-141">GCHeapAffinitizeMask 요소</span><span class="sxs-lookup"><span data-stu-id="27333-141">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="27333-142">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="27333-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="27333-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="27333-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="27333-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="27333-144">Configuration File Schema</span></span>](../index.md)
