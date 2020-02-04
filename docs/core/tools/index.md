---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 및 해당 기능에 대한 개요입니다.
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920486"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="4cd0c-103">.NET Core CLI 개요</span><span class="sxs-lookup"><span data-stu-id="4cd0c-103">.NET Core CLI overview</span></span>

<span data-ttu-id="4cd0c-104">.NET Core CLI(명령줄 인터페이스)는 .NET Core 애플리케이션의 개발, 빌드, 실행 및 게시에 사용되는 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-104">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="4cd0c-105">.NET Core CLI는 [.NET Core SDK](../sdk.md)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-105">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="4cd0c-106">.NET Core SDK를 설치하는 방법에 대한 자세한 내용은 [.NET Core SDK 설치](../install/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-106">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="4cd0c-107">CLI 명령</span><span class="sxs-lookup"><span data-stu-id="4cd0c-107">CLI commands</span></span>

<span data-ttu-id="4cd0c-108">다음은 기본적으로 설치되는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-108">The following commands are installed by default:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4cd0c-109">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4cd0c-109">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4cd0c-110">**기본 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-110">**Basic commands**</span></span>

- [<span data-ttu-id="4cd0c-111">new</span><span class="sxs-lookup"><span data-stu-id="4cd0c-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="4cd0c-112">restore</span><span class="sxs-lookup"><span data-stu-id="4cd0c-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="4cd0c-113">build</span><span class="sxs-lookup"><span data-stu-id="4cd0c-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="4cd0c-114">publish</span><span class="sxs-lookup"><span data-stu-id="4cd0c-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="4cd0c-115">run</span><span class="sxs-lookup"><span data-stu-id="4cd0c-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="4cd0c-116">test</span><span class="sxs-lookup"><span data-stu-id="4cd0c-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="4cd0c-117">vstest</span><span class="sxs-lookup"><span data-stu-id="4cd0c-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="4cd0c-118">pack</span><span class="sxs-lookup"><span data-stu-id="4cd0c-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="4cd0c-119">migrate</span><span class="sxs-lookup"><span data-stu-id="4cd0c-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="4cd0c-120">clean</span><span class="sxs-lookup"><span data-stu-id="4cd0c-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="4cd0c-121">sln</span><span class="sxs-lookup"><span data-stu-id="4cd0c-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="4cd0c-122">help</span><span class="sxs-lookup"><span data-stu-id="4cd0c-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="4cd0c-123">store</span><span class="sxs-lookup"><span data-stu-id="4cd0c-123">store</span></span>](dotnet-store.md)

<span data-ttu-id="4cd0c-124">**프로젝트 수정 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-124">**Project modification commands**</span></span>

- [<span data-ttu-id="4cd0c-125">add package</span><span class="sxs-lookup"><span data-stu-id="4cd0c-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="4cd0c-126">add reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="4cd0c-127">remove package</span><span class="sxs-lookup"><span data-stu-id="4cd0c-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="4cd0c-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="4cd0c-129">list reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-129">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="4cd0c-130">**고급 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-130">**Advanced commands**</span></span>

- [<span data-ttu-id="4cd0c-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="4cd0c-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="4cd0c-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="4cd0c-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="4cd0c-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="4cd0c-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="4cd0c-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="4cd0c-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="4cd0c-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="4cd0c-135">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4cd0c-136">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4cd0c-136">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4cd0c-137">**기본 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-137">**Basic commands**</span></span>

- [<span data-ttu-id="4cd0c-138">new</span><span class="sxs-lookup"><span data-stu-id="4cd0c-138">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="4cd0c-139">restore</span><span class="sxs-lookup"><span data-stu-id="4cd0c-139">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="4cd0c-140">build</span><span class="sxs-lookup"><span data-stu-id="4cd0c-140">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="4cd0c-141">publish</span><span class="sxs-lookup"><span data-stu-id="4cd0c-141">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="4cd0c-142">run</span><span class="sxs-lookup"><span data-stu-id="4cd0c-142">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="4cd0c-143">test</span><span class="sxs-lookup"><span data-stu-id="4cd0c-143">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="4cd0c-144">vstest</span><span class="sxs-lookup"><span data-stu-id="4cd0c-144">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="4cd0c-145">pack</span><span class="sxs-lookup"><span data-stu-id="4cd0c-145">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="4cd0c-146">migrate</span><span class="sxs-lookup"><span data-stu-id="4cd0c-146">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="4cd0c-147">clean</span><span class="sxs-lookup"><span data-stu-id="4cd0c-147">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="4cd0c-148">sln</span><span class="sxs-lookup"><span data-stu-id="4cd0c-148">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="4cd0c-149">**프로젝트 수정 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-149">**Project modification commands**</span></span>

- [<span data-ttu-id="4cd0c-150">add package</span><span class="sxs-lookup"><span data-stu-id="4cd0c-150">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="4cd0c-151">add reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-151">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="4cd0c-152">remove package</span><span class="sxs-lookup"><span data-stu-id="4cd0c-152">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="4cd0c-153">remove reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-153">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="4cd0c-154">list reference</span><span class="sxs-lookup"><span data-stu-id="4cd0c-154">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="4cd0c-155">**고급 명령**</span><span class="sxs-lookup"><span data-stu-id="4cd0c-155">**Advanced commands**</span></span>

- [<span data-ttu-id="4cd0c-156">nuget delete</span><span class="sxs-lookup"><span data-stu-id="4cd0c-156">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="4cd0c-157">nuget locals</span><span class="sxs-lookup"><span data-stu-id="4cd0c-157">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="4cd0c-158">nuget push</span><span class="sxs-lookup"><span data-stu-id="4cd0c-158">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="4cd0c-159">msbuild</span><span class="sxs-lookup"><span data-stu-id="4cd0c-159">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="4cd0c-160">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="4cd0c-160">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="4cd0c-161">CLI에는 프로젝트에 맞게 추가 도구를 지정할 수 있는 확장성 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-161">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="4cd0c-162">자세한 내용은 [.NET Core CLI 확장성 모델](extensibility.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-162">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="4cd0c-163">명령 구조</span><span class="sxs-lookup"><span data-stu-id="4cd0c-163">Command structure</span></span>

<span data-ttu-id="4cd0c-164">CLI 명령 구조는 [드라이버("dotnet")](#driver), [명령](#command), 경우에 따라 [arguments](#arguments) 및 [options](#options) 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-164">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="4cd0c-165">*my_app* 디렉터리에서 실행될 때 다음 명령이 표시하는 것처럼 새 콘솔 앱 생성 및 명령줄에서 실행 등의 대부분의 CLI 작업에서 이 패턴을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-165">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4cd0c-166">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4cd0c-166">.NET Core 2.x</span></span>](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4cd0c-167">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4cd0c-167">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="4cd0c-168">드라이버</span><span class="sxs-lookup"><span data-stu-id="4cd0c-168">Driver</span></span>

<span data-ttu-id="4cd0c-169">이 드라이버는 [dotnet](dotnet.md)으로 이름이 지정되며 [프레임워크 종속 앱](../deploying/index.md)을 실행하거나 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-169">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="4cd0c-170">예를 들어 프레임워크 종속 앱을 실행하려면 드라이버 다음에 앱을 지정합니다(예: `dotnet /path/to/my_app.dll`).</span><span class="sxs-lookup"><span data-stu-id="4cd0c-170">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="4cd0c-171">앱의 DLL이 있는 폴더에서 명령을 실행할 때는 `dotnet my_app.dll`을 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-171">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="4cd0c-172">특정 버전의 .NET Core 런타임을 사용하려면 `--fx-version <VERSION>` 옵션을 사용합니다([dotnet 명령](dotnet.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="4cd0c-172">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="4cd0c-173">드라이버에 명령을 제공하면 `dotnet.exe`가 CLI 명령 실행 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-173">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="4cd0c-174">예:</span><span class="sxs-lookup"><span data-stu-id="4cd0c-174">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="4cd0c-175">먼저 드라이버는 사용할 SDK 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-175">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="4cd0c-176">['global.json'](global-json.md)이 없는 경우 사용 가능한 최신 버전의 SDK가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-176">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="4cd0c-177">이는 머신의 최신 버전에 따라 미리 보기 또는 안정적인 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-177">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="4cd0c-178">SDK 버전이 확인되면 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-178">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="4cd0c-179">명령</span><span class="sxs-lookup"><span data-stu-id="4cd0c-179">Command</span></span>

<span data-ttu-id="4cd0c-180">이 명령이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-180">The command performs an action.</span></span> <span data-ttu-id="4cd0c-181">예를 들어 `dotnet build`는 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-181">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="4cd0c-182">`dotnet publish`는 코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-182">`dotnet publish` publishes code.</span></span> <span data-ttu-id="4cd0c-183">명령은 `dotnet {command}` 규칙을 사용하여 콘솔 애플리케이션으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-183">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="4cd0c-184">인수</span><span class="sxs-lookup"><span data-stu-id="4cd0c-184">Arguments</span></span>

<span data-ttu-id="4cd0c-185">명령줄에서 전달하는 인수는 호출되는 명령에 대한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-185">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="4cd0c-186">예를 들어 `dotnet publish my_app.csproj`를 실행하면 `my_app.csproj` 인수는 게시할 프로젝트를 나타내고 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-186">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="4cd0c-187">옵션</span><span class="sxs-lookup"><span data-stu-id="4cd0c-187">Options</span></span>

<span data-ttu-id="4cd0c-188">명령줄에서 전달하는 옵션은 호출되는 명령에 대한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-188">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="4cd0c-189">예를 들어 `dotnet publish --output /build_output`을 실행하면 `--output` 옵션 및 해당 값이 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-189">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="4cd0c-190">project.json에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="4cd0c-190">Migration from project.json</span></span>

<span data-ttu-id="4cd0c-191">Preview 2 도구를 사용하여 *project.json* 기반 프로젝트를 생성하는 경우 [dotnet migrate](dotnet-migrate.md) 항목에서 릴리스 도구와 함께 사용할 MSBuild/ *.csproj*로 프로젝트를 마이그레이션하기 위한 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-191">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="4cd0c-192">Preview 2 도구 릴리스 이전에 만든 .NET Core 프로젝트의 경우 [DNX에서.NET Core CLI(project.json)로 마이그레이션](../migration/from-dnx.md)의 지침에 따라 프로젝트를 수동으로 업데이트한 후 `dotnet migrate`를 사용하거나 프로젝트를 직접 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd0c-192">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="4cd0c-193">참조</span><span class="sxs-lookup"><span data-stu-id="4cd0c-193">See also</span></span>

- [<span data-ttu-id="4cd0c-194">dotnet/sdk GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="4cd0c-194">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="4cd0c-195">.NET Core 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="4cd0c-195">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
