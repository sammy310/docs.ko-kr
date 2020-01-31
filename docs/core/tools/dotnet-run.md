---
title: dotnet run 명령
description: dotnet run 명령은 소스 코드에서 애플리케이션을 실행하는 편리한 옵션을 제공합니다.
ms.date: 10/31/2019
ms.openlocfilehash: 5920f0d1f04204b286fdf6f51f5fd13644846390
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734110"
---
# <a name="dotnet-run"></a><span data-ttu-id="81f04-103">dotnet run</span><span class="sxs-lookup"><span data-stu-id="81f04-103">dotnet run</span></span>

<span data-ttu-id="81f04-104">**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="81f04-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="81f04-105">이름</span><span class="sxs-lookup"><span data-stu-id="81f04-105">Name</span></span>

<span data-ttu-id="81f04-106">`dotnet run` - 명시적 컴파일이나 시작 명령을 사용하지 않고 소스 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-106">`dotnet run` - Runs source code without any explicit compile or launch commands.</span></span>

## <a name="synopsis"></a><span data-ttu-id="81f04-107">개요</span><span class="sxs-lookup"><span data-stu-id="81f04-107">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="81f04-108">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="81f04-108">.NET Core 3.0</span></span>](#tab/netcore30)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--interactive] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [-r|--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="81f04-109">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="81f04-109">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [-v|--verbosity] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="81f04-110">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="81f04-110">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies]
    [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81f04-111">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81f04-111">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="81f04-112">설명</span><span class="sxs-lookup"><span data-stu-id="81f04-112">Description</span></span>

<span data-ttu-id="81f04-113">`dotnet run` 명령은 하나의 명령을 사용하여 소스 코드에서 애플리케이션을 실행하는 편리한 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-113">The `dotnet run` command provides a convenient option to run your application from the source code with one command.</span></span> <span data-ttu-id="81f04-114">명령줄에서 빠른 반복 개발에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-114">It's useful for fast iterative development from the command line.</span></span> <span data-ttu-id="81f04-115">이 명령은 코드 빌드 시 [`dotnet build`](dotnet-build.md) 명령에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-115">The command depends on the [`dotnet build`](dotnet-build.md) command to build the code.</span></span> <span data-ttu-id="81f04-116">프로젝트를 먼저 복원해야 하는 등, 빌드에 대한 요구 사항은 `dotnet run`에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-116">Any requirements for the build, such as that the project must be restored first, apply to `dotnet run` as well.</span></span>

<span data-ttu-id="81f04-117">출력 파일은 기본 위치, 즉 `bin/<configuration>/<target>`에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-117">Output files are written into the default location, which is `bin/<configuration>/<target>`.</span></span> <span data-ttu-id="81f04-118">예를 들어 `netcoreapp2.1` 애플리케이션이 있고 `dotnet run`을 실행하는 경우 출력은 `bin/Debug/netcoreapp2.1`에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-118">For example if you have a `netcoreapp2.1` application and you run `dotnet run`, the output is placed in `bin/Debug/netcoreapp2.1`.</span></span> <span data-ttu-id="81f04-119">필요에 따라 파일을 덮어씁니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-119">Files are overwritten as needed.</span></span> <span data-ttu-id="81f04-120">임시 파일은 `obj` 디렉터리에 놓입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-120">Temporary files are placed in the `obj` directory.</span></span>

<span data-ttu-id="81f04-121">프로젝트가 여러 프레임워크를 지정하는 경우 프레임워크를 지정하는 데 `-f|--framework <FRAMEWORK>` 옵션을 사용하지 않은 한, `dotnet run`을 실행하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-121">If the project specifies multiple frameworks, executing `dotnet run` results in an error unless the `-f|--framework <FRAMEWORK>` option is used to specify the framework.</span></span>

<span data-ttu-id="81f04-122">`dotnet run` 명령은 빌드된 어셈블리가 아닌 프로젝트의 컨텍스트에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-122">The `dotnet run` command is used in the context of projects, not built assemblies.</span></span> <span data-ttu-id="81f04-123">대신 프레임워크 종속 애플리케이션 DLL을 실행하려고 하는 경우 명령 없이 [dotnet](dotnet.md)을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-123">If you're trying to run a framework-dependent application DLL instead, you must use [dotnet](dotnet.md) without a command.</span></span> <span data-ttu-id="81f04-124">예를 들어 `myapp.dll`을 실행하려면 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-124">For example, to run `myapp.dll`, use:</span></span>

```dotnetcli
dotnet myapp.dll
```

<span data-ttu-id="81f04-125">`dotnet` 드라이버에 대한 자세한 내용은 [.NET Core 명령줄 도구(CLI)](index.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-125">For more information on the `dotnet` driver, see the [.NET Core Command Line Tools (CLI)](index.md) topic.</span></span>

<span data-ttu-id="81f04-126">애플리케이션을 실행하기 위해 `dotnet run` 명령은 NuGet 캐시에서 공유 런타임의 외부에 있는 애플리케이션의 종속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-126">To run the application, the `dotnet run` command resolves the dependencies of the application that are outside of the shared runtime from the NuGet cache.</span></span> <span data-ttu-id="81f04-127">캐시된 종속성을 사용하기 때문에 프로덕션 환경에서 애플리케이션을 실행하는 데 `dotnet run`을 사용하는 것은 바람직하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-127">Because it uses cached dependencies, it's not recommended to use `dotnet run` to run applications in production.</span></span> <span data-ttu-id="81f04-128">대신, [`dotnet publish`](dotnet-publish.md) 명령을 사용하여 [배포를 만들고](../deploying/index.md) 게시된 출력을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-128">Instead, [create a deployment](../deploying/index.md) using the [`dotnet publish`](dotnet-publish.md) command and deploy the published output.</span></span>

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="options"></a><span data-ttu-id="81f04-129">옵션</span><span class="sxs-lookup"><span data-stu-id="81f04-129">Options</span></span>

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="81f04-130">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="81f04-130">.NET Core 3.0</span></span>](#tab/netcore30)

`--`

<span data-ttu-id="81f04-131">실행 중인 애플리케이션에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-131">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="81f04-132">이 구분 기호 다음의 모든 인수가 실행 중인 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-132">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="81f04-133">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-133">Defines the build configuration.</span></span> <span data-ttu-id="81f04-134">대부분의 프로젝트 기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-134">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="81f04-135">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-135">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="81f04-136">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-136">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="81f04-137">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-137">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="81f04-138">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-138">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="81f04-139">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-139">Prints out a short help for the command.</span></span>

`--interactive`

<span data-ttu-id="81f04-140">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).</span><span class="sxs-lookup"><span data-stu-id="81f04-140">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="81f04-141">애플리케이션을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-141">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="81f04-142">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-142">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="81f04-143">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-143">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="81f04-144">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-144">Doesn't build the project before running.</span></span> <span data-ttu-id="81f04-145">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-145">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="81f04-146">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-146">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="81f04-147">애플리케이션을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-147">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="81f04-148">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-148">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="81f04-149">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="81f04-149">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="81f04-150">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-150">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="81f04-151">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-151">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="81f04-152">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-152">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="81f04-153">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-153">Sets the verbosity level of the command.</span></span> <span data-ttu-id="81f04-154">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-154">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="81f04-155">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="81f04-155">.NET Core 2.1</span></span>](#tab/netcore21)

`--`

<span data-ttu-id="81f04-156">실행 중인 애플리케이션에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-156">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="81f04-157">이 구분 기호 다음의 모든 인수가 실행 중인 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-157">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="81f04-158">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-158">Defines the build configuration.</span></span> <span data-ttu-id="81f04-159">대부분의 프로젝트 기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-159">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="81f04-160">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-160">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="81f04-161">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-161">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="81f04-162">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-162">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="81f04-163">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-163">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="81f04-164">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-164">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="81f04-165">애플리케이션을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-165">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="81f04-166">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-166">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="81f04-167">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-167">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="81f04-168">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-168">Doesn't build the project before running.</span></span> <span data-ttu-id="81f04-169">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-169">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="81f04-170">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-170">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="81f04-171">애플리케이션을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-171">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="81f04-172">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-172">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="81f04-173">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="81f04-173">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="81f04-174">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-174">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="81f04-175">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-175">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="81f04-176">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-176">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="81f04-177">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-177">Sets the verbosity level of the command.</span></span> <span data-ttu-id="81f04-178">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-178">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="81f04-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="81f04-179">.NET Core 2.0</span></span>](#tab/netcore20)

`--`

<span data-ttu-id="81f04-180">실행 중인 애플리케이션에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-180">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="81f04-181">이 구분 기호 다음의 모든 인수가 실행 중인 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-181">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="81f04-182">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-182">Defines the build configuration.</span></span> <span data-ttu-id="81f04-183">대부분의 프로젝트 기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-183">The default for most projects value is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="81f04-184">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-184">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="81f04-185">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-185">The framework must be specified in the project file.</span></span>

`--force`

<span data-ttu-id="81f04-186">마지막 복원이 성공한 경우에도 모든 종속성을 강제 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-186">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="81f04-187">이 플래그를 지정하는 것은 *project.assets.json* 파일을 삭제하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-187">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

`-h|--help`

<span data-ttu-id="81f04-188">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-188">Prints out a short help for the command.</span></span>

`--launch-profile <NAME>`

<span data-ttu-id="81f04-189">애플리케이션을 시작할 때 사용할 시작 프로필(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-189">The name of the launch profile (if any) to use when launching the application.</span></span> <span data-ttu-id="81f04-190">시작 프로필은 *launchSettings.json* 파일에서 정의되고 일반적으로 `Development`, `Staging` 및 `Production`이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-190">Launch profiles are defined in the *launchSettings.json* file and are typically called `Development`, `Staging`, and `Production`.</span></span> <span data-ttu-id="81f04-191">자세한 내용은 [여러 환경 사용](/aspnet/core/fundamentals/environments)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-191">For more information, see [Working with multiple environments](/aspnet/core/fundamentals/environments).</span></span>

`--no-build`

<span data-ttu-id="81f04-192">실행하기 전에 프로젝트를 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-192">Doesn't build the project before running.</span></span> <span data-ttu-id="81f04-193">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-193">It also implicit sets the `--no-restore` flag.</span></span>

`--no-dependencies`

<span data-ttu-id="81f04-194">프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-194">When restoring a project with project-to-project (P2P) references, restores the root project and not the references.</span></span>

`--no-launch-profile`

<span data-ttu-id="81f04-195">애플리케이션을 구성하는 데 *launchSettings.json*을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-195">Doesn't try to use *launchSettings.json* to configure the application.</span></span>

`--no-restore`

<span data-ttu-id="81f04-196">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-196">Doesn't execute an implicit restore when running the command.</span></span>

`-p|--project <PATH>`

<span data-ttu-id="81f04-197">실행할 프로젝트 파일의 경로를 지정합니다(폴더 이름 또는 전체 경로).</span><span class="sxs-lookup"><span data-stu-id="81f04-197">Specifies the path of the project file to run (folder name or full path).</span></span> <span data-ttu-id="81f04-198">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-198">If not specified, it defaults to the current directory.</span></span>

`--runtime <RUNTIME_IDENTIFIER>`

<span data-ttu-id="81f04-199">패키지를 복원할 대상 런타임을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-199">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="81f04-200">RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-200">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="81f04-201">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="81f04-201">.NET Core 1.x</span></span>](#tab/netcore1x)

`--`

<span data-ttu-id="81f04-202">실행 중인 애플리케이션에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-202">Delimits arguments to `dotnet run` from arguments for the application being run.</span></span> <span data-ttu-id="81f04-203">이 구분 기호 다음의 모든 인수가 실행 중인 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-203">All arguments after this delimiter are passed to the application run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="81f04-204">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-204">Defines the build configuration.</span></span> <span data-ttu-id="81f04-205">대부분의 프로젝트 기본값은 `Debug`입니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-205">The default value for most projects is `Debug`.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="81f04-206">지정된 [프레임워크](../../standard/frameworks.md)를 사용하여 앱을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-206">Builds and runs the app using the specified [framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="81f04-207">프레임워크는 프로젝트 파일에 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-207">The framework must be specified in the project file.</span></span>

`-h|--help`

<span data-ttu-id="81f04-208">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-208">Prints out a short help for the command.</span></span>

`-p|--project <PATH/PROJECT.csproj>`

<span data-ttu-id="81f04-209">프로젝트 파일의 경로 및 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-209">Specifies the path and name of the project file.</span></span> <span data-ttu-id="81f04-210">(참고 참조) 지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-210">(See the NOTE.) If not specified, it defaults to the current directory.</span></span>

> [!NOTE]
> <span data-ttu-id="81f04-211">`-p|--project` 옵션과 함께 프로젝트 파일의 경로와 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-211">Use the path and name of the project file with the `-p|--project` option.</span></span> <span data-ttu-id="81f04-212">CLI의 재발로 인해 폴더 경로에 .NET Core SDK 1.x를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-212">A regression in the CLI prevents providing a folder path with .NET Core SDK 1.x.</span></span> <span data-ttu-id="81f04-213">이 문제에 대한 자세한 내용은 [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992)(dotnet run -p로 프로젝트를 시작할 수 없음(dotnet/cli #5992))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81f04-213">For more information about this issue, see [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992).</span></span>

---

## <a name="examples"></a><span data-ttu-id="81f04-214">예</span><span class="sxs-lookup"><span data-stu-id="81f04-214">Examples</span></span>

<span data-ttu-id="81f04-215">현재 디렉터리에 있는 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-215">Run the project in the current directory:</span></span>

`dotnet run`

<span data-ttu-id="81f04-216">지정된 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-216">Run the specified project:</span></span>

`dotnet run --project ./projects/proj1/proj1.csproj`

<span data-ttu-id="81f04-217">현재 디렉터리에 있는 프로젝트를 실행합니다. 비어 있는 `--` 옵션을 사용하므로 이 예제의 `--help` 인수는 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f04-217">Run the project in the current directory (the `--help` argument in this example is passed to the application, since the blank `--` option is used):</span></span>

`dotnet run --configuration Release -- --help`

<span data-ttu-id="81f04-218">최소 출력만을 표시하는 현재 디렉터리에 프로젝트에 대한 종속성 및 도구를 저장한 다음, 프로젝트를 실행합니다(.NET Core SDK 2.0 이상 버전).</span><span class="sxs-lookup"><span data-stu-id="81f04-218">Restore dependencies and tools for the project in the current directory only showing minimal output and then run the project: (.NET Core SDK 2.0 and later versions):</span></span>

`dotnet run --verbosity m`
