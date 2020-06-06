---
title: <supportedRuntime>구성 요소-.NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: ecbe73593e5b8b87909499f6fff7e865e29b1ec8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "82796043"
---
# <a name="supportedruntime-element"></a><span data-ttu-id="a59f2-102">\<supportedRuntime> 요소</span><span class="sxs-lookup"><span data-stu-id="a59f2-102">\<supportedRuntime> element</span></span>

<span data-ttu-id="a59f2-103">응용 프로그램에서 지 원하는 공용 언어 런타임 버전과 선택적으로 .NET Framework 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-103">Specifies which common language runtime version and, optionally, .NET Framework version the application supports.</span></span>  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a><span data-ttu-id="a59f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a59f2-104">Syntax</span></span>

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a><span data-ttu-id="a59f2-105">특성</span><span class="sxs-lookup"><span data-stu-id="a59f2-105">Attributes</span></span>

|<span data-ttu-id="a59f2-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a59f2-106">Attribute</span></span>|<span data-ttu-id="a59f2-107">Description</span><span class="sxs-lookup"><span data-stu-id="a59f2-107">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a59f2-108">**version**</span><span class="sxs-lookup"><span data-stu-id="a59f2-108">**version**</span></span>|<span data-ttu-id="a59f2-109">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-109">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a59f2-110">애플리케이션이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-110">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="a59f2-111">특성의 유효한 값 `version` 은 ["런타임 버전" 값](#version) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a59f2-111">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="a59f2-112">**참고:**  .NET Framework 3.5를 통해 "*런타임 버전*" 값은 *major*형식을 사용 합니다. *부*. *빌드*.</span><span class="sxs-lookup"><span data-stu-id="a59f2-112">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="a59f2-113">.NET Framework 4부터 주 버전 및 부 버전 번호만 필요 합니다 (즉, "v 4.0.30319" 대신 "v 4.0").</span><span class="sxs-lookup"><span data-stu-id="a59f2-113">Beginning with the .NET Framework 4, only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="a59f2-114">짧은 문자열이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-114">The shorter string is recommended.</span></span>|
|<span data-ttu-id="a59f2-115">**sku**</span><span class="sxs-lookup"><span data-stu-id="a59f2-115">**sku**</span></span>|<span data-ttu-id="a59f2-116">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a59f2-117">이 애플리케이션이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-117">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="a59f2-118">.NET Framework 4.0을 시작할 때에는 `sku` 특성을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-118">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="a59f2-119">존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-119">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="a59f2-120">Sku 특성의 유효한 값은 ["sku id" 값](#sku) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a59f2-120">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a59f2-121">설명</span><span class="sxs-lookup"><span data-stu-id="a59f2-121">Remarks</span></span>

<span data-ttu-id="a59f2-122">**\<supportedRuntime>** 응용 프로그램 구성 파일에 요소가 없는 경우 응용 프로그램을 빌드하는 데 사용 되는 런타임 버전이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-122">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>

<span data-ttu-id="a59f2-123">**\<supportedRuntime>** 버전 1.1 이상을 사용 하 여 빌드된 모든 응용 프로그램에서 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-123">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="a59f2-124">런타임 버전 1.0만 지원 하도록 빌드된 응용 프로그램은 요소를 사용 해야 합니다 [\<requiredRuntime>](requiredruntime-element.md) .</span><span class="sxs-lookup"><span data-stu-id="a59f2-124">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](requiredruntime-element.md) element.</span></span>

> [!NOTE]
> <span data-ttu-id="a59f2-125">[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 함수를 사용 하 여 구성 파일을 지정 하는 경우 `<requiredRuntime>` 모든 버전의 런타임에 대해 요소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-125">If you use the [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="a59f2-126">`<supportedRuntime>` [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)를 사용 하는 경우 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-126">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="a59f2-127">.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-127">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="a59f2-128">.NET Framework 4.0 이상 버전을 지 원하는 앱의 경우 특성은 `version` .NET Framework 4 이상 버전에 공통 된 CLR 버전을 나타내며, `sku` 특성은 앱이 대상으로 하는 단일 .NET Framework 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-128">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates the single .NET Framework version that the app targets.</span></span>

<span data-ttu-id="a59f2-129">**\<supportedRuntime>** 특성이 있는 요소가 `sku` 구성 파일에 있고 설치 된 .NET Framework 버전이 지원 되는 지정 된 버전 보다 낮으면 응용 프로그램이 실행 되지 않고, 지원 되는 버전을 설치 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-129">If the **\<supportedRuntime>** element with the `sku` attribute is present in the configuration file and the installed .NET Framework version is lower then the specified supported version, the application fails to run and instead displays a message asking to install the supported version.</span></span> <span data-ttu-id="a59f2-130">그렇지 않으면 응용 프로그램이 설치 된 모든 버전에서 실행을 시도 하지만 해당 버전과 완전히 호환 되지 않으면 예기치 않게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-130">Otherwise, the application attempts to run on any installed version, but it may behave unexpectedly if it is not fully compatible with that version.</span></span> <span data-ttu-id="a59f2-131">.NET Framework 버전 간의 호환성 차이점 [은 .NET Framework의 응용 프로그램 호환성](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)을 참조 하세요. 따라서 보다 쉬운 오류 진단을 위해이 요소를 응용 프로그램 구성 파일에 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-131">(For compatibility differences between versions of .NET Framework, see [Application compatibility in the .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Therefore, we recommend that you include this element in the application configuration file for easier error diagnostics.</span></span> <span data-ttu-id="a59f2-132">(새 프로젝트를 만들 때 자동으로 생성 된 구성 파일에는 Visual Studio가 이미 포함 되어 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="a59f2-132">(The configuration file automatically generated by Visual Studio when creating a new project already contains it.)</span></span>
  
> [!NOTE]
> <span data-ttu-id="a59f2-133">응용 프로그램에서 [CorBindToRuntimeEx 함수와](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)같은 레거시 활성화 경로를 사용 하 고 이러한 경로를 사용 하 여 이전 버전 대신 CLR의 버전 4를 활성화 하는 경우 또는 응용 프로그램이 .NET Framework 4로 빌드되고 이전 버전의 .NET Framework를 사용 하 여 빌드된 혼합 모드 어셈블리에 대 한 종속성이 있는 경우 지원 되는 런타임 목록에서 .NET Framework 4를 지정 하는 것 만으로는 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-133">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the .NET Framework 4 in the list of supported runtimes.</span></span> <span data-ttu-id="a59f2-134">또한 구성 파일의 [ \<startup> 요소](startup-element.md) 에서 특성을로 설정 해야 합니다 `useLegacyV2RuntimeActivationPolicy` `true` .</span><span class="sxs-lookup"><span data-stu-id="a59f2-134">In addition, in the [\<startup> element](startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="a59f2-135">그러나이 특성을로 설정 하면 `true` 이전 버전의 .NET Framework 빌드된 모든 구성 요소가를 사용 하 여 빌드된 런타임 대신 .NET Framework 4를 사용 하 여 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-135">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the .NET Framework 4 instead of the runtimes they were built with.</span></span>

<span data-ttu-id="a59f2-136">실행할 수 있는 모든 .NET Framework 버전을 사용하여 애플리케이션을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-136">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>

<a name="version"></a>
## <a name="runtime-version-values"></a><span data-ttu-id="a59f2-137">"런타임 버전" 값</span><span class="sxs-lookup"><span data-stu-id="a59f2-137">"runtime version" values</span></span>
<span data-ttu-id="a59f2-138">`runtime`특성은 지정 된 응용 프로그램에 필요한 CLR (공용 언어 런타임) 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-138">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="a59f2-139">모든 .NET Framework (v4. x 버전은 CLR을 지정 합니다. `v4.0`</span><span class="sxs-lookup"><span data-stu-id="a59f2-139">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="a59f2-140">다음 표에서는 특성의 *런타임 버전* 값에 대 한 유효한 값을 보여 줍니다 `version` .</span><span class="sxs-lookup"><span data-stu-id="a59f2-140">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>

|<span data-ttu-id="a59f2-141">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="a59f2-141">.NET Framework version</span></span>|<span data-ttu-id="a59f2-142">`version` 특성</span><span class="sxs-lookup"><span data-stu-id="a59f2-142">`version` attribute</span></span>|
|----------------------------|-------------------------|
|<span data-ttu-id="a59f2-143">1.0</span><span class="sxs-lookup"><span data-stu-id="a59f2-143">1.0</span></span>|<span data-ttu-id="a59f2-144">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="a59f2-144">"v1.0.3705"</span></span>|
|<span data-ttu-id="a59f2-145">1.1</span><span class="sxs-lookup"><span data-stu-id="a59f2-145">1.1</span></span>|<span data-ttu-id="a59f2-146">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="a59f2-146">"v1.1.4322"</span></span>|
|<span data-ttu-id="a59f2-147">2.0</span><span class="sxs-lookup"><span data-stu-id="a59f2-147">2.0</span></span>|<span data-ttu-id="a59f2-148">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="a59f2-148">"v2.0.50727"</span></span>|
|<span data-ttu-id="a59f2-149">3.0</span><span class="sxs-lookup"><span data-stu-id="a59f2-149">3.0</span></span>|<span data-ttu-id="a59f2-150">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="a59f2-150">"v2.0.50727"</span></span>|
|<span data-ttu-id="a59f2-151">3.5</span><span class="sxs-lookup"><span data-stu-id="a59f2-151">3.5</span></span>|<span data-ttu-id="a59f2-152">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="a59f2-152">"v2.0.50727"</span></span>|
|<span data-ttu-id="a59f2-153">4.0-4.8</span><span class="sxs-lookup"><span data-stu-id="a59f2-153">4.0-4.8</span></span>|<span data-ttu-id="a59f2-154">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="a59f2-154">"v4.0"</span></span>|

## <a name="sku-id-values"></a><a name="sku"></a><span data-ttu-id="a59f2-155">"sku id" 값</span><span class="sxs-lookup"><span data-stu-id="a59f2-155">"sku id" values</span></span>

<span data-ttu-id="a59f2-156">`sku`특성은 TFM (대상 프레임 워크 모니커)를 사용 하 여 앱이 대상으로 하 고 실행 해야 하는 .NET Framework 버전을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-156">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="a59f2-157">다음 표에서는 `sku` .NET Framework 4부터 시작 하 여 특성에서 지원 되는 유효한 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-157">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>

|<span data-ttu-id="a59f2-158">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="a59f2-158">.NET Framework version</span></span>|<span data-ttu-id="a59f2-159">`sku` 특성</span><span class="sxs-lookup"><span data-stu-id="a59f2-159">`sku` attribute</span></span>|
|----------------------------|---------------------|
|<span data-ttu-id="a59f2-160">4.0</span><span class="sxs-lookup"><span data-stu-id="a59f2-160">4.0</span></span>|<span data-ttu-id="a59f2-161">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="a59f2-161">".NETFramework,Version=v4.0"</span></span>|
|<span data-ttu-id="a59f2-162">4.0, Client Profile</span><span class="sxs-lookup"><span data-stu-id="a59f2-162">4.0, Client Profile</span></span>|<span data-ttu-id="a59f2-163">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="a59f2-163">".NETFramework,Version=v4.0,Profile=Client"</span></span>|
|<span data-ttu-id="a59f2-164">4.0, 플랫폼 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="a59f2-164">4.0, platform update 1</span></span>|<span data-ttu-id="a59f2-165">". NETFramework, Version = v 4.0.1 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-165">".NETFramework,Version=v4.0.1"</span></span>|
|<span data-ttu-id="a59f2-166">4.0, Client Profile, 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="a59f2-166">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="a59f2-167">". NETFramework, Version = v 4.0.1, Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="a59f2-167">".NETFramework,Version=v4.0.1,Profile=Client"</span></span>|
|<span data-ttu-id="a59f2-168">4.0, 플랫폼 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a59f2-168">4.0, platform update 2</span></span>|<span data-ttu-id="a59f2-169">". NETFramework, Version = v 4.0.2 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-169">".NETFramework,Version=v4.0.2"</span></span>|
|<span data-ttu-id="a59f2-170">4.0, Client Profile, 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="a59f2-170">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="a59f2-171">". NETFramework, Version = v 4.0.2, Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="a59f2-171">".NETFramework,Version=v4.0.2,Profile=Client"</span></span>|
|<span data-ttu-id="a59f2-172">4.0, 플랫폼 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="a59f2-172">4.0, platform update 3</span></span>|<span data-ttu-id="a59f2-173">". NETFramework, Version = v 4.0.3 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-173">".NETFramework,Version=v4.0.3"</span></span>|
|<span data-ttu-id="a59f2-174">4.0, Client Profile, 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="a59f2-174">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="a59f2-175">". NETFramework, Version = v 4.0.3, Profile = Client "</span><span class="sxs-lookup"><span data-stu-id="a59f2-175">".NETFramework,Version=v4.0.3,Profile=Client"</span></span>|
|<span data-ttu-id="a59f2-176">4.5</span><span class="sxs-lookup"><span data-stu-id="a59f2-176">4.5</span></span>|<span data-ttu-id="a59f2-177">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="a59f2-177">".NETFramework,Version=v4.5"</span></span>|
|<span data-ttu-id="a59f2-178">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a59f2-178">4.5.1</span></span>|<span data-ttu-id="a59f2-179">".NETFramework,Version=v4.5.1"</span><span class="sxs-lookup"><span data-stu-id="a59f2-179">".NETFramework,Version=v4.5.1"</span></span>|
|<span data-ttu-id="a59f2-180">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a59f2-180">4.5.2</span></span>|<span data-ttu-id="a59f2-181">".NETFramework,Version=v4.5.2"</span><span class="sxs-lookup"><span data-stu-id="a59f2-181">".NETFramework,Version=v4.5.2"</span></span>|
|<span data-ttu-id="a59f2-182">4.6</span><span class="sxs-lookup"><span data-stu-id="a59f2-182">4.6</span></span>|<span data-ttu-id="a59f2-183">".NETFramework,Version=v4.6"</span><span class="sxs-lookup"><span data-stu-id="a59f2-183">".NETFramework,Version=v4.6"</span></span>|
|<span data-ttu-id="a59f2-184">4.6.1</span><span class="sxs-lookup"><span data-stu-id="a59f2-184">4.6.1</span></span>|<span data-ttu-id="a59f2-185">".NETFramework,Version=v4.6.1"</span><span class="sxs-lookup"><span data-stu-id="a59f2-185">".NETFramework,Version=v4.6.1"</span></span>|
|<span data-ttu-id="a59f2-186">4.6.2</span><span class="sxs-lookup"><span data-stu-id="a59f2-186">4.6.2</span></span>|<span data-ttu-id="a59f2-187">". NETFramework, Version = v 4.6.2 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-187">".NETFramework,Version=v4.6.2"</span></span>|
|<span data-ttu-id="a59f2-188">4.7</span><span class="sxs-lookup"><span data-stu-id="a59f2-188">4.7</span></span>|<span data-ttu-id="a59f2-189">". NETFramework, Version = v 4.7 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-189">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="a59f2-190">4.7.1</span><span class="sxs-lookup"><span data-stu-id="a59f2-190">4.7.1</span></span>|<span data-ttu-id="a59f2-191">". NETFramework, Version = v 4.7.1 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-191">".NETFramework,Version=v4.7.1"</span></span>|
|<span data-ttu-id="a59f2-192">4.7.2</span><span class="sxs-lookup"><span data-stu-id="a59f2-192">4.7.2</span></span>|<span data-ttu-id="a59f2-193">". NETFramework, Version = v 4.7.2 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-193">".NETFramework,Version=v4.7.2"</span></span>|
|<span data-ttu-id="a59f2-194">4.8</span><span class="sxs-lookup"><span data-stu-id="a59f2-194">4.8</span></span>|<span data-ttu-id="a59f2-195">". NETFramework, Version = v 4.8 "</span><span class="sxs-lookup"><span data-stu-id="a59f2-195">".NETFramework,Version=v4.8"</span></span>|

## <a name="example"></a><span data-ttu-id="a59f2-196">예제</span><span class="sxs-lookup"><span data-stu-id="a59f2-196">Example</span></span>

<span data-ttu-id="a59f2-197">다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-197">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="a59f2-198">구성 파일은 앱이 .NET Framework 4.7를 대상으로 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-198">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="a59f2-199">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a59f2-199">Configuration file</span></span>

<span data-ttu-id="a59f2-200">이 요소는 애플리케이션 구성 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a59f2-200">This element can be used in the application configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="a59f2-201">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a59f2-201">See also</span></span>

- [<span data-ttu-id="a59f2-202">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a59f2-202">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a59f2-203">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a59f2-203">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a59f2-204">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="a59f2-204">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
