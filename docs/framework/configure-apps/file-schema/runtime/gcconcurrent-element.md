---
title: gcConcurrent 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 5957337aa960a0d5f445249b410dbfaddb7b08e9
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969224"
---
# <a name="gcconcurrent-element"></a><span data-ttu-id="34223-102">\<gcConcurrent > 요소</span><span class="sxs-lookup"><span data-stu-id="34223-102">\<gcConcurrent> element</span></span>

<span data-ttu-id="34223-103">공용 언어 런타임이 별도 스레드에서 가비지 수집을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-103">Specifies whether the common language runtime runs garbage collection on a separate thread.</span></span>

<span data-ttu-id="34223-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34223-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="34223-105">[\<런타임 >](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="34223-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="34223-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent ></span><span class="sxs-lookup"><span data-stu-id="34223-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent></span></span>

## <a name="syntax"></a><span data-ttu-id="34223-107">구문</span><span class="sxs-lookup"><span data-stu-id="34223-107">Syntax</span></span>

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="34223-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34223-108">Attributes and elements</span></span>

<span data-ttu-id="34223-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="34223-110">특성</span><span class="sxs-lookup"><span data-stu-id="34223-110">Attributes</span></span>

|<span data-ttu-id="34223-111">특성</span><span class="sxs-lookup"><span data-stu-id="34223-111">Attribute</span></span>|<span data-ttu-id="34223-112">설명</span><span class="sxs-lookup"><span data-stu-id="34223-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="34223-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="34223-113">Required attribute.</span></span><br /><br /><span data-ttu-id="34223-114">런타임이 동시에 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-114">Specifies whether the runtime runs garbage collection concurrently.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="34223-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="34223-115">enabled attribute</span></span>

|<span data-ttu-id="34223-116">값</span><span class="sxs-lookup"><span data-stu-id="34223-116">Value</span></span>|<span data-ttu-id="34223-117">설명</span><span class="sxs-lookup"><span data-stu-id="34223-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="34223-118">가비지 수집을 동시에 실행 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34223-118">Doesn't run garbage collection concurrently.</span></span>|
|`true`|<span data-ttu-id="34223-119">동시에 가비지 컬렉션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-119">Runs garbage collection concurrently.</span></span> <span data-ttu-id="34223-120">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="34223-120">This is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="34223-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34223-121">Child elements</span></span>

<span data-ttu-id="34223-122">없음.</span><span class="sxs-lookup"><span data-stu-id="34223-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="34223-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34223-123">Parent elements</span></span>

|<span data-ttu-id="34223-124">요소</span><span class="sxs-lookup"><span data-stu-id="34223-124">Element</span></span>|<span data-ttu-id="34223-125">설명</span><span class="sxs-lookup"><span data-stu-id="34223-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="34223-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34223-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="34223-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="34223-128">주의</span><span class="sxs-lookup"><span data-stu-id="34223-128">Remarks</span></span>

<span data-ttu-id="34223-129">.NET Framework 4 이전에는 워크스테이션 가비지 수집에서 별도 스레드의 백그라운드에서 가비지 수집을 수행 하는 동시 가비지 수집을 지원 했습니다.</span><span class="sxs-lookup"><span data-stu-id="34223-129">Prior to .NET Framework 4, workstation garbage collection supported concurrent garbage collection, which performed garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="34223-130">.NET Framework 4에서는 동시 가비지 수집이 백그라운드 GC로 대체 되었으며,이는 별도의 스레드에서 백그라운드에서 가비지 수집을 수행 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-130">In .NET Framework 4, concurrent garbage collection was replaced by background GC, which also performs garbage collection in the background on a separate thread.</span></span> <span data-ttu-id="34223-131">.NET Framework 4.5부터 백그라운드 수집은 서버 가비지 컬렉션에서 사용할 수 있게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="34223-131">Starting with .NET Framework 4.5, background collection became available in server garbage collection.</span></span> <span data-ttu-id="34223-132">**GcConcurrent** 요소는 런타임이 동시 또는 백그라운드 가비지 수집을 수행 하는지 (사용할 수 있는 경우) 아니면 포그라운드에서 가비지 수집을 수행 하는지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-132">The **gcConcurrent** element controls whether the runtime performs either concurrent or background garbage collection, if it's available, or whether it performs garbage collection in the foreground.</span></span>

