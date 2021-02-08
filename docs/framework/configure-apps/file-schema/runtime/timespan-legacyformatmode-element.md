---
description: <TimeSpan_LegacyFormatMode> 요소에 대해 자세히 알아보세요.
title: <TimeSpan_LegacyFormatMode> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
ms.openlocfilehash: 1fa5c3a15941004ebab9e3622d4b3e7b27130e22
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802387"
---
# <a name="timespan_legacyformatmode-element"></a><span data-ttu-id="b2fa4-103">\<TimeSpan_LegacyFormatMode> 요소</span><span class="sxs-lookup"><span data-stu-id="b2fa4-103">\<TimeSpan_LegacyFormatMode> Element</span></span>

<span data-ttu-id="b2fa4-104">런타임에 값을 사용 하 여 서식 지정 작업에서 레거시 동작을 유지할지 여부를 결정 <xref:System.TimeSpan?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-104">Determines whether the runtime preserves legacy behavior in formatting operations with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a><span data-ttu-id="b2fa4-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2fa4-105">Syntax</span></span>

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b2fa4-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b2fa4-106">Attributes and Elements</span></span>

<span data-ttu-id="b2fa4-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b2fa4-108">특성</span><span class="sxs-lookup"><span data-stu-id="b2fa4-108">Attributes</span></span>

|<span data-ttu-id="b2fa4-109">attribute</span><span class="sxs-lookup"><span data-stu-id="b2fa4-109">Attribute</span></span>|<span data-ttu-id="b2fa4-110">설명</span><span class="sxs-lookup"><span data-stu-id="b2fa4-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="b2fa4-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="b2fa4-112">런타임에서 값에 레거시 서식 동작을 사용할지 여부를 지정 합니다 <xref:System.TimeSpan?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="b2fa4-112">Specifies whether the runtime uses legacy formatting behavior with <xref:System.TimeSpan?displayProperty=nameWithType> values.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="b2fa4-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="b2fa4-113">enabled Attribute</span></span>

|<span data-ttu-id="b2fa4-114">값</span><span class="sxs-lookup"><span data-stu-id="b2fa4-114">Value</span></span>|<span data-ttu-id="b2fa4-115">설명</span><span class="sxs-lookup"><span data-stu-id="b2fa4-115">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="b2fa4-116">런타임은 레거시 서식 지정 동작을 복원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-116">The runtime does not restore legacy formatting behavior.</span></span>|
|`true`|<span data-ttu-id="b2fa4-117">런타임이 레거시 서식 지정 동작을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-117">The runtime restores legacy formatting behavior.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b2fa4-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b2fa4-118">Child Elements</span></span>

<span data-ttu-id="b2fa4-119">없음</span><span class="sxs-lookup"><span data-stu-id="b2fa4-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b2fa4-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b2fa4-120">Parent Elements</span></span>

|<span data-ttu-id="b2fa4-121">요소</span><span class="sxs-lookup"><span data-stu-id="b2fa4-121">Element</span></span>|<span data-ttu-id="b2fa4-122">설명</span><span class="sxs-lookup"><span data-stu-id="b2fa4-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="b2fa4-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="b2fa4-124">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b2fa4-125">설명</span><span class="sxs-lookup"><span data-stu-id="b2fa4-125">Remarks</span></span>

<span data-ttu-id="b2fa4-126">.NET Framework 4부터 <xref:System.TimeSpan?displayProperty=nameWithType> 구조는 인터페이스를 구현 <xref:System.IFormattable> 하 고 표준 및 사용자 지정 서식 문자열을 사용 하 여 서식 지정 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-126">Starting with the .NET Framework 4, the <xref:System.TimeSpan?displayProperty=nameWithType> structure implements the <xref:System.IFormattable> interface and supports formatting operations with standard and custom format strings.</span></span> <span data-ttu-id="b2fa4-127">구문 분석 메서드에서 지원 되지 않는 서식 지정자 또는 형식 문자열이 발견 되 면이 throw <xref:System.FormatException> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-127">If a parsing method encounters an unsupported format specifier or format string, it throws a <xref:System.FormatException>.</span></span>

