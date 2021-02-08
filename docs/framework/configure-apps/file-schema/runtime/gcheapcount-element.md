---
description: '다음에 대 한 자세한 정보: <GCHeapCount> 요소'
title: GCHeapCount 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 9e1e000d647435fe7a8c4b1a8f7549f06c2a3b38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786969"
---
# <a name="gcheapcount-element"></a><span data-ttu-id="b122f-103">\<GCHeapCount> 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-103">\<GCHeapCount> element</span></span>

<span data-ttu-id="b122f-104">서버 가비지 수집에 사용할 힙/스레드 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-104">Specifies the number of heaps/threads to use for server garbage collection.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a><span data-ttu-id="b122f-105">구문</span><span class="sxs-lookup"><span data-stu-id="b122f-105">Syntax</span></span>

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b122f-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-106">Attributes and elements</span></span>

<span data-ttu-id="b122f-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b122f-108">특성</span><span class="sxs-lookup"><span data-stu-id="b122f-108">Attributes</span></span>

|<span data-ttu-id="b122f-109">attribute</span><span class="sxs-lookup"><span data-stu-id="b122f-109">Attribute</span></span>|<span data-ttu-id="b122f-110">설명</span><span class="sxs-lookup"><span data-stu-id="b122f-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b122f-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-111">Required attribute.</span></span><br /><br /><span data-ttu-id="b122f-112">서버 가비지 수집에 사용할 힙 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-112">Specifies the number of heaps to use for server garbage collection.</span></span> <span data-ttu-id="b122f-113">실제 힙 수는 사용자가 지정 하는 힙 수와 프로세스에서 사용할 수 있는 프로세서 수의 최소값입니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-113">The actual number of heaps is the minimum of the number of heaps you specify and the number of processors your process is allowed to use.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="b122f-114">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="b122f-114">enabled attribute</span></span>

|<span data-ttu-id="b122f-115">값</span><span class="sxs-lookup"><span data-stu-id="b122f-115">Value</span></span>|<span data-ttu-id="b122f-116">설명</span><span class="sxs-lookup"><span data-stu-id="b122f-116">Description</span></span>|
|-----------|-----------------|
|`nn`|<span data-ttu-id="b122f-117">서버 GC에 사용할 힙 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-117">The number of heaps to use for server GC.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b122f-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-118">Child elements</span></span>

<span data-ttu-id="b122f-119">없음</span><span class="sxs-lookup"><span data-stu-id="b122f-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b122f-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-120">Parent elements</span></span>

|<span data-ttu-id="b122f-121">요소</span><span class="sxs-lookup"><span data-stu-id="b122f-121">Element</span></span>|<span data-ttu-id="b122f-122">설명</span><span class="sxs-lookup"><span data-stu-id="b122f-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b122f-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b122f-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b122f-125">설명</span><span class="sxs-lookup"><span data-stu-id="b122f-125">Remarks</span></span>

<span data-ttu-id="b122f-126">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-126">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="b122f-127">.NET Framework 4.6.2부터 **GCHeapCount** 요소를 사용 하 여 응용 프로그램에서 서버 GC에 사용 하는 힙 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-127">Starting with .NET Framework 4.6.2, you can use the **GCHeapCount** element to limit the number of heaps used by your application for server GC.</span></span> <span data-ttu-id="b122f-128">서버 GC에 사용 되는 힙 수를 제한 하는 것은 서버 응용 프로그램의 여러 인스턴스를 실행 하는 시스템에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-128">Limiting the number of heaps used for server GC is particularly useful for systems that run multiple instances of a server application.</span></span>

<span data-ttu-id="b122f-129">**GCHeapCount** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-129">**GCHeapCount** is typically used along with two other flags:</span></span>

- <span data-ttu-id="b122f-130">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span>

- <span data-ttu-id="b122f-131">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)-cpu를 사용 하 여 GC 스레드/힙의 선호도를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-131">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which controls the affinity of GC threads/heaps with CPUs.</span></span>

<span data-ttu-id="b122f-132">**GCHeapCount** 를 설정 하 고 **GCNoAffinitize** 를 사용 하지 않도록 설정 하면 (기본 설정) *nn* GC 스레드/힙과 첫 번째 *nn* 프로세서 간에 선호도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-132">If **GCHeapCount** is set and **GCNoAffinitize** is disabled (its default setting), there is an affinity between the *nn* GC threads/heaps and the first *nn* processors.</span></span> <span data-ttu-id="b122f-133">**GCHeapAffinitizeMask** 요소를 사용 하 여 프로세스의 서버 GC 힙에서 사용 되는 프로세서를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-133">You can use the **GCHeapAffinitizeMask** element to specify which processors are used by the process's server GC heaps.</span></span> <span data-ttu-id="b122f-134">그렇지 않으면 여러 서버 프로세스가 시스템에서 실행 되는 경우 프로세서 사용이 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-134">Otherwise, if multiple server processes are running on a system, their processor usage will overlap.</span></span>

<span data-ttu-id="b122f-135">**GCHeapCount** 이 설정 되 고 **GCNoAffinitize** 가 설정 된 경우 가비지 수집기는 서버 gc에 사용 되는 프로세서 수를 제한 하지만 gc 힙과 프로세서를 선호도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-135">If **GCHeapCount** is set and **GCNoAffinitize** is enabled, the garbage collector limits the number of processors used for server GC but does not affinitize GC heaps and processors.</span></span>

## <a name="example"></a><span data-ttu-id="b122f-136">예제</span><span class="sxs-lookup"><span data-stu-id="b122f-136">Example</span></span>

<span data-ttu-id="b122f-137">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-137">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="b122f-138">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-138">Since you don't want those heaps to overlap with heaps from other applications running on the system, you use the **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

<span data-ttu-id="b122f-139">다음 예에서는 서버 GC 스레드를 선호도 하 고 GC 힙/스레드 수를 10으로 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b122f-139">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b122f-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b122f-140">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="b122f-141">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-141">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="b122f-142">GCHeapAffinitizeMask 요소</span><span class="sxs-lookup"><span data-stu-id="b122f-142">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="b122f-143">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="b122f-143">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="b122f-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b122f-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b122f-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b122f-145">Configuration File Schema</span></span>](../index.md)