### <a name="to-disable-background-garbage-collection"></a><span data-ttu-id="34223-133">백그라운드 가비지 수집을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="34223-133">To disable background garbage collection</span></span>

> [!WARNING]
> <span data-ttu-id="34223-134">.NET Framework 4부터 동시 가비지 수집이 백그라운드 가비지 수집으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34223-134">Starting with .NET Framework 4, concurrent garbage collection is replaced by background garbage collection.</span></span> <span data-ttu-id="34223-135">.NET Framework 설명서에서는 *동시* 및 *배경* 이라는 용어를 교대로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-135">The terms *concurrent* and *background* are used interchangeably in the .NET Framework documentation.</span></span> <span data-ttu-id="34223-136">백그라운드 가비지 수집을 사용 하지 않도록 설정 하려면이 문서에서 설명 하는 대로 **gcConcurrent** 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-136">To disable background garbage collection, use the **gcConcurrent** element, as discussed in this article.</span></span>

<span data-ttu-id="34223-137">기본적으로 런타임은 대기 시간에 최적화된 동시 또는 백그라운드 가비지 컬렉션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-137">By default, the runtime uses concurrent or background garbage collection, which is optimized for latency.</span></span> <span data-ttu-id="34223-138">사용자 상호 작용이 많이 필요한 애플리케이션인 경우에는 가비지 컬렉션을 수행할 때 애플리케이션의 일시 중지를 최소화하도록 동시 가비지 컬렉션 기능을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34223-138">If your application involves heavy user interaction, leave concurrent garbage collection enabled to minimize the application's pause time to perform garbage collection.</span></span> <span data-ttu-id="34223-139">**GcConcurrent** 요소의 `enabled` 특성을 `false`로 설정 하면 런타임에서는 처리량에 최적화 된 비 동시 가비지 수집을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-139">If you set the `enabled` attribute of the **gcConcurrent** element to `false`, the runtime uses non-concurrent garbage collection, which is optimized for throughput.</span></span>

<span data-ttu-id="34223-140">다음 구성 파일은 백그라운드 가비지 수집을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-140">The following configuration file disables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

<span data-ttu-id="34223-141">**GcConcurrentSetting** 설정이 컴퓨터 구성 파일에 있는 경우 모든 .NET Framework 응용 프로그램에 대 한 기본값을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-141">If there's a **gcConcurrentSetting** setting in the machine configuration file, it defines the default value for all .NET Framework applications.</span></span> <span data-ttu-id="34223-142">컴퓨터 구성 파일 설정은 애플리케이션 구성 파일 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-142">The machine configuration file setting overrides the application configuration file setting.</span></span>

<span data-ttu-id="34223-143">동시 및 백그라운드 가비지 수집에 대 한 자세한 내용은 [가비지 수집 기본 사항](../../../../standard/garbage-collection/fundamentals.md) 문서에서 [동시 가비지 수집](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [백그라운드 워크스테이션 가비지 수집](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection)및 [백그라운드 서버 가비지 수집](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="34223-143">For more information on concurrent and background garbage collection, see the [Concurrent garbage collection](../../../../standard/garbage-collection/fundamentals.md#concurrent-garbage-collection), [Background workstation garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection), and [Background server garbage collection](../../../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection) sections in the [Fundamentals of Garbage Collection](../../../../standard/garbage-collection/fundamentals.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="34223-144">예제</span><span class="sxs-lookup"><span data-stu-id="34223-144">Example</span></span>

<span data-ttu-id="34223-145">다음 예제에서는 백그라운드 가비지 수집을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34223-145">The following example enables background garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="34223-146">참조</span><span class="sxs-lookup"><span data-stu-id="34223-146">See also</span></span>

- [<span data-ttu-id="34223-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="34223-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34223-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="34223-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="34223-149">가비지 수집 기본 사항</span><span class="sxs-lookup"><span data-stu-id="34223-149">Fundamentals of Garbage Collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
