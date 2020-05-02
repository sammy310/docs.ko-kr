---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI의 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 02/13/2020
ms.openlocfilehash: 6a08297499d955db44e342dc82fed25b7b9b8171
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739075"
---
# <a name="dotnet-command"></a><span data-ttu-id="c5a07-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-103">dotnet command</span></span>

<span data-ttu-id="c5a07-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="c5a07-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="c5a07-105">이름</span><span class="sxs-lookup"><span data-stu-id="c5a07-105">Name</span></span>

<span data-ttu-id="c5a07-106">`dotnet` - .NET Core CLI에 대한 일반 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-106">`dotnet` - The generic driver for the .NET Core CLI.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c5a07-107">개요</span><span class="sxs-lookup"><span data-stu-id="c5a07-107">Synopsis</span></span>

<span data-ttu-id="c5a07-108">사용 가능한 명령 및 환경에 대한 정보를 얻으려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-108">To get information about the available commands and the environment:</span></span>

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

<span data-ttu-id="c5a07-109">명령을 실행하려면(SDK를 설치해야 함) 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-109">To run a command (requires SDK installation):</span></span>

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

<span data-ttu-id="c5a07-110">애플리케이션을 실행하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-110">To run an application:</span></span>

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

<span data-ttu-id="c5a07-111">`--roll-forward`는 .NET Core 3.x 이후로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-111">`--roll-forward` is available since .NET Core 3.x.</span></span> <span data-ttu-id="c5a07-112">.NET Core 2.x의 경우 `--roll-forward-on-no-candidate-fx`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-112">Use `--roll-forward-on-no-candidate-fx` for .NET Core 2.x.</span></span>

## <a name="description"></a><span data-ttu-id="c5a07-113">설명</span><span class="sxs-lookup"><span data-stu-id="c5a07-113">Description</span></span>

<span data-ttu-id="c5a07-114">`dotnet` 명령에는 두 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-114">The `dotnet` command has two functions:</span></span>

- <span data-ttu-id="c5a07-115">.NET Core 프로젝트 작업을 위한 명령을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-115">It provides commands for working with .NET Core projects.</span></span>

  <span data-ttu-id="c5a07-116">예를 들어 [`dotnet build`](dotnet-build.md)는 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-116">For example, [`dotnet build`](dotnet-build.md) builds a project.</span></span> <span data-ttu-id="c5a07-117">각 명령은 자체 옵션과 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-117">Each command defines its own options and arguments.</span></span> <span data-ttu-id="c5a07-118">모든 명령은 명령을 사용하는 방법에 대해 간략한 설명서를 출력하는 `--help` 옵션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-118">All commands support the `--help` option for printing out brief documentation about how to use the command.</span></span>

- <span data-ttu-id="c5a07-119">.NET Core 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-119">It runs .NET Core applications.</span></span>

  <span data-ttu-id="c5a07-120">애플리케이션을 실행할 애플리케이션 `.dll` 파일의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-120">You specify the path to an application `.dll` file to run the application.</span></span>  <span data-ttu-id="c5a07-121">애플리케이션을 실행하는 것은 진입점을 찾아서 실행하는 것이며 콘솔 앱의 경우에는 `Main` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-121">To run the application means to find and execute the entry point, which in the case of console apps is the `Main` method.</span></span> <span data-ttu-id="c5a07-122">예를 들어 `dotnet myapp.dll`은 `myapp` 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-122">For example, `dotnet myapp.dll` runs the `myapp` application.</span></span> <span data-ttu-id="c5a07-123">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-123">See [.NET Core application deployment](../deploying/index.md) to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="c5a07-124">옵션</span><span class="sxs-lookup"><span data-stu-id="c5a07-124">Options</span></span>

<span data-ttu-id="c5a07-125">명령 실행, 애플리케이션 실행을 위해 `dotnet` 자체에 사용할 수 있는 다양한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-125">Different options are available for `dotnet` by itself, for running a command, and for running an application.</span></span>

### <a name="options-for-dotnet-by-itself"></a><span data-ttu-id="c5a07-126">dotnet 자체에 대한 옵션</span><span class="sxs-lookup"><span data-stu-id="c5a07-126">Options for dotnet by itself</span></span>

