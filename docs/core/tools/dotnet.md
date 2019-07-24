---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI 도구에 대한 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 06/04/2018
ms.openlocfilehash: e1571bea1594b492427bdf5b3a7959733459c54e
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331017"
---
# <a name="dotnet-command"></a><span data-ttu-id="2dabf-103">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-103">dotnet command</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2dabf-104">name</span><span class="sxs-lookup"><span data-stu-id="2dabf-104">Name</span></span>

<span data-ttu-id="2dabf-105">`dotnet` - .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-105">`dotnet` - A tool for managing .NET source code and binaries.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2dabf-106">개요</span><span class="sxs-lookup"><span data-stu-id="2dabf-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2dabf-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2dabf-107">.NET Core 2.1</span></span>](#tab/netcore21)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2dabf-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2dabf-108">.NET Core 2.0</span></span>](#tab/netcore20)

```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2dabf-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2dabf-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```

---

## <a name="description"></a><span data-ttu-id="2dabf-110">설명</span><span class="sxs-lookup"><span data-stu-id="2dabf-110">Description</span></span>

<span data-ttu-id="2dabf-111">`dotnet`은 .NET 소스 코드 및 이진 파일을 관리하기 위한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-111">`dotnet` is a tool for managing .NET source code and binaries.</span></span> <span data-ttu-id="2dabf-112">[`dotnet build`](dotnet-build.md) 및 [`dotnet run`](dotnet-run.md)와 같은 특정 작업을 수행하는 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-112">It exposes commands that perform specific tasks, such as [`dotnet build`](dotnet-build.md) and [`dotnet run`](dotnet-run.md).</span></span> <span data-ttu-id="2dabf-113">각 명령은 자체 인수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-113">Each command defines its own arguments.</span></span> <span data-ttu-id="2dabf-114">각 명령 다음에 `--help`를 입력하면 간단한 도움말 설명서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-114">Type `--help` after each command to access brief help documentation.</span></span>

<span data-ttu-id="2dabf-115">`dotnet`은 `dotnet myapp.dll`과 같은 애플리케이션 DLL을 지정하여 애플리케이션을 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-115">`dotnet` can be used to run applications, by specifying an application DLL, such as `dotnet myapp.dll`.</span></span> <span data-ttu-id="2dabf-116">배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-116">See [.NET Core application deployment](../deploying/index.md) for to learn about deployment options.</span></span>

## <a name="options"></a><span data-ttu-id="2dabf-117">옵션</span><span class="sxs-lookup"><span data-stu-id="2dabf-117">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2dabf-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2dabf-118">.NET Core 2.1</span></span>](#tab/netcore21)

`--additional-deps <PATH>`

<span data-ttu-id="2dabf-119">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-119">Path to additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2dabf-120">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-120">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2dabf-121">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-121">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2dabf-122">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-122">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2dabf-123">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-123">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2dabf-124">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-124">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2dabf-125">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-125">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--list-runtimes`

<span data-ttu-id="2dabf-126">설치된 .NET Core 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-126">Displays the installed .NET Core runtimes.</span></span>

`--list-sdks`

<span data-ttu-id="2dabf-127">설치된 .NET Core SDK를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-127">Displays the installed .NET Core SDKs.</span></span>

`--roll-forward-on-no-candidate-fx <N>`

<span data-ttu-id="2dabf-128">필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-128">Defines behavior when the required shared framework is not available.</span></span> <span data-ttu-id="2dabf-129">`N`는 다음이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-129">`N` can be:</span></span>
* <span data-ttu-id="2dabf-130">`0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-130">`0` - Disable even minor version roll forward.</span></span>
* <span data-ttu-id="2dabf-131">`1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-131">`1` - Roll forward on minor version, but not on major version.</span></span> <span data-ttu-id="2dabf-132">이것은 기본적인 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-132">This is the default behavior.</span></span>
* <span data-ttu-id="2dabf-133">`2` - 부 버전과 주 버전에서 롤포워드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-133">`2` - Roll forward on minor and major versions.</span></span>

 <span data-ttu-id="2dabf-134">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-134">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2dabf-135">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-135">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2dabf-136">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-136">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2dabf-137">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-137">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2dabf-138">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-138">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2dabf-139">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2dabf-139">.NET Core 2.0</span></span>](#tab/netcore20)

`--additional-deps <PATH>`

<span data-ttu-id="2dabf-140">추가적인 *.deps.json* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-140">Path to additional *.deps.json* file.</span></span>

`--additionalprobingpath <PATH>`

<span data-ttu-id="2dabf-141">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-141">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2dabf-142">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-142">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2dabf-143">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-143">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2dabf-144">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-144">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2dabf-145">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-145">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2dabf-146">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-146">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`--roll-forward-on-no-candidate-fx`

 <span data-ttu-id="2dabf-147">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-147">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2dabf-148">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-148">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2dabf-149">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-149">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2dabf-150">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-150">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2dabf-151">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-151">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2dabf-152">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-152">Prints out the version of the .NET Core SDK in use.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2dabf-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2dabf-153">.NET Core 1.x</span></span>](#tab/netcore1x)

`--additionalprobingpath <PATH>`

<span data-ttu-id="2dabf-154">검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-154">Path containing probing policy and assemblies to probe.</span></span>

`-d|--diagnostics`

<span data-ttu-id="2dabf-155">진단 출력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-155">Enables diagnostic output.</span></span>

`--fx-version <VERSION>`

<span data-ttu-id="2dabf-156">애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-156">Version of the .NET Core runtime to use to run the application.</span></span>

`-h|--help`

<span data-ttu-id="2dabf-157">`dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-157">Prints out documentation for a given command, such as `dotnet build --help`.</span></span> <span data-ttu-id="2dabf-158">`dotnet --help`는 사용 가능한 명령 목록을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-158">`dotnet --help` prints a list of available commands.</span></span>

`--info`

<span data-ttu-id="2dabf-159">.NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-159">Prints out detailed information about a .NET Core installation and the machine environment, such as the current operating system, and commit SHA of the .NET Core version.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="2dabf-160">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2dabf-161">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="2dabf-162">모든 명령에서 지원되지 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-162">Not supported in every command; see specific command page to determine if this option is available.</span></span>

`--version`

<span data-ttu-id="2dabf-163">사용 중인 .NET Core SDK 버전을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-163">Prints out the version of the .NET Core SDK in use.</span></span>

---

## <a name="dotnet-commands"></a><span data-ttu-id="2dabf-164">dotnet 명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-164">dotnet commands</span></span>

### <a name="general"></a><span data-ttu-id="2dabf-165">일반</span><span class="sxs-lookup"><span data-stu-id="2dabf-165">General</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2dabf-166">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2dabf-166">.NET Core 2.1</span></span>](#tab/netcore21)

| <span data-ttu-id="2dabf-167">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-167">Command</span></span>                                       | <span data-ttu-id="2dabf-168">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-168">Function</span></span>                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2dabf-169">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2dabf-169">dotnet build</span></span>](dotnet-build.md)               | <span data-ttu-id="2dabf-170">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-170">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2dabf-171">dotnet build-server</span><span class="sxs-lookup"><span data-stu-id="2dabf-171">dotnet build-server</span></span>](dotnet-build-server.md) | <span data-ttu-id="2dabf-172">빌드에서 시작된 서버와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-172">Interacts with servers started by a build.</span></span>                          |
| [<span data-ttu-id="2dabf-173">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2dabf-173">dotnet clean</span></span>](dotnet-clean.md)               | <span data-ttu-id="2dabf-174">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-174">Clean build outputs.</span></span>                                                |
| [<span data-ttu-id="2dabf-175">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2dabf-175">dotnet help</span></span>](dotnet-help.md)                 | <span data-ttu-id="2dabf-176">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-176">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2dabf-177">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2dabf-177">dotnet migrate</span></span>](dotnet-migrate.md)           | <span data-ttu-id="2dabf-178">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-178">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2dabf-179">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2dabf-179">dotnet msbuild</span></span>](dotnet-msbuild.md)           | <span data-ttu-id="2dabf-180">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-180">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2dabf-181">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2dabf-181">dotnet new</span></span>](dotnet-new.md)                   | <span data-ttu-id="2dabf-182">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-182">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2dabf-183">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2dabf-183">dotnet pack</span></span>](dotnet-pack.md)                 | <span data-ttu-id="2dabf-184">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-184">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2dabf-185">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2dabf-185">dotnet publish</span></span>](dotnet-publish.md)           | <span data-ttu-id="2dabf-186">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-186">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2dabf-187">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2dabf-187">dotnet restore</span></span>](dotnet-restore.md)           | <span data-ttu-id="2dabf-188">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-188">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2dabf-189">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2dabf-189">dotnet run</span></span>](dotnet-run.md)                   | <span data-ttu-id="2dabf-190">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-190">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2dabf-191">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2dabf-191">dotnet sln</span></span>](dotnet-sln.md)                   | <span data-ttu-id="2dabf-192">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-192">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2dabf-193">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2dabf-193">dotnet store</span></span>](dotnet-store.md)               | <span data-ttu-id="2dabf-194">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-194">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2dabf-195">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2dabf-195">dotnet test</span></span>](dotnet-test.md)                 | <span data-ttu-id="2dabf-196">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-196">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2dabf-197">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2dabf-197">.NET Core 2.0</span></span>](#tab/netcore20)

| <span data-ttu-id="2dabf-198">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-198">Command</span></span>                             | <span data-ttu-id="2dabf-199">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-199">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2dabf-200">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2dabf-200">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2dabf-201">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-201">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2dabf-202">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2dabf-202">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2dabf-203">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-203">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2dabf-204">dotnet help</span><span class="sxs-lookup"><span data-stu-id="2dabf-204">dotnet help</span></span>](dotnet-help.md)       | <span data-ttu-id="2dabf-205">명령에 대한 자세한 온라인 설명서를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-205">Shows more detailed documentation online for the command.</span></span>           |
| [<span data-ttu-id="2dabf-206">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2dabf-206">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2dabf-207">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-207">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2dabf-208">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2dabf-208">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2dabf-209">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-209">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2dabf-210">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2dabf-210">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2dabf-211">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-211">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2dabf-212">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2dabf-212">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2dabf-213">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-213">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2dabf-214">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2dabf-214">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2dabf-215">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-215">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2dabf-216">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2dabf-216">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2dabf-217">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-217">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2dabf-218">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2dabf-218">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2dabf-219">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-219">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2dabf-220">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2dabf-220">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2dabf-221">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-221">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2dabf-222">dotnet store</span><span class="sxs-lookup"><span data-stu-id="2dabf-222">dotnet store</span></span>](dotnet-store.md)     | <span data-ttu-id="2dabf-223">어셈블리를 런타임 패키지 저장소에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-223">Stores assemblies in the runtime package store.</span></span>                     |
| [<span data-ttu-id="2dabf-224">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2dabf-224">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2dabf-225">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-225">Runs tests using a test runner.</span></span>                                     |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2dabf-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2dabf-226">.NET Core 1.x</span></span>](#tab/netcore1x)

| <span data-ttu-id="2dabf-227">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-227">Command</span></span>                             | <span data-ttu-id="2dabf-228">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-228">Function</span></span>                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [<span data-ttu-id="2dabf-229">dotnet build</span><span class="sxs-lookup"><span data-stu-id="2dabf-229">dotnet build</span></span>](dotnet-build.md)     | <span data-ttu-id="2dabf-230">.NET Core 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-230">Builds a .NET Core application.</span></span>                                     |
| [<span data-ttu-id="2dabf-231">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="2dabf-231">dotnet clean</span></span>](dotnet-clean.md)     | <span data-ttu-id="2dabf-232">빌드 출력을 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-232">Clean build outputs.</span></span>                                              |
| [<span data-ttu-id="2dabf-233">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="2dabf-233">dotnet migrate</span></span>](dotnet-migrate.md) | <span data-ttu-id="2dabf-234">유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-234">Migrates a valid Preview 2 project to a .NET Core SDK 1.0 project.</span></span>  |
| [<span data-ttu-id="2dabf-235">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="2dabf-235">dotnet msbuild</span></span>](dotnet-msbuild.md) | <span data-ttu-id="2dabf-236">MSBuild 명령줄에 대한 액세스 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-236">Provides access to the MSBuild command line.</span></span>                        |
| [<span data-ttu-id="2dabf-237">dotnet new</span><span class="sxs-lookup"><span data-stu-id="2dabf-237">dotnet new</span></span>](dotnet-new.md)         | <span data-ttu-id="2dabf-238">지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-238">Initializes a C# or F# project for a given template.</span></span>                |
| [<span data-ttu-id="2dabf-239">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2dabf-239">dotnet pack</span></span>](dotnet-pack.md)       | <span data-ttu-id="2dabf-240">코드의 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-240">Creates a NuGet package of your code.</span></span>                               |
| [<span data-ttu-id="2dabf-241">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="2dabf-241">dotnet publish</span></span>](dotnet-publish.md) | <span data-ttu-id="2dabf-242">.NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-242">Publishes a .NET framework-dependent or self-contained application.</span></span> |
| [<span data-ttu-id="2dabf-243">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="2dabf-243">dotnet restore</span></span>](dotnet-restore.md) | <span data-ttu-id="2dabf-244">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-244">Restores the dependencies for a given application.</span></span>                  |
| [<span data-ttu-id="2dabf-245">dotnet run</span><span class="sxs-lookup"><span data-stu-id="2dabf-245">dotnet run</span></span>](dotnet-run.md)         | <span data-ttu-id="2dabf-246">소스에서 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-246">Runs the application from source.</span></span>                                   |
| [<span data-ttu-id="2dabf-247">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="2dabf-247">dotnet sln</span></span>](dotnet-sln.md)         | <span data-ttu-id="2dabf-248">솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-248">Options to add, remove, and list projects in a solution file.</span></span>       |
| [<span data-ttu-id="2dabf-249">dotnet test</span><span class="sxs-lookup"><span data-stu-id="2dabf-249">dotnet test</span></span>](dotnet-test.md)       | <span data-ttu-id="2dabf-250">Test Runner를 사용하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-250">Runs tests using a test runner.</span></span>                                     |

---

### <a name="project-references"></a><span data-ttu-id="2dabf-251">프로젝트 참조</span><span class="sxs-lookup"><span data-stu-id="2dabf-251">Project references</span></span>

<span data-ttu-id="2dabf-252">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-252">Command</span></span> | <span data-ttu-id="2dabf-253">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-253">Function</span></span>
--- | ---
[<span data-ttu-id="2dabf-254">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="2dabf-254">dotnet add reference</span></span>](dotnet-add-reference.md) | <span data-ttu-id="2dabf-255">프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-255">Adds a project reference.</span></span>
[<span data-ttu-id="2dabf-256">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2dabf-256">dotnet list reference</span></span>](dotnet-list-reference.md) | <span data-ttu-id="2dabf-257">프로젝트 참조를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-257">Lists project references.</span></span>
[<span data-ttu-id="2dabf-258">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="2dabf-258">dotnet remove reference</span></span>](dotnet-remove-reference.md) | <span data-ttu-id="2dabf-259">프로젝트 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-259">Removes a project reference.</span></span>

### <a name="nuget-packages"></a><span data-ttu-id="2dabf-260">NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="2dabf-260">NuGet packages</span></span>

<span data-ttu-id="2dabf-261">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-261">Command</span></span> | <span data-ttu-id="2dabf-262">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-262">Function</span></span>
--- | ---
[<span data-ttu-id="2dabf-263">dotnet add package</span><span class="sxs-lookup"><span data-stu-id="2dabf-263">dotnet add package</span></span>](dotnet-add-package.md) | <span data-ttu-id="2dabf-264">NuGet 패키지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-264">Adds a NuGet package.</span></span>
[<span data-ttu-id="2dabf-265">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="2dabf-265">dotnet remove package</span></span>](dotnet-remove-package.md) | <span data-ttu-id="2dabf-266">NuGet 패키지를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-266">Removes a NuGet package.</span></span>

### <a name="nuget-commands"></a><span data-ttu-id="2dabf-267">NuGet 명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-267">NuGet commands</span></span>

<span data-ttu-id="2dabf-268">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-268">Command</span></span> | <span data-ttu-id="2dabf-269">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-269">Function</span></span>
--- | ---
[<span data-ttu-id="2dabf-270">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="2dabf-270">dotnet nuget delete</span></span>](dotnet-nuget-delete.md) | <span data-ttu-id="2dabf-271">서버에서 패키지를 삭제하거나 목록에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-271">Deletes or unlists a package from the server.</span></span>
[<span data-ttu-id="2dabf-272">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="2dabf-272">dotnet nuget locals</span></span>](dotnet-nuget-locals.md) | <span data-ttu-id="2dabf-273">http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-273">Clears or lists local NuGet resources such as http-request cache, temporary cache, or machine-wide global packages folder.</span></span>
[<span data-ttu-id="2dabf-274">dotnet nuget push</span><span class="sxs-lookup"><span data-stu-id="2dabf-274">dotnet nuget push</span></span>](dotnet-nuget-push.md) | <span data-ttu-id="2dabf-275">서버에 패키지를 푸시하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-275">Pushes a package to the server and publishes it.</span></span>

### <a name="global-tools-commands"></a><span data-ttu-id="2dabf-276">전역 도구 명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-276">Global Tools commands</span></span>

<span data-ttu-id="2dabf-277">[.NET Core 전역 도구](global-tools.md)는 .NET Core SDK 2.1.300부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-277">[.NET Core Global Tools](global-tools.md) are available starting with .NET Core SDK 2.1.300:</span></span>

<span data-ttu-id="2dabf-278">명령</span><span class="sxs-lookup"><span data-stu-id="2dabf-278">Command</span></span> | <span data-ttu-id="2dabf-279">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-279">Function</span></span>
--- | ---
[<span data-ttu-id="2dabf-280">dotnet tool install</span><span class="sxs-lookup"><span data-stu-id="2dabf-280">dotnet tool install</span></span>](dotnet-tool-install.md) | <span data-ttu-id="2dabf-281">컴퓨터에 전역 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-281">Installs a Global Tool on your machine.</span></span>
[<span data-ttu-id="2dabf-282">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="2dabf-282">dotnet tool list</span></span>](dotnet-tool-list.md) | <span data-ttu-id="2dabf-283">컴퓨터의 기본 디렉터리 또는 지정된 경로에 현재 설치된 모든 전역 도구를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-283">Lists all Global Tools currently installed in the default directory on your machine or in the specified path.</span></span>
[<span data-ttu-id="2dabf-284">dotnet tool uninstall</span><span class="sxs-lookup"><span data-stu-id="2dabf-284">dotnet tool uninstall</span></span>](dotnet-tool-uninstall.md) | <span data-ttu-id="2dabf-285">컴퓨터에서 전역 도구를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-285">Uninstalls a Global Tool from your machine.</span></span>
[<span data-ttu-id="2dabf-286">dotnet tool update</span><span class="sxs-lookup"><span data-stu-id="2dabf-286">dotnet tool update</span></span>](dotnet-tool-update.md) | <span data-ttu-id="2dabf-287">컴퓨터에서 전역 도구를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-287">Updates a Global Tool on your machine.</span></span>

### <a name="additional-tools"></a><span data-ttu-id="2dabf-288">추가 도구</span><span class="sxs-lookup"><span data-stu-id="2dabf-288">Additional tools</span></span>

<span data-ttu-id="2dabf-289">.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-289">Starting with .NET Core SDK 2.1.300, a number of tools that were available only on a per project basis using `DotnetCliToolReference` are now available as part of the .NET Core SDK.</span></span> <span data-ttu-id="2dabf-290">이러한 도구는 다음 표에 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-290">These tools are listed in the following table:</span></span>

| <span data-ttu-id="2dabf-291">도구</span><span class="sxs-lookup"><span data-stu-id="2dabf-291">Tool</span></span>                                              | <span data-ttu-id="2dabf-292">함수</span><span class="sxs-lookup"><span data-stu-id="2dabf-292">Function</span></span>                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| <span data-ttu-id="2dabf-293">dev-certs</span><span class="sxs-lookup"><span data-stu-id="2dabf-293">dev-certs</span></span>                                         | <span data-ttu-id="2dabf-294">개발 인증서를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-294">Creates and manages development certificates.</span></span>                |
| [<span data-ttu-id="2dabf-295">ef</span><span class="sxs-lookup"><span data-stu-id="2dabf-295">ef</span></span>](/ef/core/miscellaneous/cli/dotnet)           | <span data-ttu-id="2dabf-296">Entity Framework Core 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-296">Entity Framework Core command-line tools.</span></span>                    |
| <span data-ttu-id="2dabf-297">sql-cache</span><span class="sxs-lookup"><span data-stu-id="2dabf-297">sql-cache</span></span>                                         | <span data-ttu-id="2dabf-298">SQL Server 캐시 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-298">SQL Server cache command-line tools.</span></span>                         |
| [<span data-ttu-id="2dabf-299">user-secrets</span><span class="sxs-lookup"><span data-stu-id="2dabf-299">user-secrets</span></span>](/aspnet/core/security/app-secrets) | <span data-ttu-id="2dabf-300">개발 사용자 비밀을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-300">Manages development user secrets.</span></span>                            |
| [<span data-ttu-id="2dabf-301">watch</span><span class="sxs-lookup"><span data-stu-id="2dabf-301">watch</span></span>](/aspnet/core/tutorials/dotnet-watch)      | <span data-ttu-id="2dabf-302">파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-302">Starts a file watcher that runs a command when files change.</span></span> |

<span data-ttu-id="2dabf-303">각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-303">For more information about each tool, type `dotnet <tool-name> --help`.</span></span>

## <a name="examples"></a><span data-ttu-id="2dabf-304">예제</span><span class="sxs-lookup"><span data-stu-id="2dabf-304">Examples</span></span>

<span data-ttu-id="2dabf-305">새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-305">Creates a new .NET Core console application:</span></span>

`dotnet new console`

<span data-ttu-id="2dabf-306">지정된 애플리케이션에 대한 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-306">Restore dependencies for a given application:</span></span>

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="2dabf-307">지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-307">Build a project and its dependencies in a given directory:</span></span>

`dotnet build`

<span data-ttu-id="2dabf-308">`myapp.dll`과 같은 애플리케이션 DLL을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-308">Run an application DLL, such as `myapp.dll`:</span></span>

`dotnet myapp.dll`

## <a name="environment-variables"></a><span data-ttu-id="2dabf-309">환경 변수</span><span class="sxs-lookup"><span data-stu-id="2dabf-309">Environment variables</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="2dabf-310">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2dabf-310">.NET Core 2.1</span></span>](#tab/netcore21)

`DOTNET_PACKAGES`

<span data-ttu-id="2dabf-311">글로벌 패키지 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-311">The global packages folder.</span></span> <span data-ttu-id="2dabf-312">설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-312">If not set, it defaults to `~/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2dabf-313">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-313">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2dabf-314">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-314">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2dabf-315">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-315">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2dabf-316">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-316">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2dabf-317">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-317">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2dabf-318">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-318">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2dabf-319">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-319">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2dabf-320">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-320">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2dabf-321">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-321">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

<span data-ttu-id="2dabf-322">`0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-322">Disables minor version roll forward, if set to `0`.</span></span> <span data-ttu-id="2dabf-323">자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-323">For more information, see [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="2dabf-324">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="2dabf-324">.NET Core 2.0</span></span>](#tab/netcore20)

`DOTNET_PACKAGES`

<span data-ttu-id="2dabf-325">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-325">The primary package cache.</span></span> <span data-ttu-id="2dabf-326">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-326">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2dabf-327">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-327">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2dabf-328">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-328">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2dabf-329">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-329">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2dabf-330">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-330">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2dabf-331">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-331">If not set, the default is `false` and the telemetry feature is active.</span></span>

`DOTNET_MULTILEVEL_LOOKUP`

<span data-ttu-id="2dabf-332">전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-332">Specifies whether .NET Core runtime, shared framework, or SDK are resolved from the global location.</span></span> <span data-ttu-id="2dabf-333">설정하지 않은 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-333">If not set, it defaults to `true`.</span></span> <span data-ttu-id="2dabf-334">전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 가지려면 `false`로 설정합니다(값 `0` 또는 `false`는 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-334">Set to `false` to not resolve from the global location and have isolated .NET Core installations (values `0` or `false` are accepted).</span></span> <span data-ttu-id="2dabf-335">다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dabf-335">For more information about multi-level lookup, see [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="2dabf-336">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="2dabf-336">.NET Core 1.x</span></span>](#tab/netcore1x)

`DOTNET_PACKAGES`

<span data-ttu-id="2dabf-337">주 패키지 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-337">The primary package cache.</span></span> <span data-ttu-id="2dabf-338">설정하지 않으면 기본적으로 Unix에서는 `$HOME/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-338">If not set, it defaults to `$HOME/.nuget/packages` on Unix or `%userprofile%\.nuget\packages` on Windows.</span></span>

`DOTNET_SERVICING`

<span data-ttu-id="2dabf-339">런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-339">Specifies the location of the servicing index to use by the shared host when loading the runtime.</span></span>

`DOTNET_CLI_TELEMETRY_OPTOUT`

<span data-ttu-id="2dabf-340">.NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-340">Specifies whether data about the .NET Core tools usage is collected and sent to Microsoft.</span></span> <span data-ttu-id="2dabf-341">원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-341">Set to `true` to opt-out of the telemetry feature (values `true`, `1`, or `yes` accepted).</span></span> <span data-ttu-id="2dabf-342">이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨).</span><span class="sxs-lookup"><span data-stu-id="2dabf-342">Otherwise, set to `false` to opt into the telemetry features (values `false`, `0`, or `no` accepted).</span></span> <span data-ttu-id="2dabf-343">설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dabf-343">If not set, the default is `false` and the telemetry feature is active.</span></span>

---
