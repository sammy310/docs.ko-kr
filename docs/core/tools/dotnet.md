---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI의 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134071"
---
# <a name="dotnet-command"></a><span data-ttu-id="14c36-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="14c36-103">dotnet command</span></span>

<span data-ttu-id="14c36-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="14c36-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="14c36-105">속성</span><span class="sxs-lookup"><span data-stu-id="14c36-105">Name</span></span>

<span data-ttu-id="14c36-106">`dotnet` - .NET Core CLI에 대한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="14c36-107">개요</span><span class="sxs-lookup"><span data-stu-id="14c36-107">Synopsis</span></span>

<span data-ttu-id="14c36-108">사용 가능한 명령 및 환경에 대한 정보를 얻으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

<span data-ttu-id="14c36-109">명령을 실행하려면(SDK를 설치해야 함) 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

<span data-ttu-id="14c36-110">애플리케이션을 실행하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="14c36-111">`--roll-forward`는 .NET Core 3.x 이후로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="14c36-112">.NET Core 2.x의 경우 `--roll-forward-on-no-candidate-fx`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="14c36-113">Description</span><span class="sxs-lookup"><span data-stu-id="14c36-113">Description</span></span>

<span data-ttu-id="14c36-114">`dotnet` 명령에는 두 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="14c36-115">.NET Core 프로젝트 작업을 위한 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="14c36-116">예를 들어 [`dotnet build`](dotnet-build.md)는 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="14c36-117">각 명령은 자체 옵션과 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="14c36-118">모든 명령은 명령을 사용하는 방법에 대해 간략한 설명서를 출력하는 `--help` 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="14c36-119">.NET Core 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="14c36-120">애플리케이션을 실행할 애플리케이션 `.dll` 파일의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-120">You specify the path to an application `.dll` file to run the application.</span></span> <span data-ttu-id="14c36-121">예를 들어 `dotnet myapp.dll`은 `myapp` 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-121">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="14c36-122">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-122">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="14c36-123">옵션</span><span class="sxs-lookup"><span data-stu-id="14c36-123">Options</span></span>

<span data-ttu-id="14c36-124">명령 실행, 애플리케이션 실행을 위해 `dotnet` 자체에 사용할 수 있는 다양한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-124">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="14c36-125">dotnet 자체에 대한 옵션</span><span class="sxs-lookup"><span data-stu-id="14c36-125">Options for dotnet by itself</span></span>

<span data-ttu-id="14c36-126">`dotnet` 자체에 대한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-126">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="14c36-127">`dotnet --info`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-127">For example, `dotnet --info`.</span></span> <span data-ttu-id="14c36-128">환경에 대한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-128">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="14c36-129">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-129">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="14c36-130">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-130">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="14c36-131">설치된 .NET Core 런타임의 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-131">Prints out a list of the installed .NET Core runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="14c36-132">설치된 .NET Core SDK의 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-132">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="14c36-133">사용 가능한 명령 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-133">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="14c36-134">명령을 실행하기 위한 SDK 옵션</span><span class="sxs-lookup"><span data-stu-id="14c36-134">SDK options for running a command</span></span>

<span data-ttu-id="14c36-135">명령과 함께 사용하는 `dotnet`의 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-135">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="14c36-136">`dotnet build --help`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-136">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="14c36-137">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-137">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="14c36-138">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-138">Sets the verbosity level of the command.</span></span> <span data-ttu-id="14c36-139">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="14c36-140">모든 명령에서 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-140">Not supported in every command.</span></span> <span data-ttu-id="14c36-141">이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-141">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="14c36-142">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-142">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="14c36-143">각 명령은 해당 명령과 관련된 옵션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-143">Each command defines options specific to that command.</span></span> <span data-ttu-id="14c36-144">사용 가능한 옵션 목록은 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-144">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="14c36-145">런타임 옵션</span><span class="sxs-lookup"><span data-stu-id="14c36-145">Runtime options</span></span>

