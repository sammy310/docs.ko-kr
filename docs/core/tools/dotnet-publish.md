---
title: dotnet publish 명령
description: dotnet publish 명령은 .NET 프로젝트 또는 솔루션을 디렉터리에 게시합니다.
ms.date: 11/11/2020
ms.openlocfilehash: 3918c0708e207157ac33dd1a8fdefb993a1d6741
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190067"
---
# <a name="dotnet-publish"></a><span data-ttu-id="16a54-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="16a54-103">dotnet publish</span></span>

<span data-ttu-id="16a54-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="16a54-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="16a54-105">이름</span><span class="sxs-lookup"><span data-stu-id="16a54-105">Name</span></span>

<span data-ttu-id="16a54-106">`dotnet publish` - 호스팅 시스템에 배포하기 위해 애플리케이션 및 해당 종속성을 폴더에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-106">`dotnet publish` - Publishes the application and its dependencies to a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="16a54-107">개요</span><span class="sxs-lookup"><span data-stu-id="16a54-107">Synopsis</span></span>

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a><span data-ttu-id="16a54-108">설명</span><span class="sxs-lookup"><span data-stu-id="16a54-108">Description</span></span>

<span data-ttu-id="16a54-109">`dotnet publish`는 애플리케이션을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-109">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="16a54-110">출력에는 다음과 같은 자산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-110">The output includes the following assets:</span></span>

- <span data-ttu-id="16a54-111">*dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드</span><span class="sxs-lookup"><span data-stu-id="16a54-111">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="16a54-112">프로젝트의 종속성을 모두 포함하는 *.deps.json* 파일</span><span class="sxs-lookup"><span data-stu-id="16a54-112">A *.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="16a54-113">런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)과 애플리케이션에서 예상하는 공유 런타임을 지정하는 *.runtimeconfig.json* 파일</span><span class="sxs-lookup"><span data-stu-id="16a54-113">A *.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="16a54-114">애플리케이션의 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-114">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="16a54-115">`dotnet publish` 명령의 출력이 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)에 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-115">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="16a54-116">이는 배포를 위해 애플리케이션을 준비하는 데 공식적으로 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-116">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="16a54-117">프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에서 .NET 공유 런타임을 설치하거나 설치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-117">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET shared runtime installed on it.</span></span> <span data-ttu-id="16a54-118">자세한 내용은 [.NET CLI를 사용하여 .NET 앱 게시](../deploying/deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-118">For more information, see [Publish .NET apps with the .NET CLI](../deploying/deploy-with-cli.md).</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="16a54-119">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="16a54-119">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](../../../includes/dotnet-restore-note.md)]

### <a name="msbuild"></a><span data-ttu-id="16a54-120">MSBuild</span><span class="sxs-lookup"><span data-stu-id="16a54-120">MSBuild</span></span>

<span data-ttu-id="16a54-121">`dotnet publish` 명령은 `Publish` 대상을 불러오는 MSBuild를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-121">The `dotnet publish` command calls MSBuild, which invokes the `Publish` target.</span></span> <span data-ttu-id="16a54-122">`dotnet publish` 및 MSBuild에 전달된 모든 매개 변수.</span><span class="sxs-lookup"><span data-stu-id="16a54-122">Any parameters passed to `dotnet publish` are passed to MSBuild.</span></span> <span data-ttu-id="16a54-123">`-c` 및 `-o` 매개 변수는 각각 MSBuild의 `Configuration` 및 `PublishDir` 속성에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-123">The `-c` and `-o` parameters map to MSBuild's `Configuration` and `PublishDir` properties, respectively.</span></span>

<span data-ttu-id="16a54-124">`dotnet publish` 명령은 속성 설정에 대한 `-p` 및 로거를 정의하는 `-l` 같은 MSBuild 옵션을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-124">The `dotnet publish` command accepts MSBuild options, such as `-p` for setting properties and `-l` to define a logger.</span></span> <span data-ttu-id="16a54-125">예를 들어 `-p:<NAME>=<VALUE>` 형식을 사용하여 MSBuild 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-125">For example, you can set an MSBuild property by using the format: `-p:<NAME>=<VALUE>`.</span></span>

<span data-ttu-id="16a54-126">*.pubxml* 파일(.NET Core 3.1 SDK부터 제공)을 참조하여 게시 관련 속성을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-126">You can also set publish-related properties by referring to a *.pubxml* file (available since .NET Core 3.1 SDK).</span></span> <span data-ttu-id="16a54-127">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-127">For example:</span></span>

```dotnetcli
dotnet publish -p:PublishProfile=FolderProfile
```

<span data-ttu-id="16a54-128">앞의 예제에서는 *\<project_folder>/Properties/PublishProfiles* 폴더에 있는 *FolderProfile.pubxml* 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-128">The preceding example uses the *FolderProfile.pubxml* file that is found in the *\<project_folder>/Properties/PublishProfiles* folder.</span></span> <span data-ttu-id="16a54-129">`PublishProfile` 속성을 설정할 때 지정하는 경로 및 파일 확장명은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-129">If you specify a path and file extension when setting the `PublishProfile` property, they are ignored.</span></span> <span data-ttu-id="16a54-130">MSBuild는 기본적으로 *Properties/PublishProfiles* 폴더를 검색하고 *pubxml* 파일 확장명으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-130">MSBuild by default looks in the *Properties/PublishProfiles* folder and assumes the *pubxml* file extension.</span></span> <span data-ttu-id="16a54-131">확장명을 포함한 경로 및 파일 이름을 지정하려면 `PublishProfile` 속성 대신 `PublishProfileFullPath` 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-131">To specify the path and filename including extension, set the `PublishProfileFullPath` property instead of the `PublishProfile` property.</span></span>

<span data-ttu-id="16a54-132">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-132">For more information, see the following resources:</span></span>

- [<span data-ttu-id="16a54-133">MSBuild 명령줄 참조</span><span class="sxs-lookup"><span data-stu-id="16a54-133">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="16a54-134">ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)</span><span class="sxs-lookup"><span data-stu-id="16a54-134">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="16a54-135">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="16a54-135">dotnet msbuild</span></span>](dotnet-msbuild.md)

