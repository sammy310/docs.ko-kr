---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 및 해당 기능에 대한 개요입니다.
ms.date: 02/13/2020
ms.openlocfilehash: d84f96889cabc3fb4521e39db25050aacdd11546
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156714"
---
# <a name="net-core-cli-overview"></a><span data-ttu-id="185b7-103">.NET Core CLI 개요</span><span class="sxs-lookup"><span data-stu-id="185b7-103">.NET Core CLI overview</span></span>

<span data-ttu-id="185b7-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="185b7-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="185b7-105">.NET Core CLI(명령줄 인터페이스)는 .NET Core 애플리케이션의 개발, 빌드, 실행 및 게시에 사용되는 플랫폼 간 도구 체인입니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-105">The .NET Core command-line interface (CLI) is a cross-platform toolchain for developing, building, running, and publishing .NET Core applications.</span></span>

<span data-ttu-id="185b7-106">.NET Core CLI는 [.NET Core SDK](../sdk.md)에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-106">The .NET Core CLI is included with the [.NET Core SDK](../sdk.md).</span></span> <span data-ttu-id="185b7-107">.NET Core SDK를 설치하는 방법에 대한 자세한 내용은 [.NET Core SDK 설치](../install/sdk.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="185b7-107">To learn how to install the .NET Core SDK, see [Install the .NET Core SDK](../install/sdk.md).</span></span>

## <a name="cli-commands"></a><span data-ttu-id="185b7-108">CLI 명령</span><span class="sxs-lookup"><span data-stu-id="185b7-108">CLI commands</span></span>

<span data-ttu-id="185b7-109">다음은 기본적으로 설치되는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-109">The following commands are installed by default:</span></span>

### <a name="basic-commands"></a><span data-ttu-id="185b7-110">기본 명령</span><span class="sxs-lookup"><span data-stu-id="185b7-110">Basic commands</span></span>

- [<span data-ttu-id="185b7-111">new</span><span class="sxs-lookup"><span data-stu-id="185b7-111">new</span></span>](dotnet-new.md)
- [<span data-ttu-id="185b7-112">restore</span><span class="sxs-lookup"><span data-stu-id="185b7-112">restore</span></span>](dotnet-restore.md)
- [<span data-ttu-id="185b7-113">build</span><span class="sxs-lookup"><span data-stu-id="185b7-113">build</span></span>](dotnet-build.md)
- [<span data-ttu-id="185b7-114">publish</span><span class="sxs-lookup"><span data-stu-id="185b7-114">publish</span></span>](dotnet-publish.md)
- [<span data-ttu-id="185b7-115">run</span><span class="sxs-lookup"><span data-stu-id="185b7-115">run</span></span>](dotnet-run.md)
- [<span data-ttu-id="185b7-116">test</span><span class="sxs-lookup"><span data-stu-id="185b7-116">test</span></span>](dotnet-test.md)
- [<span data-ttu-id="185b7-117">vstest</span><span class="sxs-lookup"><span data-stu-id="185b7-117">vstest</span></span>](dotnet-vstest.md)
- [<span data-ttu-id="185b7-118">pack</span><span class="sxs-lookup"><span data-stu-id="185b7-118">pack</span></span>](dotnet-pack.md)
- [<span data-ttu-id="185b7-119">migrate</span><span class="sxs-lookup"><span data-stu-id="185b7-119">migrate</span></span>](dotnet-migrate.md)
- [<span data-ttu-id="185b7-120">clean</span><span class="sxs-lookup"><span data-stu-id="185b7-120">clean</span></span>](dotnet-clean.md)
- [<span data-ttu-id="185b7-121">sln</span><span class="sxs-lookup"><span data-stu-id="185b7-121">sln</span></span>](dotnet-sln.md)
- [<span data-ttu-id="185b7-122">help</span><span class="sxs-lookup"><span data-stu-id="185b7-122">help</span></span>](dotnet-help.md)
- [<span data-ttu-id="185b7-123">store</span><span class="sxs-lookup"><span data-stu-id="185b7-123">store</span></span>](dotnet-store.md)

### <a name="project-modification-commands"></a><span data-ttu-id="185b7-124">프로젝트 수정 명령</span><span class="sxs-lookup"><span data-stu-id="185b7-124">Project modification commands</span></span>

- [<span data-ttu-id="185b7-125">add package</span><span class="sxs-lookup"><span data-stu-id="185b7-125">add package</span></span>](dotnet-add-package.md)
- [<span data-ttu-id="185b7-126">add reference</span><span class="sxs-lookup"><span data-stu-id="185b7-126">add reference</span></span>](dotnet-add-reference.md)
- [<span data-ttu-id="185b7-127">remove package</span><span class="sxs-lookup"><span data-stu-id="185b7-127">remove package</span></span>](dotnet-remove-package.md)
- [<span data-ttu-id="185b7-128">remove reference</span><span class="sxs-lookup"><span data-stu-id="185b7-128">remove reference</span></span>](dotnet-remove-reference.md)
- [<span data-ttu-id="185b7-129">list reference</span><span class="sxs-lookup"><span data-stu-id="185b7-129">list reference</span></span>](dotnet-list-reference.md)

