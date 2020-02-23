---
title: dotnet publish 명령
description: dotnet publish 명령은 .NET Core 프로젝트를 디렉터리에 게시합니다.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451294"
---
# <a name="dotnet-publish"></a><span data-ttu-id="b93a7-103">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b93a7-103">dotnet publish</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b93a7-104">이름</span><span class="sxs-lookup"><span data-stu-id="b93a7-104">Name</span></span>

<span data-ttu-id="b93a7-105">`dotnet publish` - 호스팅 시스템에 배포하기 위해 애플리케이션 및 해당 종속성을 폴더에 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-105">`dotnet publish` - Packs the application and its dependencies into a folder for deployment to a hosting system.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b93a7-106">개요</span><span class="sxs-lookup"><span data-stu-id="b93a7-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[<span data-ttu-id="b93a7-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b93a7-107">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[<span data-ttu-id="b93a7-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b93a7-108">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[<span data-ttu-id="b93a7-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b93a7-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="b93a7-110">설명</span><span class="sxs-lookup"><span data-stu-id="b93a7-110">Description</span></span>

<span data-ttu-id="b93a7-111">`dotnet publish`는 애플리케이션을 컴파일하고 프로젝트 파일에 지정된 종속성을 읽은 다음 결과 파일 집합을 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-111">`dotnet publish` compiles the application, reads through its dependencies specified in the project file, and publishes the resulting set of files to a directory.</span></span> <span data-ttu-id="b93a7-112">출력에는 다음과 같은 자산이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-112">The output includes the following assets:</span></span>

- <span data-ttu-id="b93a7-113">*dll* 확장과 함께 어셈블리의 IL(중간 언어) 코드</span><span class="sxs-lookup"><span data-stu-id="b93a7-113">Intermediate Language (IL) code in an assembly with a *dll* extension.</span></span>
- <span data-ttu-id="b93a7-114">프로젝트의 종속성을 모두 포함하는 *.deps.json* 파일</span><span class="sxs-lookup"><span data-stu-id="b93a7-114">*.deps.json* file that includes all of the dependencies of the project.</span></span>
- <span data-ttu-id="b93a7-115">런타임에 대한 기타 구성 옵션(예: 가비지 수집 유형)뿐만 아니라 애플리케이션에서 예상하는 공유 런타임을 지정하는 *.runtimeconfig.json* 파일</span><span class="sxs-lookup"><span data-stu-id="b93a7-115">*.runtimeconfig.json* file that specifies the shared runtime that the application expects, as well as other configuration options for the runtime (for example, garbage collection type).</span></span>
- <span data-ttu-id="b93a7-116">애플리케이션의 종속성은 NuGet 캐시에서 출력 폴더로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-116">The application's dependencies, which are copied from the NuGet cache into the output folder.</span></span>

<span data-ttu-id="b93a7-117">`dotnet publish` 명령의 출력이 실행을 위해 호스팅 시스템(예: 서버, PC, Mac, 랩톱)에 배포할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-117">The `dotnet publish` command's output is ready for deployment to a hosting system (for example, a server, PC, Mac, laptop) for execution.</span></span> <span data-ttu-id="b93a7-118">이는 배포를 위해 애플리케이션을 준비하는 데 공식적으로 지원되는 유일한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-118">It's the only officially supported way to prepare the application for deployment.</span></span> <span data-ttu-id="b93a7-119">프로젝트에서 지정하는 배포 유형에 따라 호스팅 시스템에 .NET Core 공유 런타임이 설치되어 있을 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-119">Depending on the type of deployment that the project specifies, the hosting system may or may not have the .NET Core shared runtime installed on it.</span></span> <span data-ttu-id="b93a7-120">자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-120">For more information, see [.NET Core Application Deployment](../deploying/index.md).</span></span> <span data-ttu-id="b93a7-121">게시된 애플리케이션의 디렉터리 구조에 대해서는 [디렉터리 구조](/aspnet/core/hosting/directory-structure)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-121">For the directory structure of a published application, see [Directory structure](/aspnet/core/hosting/directory-structure).</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="b93a7-122">인수</span><span class="sxs-lookup"><span data-stu-id="b93a7-122">Arguments</span></span>

`PROJECT`

