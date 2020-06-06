---
title: GCHeapAffinitizeMask 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73978422"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="8d50e-102">\<GCHeapAffinitizeMask> 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="8d50e-103">GC 힙과 개별 프로세서 간의 선호도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-103">Defines the affinity between GC heaps and individual processors.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a><span data-ttu-id="8d50e-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d50e-104">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8d50e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-105">Attributes and elements</span></span>

<span data-ttu-id="8d50e-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d50e-107">특성</span><span class="sxs-lookup"><span data-stu-id="8d50e-107">Attributes</span></span>

|<span data-ttu-id="8d50e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="8d50e-108">Attribute</span></span>|<span data-ttu-id="8d50e-109">Description</span><span class="sxs-lookup"><span data-stu-id="8d50e-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="8d50e-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-110">Required attribute.</span></span><br /><br /><span data-ttu-id="8d50e-111">GC 힙과 개별 프로세서 간의 선호도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-111">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="8d50e-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="8d50e-112">enabled attribute</span></span>

|<span data-ttu-id="8d50e-113">값</span><span class="sxs-lookup"><span data-stu-id="8d50e-113">Value</span></span>|<span data-ttu-id="8d50e-114">Description</span><span class="sxs-lookup"><span data-stu-id="8d50e-114">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="8d50e-115">서버 GC 힙과 개별 프로세서 간의 선호도를 정의 하는 비트 마스크를 형성 하는 10 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-115">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="8d50e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-116">Child elements</span></span>

<span data-ttu-id="8d50e-117">없음</span><span class="sxs-lookup"><span data-stu-id="8d50e-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8d50e-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-118">Parent elements</span></span>

|<span data-ttu-id="8d50e-119">요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-119">Element</span></span>|<span data-ttu-id="8d50e-120">Description</span><span class="sxs-lookup"><span data-stu-id="8d50e-120">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="8d50e-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="8d50e-122">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-122">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8d50e-123">설명</span><span class="sxs-lookup"><span data-stu-id="8d50e-123">Remarks</span></span>

<span data-ttu-id="8d50e-124">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-124">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="8d50e-125">.NET Framework 4.6.2 부터는 **GCHeapAffinitizeMask** 요소를 사용 하 여 힙 수가 **GCHeapCount** 요소에 의해 제한 되는 경우 서버 GC 힙과 프로세서 간의 선호도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-125">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="8d50e-126">**GCHeapAffinitizeMask** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-126">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="8d50e-127">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-127">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="8d50e-128">`enabled` [GCNoAffinitize](gcnoaffinitize-element.md) 요소의 특성은 `false` 사용할 **GCHeapAffinitizeMask** 설정에 대해 (기본값) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-128">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="8d50e-129">[GCHeapCount](gcheapcount-element.md)-서버 GC에 대해 프로세스에서 사용 하는 힙 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-129">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="8d50e-130">기본적으로 각 프로세서에 대해 하나의 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-130">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="8d50e-131">**nnnn** 은 10 진수 값으로 표현 되는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-131">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="8d50e-132">바이트 0의 비트 0은 프로세서 0, 바이트 0의 비트 1은 프로세서 1을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-132">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="8d50e-133">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-133">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="8d50e-134">1023 값은 0x3FF 또는 0011 1111 1111b입니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-134">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="8d50e-135">프로세스는 프로세서 0부터 프로세서 9까지 10 개의 프로세서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-135">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="8d50e-136">예제</span><span class="sxs-lookup"><span data-stu-id="8d50e-136">Example</span></span>

<span data-ttu-id="8d50e-137">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-137">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="8d50e-138">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d50e-138">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="8d50e-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d50e-139">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8d50e-140">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-140">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="8d50e-141">GCHeapCount 요소</span><span class="sxs-lookup"><span data-stu-id="8d50e-141">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="8d50e-142">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="8d50e-142">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="8d50e-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="8d50e-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="8d50e-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8d50e-144">Configuration File Schema</span></span>](../index.md)
