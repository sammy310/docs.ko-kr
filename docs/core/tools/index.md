---
title: .NET Core CLI(명령줄 인터페이스) 도구
description: .NET Core CLI(명령줄 인터페이스) 도구 및 기능에 대한 개요입니다.
ms.date: 08/14/2017
ms.custom: seodec18
ms.openlocfilehash: e174867ce06e573fc85579183df0196d8276fb37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61647426"
---
# <a name="net-core-command-line-interface-cli-tools"></a><span data-ttu-id="dea98-103">.NET Core CLI(명령줄 인터페이스) 도구</span><span class="sxs-lookup"><span data-stu-id="dea98-103">.NET Core command-line interface (CLI) tools</span></span>

<span data-ttu-id="dea98-104">.NET Core CLI(명령줄 인터페이스)는 .NET 애플리케이션 개발에 사용되는 새로운 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-104">The .NET Core command-line interface (CLI) is a new cross-platform toolchain for developing .NET applications.</span></span> <span data-ttu-id="dea98-105">이 CLI는 IDE(통합 개발 환경), 편집기 및 빌드 Orchestrator와 같은 기타 상위 수준 도구의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-105">The CLI is a foundation upon which higher-level tools, such as Integrated Development Environments (IDEs), editors, and build orchestrators, can rest.</span></span>

## <a name="installation"></a><span data-ttu-id="dea98-106">설치</span><span class="sxs-lookup"><span data-stu-id="dea98-106">Installation</span></span>

<span data-ttu-id="dea98-107">기본 설치 관리자를 사용하거나 설치 셸 스크립트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-107">Either use the native installers or use the installation shell scripts:</span></span>