<span data-ttu-id="c5a07-127">`dotnet` 자체에 대한 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-127">The following options are for `dotnet` by itself.</span></span> <span data-ttu-id="c5a07-128">예: `dotnet --info`.</span><span class="sxs-lookup"><span data-stu-id="c5a07-128">For example, `dotnet --info`.</span></span> <span data-ttu-id="c5a07-129">환경에 대한 정보를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-129">They print out information about the environment.</span></span>

- **`--info`**

  <span data-ttu-id="c5a07-130">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-130">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

- **`--version`**

  <span data-ttu-id="c5a07-131">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-131">Prints out the version of the .NET Core SDK in use.</span></span>

- **`--list-runtimes`**

  <span data-ttu-id="c5a07-132">설치된 .NET Core 런타임의 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-132">Prints out a list of the installed .NET Core runtimes.</span></span> <span data-ttu-id="c5a07-133">x86 버전 SDK는 x86 런타임만 나열하며 x64 버전 SDK는 x64 런타임만 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-133">An x86 version of the SDK lists only x86 runtimes, and an x64 version of the SDK lists only x64 runtimes.</span></span>

- **`--list-sdks`**

  <span data-ttu-id="c5a07-134">설치된 .NET Core SDK의 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-134">Prints out a list of the installed .NET Core SDKs.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c5a07-135">사용 가능한 명령 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-135">Prints out a list of available commands.</span></span>

### <a name="sdk-options-for-running-a-command"></a><span data-ttu-id="c5a07-136">명령을 실행하기 위한 SDK 옵션</span><span class="sxs-lookup"><span data-stu-id="c5a07-136">SDK options for running a command</span></span>

<span data-ttu-id="c5a07-137">명령과 함께 사용하는 `dotnet`의 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-137">The following options are for `dotnet` with a command.</span></span> <span data-ttu-id="c5a07-138">예: `dotnet build --help`.</span><span class="sxs-lookup"><span data-stu-id="c5a07-138">For example, `dotnet build --help`.</span></span>

- **`-d|--diagnostics`**

  <span data-ttu-id="c5a07-139">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-139">Enables diagnostic output.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="c5a07-140">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-140">Sets the verbosity level of the command.</span></span> <span data-ttu-id="c5a07-141">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-141">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="c5a07-142">모든 명령에서 지원되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-142">Not supported in every command.</span></span> <span data-ttu-id="c5a07-143">이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-143">See specific command page to determine if this option is available.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c5a07-144">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span>

- **`command options`**

  <span data-ttu-id="c5a07-145">각 명령은 해당 명령과 관련된 옵션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-145">Each command defines options specific to that command.</span></span> <span data-ttu-id="c5a07-146">사용 가능한 옵션 목록은 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-146">See specific command page for a list of available options.</span></span>

### <a name="runtime-options"></a><span data-ttu-id="c5a07-147">런타임 옵션</span><span class="sxs-lookup"><span data-stu-id="c5a07-147">Runtime options</span></span>

<span data-ttu-id="c5a07-148">`dotnet`이 애플리케이션을 실행할 때 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-148">The following options are available when `dotnet` runs an application.</span></span> <span data-ttu-id="c5a07-149">예: `dotnet myapp.dll --fx-version 3.1.1`.</span><span class="sxs-lookup"><span data-stu-id="c5a07-149">For example, `dotnet myapp.dll --fx-version 3.1.1`.</span></span>

- **`--additionalprobingpath <PATH>`**

  <span data-ttu-id="c5a07-150">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-150">Path containing probing policy and assemblies to probe.</span></span>

- **`--additional-deps <PATH>`**

  <span data-ttu-id="c5a07-151">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-151">Path to an additional *.deps.json* file.</span></span> <span data-ttu-id="c5a07-152">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-152">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="c5a07-153">자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-153">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

- **`--fx-version <VERSION>`**

  <span data-ttu-id="c5a07-154">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-154">Version of the .NET Core runtime to use to run the application.</span></span>

- **`--runtimeconfig`**

  <span data-ttu-id="c5a07-155">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-155">Path to a *runtimeconfig.json* file.</span></span> <span data-ttu-id="c5a07-156">*runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-156">A *runtimeconfig.json* file is a configuration file that contains run-time settings.</span></span> <span data-ttu-id="c5a07-157">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-157">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

