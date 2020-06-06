---
title: <GCCpuGroup> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: f1cbe5a7109d6e4aae2e92710920a1c6b3a40d00
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102894"
---
# <a name="gccpugroup-element"></a><span data-ttu-id="b635e-102">\<GCCpuGroup> 요소</span><span class="sxs-lookup"><span data-stu-id="b635e-102">\<GCCpuGroup> Element</span></span>

<span data-ttu-id="b635e-103">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-103">Specifies whether garbage collection supports multiple CPU groups.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

## <a name="syntax"></a><span data-ttu-id="b635e-104">구문</span><span class="sxs-lookup"><span data-stu-id="b635e-104">Syntax</span></span>

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b635e-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b635e-105">Attributes and Elements</span></span>

<span data-ttu-id="b635e-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b635e-107">특성</span><span class="sxs-lookup"><span data-stu-id="b635e-107">Attributes</span></span>

|<span data-ttu-id="b635e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b635e-108">Attribute</span></span>|<span data-ttu-id="b635e-109">Description</span><span class="sxs-lookup"><span data-stu-id="b635e-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b635e-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="b635e-111">가비지 수집에서 여러 CPU 그룹을 지원할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-111">Specifies whether garbage collection supports multiple CPU groups.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="b635e-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="b635e-112">enabled Attribute</span></span>

|<span data-ttu-id="b635e-113">값</span><span class="sxs-lookup"><span data-stu-id="b635e-113">Value</span></span>|<span data-ttu-id="b635e-114">Description</span><span class="sxs-lookup"><span data-stu-id="b635e-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="b635e-115">가비지 수집은 여러 CPU 그룹을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-115">Garbage collection does not support multiple CPU groups.</span></span> <span data-ttu-id="b635e-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="b635e-117">서버 가비지 수집을 사용 하는 경우 가비지 수집은 여러 CPU 그룹을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-117">Garbage collection supports multiple CPU groups, if server garbage collection is enabled.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b635e-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b635e-118">Child Elements</span></span>

<span data-ttu-id="b635e-119">없음</span><span class="sxs-lookup"><span data-stu-id="b635e-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b635e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b635e-120">Parent Elements</span></span>

|<span data-ttu-id="b635e-121">요소</span><span class="sxs-lookup"><span data-stu-id="b635e-121">Element</span></span>|<span data-ttu-id="b635e-122">Description</span><span class="sxs-lookup"><span data-stu-id="b635e-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b635e-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b635e-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-124">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b635e-125">설명</span><span class="sxs-lookup"><span data-stu-id="b635e-125">Remarks</span></span>

<span data-ttu-id="b635e-126">컴퓨터에 여러 CPU 그룹이 있고 서버 가비지 수집이 사용 되는 경우 (요소 참조 [\<gcServer>](gcserver-element.md) )이 요소를 사용 하면 모든 CPU 그룹에서 가비지 수집을 확장 하 고 힙을 만들고 분산할 때 모든 코어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-126">When a computer has multiple CPU groups and server garbage collection is enabled (see the [\<gcServer>](gcserver-element.md) element), enabling this element extends garbage collection across all CPU groups and takes all cores into account when creating and balancing heaps.</span></span>

> [!NOTE]
> <span data-ttu-id="b635e-127">이 요소는 가비지 수집 스레드에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-127">This element applies only to garbage collection threads.</span></span> <span data-ttu-id="b635e-128">런타임이 모든 CPU 그룹에 사용자 스레드를 배포할 수 있도록 하려면 요소도 사용 하도록 설정 해야 합니다 [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) .</span><span class="sxs-lookup"><span data-stu-id="b635e-128">To enable the runtime to distribute user threads across all CPU groups, you must also enable the [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) element.</span></span>

## <a name="example"></a><span data-ttu-id="b635e-129">예제</span><span class="sxs-lookup"><span data-stu-id="b635e-129">Example</span></span>

<span data-ttu-id="b635e-130">다음 예제에서는 여러 CPU 그룹에 대해 가비지 수집을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b635e-130">The following example shows how to enable garbage collection for multiple CPU groups.</span></span>

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b635e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b635e-131">See also</span></span>

- [<span data-ttu-id="b635e-132">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b635e-132">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b635e-133">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b635e-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b635e-134">동시 가비지 수집 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b635e-134">Disable concurrent garbage collection</span></span>](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [<span data-ttu-id="b635e-135">워크스테이션 및 서버 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="b635e-135">Workstation and server garbage collection</span></span>](../../../../standard/garbage-collection/workstation-server-gc.md)
