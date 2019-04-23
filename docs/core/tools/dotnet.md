---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 06/04/2018
ms.openlocfilehash: 5278adf44d12e428cdeacf1d475377ce9155c314
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59613007"
---
# <a name="dotnet-command"></a><span data-ttu-id="e0393-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="e0393-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e0393-104">name</span><span class="sxs-lookup"><span data-stu-id="e0393-104">Name</span></span>

<span data-ttu-id="e0393-105">`dotnet` - .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e0393-106">개요</span><span class="sxs-lookup"><span data-stu-id="e0393-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0393-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0393-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0393-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0393-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0393-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0393-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="e0393-110">설명</span><span class="sxs-lookup"><span data-stu-id="e0393-110">Description</span></span>

<span data-ttu-id="e0393-111">`dotnet`은 .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="e0393-112">[`dotnet build`](dotnet-build.md) 및 [`dotnet run`](dotnet-run.md)와 같은 특정 작업을 수행하는 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="e0393-113">각 명령은 자체 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-113">Each command defines its own arguments.</span></span> <span data-ttu-id="e0393-114">각 명령 다음에 `--help`를 입력하면 간단한 도움말 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="e0393-115">`dotnet`은 `dotnet myapp.dll`과 같은 애플리케이션 DLL을 지정하여 애플리케이션을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="e0393-116">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="e0393-117">옵션</span><span class="sxs-lookup"><span data-stu-id="e0393-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0393-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0393-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="e0393-119">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-119">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="e0393-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="e0393-121">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="e0393-122">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="e0393-123">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="e0393-124">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="e0393-125">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="e0393-126">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="e0393-127">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="e0393-128">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="e0393-129">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-129">`N` can be:</span></span>
* <span data-ttu-id="e0393-130">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="e0393-131">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="e0393-132">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-132">This is the default behavior.</span></span>
* <span data-ttu-id="e0393-133">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="e0393-134">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0393-135">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0393-136">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e0393-137">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="e0393-138">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0393-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0393-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="e0393-140">추가적인 *deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-140">Path to additional *deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="e0393-141">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="e0393-142">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="e0393-143">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="e0393-144">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="e0393-145">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="e0393-146">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="e0393-147">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="e0393-148">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0393-149">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0393-150">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e0393-151">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="e0393-152">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0393-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0393-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="e0393-154">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="e0393-155">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="e0393-156">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="e0393-157">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="e0393-158">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="e0393-159">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="e0393-160">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="e0393-161">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="e0393-162">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="e0393-163">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="e0393-164">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="e0393-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="e0393-165">일반</span><span class="sxs-lookup"><span data-stu-id="e0393-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0393-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0393-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="e0393-167">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-167">Command</span></span>                                       | <span data-ttu-id="e0393-168">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e0393-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e0393-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="e0393-170">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e0393-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="e0393-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="e0393-172">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="e0393-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e0393-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="e0393-174">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="e0393-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="e0393-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="e0393-176">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="e0393-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e0393-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="e0393-178">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e0393-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e0393-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="e0393-180">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e0393-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0393-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="e0393-182">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e0393-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e0393-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="e0393-184">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e0393-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e0393-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="e0393-186">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e0393-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e0393-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="e0393-188">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e0393-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0393-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="e0393-190">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e0393-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e0393-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="e0393-192">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e0393-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e0393-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="e0393-194">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="e0393-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e0393-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="e0393-196">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0393-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0393-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="e0393-198">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-198">Command</span></span>                             | <span data-ttu-id="e0393-199">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e0393-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e0393-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="e0393-201">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e0393-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e0393-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="e0393-203">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="e0393-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="e0393-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="e0393-205">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="e0393-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e0393-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="e0393-207">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e0393-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e0393-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="e0393-209">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e0393-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0393-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="e0393-211">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e0393-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e0393-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="e0393-213">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e0393-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e0393-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="e0393-215">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e0393-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e0393-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="e0393-217">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e0393-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0393-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="e0393-219">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e0393-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e0393-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="e0393-221">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e0393-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="e0393-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="e0393-223">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="e0393-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e0393-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="e0393-225">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0393-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0393-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="e0393-227">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-227">Command</span></span>                             | <span data-ttu-id="e0393-228">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="e0393-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="e0393-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="e0393-230">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="e0393-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="e0393-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="e0393-232">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="e0393-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="e0393-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="e0393-234">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="e0393-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="e0393-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="e0393-236">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="e0393-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0393-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="e0393-238">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="e0393-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="e0393-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="e0393-240">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="e0393-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="e0393-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="e0393-242">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="e0393-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="e0393-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="e0393-244">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="e0393-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="e0393-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="e0393-246">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="e0393-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="e0393-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="e0393-248">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="e0393-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="e0393-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="e0393-250">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="e0393-251">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="e0393-251">Project references</span></span>

