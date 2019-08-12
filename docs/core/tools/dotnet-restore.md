---
title: dotnet restore 명령
description: dotnet restore 명령을 사용하여 종속성 및 프로젝트 관련 도구를 복원하는 방법을 알아봅니다.
ms.date: 05/29/2018
ms.openlocfilehash: 17bbbe33e7cb7b13d6fb1c0e44bb77dd2bbe7020
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626345"
---
# <a name="dotnet-restore"></a><span data-ttu-id="79413-103">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="79413-103">dotnet restore</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="79413-104">name</span><span class="sxs-lookup"><span data-stu-id="79413-104">Name</span></span>

<span data-ttu-id="79413-105">`dotnet restore` - 프로젝트의 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-105">`dotnet restore` - Restores the dependencies and tools of a project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="79413-106">개요</span><span class="sxs-lookup"><span data-stu-id="79413-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="79413-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="79413-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity] [--interactive]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="79413-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="79413-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache]
    [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="79413-109">설명</span><span class="sxs-lookup"><span data-stu-id="79413-109">Description</span></span>

<span data-ttu-id="79413-110">`dotnet restore` 명령은 NuGet을 사용하여 프로젝트 파일에 지정된 종속성 및 프로젝트 관련 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-110">The `dotnet restore` command uses NuGet to restore dependencies as well as project-specific tools that are specified in the project file.</span></span> <span data-ttu-id="79413-111">기본적으로 종속성 및 도구의 복원은 병렬로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-111">By default, the restoration of dependencies and tools are executed in parallel.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="79413-112">종속성을 복원하려면 NuGet에 패키지가 있는 피드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-112">To restore the dependencies, NuGet needs the feeds where the packages are located.</span></span> <span data-ttu-id="79413-113">피드는 일반적으로 *nuget.config* 구성 파일을 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-113">Feeds are usually provided via the *nuget.config* configuration file.</span></span> <span data-ttu-id="79413-114">CLI 도구가 설치될 때 기본 구성 파일이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-114">A default configuration file is provided when the CLI tools are installed.</span></span> <span data-ttu-id="79413-115">프로젝트 디렉터리에 고유한 *nuget.config* 파일을 만들어 추가 피드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-115">You specify additional feeds by creating your own *nuget.config* file in the project directory.</span></span> <span data-ttu-id="79413-116">또한 명령 프롬프트에서 호출당 추가 피드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-116">You also specify additional feeds per invocation at a command prompt.</span></span>

<span data-ttu-id="79413-117">종속성의 경우 복원 작업 중 `--packages` 인수를 사용하여 복원된 패키지가 배치될 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-117">For dependencies, you specify where the restored packages are placed during the restore operation using the `--packages` argument.</span></span> <span data-ttu-id="79413-118">지정하지 않으면 모든 운영 체제에서 사용자의 홈 디렉터리의 `.nuget/packages` 디렉터리에 있는 기본 NuGet 패키지 캐시가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-118">If not specified, the default NuGet package cache is used, which is found in the `.nuget/packages` directory in the user's home directory on all operating systems.</span></span> <span data-ttu-id="79413-119">예를 들어 Linux의 경우 */home/user1* 또는 Windows의 경우 *C:\Users\user1*입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-119">For example, */home/user1* on Linux or *C:\Users\user1* on Windows.</span></span>

<span data-ttu-id="79413-120">프로젝트 관련 도구의 경우 `dotnet restore`는 먼저 도구가 압축된 패키지를 복원한 다음 프로젝트 파일에 지정된 대로 도구의 종속성을 계속 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-120">For project-specific tooling, `dotnet restore` first restores the package in which the tool is packed, and then proceeds to restore the tool's dependencies as specified in its project file.</span></span>

### <a name="nugetconfig-differences"></a><span data-ttu-id="79413-121">nuget 구성 차이점</span><span class="sxs-lookup"><span data-stu-id="79413-121">nuget.config differences</span></span>

<span data-ttu-id="79413-122">`dotnet restore` 명령의 동작은 있는 경우 *nuget.config* 파일에 있는 일부 설정의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-122">The behavior of the `dotnet restore` command is affected by the settings in the *nuget.config* file, if present.</span></span> <span data-ttu-id="79413-123">예를 들어 *nuget.config*의 `globalPackagesFolder`를 설정하면 복원된 NuGet 패키지가 지정한 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-123">For example, setting the `globalPackagesFolder` in *nuget.config* places the restored NuGet packages in the specified folder.</span></span> <span data-ttu-id="79413-124">`dotnet restore` 명령의 `--packages` 옵션을 지정하는 대신 이 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-124">This is an alternative to specifying the `--packages` option on the `dotnet restore` command.</span></span> <span data-ttu-id="79413-125">자세한 내용은 [nuget.config 참조](/nuget/schema/nuget-config-file)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79413-125">For more information, see the [nuget.config reference](/nuget/schema/nuget-config-file).</span></span>

<span data-ttu-id="79413-126">`dotnet restore`에서 무시하는 3가지 특정 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-126">There are three specific settings that `dotnet restore` ignores:</span></span>

* [<span data-ttu-id="79413-127">bindingRedirects</span><span class="sxs-lookup"><span data-stu-id="79413-127">bindingRedirects</span></span>](/nuget/schema/nuget-config-file#bindingredirects-section)

  <span data-ttu-id="79413-128">바인딩 리디렉션은 `<PackageReference>` 요소에서 작동하지 않으며 .NET Core에서는 NuGet 패키지의 `<PackageReference>` 요소만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-128">Binding redirects don't work with `<PackageReference>` elements and .NET Core only supports `<PackageReference>` elements for NuGet packages.</span></span>

* [<span data-ttu-id="79413-129">솔루션</span><span class="sxs-lookup"><span data-stu-id="79413-129">solution</span></span>](/nuget/schema/nuget-config-file#solution-section)

  <span data-ttu-id="79413-130">이 설정은 Visual Studio에만 적용되며 .NET Core에는 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-130">This setting is Visual Studio specific and doesn't apply to .NET Core.</span></span> <span data-ttu-id="79413-131">.NET Core에서는 `packages.config` 파일을 사용하지 않고, 대신 NuGet 패키지의 `<PackageReference>` 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-131">.NET Core doesn't use a `packages.config` file and instead uses `<PackageReference>` elements for NuGet packages.</span></span>

* [<span data-ttu-id="79413-132">trustedSigners</span><span class="sxs-lookup"><span data-stu-id="79413-132">trustedSigners</span></span>](/nuget/schema/nuget-config-file#trustedsigners-section)

  <span data-ttu-id="79413-133">신뢰할 수 있는 패키지의 [플랫폼 간 확인은 NuGet에서 지원하지 않기](https://github.com/NuGet/Home/issues/7939) 때문에 이 설정은 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-133">This setting isn't applicable as [NuGet doesn't yet support cross-platform verification](https://github.com/NuGet/Home/issues/7939) of trusted packages.</span></span>

## <a name="implicit-dotnet-restore"></a><span data-ttu-id="79413-134">암시적 `dotnet restore`</span><span class="sxs-lookup"><span data-stu-id="79413-134">Implicit `dotnet restore`</span></span>

<span data-ttu-id="79413-135">.NET Core 2.0부터는 다음 명령을 실행할 때 필요한 경우 `dotnet restore`가 암시적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-135">Starting with .NET Core 2.0, `dotnet restore` is run implicitly if necessary when you issue the following commands:</span></span>

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet build-server`](dotnet-build-server.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

<span data-ttu-id="79413-136">대부분의 경우 더 이상 `dotnet restore` 명령을 명시적으로 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-136">In most cases, you no longer need to explicitly use the `dotnet restore` command.</span></span>

<span data-ttu-id="79413-137">때때로 `dotnet restore`를 암시적으로 실행하는 것이 불편할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-137">Sometimes, it might be inconvenient to run `dotnet restore` implicitly.</span></span> <span data-ttu-id="79413-138">예를 들어 빌드 시스템과 같은 자동화된 일부 시스템은 네트워크 사용량을 제어할 수 있도록 복원이 발생하는 경우를 제어하기 위해 명시적으로 `dotnet restore`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-138">For example, some automated systems, such as build systems, need to call `dotnet restore` explicitly to control when the restore occurs so that they can control network usage.</span></span> <span data-ttu-id="79413-139">`dotnet restore`가 암시적으로 실행되지 않게 하려면 이러한 명령 중 하나와 함께 `--no-restore` 플래그를 사용하여 암시적 복원을 사용하지 않도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-139">To prevent `dotnet restore` from running implicitly, you can use the `--no-restore` flag with any of these commands to disable implicit restore.</span></span>

## <a name="arguments"></a><span data-ttu-id="79413-140">인수</span><span class="sxs-lookup"><span data-stu-id="79413-140">Arguments</span></span>

`ROOT`

<span data-ttu-id="79413-141">프로젝트 파일을 복원하는 선택적 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-141">Optional path to the project file to restore.</span></span>

## <a name="options"></a><span data-ttu-id="79413-142">옵션</span><span class="sxs-lookup"><span data-stu-id="79413-142">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="79413-143">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="79413-143">.NET Core 2.x</span></span>](#tab/netcore2x)

`--configfile <FILE>`

<span data-ttu-id="79413-144">복원 작업에 사용할 NuGet 구성 파일(*NuGet.config*)입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-144">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="79413-145">여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-145">Disables restoring multiple projects in parallel.</span></span>

`--force`

<span data-ttu-id="79413-146">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-146">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="79413-147">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-147">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="79413-148">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-148">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="79413-149">버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-149">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="79413-150">패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-150">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="79413-151">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="79413-151">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="79413-152">복원된 패키지에 대한 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-152">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="79413-153">패키지 복원의 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-153">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="79413-154">*.csproj* 파일의 `<RuntimeIdentifiers>` 태그에 명시적으로 나열되지 않은 런타임의 패키지를 복원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-154">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="79413-155">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79413-155">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="79413-156">이 옵션을 여러 번 지정하여 여러 RID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-156">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="79413-157">복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-157">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="79413-158">이 설정은 *nuget.config* 파일에 지정된 모든 소스를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-158">This setting overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="79413-159">이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-159">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="79413-160">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-160">Sets the verbosity level of the command.</span></span> <span data-ttu-id="79413-161">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-161">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--interactive`

<span data-ttu-id="79413-162">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="79413-162">Allows the command to stop and wait for user input or action (for example to complete authentication).</span></span> <span data-ttu-id="79413-163">.NET Core 2.1.400 이후입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-163">Since .NET Core 2.1.400.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="79413-164">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="79413-164">.NET Core 1.x</span></span>](#tab/netcore1x)

`--configfile <FILE>`

<span data-ttu-id="79413-165">복원 작업에 사용할 NuGet 구성 파일(*NuGet.config*)입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-165">The NuGet configuration file (*nuget.config*) to use for the restore operation.</span></span>

`--disable-parallel`

<span data-ttu-id="79413-166">여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-166">Disables restoring multiple projects in parallel.</span></span>

`-h|--help`

<span data-ttu-id="79413-167">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-167">Prints out a short help for the command.</span></span>

`--ignore-failed-sources`

<span data-ttu-id="79413-168">버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-168">Only warn about failed sources if there are packages meeting the version requirement.</span></span>

`--no-cache`

<span data-ttu-id="79413-169">패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-169">Specifies to not cache packages and HTTP requests.</span></span>

`--no-dependencies`

<span data-ttu-id="79413-170">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="79413-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--packages <PACKAGES_DIRECTORY>`

<span data-ttu-id="79413-171">복원된 패키지에 대한 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-171">Specifies the directory for restored packages.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="79413-172">패키지 복원의 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-172">Specifies a runtime for the package restore.</span></span> <span data-ttu-id="79413-173">*.csproj* 파일의 `<RuntimeIdentifiers>` 태그에 명시적으로 나열되지 않은 런타임의 패키지를 복원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="79413-173">This is used to restore packages for runtimes not explicitly listed in the `<RuntimeIdentifiers>` tag in the *.csproj* file.</span></span> <span data-ttu-id="79413-174">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79413-174">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="79413-175">이 옵션을 여러 번 지정하여 여러 RID를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-175">Provide multiple RIDs by specifying this option multiple times.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="79413-176">복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-176">Specifies a NuGet package source to use during the restore operation.</span></span> <span data-ttu-id="79413-177">이 소스는 *nuget.config* 파일에 지정된 모든 소스를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-177">This overrides all of the sources specified in the *nuget.config* files.</span></span> <span data-ttu-id="79413-178">이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79413-178">Multiple sources can be provided by specifying this option multiple times.</span></span>

`--verbosity <LEVEL>`

<span data-ttu-id="79413-179">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-179">Sets the verbosity level of the command.</span></span> <span data-ttu-id="79413-180">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="79413-180">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="79413-181">예제</span><span class="sxs-lookup"><span data-stu-id="79413-181">Examples</span></span>

<span data-ttu-id="79413-182">현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-182">Restore dependencies and tools for the project in the current directory:</span></span>

`dotnet restore`

<span data-ttu-id="79413-183">지정된 경로에 있는 `app1` 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-183">Restore dependencies and tools for the `app1` project found in the given path:</span></span>

`dotnet restore ~/projects/app1/app1.csproj`

<span data-ttu-id="79413-184">소스로 제공된 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-184">Restore the dependencies and tools for the project in the current directory using the file path provided as the source:</span></span>

`dotnet restore -s c:\packages\mypackages`

<span data-ttu-id="79413-185">소스로 제공된 2개의 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-185">Restore the dependencies and tools for the project in the current directory using the two file paths provided as sources:</span></span>

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

<span data-ttu-id="79413-186">현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원하고 최소 출력만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="79413-186">Restore dependencies and tools for the project in the current directory and shows only minimal output:</span></span>

`dotnet restore --verbosity minimal`
