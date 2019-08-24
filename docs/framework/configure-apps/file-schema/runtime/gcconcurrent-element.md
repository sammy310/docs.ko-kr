---
title: <gcConcurrent> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e2be4d9384f1e1ef73ce6064184aa2621a517a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674105"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="436e3-102">\<gcConcurrent> Element</span><span class="sxs-lookup"><span data-stu-id="436e3-102">\<gcConcurrent> Element</span></span>

<span data-ttu-id="436e3-103">공용 언어 런타임이 별도 스레드에서 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="436e3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="436e3-104">\<configuration></span></span>\
<span data-ttu-id="436e3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="436e3-105">\<runtime></span></span>\
<span data-ttu-id="436e3-106">\<gcConcurrent></span><span class="sxs-lookup"><span data-stu-id="436e3-106">\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="436e3-107">구문</span><span class="sxs-lookup"><span data-stu-id="436e3-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="436e3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="436e3-108">Attributes and elements</span></span>

<span data-ttu-id="436e3-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="436e3-110">특성</span><span class="sxs-lookup"><span data-stu-id="436e3-110">Attributes</span></span>

|<span data-ttu-id="436e3-111">특성</span><span class="sxs-lookup"><span data-stu-id="436e3-111">Attribute</span></span>|<span data-ttu-id="436e3-112">설명</span><span class="sxs-lookup"><span data-stu-id="436e3-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="436e3-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="436e3-114">런타임이 동시에 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="436e3-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="436e3-115">enabled attribute</span></span>

|<span data-ttu-id="436e3-116">값</span><span class="sxs-lookup"><span data-stu-id="436e3-116">Value</span></span>|<span data-ttu-id="436e3-117">설명</span><span class="sxs-lookup"><span data-stu-id="436e3-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="436e3-118">가비지 컬렉션을 동시에 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="436e3-119">동시에 가비지 컬렉션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="436e3-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="436e3-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="436e3-121">Child elements</span></span>

<span data-ttu-id="436e3-122">없음</span><span class="sxs-lookup"><span data-stu-id="436e3-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="436e3-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="436e3-123">Parent elements</span></span>

|<span data-ttu-id="436e3-124">요소</span><span class="sxs-lookup"><span data-stu-id="436e3-124">Element</span></span>|<span data-ttu-id="436e3-125">설명</span><span class="sxs-lookup"><span data-stu-id="436e3-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="436e3-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="436e3-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="436e3-128">설명</span><span class="sxs-lookup"><span data-stu-id="436e3-128">Remarks</span></span>

<span data-ttu-id="436e3-129">.NET Framework 4 이전에는 워크스테이션 가비지 컬렉션이 별도 스레드에서 백그라운드로 가비지 컬렉션을 수행한 동시 가비지 컬렉션을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-129">Prior to the .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="436e3-130">.NET Framework 4에서는 동시 가비지 수집이 역시 별도 스레드에서 백그라운드로 가비지 수집을 수행하는 백그라운드 GC로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-130">In the .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="436e3-131">.NET Framework 4.5부터 백그라운드 수집을 서버 가비지 수집에서 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-131">Starting with the .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="436e3-132">`<gcConcurrent>` 요소 런타임은 동시 수행 하는지 여부를 제어 또는 백그라운드 가비지 컬렉션, 사용 가능한 경우 또는 포그라운드에서 가비지 수집 수행 여부를 합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-132">The `<gcConcurrent>` element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="436e3-133">백그라운드 가비지 수집을 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="436e3-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="436e3-134">.NET Framework 4부터 동시 가비지 컬렉션이 백그라운드 가비지 컬렉션으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-134">Starting with the .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="436e3-135">용어 *동시* 하 고 *백그라운드* .NET Framework 설명서에서 같은 의미로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="436e3-136">백그라운드 가비지 컬렉션을 사용하지 않으려면, 이 문서에 설명된 대로 `<gcConcurrent>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-136">To disable background garbage collection, use the `<gcConcurrent>` element, as discussed in this article.</span></span>

<span data-ttu-id="436e3-137">기본적으로 런타임은 대기 시간에 최적화된 동시 또는 백그라운드 가비지 수집을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="436e3-138">사용자 상호 작용이 많이 필요한 애플리케이션인 경우에는 가비지 컬렉션을 수행할 때 애플리케이션의 일시 중지를 최소화하도록 동시 가비지 컬렉션 기능을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="436e3-139">`enabled` 요소의 `<gcConcurrent>` 특성을 `false`에 설정할 경우 런타임은 효율성이 최적화된 비동시성 가비지 수집을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-139">If you set the `enabled` attribute of the `<gcConcurrent>` element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span> <span data-ttu-id="436e3-140">다음 구성 파일에서는 백그라운드 가비지 수집을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-140">The following configuration file disables background garbage collection.</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

 <span data-ttu-id="436e3-141">없는 경우는 `<gcConcurrentSetting>` 모든.NET Framework 응용 프로그램에 대 한 기본값 정의 컴퓨터 구성 파일에서이 옵션을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-141">If there's a `<gcConcurrentSetting>` setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="436e3-142">컴퓨터 구성 파일 설정은 애플리케이션 구성 파일 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

 <span data-ttu-id="436e3-143">자세한 방법은 동시 및 백그라운드 가비지 수집을 참조 하세요. 합니다 [동시 가비지 수집](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) 섹션을 [가비지 컬렉션 기본 사항](../../../../standard/garbage-collection/fundamentals.md) 문서.</span><span class="sxs-lookup"><span data-stu-id="436e3-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection) section in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="436e3-144">예제</span><span class="sxs-lookup"><span data-stu-id="436e3-144">Example</span></span>

<span data-ttu-id="436e3-145">다음 예제에서는 동시 가비지 컬렉션을 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="436e3-145">The following example enables concurrent garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="436e3-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="436e3-146">See also</span></span>

- [<span data-ttu-id="436e3-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="436e3-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="436e3-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="436e3-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="436e3-149">가비지 수집 기본 사항</span><span class="sxs-lookup"><span data-stu-id="436e3-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