### <a name="advanced-commands"></a><span data-ttu-id="185b7-130">고급 명령</span><span class="sxs-lookup"><span data-stu-id="185b7-130">Advanced commands</span></span>

- [<span data-ttu-id="185b7-131">nuget delete</span><span class="sxs-lookup"><span data-stu-id="185b7-131">nuget delete</span></span>](dotnet-nuget-delete.md)
- [<span data-ttu-id="185b7-132">nuget locals</span><span class="sxs-lookup"><span data-stu-id="185b7-132">nuget locals</span></span>](dotnet-nuget-locals.md)
- [<span data-ttu-id="185b7-133">nuget push</span><span class="sxs-lookup"><span data-stu-id="185b7-133">nuget push</span></span>](dotnet-nuget-push.md)
- [<span data-ttu-id="185b7-134">msbuild</span><span class="sxs-lookup"><span data-stu-id="185b7-134">msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="185b7-135">dotnet install script</span><span class="sxs-lookup"><span data-stu-id="185b7-135">dotnet install script</span></span>](dotnet-install-script.md)

### <a name="tool-management-commands"></a><span data-ttu-id="185b7-136">도구 관리 명령</span><span class="sxs-lookup"><span data-stu-id="185b7-136">Tool management commands</span></span>

- [<span data-ttu-id="185b7-137">tool install</span><span class="sxs-lookup"><span data-stu-id="185b7-137">tool install</span></span>](dotnet-tool-install.md)
- [<span data-ttu-id="185b7-138">tool list</span><span class="sxs-lookup"><span data-stu-id="185b7-138">tool list</span></span>](dotnet-tool-list.md)
- [<span data-ttu-id="185b7-139">tool update</span><span class="sxs-lookup"><span data-stu-id="185b7-139">tool update</span></span>](dotnet-tool-update.md)
- <span data-ttu-id="185b7-140">[tool restore](global-tools.md#install-a-local-tool) **.NET Core SDK 3.0부터 사용 가능**</span><span class="sxs-lookup"><span data-stu-id="185b7-140">[tool restore](global-tools.md#install-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- <span data-ttu-id="185b7-141">[tool run](global-tools.md#invoke-a-local-tool) **.NET Core SDK 3.0부터 사용 가능**</span><span class="sxs-lookup"><span data-stu-id="185b7-141">[tool run](global-tools.md#invoke-a-local-tool) **Available starting with .NET Core SDK 3.0**</span></span>
- [<span data-ttu-id="185b7-142">tool uninstall</span><span class="sxs-lookup"><span data-stu-id="185b7-142">tool uninstall</span></span>](dotnet-tool-uninstall.md)

<span data-ttu-id="185b7-143">도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-143">Tools are console applications that are installed from NuGet packages and are invoked from the command prompt.</span></span> <span data-ttu-id="185b7-144">도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-144">You can write tools yourself or install tools written by third parties.</span></span> <span data-ttu-id="185b7-145">도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-145">Tools are also known as global tools, tool-path tools, and local tools.</span></span> <span data-ttu-id="185b7-146">자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="185b7-146">For more information, see [.NET Core tools overview](global-tools.md).</span></span>

## <a name="command-structure"></a><span data-ttu-id="185b7-147">명령 구조</span><span class="sxs-lookup"><span data-stu-id="185b7-147">Command structure</span></span>

<span data-ttu-id="185b7-148">CLI 명령 구조는 [드라이버("dotnet")](#driver), [명령](#command), 경우에 따라 [arguments](#arguments) 및 [options](#options) 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-148">CLI command structure consists of [the driver ("dotnet")](#driver), [the command](#command), and possibly command [arguments](#arguments) and [options](#options).</span></span> <span data-ttu-id="185b7-149">*my_app* 디렉터리에서 실행될 때 다음 명령이 표시하는 것처럼 새 콘솔 앱 생성 및 명령줄에서 실행 등의 대부분의 CLI 작업에서 이 패턴을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-149">You see this pattern in most CLI operations, such as creating a new console app and running it from the command line as the following commands show when executed from a directory named *my_app*:</span></span>

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a><span data-ttu-id="185b7-150">드라이버</span><span class="sxs-lookup"><span data-stu-id="185b7-150">Driver</span></span>

<span data-ttu-id="185b7-151">이 드라이버는 [dotnet](dotnet.md)으로 이름이 지정되며 [프레임워크 종속 앱](../deploying/index.md)을 실행하거나 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-151">The driver is named [dotnet](dotnet.md) and has two responsibilities, either running a [framework-dependent app](../deploying/index.md) or executing a command.</span></span>

<span data-ttu-id="185b7-152">예를 들어 프레임워크 종속 앱을 실행하려면 드라이버 다음에 앱을 지정합니다(예: `dotnet /path/to/my_app.dll`).</span><span class="sxs-lookup"><span data-stu-id="185b7-152">To run a framework-dependent app, specify the app after the driver, for example, `dotnet /path/to/my_app.dll`.</span></span> <span data-ttu-id="185b7-153">앱의 DLL이 있는 폴더에서 명령을 실행할 때는 `dotnet my_app.dll`을 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-153">When executing the command from the folder where the app's DLL resides, simply execute `dotnet my_app.dll`.</span></span> <span data-ttu-id="185b7-154">특정 버전의 .NET Core 런타임을 사용하려면 `--fx-version <VERSION>` 옵션을 사용합니다([dotnet 명령](dotnet.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="185b7-154">If you want to use a specific version of the .NET Core Runtime, use the `--fx-version <VERSION>` option (see the [dotnet command](dotnet.md) reference).</span></span>

<span data-ttu-id="185b7-155">드라이버에 명령을 제공하면 `dotnet.exe`가 CLI 명령 실행 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-155">When you supply a command to the driver, `dotnet.exe` starts the CLI command execution process.</span></span> <span data-ttu-id="185b7-156">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="185b7-156">For example:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="185b7-157">먼저 드라이버는 사용할 SDK 버전을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-157">First, the driver determines the version of the SDK to use.</span></span> <span data-ttu-id="185b7-158">[global.json](global-json.md) 파일이 없는 경우 사용 가능한 최신 버전의 SDK가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-158">If there is no [global.json](global-json.md) file, the latest version of the SDK available is used.</span></span> <span data-ttu-id="185b7-159">이는 머신의 최신 버전에 따라 미리 보기 또는 안정적인 버전일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-159">This might be either a preview or stable version, depending on what is latest on the machine.</span></span>  <span data-ttu-id="185b7-160">SDK 버전이 확인되면 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-160">Once the SDK version is determined, it executes the command.</span></span>

### <a name="command"></a><span data-ttu-id="185b7-161">명령</span><span class="sxs-lookup"><span data-stu-id="185b7-161">Command</span></span>

<span data-ttu-id="185b7-162">이 명령이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-162">The command performs an action.</span></span> <span data-ttu-id="185b7-163">예를 들어 `dotnet build`는 코드를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-163">For example, `dotnet build` builds code.</span></span> <span data-ttu-id="185b7-164">`dotnet publish`는 코드를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-164">`dotnet publish` publishes code.</span></span> <span data-ttu-id="185b7-165">명령은 `dotnet {command}` 규칙을 사용하여 콘솔 애플리케이션으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-165">The commands are implemented as a console application using a `dotnet {command}` convention.</span></span>

### <a name="arguments"></a><span data-ttu-id="185b7-166">인수</span><span class="sxs-lookup"><span data-stu-id="185b7-166">Arguments</span></span>

<span data-ttu-id="185b7-167">명령줄에서 전달하는 인수는 호출되는 명령에 대한 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-167">The arguments you pass on the command line are the arguments to the command invoked.</span></span> <span data-ttu-id="185b7-168">예를 들어 `dotnet publish my_app.csproj`를 실행하면 `my_app.csproj` 인수는 게시할 프로젝트를 나타내고 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-168">For example when you execute `dotnet publish my_app.csproj`, the `my_app.csproj` argument indicates the project to publish and is passed to the `publish` command.</span></span>

### <a name="options"></a><span data-ttu-id="185b7-169">옵션</span><span class="sxs-lookup"><span data-stu-id="185b7-169">Options</span></span>

<span data-ttu-id="185b7-170">명령줄에서 전달하는 옵션은 호출되는 명령에 대한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-170">The options you pass on the command line are the options to the command invoked.</span></span> <span data-ttu-id="185b7-171">예를 들어 `dotnet publish --output /build_output`을 실행하면 `--output` 옵션 및 해당 값이 `publish` 명령에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="185b7-171">For example when you execute `dotnet publish --output /build_output`, the `--output` option and its value are passed to the `publish` command.</span></span>

## <a name="see-also"></a><span data-ttu-id="185b7-172">참조</span><span class="sxs-lookup"><span data-stu-id="185b7-172">See also</span></span>

- [<span data-ttu-id="185b7-173">dotnet/sdk GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="185b7-173">dotnet/sdk GitHub repository</span></span>](https://github.com/dotnet/sdk/)
- [<span data-ttu-id="185b7-174">.NET Core 설치 가이드</span><span class="sxs-lookup"><span data-stu-id="185b7-174">.NET Core installation guide</span></span>](../install/sdk.md)
