---
title: <GCCpuGroup> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: 352890519c1a227d664d877c3123866e5e4e1657
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116841"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="7213f-102">\<GCCpuGroup > 요소</span><span class="sxs-lookup"><span data-stu-id="7213f-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="7213f-103">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

<span data-ttu-id="7213f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7213f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7213f-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="7213f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="7213f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**</span><span class="sxs-lookup"><span data-stu-id="7213f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="7213f-107">구문</span><span class="sxs-lookup"><span data-stu-id="7213f-107">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7213f-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7213f-108">Attributes and Elements</span></span>

<span data-ttu-id="7213f-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7213f-110">특성</span><span class="sxs-lookup"><span data-stu-id="7213f-110">Attributes</span></span>

|<span data-ttu-id="7213f-111">특성</span><span class="sxs-lookup"><span data-stu-id="7213f-111">Attribute</span></span>|<span data-ttu-id="7213f-112">설명</span><span class="sxs-lookup"><span data-stu-id="7213f-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="7213f-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7213f-114">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-114">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="7213f-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="7213f-115">enabled Attribute</span></span>

|<span data-ttu-id="7213f-116">값</span><span class="sxs-lookup"><span data-stu-id="7213f-116">Value</span></span>|<span data-ttu-id="7213f-117">설명</span><span class="sxs-lookup"><span data-stu-id="7213f-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="7213f-118">가비지 수집은 여러 CPU 그룹을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-118">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="7213f-119">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="7213f-120">서버 가비지 수집을 사용 하는 경우 가비지 수집은 여러 CPU 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-120">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="7213f-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7213f-121">Child Elements</span></span>

<span data-ttu-id="7213f-122">없음.</span><span class="sxs-lookup"><span data-stu-id="7213f-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7213f-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7213f-123">Parent Elements</span></span>

|<span data-ttu-id="7213f-124">요소</span><span class="sxs-lookup"><span data-stu-id="7213f-124">Element</span></span>|<span data-ttu-id="7213f-125">설명</span><span class="sxs-lookup"><span data-stu-id="7213f-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="7213f-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="7213f-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="7213f-128">주의</span><span class="sxs-lookup"><span data-stu-id="7213f-128">Remarks</span></span>

<span data-ttu-id="7213f-129">컴퓨터에 여러 CPU 그룹이 있고 서버 가비지 수집이 사용 되는 경우 ( [\<gcServer >](gcserver-element.md) 요소 참조)이 요소를 사용 하면 모든 CPU 그룹에서 가비지 수집을 확장 하 고를 만들 때 모든 코어를 고려 합니다. 힙 분산.</span><span class="sxs-lookup"><span data-stu-id="7213f-129">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="7213f-130">이 요소는 가비지 수집 스레드에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-130">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="7213f-131">런타임이 모든 CPU 그룹에 사용자 스레드를 배포할 수 있도록 하려면 [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) 요소도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-131">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="7213f-132">예제</span><span class="sxs-lookup"><span data-stu-id="7213f-132">Example</span></span>

<span data-ttu-id="7213f-133">다음 예제에서는 여러 CPU 그룹에 대해 가비지 수집을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7213f-133">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="7213f-134">참조</span><span class="sxs-lookup"><span data-stu-id="7213f-134">See also</span></span>

- [<span data-ttu-id="7213f-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7213f-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7213f-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7213f-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7213f-137">동시 가비지 수집을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="7213f-137">To disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="7213f-138">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="7213f-138">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
