---
title: dotnet build 명령
description: dotnet build 명령은 프로젝트와 모든 종속성을 빌드합니다.
ms.date: 10/07/2019
ms.openlocfilehash: 0a3e2c0e441cfdd1cb8266bc77dc1aba08af84d6
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522787"
---
# <a name="dotnet-build"></a><span data-ttu-id="6546a-103">dotnet build</span><span class="sxs-lookup"><span data-stu-id="6546a-103">dotnet build</span></span>

<span data-ttu-id="6546a-104">**이 문서 적용 대상: ✓** .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="6546a-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="6546a-105">name</span><span class="sxs-lookup"><span data-stu-id="6546a-105">Name</span></span>

<span data-ttu-id="6546a-106">`dotnet build` - 프로젝트 및 모든 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-106">`dotnet build` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6546a-107">개요</span><span class="sxs-lookup"><span data-stu-id="6546a-107">Synopsis</span></span>

```dotnetcli
dotnet build [<PROJECT>|<SOLUTION>] [-c|--configuration] [-f|--framework] [--force] [--interactive] [--no-dependencies]
    [--no-incremental] [--no-restore] [--nologo] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]

dotnet build [-h|--help]
```

## <a name="description"></a><span data-ttu-id="6546a-108">설명</span><span class="sxs-lookup"><span data-stu-id="6546a-108">Description</span></span>

<span data-ttu-id="6546a-109">`dotnet build` 명령은 이진 파일 집합으로 프로젝트와 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-109">The `dotnet build` command builds the project and its dependencies into a set of binaries.</span></span> <span data-ttu-id="6546a-110">이진 파일에는 *.dll* 확장명을 갖는 IL(중간 언어)의 프로젝트 코드와 *.pdb* 확장명을 가지며 디버깅에 사용되는 기호 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-110">The binaries include the project's code in Intermediate Language (IL) files with a *.dll* extension and symbol files used for debugging with a *.pdb* extension.</span></span> <span data-ttu-id="6546a-111">애플리케이션의 종속성을 나열하는 종속성 JSON 파일( *.deps.json*)이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-111">A dependencies JSON file (*.deps.json*) is produced that lists the dependencies of the application.</span></span> <span data-ttu-id="6546a-112">애플리케이션에 대한 공유 런타임 및 해당 버전을 지정하는 *.runtimeconfig.json* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-112">A *.runtimeconfig.json* file is produced, which specifies the shared runtime and its version for the application.</span></span>

<span data-ttu-id="6546a-113">프로젝트에 NuGet의 라이브러리와 같은 타사 종속성이 있는 경우, 이러한 종속성은 NuGet 캐시에서 확인되고 프로젝트의 빌드 출력으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-113">If the project has third-party dependencies, such as libraries from NuGet, they're resolved from the NuGet cache and aren't available with the project's built output.</span></span> <span data-ttu-id="6546a-114">따라서 `dotnet build`의 제품을 실행하기 위해 다른 컴퓨터로 전송할 준비가 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-114">With that in mind, the product of `dotnet build` isn't ready to be transferred to another machine to run.</span></span> <span data-ttu-id="6546a-115">이는 실행 가능한 프로젝트(애플리케이션) 빌드로 .NET Framework가 설치된 컴퓨터에서 실행할 수 있는 출력을 생성하는 .NET Framework의 동작과는 대조적입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-115">This is in contrast to the behavior of the .NET Framework in which building an executable project (an application) produces output that's runnable on any machine where the .NET Framework is installed.</span></span> <span data-ttu-id="6546a-116">.NET Core에서 비슷한 환경을 사용하려면 [dotnet publish](dotnet-publish.md) 명령을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-116">To have a similar experience with .NET Core, you need to use the [dotnet publish](dotnet-publish.md) command.</span></span> <span data-ttu-id="6546a-117">자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6546a-117">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span>

