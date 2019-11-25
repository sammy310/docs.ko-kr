---
title: GCHeapAffinitizeMask 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978422"
---
# <a name="gcheapaffinitizemask-element"></a><span data-ttu-id="c410e-102">\<GCHeapAffinitizeMask > 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-102">\<GCHeapAffinitizeMask> element</span></span>

<span data-ttu-id="c410e-103">GC 힙과 개별 프로세서 간의 선호도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-103">Defines the affinity between GC heaps and individual processors.</span></span>

<span data-ttu-id="c410e-104">\<구성 > </span><span class="sxs-lookup"><span data-stu-id="c410e-104">\<configuration></span></span>\
<span data-ttu-id="c410e-105">&nbsp;&nbsp;\<런타임 > </span><span class="sxs-lookup"><span data-stu-id="c410e-105">&nbsp;&nbsp;\<runtime></span></span>\
<span data-ttu-id="c410e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask ></span><span class="sxs-lookup"><span data-stu-id="c410e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask></span></span>

## <a name="syntax"></a><span data-ttu-id="c410e-107">구문</span><span class="sxs-lookup"><span data-stu-id="c410e-107">Syntax</span></span>

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c410e-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-108">Attributes and elements</span></span>

<span data-ttu-id="c410e-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c410e-110">특성</span><span class="sxs-lookup"><span data-stu-id="c410e-110">Attributes</span></span>

|<span data-ttu-id="c410e-111">특성</span><span class="sxs-lookup"><span data-stu-id="c410e-111">Attribute</span></span>|<span data-ttu-id="c410e-112">설명</span><span class="sxs-lookup"><span data-stu-id="c410e-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c410e-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-113">Required attribute.</span></span><br /><br /><span data-ttu-id="c410e-114">GC 힙과 개별 프로세서 간의 선호도를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-114">Specifies the affinity between GC heaps and individual processors.</span></span> |

#### <a name="enabled-attribute"></a><span data-ttu-id="c410e-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c410e-115">enabled attribute</span></span>

|<span data-ttu-id="c410e-116">값</span><span class="sxs-lookup"><span data-stu-id="c410e-116">Value</span></span>|<span data-ttu-id="c410e-117">설명</span><span class="sxs-lookup"><span data-stu-id="c410e-117">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="c410e-118">서버 GC 힙과 개별 프로세서 간의 선호도를 정의 하는 비트 마스크를 형성 하는 10 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-118">A decimal value that forms a bitmask defining the affinity between server GC heaps and individual processors.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="c410e-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-119">Child elements</span></span>

<span data-ttu-id="c410e-120">없음.</span><span class="sxs-lookup"><span data-stu-id="c410e-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c410e-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-121">Parent elements</span></span>

|<span data-ttu-id="c410e-122">요소</span><span class="sxs-lookup"><span data-stu-id="c410e-122">Element</span></span>|<span data-ttu-id="c410e-123">설명</span><span class="sxs-lookup"><span data-stu-id="c410e-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c410e-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c410e-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c410e-126">주의</span><span class="sxs-lookup"><span data-stu-id="c410e-126">Remarks</span></span>

<span data-ttu-id="c410e-127">기본적으로 서버 GC 스레드는 각 프로세서에 대해 하나의 GC 힙, 하나의 서버 GC 스레드 및 하나의 백그라운드 서버 GC 스레드를 갖도록 해당 CPU와 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-127">By default, server GC threads are hard-affinitized with their respective CPU so that there is one GC heap, one server GC thread, and one background server GC thread for each processor.</span></span> <span data-ttu-id="c410e-128">.NET Framework 4.6.2 부터는 **GCHeapAffinitizeMask** 요소를 사용 하 여 힙 수가 **GCHeapCount** 요소에 의해 제한 되는 경우 서버 GC 힙과 프로세서 간의 선호도를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-128">Starting with .NET Framework 4.6.2, you can use the **GCHeapAffinitizeMask** element to control the affinity between server GC heaps and processors when the number of heaps is limited by the **GCHeapCount** element.</span></span>

<span data-ttu-id="c410e-129">**GCHeapAffinitizeMask** 는 일반적으로 두 개의 다른 플래그와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-129">**GCHeapAffinitizeMask** is typically used along with two other flags:</span></span>

- <span data-ttu-id="c410e-130">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 스레드/힙이 cpu와 선호도가 설정 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-130">[GCNoAffinitize](gcnoaffinitize-element.md), which controls whether server GC threads/heaps are affinitized with CPUs.</span></span> <span data-ttu-id="c410e-131">[GCNoAffinitize](gcnoaffinitize-element.md) 요소의 `enabled` 특성은 사용할 **GCHeapAffinitizeMask** 설정에 대 한 `false` (기본값) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-131">The `enabled` attribute of the [GCNoAffinitize](gcnoaffinitize-element.md) element must be `false` (its default value) for the **GCHeapAffinitizeMask** setting to be used.</span></span>

- <span data-ttu-id="c410e-132">[GCHeapCount](gcheapcount-element.md)-서버 GC에 대해 프로세스에서 사용 하는 힙 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-132">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by the process for server GC.</span></span> <span data-ttu-id="c410e-133">기본적으로 각 프로세서에 대해 하나의 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-133">By default, there is one heap for each processor.</span></span>

<span data-ttu-id="c410e-134">**nnnn** 은 10 진수 값으로 표현 되는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-134">**nnnn** is a bit mask expressed as a decimal value.</span></span> <span data-ttu-id="c410e-135">바이트 0의 비트 0은 프로세서 0, 바이트 0의 비트 1은 프로세서 1을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-135">Bit 0 of byte 0 represents processor 0, bit 1 of byte 0 represents processor 1, and so on.</span></span> <span data-ttu-id="c410e-136">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-136">For example:</span></span>

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

<span data-ttu-id="c410e-137">1023 값은 0x3FF 또는 0011 1111 1111b입니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-137">A value of 1023 is 0x3FF or 0011 1111 1111b.</span></span> <span data-ttu-id="c410e-138">프로세스는 프로세서 0부터 프로세서 9까지 10 개의 프로세서를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-138">The process uses 10 processors, from processor 0 through processor 9.</span></span>

## <a name="example"></a><span data-ttu-id="c410e-139">예제</span><span class="sxs-lookup"><span data-stu-id="c410e-139">Example</span></span>

<span data-ttu-id="c410e-140">다음 예는 응용 프로그램에서 서버 GC를 사용 하 고 힙/스레드를 10 개 사용 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-140">The following example indicates that an application uses server GC with 10 heaps/threads.</span></span> <span data-ttu-id="c410e-141">이러한 힙이 시스템에서 실행 되는 다른 응용 프로그램의 힙과 겹치지 않도록 하기 때문에 **GCHeapAffinitizeMask** 를 사용 하 여 프로세스에서 cpu 0 ~ 9를 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c410e-141">Since you don't want those heaps to overlap with heaps from other applications running on the system, use **GCHeapAffinitizeMask** to specify that the process should use CPUs 0 through 9.</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c410e-142">참조</span><span class="sxs-lookup"><span data-stu-id="c410e-142">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c410e-143">GCNoAffinitize 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-143">GCNoAffinitize element</span></span>](gcnoaffinitize-element.md)
- [<span data-ttu-id="c410e-144">GCHeapCount 요소</span><span class="sxs-lookup"><span data-stu-id="c410e-144">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="c410e-145">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="c410e-145">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="c410e-146">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c410e-146">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c410e-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c410e-147">Configuration File Schema</span></span>](../index.md)
