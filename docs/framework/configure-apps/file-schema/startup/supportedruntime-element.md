---
title: <supportedRuntime>구성 요소 - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153700"
---
# <a name="supportedruntime-element"></a><span data-ttu-id="c24de-102">\<지원되는런타임> 요소</span><span class="sxs-lookup"><span data-stu-id="c24de-102">\<supportedRuntime> element</span></span>

<span data-ttu-id="c24de-103">응용 프로그램에서 지원하는 공통 언어 런타임 버전과 선택적으로 .NET Framework 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-103">Specifies which common language runtime version and, optionally, .NET Framework version the application supports.</span></span>  

[<span data-ttu-id="c24de-104">\<구성></span><span class="sxs-lookup"><span data-stu-id="c24de-104">\<configuration></span></span>](../configuration-element.md)  
<span data-ttu-id="c24de-105">&nbsp;&nbsp;[\<스타트업>](startup-element.md)</span><span class="sxs-lookup"><span data-stu-id="c24de-105">&nbsp;&nbsp;[\<startup>](startup-element.md)</span></span>  
<span data-ttu-id="c24de-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<지원런타임>**</span><span class="sxs-lookup"><span data-stu-id="c24de-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="c24de-107">구문</span><span class="sxs-lookup"><span data-stu-id="c24de-107">Syntax</span></span>

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a><span data-ttu-id="c24de-108">특성</span><span class="sxs-lookup"><span data-stu-id="c24de-108">Attributes</span></span>

|<span data-ttu-id="c24de-109">attribute</span><span class="sxs-lookup"><span data-stu-id="c24de-109">Attribute</span></span>|<span data-ttu-id="c24de-110">Description</span><span class="sxs-lookup"><span data-stu-id="c24de-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="c24de-111">**version**</span><span class="sxs-lookup"><span data-stu-id="c24de-111">**version**</span></span>|<span data-ttu-id="c24de-112">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c24de-113">애플리케이션이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-113">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="c24de-114">특성의 유효한 `version` 값에 대 한 ["런타임 버전" 값](#version) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c24de-114">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="c24de-115">**참고:**  .NET Framework 3.5를 통해 *"런타임 버전"* 값은 폼 *을 major합니다.* *사소한*. *빌드*.</span><span class="sxs-lookup"><span data-stu-id="c24de-115">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="c24de-116">.NET Framework 4부터는 주 버전 과 부 버전 번호만 필요합니다(즉, "v4.0.30319" 대신 "v4.0").</span><span class="sxs-lookup"><span data-stu-id="c24de-116">Beginning with the .NET Framework 4, only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="c24de-117">짧은 문자열이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-117">The shorter string is recommended.</span></span>|
|<span data-ttu-id="c24de-118">**sku**</span><span class="sxs-lookup"><span data-stu-id="c24de-118">**sku**</span></span>|<span data-ttu-id="c24de-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="c24de-120">이 애플리케이션이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-120">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="c24de-121">.NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-121">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="c24de-122">존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-122">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="c24de-123">sku 특성의 유효한 값은 ["sku id" 값](#sku) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c24de-123">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c24de-124">설명</span><span class="sxs-lookup"><span data-stu-id="c24de-124">Remarks</span></span>

<span data-ttu-id="c24de-125">\*\* \<지원되는Runtime>\*\* 요소가 응용 프로그램 구성 파일에 없는 경우 응용 프로그램을 빌드하는 데 사용되는 런타임 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-125">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>

<span data-ttu-id="c24de-126">\*\* \<지원되는런타임>\*\* 요소는 런타임의 버전 1.1 이상을 사용하여 빌드된 모든 응용 프로그램에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-126">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="c24de-127">런타임의 버전 1.0만 지원하도록 빌드된 응용 프로그램은 [ \<필수런타임>](../startup/requiredruntime-element.md) 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-127">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](../startup/requiredruntime-element.md) element.</span></span>