<span data-ttu-id="6546a-118">빌드하려면 애플리케이션의 종속성을 나열하는 *project.assets.json* 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-118">Building requires the *project.assets.json* file, which lists the dependencies of your application.</span></span> <span data-ttu-id="6546a-119">[`dotnet restore`](dotnet-restore.md)가 실행되면 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-119">The file is created when [`dotnet restore`](dotnet-restore.md) is executed.</span></span> <span data-ttu-id="6546a-120">자산 파일이 없으면 도구로 참조 어셈블리를 확인할 수 없으므로 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-120">Without the assets file in place, the tooling can't resolve reference assemblies, which results in errors.</span></span> <span data-ttu-id="6546a-121">.NET Core 1.x SDK를 사용할 경우 `dotnet build`를 실행하기 전에 `dotnet restore`를 명시적으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-121">With .NET Core 1.x SDK, you needed to explicitly run `dotnet restore` before running `dotnet build`.</span></span> <span data-ttu-id="6546a-122">.NET Core 2.0 SDK부터 `dotnet restore`는 `dotnet build`를 실행할 때 암시적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-122">Starting with .NET Core 2.0 SDK, `dotnet restore` runs implicitly when you run `dotnet build`.</span></span> <span data-ttu-id="6546a-123">빌드 명령을 실행할 때 암시적 복원을 사용하지 않으려면 `--no-restore` 옵션을 전달하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-123">If you want to disable implicit restore when running the build command, you can pass the `--no-restore` option.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

<span data-ttu-id="6546a-124">프로젝트가 실행 가능한지 아닌지 여부는 프로젝트 파일의 `<OutputType>` 속성으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-124">Whether the project is executable or not is determined by the `<OutputType>` property in the project file.</span></span> <span data-ttu-id="6546a-125">다음 예제에서는 실행 코드를 생성하는 프로젝트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-125">The following example shows a project that produces executable code:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="6546a-126">라이브러리를 생성하려면 `<OutputType>` 속성을 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-126">To produce a library, omit the `<OutputType>` property.</span></span> <span data-ttu-id="6546a-127">빌드된 출력의 주요 차이점은 라이브러리에 대한 IL DLL이 진입점을 포함하지 않으며 실행할 수 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-127">The main difference in built output is that the IL DLL for a library doesn't contain entry points and can't be executed.</span></span>

### <a name="msbuild"></a><span data-ttu-id="6546a-128">MSBuild</span><span class="sxs-lookup"><span data-stu-id="6546a-128">MSBuild</span></span>

<span data-ttu-id="6546a-129">`dotnet build`는 MSBuild를 사용하여 프로젝트를 빌드하므로 병렬 및 증분 빌드를 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-129">`dotnet build` uses MSBuild to build the project, so it supports both parallel and incremental builds.</span></span> <span data-ttu-id="6546a-130">자세한 내용은 [증분 빌드](/visualstudio/msbuild/incremental-builds)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6546a-130">For more information, see [Incremental Builds](/visualstudio/msbuild/incremental-builds).</span></span>

<span data-ttu-id="6546a-131">해당 옵션 외에도, `dotnet build` 명령은 속성 설정에 대한 `-p` 또는 로거를 정의하는 `-l`처럼 MSBuild 옵션도 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-131">In addition to its options, the `dotnet build` command accepts MSBuild options, such as `-p` for setting properties or `-l` to define a logger.</span></span> <span data-ttu-id="6546a-132">이러한 옵션에 대한 자세한 내용은 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6546a-132">For more information about these options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="6546a-133">또는 [dotnet msbuild](dotnet-msbuild.md) 명령을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-133">Or you can also use the [dotnet msbuild](dotnet-msbuild.md) command.</span></span>

<span data-ttu-id="6546a-134">`dotnet build` 실행은 `dotnet msbuild -restore -target:Build`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-134">Running `dotnet build` is equivalent to `dotnet msbuild -restore -target:Build`.</span></span>

## <a name="arguments"></a><span data-ttu-id="6546a-135">인수</span><span class="sxs-lookup"><span data-stu-id="6546a-135">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="6546a-136">빌드할 프로젝트 또는 솔루션 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-136">The project or solution file to build.</span></span> <span data-ttu-id="6546a-137">프로젝트 또는 솔루션 파일을 지정하지 않으면 MSBuild는 현재 작업 디렉터리에서 *proj* 또는 *sln*으로 끝나는 파일 확장명이 있는 파일을 검색하고 해당 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-137">If a project or solution file isn't specified, MSBuild searches the current working directory for a file that has a file extension that ends in either *proj* or *sln* and uses that file.</span></span>

## <a name="options"></a><span data-ttu-id="6546a-138">옵션</span><span class="sxs-lookup"><span data-stu-id="6546a-138">Options</span></span>

- **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="6546a-139">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-139">Defines the build configuration.</span></span> <span data-ttu-id="6546a-140">대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-140">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="6546a-141">특정 [프레임워크](../../standard/frameworks.md)에 대해 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-141">Compiles for a specific [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="6546a-142">프레임워크는 [프로젝트 파일](csproj.md)에 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-142">The framework must be defined in the [project file](csproj.md).</span></span>

