---
title: <performanceCounters> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673744"
---
# <a name="performancecounters-element"></a><span data-ttu-id="6144b-102">\<performanceCounters > 요소</span><span class="sxs-lookup"><span data-stu-id="6144b-102">\<performanceCounters> Element</span></span>

<span data-ttu-id="6144b-103">성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-103">Specifies the size of the global memory shared by performance counters.</span></span>

 <span data-ttu-id="6144b-104">\<configuration>\\</span><span class="sxs-lookup"><span data-stu-id="6144b-104">\<configuration>\\</span></span>
<span data-ttu-id="6144b-105">\<system.diagnostics>\\</span><span class="sxs-lookup"><span data-stu-id="6144b-105">\<system.diagnostics>\\</span></span>
<span data-ttu-id="6144b-106">\<performanceCounters></span><span class="sxs-lookup"><span data-stu-id="6144b-106">\<performanceCounters></span></span>

## <a name="syntax"></a><span data-ttu-id="6144b-107">구문</span><span class="sxs-lookup"><span data-stu-id="6144b-107">Syntax</span></span>

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6144b-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6144b-108">Attributes and Elements</span></span>

<span data-ttu-id="6144b-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6144b-110">특성</span><span class="sxs-lookup"><span data-stu-id="6144b-110">Attributes</span></span>

|<span data-ttu-id="6144b-111">특성</span><span class="sxs-lookup"><span data-stu-id="6144b-111">Attribute</span></span>|<span data-ttu-id="6144b-112">설명</span><span class="sxs-lookup"><span data-stu-id="6144b-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="6144b-113">filemappingsize</span><span class="sxs-lookup"><span data-stu-id="6144b-113">filemappingsize</span></span>|<span data-ttu-id="6144b-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6144b-115">성능 카운터에서 공유 하는 전역 메모리의 바이트에서 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-115">Specifies the size, in bytes, of the global memory shared by performance counters.</span></span> <span data-ttu-id="6144b-116">기본값은 524288입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-116">The default is 524288.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6144b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6144b-117">Child Elements</span></span>

<span data-ttu-id="6144b-118">없음</span><span class="sxs-lookup"><span data-stu-id="6144b-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6144b-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6144b-119">Parent Elements</span></span>

|<span data-ttu-id="6144b-120">요소</span><span class="sxs-lookup"><span data-stu-id="6144b-120">Element</span></span>|<span data-ttu-id="6144b-121">설명</span><span class="sxs-lookup"><span data-stu-id="6144b-121">Description</span></span>|
|-------------|-----------------|
|`Configuration`|<span data-ttu-id="6144b-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`system.diagnostics`|<span data-ttu-id="6144b-123">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-123">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6144b-124">설명</span><span class="sxs-lookup"><span data-stu-id="6144b-124">Remarks</span></span>

<span data-ttu-id="6144b-125">성능 카운터 메모리 매핑된 파일 또는 공유 메모리를 사용 하 여 성능 데이터를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-125">Performance counters use a memory mapped file, or shared memory, to publish performance data.</span></span>  <span data-ttu-id="6144b-126">공유 메모리 크기의 인스턴스 개수을 한 번에 사용할 수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-126">The size of the shared memory determines how many instances can be used at once.</span></span>  <span data-ttu-id="6144b-127">공유 메모리의 두 종류가 있습니다: 전역 공유 메모리 및 별도 공유 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-127">There are two types of shared memory: global shared memory and separate shared memory.</span></span>  <span data-ttu-id="6144b-128">전역 공유 메모리는.NET Framework 버전 1.0 또는 1.1을 사용 하 여 설치 된 모든 성능 카운터 범주에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-128">The global shared memory is used by all performance counter categories installed with the .NET Framework versions 1.0 or 1.1.</span></span>  <span data-ttu-id="6144b-129">자체 메모리가 있는 각 성능 카운터 범주를 사용 하 여 별도 공유 메모리를 사용 하는 성능 카운터 범주는.NET Framework 버전 2.0 사용 하 여 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-129">Performance counter categories installed with the .NET Framework version 2.0 use separate shared memory, with each performance counter category having its own memory.</span></span>

<span data-ttu-id="6144b-130">구성 파일에만 전역 공유 메모리의 크기를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-130">The size of global shared memory can be set only with a configuration file.</span></span>  <span data-ttu-id="6144b-131">기본 크기는 524,288 바이트이 하 이기, 최대 크기는 33,554,432 바이트 및 최소 크기는 32,768 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-131">The default size is 524,288 byes, the maximum size is 33,554,432 bytes, and the minimum size is 32,768 bytes.</span></span>  <span data-ttu-id="6144b-132">모든 프로세스 및 범주에서 전역 공유 메모리를 공유 하므로 첫 번째 생성자는 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-132">Since the global shared memory is shared by all processes and categories, the first creator specifies the size.</span></span>  <span data-ttu-id="6144b-133">응용 프로그램 구성 파일의 크기를 정의 하는 경우 응용 프로그램 성능 카운터를 실행 시키는 첫 번째 응용 프로그램은 해당 크기만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-133">If you define the size in your application configuration file, that size is only used if your application is the first application that causes the performance counters to execute.</span></span>  <span data-ttu-id="6144b-134">따라서 올바른 위치를 지정 합니다 `filemappingsize` 값은 Machine.config 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-134">Therefore the correct location to specify the `filemappingsize` value is the Machine.config file.</span></span>  <span data-ttu-id="6144b-135">개별 성능 카운터 있으므로 결국 많은 수의 서로 다른 이름 사용 하 여 성능 카운터 인스턴스가 생성 되는 경우 전역 공유 메모리를 모두 사용 하 여 전역 공유 메모리에서 메모리를 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-135">Memory in the global shared memory cannot be released by individual performance counters, so eventually global shared memory is exhausted if a large number of performance counter instances with different names are created.</span></span>

<span data-ttu-id="6144b-136">별도 공유 메모리의 크기를 DWORD FileMappingSize 값을 레지스트리에서 키 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<범주 이름 >* \Performance 참조 먼저 구성 파일에서 전역 공유 메모리에 대 한 지정 된 값 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-136">For the size of separate shared memory, the DWORD FileMappingSize value in the registry key HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<category name>* \Performance is referenced first, followed by the value specified for the global shared memory in the configuration file.</span></span> <span data-ttu-id="6144b-137">FileMappingSize 값 존재 하지 않는 경우 별도 공유 메모리 크기가 1 4로 설정 됩니다 (1/4) 구성 파일에서 전역 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="6144b-137">If the FileMappingSize value does not exist, then the separate shared memory size is set to one fourth (1/4) the global setting in the configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="6144b-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="6144b-138">See also</span></span>

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
