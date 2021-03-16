---
title: global.json 개요
description: .NET CLI 명령을 실행할 때 global.json 파일을 사용하여 .NET SDK 버전을 설정하는 방법을 알아봅니다.
ms.topic: how-to
ms.date: 05/01/2020
ms.custom: updateeachrelease
ms.openlocfilehash: cc471cf5b50cf91c38b46607ccf38bd4d087aa6a
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104143"
---
# <a name="globaljson-overview"></a><span data-ttu-id="61bbd-103">global.json 개요</span><span class="sxs-lookup"><span data-stu-id="61bbd-103">global.json overview</span></span>

<span data-ttu-id="61bbd-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="61bbd-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

<span data-ttu-id="61bbd-105">*global.json* 파일을 사용하면 .NET CLI 명령을 실행할 때 어떤 .NET SDK 버전을 사용할지 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-105">The *global.json* file allows you to define which .NET SDK version is used when you run .NET CLI commands.</span></span> <span data-ttu-id="61bbd-106">.NET SDK를 선택하는 것은 프로젝트가 대상으로 하는 런타임을 지정하는 것과는 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-106">Selecting the .NET SDK is independent from specifying the runtime your project targets.</span></span> <span data-ttu-id="61bbd-107">.NET SDK 버전은 사용된 .NET CLI 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-107">The .NET SDK version indicates which versions of the .NET CLI is used.</span></span>

<span data-ttu-id="61bbd-108">일반적으로 최신 버전의 SDK Tools를 사용하려고 하기 때문에 *global.json* 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-108">In general, you want to use the latest version of the SDK tools, so no *global.json* file is needed.</span></span> <span data-ttu-id="61bbd-109">일부 고급 시나리오에서는 SDK Tools의 버전을 컨트롤하는 것이 좋습니다. 이 문서에서는 해당 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-109">In some advanced scenarios, you might want to control the version of the SDK tools, and this article explains how to do this.</span></span>

<span data-ttu-id="61bbd-110">대신 런타임 지정에 대한 자세한 내용은 [대상 프레임워크](../../standard/frameworks.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-110">For more information about specifying the runtime instead, see [Target frameworks](../../standard/frameworks.md).</span></span>

<span data-ttu-id="61bbd-111">.NET SDK는 현재 작업 디렉터리(반드시 프로젝트 디렉터리와 동일하지는 않음) 또는 부모 디렉터리 중 하나에서 *global.json* 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-111">The .NET SDK looks for a *global.json* file in the current working directory (which isn't necessarily the same as the project directory) or one of its parent directories.</span></span>

## <a name="globaljson-schema"></a><span data-ttu-id="61bbd-112">global.json 스키마</span><span class="sxs-lookup"><span data-stu-id="61bbd-112">global.json schema</span></span>

### <a name="sdk"></a><span data-ttu-id="61bbd-113">sdk</span><span class="sxs-lookup"><span data-stu-id="61bbd-113">sdk</span></span>

<span data-ttu-id="61bbd-114">형식: `object`</span><span class="sxs-lookup"><span data-stu-id="61bbd-114">Type: `object`</span></span>

<span data-ttu-id="61bbd-115">선택할 .NET SDK에 대한 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-115">Specifies information about the .NET SDK to select.</span></span>

#### <a name="version"></a><span data-ttu-id="61bbd-116">버전</span><span class="sxs-lookup"><span data-stu-id="61bbd-116">version</span></span>

- <span data-ttu-id="61bbd-117">형식: `string`</span><span class="sxs-lookup"><span data-stu-id="61bbd-117">Type: `string`</span></span>

- <span data-ttu-id="61bbd-118">.NET Core 1.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-118">Available since: .NET Core 1.0 SDK.</span></span>

<span data-ttu-id="61bbd-119">사용할 .NET SDK의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-119">The version of the .NET SDK to use.</span></span>

<span data-ttu-id="61bbd-120">이 필드:</span><span class="sxs-lookup"><span data-stu-id="61bbd-120">This field:</span></span>

- <span data-ttu-id="61bbd-121">와일드카드를 지원하지 않습니다. 즉, 전체 버전 번호가 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-121">Doesn't have wildcard support, that is, the full version number has to be specified.</span></span>
- <span data-ttu-id="61bbd-122">버전 범위를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-122">Doesn't support version ranges.</span></span>

#### <a name="allowprerelease"></a><span data-ttu-id="61bbd-123">시험판 허용</span><span class="sxs-lookup"><span data-stu-id="61bbd-123">allowPrerelease</span></span>

- <span data-ttu-id="61bbd-124">형식: `boolean`</span><span class="sxs-lookup"><span data-stu-id="61bbd-124">Type: `boolean`</span></span>

- <span data-ttu-id="61bbd-125">.NET Core 3.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-125">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="61bbd-126">사용할 SDK 버전을 선택할 때 SDK 확인자가 시험판 버전을 고려해야 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-126">Indicates whether the SDK resolver should consider prerelease versions when selecting the SDK version to use.</span></span>

<span data-ttu-id="61bbd-127">이 값을 명시적으로 설정하지 않은 경우 Visual Studio에서 실행하고 있는지에 따라 기본값이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-127">If you don't set this value explicitly, the default value depends on whether you're running from Visual Studio:</span></span>

- <span data-ttu-id="61bbd-128">Visual Studio에서 실행하지 **않는** 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-128">If you're **not** in Visual Studio, the default value is `true`.</span></span>
- <span data-ttu-id="61bbd-129">Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-129">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="61bbd-130">즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 기본값은 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-130">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), the default value is `true`; otherwise, `false`.</span></span>