<span data-ttu-id="14c36-146">`dotnet`이 애플리케이션을 실행할 때 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-146">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="14c36-147">`dotnet myapp.dll --fx-version 3.1.1`)을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-147">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="14c36-148">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-148">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="14c36-149">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-149">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="14c36-150">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-150">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="14c36-151">자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-151">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="14c36-152">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-152">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="14c36-153">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-153">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="14c36-154">*runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-154">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="14c36-155">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-155">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="14c36-156">**`--roll-forward-on-no-candidate-fx <N>`** **.NET Core 2.x SDK에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="14c36-156">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="14c36-157">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-157">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="14c36-158">`N`는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-158">`N` can be:</span></span>

  - <span data-ttu-id="14c36-159">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-159">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="14c36-160">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-160">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="14c36-161">기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-161">This is the default behavior.</span></span>
  - <span data-ttu-id="14c36-162">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-162">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="14c36-163">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-163">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="14c36-164">**`--roll-forward <SETTING>`** **.NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="14c36-164">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="14c36-165">앱에 롤포워드가 적용되는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-165">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="14c36-166">`SETTING`은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-166">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="14c36-167">지정하지 않으면 `Minor`이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-167">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="14c36-168">`LatestPatch` - 가장 높은 패치 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-168">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="14c36-169">부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-169">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="14c36-170">`Minor` - 요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-170">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="14c36-171">요청된 부 버전이 있다면 LatestPatch 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-171">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="14c36-172">`Major` - 요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-172">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="14c36-173">요청된 주 버전이 있다면 Minor 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-173">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="14c36-174">`LatestMinor` - 요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-174">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="14c36-175">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-175">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="14c36-176">`LatestMajor` - 요청된 주 버전이 있는 경우에도 가장 높은 주 버전, 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-176">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="14c36-177">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="14c36-178">`Disable` - 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-178">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="14c36-179">지정된 버전에만 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-179">Only bind to specified version.</span></span> <span data-ttu-id="14c36-180">이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-180">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="14c36-181">이 값은 테스트용으로만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-181">This value is only recommended for testing.</span></span>