> [!NOTE]
> <span data-ttu-id="c24de-128">[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용하여 구성 파일을 지정하는 경우 `<requiredRuntime>` 런타임의 모든 버전에 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-128">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="c24de-129">`<supportedRuntime>` [CorBindToRuntimeByCfg를](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)사용할 때 요소는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-129">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="c24de-130">.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-130">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="c24de-131">.NET Framework 4.0 이상 버전을 지원하는 앱의 `version` 경우 속성은 .NET Framework 4 및 이후 버전에 공통적인 `sku` CLR 버전을 나타내며, 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-131">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates the single .NET Framework version that the app targets.</span></span>

<span data-ttu-id="c24de-132">특성이 `sku` 있는 **지원되는Runtime>요소가 구성 파일에 있고 설치된 .NET Framework 버전이 더 낮은 경우 지정된 지원되는 버전이 더 낮으면 응용 프로그램이 실행되지 않고 대신 지원되는 버전을 설치하라는 메시지가 \<** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-132">If the **\<supportedRuntime>** element with the `sku` attribute is present in the configuration file and the installed .NET Framework version is lower then the specified supported version, the application fails to run and instead displays a message asking to install the supported version.</span></span> <span data-ttu-id="c24de-133">그렇지 않으면 응용 프로그램이 설치된 모든 버전에서 실행하려고 시도하지만 해당 버전과 완전히 호환되지 않으면 예기치 않게 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-133">Otherwise, the application attempts to run on any installed version, but it may behave unexpectedly if it is not fully compatible with that version.</span></span> <span data-ttu-id="c24de-134">.NET Framework 버전 간의 호환성 차이는 [.NET Framework의 응용 프로그램 호환성을](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)참조하십시오. 따라서 쉽게 오류 진단을 위해 응용 프로그램 구성 파일에 이 요소를 포함하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-134">(For compatibility differences between versions of .NET Framework, see [Application compatibility in the .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Therefore, we recommend that you include this element in the application configuration file for easier error diagnostics.</span></span> <span data-ttu-id="c24de-135">(새 프로젝트를 만들 때 Visual Studio에서 자동으로 생성된 구성 파일에는 이미 포함되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c24de-135">(The configuration file automatically generated by Visual Studio when creating a new project already contains it.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="c24de-136">응용 프로그램에서 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용하고 해당 경로가 이전 버전 대신 CLR의 버전 4를 활성화하도록 하거나 응용 프로그램이 .NET Framework 4로 빌드되었지만 .NET Framework의 이전 버전으로 빌드된 혼합 모드 어셈블리에 종속되어 있는 경우 지원되는 런타임 목록에 .NET Framework 4를 지정하기에 충분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-136">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the .NET Framework 4 in the list of supported runtimes.</span></span> <span data-ttu-id="c24de-137">또한 구성 파일의 `useLegacyV2RuntimeActivationPolicy` `true` [ \<시작> 요소에서](../startup/startup-element.md) 속성을 로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-137">In addition, in the [\<startup> element](../startup/startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="c24de-138">그러나 이 특성을 `true` 설정하면 이전 버전의 .NET Framework로 빌드된 모든 구성 요소가 빌드된 런타임 대신 .NET Framework 4를 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-138">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the .NET Framework 4 instead of the runtimes they were built with.</span></span>

<span data-ttu-id="c24de-139">실행할 수 있는 모든 .NET Framework 버전을 사용하여 애플리케이션을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-139">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>

<a name="version"></a>
## <a name="runtime-version-values"></a><span data-ttu-id="c24de-140">"런타임 버전" 값</span><span class="sxs-lookup"><span data-stu-id="c24de-140">"runtime version" values</span></span>
<span data-ttu-id="c24de-141">특성은 `runtime` 지정된 응용 프로그램에 필요한 공통 언어 런타임(CLR) 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-141">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="c24de-142">모든 .NET 프레임워크 v4.x 버전은 `v4.0` CLR을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-142">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="c24de-143">다음 표에는 특성의 *런타임 버전* 값에 대한 유효한 값이 나열됩니다. `version`</span><span class="sxs-lookup"><span data-stu-id="c24de-143">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>

|<span data-ttu-id="c24de-144">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="c24de-144">.NET Framework version</span></span>|<span data-ttu-id="c24de-145">`version` 특성</span><span class="sxs-lookup"><span data-stu-id="c24de-145">`version` attribute</span></span>|
|----------------------------|-------------------------|
|<span data-ttu-id="c24de-146">1.0</span><span class="sxs-lookup"><span data-stu-id="c24de-146">1.0</span></span>|<span data-ttu-id="c24de-147">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="c24de-147">"v1.0.3705"</span></span>|
|<span data-ttu-id="c24de-148">1.1</span><span class="sxs-lookup"><span data-stu-id="c24de-148">1.1</span></span>|<span data-ttu-id="c24de-149">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="c24de-149">"v1.1.4322"</span></span>|
|<span data-ttu-id="c24de-150">2.0</span><span class="sxs-lookup"><span data-stu-id="c24de-150">2.0</span></span>|<span data-ttu-id="c24de-151">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="c24de-151">"v2.0.50727"</span></span>|
|<span data-ttu-id="c24de-152">3.0</span><span class="sxs-lookup"><span data-stu-id="c24de-152">3.0</span></span>|<span data-ttu-id="c24de-153">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="c24de-153">"v2.0.50727"</span></span>|
|<span data-ttu-id="c24de-154">3.5</span><span class="sxs-lookup"><span data-stu-id="c24de-154">3.5</span></span>|<span data-ttu-id="c24de-155">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="c24de-155">"v2.0.50727"</span></span>|
|<span data-ttu-id="c24de-156">4.0-4.8</span><span class="sxs-lookup"><span data-stu-id="c24de-156">4.0-4.8</span></span>|<span data-ttu-id="c24de-157">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="c24de-157">"v4.0"</span></span>|

## <a name="sku-id-values"></a><a name="sku"></a><span data-ttu-id="c24de-158">"sku ID" 값</span><span class="sxs-lookup"><span data-stu-id="c24de-158">"sku id" values</span></span>

<span data-ttu-id="c24de-159">특성은 `sku` TFM(대상 프레임워크 모니커)을 사용하여 앱이 대상으로 하고 실행하는 데 필요한 .NET Framework의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-159">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="c24de-160">다음 표에는 .NET Framework 4부터 시작하여 특성에서 `sku` 지원하는 유효한 값이 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-160">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>

|<span data-ttu-id="c24de-161">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="c24de-161">.NET Framework version</span></span>|<span data-ttu-id="c24de-162">`sku` 특성</span><span class="sxs-lookup"><span data-stu-id="c24de-162">`sku` attribute</span></span>|
|----------------------------|---------------------|
|<span data-ttu-id="c24de-163">4.0</span><span class="sxs-lookup"><span data-stu-id="c24de-163">4.0</span></span>|<span data-ttu-id="c24de-164">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="c24de-164">".NETFramework,Version=v4.0"</span></span>|
|<span data-ttu-id="c24de-165">4.0, Client Profile</span><span class="sxs-lookup"><span data-stu-id="c24de-165">4.0, Client Profile</span></span>|<span data-ttu-id="c24de-166">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="c24de-166">".NETFramework,Version=v4.0,Profile=Client"</span></span>|
|<span data-ttu-id="c24de-167">4.0, 플랫폼 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="c24de-167">4.0, platform update 1</span></span>|<span data-ttu-id="c24de-168">". 넷 프레임 워크, 버전 = v4.0.1"</span><span class="sxs-lookup"><span data-stu-id="c24de-168">".NETFramework,Version=v4.0.1"</span></span>|
|<span data-ttu-id="c24de-169">4.0, Client Profile, 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="c24de-169">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="c24de-170">". NETFramework, 버전= v4.0.1, 프로필=클라이언트"</span><span class="sxs-lookup"><span data-stu-id="c24de-170">".NETFramework,Version=v4.0.1,Profile=Client"</span></span>|
|<span data-ttu-id="c24de-171">4.0, 플랫폼 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="c24de-171">4.0, platform update 2</span></span>|<span data-ttu-id="c24de-172">". 넷 프레임 워크, 버전 = v4.0.2"</span><span class="sxs-lookup"><span data-stu-id="c24de-172">".NETFramework,Version=v4.0.2"</span></span>|
|<span data-ttu-id="c24de-173">4.0, Client Profile, 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="c24de-173">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="c24de-174">". NETFramework, 버전= v4.0.2, 프로필=클라이언트"</span><span class="sxs-lookup"><span data-stu-id="c24de-174">".NETFramework,Version=v4.0.2,Profile=Client"</span></span>|
|<span data-ttu-id="c24de-175">4.0, 플랫폼 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="c24de-175">4.0, platform update 3</span></span>|<span data-ttu-id="c24de-176">". 넷 프레임 워크, 버전 = v4.0.3"</span><span class="sxs-lookup"><span data-stu-id="c24de-176">".NETFramework,Version=v4.0.3"</span></span>|
|<span data-ttu-id="c24de-177">4.0, Client Profile, 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="c24de-177">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="c24de-178">". NETFramework, 버전= v4.0.3, 프로필=클라이언트"</span><span class="sxs-lookup"><span data-stu-id="c24de-178">".NETFramework,Version=v4.0.3,Profile=Client"</span></span>|
|<span data-ttu-id="c24de-179">4.5.</span><span class="sxs-lookup"><span data-stu-id="c24de-179">4.5</span></span>|<span data-ttu-id="c24de-180">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="c24de-180">".NETFramework,Version=v4.5"</span></span>|
|<span data-ttu-id="c24de-181">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c24de-181">4.5.1</span></span>|<span data-ttu-id="c24de-182">".NETFramework,Version=v4.5.1"</span><span class="sxs-lookup"><span data-stu-id="c24de-182">".NETFramework,Version=v4.5.1"</span></span>|
|<span data-ttu-id="c24de-183">4.5.2</span><span class="sxs-lookup"><span data-stu-id="c24de-183">4.5.2</span></span>|<span data-ttu-id="c24de-184">".NETFramework,Version=v4.5.2"</span><span class="sxs-lookup"><span data-stu-id="c24de-184">".NETFramework,Version=v4.5.2"</span></span>|
|<span data-ttu-id="c24de-185">4.6</span><span class="sxs-lookup"><span data-stu-id="c24de-185">4.6</span></span>|<span data-ttu-id="c24de-186">".NETFramework,Version=v4.6"</span><span class="sxs-lookup"><span data-stu-id="c24de-186">".NETFramework,Version=v4.6"</span></span>|
|<span data-ttu-id="c24de-187">4.6.1</span><span class="sxs-lookup"><span data-stu-id="c24de-187">4.6.1</span></span>|<span data-ttu-id="c24de-188">".NETFramework,Version=v4.6.1"</span><span class="sxs-lookup"><span data-stu-id="c24de-188">".NETFramework,Version=v4.6.1"</span></span>|
|<span data-ttu-id="c24de-189">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c24de-189">4.6.2</span></span>|<span data-ttu-id="c24de-190">". 넷 프레임 워크, 버전 = v4.6.2"</span><span class="sxs-lookup"><span data-stu-id="c24de-190">".NETFramework,Version=v4.6.2"</span></span>|
|<span data-ttu-id="c24de-191">4.7</span><span class="sxs-lookup"><span data-stu-id="c24de-191">4.7</span></span>|<span data-ttu-id="c24de-192">". 넷 프레임 워크, 버전 = v4.7"</span><span class="sxs-lookup"><span data-stu-id="c24de-192">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="c24de-193">4.7.1</span><span class="sxs-lookup"><span data-stu-id="c24de-193">4.7.1</span></span>|<span data-ttu-id="c24de-194">". 넷 프레임 워크, 버전 = v4.7.1"</span><span class="sxs-lookup"><span data-stu-id="c24de-194">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="c24de-195">4.7.2</span><span class="sxs-lookup"><span data-stu-id="c24de-195">4.7.2</span></span>|<span data-ttu-id="c24de-196">". 넷 프레임 워크, 버전 = v4.7.2"</span><span class="sxs-lookup"><span data-stu-id="c24de-196">".NETFramework,Version=v4.7.2"</span></span>|
|<span data-ttu-id="c24de-197">4.8</span><span class="sxs-lookup"><span data-stu-id="c24de-197">4.8</span></span>|<span data-ttu-id="c24de-198">". 넷 프레임 워크, 버전 = v4.8"</span><span class="sxs-lookup"><span data-stu-id="c24de-198">".NETFramework,Version=v4.8"</span></span>|

## <a name="example"></a><span data-ttu-id="c24de-199">예제</span><span class="sxs-lookup"><span data-stu-id="c24de-199">Example</span></span>

<span data-ttu-id="c24de-200">다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-200">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="c24de-201">구성 파일은 앱이 .NET Framework 4.7을 대상으로 한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-201">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="c24de-202">구성 파일</span><span class="sxs-lookup"><span data-stu-id="c24de-202">Configuration file</span></span>

<span data-ttu-id="c24de-203">이 요소는 애플리케이션 구성 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c24de-203">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="c24de-204">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c24de-204">See also</span></span>

- [<span data-ttu-id="c24de-205">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c24de-205">Startup Settings Schema</span></span>](../startup/index.md)
- [<span data-ttu-id="c24de-206">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c24de-206">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c24de-207">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="c24de-207">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
