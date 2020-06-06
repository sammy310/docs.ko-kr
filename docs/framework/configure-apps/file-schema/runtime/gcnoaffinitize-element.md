---
title: GCNoAffinitize 요소
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 16d6e5adefe2b632d7251669650058d7df7cea70
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "84004740"
---
# <a name="gcnoaffinitize-element"></a><span data-ttu-id="24efe-102">\<GCNoAffinitize> 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-102">\<GCNoAffinitize> element</span></span>

<span data-ttu-id="24efe-103">Cpu가 있는 서버 GC 스레드를 선호도 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-103">Specifies whether or not to affinitize server GC threads with CPUs.</span></span>

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a><span data-ttu-id="24efe-104">구문</span><span class="sxs-lookup"><span data-stu-id="24efe-104">Syntax</span></span>

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="24efe-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-105">Attributes and elements</span></span>

<span data-ttu-id="24efe-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="24efe-107">특성</span><span class="sxs-lookup"><span data-stu-id="24efe-107">Attributes</span></span>

|<span data-ttu-id="24efe-108">attribute</span><span class="sxs-lookup"><span data-stu-id="24efe-108">Attribute</span></span>|<span data-ttu-id="24efe-109">Description</span><span class="sxs-lookup"><span data-stu-id="24efe-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="24efe-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-110">Required attribute.</span></span><br /><br /><span data-ttu-id="24efe-111">서버 GC 스레드/힙이 컴퓨터에서 사용할 수 있는 프로세서와 선호도가 설정 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-111">Specifies whether server GC threads/heaps are affinitized with the processors available on the machine.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="24efe-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="24efe-112">enabled attribute</span></span>

|<span data-ttu-id="24efe-113">값</span><span class="sxs-lookup"><span data-stu-id="24efe-113">Value</span></span>|<span data-ttu-id="24efe-114">Description</span><span class="sxs-lookup"><span data-stu-id="24efe-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="24efe-115">Cpu가 있는 서버 GC 스레드를 선호도 합니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-115">Affinitizes server GC threads with CPUs.</span></span> <span data-ttu-id="24efe-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="24efe-117">는 Cpu가 있는 서버 GC 스레드를 선호도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-117">Does not affinitize server GC threads with CPUs.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="24efe-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-118">Child elements</span></span>

<span data-ttu-id="24efe-119">없음</span><span class="sxs-lookup"><span data-stu-id="24efe-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="24efe-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-120">Parent elements</span></span>

|<span data-ttu-id="24efe-121">요소</span><span class="sxs-lookup"><span data-stu-id="24efe-121">Element</span></span>|<span data-ttu-id="24efe-122">Description</span><span class="sxs-lookup"><span data-stu-id="24efe-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="24efe-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="24efe-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="24efe-125">설명</span><span class="sxs-lookup"><span data-stu-id="24efe-125">Remarks</span></span>

<span data-ttu-id="24efe-126">기본적으로 서버 GC 스레드는 해당 Cpu와 함께 하드 선호도가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-126">By default, server GC threads are hard-affinitized with their respective CPUs.</span></span> <span data-ttu-id="24efe-127">각 시스템의 사용 가능한 프로세서에는 자체 GC 힙과 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-127">Each of the system's available processors has its own GC heap and thread.</span></span> <span data-ttu-id="24efe-128">이 설정은 캐시 사용을 최적화 하므로 일반적으로 선호 되는 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-128">This is typically the preferred setting since it optimizes cache usage.</span></span> <span data-ttu-id="24efe-129">.NET Framework 4.6.2 부터는 **GCNoAffinitize** 요소의 특성을로 설정 하 여 `enabled` `true` 서버 GC 스레드 및 cpu를 긴밀 하 게 결합 하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-129">Starting with .NET Framework 4.6.2, by setting the **GCNoAffinitize** element's `enabled` attribute to `true`, you can specify that server GC threads and CPUs should not be tightly coupled.</span></span>

<span data-ttu-id="24efe-130">Cpu가 있는 서버 GC 스레드를 선호도 하지 않도록 **GCNoAffinitize** 구성 요소를 단독으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-130">You can specify the **GCNoAffinitize** configuration element alone to not affinitize server GC threads with CPUs.</span></span> <span data-ttu-id="24efe-131">[GCHeapCount](gcheapcount-element.md) 요소와 함께 사용 하 여 응용 프로그램에서 사용 하는 GC 힙과 스레드 수를 제어할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-131">You can also use it along with the [GCHeapCount](gcheapcount-element.md) element to control the number of GC heaps and threads used by an application.</span></span>

<span data-ttu-id="24efe-132">`enabled` **GCNoAffinitize** 요소의 특성이 `false` (기본값) 인 경우 [GCHeapCount](gcheapcount-element.md) 요소를 사용 하 여 gc 스레드 및 힙을 선호도가 설정 하는 프로세서를 지정 하는 [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) 요소와 함께 gc 스레드 및 힙 수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-132">If the `enabled` attribute of the **GCNoAffinitize** element is `false` (its default value), you can also use the [GCHeapCount](gcheapcount-element.md) element to specify the number of GC threads and heaps, along with the [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) element to specify the processors to which the GC threads and heaps are affinitized.</span></span>

## <a name="example"></a><span data-ttu-id="24efe-133">예제</span><span class="sxs-lookup"><span data-stu-id="24efe-133">Example</span></span>

<span data-ttu-id="24efe-134">다음 예에서는 서버 GC 스레드를 하드 선호도 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-134">The following example does not hard-affinitize server GC threads:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

<span data-ttu-id="24efe-135">다음 예에서는 서버 GC 스레드를 선호도 하 고 GC 힙/스레드 수를 10으로 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="24efe-135">The following example does not affinitize server GC threads and limits the number of GC heaps/threads to 10:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="24efe-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24efe-136">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="24efe-137">GCHeapAffinitizeMask 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-137">GCHeapAffinitizeMask element</span></span>](gcheapaffinitizemask-element.md)
- [<span data-ttu-id="24efe-138">GCHeapCount 요소</span><span class="sxs-lookup"><span data-stu-id="24efe-138">GCHeapCount element</span></span>](gcheapcount-element.md)
- [<span data-ttu-id="24efe-139">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="24efe-139">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="24efe-140">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="24efe-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="24efe-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="24efe-141">Configuration File Schema</span></span>](../index.md)
