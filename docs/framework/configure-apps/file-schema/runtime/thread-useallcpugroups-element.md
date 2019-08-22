---
title: <Thread_UseAllCpuGroups> 요소
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9ee6bdb7094ea2bc9e283e331c0f6ad9b68e4f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663418"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="2f61d-102">\<Thread_UseAllCpuGroups > 요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="2f61d-103">런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

<span data-ttu-id="2f61d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="2f61d-104">\<configuration></span></span>\
<span data-ttu-id="2f61d-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="2f61d-105">\<runtime></span></span>\
<span data-ttu-id="2f61d-106">\<Thread_UseAllCpuGroups></span><span class="sxs-lookup"><span data-stu-id="2f61d-106">\<Thread_UseAllCpuGroups></span></span>

## <a name="syntax"></a><span data-ttu-id="2f61d-107">구문</span><span class="sxs-lookup"><span data-stu-id="2f61d-107">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2f61d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-108">Attributes and Elements</span></span>

<span data-ttu-id="2f61d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2f61d-110">특성</span><span class="sxs-lookup"><span data-stu-id="2f61d-110">Attributes</span></span>

|<span data-ttu-id="2f61d-111">특성</span><span class="sxs-lookup"><span data-stu-id="2f61d-111">Attribute</span></span>|<span data-ttu-id="2f61d-112">설명</span><span class="sxs-lookup"><span data-stu-id="2f61d-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2f61d-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2f61d-114">런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-114">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="2f61d-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="2f61d-115">enabled Attribute</span></span>

|<span data-ttu-id="2f61d-116">값</span><span class="sxs-lookup"><span data-stu-id="2f61d-116">Value</span></span>|<span data-ttu-id="2f61d-117">설명</span><span class="sxs-lookup"><span data-stu-id="2f61d-117">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="2f61d-118">런타임은 여러 CPU 그룹에 관리 되는 스레드를 배포 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-118">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="2f61d-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-119">This is the default.</span></span>|
|`true`|<span data-ttu-id="2f61d-120">컴퓨터에 여러 cpu 그룹이 있고 [ \<GCCpuGroup >](gccpugroup-element.md) 요소가 사용 하도록 설정 된 경우 런타임은 여러 cpu 그룹에 관리 되는 스레드를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-120">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2f61d-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-121">Child Elements</span></span>

<span data-ttu-id="2f61d-122">없음</span><span class="sxs-lookup"><span data-stu-id="2f61d-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2f61d-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-123">Parent Elements</span></span>

|<span data-ttu-id="2f61d-124">요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-124">Element</span></span>|<span data-ttu-id="2f61d-125">설명</span><span class="sxs-lookup"><span data-stu-id="2f61d-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2f61d-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2f61d-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-127">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2f61d-128">설명</span><span class="sxs-lookup"><span data-stu-id="2f61d-128">Remarks</span></span>

<span data-ttu-id="2f61d-129">컴퓨터에 여러 CPU 그룹이 있는 경우이 요소를 사용 하도록 설정 하면 런타임이 모든 CPU 그룹에 관리 되는 스레드를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-129">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="2f61d-130">또한이 기능을 사용 하려면 [ \<GCCpuGroup >](gccpugroup-element.md) 요소를 사용 하도록 설정 해야 합니다 .이 요소는 가비지 수집을 모든 CPU 그룹으로 확장 하 고 힙을 만들고 분산 하는 경우 모든 코어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-130">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="2f61d-131">[ \<GCCpuGroup >](gccpugroup-element.md) 요소를 사용 하도록 설정 하려면 [ \<gcServer >](gcserver-element.md) 요소를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-131">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="2f61d-132">이러한 요소를 사용할 수 없는 경우 요소를 `<Thread_UseAllCpuGroups>` 사용 하도록 설정 해도 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-132">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="2f61d-133">예제</span><span class="sxs-lookup"><span data-stu-id="2f61d-133">Example</span></span>

<span data-ttu-id="2f61d-134">다음 예제에서는 여러 CPU 그룹에 대 한 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f61d-134">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="2f61d-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f61d-135">See also</span></span>

- [<span data-ttu-id="2f61d-136">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2f61d-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2f61d-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2f61d-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="2f61d-138">\<GCCpuGroup > 요소</span><span class="sxs-lookup"><span data-stu-id="2f61d-138">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
