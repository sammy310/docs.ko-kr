---
title: <Thread_UseAllCpuGroups> 요소
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: a3a612c0ffbcb211157b9623d298ce8ad7a13e94
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115405"
---
# <a name="thread_useallcpugroups-element"></a><span data-ttu-id="bae7d-102">\<Thread_UseAllCpuGroups> 요소</span><span class="sxs-lookup"><span data-stu-id="bae7d-102">\<Thread_UseAllCpuGroups> Element</span></span>

<span data-ttu-id="bae7d-103">런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-103">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a><span data-ttu-id="bae7d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bae7d-104">Syntax</span></span>

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="bae7d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bae7d-105">Attributes and Elements</span></span>

<span data-ttu-id="bae7d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="bae7d-107">특성</span><span class="sxs-lookup"><span data-stu-id="bae7d-107">Attributes</span></span>

|<span data-ttu-id="bae7d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="bae7d-108">Attribute</span></span>|<span data-ttu-id="bae7d-109">Description</span><span class="sxs-lookup"><span data-stu-id="bae7d-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="bae7d-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="bae7d-111">런타임이 모든 CPU 그룹에 관리되는 스레드를 배포할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-111">Specifies whether the runtime distributes managed threads across all CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="bae7d-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="bae7d-112">enabled Attribute</span></span>

|<span data-ttu-id="bae7d-113">값</span><span class="sxs-lookup"><span data-stu-id="bae7d-113">Value</span></span>|<span data-ttu-id="bae7d-114">Description</span><span class="sxs-lookup"><span data-stu-id="bae7d-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="bae7d-115">런타임은 여러 CPU 그룹에 관리 되는 스레드를 배포 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-115">The runtime does not distribute managed threads across multiple CPU groups.</span></span> <span data-ttu-id="bae7d-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="bae7d-117">컴퓨터에 여러 CPU 그룹이 있고 요소가 사용 되는 경우 런타임은 여러 CPU 그룹에 관리 되는 스레드를 배포 합니다 [\<GCCpuGroup>](gccpugroup-element.md) .</span><span class="sxs-lookup"><span data-stu-id="bae7d-117">The runtime distributes managed threads across multiple CPU groups, if the computer has multiple CPU groups and the [\<GCCpuGroup>](gccpugroup-element.md) element is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="bae7d-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bae7d-118">Child Elements</span></span>

<span data-ttu-id="bae7d-119">없음</span><span class="sxs-lookup"><span data-stu-id="bae7d-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bae7d-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bae7d-120">Parent Elements</span></span>

|<span data-ttu-id="bae7d-121">요소</span><span class="sxs-lookup"><span data-stu-id="bae7d-121">Element</span></span>|<span data-ttu-id="bae7d-122">Description</span><span class="sxs-lookup"><span data-stu-id="bae7d-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="bae7d-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="bae7d-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="bae7d-125">설명</span><span class="sxs-lookup"><span data-stu-id="bae7d-125">Remarks</span></span>

<span data-ttu-id="bae7d-126">컴퓨터에 여러 CPU 그룹이 있는 경우이 요소를 사용 하도록 설정 하면 런타임이 모든 CPU 그룹에 관리 되는 스레드를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-126">When a computer has multiple CPU groups, enabling this element causes the runtime to distribute managed threads across all CPU groups.</span></span> <span data-ttu-id="bae7d-127">또한이 기능을 사용 하려면 [\<GCCpuGroup>](gccpugroup-element.md) 가비지 수집을 모든 CPU 그룹으로 확장 하 고 힙을 만들고 분산할 때 모든 코어를 고려 하는 요소도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-127">To use this feature, you must also enable the [\<GCCpuGroup>](gccpugroup-element.md) element, which extends garbage collection to all CPU groups and takes all cores into account when creating and balancing heaps.</span></span> <span data-ttu-id="bae7d-128">요소를 사용 하도록 설정 [\<GCCpuGroup>](gccpugroup-element.md) 하려면 요소를 사용 하도록 설정 해야 [\<gcServer>](gcserver-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-128">Enabling the [\<GCCpuGroup>](gccpugroup-element.md) element requires enabling the [\<gcServer>](gcserver-element.md) element.</span></span> <span data-ttu-id="bae7d-129">이러한 요소를 사용할 수 없는 경우 요소를 사용 하도록 설정 `<Thread_UseAllCpuGroups>` 해도 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-129">If these elements are not enabled, enabling the `<Thread_UseAllCpuGroups>` element has no effect.</span></span>

## <a name="example"></a><span data-ttu-id="bae7d-130">예제</span><span class="sxs-lookup"><span data-stu-id="bae7d-130">Example</span></span>

<span data-ttu-id="bae7d-131">다음 예제에서는 여러 CPU 그룹에 대 한 지원을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bae7d-131">The following example shows how to enable support for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="bae7d-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bae7d-132">See also</span></span>

- [<span data-ttu-id="bae7d-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="bae7d-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bae7d-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bae7d-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bae7d-135">\<GCCpuGroup>요소인</span><span class="sxs-lookup"><span data-stu-id="bae7d-135">\<GCCpuGroup> Element</span></span>](gccpugroup-element.md)