#### <a name="rollforward"></a><span data-ttu-id="61bbd-131">롤포워드</span><span class="sxs-lookup"><span data-stu-id="61bbd-131">rollForward</span></span>

- <span data-ttu-id="61bbd-132">형식: `string`</span><span class="sxs-lookup"><span data-stu-id="61bbd-132">Type: `string`</span></span>

- <span data-ttu-id="61bbd-133">.NET Core 3.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-133">Available since: .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="61bbd-134">SDK 버전을 선택할 때, 특정 SDK 버전이 누락된 경우 대체하거나 상위 버전을 사용하기 위한 지시문으로 사용할 롤포워드 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-134">The roll-forward policy to use when selecting an SDK version, either as a fallback when a specific SDK version is missing or as a directive to use a higher version.</span></span> <span data-ttu-id="61bbd-135">버전을 `latestMajor`로 설정하지 않는 한 `rollForward` 값을 사용하여 [버전](#version)을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-135">A [version](#version) must be specified with a `rollForward` value, unless you're setting it to `latestMajor`.</span></span>
<span data-ttu-id="61bbd-136">기본 롤포워드 동작은 [일치 규칙](#matching-rules)에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-136">The default roll forward behavior is determined by the [matching rules](#matching-rules).</span></span>

<span data-ttu-id="61bbd-137">사용 가능한 정책 및 해당 동작을 이해하려면 `x.y.znn` 형식의 SDK 버전에 대한 다음 정의를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-137">To understand the available policies and their behavior, consider the following definitions for an SDK version in the format `x.y.znn`:</span></span>

- <span data-ttu-id="61bbd-138">`x`는 주 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-138">`x` is the major version.</span></span>
- <span data-ttu-id="61bbd-139">`y`는 부 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-139">`y` is the minor version.</span></span>
- <span data-ttu-id="61bbd-140">`z`는 기능 밴드입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-140">`z` is the feature band.</span></span>
- <span data-ttu-id="61bbd-141">`nn`은 패치 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-141">`nn` is the patch version.</span></span>

<span data-ttu-id="61bbd-142">다음 표에서는 `rollForward` 키에 사용할 수 있는 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-142">The following table shows the possible values for the `rollForward` key:</span></span>

| <span data-ttu-id="61bbd-143">값</span><span class="sxs-lookup"><span data-stu-id="61bbd-143">Value</span></span>         | <span data-ttu-id="61bbd-144">동작</span><span class="sxs-lookup"><span data-stu-id="61bbd-144">Behavior</span></span> |
| ------------- | ---------- |
| `patch`       | <span data-ttu-id="61bbd-145">지정한 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-145">Uses the specified version.</span></span> <br> <span data-ttu-id="61bbd-146">버전이 없으면 최신 패치 수준으로 롤포워드하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-146">If not found, rolls forward to the latest patch level.</span></span> <br> <span data-ttu-id="61bbd-147">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-147">If not found, fails.</span></span> <br><br> <span data-ttu-id="61bbd-148">이 값은 이전 버전의 SDK에서 발생하는 레거시 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-148">This value is the legacy behavior from the earlier versions of the SDK.</span></span> |
| `feature`     | <span data-ttu-id="61bbd-149">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-149">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="61bbd-150">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-150">If not found, rolls forward to the next higher feature band within the same major/minor and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-151">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-151">If not found, fails.</span></span> |
| `minor`       | <span data-ttu-id="61bbd-152">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-152">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="61bbd-153">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-153">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-154">최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-154">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-155">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-155">If not found, fails.</span></span> |
| `major`       | <span data-ttu-id="61bbd-156">지정된 주 버전, 부 버전 및 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-156">Uses the latest patch level for the specified major, minor, and feature band.</span></span> <br> <span data-ttu-id="61bbd-157">최신 패치 수준을 찾을 수 없는 경우 동일한 주/부 버전에 있는 다음 상위 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-157">If not found, rolls forward to the next higher feature band within the same major/minor version and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-158">최신 패치 수준을 찾을 수 없는 경우 동일한 주 버전에 있는 다음 상위 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드에 대한 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-158">If not found, rolls forward to the next higher minor and feature band within the same major and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-159">최신 패치 수준을 찾을 수 없는 경우 다음 상위 주 버전, 부 버전 및 기능 밴드로 롤포워드하고 해당 기능 밴드의 최신 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-159">If not found, rolls forward to the next higher major, minor, and feature band and uses the latest patch level for that feature band.</span></span> <br> <span data-ttu-id="61bbd-160">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-160">If not found, fails.</span></span> |
| `latestPatch` | <span data-ttu-id="61bbd-161">요청된 주 버전, 부 버전 및 기능 밴드와 패치 수준이 일치하고 지정된 값과 같거나 큰 최신 설치된 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-161">Uses the latest installed patch level that matches the requested major, minor, and feature band with a patch level and that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="61bbd-162">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-162">If not found, fails.</span></span> |
| `latestFeature` | <span data-ttu-id="61bbd-163">요청된 주 버전과 부 버전이 지정된 값보다 크거나 같은 기능 밴드 및 패치 수준과 일치하는 설치된 최상위 기능 밴드와 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-163">Uses the highest installed feature band and patch level that matches the requested major and minor with a feature band and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="61bbd-164">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-164">If not found, fails.</span></span> |
| `latestMinor` | <span data-ttu-id="61bbd-165">요청된 주 버전이 지정된 값보다 크거나 같은 부 버전, 기능 밴드, 패치 수준과 일치하는 설치된 최상위 부 버전, 기능 밴드, 패치 수준을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-165">Uses the highest installed minor, feature band, and patch level that matches the requested major with a minor, feature band, and patch level that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="61bbd-166">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-166">If not found, fails.</span></span> |
| `latestMajor` | <span data-ttu-id="61bbd-167">지정한 값보다 크거나 같은 버전과 함께 설치된 최상위 .NET SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-167">Uses the highest installed .NET SDK with a version that is greater or equal than the specified value.</span></span> <br> <span data-ttu-id="61bbd-168">찾을 수 없으면 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-168">If not found, fail.</span></span> |
| `disable`     | <span data-ttu-id="61bbd-169">롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-169">Doesn't roll forward.</span></span> <span data-ttu-id="61bbd-170">정확하게 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-170">Exact match required.</span></span> |

### <a name="msbuild-sdks"></a><span data-ttu-id="61bbd-171">msbuild-sdk</span><span class="sxs-lookup"><span data-stu-id="61bbd-171">msbuild-sdks</span></span>

<span data-ttu-id="61bbd-172">형식: `object`</span><span class="sxs-lookup"><span data-stu-id="61bbd-172">Type: `object`</span></span>

<span data-ttu-id="61bbd-173">개별 프로젝트가 아닌 한 곳에서 프로젝트 SDK 버전을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-173">Lets you control the project SDK version in one place rather than in each individual project.</span></span> <span data-ttu-id="61bbd-174">자세한 내용은 [프로젝트 SDK를 확인하는 방법](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-174">For more information, see [How project SDKs are resolved](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved).</span></span>

## <a name="examples"></a><span data-ttu-id="61bbd-175">예</span><span class="sxs-lookup"><span data-stu-id="61bbd-175">Examples</span></span>

<span data-ttu-id="61bbd-176">다음 예제에서는 시험판 버전을 사용하지 않는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-176">The following example shows how to not use prerelease versions:</span></span>

```json
{
  "sdk": {
    "allowPrerelease": false
  }
}
```

<span data-ttu-id="61bbd-177">다음 예제에서는 지정된 버전과 같거나 높은 최상위 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-177">The following example shows how to use the highest version installed that is greater or equal than the specified version.</span></span> <span data-ttu-id="61bbd-178">표시된 JSON은 2.2.200 이전 SDK 버전을 허용하지 않으며 2.2.200 이상 버전(3.0.xxx 및 3.1.xxx 포함)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-178">The JSON shown disallows any SDK version earlier than 2.2.200 and allows 2.2.200 or any later version, including 3.0.xxx and 3.1.xxx.</span></span>

```json
{
  "sdk": {
    "version": "2.2.200",
    "rollForward": "latestMajor"
  }
}
```

<span data-ttu-id="61bbd-179">다음 예제에서는 정확하게 지정된 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-179">The following example shows how to use the exact specified version:</span></span>

```json
{
  "sdk": {
    "version": "3.1.100",
    "rollForward": "disable"
  }
}
```

<span data-ttu-id="61bbd-180">다음 예제에서는 설치된 특정 주 버전과 부 버전의 최신 기능 밴드 및 패치 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-180">The following example shows how to use the latest feature band and patch version installed of a specific major and minor version.</span></span> <span data-ttu-id="61bbd-181">표시된 JSON은 3.1.102 이전 SDK 버전을 허용하지 않으며 3.1.102 이상인 3.1.xxx 버전(예: 3.1.103 또는 3.1.200)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-181">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.xxx version, such as 3.1.103 or 3.1.200.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestFeature"
  }
}
```

<span data-ttu-id="61bbd-182">다음 예제에서는 특정 버전으로 설치된 최상위 패치 버전을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-182">The following example shows how to use the highest patch version installed of a specific version.</span></span> <span data-ttu-id="61bbd-183">표시된 JSON은 3.1.102 이전 SDK 버전을 허용하지 않으며 3.1.102 이상인 3.1.1xx 버전(예: 3.1.103 또는 3.1.199)을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-183">The JSON shown disallows any SDK version earlier than 3.1.102 and allows 3.1.102 or any later 3.1.1xx version, such as 3.1.103 or 3.1.199.</span></span>

```json
{
  "sdk": {
    "version": "3.1.102",
    "rollForward": "latestPatch"
  }
}
```

## <a name="globaljson-and-the-net-cli"></a><span data-ttu-id="61bbd-184">global.json 및 .NET CLI</span><span class="sxs-lookup"><span data-stu-id="61bbd-184">global.json and the .NET CLI</span></span>

<span data-ttu-id="61bbd-185">*global json* 파일에 버전을 설정하기 위해서는 컴퓨터에 설치된 SDK 버전을 알고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-185">It's helpful to know which SDK versions are installed on your machine to set one in the *global.json* file.</span></span> <span data-ttu-id="61bbd-186">이 작업을 수행하는 방법에 대한 자세한 내용은 [.NET이 이미 설치되어 있는지 확인하는 방법](../install/how-to-detect-installed-versions.md#check-sdk-versions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-186">For more information on how to do that, see [How to check that .NET is already installed](../install/how-to-detect-installed-versions.md#check-sdk-versions).</span></span>

<span data-ttu-id="61bbd-187">머신에 추가 .NET SDK 버전을 설치하려면 [.NET 다운로드](https://dotnet.microsoft.com/download/dotnet) 페이지를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-187">To install additional .NET SDK versions on your machine, visit the [Download .NET](https://dotnet.microsoft.com/download/dotnet) page.</span></span>

<span data-ttu-id="61bbd-188">다음 예제와 비슷한 [dotnet new](dotnet-new.md) 명령을 실행하여 현재 디렉터리에서 *global.json* 파일을 새로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-188">You can create a new the *global.json* file in the current directory by executing the [dotnet new](dotnet-new.md) command, similar to the following example:</span></span>

```dotnetcli
dotnet new globaljson --sdk-version 3.0.100
```

## <a name="matching-rules"></a><span data-ttu-id="61bbd-189">일치 규칙</span><span class="sxs-lookup"><span data-stu-id="61bbd-189">Matching rules</span></span>

> [!NOTE]
> <span data-ttu-id="61bbd-190">일치 규칙에는 설치된 모든 .NET 설치 런타임에서 공통으로 사용되는 `dotnet.exe` 진입점이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-190">The matching rules are governed by the `dotnet.exe` entry point, which is common across all installed .NET installed runtimes.</span></span> <span data-ttu-id="61bbd-191">여러 런타임이 함께 설치되어 있거나 *global.json* 파일을 사용 중인 경우 설치된 최신 버전의 .NET 런타임에 대한 일치 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-191">The matching rules for the latest installed version of the .NET Runtime are used when you have multiple runtimes installed side-by-side or if or you're using a *global.json* file.</span></span>

## <a name="net-core-3x"></a>[<span data-ttu-id="61bbd-192">.NET Core 3.x</span><span class="sxs-lookup"><span data-stu-id="61bbd-192">.NET Core 3.x</span></span>](#tab/netcore3x)

<span data-ttu-id="61bbd-193">.NET Core 3.0부터는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-193">Starting with .NET Core 3.0, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="61bbd-194">*global. json* 파일을 찾을 수 없거나 *global.json* 이 SDK 버전 또는 `allowPrerelease` 값을 지정하지 않은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`을 `latestMajor`로 설정하는 것과 같음).</span><span class="sxs-lookup"><span data-stu-id="61bbd-194">If no *global.json* file is found, or *global.json* doesn't specify an SDK version nor an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="61bbd-195">시험판 SDK 버전을 고려하는지는 `dotnet`을 호출하는 방법에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-195">Whether prerelease SDK versions are considered depends on how `dotnet` is being invoked.</span></span>
  - <span data-ttu-id="61bbd-196">Visual Studio에서 실행하지 **않는** 경우 시험판 버전이 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-196">If you're **not** in Visual Studio, prerelease versions are considered.</span></span>
  - <span data-ttu-id="61bbd-197">Visual Studio에서 실행하는 경우 요청된 시험판 상태를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-197">If you are in Visual Studio, it uses the prerelease status requested.</span></span> <span data-ttu-id="61bbd-198">즉, Visual Studio의 미리 보기 버전을 사용하거나 **.NET Core SDK의 미리 보기 사용** 옵션(**도구** > **옵션** > **환경** > **미리 보기 기능**)을 설정하는 경우 시험판 버전이 고려됩니다. 그렇지 않으면 릴리스 버전만 고려됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-198">That is, if you're using a Preview version of Visual Studio or you set the **Use previews of the .NET Core SDK** option (under **Tools** > **Options** > **Environment** > **Preview Features**), prerelease versions are considered; otherwise, only release versions are considered.</span></span>
