---
title: <startup> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153735"
---
# <a name="startup-element"></a><span data-ttu-id="09d16-102">\<시작> 요소</span><span class="sxs-lookup"><span data-stu-id="09d16-102">\<startup> element</span></span>

<span data-ttu-id="09d16-103">공통 언어 런타임 시작 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="09d16-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="09d16-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="09d16-105">&nbsp;&nbsp;**\<스타트업>**</span><span class="sxs-lookup"><span data-stu-id="09d16-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="09d16-106">구문</span><span class="sxs-lookup"><span data-stu-id="09d16-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="09d16-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="09d16-107">Attributes and elements</span></span>

 <span data-ttu-id="09d16-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="09d16-109">특성</span><span class="sxs-lookup"><span data-stu-id="09d16-109">Attributes</span></span>

|<span data-ttu-id="09d16-110">attribute</span><span class="sxs-lookup"><span data-stu-id="09d16-110">Attribute</span></span>|<span data-ttu-id="09d16-111">Description</span><span class="sxs-lookup"><span data-stu-id="09d16-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="09d16-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="09d16-113">.NET Framework 2.0 런타임 활성화 정책을 사용하도록 설정하거나 .NET Framework 4 활성화 정책을 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="09d16-114">use레거시V2Runtime활성화정책 특성</span><span class="sxs-lookup"><span data-stu-id="09d16-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="09d16-115">값</span><span class="sxs-lookup"><span data-stu-id="09d16-115">Value</span></span>|<span data-ttu-id="09d16-116">Description</span><span class="sxs-lookup"><span data-stu-id="09d16-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="09d16-117">CLR 버전 2.0에서 해당 를 제한하는 대신 구성 파일에서 선택한 런타임에 레거시 런타임 활성화 기술(예: [CorBindToRuntimeEx 함수)을](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)바인딩하는 선택된 런타임에 대해 .NET Framework 2.0 런타임 활성화 정책을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="09d16-118">따라서 CLR 버전 4 이상이 구성 파일에서 선택된 경우 이전 버전의 .NET Framework로 만든 혼합 모드 어셈블리가 선택한 CLR 버전으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="09d16-119">이 값을 설정하면 CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드되지 못하게 되어 프로세스 내 기능을 나란히 사용하지 않도록 효과적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="09d16-120">.NET Framework 4 이상에 대한 기본 활성화 정책을 사용하여 레거시 런타임 활성화 기술을 사용하여 CLR 버전 1.1 또는 2.0을 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="09d16-121">이 값을 설정하면 .NET Framework 4 이상으로 빌드되지 않는 한 혼합 모드 어셈블리가 .NET Framework 4 이상에 로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="09d16-122">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="09d16-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="09d16-123">Child elements</span></span>

|<span data-ttu-id="09d16-124">요소</span><span class="sxs-lookup"><span data-stu-id="09d16-124">Element</span></span>|<span data-ttu-id="09d16-125">Description</span><span class="sxs-lookup"><span data-stu-id="09d16-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="09d16-126">\<필수런타임></span><span class="sxs-lookup"><span data-stu-id="09d16-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="09d16-127">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="09d16-128">런타임 버전 1.1 이상으로 빌드된 응용 프로그램은 \*\* \<지원되는 런타임>\*\* 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="09d16-129">\<지원런타임></span><span class="sxs-lookup"><span data-stu-id="09d16-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="09d16-130">애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="09d16-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="09d16-131">Parent elements</span></span>

|<span data-ttu-id="09d16-132">요소</span><span class="sxs-lookup"><span data-stu-id="09d16-132">Element</span></span>|<span data-ttu-id="09d16-133">Description</span><span class="sxs-lookup"><span data-stu-id="09d16-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="09d16-134">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="09d16-135">설명</span><span class="sxs-lookup"><span data-stu-id="09d16-135">Remarks</span></span>

 <span data-ttu-id="09d16-136">\*\* \<지원되는런타임>\*\* 요소는 런타임의 버전 1.1 이상을 사용하여 빌드된 모든 응용 프로그램에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="09d16-137">런타임의 버전 1.0만 지원하도록 빌드된 응용 프로그램은 \*\* \<필수런타임>\*\* 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="09d16-138">Microsoft Internet Explorer에서 호스팅되는 응용 프로그램의 시작 코드는 \*\* \<시작>\*\* 요소와 자식 요소를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="09d16-139">useLegacyV2Runtime활성화정책 특성</span><span class="sxs-lookup"><span data-stu-id="09d16-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="09d16-140">이 특성은 응용 프로그램이 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용하고 해당 경로가 이전 버전 대신 CLR의 버전 4를 활성화하도록 하거나 응용 프로그램이 .NET Framework 4로 빌드되었지만 이전 버전의 .NET Framework로 빌드된 혼합 모드 어셈블리에 종속된 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="09d16-141">이러한 시나리오에서는 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="09d16-142">특성을 설정하여 `true` CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드되는 것을 방지하고 프로세스 내 기능을 효과적으로 비활성화합니다(COM [Interop의 경우 나란히 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))참조).</span><span class="sxs-lookup"><span data-stu-id="09d16-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="09d16-143">예제</span><span class="sxs-lookup"><span data-stu-id="09d16-143">Example</span></span>

 <span data-ttu-id="09d16-144">다음 예제에서는 구성 파일에서 런타임 버전을 지정하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="09d16-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09d16-145">See also</span></span>

- [<span data-ttu-id="09d16-146">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="09d16-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="09d16-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="09d16-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="09d16-148">방법: .NET Framework 4 이상 버전을 지원하도록 앱을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09d16-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="09d16-149">[COM Interop의 Side-By-Side 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="09d16-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="09d16-150">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="09d16-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
