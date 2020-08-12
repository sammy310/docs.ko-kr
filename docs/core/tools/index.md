---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 및 해당 기능에 대한 개요입니다.
ms.topic: overview
ms.date: 02/13/2020
ms.openlocfilehash: 18dde384058206f437b53572b2f8331d65324482
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062693"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="d8e36-103">.NET Core CLI 개요</span><span class="sxs-lookup"><span data-stu-id="d8e36-103">.NET Core CLI overview</span></span>

<span data-ttu-id="d8e36-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d8e36-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="d8e36-105">.NET Core CLI(명령줄 인터페이스)는 .NET Core 애플리케이션의 개발, 빌드, 실행 및 게시에 사용되는 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="d8e36-106">.NET Core CLI는 [.NET Core SDK](../sdk.md)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="d8e36-107">.NET Core SDK를 설치하는 방법에 대한 자세한 내용은 [.NET Core 설치](../install/windows.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8e36-107">To learn how to install the .NET Core SDK, see [Install .NET Core](../install/windows.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="d8e36-108">CLI 명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-108">CLI commands</span></span>

<span data-ttu-id="d8e36-109">다음은 기본적으로 설치되는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="d8e36-110">기본 명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-110">Basic commands</span></span>

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="d8e36-111">프로젝트 수정 명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-111">Project modification commands</span></span>

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="d8e36-112">고급 명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-112">Advanced commands</span></span>

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="d8e36-113">도구 관리 명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-113">Tool management commands</span></span>

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- <span data-ttu-id="d8e36-114">[`tool restore`](global-tools.md#install-a-local-tool) .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-114">[`tool restore`](global-tools.md#install-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- <span data-ttu-id="d8e36-115">[`tool run`](global-tools.md#invoke-a-local-tool) .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-115">[`tool run`](global-tools.md#invoke-a-local-tool) Available since .NET Core SDK 3.0.</span></span>
- [`tool uninstall`](dotnet-tool-uninstall.md)

<span data-ttu-id="d8e36-116">도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-116">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="d8e36-117">도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-117">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="d8e36-118">도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-118">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="d8e36-119">자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d8e36-119">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="d8e36-120">명령 구조</span><span class="sxs-lookup"><span data-stu-id="d8e36-120">Command structure</span></span>

<span data-ttu-id="d8e36-121">CLI 명령 구조는 [드라이버("dotnet")](#driver), [명령](#command), 경우에 따라 [arguments](#arguments) 및 [options](#options) 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-121">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="d8e36-122">*my_app* 디렉터리에서 실행될 때 다음 명령이 표시하는 것처럼 새 콘솔 앱 생성 및 명령줄에서 실행 등의 대부분의 CLI 작업에서 이 패턴을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-122">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="d8e36-123">드라이버</span><span class="sxs-lookup"><span data-stu-id="d8e36-123">Driver</span></span>

<span data-ttu-id="d8e36-124">이 드라이버는 [dotnet](dotnet.md)으로 이름이 지정되며 [프레임워크 종속 앱](../deploying/index.md)을 실행하거나 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-124">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="d8e36-125">예를 들어 프레임워크 종속 앱을 실행하려면 드라이버 다음에 앱을 지정합니다(예: `dotnet /path/to/my_app.dll`).</span><span class="sxs-lookup"><span data-stu-id="d8e36-125">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="d8e36-126">앱의 DLL이 있는 폴더에서 명령을 실행할 때는 `dotnet my_app.dll`을 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-126">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="d8e36-127">특정 버전의 .NET Core 런타임을 사용하려면 `--fx-version <VERSION>` 옵션을 사용합니다([dotnet 명령](dotnet.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="d8e36-127">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="d8e36-128">드라이버에 명령을 제공하면 `dotnet.exe`가 CLI 명령 실행 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-128">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="d8e36-129">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d8e36-129">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="d8e36-130">먼저 드라이버는 사용할 SDK 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-130">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="d8e36-131">[global.json](global-json.md) 파일이 없는 경우 사용 가능한 최신 버전의 SDK가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-131">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="d8e36-132">이는 머신의 최신 버전에 따라 미리 보기 또는 안정적인 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-132">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="d8e36-133">SDK 버전이 확인되면 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-133">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="d8e36-134">명령</span><span class="sxs-lookup"><span data-stu-id="d8e36-134">Command</span></span>

<span data-ttu-id="d8e36-135">이 명령이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-135">The command performs an action.</span></span> <span data-ttu-id="d8e36-136">예를 들어 `dotnet build`는 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-136">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="d8e36-137">`dotnet publish`는 코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-137">`dotnet publish` publishes code.</span></span> <span data-ttu-id="d8e36-138">명령은 `dotnet {command}` 규칙을 사용하여 콘솔 애플리케이션으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-138">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="d8e36-139">인수</span><span class="sxs-lookup"><span data-stu-id="d8e36-139">Arguments</span></span>

<span data-ttu-id="d8e36-140">명령줄에서 전달하는 인수는 호출되는 명령에 대한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-140">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="d8e36-141">예를 들어 `dotnet publish my_app.csproj`를 실행하면 `my_app.csproj` 인수는 게시할 프로젝트를 나타내고 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-141">For example, when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="d8e36-142">옵션</span><span class="sxs-lookup"><span data-stu-id="d8e36-142">Options</span></span>

<span data-ttu-id="d8e36-143">명령줄에서 전달하는 옵션은 호출되는 명령에 대한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-143">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="d8e36-144">예를 들어 `dotnet publish --output /build_output`을 실행하면 `--output` 옵션 및 해당 값이 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8e36-144">For example, when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8e36-145">참조</span><span class="sxs-lookup"><span data-stu-id="d8e36-145">See also</span></span>

- [<span data-ttu-id="d8e36-146">dotnet/sdk GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="d8e36-146">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="d8e36-147">.NET Core 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="d8e36-147">.NET Core installation guide</span></span>](../install/windows.md)