- <span data-ttu-id="61bbd-199">SDK 버전을 지정하지 않고 `allowPrerelease` 값을 지정하는 *global.json* 파일을 찾은 경우 설치된 최상위 SDK 버전이 사용됩니다(`rollForward`를 `latestMajor`로 설정하는 것과 같음).</span><span class="sxs-lookup"><span data-stu-id="61bbd-199">If a *global.json* file is found that doesn't specify an SDK version but it specifies an `allowPrerelease` value, the highest installed SDK version is used (equivalent to setting `rollForward` to `latestMajor`).</span></span> <span data-ttu-id="61bbd-200">최신 SDK 버전을 릴리스 또는 시험판이 될 수 있는지는 `allowPrerelease` 값에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-200">Whether the latest SDK version can be release or prerelease depends on the value of `allowPrerelease`.</span></span> <span data-ttu-id="61bbd-201">`true`는 시험판 버전이 고려됨을 나타냅니다. `false`는 릴리스 버전만 고려됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-201">`true` indicates prerelease versions are considered; `false` indicates that only release versions are considered.</span></span>
- <span data-ttu-id="61bbd-202">*global.json* 파일을 찾아 SDK 버전을 지정하는 경우 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-202">If a *global.json* file is found and it specifies an SDK version:</span></span>

  - <span data-ttu-id="61bbd-203">`rollForward` 값이 설정되지 않은 경우 `latestPatch`를 기본 `rollForward` 정책으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-203">If no `rollForward` value is set, it uses `latestPatch` as the default `rollForward` policy.</span></span> <span data-ttu-id="61bbd-204">그렇지 않으면 [롤포워드](#rollforward) 섹션에서 각 값과 해당 동작을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-204">Otherwise, check each value and their behavior in the [rollForward](#rollforward) section.</span></span>
  - <span data-ttu-id="61bbd-205">시험판 버전을 고려하는지와 `allowPrerelease`가 설정되지 않은 경우의 기본 동작은 [allowPrerelease](#allowprerelease) 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-205">Whether prerelease versions are considered and what's the default behavior when `allowPrerelease` isn't set is described in the [allowPrerelease](#allowprerelease) section.</span></span>

## <a name="net-core-2x"></a>[<span data-ttu-id="61bbd-206">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="61bbd-206">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="61bbd-207">.NET Core 2.x SDK에서는 어떤 SDK 버전을 사용할지 결정할 때 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-207">In .NET Core 2.x SDK, the following rules apply when determining which version of the SDK to use:</span></span>

- <span data-ttu-id="61bbd-208">*global.json* 파일이 없거나 *global.json* 이 SDK 버전을 지정하지 않으면 최신 설치된 SDK 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-208">If no *global.json* file is found or *global.json* doesn't specify an SDK version, the latest installed SDK version is used.</span></span> <span data-ttu-id="61bbd-209">최신 SDK 버전은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-209">Latest SDK version can be either release or prerelease - the highest version number wins.</span></span>
- <span data-ttu-id="61bbd-210">*global.json* 이 SDK 버전을 지정하는 경우</span><span class="sxs-lookup"><span data-stu-id="61bbd-210">If *global.json* does specify an SDK version:</span></span>
  - <span data-ttu-id="61bbd-211">지정된 SDK 버전이 머신에서 발견되면 정확한 버전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-211">If the specified SDK version is found on the machine, that exact version is used.</span></span>
  - <span data-ttu-id="61bbd-212">지정된 SDK 버전이 시스템에서 발견되지 않으면 해당 버전의 최신 **패치 버전** 이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-212">If the specified SDK version can't be found on the machine, the latest installed SDK **patch version** of that version is used.</span></span> <span data-ttu-id="61bbd-213">설치된 최신 SDK **패치 버전** 은 릴리스나 시험판일 수 있으며, 이 중에 최상위 버전 번호가 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-213">Latest installed SDK **patch version** can be either release or prerelease - the highest version number wins.</span></span> <span data-ttu-id="61bbd-214">.NET Core 2.1 이상에서는 지정된 **패치 버전** 보다 낮은 **패치 버전** 은 SDK 선택에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-214">In .NET Core 2.1 and higher, the **patch versions** lower than the **patch version** specified are ignored in the SDK selection.</span></span>
  - <span data-ttu-id="61bbd-215">지정된 SDK 버전과 적절한 SDK **패치 버전** 을 찾을 수 없으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-215">If the specified SDK version and an appropriate SDK **patch version** can't be found, an error is thrown.</span></span>

<span data-ttu-id="61bbd-216">SDK 버전은 다음과 같은 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-216">The SDK version is composed of the following parts:</span></span>

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

<span data-ttu-id="61bbd-217">.NET Core SDK의 **기능 릴리스** 는 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 첫 번째 자리(`x`)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-217">The **feature release** of the .NET Core SDK is represented by the first digit (`x`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="61bbd-218">일반적으로 .NET Core SDK는 .NET Core보다 릴리스 주기가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-218">In general, the .NET Core SDK has a faster release cycle than .NET Core.</span></span>

<span data-ttu-id="61bbd-219">**패치 버전** 은 SDK 버전 2.1.100 이상의 경우 번호의 마지막 부분(`xyz`)의 마지막 두 자리(`yz`)로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-219">The **patch version** is defined by the last two digits (`yz`) in the last portion of the number (`xyz`) for SDK versions 2.1.100 and higher.</span></span> <span data-ttu-id="61bbd-220">예를 들어, SDK 버전으로 `2.1.300`을 지정하면 SDK 선택은 최대 `2.1.399`까지 찾지만 `2.1.400`은 `2.1.300`의 패치 버전으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-220">For example, if you specify `2.1.300` as the SDK version, SDK selection finds up to `2.1.399` but `2.1.400` isn't considered a patch version for `2.1.300`.</span></span>

<span data-ttu-id="61bbd-221">`2.1.100`부터 `2.1.201`까지의 .NET Core SDK 버전은 버전 번호 체계가 전환되는 중에 릴리스되었으며 `xyz` 표기법을 올바르게 처리하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-221">.NET Core SDK versions `2.1.100` through `2.1.201` were released during the transition between version number schemes and don't correctly handle the `xyz` notation.</span></span> <span data-ttu-id="61bbd-222">*global.json* 파일에서 이 버전을 지정하면 지정된 버전이 대상 머신에 있는지 확인할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-222">We highly recommend if you specify these versions in the *global.json* file, that you ensure the specified versions are on the target machines.</span></span>

---

## <a name="troubleshoot-build-warnings"></a><span data-ttu-id="61bbd-223">빌드 경고 문제 해결</span><span class="sxs-lookup"><span data-stu-id="61bbd-223">Troubleshoot build warnings</span></span>

* <span data-ttu-id="61bbd-224">다음 경고는 .NET Core SDK의 시험판 버전을 사용하여 프로젝트를 컴파일했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-224">The following warning indicates that your project was compiled using a prerelease version of the .NET Core SDK:</span></span>

  > <span data-ttu-id="61bbd-225">.NET Core SDK의 미리보기 버전으로 작업하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-225">You are working with a preview version of the .NET Core SDK.</span></span> <span data-ttu-id="61bbd-226">SDK 버전은 현재 프로젝트의 global.json 파일을 통해 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-226">You can define the SDK version via a global.json file in the current project.</span></span> <span data-ttu-id="61bbd-227">자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=869452>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-227">More at <https://go.microsoft.com/fwlink/?linkid=869452>.</span></span>

  <span data-ttu-id="61bbd-228">.NET Core SDK 버전은 높은 품질의 기록과 약정을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-228">.NET Core SDK versions have a history and commitment of being high quality.</span></span> <span data-ttu-id="61bbd-229">그러나 시험판 버전을 사용하지 않으려면 [allowPrerelease](#allowprerelease) 섹션의 .NET Core 3.0 SDK 이상 버전에서 사용할 수 있는 다양한 전략을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-229">However, if you don't want to use a prerelease version, check the different strategies you can use with the .NET Core 3.0 SDK or a later version in the [allowPrerelease](#allowprerelease) section.</span></span> <span data-ttu-id="61bbd-230">.NET Core 3.0 이상 런타임 또는 SDK가 설치된 적이 없던 컴퓨터의 경우 *global.json* 파일을 만들고 사용할 정확한 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-230">For machines that have never had a .NET Core 3.0 or higher Runtime or SDK installed, you need to create a *global.json* file and specify the exact version you want to use.</span></span>

* <span data-ttu-id="61bbd-231">다음 경고는 프로젝트가 .NET Core 2.1 SDK 이상 버전과 호환되지 않는 EF Core 1.0 또는 1.1을 대상으로 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-231">The following warning indicates that your project targets EF Core 1.0 or 1.1, which isn't compatible with .NET Core 2.1 SDK and later versions:</span></span>

  > <span data-ttu-id="61bbd-232">스타트업 프로젝트 '{startupProject}'는 '.NETCoreApp' 버전 '{targetFrameworkVersion}' 프레임워크를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-232">Startup project '{startupProject}' targets framework '.NETCoreApp' version '{targetFrameworkVersion}'.</span></span> <span data-ttu-id="61bbd-233">이 버전의 Entity Framework Core .NET 명령줄 도구는 버전 2.0 이상만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-233">This version of the Entity Framework Core .NET Command-line Tools only supports version 2.0 or higher.</span></span> <span data-ttu-id="61bbd-234">이전 버전의 도구 사용에 대한 자세한 내용은 <https://go.microsoft.com/fwlink/?linkid=871254>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-234">For information on using older versions of the tools, see <https://go.microsoft.com/fwlink/?linkid=871254>.</span></span>

  <span data-ttu-id="61bbd-235">.NET Core 2.1 SDK(버전 2.1.300)부터 `dotnet ef` 명령이 SDK에 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61bbd-235">Starting with .NET Core 2.1 SDK (version 2.1.300), the `dotnet ef` command comes included in the SDK.</span></span> <span data-ttu-id="61bbd-236">프로젝트를 컴파일하려면 머신에 .NET Core 2.0 SDK(버전 2.1.201) 또는 이전 버전을 설치하고 *global.json* 파일을 사용하여 원하는 SDK 버전을 정의하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-236">To compile your project, install .NET Core 2.0 SDK (version 2.1.201) or earlier on your machine and define the desired SDK version using the *global.json* file.</span></span> <span data-ttu-id="61bbd-237">`dotnet ef` 명령에 대한 자세한 내용은 [EF Core .NET 명령줄 도구](/ef/core/miscellaneous/cli/dotnet)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61bbd-237">For more information about the `dotnet ef` command, see [EF Core .NET Command-line Tools](/ef/core/miscellaneous/cli/dotnet).</span></span>

## <a name="see-also"></a><span data-ttu-id="61bbd-238">참조</span><span class="sxs-lookup"><span data-stu-id="61bbd-238">See also</span></span>

- [<span data-ttu-id="61bbd-239">프로젝트 SDK를 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="61bbd-239">How project SDKs are resolved</span></span>](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