- <span data-ttu-id="c5a07-158">**`--roll-forward-on-no-candidate-fx <N>`** **.NET Core 2.x SDK에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5a07-158">**`--roll-forward-on-no-candidate-fx <N>`** **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="c5a07-159">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-159">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="c5a07-160">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-160">`N` can be:</span></span>

  - <span data-ttu-id="c5a07-161">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-161">`0` - Disable even minor version roll forward.</span></span>
  - <span data-ttu-id="c5a07-162">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-162">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="c5a07-163">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-163">This is the default behavior.</span></span>
  - <span data-ttu-id="c5a07-164">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-164">`2` - Roll forward on minor and major versions.</span></span>

   <span data-ttu-id="c5a07-165">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-165">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- <span data-ttu-id="c5a07-166">**`--roll-forward <SETTING>`** **.NET Core SDK 3.0부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5a07-166">**`--roll-forward <SETTING>`** **Available starting with .NET Core SDK 3.0.**</span></span>

  <span data-ttu-id="c5a07-167">앱에 롤포워드가 적용되는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-167">Controls how roll forward is applied to the app.</span></span> <span data-ttu-id="c5a07-168">`SETTING`은 다음 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-168">The `SETTING` can be one of the following values.</span></span> <span data-ttu-id="c5a07-169">지정하지 않으면 `Minor`이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-169">If not specified, `Minor` is the default.</span></span>

  - <span data-ttu-id="c5a07-170">`LatestPatch` - 가장 높은 패치 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-170">`LatestPatch` - Roll forward to the highest patch version.</span></span> <span data-ttu-id="c5a07-171">부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-171">This disables minor version roll forward.</span></span>
  - <span data-ttu-id="c5a07-172">`Minor` - 요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-172">`Minor` - Roll forward to the lowest higher minor version, if requested minor version is missing.</span></span> <span data-ttu-id="c5a07-173">요청된 부 버전이 있다면 LatestPatch 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-173">If the requested minor version is present, then the LatestPatch policy is used.</span></span>
  - <span data-ttu-id="c5a07-174">`Major` - 요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-174">`Major` - Roll forward to lowest higher major version, and lowest minor version, if requested major version is missing.</span></span> <span data-ttu-id="c5a07-175">요청된 주 버전이 있다면 Minor 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-175">If the requested major version is present, then the Minor policy is used.</span></span>
  - <span data-ttu-id="c5a07-176">`LatestMinor` - 요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-176">`LatestMinor` - Roll forward to highest minor version, even if requested minor version is present.</span></span> <span data-ttu-id="c5a07-177">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-177">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="c5a07-178">`LatestMajor` - 요청된 주 버전이 있는 경우에도 가장 높은 주 버전, 가장 높은 부 버전으로 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-178">`LatestMajor` - Roll forward to highest major and highest minor version, even if requested major is present.</span></span> <span data-ttu-id="c5a07-179">구성 요소 호스팅 시나리오를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-179">Intended for component hosting scenarios.</span></span>
  - <span data-ttu-id="c5a07-180">`Disable` - 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-180">`Disable` - Don't roll forward.</span></span> <span data-ttu-id="c5a07-181">지정된 버전에만 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-181">Only bind to specified version.</span></span> <span data-ttu-id="c5a07-182">이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-182">This policy isn't recommended for general use because it disables the ability to roll forward to the latest patches.</span></span> <span data-ttu-id="c5a07-183">이 값은 테스트용으로만 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-183">This value is only recommended for testing.</span></span>

<span data-ttu-id="c5a07-184">`Disable`을 제외하고, 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-184">With the exception of `Disable`, all settings will use the highest available patch version.</span></span>

<span data-ttu-id="c5a07-185">롤포워드 동작은 프로젝트 파일 속성, 런타임 구성 파일 속성 및 환경 변수에서도 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-185">Roll forward behavior can also be configured in a project file property, a run-time configuration file property, and an environment variable.</span></span> <span data-ttu-id="c5a07-186">자세한 내용은 [주 버전 런타임 롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-186">For more information, see [Major-version runtime roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).</span></span>

