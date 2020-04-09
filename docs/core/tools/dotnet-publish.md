---
title: dotnet publish 명령
description: dotnet publish 명령은 .NET Core 프로젝트 또는 솔루션을 디렉터리에 게시합니다.
ms.date: 02/24/2020
ms.openlocfilehash: 0e18220443f3713c86c257fcf401b98ddd716ebc
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588276"
---
# <a name="dotnet-publish"></a><span data-ttu-id="67a49-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="67a49-103">dotnet publish</span></span>

<span data-ttu-id="67a49-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="67a49-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="67a49-105">이름</span><span class="sxs-lookup"><span data-stu-id="67a49-105">Name</span></span>

<span data-ttu-id="67a49-106">`dotnet publish` - 호스팅 시스템에 배포하기 위해 애플리케이션 및 해당 종속성을 폴더에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="67a49-107">개요</span><span class="sxs-lookup"><span data-stu-id="67a49-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration]
    [-f|--framework] [--force] [--interactive] [--manifest]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output] [-r|--runtime] [--self-contained]
    [--no-self-contained] [-v|--verbosity] [--version-suffix]

dotnet publish [-h|--help]
```

## <a name="description"></a><span data-ttu-id="67a49-108">설명</span><span class="sxs-lookup"><span data-stu-id="67a49-108">Description</span></span>

<span data-ttu-id="67a49-109">`dotnet publish`는 애플리케이션을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="67a49-110">출력에는 다음과 같은 자산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-110">The output includes the following assets:</span></span>

- <span data-ttu-id="67a49-111">*dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드</span><span class="sxs-lookup"><span data-stu-id="67a49-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="67a49-112">프로젝트의 종속성을 모두 포함하는 *.deps.json* 파일</span><span class="sxs-lookup"><span data-stu-id="67a49-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="67a49-113">런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)과 애플리케이션에서 예상하는 공유 런타임을 지정하는 *.runtimeconfig.json* 파일</span><span class="sxs-lookup"><span data-stu-id="67a49-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="67a49-114">애플리케이션의 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="67a49-115">`dotnet publish` 명령의 출력이 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)에 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="67a49-116">이는 배포를 위해 애플리케이션을 준비하는 데 공식적으로 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="67a49-117">프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="67a49-118">자세한 내용은 [.NET Core CLI를 사용하여 .NET Core 앱 게시](../deploying/deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a49-118">For more information, see [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="msbuild"></a><span data-ttu-id="67a49-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="67a49-119">MSBuild</span></span>

<span data-ttu-id="67a49-120">`dotnet publish` 명령은 `Publish` 대상을 불러오는 MSBuild를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-120">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="67a49-121">`dotnet publish` 및 MSBuild에 전달된 모든 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="67a49-121">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="67a49-122">`-c` 및 `-o` 매개 변수는 각각 MSBuild의 `Configuration` 및 `OutputPath` 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-122">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `OutputPath` properties, respectively.</span></span>

<span data-ttu-id="67a49-123">`dotnet publish` 명령은 속성 설정에 대한 `-p` 및 로거를 정의하는 `-l` 같은 MSBuild 옵션을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-123">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="67a49-124">예를 들어 `-p:<NAME>=<VALUE>` 형식을 사용하여 MSBuild 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-124">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span> <span data-ttu-id="67a49-125">*.pubxml* 파일을 참조하여 게시 관련 속성을 설정할 수도 있습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-125">You can also set publish-related properties by referring to a *.pubxml* file, for example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

<span data-ttu-id="67a49-126">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a49-126">For more information, see the following resources:</span></span>

- [<span data-ttu-id="67a49-127">MSBuild 명령줄 참조</span><span class="sxs-lookup"><span data-stu-id="67a49-127">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="67a49-128">ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)</span><span class="sxs-lookup"><span data-stu-id="67a49-128">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="67a49-129">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="67a49-129">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="67a49-130">인수</span><span class="sxs-lookup"><span data-stu-id="67a49-130">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="67a49-131">게시할 프로젝트 또는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-131">The project or solution to publish.</span></span>
  
  * <span data-ttu-id="67a49-132">`PROJECT`는 [C#](csproj.md), F# 또는 Visual Basic 프로젝트 파일의 경로 및 파일 이름이거나 C#, F# 또는 Visual Basic 프로젝트 파일을 포함하는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-132">`PROJECT` is the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="67a49-133">디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-133">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="67a49-134">`SOLUTION`은 솔루션 파일 ( *.sln* 확장명)의 경로 및 파일 이름이거나 솔루션 파일을 포함하는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-134">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="67a49-135">디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-135">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="67a49-136">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-136">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="67a49-137">옵션</span><span class="sxs-lookup"><span data-stu-id="67a49-137">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="67a49-138">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-138">Defines the build configuration.</span></span> <span data-ttu-id="67a49-139">대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-139">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="67a49-140">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-140">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="67a49-141">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-141">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="67a49-142">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-142">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="67a49-143">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-143">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="67a49-144">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-144">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="67a49-145">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-145">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="67a49-146">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-146">For example, to complete authentication.</span></span> <span data-ttu-id="67a49-147">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-147">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="67a49-148">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-148">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="67a49-149">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-149">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="67a49-150">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-150">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="67a49-151">게시하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-151">Doesn't build the project before publishing.</span></span> <span data-ttu-id="67a49-152">또한 암시적으로 `--no-restore` 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-152">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="67a49-153">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-153">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="67a49-154">시작 배너 또는 저작권 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-154">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="67a49-155">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-155">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="67a49-156">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-156">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="67a49-157">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-157">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="67a49-158">지정하지 않으면 런타임 종속 실행 파일과 플랫폼 간 이진 파일에 대해 *[project_file_folder]./bin/[configuration]/[framework]/publish/* 로 기본 설정되고</span><span class="sxs-lookup"><span data-stu-id="67a49-158">If not specified, it defaults to *[project_file_folder]./bin/[configuration]/[framework]/publish/* for a runtime-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="67a49-159">자체 포함 실행 파일에 대해 *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-159">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  - <span data-ttu-id="67a49-160">.NET Core 3.x SDK 이상</span><span class="sxs-lookup"><span data-stu-id="67a49-160">.NET Core 3.x SDK and later</span></span>
  
    <span data-ttu-id="67a49-161">프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 프로젝트 파일 위치가 아니라 현재 작업 디렉터리에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-161">If a relative path is specified when publishing a project, the output directory generated is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="67a49-162">솔루션을 게시할 때 상대 경로를 지정하는 경우 모든 프로젝트에 대한 모든 출력은 현재 작업 디렉터리에 대해 상대적인 지정 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-162">If a relative path is specified when publishing a solution, all output for all projects go into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="67a49-163">게시 출력을 각 프로젝트의 별도 폴더로 이동하려면 `--output` 옵션 대신 msbuild `PublishDir` 속성을 사용하여 상대 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-163">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="67a49-164">예를 들어 `dotnet publish -p:PublishDir=.\publish`는 각 프로젝트의 게시 출력을 프로젝트 파일이 포함된 폴더 아래에 있는 `publish` 폴더로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-164">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="67a49-165">.NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="67a49-165">.NET Core 2.x SDK</span></span>
  
    <span data-ttu-id="67a49-166">프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 현재 작업 디렉터리가 아니라 프로젝트 파일 위치에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-166">If a relative path is specified when publishing a project, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="67a49-167">솔루션을 게시할 때 상대 경로를 지정하는 경우 각 프로젝트의 출력은 프로젝트 파일 위치에 대해 상대적인 별도의 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-167">If a relative path is specified when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="67a49-168">솔루션을 게시할 때 절대 경로를 지정하는 경우 모든 프로젝트에 대한 모든 게시 출력은 지정된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-168">If an absolute path is specified when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="67a49-169">대상 컴퓨터에 런타임을 설치할 필요가 없도록 애플리케이션을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-169">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="67a49-170">런타임 식별자가 지정되고 프로젝트가 라이브러리 프로젝트가 아니라 실행 가능 프로젝트인 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-170">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="67a49-171">자세한 내용은 [.NET Core application publishing](../deploying/index.md)(.NET Core 애플리케이션 게시) 및 [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)(.NET Core CLI를 사용하여 .NET Core 앱 게시)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a49-171">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="67a49-172">`true` 또는 `false`를 지정하지 않고 이 옵션을 사용하는 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-172">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="67a49-173">이 경우 솔루션 또는 프로젝트 인수를 `--self-contained` 바로 뒤에 배치하지 마세요. 이 위치에 `true` 또는 `false`가 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-173">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="67a49-174">`--self-contained false`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-174">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="67a49-175">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-175">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="67a49-176">지정된 런타임에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="67a49-177">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a49-177">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="67a49-178">자세한 내용은 [.NET Core application publishing](../deploying/index.md)(.NET Core 애플리케이션 게시) 및 [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md)(.NET Core CLI를 사용하여 .NET Core 앱 게시)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67a49-178">For more information, see [.NET Core application publishing](../deploying/index.md) and [Publish .NET Core apps with the .NET Core CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="67a49-179">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="67a49-180">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="67a49-181">기본값은 `minimal`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-181">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="67a49-182">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="67a49-183">예</span><span class="sxs-lookup"><span data-stu-id="67a49-183">Examples</span></span>

- <span data-ttu-id="67a49-184">현재 디렉터리에 있는 프로젝트에 대해 [런타임 종속 플랫폼 간 이진 파일](../deploying/index.md#produce-a-cross-platform-binary)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-184">Create a [runtime-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="67a49-185">.NET Core 3.0 SDK부터, 이 예제는 현재 플랫폼에 대해 [런타임 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-185">Starting with .NET Core 3.0 SDK, this example also creates a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the current platform.</span></span>

- <span data-ttu-id="67a49-186">현재 디렉터리에 있는 프로젝트에 대해 특정 런타임에 대한 [자체 포함 실행 파일](../deploying/index.md#publish-self-contained)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-186">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="67a49-187">RID가 프로젝트 파일 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-187">The RID must be in the project file.</span></span>

- <span data-ttu-id="67a49-188">현재 디렉터리에 있는 프로젝트에 대해 특정 플랫폼에 대한 [런타임 종속 실행 파일](../deploying/index.md#publish-runtime-dependent)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-188">Create a [runtime-dependent executable](../deploying/index.md#publish-runtime-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="67a49-189">RID가 프로젝트 파일 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-189">The RID must be in the project file.</span></span> <span data-ttu-id="67a49-190">이 예제는 .NET Core 3.0 SDK 이상 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-190">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="67a49-191">현재 디렉터리에 있는 프로젝트를 특정 런타임 및 대상 프레임워크에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-191">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="67a49-192">지정된 프로젝트 파일을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-192">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="67a49-193">현재 애플리케이션을 게시하되 복원 작업 중에 프로젝트 간(P2P) 참조는 복원하지 않고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="67a49-193">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="67a49-194">참조</span><span class="sxs-lookup"><span data-stu-id="67a49-194">See also</span></span>

- <span data-ttu-id="67a49-195">[.NET Core application publishing overview](../deploying/index.md)(.NET Core 애플리케이션 게시 개요)</span><span class="sxs-lookup"><span data-stu-id="67a49-195">[.NET Core application publishing overview](../deploying/index.md)</span></span>
- [<span data-ttu-id="67a49-196">.NET Core CLI를 사용하여 .NET Core 앱 게시</span><span class="sxs-lookup"><span data-stu-id="67a49-196">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="67a49-197">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="67a49-197">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="67a49-198">RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="67a49-198">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="67a49-199">macOS Catalina 공증 관련 사항</span><span class="sxs-lookup"><span data-stu-id="67a49-199">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- <span data-ttu-id="67a49-200">[Directory structure of a published application](/aspnet/core/hosting/directory-structure)(게시된 애플리케이션의 디렉터리 구조)</span><span class="sxs-lookup"><span data-stu-id="67a49-200">[Directory structure of a published application](/aspnet/core/hosting/directory-structure)</span></span>
- [<span data-ttu-id="67a49-201">MSBuild 명령줄 참조</span><span class="sxs-lookup"><span data-stu-id="67a49-201">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="67a49-202">ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)</span><span class="sxs-lookup"><span data-stu-id="67a49-202">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="67a49-203">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="67a49-203">dotnet msbuild</span></span>](dotnet-msbuild.md)
