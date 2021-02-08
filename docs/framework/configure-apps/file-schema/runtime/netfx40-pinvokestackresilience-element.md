---
description: <NetFx40_PInvokeStackResilience> 요소에 대해 자세히 알아보세요.
title: <NetFx40_PInvokeStackResilience> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 59e2a5845868ebfa186344c9a731871739a29c47
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782301"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="016a0-103">\<NetFx40_PInvokeStackResilience> 요소</span><span class="sxs-lookup"><span data-stu-id="016a0-103">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="016a0-104">런타임이 잘못된 플랫폼 호출 선언을 실행 시간에 자동으로 수정할지를 지정합니다. 자동 수정을 수행하는 경우 관리 코드와 비관리 코드 간 전환 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-104">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="016a0-105">구문</span><span class="sxs-lookup"><span data-stu-id="016a0-105">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="016a0-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="016a0-106">Attributes and Elements</span></span>

<span data-ttu-id="016a0-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="016a0-108">특성</span><span class="sxs-lookup"><span data-stu-id="016a0-108">Attributes</span></span>

|<span data-ttu-id="016a0-109">attribute</span><span class="sxs-lookup"><span data-stu-id="016a0-109">Attribute</span></span>|<span data-ttu-id="016a0-110">설명</span><span class="sxs-lookup"><span data-stu-id="016a0-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="016a0-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="016a0-112">런타임이 잘못 된 플랫폼 호출 선언을 검색 하 고 런타임에 32 비트 플랫폼에서 스택을 자동으로 수정 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-112">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="016a0-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="016a0-113">enabled Attribute</span></span>

|<span data-ttu-id="016a0-114">값</span><span class="sxs-lookup"><span data-stu-id="016a0-114">Value</span></span>|<span data-ttu-id="016a0-115">설명</span><span class="sxs-lookup"><span data-stu-id="016a0-115">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="016a0-116">런타임은 잘못 된 플랫폼 호출 선언을 검색 하 고 수정 하지 않는 .NET Framework 4에서 도입 된 더 빠른 interop 마샬링 아키텍처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-116">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="016a0-117">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-117">This is the default.</span></span>|
|`1`|<span data-ttu-id="016a0-118">런타임에서는 잘못 된 플랫폼 호출 선언을 검색 하 고 수정 하는 느린 전환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-118">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="016a0-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="016a0-119">Child Elements</span></span>

<span data-ttu-id="016a0-120">없음</span><span class="sxs-lookup"><span data-stu-id="016a0-120">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="016a0-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="016a0-121">Parent Elements</span></span>

|<span data-ttu-id="016a0-122">요소</span><span class="sxs-lookup"><span data-stu-id="016a0-122">Element</span></span>|<span data-ttu-id="016a0-123">설명</span><span class="sxs-lookup"><span data-stu-id="016a0-123">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="016a0-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="016a0-125">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-125">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="016a0-126">설명</span><span class="sxs-lookup"><span data-stu-id="016a0-126">Remarks</span></span>

<span data-ttu-id="016a0-127">이 요소를 사용 하면 잘못 된 플랫폼 호출 선언에 대해 런타임 복원 력을 더 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-127">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="016a0-128">.NET Framework 4부터, 간소화 된 interop 마샬링 아키텍처는 관리 코드에서 비관리 코드로의 전환을 위한 상당한 성능 향상을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-128">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="016a0-129">이전 버전의 .NET Framework에서는 마샬링 계층이 32 비트 플랫폼에서 잘못 된 플랫폼 호출 선언을 검색 하 고 스택을 자동으로 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-129">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="016a0-130">새 마샬링 아키텍처는이 단계를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-130">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="016a0-131">결과적으로 전환은 매우 빠르지만 잘못 된 플랫폼 호출 선언으로 인해 프로그램 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-131">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="016a0-132">개발 하는 동안 잘못 된 선언을 쉽게 검색할 수 있도록 Visual Studio 디버깅 환경이 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-132">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="016a0-133">[PINVOKESTACKIMBALANCE](../../../debug-trace-profile/pinvokestackimbalance-mda.md) MDA (관리 디버깅 도우미)는 디버거가 연결 된 상태에서 응용 프로그램을 실행할 때 잘못 된 플랫폼 호출 선언이 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-133">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="016a0-134">응용 프로그램에서 다시 컴파일할 수 없는 구성 요소를 사용 하 고 잘못 된 플랫폼 호출 선언이 있는 시나리오를 해결 하기 위해 요소를 사용할 수 있습니다 `NetFx40_PInvokeStackResilience` .</span><span class="sxs-lookup"><span data-stu-id="016a0-134">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="016a0-135">Opts를 사용 하 여이 요소를 응용 프로그램 구성 파일에 추가 하는 것은 `enabled="1"` 이전 버전의 .NET Framework 동작을 사용 하 여 호환성 모드로 전환 하는 것이 더 느린 전환의 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-135">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="016a0-136">이전 버전의 .NET Framework에 대해 컴파일된 어셈블리는 자동으로이 호환 모드로 옵트인 되며이 요소가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-136">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="016a0-137">구성 파일</span><span class="sxs-lookup"><span data-stu-id="016a0-137">Configuration File</span></span>

<span data-ttu-id="016a0-138">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-138">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="016a0-139">예제</span><span class="sxs-lookup"><span data-stu-id="016a0-139">Example</span></span>

<span data-ttu-id="016a0-140">다음 예제에서는 관리 코드와 비관리 코드 간의 느린 전환으로 인해 응용 프로그램에 대 한 잘못 된 플랫폼 호출 선언에 대해 늘어난 복원 력을 옵트인 (opt in) 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="016a0-140">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="016a0-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="016a0-141">See also</span></span>

- [<span data-ttu-id="016a0-142">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="016a0-142">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="016a0-143">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="016a0-143">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="016a0-144">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="016a0-144">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
