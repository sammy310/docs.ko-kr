---
description: '다음에 대 한 자세한 정보: <GCCpuGroup> 요소'
title: <GCCpuGroup> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: d4b3aa7084cbc2cb23b273bea95ffaec6e3a74d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786995"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="c2583-103">\<GCCpuGroup> 요소</span><span class="sxs-lookup"><span data-stu-id="c2583-103">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="c2583-104">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-104">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="c2583-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2583-105">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c2583-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c2583-106">Attributes and Elements</span></span>

<span data-ttu-id="c2583-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c2583-108">특성</span><span class="sxs-lookup"><span data-stu-id="c2583-108">Attributes</span></span>

|<span data-ttu-id="c2583-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c2583-109">Attribute</span></span>|<span data-ttu-id="c2583-110">설명</span><span class="sxs-lookup"><span data-stu-id="c2583-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="c2583-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="c2583-112">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-112">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="c2583-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c2583-113">enabled Attribute</span></span>

|<span data-ttu-id="c2583-114">값</span><span class="sxs-lookup"><span data-stu-id="c2583-114">Value</span></span>|<span data-ttu-id="c2583-115">설명</span><span class="sxs-lookup"><span data-stu-id="c2583-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="c2583-116">가비지 수집은 여러 CPU 그룹을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-116">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="c2583-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-117">This is the default.</span></span>|
|`true`|<span data-ttu-id="c2583-118">서버 가비지 수집을 사용 하는 경우 가비지 수집은 여러 CPU 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-118">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c2583-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c2583-119">Child Elements</span></span>

<span data-ttu-id="c2583-120">없음</span><span class="sxs-lookup"><span data-stu-id="c2583-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c2583-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c2583-121">Parent Elements</span></span>

|<span data-ttu-id="c2583-122">요소</span><span class="sxs-lookup"><span data-stu-id="c2583-122">Element</span></span>|<span data-ttu-id="c2583-123">설명</span><span class="sxs-lookup"><span data-stu-id="c2583-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="c2583-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="c2583-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-125">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c2583-126">설명</span><span class="sxs-lookup"><span data-stu-id="c2583-126">Remarks</span></span>

<span data-ttu-id="c2583-127">컴퓨터에 여러 CPU 그룹이 있고 서버 가비지 수집이 사용 되는 경우 (요소 참조 [\<gcServer>](gcserver-element.md) )이 요소를 사용 하면 모든 CPU 그룹에서 가비지 수집을 확장 하 고 힙을 만들고 분산할 때 모든 코어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-127">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="c2583-128">이 요소는 가비지 수집 스레드에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-128">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="c2583-129">런타임이 모든 CPU 그룹에 사용자 스레드를 배포할 수 있도록 하려면 요소도 사용 하도록 설정 해야 합니다 [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="c2583-129">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="c2583-130">예제</span><span class="sxs-lookup"><span data-stu-id="c2583-130">Example</span></span>

<span data-ttu-id="c2583-131">다음 예제에서는 여러 CPU 그룹에 대해 가비지 수집을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c2583-131">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c2583-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2583-132">See also</span></span>

- [<span data-ttu-id="c2583-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c2583-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c2583-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c2583-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c2583-135">동시 가비지 수집 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c2583-135">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="c2583-136">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="c2583-136">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