<span data-ttu-id="b2fa4-128">이전 버전의 .NET Framework에서 구조는를 <xref:System.TimeSpan> 구현 하지 않았으며 <xref:System.IFormattable> 형식 문자열을 지원 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-128">In previous versions of the .NET Framework, the <xref:System.TimeSpan> structure did not implement <xref:System.IFormattable> and did not support format strings.</span></span> <span data-ttu-id="b2fa4-129">그러나 대부분의 개발자는 <xref:System.TimeSpan> 형식 문자열 집합을 지원 하 고와 같은 메서드를 사용 하 여 [복합 형식 지정 작업](../../../../standard/base-types/composite-formatting.md) 에 사용 하는 것으로 잘못 된 것으로 가정 <xref:System.String.Format%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-129">However, many developers mistakenly assumed that <xref:System.TimeSpan> did support a set of format strings and used them in [composite formatting operations](../../../../standard/base-types/composite-formatting.md) with methods such as <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b2fa4-130">일반적으로 형식이 <xref:System.IFormattable> 형식 문자열을 구현 하 고 지 원하는 경우 지원 되지 않는 형식 문자열을 사용 하 여 형식 지정 메서드를 호출 하면 일반적으로이 throw <xref:System.FormatException> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-130">Ordinarily, if a type implements <xref:System.IFormattable> and supports format strings, calls to formatting methods with unsupported format strings usually throw a <xref:System.FormatException>.</span></span> <span data-ttu-id="b2fa4-131">그러나가 <xref:System.TimeSpan> 를 구현 하지 않았기 때문에 <xref:System.IFormattable> 런타임은 형식 문자열을 무시 하 고 대신 메서드를 호출 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-131">However, because <xref:System.TimeSpan> did not implement <xref:System.IFormattable>, the runtime ignored the format string and instead called the <xref:System.TimeSpan.ToString?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b2fa4-132">즉, 서식 문자열은 서식 지정 작업에 영향을 주지 않지만의 현재 상태는로 설정 되지 않습니다 <xref:System.FormatException> .</span><span class="sxs-lookup"><span data-stu-id="b2fa4-132">This means that, although the format strings had no effect on the formatting operation, their presence did not result in a <xref:System.FormatException>.</span></span>

<span data-ttu-id="b2fa4-133">레거시 코드가 복합 서식 지정 메서드와 잘못 된 서식 문자열을 전달 하 고 해당 코드를 다시 컴파일할 수 없는 경우에는 요소를 사용 `<TimeSpan_LegacyFormatMode>` 하 여 레거시 동작을 복원할 수 있습니다 <xref:System.TimeSpan> .</span><span class="sxs-lookup"><span data-stu-id="b2fa4-133">For cases in which legacy code passes a composite formatting method and an invalid format string, and that code cannot be recompiled, you can use the `<TimeSpan_LegacyFormatMode>` element to restore the legacy <xref:System.TimeSpan> behavior.</span></span> <span data-ttu-id="b2fa4-134">`enabled`이 요소의 특성을로 설정 하는 경우 `true` 복합 형식 지정 메서드는가 아닌에 대 한 호출을 발생 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 하 고는 <xref:System.FormatException> throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-134">When you set the `enabled` attribute of this element to `true`, the composite formatting method results in a call to <xref:System.TimeSpan.ToString?displayProperty=nameWithType> rather than <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, and a <xref:System.FormatException> is not thrown.</span></span>

## <a name="example"></a><span data-ttu-id="b2fa4-135">예제</span><span class="sxs-lookup"><span data-stu-id="b2fa4-135">Example</span></span>

<span data-ttu-id="b2fa4-136">다음 예제에서는 개체를 인스턴스화하고 <xref:System.TimeSpan> <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> 지원 되지 않는 표준 형식 문자열을 사용 하 여 메서드를 사용 하 여 형식을 지정 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-136">The following example instantiates a <xref:System.TimeSpan> object and attempts to format it with the <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> method by using an unsupported standard format string.</span></span>

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

<span data-ttu-id="b2fa4-137">.NET Framework 3.5 또는 이전 버전에서 예제를 실행 하면 다음과 같은 출력이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-137">When you run the example on the .NET Framework 3.5 or on an earlier version, it displays the following output:</span></span>

```console
12:30:45
```

<span data-ttu-id="b2fa4-138">.NET Framework 4 이상 버전에서 예제를 실행 하는 경우에는 출력과 현저히 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-138">This differs markedly from the output if you run the example on the .NET Framework 4 or later version:</span></span>

```console
Invalid Format
```

<span data-ttu-id="b2fa4-139">그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 .NET Framework 4 이상 버전에서 예제를 실행 하는 경우 출력은 3.5 .NET Framework에서 실행 될 때 예제에 의해 생성 된 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2fa4-139">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4 or later version, the output is identical to that produced by the example when it is run on .NET Framework 3.5.</span></span>

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="b2fa4-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2fa4-140">See also</span></span>

- [<span data-ttu-id="b2fa4-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b2fa4-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b2fa4-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b2fa4-142">Configuration File Schema</span></span>](../index.md)