<span data-ttu-id="b93a7-123">게시할 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-123">The project to publish.</span></span> <span data-ttu-id="b93a7-124">[C#](csproj.md), F# 또는 Visual Basic 프로젝트 파일의 경로 및 파일 이름이거나 C#, F# 또는 Visual Basic 프로젝트 파일을 포함하는 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-124">It's either the path and filename of a [C#](csproj.md), F#, or Visual Basic project file, or the path to a directory that contains a C#, F#, or Visual Basic project file.</span></span> <span data-ttu-id="b93a7-125">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-125">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="b93a7-126">옵션</span><span class="sxs-lookup"><span data-stu-id="b93a7-126">Options</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="b93a7-127">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b93a7-127">.NET Core 2.1</span></span>](#tab/netcore21)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b93a7-128">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-128">Defines the build configuration.</span></span> <span data-ttu-id="b93a7-129">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-129">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b93a7-130">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-130">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b93a7-131">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-131">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="b93a7-132">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b93a7-133">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b93a7-134">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-134">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="b93a7-135">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-135">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="b93a7-136">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-136">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="b93a7-137">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-137">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="b93a7-138">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-138">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-build`

<span data-ttu-id="b93a7-139">게시하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-139">Doesn't build the project before publishing.</span></span> <span data-ttu-id="b93a7-140">또한 암시적으로 `--no-restore` 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-140">It also implicitly sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="b93a7-141">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-141">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="b93a7-142">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-142">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b93a7-143">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-143">Specifies the path for the output directory.</span></span> <span data-ttu-id="b93a7-144">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-144">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="b93a7-145">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-145">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="b93a7-146">대상 컴퓨터에 런타임을 설치할 필요가 없도록 애플리케이션을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-146">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="b93a7-147">런타임 식별자를 지정할 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-147">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="b93a7-148">다른 배포 형식에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-148">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b93a7-149">지정된 런타임에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-149">Publishes the application for a given runtime.</span></span> <span data-ttu-id="b93a7-150">[SCD(자체 포함 배포_](../deploying/index.md#publish-self-contained)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-150">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="b93a7-151">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-151">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="b93a7-152">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#publish-runtime-dependent)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-152">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b93a7-153">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b93a7-154">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="b93a7-155">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-155">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-20"></a>[<span data-ttu-id="b93a7-156">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="b93a7-156">.NET Core 2.0</span></span>](#tab/netcore20)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b93a7-157">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-157">Defines the build configuration.</span></span> <span data-ttu-id="b93a7-158">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-158">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b93a7-159">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-159">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b93a7-160">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-160">You must specify the target framework in the project file.</span></span>

`--force`

<span data-ttu-id="b93a7-161">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-161">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="b93a7-162">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-162">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="b93a7-163">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-163">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="b93a7-164">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-164">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="b93a7-165">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-165">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="b93a7-166">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-166">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="b93a7-167">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-167">This option is available starting with .NET Core 2.0 SDK.</span></span>

`--no-dependencies`

<span data-ttu-id="b93a7-168">프로젝트 간 참조를 무시하고 루트 프로젝트만 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-168">Ignores project-to-project references and only restores the root project.</span></span>

`--no-restore`

<span data-ttu-id="b93a7-169">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-169">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b93a7-170">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-170">Specifies the path for the output directory.</span></span> <span data-ttu-id="b93a7-171">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-171">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="b93a7-172">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-172">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`--self-contained`

<span data-ttu-id="b93a7-173">대상 컴퓨터에 런타임을 설치할 필요가 없도록 애플리케이션을 통해 .NET Core 런타임을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-173">Publishes the .NET Core runtime with your application so the runtime doesn't need to be installed on the target machine.</span></span> <span data-ttu-id="b93a7-174">런타임 식별자를 지정할 경우 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-174">If a runtime identifier is specified, its default value is `true`.</span></span> <span data-ttu-id="b93a7-175">다른 배포 형식에 대한 자세한 내용은 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-175">For more information about the different deployment types, see [.NET Core application deployment](../deploying/index.md).</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b93a7-176">지정된 런타임에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-176">Publishes the application for a given runtime.</span></span> <span data-ttu-id="b93a7-177">[SCD(자체 포함 배포_](../deploying/index.md#publish-self-contained)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-177">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="b93a7-178">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-178">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="b93a7-179">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#publish-runtime-dependent)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-179">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b93a7-180">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-180">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b93a7-181">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-181">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="b93a7-182">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-182">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

# <a name="net-core-1x"></a>[<span data-ttu-id="b93a7-183">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="b93a7-183">.NET Core 1.x</span></span>](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

<span data-ttu-id="b93a7-184">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-184">Defines the build configuration.</span></span> <span data-ttu-id="b93a7-185">기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-185">The default value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="b93a7-186">지정한 [대상 프레임워크](../../standard/frameworks.md)에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-186">Publishes the application for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="b93a7-187">프로젝트 파일에 대상 프레임워크를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-187">You must specify the target framework in the project file.</span></span>

`-h|--help`

<span data-ttu-id="b93a7-188">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-188">Prints out a short help for the command.</span></span>

`--manifest <PATH_TO_MANIFEST_FILE>`

<span data-ttu-id="b93a7-189">앱을 통해 게시된 패키지 집합을 잘라내는 데 사용할 하나 이상의 [대상 매니페스트](../deploying/runtime-store.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-189">Specifies one or several [target manifests](../deploying/runtime-store.md) to use to trim the set of packages published with the app.</span></span> <span data-ttu-id="b93a7-190">매니페스트 파일은 [`dotnet store` 명령](dotnet-store.md) 출력의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-190">The manifest file is part of the output of the [`dotnet store` command](dotnet-store.md).</span></span> <span data-ttu-id="b93a7-191">여러 매니페스트를 지정하려면 각 매니페스트에 대해 `--manifest` 옵션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-191">To specify multiple manifests, add a `--manifest` option for each manifest.</span></span> <span data-ttu-id="b93a7-192">이 옵션은 .NET Core 2.0 SDK부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-192">This option is available starting with .NET Core 2.0 SDK.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="b93a7-193">출력 디렉터리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-193">Specifies the path for the output directory.</span></span> <span data-ttu-id="b93a7-194">지정하지 않으면 프레임워크 종속 배포의 경우 *./bin/[configuration]/[framework]/publish/* 로, 자체 포함 배포의 경우 *./bin/[configuration]/[framework]/[runtime]/publish/* 로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-194">If not specified, it defaults to *./bin/[configuration]/[framework]/publish/* for a framework-dependent deployment or *./bin/[configuration]/[framework]/[runtime]/publish/* for a self-contained deployment.</span></span>
<span data-ttu-id="b93a7-195">상대 경로인 경우 생성된 출력 디렉터리는 현재 작업 디렉터리가 아닌 프로젝트 파일 위치에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-195">If the path is relative, the output directory generated is relative to the project file location, not to the current working directory.</span></span>

`-r|--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="b93a7-196">지정된 런타임에 대한 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-196">Publishes the application for a given runtime.</span></span> <span data-ttu-id="b93a7-197">[SCD(자체 포함 배포_](../deploying/index.md#publish-self-contained)를 만들 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-197">This is used when creating a [self-contained deployment (SCD)](../deploying/index.md#publish-self-contained).</span></span> <span data-ttu-id="b93a7-198">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b93a7-198">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span> <span data-ttu-id="b93a7-199">기본값은 [FDD(프레임워크 종속 배포)](../deploying/index.md#publish-runtime-dependent)를 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-199">Default is to publish a [framework-dependent deployment (FDD)](../deploying/index.md#publish-runtime-dependent).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="b93a7-200">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-200">Sets the verbosity level of the command.</span></span> <span data-ttu-id="b93a7-201">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-201">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`--version-suffix <VERSION_SUFFIX>`

<span data-ttu-id="b93a7-202">프로젝트 파일의 버전 필드에서 별표(`*`)를 대신할 버전 접미사를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-202">Defines the version suffix to replace the asterisk (`*`) in the version field of the project file.</span></span>

---

## <a name="examples"></a><span data-ttu-id="b93a7-203">예</span><span class="sxs-lookup"><span data-stu-id="b93a7-203">Examples</span></span>

<span data-ttu-id="b93a7-204">현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-204">Publish the project in the current directory:</span></span>

`dotnet publish`

<span data-ttu-id="b93a7-205">지정된 프로젝트 파일을 사용하여 애플리케이션을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-205">Publish the application using the specified project file:</span></span>

`dotnet publish ~/projects/app1/app1.csproj`

<span data-ttu-id="b93a7-206">`netcoreapp1.1` 프레임워크를 사용하여 현재 디렉터리에 있는 프로젝트를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-206">Publish the project in the current directory using the `netcoreapp1.1` framework:</span></span>

`dotnet publish --framework netcoreapp1.1`

<span data-ttu-id="b93a7-207">`netcoreapp1.1` 프레임워크 및 `OS X 10.10`에 대한 런타임을 사용하여 현재 애플리케이션을 게시합니다. 프로젝트 파일에서 이 RID를 나열해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b93a7-207">Publish the current application using the `netcoreapp1.1` framework and the runtime for `OS X 10.10` (you must list this RID in the project file).</span></span>

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

<span data-ttu-id="b93a7-208">현재 애플리케이션을 게시하지만 프로젝트 간(P2P) 참조를 복원하지 않습니다. 복원 작업 중 루트 프로젝트만 복원합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="b93a7-208">Publish the current application but don't restore project-to-project (P2P) references, just the root project during the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet publish --no-dependencies`

## <a name="see-also"></a><span data-ttu-id="b93a7-209">참조</span><span class="sxs-lookup"><span data-stu-id="b93a7-209">See also</span></span>

- [<span data-ttu-id="b93a7-210">대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="b93a7-210">Target frameworks</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="b93a7-211">RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="b93a7-211">Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