## <a name="arguments"></a><span data-ttu-id="16a54-136">인수</span><span class="sxs-lookup"><span data-stu-id="16a54-136">Arguments</span></span>

- **`PROJECT|SOLUTION`**

  <span data-ttu-id="16a54-137">게시할 프로젝트 또는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-137">The project or solution to publish.</span></span>

  * <span data-ttu-id="16a54-138">`PROJECT`는 C#, F# 또는 Visual Basic 프로젝트 파일의 경로 및 파일 이름이거나 C#, F# 또는 Visual Basic 프로젝트 파일을 포함하는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-138">`PROJECT` is the path and filename of a C#, F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="16a54-139">디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-139">If the directory is not specified, it defaults to the current directory.</span></span>

  * <span data-ttu-id="16a54-140">`SOLUTION`은 솔루션 파일 ( *.sln* 확장명)의 경로 및 파일 이름이거나 솔루션 파일을 포함하는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-140">`SOLUTION` is the path and filename of a solution file (*.sln* extension), or the path to a directory that contains a solution file.</span></span> <span data-ttu-id="16a54-141">디렉터리를 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-141">If the directory is not specified, it defaults to the current directory.</span></span> <span data-ttu-id="16a54-142">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-142">Available since .NET Core 3.0 SDK.</span></span>

## <a name="options"></a><span data-ttu-id="16a54-143">옵션</span><span class="sxs-lookup"><span data-stu-id="16a54-143">Options</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="16a54-144">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-144">Defines the build configuration.</span></span> <span data-ttu-id="16a54-145">대부분의 프로젝트에 대한 기본값은 `Debug`이지만 프로젝트의 빌드 구성 설정을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-145">The default for most projects is `Debug`, but you can override the build configuration settings in your project.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="16a54-146">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-146">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="16a54-147">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-147">You must specify the target framework in the project file.</span></span>

- **`--force`**

  <span data-ttu-id="16a54-148">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-148">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="16a54-149">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-149">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

