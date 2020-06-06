---
title: <NetFx40_LegacySecurityPolicy> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116248"
---
# <a name="netfx40_legacysecuritypolicy-element"></a><span data-ttu-id="0d41d-102">\<NetFx40_LegacySecurityPolicy> 요소</span><span class="sxs-lookup"><span data-stu-id="0d41d-102">\<NetFx40_LegacySecurityPolicy> Element</span></span>

<span data-ttu-id="0d41d-103">런타임이 레거시 CAS(코드 액세스 보안) 정책을 사용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a><span data-ttu-id="0d41d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d41d-104">Syntax</span></span>

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0d41d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0d41d-105">Attributes and Elements</span></span>

<span data-ttu-id="0d41d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0d41d-107">특성</span><span class="sxs-lookup"><span data-stu-id="0d41d-107">Attributes</span></span>

|<span data-ttu-id="0d41d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0d41d-108">Attribute</span></span>|<span data-ttu-id="0d41d-109">Description</span><span class="sxs-lookup"><span data-stu-id="0d41d-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="0d41d-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="0d41d-111">런타임이 레거시 CAS 정책을 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-111">Specifies whether the runtime uses legacy CAS policy.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="0d41d-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="0d41d-112">enabled Attribute</span></span>

|<span data-ttu-id="0d41d-113">값</span><span class="sxs-lookup"><span data-stu-id="0d41d-113">Value</span></span>|<span data-ttu-id="0d41d-114">Description</span><span class="sxs-lookup"><span data-stu-id="0d41d-114">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="0d41d-115">런타임은 레거시 CAS 정책을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-115">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="0d41d-116">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-116">This is the default.</span></span>|
|`true`|<span data-ttu-id="0d41d-117">런타임은 레거시 CAS 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-117">The runtime uses legacy CAS policy.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0d41d-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0d41d-118">Child Elements</span></span>

<span data-ttu-id="0d41d-119">없음</span><span class="sxs-lookup"><span data-stu-id="0d41d-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0d41d-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0d41d-120">Parent Elements</span></span>

|<span data-ttu-id="0d41d-121">요소</span><span class="sxs-lookup"><span data-stu-id="0d41d-121">Element</span></span>|<span data-ttu-id="0d41d-122">Description</span><span class="sxs-lookup"><span data-stu-id="0d41d-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="0d41d-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="0d41d-124">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="0d41d-125">설명</span><span class="sxs-lookup"><span data-stu-id="0d41d-125">Remarks</span></span>

<span data-ttu-id="0d41d-126">.NET Framework 버전 3.5 및 이전 버전에서는 CAS 정책이 항상 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-126">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="0d41d-127">.NET Framework 4에서 CAS 정책을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-127">In the .NET Framework 4, CAS policy must be enabled.</span></span>

<span data-ttu-id="0d41d-128">CAS 정책은 버전별 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-128">CAS policy is version-specific.</span></span> <span data-ttu-id="0d41d-129">이전 버전의 .NET Framework에 존재 하는 사용자 지정 CAS 정책은 .NET Framework 4에서 respecified 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-129">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the .NET Framework 4.</span></span>

<span data-ttu-id="0d41d-130">.NET Framework 4 어셈블리에 `<NetFx40_LegacySecurityPolicy>` 요소를 적용해도 [보안 투명코드](../../../misc/security-transparent-code.md)에는 영향을 주지않습니다. 투명성 규칙은 여전히 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-130">Applying the `<NetFx40_LegacySecurityPolicy>` element to a .NET Framework 4 assembly does not affect [security-transparent code](../../../misc/security-transparent-code.md); the transparency rules still apply.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d41d-131">요소를 적용 `<NetFx40_LegacySecurityPolicy>` 하면 [전역 어셈블리 캐시](../../../app-domains/gac.md)에 설치 되지 않은 [네이티브 이미지 생성기 (ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) 에서 생성 되는 네이티브 이미지 어셈블리에 대해 상당한 성능 저하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-131">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../app-domains/gac.md).</span></span> <span data-ttu-id="0d41d-132">성능이 저하 되는 이유는 특성이 적용 될 때 런타임이 네이티브 이미지로 어셈블리를 로드할 수 없어 just-in-time 어셈블리로 로드 되는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-132">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>

> [!NOTE]
> <span data-ttu-id="0d41d-133">Visual Studio 프로젝트에 대 한 프로젝트 설정에서 .NET Framework 4 이전의 대상 .NET Framework 버전을 지정 하는 경우 해당 버전에 대해 지정한 모든 사용자 지정 CAS 정책을 포함 하 여 CAS 정책이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-133">If you specify a target .NET Framework version that is earlier than the .NET Framework 4 in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="0d41d-134">그러나 새 .NET Framework 4 형식 및 멤버를 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-134">However, you will not be able to use new .NET Framework 4 types and members.</span></span> <span data-ttu-id="0d41d-135">[응용 프로그램 구성 파일](../../index.md)에서 시작 설정 스키마의 [ \<supportedRuntime> 요소](../startup/supportedruntime-element.md) 를 사용 하 여 .NET Framework의 이전 버전을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-135">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0d41d-136">구성 파일 구문은 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-136">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="0d41d-137">구문 및 예제 섹션에서 제공 하는 구문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-137">You should use the syntax as provided in the Syntax and Example sections.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="0d41d-138">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0d41d-138">Configuration File</span></span>

<span data-ttu-id="0d41d-139">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-139">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="0d41d-140">예제</span><span class="sxs-lookup"><span data-stu-id="0d41d-140">Example</span></span>

<span data-ttu-id="0d41d-141">다음 예제에서는 응용 프로그램에 대해 레거시 CAS 정책을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d41d-141">The following example shows how to enable legacy CAS policy for an application.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="0d41d-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d41d-142">See also</span></span>

- [<span data-ttu-id="0d41d-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0d41d-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0d41d-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0d41d-144">Configuration File Schema</span></span>](../index.md)
