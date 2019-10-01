---
title: <requiredRuntime> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697496"
---
# <a name="requiredruntime-element"></a><span data-ttu-id="81f80-102">\<requiredRuntime > 요소</span><span class="sxs-lookup"><span data-stu-id="81f80-102">\<requiredRuntime> element</span></span>

<span data-ttu-id="81f80-103">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="81f80-104">이 요소는 사용 되지 않으며 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="81f80-105">[@No__t-1](supportedruntime-element.md) 요소를 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>

[<span data-ttu-id="81f80-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="81f80-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="81f80-107">&nbsp; @ no__t-1[ **\<startup >** ](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="81f80-107">&nbsp;&nbsp;[**\<startup>**](startup-element.md)</span></span>  
<span data-ttu-id="81f80-108">&nbsp; @ no__t-1 @ no__t @ no__t **\<requiredRuntime >**</span><span class="sxs-lookup"><span data-stu-id="81f80-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="81f80-109">구문</span><span class="sxs-lookup"><span data-stu-id="81f80-109">Syntax</span></span>

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="81f80-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="81f80-110">Attributes and elements</span></span>

<span data-ttu-id="81f80-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="81f80-112">특성</span><span class="sxs-lookup"><span data-stu-id="81f80-112">Attributes</span></span>

|<span data-ttu-id="81f80-113">특성</span><span class="sxs-lookup"><span data-stu-id="81f80-113">Attribute</span></span>|<span data-ttu-id="81f80-114">설명</span><span class="sxs-lookup"><span data-stu-id="81f80-114">Description</span></span>|
|---------------|-----------------|
|`version`|<span data-ttu-id="81f80-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="81f80-116">이 응용 프로그램에서 지 원하는 .NET Framework 버전을 지정 하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="81f80-117">문자열 값은 .NET Framework 설치 루트 아래에 있는 디렉터리 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="81f80-118">문자열 값의 내용은 구문 분석 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-118">The contents of the string value are not parsed.</span></span>|
|`safemode`|<span data-ttu-id="81f80-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="81f80-120">런타임 시작 코드가 레지스트리를 검색 하 여 런타임 버전을 확인할 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|

## <a name="safemode-attribute"></a><span data-ttu-id="81f80-121">안전 안전 특성</span><span class="sxs-lookup"><span data-stu-id="81f80-121">safemode attribute</span></span>

|<span data-ttu-id="81f80-122">값</span><span class="sxs-lookup"><span data-stu-id="81f80-122">Value</span></span>|<span data-ttu-id="81f80-123">설명</span><span class="sxs-lookup"><span data-stu-id="81f80-123">Description</span></span>|
|-----------|-----------------|
|`false`|<span data-ttu-id="81f80-124">런타임 시작 코드는 레지스트리에서 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="81f80-125">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-125">This is the default value.</span></span>|
|`true`|<span data-ttu-id="81f80-126">런타임 시작 코드는 레지스트리에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-126">The runtime startup code does not look in the registry.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="81f80-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="81f80-127">Child elements</span></span>

<span data-ttu-id="81f80-128">없음</span><span class="sxs-lookup"><span data-stu-id="81f80-128">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="81f80-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="81f80-129">Parent elements</span></span>

|<span data-ttu-id="81f80-130">요소</span><span class="sxs-lookup"><span data-stu-id="81f80-130">Element</span></span>|<span data-ttu-id="81f80-131">설명</span><span class="sxs-lookup"><span data-stu-id="81f80-131">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="81f80-132">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`startup`|<span data-ttu-id="81f80-133">요소를 `<requiredRuntime>` 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-133">Contains the `<requiredRuntime>` element.</span></span>|

## <a name="remarks"></a><span data-ttu-id="81f80-134">설명</span><span class="sxs-lookup"><span data-stu-id="81f80-134">Remarks</span></span>
 <span data-ttu-id="81f80-135">버전 1.0의 런타임을 지원 하도록 빌드된 응용 프로그램은 `<requiredRuntime>` 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="81f80-136">버전 1.1 이상을 사용 하 여 빌드된 응용 프로그램은 `<supportedRuntime>` 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>

> [!NOTE]
> <span data-ttu-id="81f80-137">[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용 하 여 구성 파일을 지정 하는 경우 모든 버전의 런타임에 대해 `<requiredRuntime>` 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-137">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="81f80-138">[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)를 사용 하는 경우 `<supportedRuntime>` 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>

 <span data-ttu-id="81f80-139">@No__t-0 특성 문자열은 지정 된 .NET Framework 버전의 설치 폴더 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="81f80-140">이 문자열은 해석 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-140">This string is not interpreted.</span></span> <span data-ttu-id="81f80-141">런타임 시작 코드에서 일치 하는 폴더를 찾지 못하면 런타임은 로드 되지 않습니다. 시작 코드는 오류 메시지를 표시 하 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>

> [!NOTE]
> <span data-ttu-id="81f80-142">Microsoft Internet Explorer에서 호스트 되는 응용 프로그램의 시작 코드는 `<requiredRuntime>` 요소를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>

## <a name="example"></a><span data-ttu-id="81f80-143">예제</span><span class="sxs-lookup"><span data-stu-id="81f80-143">Example</span></span>

<span data-ttu-id="81f80-144">다음 예제에서는 구성 파일의 런타임 버전을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81f80-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="81f80-145">참조</span><span class="sxs-lookup"><span data-stu-id="81f80-145">See also</span></span>

- [<span data-ttu-id="81f80-146">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="81f80-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="81f80-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="81f80-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="81f80-148">방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="81f80-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