## <a name="dotnet-commands"></a><span data-ttu-id="c5a07-187">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-187">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="c5a07-188">일반</span><span class="sxs-lookup"><span data-stu-id="c5a07-188">General</span></span>

| <span data-ttu-id="c5a07-189">명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-189">Command</span></span>                                       | <span data-ttu-id="c5a07-190">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-190">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="c5a07-191">dotnet build</span><span class="sxs-lookup"><span data-stu-id="c5a07-191">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="c5a07-192">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-192">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="c5a07-193">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="c5a07-193">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="c5a07-194">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-194">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="c5a07-195">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="c5a07-195">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="c5a07-196">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-196">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="c5a07-197">dotnet help</span><span class="sxs-lookup"><span data-stu-id="c5a07-197">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="c5a07-198">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-198">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="c5a07-199">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="c5a07-199">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="c5a07-200">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-200">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="c5a07-201">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="c5a07-201">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="c5a07-202">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-202">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="c5a07-203">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c5a07-203">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="c5a07-204">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-204">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="c5a07-205">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="c5a07-205">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="c5a07-206">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-206">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="c5a07-207">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="c5a07-207">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="c5a07-208">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-208">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="c5a07-209">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="c5a07-209">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="c5a07-210">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-210">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="c5a07-211">dotnet run</span><span class="sxs-lookup"><span data-stu-id="c5a07-211">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="c5a07-212">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-212">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="c5a07-213">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="c5a07-213">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="c5a07-214">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-214">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="c5a07-215">dotnet store</span><span class="sxs-lookup"><span data-stu-id="c5a07-215">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="c5a07-216">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-216">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="c5a07-217">dotnet test</span><span class="sxs-lookup"><span data-stu-id="c5a07-217">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="c5a07-218">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-218">Runs tests using a test runner.</span></span>                                     |

### <a name="project-references"></a><span data-ttu-id="c5a07-219">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="c5a07-219">Project references</span></span>

