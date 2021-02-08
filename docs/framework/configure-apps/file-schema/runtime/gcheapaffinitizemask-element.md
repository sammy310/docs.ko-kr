---
description: '다음에 대 한 자세한 정보: <GCHeapAffinitizeMask> 요소'
title: GCHeapAffinitizeMask 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: ea6be3fa3d973f228576db69d0700b1f7ddba585
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786982"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="f21b3-103">\<GCHeapAffinitizeMask> 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-103">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="f21b3-104">GC 힙과 개별 프로세서 간의 선호도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-104">Defines the affinity between GC heaps and individual processors.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a><span data-ttu-id="f21b3-105">구문</span><span class="sxs-lookup"><span data-stu-id="f21b3-105">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f21b3-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-106">Attributes and elements</span></span>

<span data-ttu-id="f21b3-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f21b3-108">특성</span><span class="sxs-lookup"><span data-stu-id="f21b3-108">Attributes</span></span>

|<span data-ttu-id="f21b3-109">attribute</span><span class="sxs-lookup"><span data-stu-id="f21b3-109">Attribute</span></span>|<span data-ttu-id="f21b3-110">설명</span><span class="sxs-lookup"><span data-stu-id="f21b3-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f21b3-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-111">Required attribute.</span></span><br /><br /><span data-ttu-id="f21b3-112">GC 힙과 개별 프로세서 간의 선호도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-112">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="f21b3-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="f21b3-113">enabled attribute</span></span>

|<span data-ttu-id="f21b3-114">값</span><span class="sxs-lookup"><span data-stu-id="f21b3-114">Value</span></span>|<span data-ttu-id="f21b3-115">설명</span><span class="sxs-lookup"><span data-stu-id="f21b3-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="f21b3-116">서버 GC 힙과 개별 프로세서 간의 선호도를 정의 하는 비트 마스크를 형성 하는 10 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-116">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="f21b3-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-117">Child elements</span></span>

<span data-ttu-id="f21b3-118">없음</span><span class="sxs-lookup"><span data-stu-id="f21b3-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f21b3-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-119">Parent elements</span></span>

|<span data-ttu-id="f21b3-120">요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-120">Element</span></span>|<span data-ttu-id="f21b3-121">설명</span><span class="sxs-lookup"><span data-stu-id="f21b3-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f21b3-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f21b3-123">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f21b3-124">설명</span><span class="sxs-lookup"><span data-stu-id="f21b3-124">Remarks</span></span>

<span data-ttu-id="f21b3-125">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-125">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="f21b3-126">.NET Framework 4.6.2 부터는 **GCHeapAffinitizeMask** 요소를 사용 하 여 힙 수가 **GCHeapCount** 요소에 의해 제한 되는 경우 서버 GC 힙과 프로세서 간의 선호도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-126">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="f21b3-127">**GCHeapAffinitizeMask** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-127">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="f21b3-128">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-128">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="f21b3-129">`enabled` [GCNoAffinitize](gcnoaffinitize-element.md) 요소의 특성은 `false` 사용할 **GCHeapAffinitizeMask** 설정에 대해 (기본값) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-129">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="f21b3-130">[GCHeapCount](gcheapcount-element.md)-서버 GC에 대해 프로세스에서 사용 하는 힙 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-130">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="f21b3-131">기본적으로 각 프로세서에 대해 하나의 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-131">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="f21b3-132">**nnnn** 은 10 진수 값으로 표현 되는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-132">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="f21b3-133">바이트 0의 비트 0은 프로세서 0, 바이트 0의 비트 1은 프로세서 1을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-133">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="f21b3-134">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="f21b3-134">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="f21b3-135">1023 값은 0x3FF 또는 0011 1111 1111b입니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-135">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="f21b3-136">프로세스는 프로세서 0부터 프로세서 9까지 10 개의 프로세서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-136">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="f21b3-137">예제</span><span class="sxs-lookup"><span data-stu-id="f21b3-137">Example</span></span>

<span data-ttu-id="f21b3-138">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-138">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="f21b3-139">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f21b3-139">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f21b3-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f21b3-140">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f21b3-141">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-141">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="f21b3-142">GCHeapCount 요소</span><span class="sxs-lookup"><span data-stu-id="f21b3-142">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="f21b3-143">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f21b3-143">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="f21b3-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f21b3-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f21b3-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f21b3-145">Configuration File Schema</span></span>](../index.md)