* <span data-ttu-id="dea98-108">Ubuntu의 DEB 패키지 또는 Windows의 MSI 번들처럼 기본 설치 관리자는 주로 개발자 컴퓨터에서 사용되고 지원되는 각 플랫폼의 기본 설치 메커니즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-108">The native installers are primarily used on developer's machines and use each supported platform's native install mechanism, for instance, DEB packages on Ubuntu or MSI bundles on Windows.</span></span> <span data-ttu-id="dea98-109">이러한 설치 관리자는 개발자가 즉시 사용할 수 있도록 환경을 설치하고 구성하지만 컴퓨터에서 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-109">These installers install and configure the environment for immediate use by the developer but require administrative privileges on the machine.</span></span> <span data-ttu-id="dea98-110">[.NET Core 설치 가이드](https://aka.ms/dotnetcoregs)에서 설치 지침을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-110">You can view the installation instructions in the [.NET Core installation guide](https://aka.ms/dotnetcoregs).</span></span>
* <span data-ttu-id="dea98-111">셸 스크립트는 대개 빌드 서버를 설정하거나 관리자 권한 없이 도구를 설치할 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-111">Shell scripts are primarily used for setting up build servers or when you wish to install the tools without administrative privileges.</span></span> <span data-ttu-id="dea98-112">설치 스크립트는 컴퓨터에 필수 구성 요소를 설치하지 않으므로 이러한 구성 요소는 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-112">Install scripts don't install prerequisites on the machine, which must be installed manually.</span></span> <span data-ttu-id="dea98-113">자세한 내용은 [스크립트 참조 설치 항목](dotnet-install-script.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dea98-113">For more information, see the [install script reference topic](dotnet-install-script.md).</span></span> <span data-ttu-id="dea98-114">CI(연속 통합) 빌드 서버에서 CLI를 설치하는 방법에 대한 자세한 내용은 [.NET Core SDK 및 CI(연속 통합)의 도구 사용](using-ci-with-cli.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dea98-114">For information on how to set up CLI on your continuous integration (CI) build server, see [Using .NET Core SDK and tools in Continuous Integration (CI)](using-ci-with-cli.md).</span></span>

<span data-ttu-id="dea98-115">기본적으로 CLI는 병렬(SxS) 방식으로 설치되므로 여러 버전의 CLI 도구가 단일 컴퓨터에 공존할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-115">By default, the CLI installs in a side-by-side (SxS) manner, so multiple versions of the CLI tools can coexist on a single machine.</span></span> <span data-ttu-id="dea98-116">여러 버전이 설치되어 있는 컴퓨터에서 사용되는 버전을 확인하는 방법은 [드라이버](#driver) 섹션에 좀 더 자세히 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-116">Determining which version is used on a machine where multiple versions are installed is explained in more detail in the [Driver](#driver) section.</span></span>

## <a name="cli-commands"></a><span data-ttu-id="dea98-117">CLI 명령</span><span class="sxs-lookup"><span data-stu-id="dea98-117">CLI commands</span></span>

<span data-ttu-id="dea98-118">다음은 기본적으로 설치되는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-118">The following commands are installed by default:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dea98-119">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dea98-119">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="dea98-120">**기본 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-120">**Basic commands**</span></span>

* [<span data-ttu-id="dea98-121">new</span><span class="sxs-lookup"><span data-stu-id="dea98-121">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="dea98-122">restore</span><span class="sxs-lookup"><span data-stu-id="dea98-122">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="dea98-123">build</span><span class="sxs-lookup"><span data-stu-id="dea98-123">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="dea98-124">publish</span><span class="sxs-lookup"><span data-stu-id="dea98-124">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="dea98-125">run</span><span class="sxs-lookup"><span data-stu-id="dea98-125">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="dea98-126">test</span><span class="sxs-lookup"><span data-stu-id="dea98-126">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="dea98-127">vstest</span><span class="sxs-lookup"><span data-stu-id="dea98-127">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="dea98-128">pack</span><span class="sxs-lookup"><span data-stu-id="dea98-128">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="dea98-129">migrate</span><span class="sxs-lookup"><span data-stu-id="dea98-129">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="dea98-130">clean</span><span class="sxs-lookup"><span data-stu-id="dea98-130">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="dea98-131">sln</span><span class="sxs-lookup"><span data-stu-id="dea98-131">sln</span></span>](dotnet-sln.md)
* [<span data-ttu-id="dea98-132">help</span><span class="sxs-lookup"><span data-stu-id="dea98-132">help</span></span>](dotnet-help.md)
* [<span data-ttu-id="dea98-133">store</span><span class="sxs-lookup"><span data-stu-id="dea98-133">store</span></span>](dotnet-store.md)

<span data-ttu-id="dea98-134">**프로젝트 수정 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-134">**Project modification commands**</span></span>

* [<span data-ttu-id="dea98-135">add package</span><span class="sxs-lookup"><span data-stu-id="dea98-135">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="dea98-136">add reference</span><span class="sxs-lookup"><span data-stu-id="dea98-136">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="dea98-137">remove package</span><span class="sxs-lookup"><span data-stu-id="dea98-137">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="dea98-138">remove reference</span><span class="sxs-lookup"><span data-stu-id="dea98-138">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="dea98-139">list reference</span><span class="sxs-lookup"><span data-stu-id="dea98-139">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="dea98-140">**고급 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-140">**Advanced commands**</span></span>

* [<span data-ttu-id="dea98-141">nuget delete</span><span class="sxs-lookup"><span data-stu-id="dea98-141">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="dea98-142">nuget locals</span><span class="sxs-lookup"><span data-stu-id="dea98-142">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="dea98-143">nuget push</span><span class="sxs-lookup"><span data-stu-id="dea98-143">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="dea98-144">msbuild</span><span class="sxs-lookup"><span data-stu-id="dea98-144">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="dea98-145">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="dea98-145">dotnet install script</span></span>](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dea98-146">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dea98-146">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="dea98-147">**기본 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-147">**Basic commands**</span></span>

* [<span data-ttu-id="dea98-148">new</span><span class="sxs-lookup"><span data-stu-id="dea98-148">new</span></span>](dotnet-new.md)
* [<span data-ttu-id="dea98-149">restore</span><span class="sxs-lookup"><span data-stu-id="dea98-149">restore</span></span>](dotnet-restore.md)
* [<span data-ttu-id="dea98-150">build</span><span class="sxs-lookup"><span data-stu-id="dea98-150">build</span></span>](dotnet-build.md)
* [<span data-ttu-id="dea98-151">publish</span><span class="sxs-lookup"><span data-stu-id="dea98-151">publish</span></span>](dotnet-publish.md)
* [<span data-ttu-id="dea98-152">run</span><span class="sxs-lookup"><span data-stu-id="dea98-152">run</span></span>](dotnet-run.md)
* [<span data-ttu-id="dea98-153">test</span><span class="sxs-lookup"><span data-stu-id="dea98-153">test</span></span>](dotnet-test.md)
* [<span data-ttu-id="dea98-154">vstest</span><span class="sxs-lookup"><span data-stu-id="dea98-154">vstest</span></span>](dotnet-vstest.md)
* [<span data-ttu-id="dea98-155">pack</span><span class="sxs-lookup"><span data-stu-id="dea98-155">pack</span></span>](dotnet-pack.md)
* [<span data-ttu-id="dea98-156">migrate</span><span class="sxs-lookup"><span data-stu-id="dea98-156">migrate</span></span>](dotnet-migrate.md)
* [<span data-ttu-id="dea98-157">clean</span><span class="sxs-lookup"><span data-stu-id="dea98-157">clean</span></span>](dotnet-clean.md)
* [<span data-ttu-id="dea98-158">sln</span><span class="sxs-lookup"><span data-stu-id="dea98-158">sln</span></span>](dotnet-sln.md)

<span data-ttu-id="dea98-159">**프로젝트 수정 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-159">**Project modification commands**</span></span>

* [<span data-ttu-id="dea98-160">add package</span><span class="sxs-lookup"><span data-stu-id="dea98-160">add package</span></span>](dotnet-add-package.md)
* [<span data-ttu-id="dea98-161">add reference</span><span class="sxs-lookup"><span data-stu-id="dea98-161">add reference</span></span>](dotnet-add-reference.md)
* [<span data-ttu-id="dea98-162">remove package</span><span class="sxs-lookup"><span data-stu-id="dea98-162">remove package</span></span>](dotnet-remove-package.md)
* [<span data-ttu-id="dea98-163">remove reference</span><span class="sxs-lookup"><span data-stu-id="dea98-163">remove reference</span></span>](dotnet-remove-reference.md)
* [<span data-ttu-id="dea98-164">list reference</span><span class="sxs-lookup"><span data-stu-id="dea98-164">list reference</span></span>](dotnet-list-reference.md)

<span data-ttu-id="dea98-165">**고급 명령**</span><span class="sxs-lookup"><span data-stu-id="dea98-165">**Advanced commands**</span></span>

* [<span data-ttu-id="dea98-166">nuget delete</span><span class="sxs-lookup"><span data-stu-id="dea98-166">nuget delete</span></span>](dotnet-nuget-delete.md)
* [<span data-ttu-id="dea98-167">nuget locals</span><span class="sxs-lookup"><span data-stu-id="dea98-167">nuget locals</span></span>](dotnet-nuget-locals.md)
* [<span data-ttu-id="dea98-168">nuget push</span><span class="sxs-lookup"><span data-stu-id="dea98-168">nuget push</span></span>](dotnet-nuget-push.md)
* [<span data-ttu-id="dea98-169">msbuild</span><span class="sxs-lookup"><span data-stu-id="dea98-169">msbuild</span></span>](dotnet-msbuild.md)
* [<span data-ttu-id="dea98-170">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="dea98-170">dotnet install script</span></span>](dotnet-install-script.md)

---

<span data-ttu-id="dea98-171">CLI에는 프로젝트에 맞게 추가 도구를 지정할 수 있는 확장성 모델이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-171">The CLI adopts an extensibility model that allows you to specify additional tools for your projects.</span></span> <span data-ttu-id="dea98-172">자세한 내용은 [.NET Core CLI 확장성 모델](extensibility.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dea98-172">For more information, see the [.NET Core CLI extensibility model](extensibility.md) topic.</span></span>

## <a name="command-structure"></a><span data-ttu-id="dea98-173">명령 구조</span><span class="sxs-lookup"><span data-stu-id="dea98-173">Command structure</span></span>

<span data-ttu-id="dea98-174">CLI 명령 구조는 [드라이버("dotnet")](#driver), [명령(또는 "동사")](#command-verb), 경우에 따라 [arguments](#arguments) 및 [options](#options) 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-174">CLI command structure consists of [the driver ("dotnet")](#driver), [the command (or "verb")](#command-verb), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="dea98-175">*my_app* 디렉터리에서 실행될 때 다음 명령이 표시하는 것처럼 새 콘솔 앱 생성 및 명령줄에서 실행 등의 대부분의 CLI 작업에서 이 패턴을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-175">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="dea98-176">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="dea98-176">.NET Core 2.x</span></span>](#tab/netcore2x)

```console
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="dea98-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="dea98-177">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a><span data-ttu-id="dea98-178">드라이버</span><span class="sxs-lookup"><span data-stu-id="dea98-178">Driver</span></span>

<span data-ttu-id="dea98-179">이 드라이버는 [dotnet](dotnet.md)으로 이름이 지정되며 [프레임워크 종속 앱](../deploying/index.md)을 실행하거나 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-179">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span> 

<span data-ttu-id="dea98-180">예를 들어 프레임워크 종속 앱을 실행하려면 드라이버 다음에 앱을 지정합니다(예: `dotnet /path/to/my_app.dll`).</span><span class="sxs-lookup"><span data-stu-id="dea98-180">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="dea98-181">앱의 DLL이 있는 폴더에서 명령을 실행할 때는 `dotnet my_app.dll`을 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-181">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="dea98-182">특정 버전의 .NET Core 런타임을 사용하려면 `--fx-version <VERSION>` 옵션을 사용합니다([dotnet 명령](dotnet.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="dea98-182">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="dea98-183">드라이버에 명령을 제공하면 `dotnet.exe`가 CLI 명령 실행 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-183">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="dea98-184">예:</span><span class="sxs-lookup"><span data-stu-id="dea98-184">For example:</span></span>

```bash
> dotnet build
```

<span data-ttu-id="dea98-185">먼저 드라이버는 사용할 SDK 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-185">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="dea98-186">['global.json'](global-json.md)이 없는 경우 사용 가능한 최신 버전의 SDK가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-186">If there is no ['global.json'](global-json.md), the latest version of the SDK available is used.</span></span> <span data-ttu-id="dea98-187">이는 머신의 최신 버전에 따라 미리 보기 또는 안정적인 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-187">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="dea98-188">SDK 버전이 확인되면 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-188">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command-verb"></a><span data-ttu-id="dea98-189">명령("동사")</span><span class="sxs-lookup"><span data-stu-id="dea98-189">Command ("verb")</span></span>

<span data-ttu-id="dea98-190">명령("동사")은 작업을 수행하는 명령일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-190">The command (or "verb") is simply a command that performs an action.</span></span> <span data-ttu-id="dea98-191">예를 들어 `dotnet build`는 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-191">For example, `dotnet build` builds your code.</span></span> <span data-ttu-id="dea98-192">`dotnet publish`는 코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-192">`dotnet publish` publishes your code.</span></span> <span data-ttu-id="dea98-193">명령은 `dotnet {verb}` 규칙을 사용하여 콘솔 애플리케이션으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-193">The commands are implemented as a console application using a `dotnet {verb}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="dea98-194">인수</span><span class="sxs-lookup"><span data-stu-id="dea98-194">Arguments</span></span>

<span data-ttu-id="dea98-195">명령줄에서 전달하는 인수는 호출되는 명령에 대한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-195">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="dea98-196">예를 들어 `dotnet publish my_app.csproj`를 실행하면 `my_app.csproj` 인수는 게시할 프로젝트를 나타내고 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-196">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="dea98-197">옵션</span><span class="sxs-lookup"><span data-stu-id="dea98-197">Options</span></span>

<span data-ttu-id="dea98-198">명령줄에서 전달하는 옵션은 호출되는 명령에 대한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-198">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="dea98-199">예를 들어 `dotnet publish --output /build_output`을 실행하면 `--output` 옵션 및 해당 값이 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-199">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="migration-from-projectjson"></a><span data-ttu-id="dea98-200">project.json에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="dea98-200">Migration from project.json</span></span>

<span data-ttu-id="dea98-201">Preview 2 도구를 사용하여 *project.json* 기반 프로젝트를 생성하는 경우 [dotnet migrate](dotnet-migrate.md) 항목에서 릴리스 도구와 함께 사용할 MSBuild/*.csproj*로 프로젝트를 마이그레이션하기 위한 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dea98-201">If you used Preview 2 tooling to produce *project.json*-based projects, consult the [dotnet migrate](dotnet-migrate.md) topic for information on migrating your project to MSBuild/*.csproj* for use with release tooling.</span></span> <span data-ttu-id="dea98-202">Preview 2 도구 릴리스 이전에 만든 .NET Core 프로젝트의 경우 [DNX에서.NET Core CLI(project.json)로 마이그레이션](../migration/from-dnx.md)의 지침에 따라 프로젝트를 수동으로 업데이트한 후 `dotnet migrate`를 사용하거나 프로젝트를 직접 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="dea98-202">For .NET Core projects created prior to the release of Preview 2 tooling, either manually update the project following the guidance in [Migrating from DNX to .NET Core CLI (project.json)](../migration/from-dnx.md) and then use `dotnet migrate` or directly upgrade your projects.</span></span>

## <a name="see-also"></a><span data-ttu-id="dea98-203">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dea98-203">See also</span></span>

- [<span data-ttu-id="dea98-204">dotnet/CLI GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="dea98-204">dotnet/CLI GitHub Repository</span></span>](https://github.com/dotnet/cli/)
- [<span data-ttu-id="dea98-205">.NET Core 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="dea98-205">.NET Core installation guide</span></span>](https://aka.ms/dotnetcoregs)
