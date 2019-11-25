---
title: gcServer 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: 8eab5e36bab90510aff4f1a3e15328197ac59ed7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968943"
---
# <a name="gcserver-element"></a><span data-ttu-id="5a1fd-102">\<gcServer > 요소</span><span class="sxs-lookup"><span data-stu-id="5a1fd-102">\<gcServer> element</span></span>

<span data-ttu-id="5a1fd-103">공용 언어 런타임이 서버 가비지 컬렉션을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-103">Specifies whether the common language runtime runs server garbage collection.</span></span>

<span data-ttu-id="5a1fd-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a1fd-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="5a1fd-105">[\<런타임 >](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="5a1fd-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="5a1fd-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer ></span><span class="sxs-lookup"><span data-stu-id="5a1fd-106">&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer></span></span>

## <a name="syntax"></a><span data-ttu-id="5a1fd-107">구문</span><span class="sxs-lookup"><span data-stu-id="5a1fd-107">Syntax</span></span>

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="5a1fd-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5a1fd-108">Attributes and elements</span></span>

<span data-ttu-id="5a1fd-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5a1fd-110">특성</span><span class="sxs-lookup"><span data-stu-id="5a1fd-110">Attributes</span></span>

|<span data-ttu-id="5a1fd-111">특성</span><span class="sxs-lookup"><span data-stu-id="5a1fd-111">Attribute</span></span>|<span data-ttu-id="5a1fd-112">설명</span><span class="sxs-lookup"><span data-stu-id="5a1fd-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="5a1fd-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-113">Required attribute.</span></span><br /><br /><span data-ttu-id="5a1fd-114">런타임이 서버 가비지 수집을 실행하는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-114">Specifies whether the runtime runs server garbage collection.</span></span>|

#### <a name="enabled-attribute"></a><span data-ttu-id="5a1fd-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="5a1fd-115">enabled attribute</span></span>

|<span data-ttu-id="5a1fd-116">값</span><span class="sxs-lookup"><span data-stu-id="5a1fd-116">Value</span></span>|<span data-ttu-id="5a1fd-117">설명</span><span class="sxs-lookup"><span data-stu-id="5a1fd-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="5a1fd-118">서버 가비지 컬렉션을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-118">Does not run server garbage collection.</span></span> <span data-ttu-id="5a1fd-119">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="5a1fd-120">서버 가비지 컬렉션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-120">Runs server garbage collection.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="5a1fd-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5a1fd-121">Child elements</span></span>

<span data-ttu-id="5a1fd-122">없음.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="5a1fd-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5a1fd-123">Parent elements</span></span>

|<span data-ttu-id="5a1fd-124">요소</span><span class="sxs-lookup"><span data-stu-id="5a1fd-124">Element</span></span>|<span data-ttu-id="5a1fd-125">설명</span><span class="sxs-lookup"><span data-stu-id="5a1fd-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="5a1fd-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="5a1fd-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="5a1fd-128">주의</span><span class="sxs-lookup"><span data-stu-id="5a1fd-128">Remarks</span></span>

<span data-ttu-id="5a1fd-129">CLR(공용 언어 런타임)에서는 두 가지 유형의 가비지 컬렉션을 지원합니다. 워크스테이션 가비지 컬렉션은 모든 시스템에서 사용할 수 있고, 서버 가비지 컬렉션은 다중 프로세서 시스템에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-129">The common language runtime (CLR) supports two types of garbage collection: workstation garbage collection, which is available on all systems, and server garbage collection, which is available on multiprocessor systems.</span></span> <span data-ttu-id="5a1fd-130">**GcServer** 요소를 사용 하 여 CLR에서 수행 하는 가비지 수집 유형을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-130">Use the **gcServer** element to control the type of garbage collection the CLR performs.</span></span> <span data-ttu-id="5a1fd-131"><xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> 속성을 사용하여 서버 가비지 컬렉션이 사용하도록 설정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-131">Use the <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> property to determine if server garbage collection is enabled.</span></span>