<span data-ttu-id="c5a07-220">명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-220">Command</span></span> | <span data-ttu-id="c5a07-221">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-221">Function</span></span>
--- | ---
[<span data-ttu-id="c5a07-222">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="c5a07-222">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="c5a07-223">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-223">Adds a project reference.</span></span>
[<span data-ttu-id="c5a07-224">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c5a07-224">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="c5a07-225">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-225">Lists project references.</span></span>
[<span data-ttu-id="c5a07-226">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="c5a07-226">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="c5a07-227">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-227">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="c5a07-228">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="c5a07-228">NuGet packages</span></span>

<span data-ttu-id="c5a07-229">명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-229">Command</span></span> | <span data-ttu-id="c5a07-230">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-230">Function</span></span>
--- | ---
[<span data-ttu-id="c5a07-231">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="c5a07-231">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="c5a07-232">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-232">Adds a NuGet package.</span></span>
[<span data-ttu-id="c5a07-233">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="c5a07-233">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="c5a07-234">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-234">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="c5a07-235">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-235">NuGet commands</span></span>

<span data-ttu-id="c5a07-236">명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-236">Command</span></span> | <span data-ttu-id="c5a07-237">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-237">Function</span></span>
--- | ---
[<span data-ttu-id="c5a07-238">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c5a07-238">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="c5a07-239">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-239">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="c5a07-240">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="c5a07-240">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="c5a07-241">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-241">Pushes a package to the server and publishes it.</span></span>
[<span data-ttu-id="c5a07-242">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="c5a07-242">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="c5a07-243">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-243">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="c5a07-244">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="c5a07-244">dotnet nuget add source</span></span>](dotnet-nuget-add-source.md) | <span data-ttu-id="c5a07-245">NuGet 소스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-245">Adds a NuGet source.</span></span>
[<span data-ttu-id="c5a07-246">dotnet nuget disable source</span><span class="sxs-lookup"><span data-stu-id="c5a07-246">dotnet nuget disable source</span></span>](dotnet-nuget-disable-source.md) | <span data-ttu-id="c5a07-247">NuGet 소스를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-247">Disables a NuGet source.</span></span>
[<span data-ttu-id="c5a07-248">dotnet nuget enable source</span><span class="sxs-lookup"><span data-stu-id="c5a07-248">dotnet nuget enable source</span></span>](dotnet-nuget-enable-source.md) | <span data-ttu-id="c5a07-249">NuGet 소스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-249">Enables a NuGet source.</span></span>
[<span data-ttu-id="c5a07-250">dotnet nuget list source</span><span class="sxs-lookup"><span data-stu-id="c5a07-250">dotnet nuget list source</span></span>](dotnet-nuget-list-source.md) | <span data-ttu-id="c5a07-251">구성된 NuGet 소스를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-251">Lists all configured NuGet sources.</span></span>
[<span data-ttu-id="c5a07-252">dotnet nuget remove source</span><span class="sxs-lookup"><span data-stu-id="c5a07-252">dotnet nuget remove source</span></span>](dotnet-nuget-remove-source.md) | <span data-ttu-id="c5a07-253">NuGet 소스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-253">Removes a NuGet source.</span></span>
[<span data-ttu-id="c5a07-254">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="c5a07-254">dotnet nuget update source</span></span>](dotnet-nuget-update-source.md) | <span data-ttu-id="c5a07-255">NuGet 소스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-255">Updates a NuGet source.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="c5a07-256">전역, 도구 경로 및 로컬 도구 명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-256">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="c5a07-257">도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-257">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="c5a07-258">도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-258">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="c5a07-259">도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-259">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="c5a07-260">자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-260">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="c5a07-261">전역 및 도구 경로 도구는 .NET Core SDK 2.1부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-261">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="c5a07-262">로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-262">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="c5a07-263">명령</span><span class="sxs-lookup"><span data-stu-id="c5a07-263">Command</span></span> | <span data-ttu-id="c5a07-264">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-264">Function</span></span>
--- | ---
[<span data-ttu-id="c5a07-265">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="c5a07-265">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="c5a07-266">컴퓨터에 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-266">Installs a tool on your machine.</span></span>
[<span data-ttu-id="c5a07-267">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="c5a07-267">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="c5a07-268">컴퓨터에 현재 설치되어 있는 모든 전역, 도구 경로 또는 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-268">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="c5a07-269">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="c5a07-269">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="c5a07-270">컴퓨터에서 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-270">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="c5a07-271">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="c5a07-271">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="c5a07-272">컴퓨터에 설치된 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-272">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="c5a07-273">추가 도구</span><span class="sxs-lookup"><span data-stu-id="c5a07-273">Additional tools</span></span>

<span data-ttu-id="c5a07-274">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-274">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="c5a07-275">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-275">These tools are listed in the following table:</span></span>

| <span data-ttu-id="c5a07-276">도구</span><span class="sxs-lookup"><span data-stu-id="c5a07-276">Tool</span></span>                                              | <span data-ttu-id="c5a07-277">기능</span><span class="sxs-lookup"><span data-stu-id="c5a07-277">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="c5a07-278">dev-certs</span><span class="sxs-lookup"><span data-stu-id="c5a07-278">dev-certs</span></span>                                         | <span data-ttu-id="c5a07-279">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-279">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="c5a07-280">ef</span><span class="sxs-lookup"><span data-stu-id="c5a07-280">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="c5a07-281">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-281">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="c5a07-282">sql-cache</span><span class="sxs-lookup"><span data-stu-id="c5a07-282">sql-cache</span></span>                                         | <span data-ttu-id="c5a07-283">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-283">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="c5a07-284">user-secrets</span><span class="sxs-lookup"><span data-stu-id="c5a07-284">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="c5a07-285">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-285">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="c5a07-286">watch</span><span class="sxs-lookup"><span data-stu-id="c5a07-286">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="c5a07-287">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-287">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="c5a07-288">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-288">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="c5a07-289">예</span><span class="sxs-lookup"><span data-stu-id="c5a07-289">Examples</span></span>

<span data-ttu-id="c5a07-290">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-290">Create a new .NET Core console application:</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="c5a07-291">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-291">Build a project and its dependencies in a given directory:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="c5a07-292">애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-292">Run an application:</span></span>

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a><span data-ttu-id="c5a07-293">환경 변수</span><span class="sxs-lookup"><span data-stu-id="c5a07-293">Environment variables</span></span>

- <span data-ttu-id="c5a07-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span><span class="sxs-lookup"><span data-stu-id="c5a07-294">`DOTNET_ROOT`, `DOTNET_ROOT(x86)`</span></span>

  <span data-ttu-id="c5a07-295">기본 위치에 설치되어 있지 않은 경우 .NET Core 런타임의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-295">Specifies the location of the .NET Core runtimes, if they are not installed in the default location.</span></span> <span data-ttu-id="c5a07-296">Windows에서 기본 위치는 `C:\Program Files\dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-296">The default location on Windows is `C:\Program Files\dotnet`.</span></span> <span data-ttu-id="c5a07-297">Linux 및 macOS에서 기본 위치는 `/usr/share/dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-297">The default location on Linux and macOS is `/usr/share/dotnet`.</span></span> <span data-ttu-id="c5a07-298">이 환경 변수는 생성된 실행 파일(apphost)을 통해 앱을 실행할 때만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-298">This environment variable is used only when running apps via generated executables (apphosts).</span></span> <span data-ttu-id="c5a07-299">64비트 OS에서 32비트 실행 파일을 실행할 때는 대신 `DOTNET_ROOT(x86)`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-299">`DOTNET_ROOT(x86)` is used instead when running a 32-bit executable on a 64-bit OS.</span></span>

- `DOTNET_PACKAGES`

  <span data-ttu-id="c5a07-300">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-300">The global packages folder.</span></span> <span data-ttu-id="c5a07-301">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-301">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

- `DOTNET_SERVICING`

  <span data-ttu-id="c5a07-302">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-302">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

- `DOTNET_NOLOGO`

  <span data-ttu-id="c5a07-303">처음 실행할 때 .NET Core 시작 및 원격 분석 메시지를 표시할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-303">Specifies whether .NET Core welcome and telemetry messages are displayed on first run.</span></span> <span data-ttu-id="c5a07-304">이러한 메시지를 음소거하려면 `true`로 설정하고(`true`, `1` 또는 `yes` 값 사용) 허용하려면 `false`로 설정합니다(`false`, `0` 또는 `no` 값 사용).</span><span class="sxs-lookup"><span data-stu-id="c5a07-304">Set to `true` to mute these messages (values `true`, `1`, or `yes` accepted) or set to `false` to allow (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c5a07-305">설정되지 않은 경우 기본값은 `false`이고 처음 실행될 때 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-305">If not set, the default is `false` and the messages will be displayed on first run.</span></span> <span data-ttu-id="c5a07-306">이 플래그는 원격 분석에는 영향을 주지 않습니다(원격 분석 보내기를 옵트아웃하는 경우 `DOTNET_CLI_TELEMETRY_OPTOUT` 참조).</span><span class="sxs-lookup"><span data-stu-id="c5a07-306">This flag has no effect on telemetry (see `DOTNET_CLI_TELEMETRY_OPTOUT` for opting out of sending telemetry).</span></span>

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  <span data-ttu-id="c5a07-307">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-307">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="c5a07-308">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="c5a07-308">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="c5a07-309">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="c5a07-309">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="c5a07-310">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-310">If not set, the default is `false` and the telemetry feature is active.</span></span>

- `DOTNET_MULTILEVEL_LOOKUP`

  <span data-ttu-id="c5a07-311">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-311">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="c5a07-312">설정하지 않은 경우 기본값은 1(논리적 `true`)입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-312">If not set, it defaults to 1 (logical `true`).</span></span> <span data-ttu-id="c5a07-313">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 사용하려면 0(논리적 `false`)으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-313">Set to 0 (logical `false`) to not resolve from the global location and have isolated .NET Core installations.</span></span> <span data-ttu-id="c5a07-314">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-314">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

- <span data-ttu-id="c5a07-315">`DOTNET_ROLL_FORWARD` **.NET Core 3.x SDK부터 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5a07-315">`DOTNET_ROLL_FORWARD` **Available starting with .NET Core 3.x SDK.**</span></span>

  <span data-ttu-id="c5a07-316">롤포워드 동작을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-316">Determines roll forward behavior.</span></span> <span data-ttu-id="c5a07-317">자세한 내용은 이 문서 앞부분에서 `--roll-forward` 옵션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-317">For more information, see the `--roll-forward` option earlier in this article.</span></span>

- <span data-ttu-id="c5a07-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **.NET Core 2.x SDK에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c5a07-318">`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Available in .NET Core 2.x SDK.**</span></span>

  <span data-ttu-id="c5a07-319">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-319">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="c5a07-320">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-320">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

- `DOTNET_CLI_UI_LANGUAGE`

  <span data-ttu-id="c5a07-321">`en-us`와 같은 로캘 값을 사용하여 CLI UI의 언어를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-321">Sets the language of the CLI UI using a locale value such as `en-us`.</span></span> <span data-ttu-id="c5a07-322">지원되는 값은 Visual Studio의 경우와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-322">The supported values are the same as for Visual Studio.</span></span> <span data-ttu-id="c5a07-323">자세한 내용은 [Visual Studio 설치 설명서](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)에서 설치 프로그램 언어 변경에 대한 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5a07-323">For more information, see the section on changing the installer language in the [Visual Studio installation documentation](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019).</span></span> <span data-ttu-id="c5a07-324">.NET 리소스 관리자 규칙이 적용되므로, 정확한 일치를 선택할 필요가 없습니다. `CultureInfo` 트리에서 하위 항목을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-324">The .NET resource manager rules apply, so you don't have to pick an exact match&mdash;you can also pick descendants in the `CultureInfo` tree.</span></span> <span data-ttu-id="c5a07-325">예를 들어 `fr-CA`로 설정하면 CLI에서 `fr` 번역을 찾아 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-325">For example, if you set it to `fr-CA`, the CLI will find and use the `fr` translations.</span></span> <span data-ttu-id="c5a07-326">지원되지 않는 언어로 설정하면 CLI는 영어로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-326">If you set it to a language that is not supported, the CLI falls back to English.</span></span>

- `DOTNET_DISABLE_GUI_ERRORS`

  <span data-ttu-id="c5a07-327">GUI 지원 생성된 실행 파일의 경우 일반적으로 특정 오류 클래스에 대해 표시하는 대화 상자 팝업을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-327">For GUI-enabled generated executables - disables dialog popup, which normally shows for certain classes of errors.</span></span> <span data-ttu-id="c5a07-328">`stderr`에만 쓰고 이러한 경우에는 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-328">It only writes to `stderr` and exits in those cases.</span></span>
  
- `DOTNET_ADDITIONAL_DEPS`

  <span data-ttu-id="c5a07-329">CLI 옵션 `--additional-deps`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-329">Equivalent to CLI option `--additional-deps`.</span></span>

- `DOTNET_RUNTIME_ID`

  <span data-ttu-id="c5a07-330">검색된 RID를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-330">Overrides the detected RID.</span></span>

- `DOTNET_SHARED_STORE`

  <span data-ttu-id="c5a07-331">일부 경우에는 어셈블리 확인이 대체되는 "공유 저장소"의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-331">Location of the "shared store" which assembly resolution falls back to in some cases.</span></span>

- `DOTNET_STARTUP_HOOKS`

  <span data-ttu-id="c5a07-332">시작 후크를 로드하고 실행하는 어셈블리의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-332">List of assemblies to load and execute startup hooks from.</span></span>

- <span data-ttu-id="c5a07-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span><span class="sxs-lookup"><span data-stu-id="c5a07-333">`COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`</span></span>

  <span data-ttu-id="c5a07-334">호스팅 구성 요소(예: `dotnet.exe`, `hostfxr`, `hostpolicy`)에서 진단 추적을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c5a07-334">Controls diagnostics tracing from the hosting components, such as `dotnet.exe`, `hostfxr`, and `hostpolicy`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5a07-335">참조</span><span class="sxs-lookup"><span data-stu-id="c5a07-335">See also</span></span>

- [<span data-ttu-id="c5a07-336">런타임 구성 파일</span><span class="sxs-lookup"><span data-stu-id="c5a07-336">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="c5a07-337">.NET Core 런타임 구성 설정</span><span class="sxs-lookup"><span data-stu-id="c5a07-337">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
