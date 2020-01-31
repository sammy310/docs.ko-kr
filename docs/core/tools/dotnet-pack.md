---
title: dotnet pack 명령
description: dotnet pack 명령은 .NET Core 프로젝트에 대한 NuGet 패키지를 만듭니다.
ms.date: 08/08/2019
ms.openlocfilehash: 057d1029e5c933912c43c178b6db8a8498f2ed57
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734115"
---
# <a name="dotnet-pack"></a><span data-ttu-id="2e815-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="2e815-103">dotnet pack</span></span>

<span data-ttu-id="2e815-104">**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="2e815-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="2e815-105">이름</span><span class="sxs-lookup"><span data-stu-id="2e815-105">Name</span></span>

<span data-ttu-id="2e815-106">`dotnet pack` - 코드를 NuGet 패키지로 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-106">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2e815-107">개요</span><span class="sxs-lookup"><span data-stu-id="2e815-107">Synopsis</span></span>

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo] [-o|--output] [--runtime] [-s|--serviceable]
    [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

## <a name="description"></a><span data-ttu-id="2e815-108">설명</span><span class="sxs-lookup"><span data-stu-id="2e815-108">Description</span></span>

<span data-ttu-id="2e815-109">`dotnet pack` 명령은 프로젝트를 빌드하고 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-109">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="2e815-110">이 명령의 결과가 NuGet 패키지(즉, *.nupkg* 파일)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-110">The result of this command is a NuGet package (that is, a *.nupkg* file).</span></span>

<span data-ttu-id="2e815-111">디버그 기호를 포함하는 패키지를 만들려면 다음 두 가지 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-111">If you want to generate a package that contains the debug symbols, you have two options available:</span></span>

- <span data-ttu-id="2e815-112">`--include-symbols` - 기호 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-112">`--include-symbols` - it creates the symbols package.</span></span>
- <span data-ttu-id="2e815-113">`--include-source` - 내부에 원본 파일이 포함된 `src` 폴더가 있는 기호 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-113">`--include-source` - it creates the symbols package with a `src` folder inside containing the source files.</span></span>

<span data-ttu-id="2e815-114">압축된 프로젝트의 NuGet 종속성은 *.nuspec* 파일에 추가되므로 패키지를 설치할 때 적절히 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-114">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="2e815-115">프로젝트 간 참조는 프로젝트 내에서 패키지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-115">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="2e815-116">현재 프로젝트 간 종속성이 있는 경우 프로젝트당 패키지가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-116">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="2e815-117">`dotnet pack`은 기본적으로 프로젝트를 먼저 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-117">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="2e815-118">이렇게 하지 않으려면 `--no-build` 옵션을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-118">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="2e815-119">이 옵션은 코드가 이미 빌드된 CI(연속 통합) 빌드 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-119">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="2e815-120">압축 프로세스에 대한 `dotnet pack` 명령에 MSBuild 속성을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-120">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="2e815-121">자세한 내용은 [NuGet 메타데이터 속성](csproj.md#nuget-metadata-properties) 및 [MSBuild 명령줄 참조](/visualstudio/msbuild/msbuild-command-line-reference)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e815-121">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="2e815-122">[예제](#examples) 섹션에서는 몇 가지 시나리오에 MSBuild -p 스위치를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-122">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="2e815-123">웹 프로젝트는 기본적으로 패키지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-123">Web projects aren't packable by default.</span></span> <span data-ttu-id="2e815-124">기본 동작을 재정의하려면 다음 속성을 *.csproj* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-124">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="2e815-125">인수</span><span class="sxs-lookup"><span data-stu-id="2e815-125">Arguments</span></span>

`PROJECT | SOLUTION`

  <span data-ttu-id="2e815-126">압축할 프로젝트 또는 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-126">The project or solution to pack.</span></span> <span data-ttu-id="2e815-127">[csproj 파일](csproj.md), 솔루션 파일 또는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-127">It's either a path to a [csproj file](csproj.md), a solution file, or to a directory.</span></span> <span data-ttu-id="2e815-128">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 또는 솔루션 파일을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-128">If not specified, the command searches the current directory for a project or solution file.</span></span>

## <a name="options"></a><span data-ttu-id="2e815-129">옵션</span><span class="sxs-lookup"><span data-stu-id="2e815-129">Options</span></span>

- **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="2e815-130">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-130">Defines the build configuration.</span></span> <span data-ttu-id="2e815-131">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-131">The default value is `Debug`.</span></span>

- **`--force`**

  <span data-ttu-id="2e815-132">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="2e815-133">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span> <span data-ttu-id="2e815-134">.NET Core 2.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-134">Option available since .NET Core 2.0 SDK.</span></span>

- **`-h|--help`**

  <span data-ttu-id="2e815-135">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-135">Prints out a short help for the command.</span></span>

- **`--include-source`**

  <span data-ttu-id="2e815-136">출력 디렉터리에 일반 NuGet 패키지 외에 디버그 기호 NuGet 패키지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-136">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span> <span data-ttu-id="2e815-137">원본 파일은 기호 패키지 내 `src` 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-137">The sources files are included in the `src` folder within the symbols package.</span></span>

- **`--include-symbols`**

  <span data-ttu-id="2e815-138">출력 디렉터리에 일반 NuGet 패키지 외에 디버그 기호 NuGet 패키지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-138">Includes the debug symbols NuGet packages in addition to the regular NuGet packages in the output directory.</span></span>

- **`--interactive`**

  <span data-ttu-id="2e815-139">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="2e815-139">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="2e815-140">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-140">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-build`**

  <span data-ttu-id="2e815-141">압축하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-141">Doesn't build the project before packing.</span></span> <span data-ttu-id="2e815-142">또한 암시적으로 `--no-restore` 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-142">It also implicitly sets the `--no-restore` flag.</span></span>

- **`--no-dependencies`**

  <span data-ttu-id="2e815-143">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-143">Ignores project-to-project references and only restores the root project.</span></span> <span data-ttu-id="2e815-144">.NET Core 2.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-144">Option available since .NET Core 2.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="2e815-145">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-145">Doesn't execute an implicit restore when running the command.</span></span> <span data-ttu-id="2e815-146">.NET Core 2.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-146">Option available since .NET Core 2.0 SDK.</span></span>

- **`--nologo`**

  <span data-ttu-id="2e815-147">시작 배너 또는 저작권 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-147">Doesn't display the startup banner or the copyright message.</span></span> <span data-ttu-id="2e815-148">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-148">Available since .NET Core 3.0 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="2e815-149">지정된 디렉터리에 빌드된 패키지를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-149">Places the built packages in the directory specified.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="2e815-150">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-150">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="2e815-151">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e815-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="2e815-152">.NET Core 2.0 SDK 이후 사용할 수 있는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-152">Option available since .NET Core 2.0 SDK.</span></span>

- **`-s|--serviceable`**

  <span data-ttu-id="2e815-153">패키지에 서비스 가능 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-153">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="2e815-154">자세한 내용은 [.NET 블로그: .NET 4.5.1에서 .NET NuGet 라이브러리에 대한 Microsoft 보안 업데이트를 지원함](https://aka.ms/nupkgservicing)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e815-154">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

- **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="2e815-155">프로젝트에서 `$(VersionSuffix)` MSBuild 속성에 대한 값을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-155">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="2e815-156">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-156">Sets the verbosity level of the command.</span></span> <span data-ttu-id="2e815-157">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-157">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

## <a name="examples"></a><span data-ttu-id="2e815-158">예</span><span class="sxs-lookup"><span data-stu-id="2e815-158">Examples</span></span>

- <span data-ttu-id="2e815-159">현재 디렉터리에 있는 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-159">Pack the project in the current directory:</span></span>

  ```dotnetcli
  dotnet pack
  ```

- <span data-ttu-id="2e815-160">`app1` 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-160">Pack the `app1` project:</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- <span data-ttu-id="2e815-161">현재 디렉터리에 있는 프로젝트를 압축하고 결과 패키지를 `nupkgs` 폴더에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-161">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- <span data-ttu-id="2e815-162">현재 디렉터리에 있는 프로젝트를 `nupkgs` 폴더로 압축하고 빌드 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-162">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- <span data-ttu-id="2e815-163">*.csproj* 파일에서 프로젝트의 버전 접미사를 `<VersionSuffix>$(VersionSuffix)</VersionSuffix>`로 구성한 상태로 현재 프로젝트를 압축하고 결과 패키지 버전을 지정된 접미사로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-163">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- <span data-ttu-id="2e815-164">`PackageVersion` MSBuild 속성을 사용하여 패키지 버전을 `2.1.0`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-164">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- <span data-ttu-id="2e815-165">특정 [대상 프레임워크](../../standard/frameworks.md)에 대한 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-165">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- <span data-ttu-id="2e815-166">프로젝트를 압축하고 복원 작업에 대한 특정 런타임(Windows 10)을 사용합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="2e815-166">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- <span data-ttu-id="2e815-167">[.nuspec 파일](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec)을 사용하여 프로젝트를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2e815-167">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```
