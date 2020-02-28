---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI의 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 02/13/2020
ms.openlocfilehash: 364978465b63401907b46ead64dbceb2f15c8169
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451170"
---
# <a name="dotnet-command"></a><span data-ttu-id="1c577-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="1c577-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="1c577-104">이름</span><span class="sxs-lookup"><span data-stu-id="1c577-104">Name</span></span>

<span data-ttu-id="1c577-105">`dotnet` - .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1c577-106">개요</span><span class="sxs-lookup"><span data-stu-id="1c577-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="1c577-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c577-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20"></a>[<span data-ttu-id="1c577-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1c577-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="1c577-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c577-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="1c577-110">설명</span><span class="sxs-lookup"><span data-stu-id="1c577-110">Description</span></span>

<span data-ttu-id="1c577-111">`dotnet`은 .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="1c577-112">[`dotnet build`](dotnet-build.md) 및 [`dotnet run`](dotnet-run.md)와 같은 특정 작업을 수행하는 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="1c577-113">각 명령은 자체 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-113">Each command defines its own arguments.</span></span> <span data-ttu-id="1c577-114">각 명령 다음에 `--help`를 입력하면 간단한 도움말 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="1c577-115">`dotnet`은 `dotnet myapp.dll`과 같은 애플리케이션 DLL을 지정하여 애플리케이션을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="1c577-116">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="1c577-117">옵션</span><span class="sxs-lookup"><span data-stu-id="1c577-117">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1c577-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c577-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="1c577-119">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="1c577-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="1c577-121">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="1c577-122">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-122">A *deps.json* file contains a list of dependencies, compilation dependencies, and version information used to address assembly conflicts.</span></span> <span data-ttu-id="1c577-123">이 파일에 대한 자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="1c577-124">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="1c577-125">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="1c577-126">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="1c577-127">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="1c577-128">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="1c577-129">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="1c577-130">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="1c577-131">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="1c577-132">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-132">`N` can be:</span></span>

- <span data-ttu-id="1c577-133">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="1c577-134">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="1c577-135">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-135">This is the default behavior.</span></span>
- <span data-ttu-id="1c577-136">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="1c577-137">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="1c577-138">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="1c577-139">*runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-139">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="1c577-140">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-140">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1c577-141">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1c577-142">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1c577-143">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="1c577-144">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="1c577-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1c577-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="1c577-146">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="1c577-147">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="1c577-148">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="1c577-149">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="1c577-150">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="1c577-151">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="1c577-152">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="1c577-153">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="1c577-154">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="1c577-155">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="1c577-156">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="1c577-157">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="1c577-158">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="1c577-159">*runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-159">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="1c577-160">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-160">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1c577-161">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1c577-162">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1c577-163">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="1c577-164">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="1c577-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c577-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="1c577-166">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="1c577-167">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="1c577-168">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="1c577-169">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="1c577-170">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="1c577-171">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="1c577-172">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="1c577-173">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="1c577-174">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="1c577-175">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="1c577-176">*runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-176">A *runtimeconfig.json* file is a configuration file containing run-time settings.</span></span> <span data-ttu-id="1c577-177">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-177">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="1c577-178">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="1c577-179">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1c577-180">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="1c577-181">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="1c577-182">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="1c577-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="1c577-183">일반</span><span class="sxs-lookup"><span data-stu-id="1c577-183">General</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1c577-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c577-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="1c577-185">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-185">Command</span></span>                                       | <span data-ttu-id="1c577-186">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="1c577-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="1c577-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="1c577-188">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="1c577-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="1c577-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="1c577-190">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="1c577-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="1c577-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="1c577-192">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="1c577-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="1c577-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="1c577-194">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="1c577-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="1c577-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="1c577-196">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="1c577-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c577-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="1c577-198">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="1c577-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1c577-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="1c577-200">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="1c577-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="1c577-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="1c577-202">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="1c577-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="1c577-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="1c577-204">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="1c577-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="1c577-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="1c577-206">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="1c577-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="1c577-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="1c577-208">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="1c577-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1c577-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="1c577-210">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="1c577-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="1c577-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="1c577-212">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="1c577-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1c577-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="1c577-214">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20"></a>[<span data-ttu-id="1c577-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1c577-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="1c577-216">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-216">Command</span></span>                             | <span data-ttu-id="1c577-217">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="1c577-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="1c577-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="1c577-219">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="1c577-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="1c577-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="1c577-221">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="1c577-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="1c577-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="1c577-223">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="1c577-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="1c577-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="1c577-225">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="1c577-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c577-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="1c577-227">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="1c577-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1c577-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="1c577-229">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="1c577-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="1c577-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="1c577-231">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="1c577-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="1c577-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="1c577-233">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="1c577-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="1c577-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="1c577-235">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="1c577-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="1c577-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="1c577-237">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="1c577-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1c577-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="1c577-239">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="1c577-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="1c577-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="1c577-241">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="1c577-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1c577-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="1c577-243">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1x"></a>[<span data-ttu-id="1c577-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c577-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="1c577-245">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-245">Command</span></span>                             | <span data-ttu-id="1c577-246">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="1c577-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="1c577-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="1c577-248">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="1c577-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="1c577-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="1c577-250">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="1c577-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="1c577-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="1c577-252">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="1c577-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="1c577-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="1c577-254">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="1c577-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="1c577-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="1c577-256">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="1c577-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="1c577-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="1c577-258">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="1c577-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="1c577-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="1c577-260">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="1c577-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="1c577-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="1c577-262">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="1c577-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="1c577-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="1c577-264">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="1c577-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="1c577-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="1c577-266">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="1c577-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="1c577-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="1c577-268">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="1c577-269">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="1c577-269">Project references</span></span>

<span data-ttu-id="1c577-270">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-270">Command</span></span> | <span data-ttu-id="1c577-271">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-271">Function</span></span>
--- | ---
[<span data-ttu-id="1c577-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="1c577-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="1c577-273">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-273">Adds a project reference.</span></span>
[<span data-ttu-id="1c577-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="1c577-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="1c577-275">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-275">Lists project references.</span></span>
[<span data-ttu-id="1c577-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="1c577-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="1c577-277">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="1c577-278">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="1c577-278">NuGet packages</span></span>

<span data-ttu-id="1c577-279">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-279">Command</span></span> | <span data-ttu-id="1c577-280">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-280">Function</span></span>
--- | ---
[<span data-ttu-id="1c577-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="1c577-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="1c577-282">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="1c577-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="1c577-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="1c577-284">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="1c577-285">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="1c577-285">NuGet commands</span></span>

<span data-ttu-id="1c577-286">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-286">Command</span></span> | <span data-ttu-id="1c577-287">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-287">Function</span></span>
--- | ---
[<span data-ttu-id="1c577-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="1c577-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="1c577-289">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="1c577-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="1c577-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="1c577-291">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="1c577-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="1c577-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="1c577-293">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tool-path-and-local-tools-commands"></a><span data-ttu-id="1c577-294">전역, 도구 경로 및 로컬 도구 명령</span><span class="sxs-lookup"><span data-stu-id="1c577-294">Global, tool-path, and local tools commands</span></span>

<span data-ttu-id="1c577-295">도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-295">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="1c577-296">도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-296">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="1c577-297">도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-297">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="1c577-298">자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-298">For more information, see [.NET Core tools overview](global-tools.md).</span></span> <span data-ttu-id="1c577-299">전역 및 도구 경로 도구는 .NET Core SDK 2.1부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-299">Global and tool-path tools are available starting with .NET Core SDK 2.1.</span></span> <span data-ttu-id="1c577-300">로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-300">Local tools are available starting with .NET Core SDK 3.0.</span></span>

<span data-ttu-id="1c577-301">명령</span><span class="sxs-lookup"><span data-stu-id="1c577-301">Command</span></span> | <span data-ttu-id="1c577-302">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-302">Function</span></span>
--- | ---
[<span data-ttu-id="1c577-303">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="1c577-303">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="1c577-304">컴퓨터에 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-304">Installs a tool on your machine.</span></span>
[<span data-ttu-id="1c577-305">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="1c577-305">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="1c577-306">컴퓨터에 현재 설치되어 있는 모든 전역, 도구 경로 또는 로컬 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-306">Lists all global, tool-path, or local tools currently installed on your machine.</span></span>
[<span data-ttu-id="1c577-307">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="1c577-307">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="1c577-308">컴퓨터에서 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-308">Uninstalls a tool from your machine.</span></span>
[<span data-ttu-id="1c577-309">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="1c577-309">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="1c577-310">컴퓨터에 설치된 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-310">Updates a tool that is installed on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="1c577-311">추가 도구</span><span class="sxs-lookup"><span data-stu-id="1c577-311">Additional tools</span></span>

<span data-ttu-id="1c577-312">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-312">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="1c577-313">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-313">These tools are listed in the following table:</span></span>

| <span data-ttu-id="1c577-314">도구</span><span class="sxs-lookup"><span data-stu-id="1c577-314">Tool</span></span>                                              | <span data-ttu-id="1c577-315">기능</span><span class="sxs-lookup"><span data-stu-id="1c577-315">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="1c577-316">dev-certs</span><span class="sxs-lookup"><span data-stu-id="1c577-316">dev-certs</span></span>                                         | <span data-ttu-id="1c577-317">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-317">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="1c577-318">ef</span><span class="sxs-lookup"><span data-stu-id="1c577-318">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="1c577-319">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-319">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="1c577-320">sql-cache</span><span class="sxs-lookup"><span data-stu-id="1c577-320">sql-cache</span></span>                                         | <span data-ttu-id="1c577-321">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-321">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="1c577-322">user-secrets</span><span class="sxs-lookup"><span data-stu-id="1c577-322">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="1c577-323">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-323">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="1c577-324">watch</span><span class="sxs-lookup"><span data-stu-id="1c577-324">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="1c577-325">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-325">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="1c577-326">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-326">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="1c577-327">예</span><span class="sxs-lookup"><span data-stu-id="1c577-327">Examples</span></span>

<span data-ttu-id="1c577-328">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-328">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="1c577-329">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-329">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="1c577-330">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-330">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="1c577-331">`myapp.dll`과 같은 애플리케이션 DLL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-331">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="1c577-332">환경 변수</span><span class="sxs-lookup"><span data-stu-id="1c577-332">Environment variables</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1c577-333">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1c577-333">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="1c577-334">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-334">The global packages folder.</span></span> <span data-ttu-id="1c577-335">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-335">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="1c577-336">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-336">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="1c577-337">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-337">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="1c577-338">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-338">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="1c577-339">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-339">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="1c577-340">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-340">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="1c577-341">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-341">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="1c577-342">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-342">If not set, it defaults to `true`.</span></span> <span data-ttu-id="1c577-343">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-343">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="1c577-344">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-344">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="1c577-345">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-345">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="1c577-346">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-346">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="1c577-347">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="1c577-347">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="1c577-348">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-348">The primary package cache.</span></span> <span data-ttu-id="1c577-349">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-349">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="1c577-350">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-350">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="1c577-351">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-351">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="1c577-352">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-352">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="1c577-353">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-353">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="1c577-354">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-354">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="1c577-355">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-355">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="1c577-356">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-356">If not set, it defaults to `true`.</span></span> <span data-ttu-id="1c577-357">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-357">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="1c577-358">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c577-358">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="1c577-359">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="1c577-359">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="1c577-360">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-360">The primary package cache.</span></span> <span data-ttu-id="1c577-361">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-361">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="1c577-362">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-362">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="1c577-363">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-363">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="1c577-364">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-364">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="1c577-365">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="1c577-365">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="1c577-366">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c577-366">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="1c577-367">참조</span><span class="sxs-lookup"><span data-stu-id="1c577-367">See also</span></span>

- [<span data-ttu-id="1c577-368">런타임 구성 파일</span><span class="sxs-lookup"><span data-stu-id="1c577-368">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [<span data-ttu-id="1c577-369">.NET Core 런타임 구성 설정</span><span class="sxs-lookup"><span data-stu-id="1c577-369">.NET Core run-time configuration settings</span></span>](../run-time-config/index.md)