<span data-ttu-id="5a1fd-132">단일 프로세서 컴퓨터의 경우 기본 워크스테이션 가비지 수집이 가장 빠른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-132">For single-processor computers, the default workstation garbage collection should be the fastest option.</span></span> <span data-ttu-id="5a1fd-133">두 개의 프로세서가 있는 컴퓨터에는 워크스테이션 또는 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-133">Either workstation or server can be used for two-processor computers.</span></span> <span data-ttu-id="5a1fd-134">세 개 이상 프로세서의 경우 서버 가비지 수집이 가장 빠른 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-134">Server garbage collection should be the fastest option for more than two processors.</span></span> <span data-ttu-id="5a1fd-135">일반적으로 다중 프로세서 서버 시스템은 서버 GC를 사용 하지 않도록 설정 하 고, 서버 앱의 여러 인스턴스가 동일한 컴퓨터에서 실행 되는 경우 대신 워크스테이션 GC를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-135">Most commonly, multiprocessor server systems disable server GC and use workstation GC instead when many instances of a server app run on the same machine.</span></span>

<span data-ttu-id="5a1fd-136">이 요소는 애플리케이션 구성 파일에만 사용할 수 있습니다. 컴퓨터 구성 파일에 있는 경우 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-136">This element can be used only in the application configuration file; it is ignored if it is in the machine configuration file.</span></span>

> [!NOTE]
> <span data-ttu-id="5a1fd-137">.NET Framework 4 및 이전 버전에서, 서버 가비지 수집이 사용되는 경우에는 동시 가비지 수집을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-137">In the .NET Framework 4 and earlier versions, concurrent garbage collection is not available when server garbage collection is enabled.</span></span> <span data-ttu-id="5a1fd-138">.NET Framework 4.5부터 서버 가비지 수집이 동시에 이루어 집니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-138">Starting with the .NET Framework 4.5, server garbage collection is concurrent.</span></span> <span data-ttu-id="5a1fd-139">비 동시 서버 가비지 수집을 사용 하려면 **gcServer** 요소를 `true`으로 설정 하 고 [gcConcurrent 요소](gcconcurrent-element.md) 를 `false`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-139">To use non-concurrent server garbage collection, set the **gcServer** element to `true` and the [gcConcurrent element](gcconcurrent-element.md) to `false`.</span></span>

<span data-ttu-id="5a1fd-140">.NET Framework 4.6.2부터 다음 요소를 사용 하 여 서버 GC를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-140">Starting with .NET Framework 4.6.2, you can also use the following elements to configure server GC:</span></span>

- <span data-ttu-id="5a1fd-141">[GCNoAffinitize](gcnoaffinitize-element.md)-서버 GC 힙과 프로세서 간에 선호도가 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-141">[GCNoAffinitize](gcnoaffinitize-element.md), which specifies whether there is an affinity between server GC heaps and processors.</span></span> <span data-ttu-id="5a1fd-142">기본적으로 각 프로세서에 대해 하나의 서버 GC 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-142">By default, there is one server GC heap for each processor.</span></span>

- <span data-ttu-id="5a1fd-143">[GCHeapCount](gcheapcount-element.md)-프로세스에서 사용 하는 힙 수를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-143">[GCHeapCount](gcheapcount-element.md), which limits the number of heaps used by a process.</span></span>

- <span data-ttu-id="5a1fd-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)-사용 가능한 서버 GC 힙과 개별 프로세서 간의 선호도를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-144">[GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), which defines the affinity between the available server GC heaps and individual processors.</span></span>

## <a name="example"></a><span data-ttu-id="5a1fd-145">예제</span><span class="sxs-lookup"><span data-stu-id="5a1fd-145">Example</span></span>

<span data-ttu-id="5a1fd-146">다음 예에서는 서버 가비지 수집을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a1fd-146">The following example enables server garbage collection:</span></span>

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="5a1fd-147">참조</span><span class="sxs-lookup"><span data-stu-id="5a1fd-147">See also</span></span>

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [<span data-ttu-id="5a1fd-148">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5a1fd-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5a1fd-149">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5a1fd-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="5a1fd-150">동시 가비지 수집을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="5a1fd-150">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
