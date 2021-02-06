---
description: '자세히 알아보기: GCLOHThreshold 요소'
title: GCLOHThreshold 요소
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: 5d4ef4e6aaf44642c2307dc27ac2e99e966d3ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652811"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="83848-103">GCLOHThreshold 요소</span><span class="sxs-lookup"><span data-stu-id="83848-103">GCLOHThreshold element</span></span>

<span data-ttu-id="83848-104">가비지 수집기가 개체를 LOH (large object heap)에 배치 하 게 하는 임계값 크기 (바이트)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83848-104">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a><span data-ttu-id="83848-105">구문</span><span class="sxs-lookup"><span data-stu-id="83848-105">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="83848-106">특성</span><span class="sxs-lookup"><span data-stu-id="83848-106">Attributes</span></span>

|<span data-ttu-id="83848-107">attribute</span><span class="sxs-lookup"><span data-stu-id="83848-107">Attribute</span></span>|<span data-ttu-id="83848-108">설명</span><span class="sxs-lookup"><span data-stu-id="83848-108">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="83848-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="83848-109">Required attribute.</span></span><br /><br /><span data-ttu-id="83848-110">큰 개체 힙에서 개체를 이동 하 게 하는 임계값 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83848-110">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="83848-111">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="83848-111">enabled attribute</span></span>

|<span data-ttu-id="83848-112">값</span><span class="sxs-lookup"><span data-stu-id="83848-112">Value</span></span>|<span data-ttu-id="83848-113">설명</span><span class="sxs-lookup"><span data-stu-id="83848-113">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="83848-114">개체가 큰 개체 힙에 이동 되도록 하는 임계값 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="83848-114">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="83848-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="83848-115">Child elements</span></span>

<span data-ttu-id="83848-116">없음</span><span class="sxs-lookup"><span data-stu-id="83848-116">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="83848-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="83848-117">Parent elements</span></span>

|<span data-ttu-id="83848-118">요소</span><span class="sxs-lookup"><span data-stu-id="83848-118">Element</span></span>|<span data-ttu-id="83848-119">설명</span><span class="sxs-lookup"><span data-stu-id="83848-119">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="83848-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="83848-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="83848-121">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="83848-121">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="83848-122">설명</span><span class="sxs-lookup"><span data-stu-id="83848-122">Remarks</span></span>

<span data-ttu-id="83848-123">이 설정은 .NET Framework 4.8에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83848-123">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="83848-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83848-124">See also</span></span>

- [<span data-ttu-id="83848-125">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="83848-125">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="83848-126">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="83848-126">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="83848-127">가비지 컬렉션 기본 사항</span><span class="sxs-lookup"><span data-stu-id="83848-127">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="83848-128">GC에 대 한 NET Core 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="83848-128">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
