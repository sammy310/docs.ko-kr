---
title: <NetFx45_CultureAwareComparerGetHashCode_LongStrings> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: 413eb6c6e61b509135601c65cf045eabd849e8b3
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802116"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a><span data-ttu-id="002e2-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings > 요소</span><span class="sxs-lookup"><span data-stu-id="002e2-102">\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> Element</span></span>

<span data-ttu-id="002e2-103">런타임이 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 대한 해시 코드를 계산하기 위해 고정된 양의 메모리를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-103">Specifies whether the runtime uses a fixed amount of memory to calculate hash codes for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="002e2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="002e2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="002e2-105">[ **\<런타임 >** ](runtime-element.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="002e2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="002e2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx45_CultureAwareComparerGetHashCode_LongStrings >**</span><span class="sxs-lookup"><span data-stu-id="002e2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="002e2-107">구문</span><span class="sxs-lookup"><span data-stu-id="002e2-107">Syntax</span></span>

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a><span data-ttu-id="002e2-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="002e2-108">Attributes and Elements</span></span>

<span data-ttu-id="002e2-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="002e2-110">특성</span><span class="sxs-lookup"><span data-stu-id="002e2-110">Attributes</span></span>

|<span data-ttu-id="002e2-111">특성</span><span class="sxs-lookup"><span data-stu-id="002e2-111">Attribute</span></span>|<span data-ttu-id="002e2-112">설명</span><span class="sxs-lookup"><span data-stu-id="002e2-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="002e2-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="002e2-114">해시 코드를 계산할 때 공용 언어 런타임에서 고정된 양의 메모리를 할당할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-114">Specifies whether the common language runtime allocates a fixed amount of memory when calculating hash codes.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="002e2-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="002e2-115">enabled Attribute</span></span>

|<span data-ttu-id="002e2-116">값</span><span class="sxs-lookup"><span data-stu-id="002e2-116">Value</span></span>|<span data-ttu-id="002e2-117">설명</span><span class="sxs-lookup"><span data-stu-id="002e2-117">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="002e2-118">0</span><span class="sxs-lookup"><span data-stu-id="002e2-118">0</span></span>|<span data-ttu-id="002e2-119">공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-119">The common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span> <span data-ttu-id="002e2-120">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-120">This is the default.</span></span>|
|<span data-ttu-id="002e2-121">1</span><span class="sxs-lookup"><span data-stu-id="002e2-121">1</span></span>|<span data-ttu-id="002e2-122">공용 언어 런타임은 해시 코드를 계산하기 위해 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 고정적인 양의 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-122">The common language runtime allocates a fixed amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method to calculate hash codes.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="002e2-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="002e2-123">Child Elements</span></span>

<span data-ttu-id="002e2-124">없음.</span><span class="sxs-lookup"><span data-stu-id="002e2-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="002e2-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="002e2-125">Parent Elements</span></span>

|<span data-ttu-id="002e2-126">요소</span><span class="sxs-lookup"><span data-stu-id="002e2-126">Element</span></span>|<span data-ttu-id="002e2-127">설명</span><span class="sxs-lookup"><span data-stu-id="002e2-127">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="002e2-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="002e2-129">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-129">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="002e2-130">주의</span><span class="sxs-lookup"><span data-stu-id="002e2-130">Remarks</span></span>

<span data-ttu-id="002e2-131">기본적으로, 공용 언어 런타임은 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드에 가변적인 양의 메모리를 할당하고, 이 메서드가 (길이가 수백만 자 이상인) 매우 큰 문자열의 해시 코드를 컴퓨팅하려고 할 때 <xref:System.ArgumentException> 이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-131">By default, the common language runtime allocates a variable amount of memory for the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method, and an <xref:System.ArgumentException> can be thrown when the method attempts to compute the hash code of very large strings (over several million characters long).</span></span> <span data-ttu-id="002e2-132">이 요소를 애플리케이션 구성 파일에 추가하고 `enabled` 특성을 "1"로 설정하여 <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> 메서드가 해시 코드의 계산을 위해 고정된 양의 메모리를 할당하는 대체 알고리즘을 사용하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-132">By adding this element to an application configuration file and setting its `enabled` attribute to "1", you can specify that the <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> method use an alternate algorithm that allocates a fixed amount of memory for the computation of hash codes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="002e2-133">`<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` 요소는 Windows 8 이상 버전에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="002e2-133">The `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` element is not used in Windows 8 and later versions.</span></span>

## <a name="see-also"></a><span data-ttu-id="002e2-134">참조</span><span class="sxs-lookup"><span data-stu-id="002e2-134">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="002e2-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="002e2-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="002e2-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="002e2-136">Configuration File Schema</span></span>](../index.md)
