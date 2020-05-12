---
title: global.json 개요
description: .NET Core CLI 명령을 실행할 때 global.json 파일을 사용하여 .NET Core SDK 버전을 설정하는 방법에 대해 알아보세요.
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: 15d8e6191394b9ba67b1e5eb5e8ae54ebaf61bef
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795510"
---
# <a name="globaljson-overview"></a><span data-ttu-id="d3590-103">global.json 개요</span><span class="sxs-lookup"><span data-stu-id="d3590-103">global.json overview</span></span>

<span data-ttu-id="d3590-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d3590-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="d3590-105">*global.json* 파일을 사용하면 .NET Core CLI 명령을 실행할 때 어떤 .NET Core SDK 버전을 사용할지 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-105">The *global.json* file allows you to define which .NET Core SDK version is used when you run .NET Core CLI commands.</span></span> <span data-ttu-id="d3590-106">.NET Core SDK를 선택하는 것은 프로젝트가 대상으로 하는 런타임을 지정하는 것과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-106">Selecting the .NET Core SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="d3590-107">.NET Core SDK 버전은 사용된 .NET Core CLI 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-107">The .NET Core SDK version indicates which versions of the .NET Core CLI is used.</span></span>

<span data-ttu-id="d3590-108">일반적으로 최신 버전의 SDK Tools를 사용하려고 하기 때문에 *global.json* 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="d3590-109">일부 고급 시나리오에서는 SDK Tools의 버전을 컨트롤하는 것이 좋습니다. 이 문서에서는 해당 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="d3590-110">대신 런타임 지정에 대한 자세한 내용은 [대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="d3590-111">.NET Core SDK는 현재 작업 디렉터리(반드시 프로젝트 디렉터리와 동일하지는 않음) 또는 상위 디렉터리 중 하나에서 *global.json* 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-111">.NET Core SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="d3590-112">global.json 스키마</span><span class="sxs-lookup"><span data-stu-id="d3590-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="d3590-113">sdk</span><span class="sxs-lookup"><span data-stu-id="d3590-113">sdk</span></span>

<span data-ttu-id="d3590-114">형식: `object`</span><span class="sxs-lookup"><span data-stu-id="d3590-114">Type: `object`</span></span>

<span data-ttu-id="d3590-115">선택할 .NET Core SDK에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-115">Specifies information about the .NET Core SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="d3590-116">버전</span><span class="sxs-lookup"><span data-stu-id="d3590-116">version</span></span>

- <span data-ttu-id="d3590-117">형식: `string`</span><span class="sxs-lookup"><span data-stu-id="d3590-117">Type: `string`</span></span>

- <span data-ttu-id="d3590-118">.NET Core 1.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="d3590-119">사용할 .NET Core SDK의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-119">The version of the .NET Core SDK to use.</span></span>

<span data-ttu-id="d3590-120">이 필드:</span><span class="sxs-lookup"><span data-stu-id="d3590-120">This field:</span></span>

- <span data-ttu-id="d3590-121">와일드카드를 지원하지 않습니다. 즉, 전체 버전 번호가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="d3590-122">버전 범위를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="d3590-123">시험판 허용</span><span class="sxs-lookup"><span data-stu-id="d3590-123">allowPrerelease</span></span>

- <span data-ttu-id="d3590-124">형식: `boolean`</span><span class="sxs-lookup"><span data-stu-id="d3590-124">Type: `boolean`</span></span>

- <span data-ttu-id="d3590-125">.NET Core 3.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="d3590-126">사용할 SDK 버전을 선택할 때 SDK 확인자가 시험판 버전을 고려해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="d3590-127">이 값을 명시적으로 설정하지 않은 경우 Visual Studio에서 실행하고 있는지에 따라 기본값이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="d3590-128">Visual Studio에서 실행하지 **않는** 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="d3590-129">Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="d3590-130">즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 기본값은 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="d3590-131">롤포워드</span><span class="sxs-lookup"><span data-stu-id="d3590-131">rollForward</span></span>

- <span data-ttu-id="d3590-132">형식: `string`</span><span class="sxs-lookup"><span data-stu-id="d3590-132">Type: `string`</span></span>

- <span data-ttu-id="d3590-133">.NET Core 3.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="d3590-134">SDK 버전을 선택할 때, 특정 SDK 버전이 누락된 경우 대체하거나 상위 버전을 사용하기 위한 지시문으로 사용할 롤포워드 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="d3590-135">버전을 `latestMajor`로 설정하지 않는 한 `rollForward` 값을 사용하여 [버전](#version)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>

<span data-ttu-id="d3590-136">사용 가능한 정책 및 해당 동작을 이해하려면 `x.y.znn` 형식의 SDK 버전에 대한 다음 정의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-136">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="d3590-137">`x`는 주 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-137">`x` is the major version.</span></span>
- <span data-ttu-id="d3590-138">`y`는 부 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-138">`y` is the minor version.</span></span>
- <span data-ttu-id="d3590-139">`z`는 기능 밴드입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-139">`z` is the feature band.</span></span>
- <span data-ttu-id="d3590-140">`nn`은 패치 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-140">`nn` is the patch version.</span></span>

<span data-ttu-id="d3590-141">다음 표에서는 `rollForward` 키에 사용할 수 있는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-141">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="d3590-142">값</span><span class="sxs-lookup"><span data-stu-id="d3590-142">Value</span></span>         | <span data-ttu-id="d3590-143">동작</span><span class="sxs-lookup"><span data-stu-id="d3590-143">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="d3590-144">지정한 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-144">Uses the specified version.</span></span> <br> <span data-ttu-id="d3590-145">버전이 없으면 최신 패치 수준으로 롤포워드하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-145">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="d3590-146">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-146">If not found, fails.</span></span> <br><br> <span data-ttu-id="d3590-147">이 값은 이전 버전의 SDK에서 발생하는 레거시 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-147">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="d3590-148">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-148">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="d3590-149">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-149">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-150">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-150">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="d3590-151">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-151">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="d3590-152">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-152">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-153">최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-153">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-154">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-154">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="d3590-155">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-155">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="d3590-156">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-156">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-157">최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-157">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-158">최신 패치 수준을 찾을 수 없는 경우 다음 상위 주 버전, 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-158">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="d3590-159">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-159">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="d3590-160">요청된 주 버전, 부 버전 및 기능 밴드와 패치 수준이 일치하고 지정된 값과 같거나 큰 최신 설치된 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-160">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="d3590-161">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-161">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="d3590-162">요청된 주 버전과 부 버전이 지정된 값과 같거나 큰 기능 밴드와 일치하는 설치된 최상위 기능 밴드와 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-162">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="d3590-163">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-163">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="d3590-164">요청된 주 버전이 지정된 값보다 크거나 같은 부 버전과 일치하는 최상위 부 버전, 기능 밴드 및 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-164">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="d3590-165">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-165">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="d3590-166">지정된 값보다 크거나 같은 주 버전과 함께 최상위 .Net Core SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-166">Uses the highest installed .NET Core SDK with a major that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="d3590-167">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-167">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="d3590-168">롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-168">Doesn't roll forward.</span></span> <span data-ttu-id="d3590-169">정확하게 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-169">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="d3590-170">msbuild-sdk</span><span class="sxs-lookup"><span data-stu-id="d3590-170">msbuild-sdks</span></span>

<span data-ttu-id="d3590-171">형식: `object`</span><span class="sxs-lookup"><span data-stu-id="d3590-171">Type: `object`</span></span>

<span data-ttu-id="d3590-172">개별 프로젝트가 아닌 한 곳에서 프로젝트 SDK 버전을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-172">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="d3590-173">자세한 내용은 [프로젝트 SDK를 확인하는 방법](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-173">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="d3590-174">예</span><span class="sxs-lookup"><span data-stu-id="d3590-174">Examples</span></span>

<span data-ttu-id="d3590-175">다음 예제에서는 시험판 버전을 사용하지 않는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-175">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="d3590-176">다음 예제에서는 지정된 버전과 같거나 높은 최상위 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-176">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="d3590-177">표시된 JSON은 2.2.200 이전 SDK 버전을 허용하지 않으며 2.2.200 이상 버전(3.0.xxx 및 3.1.xxx 포함)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-177">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="d3590-178">다음 예제에서는 정확하게 지정된 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-178">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="d3590-179">다음 예제에서는 설치된 특정 주 버전과 부 버전의 최신 기능 밴드 및 패치 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-179">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="d3590-180">표시된 JSON은 3.1.102 이전 SDK 버전을 허용하지 않으며 3.1.102 이상인 3.1.xxx 버전(예: 3.1.103 또는 3.1.200)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-180">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="d3590-181">다음 예제에서는 특정 버전으로 설치된 최상위 패치 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-181">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="d3590-182">표시된 JSON은 3.1.102 이전 SDK 버전을 허용하지 않으며 3.1.102 이상인 3.1.1xx 버전(예: 3.1.103 또는 3.1.199)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-182">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a><span data-ttu-id="d3590-183">global.json 및 .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="d3590-183">global.json and the .NET Core CLI</span></span>

<span data-ttu-id="d3590-184">*global json* 파일에 버전을 설정하기 위해서는 컴퓨터에 설치된 SDK 버전을 알고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-184">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="d3590-185">이 작업을 수행하는 방법에 대한 자세한 내용은 [.NET Core가 이미 설치되어 있는지 확인하는 방법](../install/how-to-detect-installed-versions.md#check-sdk-versions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-185">For more information on how to do that, see [How to check that .NET Core is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="d3590-186">컴퓨터에 추가 .NET Core SDK 버전을 설치하려면 [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-186">To install additional .NET Core SDK versions on your machine, visit the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>

<span data-ttu-id="d3590-187">다음 예제와 비슷한 [dotnet new](dotnet-new.md) 명령을 실행하여 현재 디렉터리에서 *global.json* 파일을 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-187">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="d3590-188">일치 규칙</span><span class="sxs-lookup"><span data-stu-id="d3590-188">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="d3590-189">일치 규칙은 설치된 모든 .NET Core 설치 런타임에서 공통으로 사용되는 `dotnet.exe` 진입점에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-189">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET Core installed runtimes.</span></span> <span data-ttu-id="d3590-190">여러 개의 런타임이 나란히 설치된 경우 최신 버전의 .NET Corea Runtime에 대한 일치하는 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-190">The matching rules for the latest installed version of the .NET Core Runtime are used when you have multiple runtimes installed side-by-side.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="d3590-191">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="d3590-191">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="d3590-192">.NET Core 3.0부터는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-192">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="d3590-193">*global. json* 파일을 찾을 수 없거나 *global.json*이 SDK 버전 또는 `allowPrerelease` 값을 지정하지 않은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`을 `latestMajor`로 설정하는 것과 같음).</span><span class="sxs-lookup"><span data-stu-id="d3590-193">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="d3590-194">시험판 SDK 버전을 고려하는지는 `dotnet`을 호출하는 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-194">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="d3590-195">Visual Studio에서 실행하지 **않는** 경우 시험판 버전이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-195">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="d3590-196">Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-196">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="d3590-197">즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK의 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 시험판 버전이 고려됩니다. 그렇지 않으면 릴리스 버전만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-197">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="d3590-198">SDK 버전을 지정하지 않고 `allowPrerelease` 값을 지정하는 *global.json* 파일을 찾은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`를 `latestMajor`로 설정하는 것과 같음).</span><span class="sxs-lookup"><span data-stu-id="d3590-198">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="d3590-199">최신 SDK 버전을 릴리스 또는 시험판이 될 수 있는지는 `allowPrerelease` 값에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-199">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="d3590-200">`true`는 시험판 버전이 고려됨을 나타냅니다. `false`는 릴리스 버전만 고려됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-200">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="d3590-201">*global.json* 파일을 찾아 SDK 버전을 지정하는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-201">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="d3590-202">`rollFoward` 값이 설정되지 않은 경우 `latestPatch`를 기본 `rollForward` 정책으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-202">If no `rollFoward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="d3590-203">그렇지 않으면 [롤포워드](#rollforward) 섹션에서 각 값과 해당 동작을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-203">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="d3590-204">시험판 버전을 고려하는지와 `allowPrerelease`가 설정되지 않은 경우의 기본 동작은 [allowPrerelease](#allowprerelease) 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-204">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="d3590-205">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d3590-205">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d3590-206">.NET Core 2.x SDK에서는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-206">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="d3590-207">*global.json* 파일이 없거나 *global.json*이 SDK 버전을 지정하지 않으면 최신 설치된 SDK 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-207">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="d3590-208">최신 SDK 버전은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-208">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="d3590-209">*global.json*이 SDK 버전을 지정하는 경우</span><span class="sxs-lookup"><span data-stu-id="d3590-209">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="d3590-210">지정된 SDK 버전이 머신에서 발견되면 정확한 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-210">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="d3590-211">지정된 SDK 버전이 시스템에서 발견되지 않으면 해당 버전의 최신 **패치 버전**이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-211">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="d3590-212">설치된 최신 SDK **패치 버전**은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-212">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="d3590-213">.NET Core 2.1 이상에서는 지정된 **패치 버전**보다 낮은 **패치 버전**은 SDK 선택에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-213">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="d3590-214">지정된 SDK 버전과 적절한 SDK **패치 버전**을 찾을 수 없으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-214">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="d3590-215">SDK 버전은 다음과 같은 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-215">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="d3590-216">.NET Core SDK의 **기능 릴리스**는 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 첫 번째 자리(`x`)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-216">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="d3590-217">일반적으로 .NET Core SDK는 .NET Core보다 릴리스 주기가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-217">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="d3590-218">**패치 버전**은 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 마지막 두 자리(`yz`)로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-218">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="d3590-219">예를 들어, SDK 버전으로 `2.1.300`을 지정하면 SDK 선택은 최대 `2.1.399`까지 찾지만 `2.1.400`은 `2.1.300`의 패치 버전으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-219">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="d3590-220">`2.1.100`부터 `2.1.201`까지의 .NET Core SDK 버전은 버전 번호 체계가 전환되는 중에 릴리스되었으며 `xyz` 표기법을 올바르게 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-220">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="d3590-221">*global.json* 파일에서 이 버전을 지정하면 지정된 버전이 대상 머신에 있는지 확인할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-221">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="d3590-222">빌드 경고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d3590-222">Troubleshoot build warnings</span></span>

* <span data-ttu-id="d3590-223">다음 경고는 .NET Core SDK의 시험판 버전을 사용하여 프로젝트를 컴파일했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-223">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="d3590-224">.NET Core SDK의 미리보기 버전으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-224">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="d3590-225">SDK 버전은 현재 프로젝트의 global.json 파일을 통해 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-225">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="d3590-226">자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=869452>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-226">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="d3590-227">.NET Core SDK 버전은 높은 품질의 기록과 약정을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-227">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="d3590-228">그러나 시험판 버전을 사용하지 않으려면 [allowPrerelease](#allowprerelease) 섹션의 .NET Core 3.0 SDK 이상 버전에서 사용할 수 있는 다양한 전략을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-228">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="d3590-229">.NET Core 3.0 이상 런타임 또는 SDK가 설치된 적이 없던 컴퓨터의 경우 *global.json* 파일을 만들고 사용할 정확한 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-229">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="d3590-230">다음 경고는 프로젝트가 .NET Core 2.1 SDK 이상 버전과 호환되지 않는 EF Core 1.0 또는 1.1을 대상으로 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-230">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="d3590-231">스타트업 프로젝트 '{startupProject}'는 '.NETCoreApp' 버전 '{targetFrameworkVersion}' 프레임워크를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-231">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="d3590-232">이 버전의 Entity Framework Core .NET 명령줄 도구는 버전 2.0 이상만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-232">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="d3590-233">이전 버전의 도구 사용에 대한 자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=871254>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-233">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="d3590-234">.NET Core 2.1 SDK(버전 2.1.300)부터 `dotnet ef` 명령이 SDK에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d3590-234">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="d3590-235">프로젝트를 컴파일하려면 머신에 .NET Core 2.0 SDK(버전 2.1.201) 또는 이전 버전을 설치하고 *global.json* 파일을 사용하여 원하는 SDK 버전을 정의하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-235">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="d3590-236">`dotnet ef` 명령에 대한 자세한 내용은 [EF Core .NET 명령줄 도구](/ef/core/miscellaneous/cli/dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3590-236">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="d3590-237">참조</span><span class="sxs-lookup"><span data-stu-id="d3590-237">See also</span></span>

- [<span data-ttu-id="d3590-238">프로젝트 SDK를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="d3590-238">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
