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
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699409"
---
# <a name="startup-element"></a><span data-ttu-id="ad2cc-102">\<startup > 요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-102">\<startup> element</span></span>

<span data-ttu-id="ad2cc-103">공용 언어 런타임 시작 정보를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="ad2cc-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="ad2cc-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="ad2cc-105">&nbsp;&nbsp; **\<startup>**</span><span class="sxs-lookup"><span data-stu-id="ad2cc-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ad2cc-106">구문</span><span class="sxs-lookup"><span data-stu-id="ad2cc-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ad2cc-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-107">Attributes and elements</span></span>

 <span data-ttu-id="ad2cc-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ad2cc-109">특성</span><span class="sxs-lookup"><span data-stu-id="ad2cc-109">Attributes</span></span>

|<span data-ttu-id="ad2cc-110">특성</span><span class="sxs-lookup"><span data-stu-id="ad2cc-110">Attribute</span></span>|<span data-ttu-id="ad2cc-111">설명</span><span class="sxs-lookup"><span data-stu-id="ad2cc-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="ad2cc-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ad2cc-113">.NET Framework 2.0 런타임 활성화 정책 사용 여부를 지정 하거나 .NET Framework 4 활성화 정책을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="ad2cc-114">useLegacyV2RuntimeActivationPolicy 특성</span><span class="sxs-lookup"><span data-stu-id="ad2cc-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="ad2cc-115">값</span><span class="sxs-lookup"><span data-stu-id="ad2cc-115">Value</span></span>|<span data-ttu-id="ad2cc-116">설명</span><span class="sxs-lookup"><span data-stu-id="ad2cc-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="ad2cc-117">[CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)등의 레거시 런타임 활성화 기법을 CLR에서 50, 하는 대신 구성 파일에서 선택한 런타임에 바인딩하는 .NET Framework 2.0 런타임 활성화 정책을 사용 하도록 설정 합니다. 버전 2.0.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="ad2cc-118">따라서 구성 파일에서 CLR 버전 4 이상을 선택한 경우 이전 버전의 .NET Framework을 사용 하 여 만든 혼합 모드 어셈블리는 선택한 CLR 버전과 함께 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="ad2cc-119">이 값을 설정 하면 CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드 되지 않으므로 in-process side-by-side 기능을 효과적으로 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="ad2cc-120">.NET Framework 4 이상에 대 한 기본 활성화 정책을 사용 합니다 .이는 레거시 런타임 활성화 기술을 통해 CLR 버전 1.1 또는 2.0을 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="ad2cc-121">이 값을 설정 하면 .NET Framework 4 이상에서 빌드된 경우를 제외 하 고 혼합 모드 어셈블리를 .NET Framework 4 이상으로 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="ad2cc-122">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ad2cc-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-123">Child elements</span></span>

|<span data-ttu-id="ad2cc-124">요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-124">Element</span></span>|<span data-ttu-id="ad2cc-125">설명</span><span class="sxs-lookup"><span data-stu-id="ad2cc-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ad2cc-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="ad2cc-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="ad2cc-127">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="ad2cc-128">런타임 버전 1.1 이상을 사용 하 여 빌드된 응용 프로그램은 **\<supportedRuntime >** 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="ad2cc-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="ad2cc-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="ad2cc-130">애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ad2cc-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-131">Parent elements</span></span>

|<span data-ttu-id="ad2cc-132">요소</span><span class="sxs-lookup"><span data-stu-id="ad2cc-132">Element</span></span>|<span data-ttu-id="ad2cc-133">설명</span><span class="sxs-lookup"><span data-stu-id="ad2cc-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="ad2cc-134">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ad2cc-135">설명</span><span class="sxs-lookup"><span data-stu-id="ad2cc-135">Remarks</span></span>

 <span data-ttu-id="ad2cc-136">**@No__t-1supportedRuntime >** 요소는 버전 1.1 이상을 사용 하 여 빌드된 모든 응용 프로그램에서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="ad2cc-137">버전 1.0의 런타임을 지원 하도록 빌드된 응용 프로그램은 **\<requiredRuntime >** 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="ad2cc-138">Microsoft Internet Explorer에서 호스트 되는 응용 프로그램의 시작 코드는 **\<startup >** 요소 및 해당 자식 요소를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="ad2cc-139">UseLegacyV2RuntimeActivationPolicy 특성</span><span class="sxs-lookup"><span data-stu-id="ad2cc-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="ad2cc-140">이 특성은 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용 하는 응용 프로그램에서 이전 버전이 아닌 CLR 버전 4를 활성화 하거나 응용 프로그램을 .net으로 빌드하는 경우에 유용 합니다. 프레임 워크 4 이지만 이전 버전의 .NET Framework로 빌드된 혼합 모드 어셈블리에 대 한 종속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="ad2cc-141">이러한 시나리오에서는 특성을 `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="ad2cc-142">특성을 `true`으로 설정 하면 CLR 버전 1.1 또는 CLR 버전 2.0이 동일한 프로세스로 로드 되지 않으므로 in-process side-by-side 기능이 효과적으로 사용 되지 않습니다 ( [COM Interop에 대 한 Side-by-side 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))참조).</span><span class="sxs-lookup"><span data-stu-id="ad2cc-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="ad2cc-143">예제</span><span class="sxs-lookup"><span data-stu-id="ad2cc-143">Example</span></span>

 <span data-ttu-id="ad2cc-144">다음 예제에서는 구성 파일의 런타임 버전을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad2cc-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ad2cc-145">참조</span><span class="sxs-lookup"><span data-stu-id="ad2cc-145">See also</span></span>

- [<span data-ttu-id="ad2cc-146">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="ad2cc-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ad2cc-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ad2cc-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ad2cc-148">방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="ad2cc-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="ad2cc-149">[COM Interop에 대 한 side-by-side 실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ad2cc-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="ad2cc-150">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="ad2cc-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