<span data-ttu-id="14c36-182">`Disable`을 제외하고, 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-182">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="14c36-183">롤포워드 동작은 프로젝트 파일 속성, 런타임 구성 파일 속성 및 환경 변수에서도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-183">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="14c36-184">자세한 내용은 [주 버전 런타임 롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-184">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="14c36-185">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="14c36-185">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="14c36-186">일반</span><span class="sxs-lookup"><span data-stu-id="14c36-186">General</span></span>

| <span data-ttu-id="14c36-187">명령</span><span class="sxs-lookup"><span data-stu-id="14c36-187">Command</span></span>                                       | <span data-ttu-id="14c36-188">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-188">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="14c36-189">dotnet build</span><span class="sxs-lookup"><span data-stu-id="14c36-189">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="14c36-190">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-190">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="14c36-191">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="14c36-191">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="14c36-192">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-192">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="14c36-193">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="14c36-193">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="14c36-194">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-194">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="14c36-195">dotnet help</span><span class="sxs-lookup"><span data-stu-id="14c36-195">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="14c36-196">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-196">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="14c36-197">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="14c36-197">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="14c36-198">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-198">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="14c36-199">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="14c36-199">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="14c36-200">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-200">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="14c36-201">dotnet new</span><span class="sxs-lookup"><span data-stu-id="14c36-201">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="14c36-202">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-202">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="14c36-203">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="14c36-203">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="14c36-204">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-204">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="14c36-205">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="14c36-205">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="14c36-206">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-206">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="14c36-207">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="14c36-207">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="14c36-208">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-208">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="14c36-209">dotnet run</span><span class="sxs-lookup"><span data-stu-id="14c36-209">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="14c36-210">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-210">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="14c36-211">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="14c36-211">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="14c36-212">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-212">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="14c36-213">dotnet store</span><span class="sxs-lookup"><span data-stu-id="14c36-213">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="14c36-214">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-214">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="14c36-215">dotnet test</span><span class="sxs-lookup"><span data-stu-id="14c36-215">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="14c36-216">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-216">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="14c36-217">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="14c36-217">Project references</span></span>

<span data-ttu-id="14c36-218">명령</span><span class="sxs-lookup"><span data-stu-id="14c36-218">Command</span></span> | <span data-ttu-id="14c36-219">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-219">Function</span></span>
--- | ---
[<span data-ttu-id="14c36-220">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="14c36-220">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="14c36-221">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-221">Adds a project reference.</span></span>
[<span data-ttu-id="14c36-222">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="14c36-222">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="14c36-223">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-223">Lists project references.</span></span>
[<span data-ttu-id="14c36-224">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="14c36-224">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="14c36-225">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-225">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="14c36-226">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="14c36-226">NuGet packages</span></span>

<span data-ttu-id="14c36-227">명령</span><span class="sxs-lookup"><span data-stu-id="14c36-227">Command</span></span> | <span data-ttu-id="14c36-228">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-228">Function</span></span>
--- | ---
[<span data-ttu-id="14c36-229">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="14c36-229">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="14c36-230">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-230">Adds a NuGet package.</span></span>
[<span data-ttu-id="14c36-231">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="14c36-231">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="14c36-232">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-232">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="14c36-233">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="14c36-233">NuGet commands</span></span>

<span data-ttu-id="14c36-234">명령</span><span class="sxs-lookup"><span data-stu-id="14c36-234">Command</span></span> | <span data-ttu-id="14c36-235">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-235">Function</span></span>
--- | ---
[<span data-ttu-id="14c36-236">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="14c36-236">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="14c36-237">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-237">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="14c36-238">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="14c36-238">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="14c36-239">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-239">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="14c36-240">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="14c36-240">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="14c36-241">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-241">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="14c36-242">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="14c36-242">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="14c36-243">NuGet 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-243">Adds a NuGet source.</span></span>
[<span data-ttu-id="14c36-244">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="14c36-244">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="14c36-245">NuGet 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-245">Disables a NuGet source.</span></span>
[<span data-ttu-id="14c36-246">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="14c36-246">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="14c36-247">NuGet 소스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-247">Enables a NuGet source.</span></span>
[<span data-ttu-id="14c36-248">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="14c36-248">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="14c36-249">구성된 NuGet 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-249">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="14c36-250">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="14c36-250">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="14c36-251">NuGet 소스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-251">Removes a NuGet source.</span></span>
[<span data-ttu-id="14c36-252">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="14c36-252">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="14c36-253">NuGet 소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-253">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="14c36-254">전역, 도구 경로 및 로컬 도구 명령</span><span class="sxs-lookup"><span data-stu-id="14c36-254">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="14c36-255">도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-255">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="14c36-256">도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-256">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="14c36-257">도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-257">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="14c36-258">자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-258">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="14c36-259">전역 및 도구 경로 도구는 .NET Core SDK 2.1부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-259">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="14c36-260">로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-260">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="14c36-261">명령</span><span class="sxs-lookup"><span data-stu-id="14c36-261">Command</span></span> | <span data-ttu-id="14c36-262">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-262">Function</span></span>
--- | ---
[<span data-ttu-id="14c36-263">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="14c36-263">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="14c36-264">컴퓨터에 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-264">Installs a tool on your machine.</span></span>
[<span data-ttu-id="14c36-265">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="14c36-265">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="14c36-266">컴퓨터에 현재 설치되어 있는 모든 전역, 도구 경로 또는 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-266">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="14c36-267">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="14c36-267">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="14c36-268">컴퓨터에서 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-268">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="14c36-269">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="14c36-269">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="14c36-270">컴퓨터에 설치된 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-270">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="14c36-271">추가 도구</span><span class="sxs-lookup"><span data-stu-id="14c36-271">Additional tools</span></span>

<span data-ttu-id="14c36-272">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-272">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="14c36-273">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-273">These tools are listed in the following table:</span></span>

| <span data-ttu-id="14c36-274">도구</span><span class="sxs-lookup"><span data-stu-id="14c36-274">Tool</span></span>                                              | <span data-ttu-id="14c36-275">함수</span><span class="sxs-lookup"><span data-stu-id="14c36-275">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="14c36-276">dev-certs</span><span class="sxs-lookup"><span data-stu-id="14c36-276">dev-certs</span></span>                                         | <span data-ttu-id="14c36-277">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-277">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="14c36-278">ef</span><span class="sxs-lookup"><span data-stu-id="14c36-278">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="14c36-279">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-279">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="14c36-280">sql-cache</span><span class="sxs-lookup"><span data-stu-id="14c36-280">sql-cache</span></span>                                         | <span data-ttu-id="14c36-281">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-281">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="14c36-282">user-secrets</span><span class="sxs-lookup"><span data-stu-id="14c36-282">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="14c36-283">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-283">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="14c36-284">watch</span><span class="sxs-lookup"><span data-stu-id="14c36-284">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="14c36-285">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-285">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="14c36-286">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-286">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="14c36-287">예</span><span class="sxs-lookup"><span data-stu-id="14c36-287">Examples</span></span>

<span data-ttu-id="14c36-288">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-288">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="14c36-289">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-289">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="14c36-290">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-290">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="14c36-291">환경 변수</span><span class="sxs-lookup"><span data-stu-id="14c36-291">Environment variables</span></span>

- <span data-ttu-id="14c36-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="14c36-292">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="14c36-293">기본 위치에 설치되어 있지 않은 경우 .NET Core 런타임의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-293">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="14c36-294">Windows에서 기본 위치는 `C:\Program Files\dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-294">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="14c36-295">Linux 및 macOS에서 기본 위치는 `/usr/share/dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-295">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="14c36-296">이 환경 변수는 생성된 실행 파일(apphost)을 통해 앱을 실행할 때만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-296">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="14c36-297">64비트 OS에서 32비트 실행 파일을 실행할 때는 대신 `DOTNET_ROOT(x86)`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-297">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="14c36-298">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-298">The global packages folder.</span></span> <span data-ttu-id="14c36-299">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-299">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="14c36-300">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-300">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="14c36-301">처음 실행할 때 .NET Core 시작 및 원격 분석 메시지를 표시할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-301">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="14c36-302">이러한 메시지를 음소거하려면 `true`로 설정하고(`true`, `1` 또는 `yes` 값 사용) 허용하려면 `false`로 설정합니다(`false`, `0` 또는 `no` 값 사용).</span><span class="sxs-lookup"><span data-stu-id="14c36-302">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="14c36-303">설정되지 않은 경우 기본값은 `false`이고 처음 실행될 때 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-303">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="14c36-304">이 플래그는 원격 분석에는 영향을 주지 않습니다(원격 분석 보내기를 옵트아웃하기 위한 `DOTNET_CLI_TELEMETRY_OPTOUT` 참조).</span><span class="sxs-lookup"><span data-stu-id="14c36-304">Note that this flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="14c36-305">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-305">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="14c36-306">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="14c36-306">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="14c36-307">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="14c36-307">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="14c36-308">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-308">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="14c36-309">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-309">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="14c36-310">설정하지 않은 경우 기본값은 1(논리적 `true`)입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-310">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="14c36-311">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 사용하려면 0(논리적 `false`)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-311">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="14c36-312">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-312">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="14c36-313">`DOTNET_ROLL_FORWARD` **.NET Core 3.x SDK부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="14c36-313">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="14c36-314">롤포워드 동작을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-314">Determines roll forward behavior.</span></span> <span data-ttu-id="14c36-315">자세한 내용은 이 문서 앞부분에서 `--roll-forward` 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-315">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="14c36-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **.NET Core 2.x SDK에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="14c36-316">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="14c36-317">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-317">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="14c36-318">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-318">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="14c36-319">`en-us`와 같은 로캘 값을 사용하여 CLI UI의 언어를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-319">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="14c36-320">지원되는 값은 Visual Studio의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-320">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="14c36-321">자세한 내용은 [Visual Studio 설치 설명서](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)에서 설치 프로그램 언어 변경에 대한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14c36-321">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="14c36-322">.NET 리소스 관리자 규칙이 적용되므로, 정확한 일치를 선택할 필요가 없습니다. `CultureInfo` 트리에서 하위 항목을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-322">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="14c36-323">예를 들어 `fr-CA`로 설정하면 CLI에서 `fr` 번역을 찾아 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-323">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="14c36-324">지원되지 않는 언어로 설정하면 CLI는 영어로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-324">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="14c36-325">GUI 지원 생성된 실행 파일의 경우 일반적으로 특정 오류 클래스에 대해 표시하는 대화 상자 팝업을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-325">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="14c36-326">`stderr`에만 쓰고 이러한 경우에는 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-326">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="14c36-327">CLI 옵션 `--additional-deps`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-327">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="14c36-328">검색된 RID를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-328">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="14c36-329">일부 경우에는 어셈블리 확인이 대체되는 "공유 저장소"의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-329">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="14c36-330">시작 후크를 로드하고 실행하는 어셈블리의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-330">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="14c36-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="14c36-331">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="14c36-332">호스팅 구성 요소(예: `dotnet.exe`, `hostfxr`, `hostpolicy`)에서 진단 추적을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="14c36-332">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="14c36-333">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14c36-333">See also</span></span>

- [<span data-ttu-id="14c36-334">런타임 구성 파일</span><span class="sxs-lookup"><span data-stu-id="14c36-334">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="14c36-335">.NET Core 런타임 구성 설정</span><span class="sxs-lookup"><span data-stu-id="14c36-335">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
