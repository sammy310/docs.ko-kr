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
ms.openlocfilehash: 022f0efbbb2e6e9a4ac9d3d7ddcc1fb1022cdbee
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169768"
---
# <a name="startup-element"></a><span data-ttu-id="3b8a5-102">\<시작 > 요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-102">\<startup> element</span></span>

<span data-ttu-id="3b8a5-103">공용 언어 런타임 시작 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-103">Specifies common language runtime startup information.</span></span>

 <span data-ttu-id="3b8a5-104">\<configuration> \<startup></span><span class="sxs-lookup"><span data-stu-id="3b8a5-104">\<configuration> \<startup></span></span>

## <a name="syntax"></a><span data-ttu-id="3b8a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="3b8a5-105">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b8a5-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-106">Attributes and elements</span></span>

 <span data-ttu-id="3b8a5-107">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3b8a5-108">특성</span><span class="sxs-lookup"><span data-stu-id="3b8a5-108">Attributes</span></span>

|<span data-ttu-id="3b8a5-109">특성</span><span class="sxs-lookup"><span data-stu-id="3b8a5-109">Attribute</span></span>|<span data-ttu-id="3b8a5-110">설명</span><span class="sxs-lookup"><span data-stu-id="3b8a5-110">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="3b8a5-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3b8a5-112">.NET Framework 2.0 런타임 정품 인증 정책을 사용 하도록 설정 또는.NET Framework 4 정품 인증 정책을 사용 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-112">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="3b8a5-113">useLegacyV2RuntimeActivationPolicy 특성</span><span class="sxs-lookup"><span data-stu-id="3b8a5-113">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="3b8a5-114">값</span><span class="sxs-lookup"><span data-stu-id="3b8a5-114">Value</span></span>|<span data-ttu-id="3b8a5-115">설명</span><span class="sxs-lookup"><span data-stu-id="3b8a5-115">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="3b8a5-116">레거시 런타임 정품 인증 기술에 바인딩하는 선택한 런타임용.NET Framework 2.0 런타임 정품 인증 정책을 사용 하도록 설정 (예는 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) 대신 구성 파일에서 선택한 런타임에 CLR 버전 2.0에서 해당를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-116">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="3b8a5-117">따라서 CLR 버전 4 이상을 구성 파일에서을 선택 하면 이전 버전의.NET Framework를 사용 하 여 만든 혼합 모드 어셈블리에 있는 선택한 CLR 버전을 사용 하 여 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-117">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="3b8a5-118">CLR 버전 1.1 또는 CLR 버전 2.0-in-process side-by-side-기능을 효과적으로 사용 하지 않도록 설정 하는 동일한 프로세스로 로드 방지이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-118">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="3b8a5-119">레거시 런타임 정품 인증 기술을 프로세스에 1.1 또는 2.0 버전 CLR을 로드할 수 있도록.NET Framework 4 이상에서는 기본 정품 인증 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-119">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="3b8a5-120">혼합 모드 어셈블리의.NET Framework 4 이상 빌드된.NET Framework 4 또는 나중에 로드를 방해이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-120">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="3b8a5-121">이 값은 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-121">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3b8a5-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-122">Child elements</span></span>

|<span data-ttu-id="3b8a5-123">요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-123">Element</span></span>|<span data-ttu-id="3b8a5-124">설명</span><span class="sxs-lookup"><span data-stu-id="3b8a5-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="3b8a5-125">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="3b8a5-125">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="3b8a5-126">애플리케이션에서 1.0 버전의 공용 언어 런타임만 지원하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-126">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="3b8a5-127">런타임 버전 1.1 이상으로 빌드된 응용 프로그램을 사용 해야 합니다  **\<supportedRuntime >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-127">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="3b8a5-128">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="3b8a5-128">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="3b8a5-129">애플리케이션이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-129">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="3b8a5-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-130">Parent elements</span></span>

|<span data-ttu-id="3b8a5-131">요소</span><span class="sxs-lookup"><span data-stu-id="3b8a5-131">Element</span></span>|<span data-ttu-id="3b8a5-132">설명</span><span class="sxs-lookup"><span data-stu-id="3b8a5-132">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="3b8a5-133">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3b8a5-134">설명</span><span class="sxs-lookup"><span data-stu-id="3b8a5-134">Remarks</span></span>

 <span data-ttu-id="3b8a5-135">합니다  **\<supportedRuntime >** 런타임의 1.1 이상 버전을 사용 하 여 빌드된 모든 응용 프로그램에서 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-135">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="3b8a5-136">런타임이 버전 1.0만을 지원 하도록 빌드된 응용 프로그램을 사용 해야 합니다  **\<requiredRuntime >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-136">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="3b8a5-137">Microsoft Internet Explorer에서 호스팅되는 응용 프로그램 시작 코드를 무시 합니다  **\<시작 >** 요소와 해당 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-137">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="3b8a5-138">UseLegacyV2RuntimeActivationPolicy 특성</span><span class="sxs-lookup"><span data-stu-id="3b8a5-138">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="3b8a5-139">이 특성은 응용 프로그램에서 같은 레거시 활성화 경로 사용 하는 경우에 유용 합니다 [CorBindToRuntimeEx 함수](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), 해당 경로 이전 버전 대신 CLR 버전 4를 활성화 하 고 응용 프로그램이 나 사용 하 여 빌드한.NET Framework 4 이전 버전의.NET Framework를 사용 하 여 빌드된 혼합 모드 어셈블리에 종속성을 하지만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-139">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="3b8a5-140">이러한 시나리오에서는 특성을 설정할 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-140">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="3b8a5-141">특성을 설정 `true` CLR 버전 1.1 또는 CLR 버전 2.0-in-process side-by-side-기능을 효과적으로 사용 하지 않도록 설정 하는 동일한 프로세스로 로드 방지 하 고 (참조 [COM Interop에 대 한 Side-by-side-실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="3b8a5-141">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="3b8a5-142">예제</span><span class="sxs-lookup"><span data-stu-id="3b8a5-142">Example</span></span>

 <span data-ttu-id="3b8a5-143">다음 예제에서는 구성 파일에서 런타임 버전을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3b8a5-143">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="3b8a5-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="3b8a5-144">See also</span></span>

- [<span data-ttu-id="3b8a5-145">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3b8a5-145">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3b8a5-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3b8a5-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="3b8a5-147">방법: .NET Framework 4 이상 버전을 지원하도록 앱 구성</span><span class="sxs-lookup"><span data-stu-id="3b8a5-147">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="3b8a5-148">[COM Interop에 대 한 Side-by-side-실행](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3b8a5-148">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="3b8a5-149">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="3b8a5-149">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