<span data-ttu-id="e0393-252">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-252">Command</span></span> | <span data-ttu-id="e0393-253">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-253">Function</span></span>
--- | ---
[<span data-ttu-id="e0393-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="e0393-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="e0393-255">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-255">Adds a project reference.</span></span>
[<span data-ttu-id="e0393-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="e0393-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="e0393-257">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-257">Lists project references.</span></span>
[<span data-ttu-id="e0393-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="e0393-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="e0393-259">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="e0393-260">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="e0393-260">NuGet packages</span></span>

<span data-ttu-id="e0393-261">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-261">Command</span></span> | <span data-ttu-id="e0393-262">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-262">Function</span></span>
--- | ---
[<span data-ttu-id="e0393-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="e0393-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="e0393-264">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="e0393-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="e0393-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="e0393-266">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="e0393-267">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="e0393-267">NuGet commands</span></span>

<span data-ttu-id="e0393-268">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-268">Command</span></span> | <span data-ttu-id="e0393-269">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-269">Function</span></span>
--- | ---
[<span data-ttu-id="e0393-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="e0393-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="e0393-271">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="e0393-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="e0393-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="e0393-273">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="e0393-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="e0393-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="e0393-275">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="e0393-276">전역 도구 명령</span><span class="sxs-lookup"><span data-stu-id="e0393-276">Global Tools commands</span></span>

<span data-ttu-id="e0393-277">[.NET Core 전역 도구](global-tools.md)는 .NET Core SDK 2.1.300부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="e0393-278">명령</span><span class="sxs-lookup"><span data-stu-id="e0393-278">Command</span></span> | <span data-ttu-id="e0393-279">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-279">Function</span></span>
--- | ---
[<span data-ttu-id="e0393-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="e0393-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="e0393-281">컴퓨터에 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="e0393-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="e0393-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="e0393-283">컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="e0393-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="e0393-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="e0393-285">컴퓨터에서 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="e0393-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="e0393-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="e0393-287">컴퓨터에서 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="e0393-288">추가 도구</span><span class="sxs-lookup"><span data-stu-id="e0393-288">Additional tools</span></span>

<span data-ttu-id="e0393-289">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="e0393-290">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="e0393-291">도구</span><span class="sxs-lookup"><span data-stu-id="e0393-291">Tool</span></span>                                              | <span data-ttu-id="e0393-292">함수</span><span class="sxs-lookup"><span data-stu-id="e0393-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="e0393-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="e0393-293">dev-certs</span></span>                                         | <span data-ttu-id="e0393-294">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="e0393-295">ef</span><span class="sxs-lookup"><span data-stu-id="e0393-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="e0393-296">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="e0393-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="e0393-297">sql-cache</span></span>                                         | <span data-ttu-id="e0393-298">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="e0393-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="e0393-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="e0393-300">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="e0393-301">watch</span><span class="sxs-lookup"><span data-stu-id="e0393-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="e0393-302">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="e0393-303">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="e0393-304">예제</span><span class="sxs-lookup"><span data-stu-id="e0393-304">Examples</span></span>

<span data-ttu-id="e0393-305">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="e0393-306">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="e0393-307">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="e0393-308">`myapp.dll`과 같은 애플리케이션 DLL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="e0393-309">환경 변수</span><span class="sxs-lookup"><span data-stu-id="e0393-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0393-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0393-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="e0393-311">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-311">The primary package cache.</span></span> <span data-ttu-id="e0393-312">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-312">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="e0393-313">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="e0393-314">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e0393-315">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="e0393-316">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e0393-317">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="e0393-318">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="e0393-319">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="e0393-320">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="e0393-321">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="e0393-322">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="e0393-323">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0393-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0393-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="e0393-325">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-325">The primary package cache.</span></span> <span data-ttu-id="e0393-326">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="e0393-327">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="e0393-328">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e0393-329">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="e0393-330">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e0393-331">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="e0393-332">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="e0393-333">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="e0393-334">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="e0393-335">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e0393-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0393-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0393-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="e0393-337">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-337">The primary package cache.</span></span> <span data-ttu-id="e0393-338">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%HOME%\NuGet\Packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%HOME%\NuGet\Packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="e0393-339">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="e0393-340">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="e0393-341">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="e0393-342">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="e0393-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="e0393-343">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0393-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
