---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 06/04/2018
ms.openlocfilehash: a22340c26ca2e483e43857e2ecb31f2ab53b60f4
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117512"
---
# <a name="dotnet-command"></a><span data-ttu-id="6cb88-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="6cb88-104">name</span><span class="sxs-lookup"><span data-stu-id="6cb88-104">Name</span></span>

<span data-ttu-id="6cb88-105">`dotnet` - .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6cb88-106">개요</span><span class="sxs-lookup"><span data-stu-id="6cb88-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cb88-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cb88-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cb88-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cb88-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [--depsfile]
    [-d|--diagnostics] [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx]
    [--runtimeconfig] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cb88-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cb88-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet [command] [arguments] [--additionalprobingpath] [--depsfile] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--runtimeconfig] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="6cb88-110">설명</span><span class="sxs-lookup"><span data-stu-id="6cb88-110">Description</span></span>

<span data-ttu-id="6cb88-111">`dotnet`은 .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="6cb88-112">[`dotnet build`](dotnet-build.md) 및 [`dotnet run`](dotnet-run.md)와 같은 특정 작업을 수행하는 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="6cb88-113">각 명령은 자체 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-113">Each command defines its own arguments.</span></span> <span data-ttu-id="6cb88-114">각 명령 다음에 `--help`를 입력하면 간단한 도움말 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="6cb88-115">`dotnet`은 `dotnet myapp.dll`과 같은 애플리케이션 DLL을 지정하여 애플리케이션을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="6cb88-116">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="6cb88-117">옵션</span><span class="sxs-lookup"><span data-stu-id="6cb88-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cb88-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cb88-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="6cb88-119">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-119">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="6cb88-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-120">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="6cb88-121">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-121">Path to a *deps.json* file.</span></span>

<span data-ttu-id="6cb88-122">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-122">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="6cb88-123">이 파일에 대한 자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-123">For more information about this file, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-d|--diagnostics`

<span data-ttu-id="6cb88-124">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-124">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="6cb88-125">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-125">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="6cb88-126">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-126">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="6cb88-127">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-127">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="6cb88-128">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-128">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="6cb88-129">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-129">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="6cb88-130">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-130">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="6cb88-131">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-131">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="6cb88-132">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-132">`N` can be:</span></span>

- <span data-ttu-id="6cb88-133">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-133">`0` - Disable even minor version roll forward.</span></span>
- <span data-ttu-id="6cb88-134">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-134">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="6cb88-135">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-135">This is the default behavior.</span></span>
- <span data-ttu-id="6cb88-136">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-136">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="6cb88-137">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-137">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="6cb88-138">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-138">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="6cb88-139">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-139">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="6cb88-140">자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-140">For more information, see [Runtime Configuration Files](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) on GitHub.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cb88-141">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-141">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cb88-142">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-142">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6cb88-143">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-143">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="6cb88-144">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-144">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cb88-145">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cb88-145">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="6cb88-146">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-146">Path to an additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="6cb88-147">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-147">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="6cb88-148">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-148">Path to a *deps.json* file.</span></span>

<span data-ttu-id="6cb88-149">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-149">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="6cb88-150">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-150">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="6cb88-151">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-151">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="6cb88-152">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-152">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="6cb88-153">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-153">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="6cb88-154">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-154">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="6cb88-155">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-155">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="6cb88-156">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-156">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="6cb88-157">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-157">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`--runtimeconfig`

<span data-ttu-id="6cb88-158">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-158">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="6cb88-159">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-159">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="6cb88-160">자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-160">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cb88-161">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-161">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cb88-162">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-162">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6cb88-163">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-163">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="6cb88-164">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-164">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cb88-165">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cb88-165">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="6cb88-166">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-166">Path containing probing policy and assemblies to probe.</span></span>

`--depsfile`

<span data-ttu-id="6cb88-167">*deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-167">Path to a *deps.json* file.</span></span>

<span data-ttu-id="6cb88-168">*deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-168">A *deps.json* file contains a list of dependencies, compilation dependencies and version information used to address assembly conflicts.</span></span> <span data-ttu-id="6cb88-169">이 파일에 대한 자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-169">For more details on this file, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-d|--diagnostics`

<span data-ttu-id="6cb88-170">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-170">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="6cb88-171">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-171">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="6cb88-172">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-172">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="6cb88-173">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-173">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="6cb88-174">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-174">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--runtimeconfig`

<span data-ttu-id="6cb88-175">*runtimeconfig.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-175">Path to a *runtimeconfig.json* file.</span></span>

