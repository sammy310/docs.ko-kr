---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 06/04/2018
ms.openlocfilehash: 801320bf7f3527ac70f1d5b9fe3d0ce537e50e93
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969775"
---
# <a name="dotnet-command"></a><span data-ttu-id="f03cb-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f03cb-104">name</span><span class="sxs-lookup"><span data-stu-id="f03cb-104">Name</span></span>

<span data-ttu-id="f03cb-105">`dotnet` - .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f03cb-106">개요</span><span class="sxs-lookup"><span data-stu-id="f03cb-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f03cb-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f03cb-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f03cb-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f03cb-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f03cb-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f03cb-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="f03cb-110">설명</span><span class="sxs-lookup"><span data-stu-id="f03cb-110">Description</span></span>

<span data-ttu-id="f03cb-111">`dotnet`은 .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="f03cb-112">[`dotnet build`](dotnet-build.md) 및 [`dotnet run`](dotnet-run.md)와 같은 특정 작업을 수행하는 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="f03cb-113">각 명령은 자체 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-113">Each command defines its own arguments.</span></span> <span data-ttu-id="f03cb-114">각 명령 다음에 `--help`를 입력하면 간단한 도움말 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="f03cb-115">`dotnet`은 `dotnet myapp.dll`과 같은 애플리케이션 DLL을 지정하여 애플리케이션을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="f03cb-116">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="f03cb-117">옵션</span><span class="sxs-lookup"><span data-stu-id="f03cb-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f03cb-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f03cb-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="f03cb-119">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="f03cb-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="f03cb-121">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="f03cb-122">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="f03cb-123">이 파일에 대한 자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="f03cb-124">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f03cb-125">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f03cb-126">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f03cb-127">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f03cb-128">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="f03cb-129">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="f03cb-130">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="f03cb-131">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="f03cb-132">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-132">`N` can be:</span></span>

- <span data-ttu-id="f03cb-133">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="f03cb-134">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="f03cb-135">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-135">This is the default behavior.</span></span>
- <span data-ttu-id="f03cb-136">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="f03cb-137">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="f03cb-138">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="f03cb-139">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="f03cb-140">자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f03cb-141">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f03cb-142">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f03cb-143">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f03cb-144">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f03cb-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f03cb-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="f03cb-146">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="f03cb-147">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="f03cb-148">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="f03cb-149">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="f03cb-150">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="f03cb-151">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f03cb-152">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f03cb-153">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f03cb-154">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f03cb-155">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="f03cb-156">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="f03cb-157">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="f03cb-158">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="f03cb-159">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="f03cb-160">자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f03cb-161">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f03cb-162">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f03cb-163">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f03cb-164">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f03cb-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f03cb-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="f03cb-166">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="f03cb-167">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="f03cb-168">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="f03cb-169">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="f03cb-170">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="f03cb-171">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="f03cb-172">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="f03cb-173">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="f03cb-174">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="f03cb-175">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="f03cb-176">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="f03cb-177">자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="f03cb-178">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="f03cb-179">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f03cb-180">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="f03cb-181">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="f03cb-182">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="f03cb-183">일반</span><span class="sxs-lookup"><span data-stu-id="f03cb-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f03cb-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f03cb-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="f03cb-185">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-185">Command</span></span>                                       | <span data-ttu-id="f03cb-186">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f03cb-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f03cb-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="f03cb-188">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f03cb-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="f03cb-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="f03cb-190">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="f03cb-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f03cb-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="f03cb-192">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="f03cb-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f03cb-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="f03cb-194">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f03cb-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f03cb-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="f03cb-196">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f03cb-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f03cb-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="f03cb-198">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f03cb-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f03cb-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="f03cb-200">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f03cb-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f03cb-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="f03cb-202">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f03cb-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f03cb-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="f03cb-204">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f03cb-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f03cb-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="f03cb-206">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f03cb-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f03cb-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="f03cb-208">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f03cb-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f03cb-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="f03cb-210">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f03cb-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f03cb-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="f03cb-212">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f03cb-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f03cb-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="f03cb-214">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f03cb-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f03cb-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="f03cb-216">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-216">Command</span></span>                             | <span data-ttu-id="f03cb-217">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f03cb-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f03cb-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f03cb-219">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f03cb-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f03cb-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f03cb-221">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f03cb-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="f03cb-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="f03cb-223">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="f03cb-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f03cb-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f03cb-225">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f03cb-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f03cb-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f03cb-227">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f03cb-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f03cb-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f03cb-229">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f03cb-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f03cb-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f03cb-231">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f03cb-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f03cb-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f03cb-233">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f03cb-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f03cb-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f03cb-235">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f03cb-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f03cb-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f03cb-237">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f03cb-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f03cb-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f03cb-239">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f03cb-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="f03cb-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="f03cb-241">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="f03cb-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f03cb-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f03cb-243">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f03cb-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f03cb-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="f03cb-245">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-245">Command</span></span>                             | <span data-ttu-id="f03cb-246">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="f03cb-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="f03cb-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="f03cb-248">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="f03cb-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="f03cb-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="f03cb-250">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="f03cb-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="f03cb-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="f03cb-252">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="f03cb-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="f03cb-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="f03cb-254">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="f03cb-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f03cb-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="f03cb-256">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="f03cb-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="f03cb-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="f03cb-258">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="f03cb-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="f03cb-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="f03cb-260">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="f03cb-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="f03cb-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="f03cb-262">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="f03cb-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="f03cb-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="f03cb-264">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="f03cb-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f03cb-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="f03cb-266">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="f03cb-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="f03cb-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="f03cb-268">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="f03cb-269">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="f03cb-269">Project references</span></span>

