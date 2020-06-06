---
title: <NetFx40_PInvokeStackResilience> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116154"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="f3f89-102">\<NetFx40_PInvokeStackResilience> 요소</span><span class="sxs-lookup"><span data-stu-id="f3f89-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="f3f89-103">런타임이 잘못된 플랫폼 호출 선언을 실행 시간에 자동으로 수정할지를 지정합니다. 자동 수정을 수행하는 경우 관리 코드와 비관리 코드 간 전환 속도가 느려집니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="f3f89-104">구문</span><span class="sxs-lookup"><span data-stu-id="f3f89-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f3f89-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3f89-105">Attributes and Elements</span></span>

<span data-ttu-id="f3f89-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f3f89-107">특성</span><span class="sxs-lookup"><span data-stu-id="f3f89-107">Attributes</span></span>

|<span data-ttu-id="f3f89-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f3f89-108">Attribute</span></span>|<span data-ttu-id="f3f89-109">Description</span><span class="sxs-lookup"><span data-stu-id="f3f89-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="f3f89-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="f3f89-111">런타임이 잘못 된 플랫폼 호출 선언을 검색 하 고 런타임에 32 비트 플랫폼에서 스택을 자동으로 수정 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="f3f89-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="f3f89-112">enabled Attribute</span></span>

|<span data-ttu-id="f3f89-113">값</span><span class="sxs-lookup"><span data-stu-id="f3f89-113">Value</span></span>|<span data-ttu-id="f3f89-114">Description</span><span class="sxs-lookup"><span data-stu-id="f3f89-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="f3f89-115">런타임은 잘못 된 플랫폼 호출 선언을 검색 하 고 수정 하지 않는 .NET Framework 4에서 도입 된 더 빠른 interop 마샬링 아키텍처를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="f3f89-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="f3f89-117">런타임에서는 잘못 된 플랫폼 호출 선언을 검색 하 고 수정 하는 느린 전환을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="f3f89-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3f89-118">Child Elements</span></span>

<span data-ttu-id="f3f89-119">없음</span><span class="sxs-lookup"><span data-stu-id="f3f89-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f3f89-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3f89-120">Parent Elements</span></span>

|<span data-ttu-id="f3f89-121">요소</span><span class="sxs-lookup"><span data-stu-id="f3f89-121">Element</span></span>|<span data-ttu-id="f3f89-122">Description</span><span class="sxs-lookup"><span data-stu-id="f3f89-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="f3f89-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="f3f89-124">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f3f89-125">설명</span><span class="sxs-lookup"><span data-stu-id="f3f89-125">Remarks</span></span>

<span data-ttu-id="f3f89-126">이 요소를 사용 하면 잘못 된 플랫폼 호출 선언에 대해 런타임 복원 력을 더 빠르게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="f3f89-127">.NET Framework 4부터, 간소화 된 interop 마샬링 아키텍처는 관리 코드에서 비관리 코드로의 전환을 위한 상당한 성능 향상을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="f3f89-128">이전 버전의 .NET Framework에서는 마샬링 계층이 32 비트 플랫폼에서 잘못 된 플랫폼 호출 선언을 검색 하 고 스택을 자동으로 수정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="f3f89-129">새 마샬링 아키텍처는이 단계를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="f3f89-130">결과적으로 전환은 매우 빠르지만 잘못 된 플랫폼 호출 선언으로 인해 프로그램 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="f3f89-131">개발 하는 동안 잘못 된 선언을 쉽게 검색할 수 있도록 Visual Studio 디버깅 환경이 개선 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="f3f89-132">[PINVOKESTACKIMBALANCE](../../../debug-trace-profile/pinvokestackimbalance-mda.md) MDA (관리 디버깅 도우미)는 디버거가 연결 된 상태에서 응용 프로그램을 실행할 때 잘못 된 플랫폼 호출 선언이 있음을 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="f3f89-133">응용 프로그램에서 다시 컴파일할 수 없는 구성 요소를 사용 하 고 잘못 된 플랫폼 호출 선언이 있는 시나리오를 해결 하기 위해 요소를 사용할 수 있습니다 `NetFx40_PInvokeStackResilience` .</span><span class="sxs-lookup"><span data-stu-id="f3f89-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="f3f89-134">Opts를 사용 하 여이 요소를 응용 프로그램 구성 파일에 추가 하는 것은 `enabled="1"` 이전 버전의 .NET Framework 동작을 사용 하 여 호환성 모드로 전환 하는 것이 더 느린 전환의 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="f3f89-135">이전 버전의 .NET Framework에 대해 컴파일된 어셈블리는 자동으로이 호환 모드로 옵트인 되며이 요소가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="f3f89-136">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f3f89-136">Configuration File</span></span>

<span data-ttu-id="f3f89-137">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="f3f89-138">예제</span><span class="sxs-lookup"><span data-stu-id="f3f89-138">Example</span></span>

<span data-ttu-id="f3f89-139">다음 예제에서는 관리 코드와 비관리 코드 간의 느린 전환으로 인해 응용 프로그램에 대 한 잘못 된 플랫폼 호출 선언에 대해 늘어난 복원 력을 옵트인 (opt in) 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3f89-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="f3f89-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3f89-140">See also</span></span>

- [<span data-ttu-id="f3f89-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f3f89-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f3f89-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f3f89-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f3f89-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="f3f89-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