<span data-ttu-id="6cb88-176">*runtimeconfig.json* 파일은 런타임 구성 설정을 포함하는 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-176">A *runtimeconfig.json* file is a configuration file containing runtime configuration settings.</span></span> <span data-ttu-id="6cb88-177">자세한 내용은 [GitHub에서 런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-177">For more details, see [Runtime Configuration Files on GitHub](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="6cb88-178">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-178">Sets the verbosity level of the command.</span></span> <span data-ttu-id="6cb88-179">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-179">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6cb88-180">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-180">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="6cb88-181">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-181">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="6cb88-182">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-182">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="6cb88-183">일반</span><span class="sxs-lookup"><span data-stu-id="6cb88-183">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cb88-184">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cb88-184">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="6cb88-185">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-185">Command</span></span>                                       | <span data-ttu-id="6cb88-186">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-186">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6cb88-187">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6cb88-187">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="6cb88-188">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-188">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6cb88-189">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="6cb88-189">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="6cb88-190">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-190">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="6cb88-191">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6cb88-191">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="6cb88-192">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-192">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="6cb88-193">dotnet help</span><span class="sxs-lookup"><span data-stu-id="6cb88-193">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="6cb88-194">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-194">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="6cb88-195">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6cb88-195">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="6cb88-196">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-196">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6cb88-197">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6cb88-197">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="6cb88-198">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-198">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6cb88-199">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6cb88-199">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="6cb88-200">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-200">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6cb88-201">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6cb88-201">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="6cb88-202">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-202">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6cb88-203">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6cb88-203">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="6cb88-204">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-204">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6cb88-205">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6cb88-205">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="6cb88-206">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-206">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6cb88-207">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6cb88-207">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="6cb88-208">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-208">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6cb88-209">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6cb88-209">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="6cb88-210">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-210">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6cb88-211">dotnet store</span><span class="sxs-lookup"><span data-stu-id="6cb88-211">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="6cb88-212">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-212">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="6cb88-213">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6cb88-213">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="6cb88-214">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-214">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cb88-215">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cb88-215">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="6cb88-216">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-216">Command</span></span>                             | <span data-ttu-id="6cb88-217">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-217">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6cb88-218">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6cb88-218">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="6cb88-219">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-219">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6cb88-220">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6cb88-220">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="6cb88-221">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-221">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="6cb88-222">dotnet help</span><span class="sxs-lookup"><span data-stu-id="6cb88-222">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="6cb88-223">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-223">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="6cb88-224">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6cb88-224">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="6cb88-225">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-225">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6cb88-226">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6cb88-226">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="6cb88-227">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-227">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6cb88-228">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6cb88-228">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="6cb88-229">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-229">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6cb88-230">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6cb88-230">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="6cb88-231">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-231">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6cb88-232">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6cb88-232">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="6cb88-233">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-233">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6cb88-234">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6cb88-234">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="6cb88-235">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-235">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6cb88-236">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6cb88-236">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="6cb88-237">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-237">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6cb88-238">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6cb88-238">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="6cb88-239">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-239">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6cb88-240">dotnet store</span><span class="sxs-lookup"><span data-stu-id="6cb88-240">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="6cb88-241">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-241">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="6cb88-242">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6cb88-242">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="6cb88-243">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-243">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cb88-244">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cb88-244">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="6cb88-245">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-245">Command</span></span>                             | <span data-ttu-id="6cb88-246">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-246">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="6cb88-247">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6cb88-247">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="6cb88-248">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-248">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="6cb88-249">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="6cb88-249">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="6cb88-250">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-250">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="6cb88-251">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="6cb88-251">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="6cb88-252">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-252">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="6cb88-253">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="6cb88-253">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="6cb88-254">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-254">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="6cb88-255">dotnet new</span><span class="sxs-lookup"><span data-stu-id="6cb88-255">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="6cb88-256">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-256">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="6cb88-257">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="6cb88-257">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="6cb88-258">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-258">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="6cb88-259">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="6cb88-259">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="6cb88-260">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-260">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="6cb88-261">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="6cb88-261">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="6cb88-262">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-262">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="6cb88-263">dotnet run</span><span class="sxs-lookup"><span data-stu-id="6cb88-263">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="6cb88-264">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-264">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="6cb88-265">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="6cb88-265">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="6cb88-266">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-266">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="6cb88-267">dotnet test</span><span class="sxs-lookup"><span data-stu-id="6cb88-267">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="6cb88-268">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-268">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="6cb88-269">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="6cb88-269">Project references</span></span>

<span data-ttu-id="6cb88-270">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-270">Command</span></span> | <span data-ttu-id="6cb88-271">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-271">Function</span></span>
--- | ---
[<span data-ttu-id="6cb88-272">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="6cb88-272">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="6cb88-273">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-273">Adds a project reference.</span></span>
[<span data-ttu-id="6cb88-274">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="6cb88-274">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="6cb88-275">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-275">Lists project references.</span></span>
[<span data-ttu-id="6cb88-276">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="6cb88-276">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="6cb88-277">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-277">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="6cb88-278">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="6cb88-278">NuGet packages</span></span>

<span data-ttu-id="6cb88-279">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-279">Command</span></span> | <span data-ttu-id="6cb88-280">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-280">Function</span></span>
--- | ---
[<span data-ttu-id="6cb88-281">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="6cb88-281">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="6cb88-282">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-282">Adds a NuGet package.</span></span>
[<span data-ttu-id="6cb88-283">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="6cb88-283">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="6cb88-284">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-284">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="6cb88-285">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-285">NuGet commands</span></span>

<span data-ttu-id="6cb88-286">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-286">Command</span></span> | <span data-ttu-id="6cb88-287">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-287">Function</span></span>
--- | ---
[<span data-ttu-id="6cb88-288">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="6cb88-288">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="6cb88-289">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-289">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="6cb88-290">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="6cb88-290">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="6cb88-291">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-291">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="6cb88-292">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="6cb88-292">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="6cb88-293">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-293">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="6cb88-294">전역 도구 명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-294">Global Tools commands</span></span>

<span data-ttu-id="6cb88-295">[.NET Core 전역 도구](global-tools.md)는 .NET Core SDK 2.1.300부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-295">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="6cb88-296">명령</span><span class="sxs-lookup"><span data-stu-id="6cb88-296">Command</span></span> | <span data-ttu-id="6cb88-297">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-297">Function</span></span>
--- | ---
[<span data-ttu-id="6cb88-298">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="6cb88-298">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="6cb88-299">컴퓨터에 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-299">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="6cb88-300">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="6cb88-300">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="6cb88-301">컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-301">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="6cb88-302">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="6cb88-302">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="6cb88-303">컴퓨터에서 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-303">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="6cb88-304">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="6cb88-304">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="6cb88-305">컴퓨터에서 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-305">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="6cb88-306">추가 도구</span><span class="sxs-lookup"><span data-stu-id="6cb88-306">Additional tools</span></span>

<span data-ttu-id="6cb88-307">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-307">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="6cb88-308">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-308">These tools are listed in the following table:</span></span>

| <span data-ttu-id="6cb88-309">도구</span><span class="sxs-lookup"><span data-stu-id="6cb88-309">Tool</span></span>                                              | <span data-ttu-id="6cb88-310">함수</span><span class="sxs-lookup"><span data-stu-id="6cb88-310">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="6cb88-311">dev-certs</span><span class="sxs-lookup"><span data-stu-id="6cb88-311">dev-certs</span></span>                                         | <span data-ttu-id="6cb88-312">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-312">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="6cb88-313">ef</span><span class="sxs-lookup"><span data-stu-id="6cb88-313">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="6cb88-314">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-314">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="6cb88-315">sql-cache</span><span class="sxs-lookup"><span data-stu-id="6cb88-315">sql-cache</span></span>                                         | <span data-ttu-id="6cb88-316">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-316">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="6cb88-317">user-secrets</span><span class="sxs-lookup"><span data-stu-id="6cb88-317">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="6cb88-318">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-318">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="6cb88-319">watch</span><span class="sxs-lookup"><span data-stu-id="6cb88-319">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="6cb88-320">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-320">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="6cb88-321">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-321">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="6cb88-322">예제</span><span class="sxs-lookup"><span data-stu-id="6cb88-322">Examples</span></span>

<span data-ttu-id="6cb88-323">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-323">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="6cb88-324">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-324">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="6cb88-325">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-325">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="6cb88-326">`myapp.dll`과 같은 애플리케이션 DLL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-326">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="6cb88-327">환경 변수</span><span class="sxs-lookup"><span data-stu-id="6cb88-327">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="6cb88-328">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6cb88-328">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="6cb88-329">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-329">The global packages folder.</span></span> <span data-ttu-id="6cb88-330">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-330">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="6cb88-331">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-331">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="6cb88-332">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-332">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6cb88-333">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-333">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="6cb88-334">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-334">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6cb88-335">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-335">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="6cb88-336">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-336">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="6cb88-337">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-337">If not set, it defaults to `true`.</span></span> <span data-ttu-id="6cb88-338">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-338">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="6cb88-339">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-339">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="6cb88-340">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-340">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="6cb88-341">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-341">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="6cb88-342">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="6cb88-342">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="6cb88-343">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-343">The primary package cache.</span></span> <span data-ttu-id="6cb88-344">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-344">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="6cb88-345">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-345">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="6cb88-346">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-346">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6cb88-347">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-347">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="6cb88-348">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-348">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6cb88-349">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-349">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="6cb88-350">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-350">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="6cb88-351">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-351">If not set, it defaults to `true`.</span></span> <span data-ttu-id="6cb88-352">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-352">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="6cb88-353">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cb88-353">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="6cb88-354">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="6cb88-354">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="6cb88-355">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-355">The primary package cache.</span></span> <span data-ttu-id="6cb88-356">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-356">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="6cb88-357">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-357">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="6cb88-358">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-358">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="6cb88-359">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-359">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="6cb88-360">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="6cb88-360">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="6cb88-361">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cb88-361">If not set, the default is `false` and the telemetry feature is active.</span></span>

---

## <a name="see-also"></a><span data-ttu-id="6cb88-362">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cb88-362">See also</span></span>

- [<span data-ttu-id="6cb88-363">런타임 구성 파일</span><span class="sxs-lookup"><span data-stu-id="6cb88-363">Runtime Configuration Files</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