<span data-ttu-id="f03cb-270">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-270">Command</span></span> | <span data-ttu-id="f03cb-271">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-271">Function</span></span>
--- | ---
[<span data-ttu-id="f03cb-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="f03cb-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="f03cb-273">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-273">Adds a project reference.</span></span>
[<span data-ttu-id="f03cb-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="f03cb-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="f03cb-275">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-275">Lists project references.</span></span>
[<span data-ttu-id="f03cb-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="f03cb-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="f03cb-277">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="f03cb-278">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="f03cb-278">NuGet packages</span></span>

<span data-ttu-id="f03cb-279">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-279">Command</span></span> | <span data-ttu-id="f03cb-280">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-280">Function</span></span>
--- | ---
[<span data-ttu-id="f03cb-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="f03cb-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="f03cb-282">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="f03cb-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="f03cb-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="f03cb-284">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="f03cb-285">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-285">NuGet commands</span></span>

<span data-ttu-id="f03cb-286">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-286">Command</span></span> | <span data-ttu-id="f03cb-287">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-287">Function</span></span>
--- | ---
[<span data-ttu-id="f03cb-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="f03cb-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="f03cb-289">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="f03cb-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="f03cb-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="f03cb-291">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="f03cb-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="f03cb-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="f03cb-293">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="f03cb-294">전역 도구 명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-294">Global Tools commands</span></span>

<span data-ttu-id="f03cb-295">[.NET Core 전역 도구](global-tools.md)는 .NET Core SDK 2.1.300부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="f03cb-296">명령</span><span class="sxs-lookup"><span data-stu-id="f03cb-296">Command</span></span> | <span data-ttu-id="f03cb-297">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-297">Function</span></span>
--- | ---
[<span data-ttu-id="f03cb-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="f03cb-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="f03cb-299">컴퓨터에 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="f03cb-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="f03cb-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="f03cb-301">컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="f03cb-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="f03cb-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="f03cb-303">컴퓨터에서 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="f03cb-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="f03cb-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="f03cb-305">컴퓨터에서 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="f03cb-306">추가 도구</span><span class="sxs-lookup"><span data-stu-id="f03cb-306">Additional tools</span></span>

<span data-ttu-id="f03cb-307">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="f03cb-308">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="f03cb-309">도구</span><span class="sxs-lookup"><span data-stu-id="f03cb-309">Tool</span></span>                                              | <span data-ttu-id="f03cb-310">함수</span><span class="sxs-lookup"><span data-stu-id="f03cb-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="f03cb-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="f03cb-311">dev-certs</span></span>                                         | <span data-ttu-id="f03cb-312">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="f03cb-313">ef</span><span class="sxs-lookup"><span data-stu-id="f03cb-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="f03cb-314">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="f03cb-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="f03cb-315">sql-cache</span></span>                                         | <span data-ttu-id="f03cb-316">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="f03cb-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="f03cb-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="f03cb-318">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="f03cb-319">watch</span><span class="sxs-lookup"><span data-stu-id="f03cb-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="f03cb-320">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="f03cb-321">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="f03cb-322">예제</span><span class="sxs-lookup"><span data-stu-id="f03cb-322">Examples</span></span>

<span data-ttu-id="f03cb-323">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="f03cb-324">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="f03cb-325">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="f03cb-326">`myapp.dll`과 같은 애플리케이션 DLL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="f03cb-327">환경 변수</span><span class="sxs-lookup"><span data-stu-id="f03cb-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f03cb-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f03cb-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="f03cb-329">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-329">The global packages folder.</span></span> <span data-ttu-id="f03cb-330">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f03cb-331">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f03cb-332">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f03cb-333">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f03cb-334">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f03cb-335">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="f03cb-336">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="f03cb-337">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="f03cb-338">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="f03cb-339">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="f03cb-340">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="f03cb-341">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f03cb-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f03cb-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="f03cb-343">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-343">The primary package cache.</span></span> <span data-ttu-id="f03cb-344">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f03cb-345">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f03cb-346">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f03cb-347">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f03cb-348">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f03cb-349">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="f03cb-350">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="f03cb-351">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="f03cb-352">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="f03cb-353">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f03cb-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f03cb-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f03cb-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="f03cb-355">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-355">The primary package cache.</span></span> <span data-ttu-id="f03cb-356">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="f03cb-357">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="f03cb-358">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="f03cb-359">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="f03cb-360">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="f03cb-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="f03cb-361">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f03cb-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="f03cb-362">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f03cb-362">See also</span></span>

- [<span data-ttu-id="f03cb-363">런타임 구성 파일</span><span class="sxs-lookup"><span data-stu-id="f03cb-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