- **`-h|--help`**

  <span data-ttu-id="16a54-150">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-150">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="16a54-151">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-151">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="16a54-152">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-152">For example, to complete authentication.</span></span> <span data-ttu-id="16a54-153">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-153">Available since .NET Core 3.0 SDK.</span></span>

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  <span data-ttu-id="16a54-154">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-154">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="16a54-155">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-155">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="16a54-156">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-156">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span>

- **`--no-build`**

  <span data-ttu-id="16a54-157">게시하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-157">Doesn't build the project before publishing.</span></span> <span data-ttu-id="16a54-158">또한 암시적으로 `--no-restore` 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-158">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="16a54-159">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-159">Ignores project-to-project references and only restores the root project.</span></span>

- **`--nologo`**

  <span data-ttu-id="16a54-160">시작 배너 또는 저작권 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-160">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="16a54-161">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-161">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="16a54-162">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-162">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="16a54-163">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-163">Specifies the path for the output directory.</span></span>
  
  <span data-ttu-id="16a54-164">지정하지 않으면 프레임워크 종속 실행 파일과 플랫폼 간 이진 파일에 대해 *[project_file_folder]/bin/[configuration]/[framework]/publish/* 로 기본 설정되고,</span><span class="sxs-lookup"><span data-stu-id="16a54-164">If not specified, it defaults to *[project_file_folder]/bin/[configuration]/[framework]/publish/* for a framework-dependent executable and cross-platform binaries.</span></span> <span data-ttu-id="16a54-165">자체 포함 실행 파일에 대해 *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-165">It defaults to *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained executable.</span></span>

  <span data-ttu-id="16a54-166">웹 프로젝트에서 출력 폴더가 프로젝트 폴더에 있는 경우 연속 `dotnet publish` 명령에서는 중첩된 출력 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-166">In a web project, if the output folder is in the project folder, successive `dotnet publish` commands result in nested output folders.</span></span> <span data-ttu-id="16a54-167">예를 들어 프로젝트 폴더가 *myproject* 이고 게시 출력 폴더가 *myproject/publish* 일 때 `dotnet publish`를 두 번 실행하면 두 번째 실행에서는 *.config* 및 *.json* 파일과 같은 콘텐츠 파일이 *myproject/publish/publish* 에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-167">For example, if the project folder is *myproject*, and the publish output folder is *myproject/publish*, and you run `dotnet publish` twice, the second run puts content files such as *.config* and *.json* files in *myproject/publish/publish*.</span></span> <span data-ttu-id="16a54-168">게시 폴더가 중첩되지 않게 하려면 프로젝트 폴더 **바로** 아래에 있지 않은 게시 폴더를 지정하거나 프로젝트에서 게시 폴더를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-168">To avoid nesting publish folders, specify a publish folder that is not **directly** under the project folder, or exclude the publish folder from the project.</span></span> <span data-ttu-id="16a54-169">*publishoutput* 이라는 게시 폴더를 제외하려면 *.csproj* 파일의 `PropertyGroup` 요소에 다음 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-169">To exclude a publish folder named *publishoutput*, add the following element to a `PropertyGroup` element in the *.csproj* file:</span></span>

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - <span data-ttu-id="16a54-170">.NET Core 3.x SDK 이상</span><span class="sxs-lookup"><span data-stu-id="16a54-170">.NET Core 3.x SDK and later</span></span>

    <span data-ttu-id="16a54-171">프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 프로젝트 파일 위치가 아니라 현재 작업 디렉터리에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-171">If you specify a relative path when publishing a project, the generated output directory is relative to the current working directory, not to the project file location.</span></span>

    <span data-ttu-id="16a54-172">솔루션을 게시할 때 상대 경로를 지정하는 경우 모든 프로젝트의 모든 출력은 현재 작업 디렉터리를 기준으로 지정된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-172">If you specify a relative path when publishing a solution, all output for all projects goes into the specified folder relative to the current working directory.</span></span> <span data-ttu-id="16a54-173">게시 출력을 각 프로젝트의 별도 폴더로 이동하려면 `--output` 옵션 대신 msbuild `PublishDir` 속성을 사용하여 상대 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-173">To make publish output go to separate folders for each project, specify a relative path by using the msbuild `PublishDir` property instead of the `--output` option.</span></span> <span data-ttu-id="16a54-174">예를 들어 `dotnet publish -p:PublishDir=.\publish`는 각 프로젝트의 게시 출력을 프로젝트 파일이 포함된 폴더 아래에 있는 `publish` 폴더로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-174">For example, `dotnet publish -p:PublishDir=.\publish` sends publish output for each project to a `publish` folder under the folder that contains the project file.</span></span>

  - <span data-ttu-id="16a54-175">.NET Core 2.x SDK</span><span class="sxs-lookup"><span data-stu-id="16a54-175">.NET Core 2.x SDK</span></span>

    <span data-ttu-id="16a54-176">프로젝트를 게시할 때 상대 경로를 지정하는 경우 생성되는 출력 디렉터리는 현재 작업 디렉터리가 아니라 프로젝트 파일 위치에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-176">If you specify a relative path when publishing a project, the generated output directory is relative to the project file location, not to the current working directory.</span></span>

    <span data-ttu-id="16a54-177">솔루션을 게시할 때 상대 경로를 지정하는 경우 각 프로젝트의 출력은 프로젝트 파일 위치에 대해 상대적인 별도의 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-177">If you specify a relative path when publishing a solution, each project's output goes into a separate folder relative to the project file location.</span></span> <span data-ttu-id="16a54-178">솔루션을 게시할 때 절대 경로를 지정하는 경우 모든 프로젝트의 모든 게시 출력은 지정된 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-178">If you specify an absolute path when publishing a solution, all publish output for all projects goes into the specified folder.</span></span>

- **`-p:PublishReadyToRun=true`**

  <span data-ttu-id="16a54-179">애플리케이션 어셈블리를 R2R(ReadyToRun) 형식으로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-179">Compiles application assemblies as ReadyToRun (R2R) format.</span></span> <span data-ttu-id="16a54-180">R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-180">R2R is a form of ahead-of-time (AOT) compilation.</span></span> <span data-ttu-id="16a54-181">자세한 내용은 [ReadyToRun 이미지](../deploying/ready-to-run.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-181">For more information, see [ReadyToRun images](../deploying/ready-to-run.md).</span></span> <span data-ttu-id="16a54-182">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-182">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="16a54-183">이 옵션은 명령줄이 아닌 게시 프로필에서 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-183">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="16a54-184">자세한 내용은 [MSBuild](#msbuild)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-184">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishSingleFile=true`**

  <span data-ttu-id="16a54-185">앱을 플랫폼별 단일 파일 실행 파일로 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-185">Packages the app into a platform-specific single-file executable.</span></span> <span data-ttu-id="16a54-186">실행 파일은 자동 압축 풀기 파일이며 앱을 실행하는 데 필요한 모든 종속 항목(네이티브 포함)을 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-186">The executable is self-extracting and contains all dependencies (including native) that are required to run the app.</span></span> <span data-ttu-id="16a54-187">앱을 처음 실행하면 애플리케이션은 앱 이름과 빌드 식별자에 기반하여 디렉터리로 압축이 풀립니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-187">When the app is first run, the application is extracted to a directory based on the app name and build identifier.</span></span> <span data-ttu-id="16a54-188">해당 애플리케이션을 다시 실행하면 시작이 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-188">Startup is faster when the application is run again.</span></span> <span data-ttu-id="16a54-189">새 버전을 사용한 경우가 아니라면 두 번째에는 애플리케이션의 압축을 풀 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-189">The application doesn't need to extract itself a second time unless a new version is used.</span></span> <span data-ttu-id="16a54-190">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-190">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="16a54-191">단일 파일 게시에 대한 자세한 내용은 [단일 파일 번들러 설계 문서](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-191">For more information about single-file publishing, see the [single-file bundler design document](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).</span></span>

  <span data-ttu-id="16a54-192">이 옵션은 명령줄이 아닌 게시 프로필에서 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-192">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="16a54-193">자세한 내용은 [MSBuild](#msbuild)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-193">For more information, see [MSBuild](#msbuild).</span></span>

- **`-p:PublishTrimmed=true`**

  <span data-ttu-id="16a54-194">자체 포함 실행 파일을 게시할 때 앱의 배포 크기를 줄이기 위해 사용되지 않는 라이브러리를 트리밍합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-194">Trims unused libraries to reduce the deployment size of an app when publishing a self-contained executable.</span></span> <span data-ttu-id="16a54-195">자세한 내용은 [자체 포함 배포 및 실행 파일 트리밍](../deploying/trim-self-contained.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-195">For more information, see [Trim self-contained deployments and executables](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="16a54-196">.NET Core 3.0 SDK부터 미리 보기 기능으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-196">Available since .NET Core 3.0 SDK as a preview feature.</span></span>

  <span data-ttu-id="16a54-197">이 옵션은 명령줄이 아닌 게시 프로필에서 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-197">We recommend that you specify this option in a publish profile rather than on the command line.</span></span> <span data-ttu-id="16a54-198">자세한 내용은 [MSBuild](#msbuild)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-198">For more information, see [MSBuild](#msbuild).</span></span>

- **`--self-contained [true|false]`**

  <span data-ttu-id="16a54-199">애플리케이션과 함께 .NET 런타임을 게시하여 대상 머신에 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-199">Publishes the .NET runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="16a54-200">런타임 식별자가 지정되고 프로젝트가 라이브러리 프로젝트가 아니라 실행 가능 프로젝트인 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-200">Default is `true` if a runtime identifier is specified and the project is an executable project (not a library project).</span></span> <span data-ttu-id="16a54-201">자세한 내용은 [.NET 애플리케이션 게시](../deploying/index.md) 및 [.NET CLI를 사용하여 .NET 앱 게시](../deploying/deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-201">For more information, see [.NET application publishing](../deploying/index.md) and [Publish .NET apps with the .NET CLI](../deploying/deploy-with-cli.md).</span></span>

  <span data-ttu-id="16a54-202">`true` 또는 `false`를 지정하지 않고 이 옵션을 사용하는 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-202">If this option is used without specifying `true` or `false`, the default is `true`.</span></span> <span data-ttu-id="16a54-203">이 경우 솔루션 또는 프로젝트 인수를 `--self-contained` 바로 뒤에 배치하지 마세요. 이 위치에 `true` 또는 `false`가 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-203">In that case, don't put the solution or project argument immediately after `--self-contained`, because `true` or `false` is expected in that position.</span></span>

- **`--no-self-contained`**

  <span data-ttu-id="16a54-204">`--self-contained false`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-204">Equivalent to `--self-contained false`.</span></span> <span data-ttu-id="16a54-205">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-205">Available since .NET Core 3.0 SDK.</span></span>

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="16a54-206">지정된 런타임에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-206">Publishes the application for a given runtime.</span></span> <span data-ttu-id="16a54-207">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-207">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="16a54-208">자세한 내용은 [.NET 애플리케이션 게시](../deploying/index.md) 및 [.NET CLI를 사용하여 .NET 앱 게시](../deploying/deploy-with-cli.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16a54-208">For more information, see [.NET application publishing](../deploying/index.md) and [Publish .NET apps with the .NET CLI](../deploying/deploy-with-cli.md).</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="16a54-209">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="16a54-210">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="16a54-211">기본값은 `minimal`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-211">Default value is `minimal`.</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="16a54-212">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-212">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

## <a name="examples"></a><span data-ttu-id="16a54-213">예</span><span class="sxs-lookup"><span data-stu-id="16a54-213">Examples</span></span>

- <span data-ttu-id="16a54-214">현재 디렉터리에 프로젝트의 [프레임워크 종속 플랫폼 간 이진 파일](../deploying/index.md#produce-a-cross-platform-binary)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-214">Create a [framework-dependent cross-platform binary](../deploying/index.md#produce-a-cross-platform-binary) for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet publish
  ```

  <span data-ttu-id="16a54-215">.NET Core 3.0 SDK부터 이 예제에서 현재 플랫폼의 [프레임워크 종속 실행 파일](../deploying/index.md#publish-framework-dependent)도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-215">Starting with .NET Core 3.0 SDK, this example also creates a [framework-dependent executable](../deploying/index.md#publish-framework-dependent) for the current platform.</span></span>

- <span data-ttu-id="16a54-216">현재 디렉터리에 있는 프로젝트에 대해 특정 런타임에 대한 [자체 포함 실행 파일](../deploying/index.md#publish-self-contained)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-216">Create a [self-contained executable](../deploying/index.md#publish-self-contained) for the project in the current directory, for a specific runtime:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  <span data-ttu-id="16a54-217">RID가 프로젝트 파일 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-217">The RID must be in the project file.</span></span>

- <span data-ttu-id="16a54-218">현재 디렉터리에 프로젝트의 특정 플랫폼용 [프레임워크 종속 실행 파일](../deploying/index.md#publish-framework-dependent)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-218">Create a [framework-dependent executable](../deploying/index.md#publish-framework-dependent) for the project in the current directory, for a specific platform:</span></span>

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  <span data-ttu-id="16a54-219">RID가 프로젝트 파일 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-219">The RID must be in the project file.</span></span> <span data-ttu-id="16a54-220">이 예제는 .NET Core 3.0 SDK 이상 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-220">This example applies to .NET Core 3.0 SDK and later versions.</span></span>

- <span data-ttu-id="16a54-221">현재 디렉터리에 있는 프로젝트를 특정 런타임 및 대상 프레임워크에 대해 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-221">Publish the project in the current directory, for a specific runtime and target framework:</span></span>

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- <span data-ttu-id="16a54-222">지정된 프로젝트 파일을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-222">Publish the specified project file:</span></span>

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- <span data-ttu-id="16a54-223">현재 애플리케이션을 게시하되 복원 작업 중에 프로젝트 간(P2P) 참조는 복원하지 않고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="16a54-223">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation:</span></span>

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a><span data-ttu-id="16a54-224">참조</span><span class="sxs-lookup"><span data-stu-id="16a54-224">See also</span></span>

- [<span data-ttu-id="16a54-225">.NET 애플리케이션 게시 개요</span><span class="sxs-lookup"><span data-stu-id="16a54-225">.NET application publishing overview</span></span>](../deploying/index.md)
- [<span data-ttu-id="16a54-226">.NET CLI를 사용하여 .NET 앱 게시</span><span class="sxs-lookup"><span data-stu-id="16a54-226">Publish .NET apps with the .NET CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="16a54-227">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="16a54-227">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="16a54-228">RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="16a54-228">Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="16a54-229">macOS Catalina 공증 관련 사항</span><span class="sxs-lookup"><span data-stu-id="16a54-229">Working with macOS Catalina Notarization</span></span>](../install/macos-notarization-issues.md)
- <span data-ttu-id="16a54-230">[Directory structure of a published application](/aspnet/core/hosting/directory-structure)(게시된 애플리케이션의 디렉터리 구조)</span><span class="sxs-lookup"><span data-stu-id="16a54-230">[Directory structure of a published application](/aspnet/core/hosting/directory-structure)</span></span>
- [<span data-ttu-id="16a54-231">MSBuild 명령줄 참조</span><span class="sxs-lookup"><span data-stu-id="16a54-231">MSBuild command-line reference</span></span>](/visualstudio/msbuild/msbuild-command-line-reference)
- [<span data-ttu-id="16a54-232">ASP.NET Core 앱 배포용 Visual Studio 게시 프로필(.pubxml)</span><span class="sxs-lookup"><span data-stu-id="16a54-232">Visual Studio publish profiles (.pubxml) for ASP.NET Core app deployment</span></span>](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [<span data-ttu-id="16a54-233">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="16a54-233">dotnet msbuild</span></span>](dotnet-msbuild.md)
- [<span data-ttu-id="16a54-234">ILLInk.Tasks</span><span class="sxs-lookup"><span data-stu-id="16a54-234">ILLInk.Tasks</span></span>](../deploying/trim-self-contained.md)