- **`--force`**

  <span data-ttu-id="6546a-143">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-143">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="6546a-144">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-144">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="6546a-145">.NET Core 2.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-145">Available since .NET Core 2.0 SDK.</span></span>

- **`-h|--help`**

  <span data-ttu-id="6546a-146">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-146">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="6546a-147">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-147">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="6546a-148">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-148">For example, to complete authentication.</span></span> <span data-ttu-id="6546a-149">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-149">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="6546a-150">프로젝트 간(P2P) 참조를 무시하고 지정된 루트 프로젝트만 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-150">Ignores project-to-project (P2P) references and only builds the specified root project.</span></span>

- **`--no-incremental`**

  <span data-ttu-id="6546a-151">빌드를 증분 빌드에 안전하지 않은 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-151">Marks the build as unsafe for incremental build.</span></span> <span data-ttu-id="6546a-152">이 플래그로 증분 컴파일이 해제되고 프로젝트 종속성 그래프를 강제로 완전히 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-152">This flag turns off incremental compilation and forces a clean rebuild of the project's dependency graph.</span></span>

- **`--no-restore`**

  <span data-ttu-id="6546a-153">빌드하는 동안 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-153">Doesn't execute an implicit restore during build.</span></span> <span data-ttu-id="6546a-154">.NET Core 2.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-154">Available since .NET Core 2.0 SDK.</span></span>

- **`--nologo`**

  <span data-ttu-id="6546a-155">시작 배너 또는 저작권 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-155">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="6546a-156">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-156">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="6546a-157">빌드된 이진 파일을 배치할 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-157">Directory in which to place the built binaries.</span></span> <span data-ttu-id="6546a-158">이 옵션을 지정하는 경우 `--framework`도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-158">You also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="6546a-159">지정하지 않으면 기본 경로는 `./bin/<configuration>/<framework>/`입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-159">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="6546a-160">대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-160">Specifies the target runtime.</span></span> <span data-ttu-id="6546a-161">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6546a-161">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="6546a-162">MSBuild의 자세한 정도 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-162">Sets the MSBuild verbosity level.</span></span> <span data-ttu-id="6546a-163">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="6546a-164">기본값은 `minimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-164">The default is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="6546a-165">프로젝트를 빌드할 때 사용할 `$(VersionSuffix)` 속성의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-165">Sets the value of the `$(VersionSuffix)` property to use when building the project.</span></span> <span data-ttu-id="6546a-166">`$(Version)` 속성이 설정되지 않은 경우에만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-166">This only works if the `$(Version)` property isn't set.</span></span> <span data-ttu-id="6546a-167">그런 다음, `$(Version)`이 대시로 구분하여 `$(VersionSuffix)`와 결합된 `$(VersionPrefix)`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-167">Then, `$(Version)` is set to the `$(VersionPrefix)` combined with the `$(VersionSuffix)`, separated by a dash.</span></span>

## <a name="examples"></a><span data-ttu-id="6546a-168">예</span><span class="sxs-lookup"><span data-stu-id="6546a-168">Examples</span></span>

- <span data-ttu-id="6546a-169">프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-169">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet build
  ```

- <span data-ttu-id="6546a-170">릴리스 구성을 사용하여 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-170">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet build --configuration Release
  ```

- <span data-ttu-id="6546a-171">특정 런타임(이 예제의 경우 Ubuntu 18.04)에 대한 프로젝트 및 해당 종속성을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-171">Build a project and its dependencies for a specific runtime (in this example, Ubuntu 18.04):</span></span>

  ```dotnetcli
  dotnet build --runtime ubuntu.18.04-x64
  ```

- <span data-ttu-id="6546a-172">프로젝트를 빌드하고 복원 작업 중 지정된 NuGet 패키지 소스를 사용합니다(.NET Core 2.0 SDK 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="6546a-172">Build the project and use the specified NuGet package source during the restore operation (.NET Core 2.0 SDK and later versions):</span></span>

  ```dotnetcli
  dotnet build --source c:\packages\mypackages
  ```

- <span data-ttu-id="6546a-173">`-p` [MSBuild 옵션](#msbuild)을 사용하여 프로젝트를 빌드하고 버전 1.2.3.4를 빌드 매개 변수로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6546a-173">Build the project and set version 1.2.3.4 as a build parameter using the `-p` [MSBuild option](#msbuild):</span></span>

  ```dotnetcli
  dotnet build -p:Version=1.2.3.4
  ```
