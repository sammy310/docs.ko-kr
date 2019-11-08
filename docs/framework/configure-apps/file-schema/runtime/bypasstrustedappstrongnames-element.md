---
title: <bypassTrustedAppStrongNames> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739091"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="ce9ab-102">\<bypassTrustedAppStrongNames> 요소</span><span class="sxs-lookup"><span data-stu-id="ce9ab-102">\<bypassTrustedAppStrongNames> Element</span></span>

<span data-ttu-id="ce9ab-103">완전 신뢰 <xref:System.AppDomain>에 로드 된 완전 신뢰 어셈블리의 강력한 이름에 대 한 유효성 검사를 건너뛸지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>

<span data-ttu-id="ce9ab-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ce9ab-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ce9ab-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="ce9ab-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="ce9ab-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<bypassTrustedAppStrongNames >**</span><span class="sxs-lookup"><span data-stu-id="ce9ab-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ce9ab-107">구문</span><span class="sxs-lookup"><span data-stu-id="ce9ab-107">Syntax</span></span>

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ce9ab-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ce9ab-108">Attributes and Elements</span></span>

<span data-ttu-id="ce9ab-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ce9ab-110">특성</span><span class="sxs-lookup"><span data-stu-id="ce9ab-110">Attributes</span></span>

|<span data-ttu-id="ce9ab-111">특성</span><span class="sxs-lookup"><span data-stu-id="ce9ab-111">Attribute</span></span>|<span data-ttu-id="ce9ab-112">설명</span><span class="sxs-lookup"><span data-stu-id="ce9ab-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="ce9ab-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ce9ab-114">완전 신뢰 어셈블리의 강력한 이름 유효성 검사를 방지 하는 바이패스 기능을 사용 하도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="ce9ab-115">이 기능을 사용 하는 경우 어셈블리가 로드 될 때 강력한 이름의 유효성이 검사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="ce9ab-116">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-116">The default is `true`.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="ce9ab-117">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ce9ab-117">enabled Attribute</span></span>

|<span data-ttu-id="ce9ab-118">값</span><span class="sxs-lookup"><span data-stu-id="ce9ab-118">Value</span></span>|<span data-ttu-id="ce9ab-119">설명</span><span class="sxs-lookup"><span data-stu-id="ce9ab-119">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="ce9ab-120">완전 신뢰 어셈블리의 강력한 이름 서명은 어셈블리를 완전 신뢰 <xref:System.AppDomain>로드할 때 유효성이 검사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ce9ab-121">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-121">This is the default.</span></span>|
|`false`|<span data-ttu-id="ce9ab-122">완전 신뢰 어셈블리의 강력한 이름 서명은 어셈블리를 완전 신뢰 <xref:System.AppDomain>으로 로드할 때 유효성이 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ce9ab-123">강력한 이름 시그니처는 서명 정확성에 대해서만 확인 됩니다. 일치 항목에 대 한 다른 강력한 이름과 비교 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ce9ab-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce9ab-124">Child Elements</span></span>

<span data-ttu-id="ce9ab-125">없음.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ce9ab-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce9ab-126">Parent Elements</span></span>

|<span data-ttu-id="ce9ab-127">요소</span><span class="sxs-lookup"><span data-stu-id="ce9ab-127">Element</span></span>|<span data-ttu-id="ce9ab-128">설명</span><span class="sxs-lookup"><span data-stu-id="ce9ab-128">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ce9ab-129">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="ce9ab-130">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-130">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ce9ab-131">주의</span><span class="sxs-lookup"><span data-stu-id="ce9ab-131">Remarks</span></span>

<span data-ttu-id="ce9ab-132">강력한 이름 건너뛰기 기능을 사용 하면 완전 신뢰 어셈블리의 강력한 이름 서명 확인의 오버 헤드가 방지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>

<span data-ttu-id="ce9ab-133">건너뛰기 기능은 강력한 이름으로 서명되었으며 다음과 같은 특징이 있는 모든 어셈블리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>

- <span data-ttu-id="ce9ab-134"><xref:System.Security.Policy.StrongName> 증명 정보 없이 완전히 신뢰할 수 있습니다 (예: `MyComputer` 영역 증명 정보 포함).</span><span class="sxs-lookup"><span data-stu-id="ce9ab-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>

- <span data-ttu-id="ce9ab-135">완전히 신뢰할 수 있는 <xref:System.AppDomain>에 로드됨</span><span class="sxs-lookup"><span data-stu-id="ce9ab-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="ce9ab-136">해당 <xref:System.AppDomain>의 <xref:System.AppDomainSetup.ApplicationBase%2A> 속성 아래에 있는 위치에서 로드됨</span><span class="sxs-lookup"><span data-stu-id="ce9ab-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>

- <span data-ttu-id="ce9ab-137">서명이 연기되지 않음</span><span class="sxs-lookup"><span data-stu-id="ce9ab-137">Not delay-signed.</span></span>

> [!NOTE]
> <span data-ttu-id="ce9ab-138">레지스트리 키를 사용 하 여 컴퓨터의 모든 응용 프로그램에 대해 바이패스 기능이 꺼져 있는 경우이 구성 파일 설정은 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="ce9ab-139">자세한 내용은 [방법: 강력한 이름 건너뛰기 기능 사용 안 함](../../../../standard/assembly/disable-strong-name-bypass-feature.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../standard/assembly/disable-strong-name-bypass-feature.md).</span></span>

## <a name="example"></a><span data-ttu-id="ce9ab-140">예제</span><span class="sxs-lookup"><span data-stu-id="ce9ab-140">Example</span></span>

<span data-ttu-id="ce9ab-141">다음 예제에서는 완전 신뢰 어셈블리에서 강력한 이름 서명의 유효성을 검사 하는 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce9ab-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="ce9ab-142">참조</span><span class="sxs-lookup"><span data-stu-id="ce9ab-142">See also</span></span>

- [<span data-ttu-id="ce9ab-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ce9ab-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ce9ab-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ce9ab-144">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ce9ab-145">방법: 강력한 이름 건너뛰기 기능 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="ce9ab-145">How to: Disable the strong-name bypass feature</span></span>](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
