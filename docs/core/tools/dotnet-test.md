---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 05/29/2018
ms.openlocfilehash: 6b67273f549edd7712237756a5aba13d5cb59a61
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410362"
---
# <a name="dotnet-test"></a><span data-ttu-id="7011e-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="7011e-103">dotnet test</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7011e-104">name</span><span class="sxs-lookup"><span data-stu-id="7011e-104">Name</span></span>

<span data-ttu-id="7011e-105">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-105">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7011e-106">개요</span><span class="sxs-lookup"><span data-stu-id="7011e-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7011e-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7011e-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] 
    [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7011e-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7011e-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [--collect] [-d|--diag] [-f|--framework] [--filter]
    [-l|--logger] [--no-build] [--no-restore] [-o|--output] [-r|--results-directory] [-s|--settings] [-t|--list-tests] [-v|--verbosity]

dotnet test [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7011e-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7011e-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet test [<PROJECT>] [-a|--test-adapter-path] [-c|--configuration] [-d|--diag] [-f|--framework] [--filter] [-l|--logger] [--no-build] [-o|--output] [-s|--settings] [-t|--list-tests]  [-v|--verbosity]

dotnet test [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="7011e-110">설명</span><span class="sxs-lookup"><span data-stu-id="7011e-110">Description</span></span>

<span data-ttu-id="7011e-111">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-111">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="7011e-112">`dotnet test` 명령은 프로젝트에 대해 지정된 테스트 러너 콘솔 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-112">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="7011e-113">테스트 러너는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit)에 대해 정의된 테스트를 실행하고 각 테스트의 성공 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-113">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="7011e-114">모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-114">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="7011e-115">테스트 러너와 단위 테스트 라이브러리는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-115">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="7011e-116">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-116">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="7011e-117">인수</span><span class="sxs-lookup"><span data-stu-id="7011e-117">Arguments</span></span>

`PROJECT`

<span data-ttu-id="7011e-118">테스트 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-118">Path to the test project.</span></span> <span data-ttu-id="7011e-119">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="7011e-120">옵션</span><span class="sxs-lookup"><span data-stu-id="7011e-120">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7011e-121">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7011e-121">.NET Core 2.1</span></span>](#tab/netcore21)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="7011e-122">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-122">Use the custom test adapters from the specified path in the test run.</span></span>

`--blame`

<span data-ttu-id="7011e-123">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-123">Runs the tests in blame mode.</span></span> <span data-ttu-id="7011e-124">이 옵션은 테스트 호스트를 충돌시키는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-124">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="7011e-125">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-125">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7011e-126">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-126">Defines the build configuration.</span></span> <span data-ttu-id="7011e-127">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-127">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="7011e-128">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-128">Enables data collector for the test run.</span></span> <span data-ttu-id="7011e-129">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-129">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="7011e-130">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-130">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7011e-131">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-131">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7011e-132">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-132">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="7011e-133">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-133">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="7011e-134">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-134">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="7011e-135">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-135">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="7011e-136">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-136">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="7011e-137">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-137">Doesn't build the test project before running it.</span></span> <span data-ttu-id="7011e-138">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-138">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="7011e-139">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-139">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7011e-140">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-140">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="7011e-141">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-141">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="7011e-142">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-142">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="7011e-143">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-143">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="7011e-144">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-144">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="7011e-145">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-145">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7011e-146">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-146">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7011e-147">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

`RunSettings arguments`

<span data-ttu-id="7011e-148">테스트를 위해 RunSettings 구성으로 전달되는 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-148">Arguments passed as RunSettings configurations for the test.</span></span> <span data-ttu-id="7011e-149">인수는 “-- ” 뒤에 `[name]=[value]` 쌍으로 지정됩니다(-- 뒤 공백 주의).</span><span class="sxs-lookup"><span data-stu-id="7011e-149">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="7011e-150">공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-150">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

<span data-ttu-id="7011e-151">예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="7011e-151">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

<span data-ttu-id="7011e-152">RunSettings에 대한 자세한 내용은 [vstest.console.exe: Passing RunSettings args(vstest.console.exe: RunSettings 인수 전달)](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-152">For more information about RunSettings, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7011e-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7011e-153">.NET Core 2.0</span></span>](#tab/netcore20)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="7011e-154">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-154">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7011e-155">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-155">Defines the build configuration.</span></span> <span data-ttu-id="7011e-156">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-156">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`

<span data-ttu-id="7011e-157">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-157">Enables data collector for the test run.</span></span> <span data-ttu-id="7011e-158">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-158">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="7011e-159">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-159">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7011e-160">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-160">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7011e-161">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-161">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="7011e-162">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-162">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="7011e-163">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-163">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="7011e-164">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-164">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="7011e-165">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-165">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="7011e-166">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-166">Doesn't build the test project before running it.</span></span> <span data-ttu-id="7011e-167">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-167">It also implicit sets the `--no-restore` flag.</span></span>

`--no-restore`

<span data-ttu-id="7011e-168">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-168">Doesn't execute an implicit restore when running the command.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7011e-169">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-169">Directory in which to find the binaries to run.</span></span>

`-r|--results-directory <PATH>`

<span data-ttu-id="7011e-170">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-170">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="7011e-171">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-171">If the specified directory doesn't exist, it's created.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="7011e-172">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-172">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="7011e-173">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-173">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="7011e-174">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-174">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7011e-175">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-175">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7011e-176">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-176">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7011e-177">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7011e-177">.NET Core 1.x</span></span>](#tab/netcore1x)

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

<span data-ttu-id="7011e-178">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-178">Use the custom test adapters from the specified path in the test run.</span></span>

`-c|--configuration {Debug|Release}`

<span data-ttu-id="7011e-179">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-179">Defines the build configuration.</span></span> <span data-ttu-id="7011e-180">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-180">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

<span data-ttu-id="7011e-181">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-181">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="7011e-182">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-182">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7011e-183">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-183">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="7011e-184">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-184">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="7011e-185">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-185">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

`-h|--help`

<span data-ttu-id="7011e-186">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-186">Prints out a short help for the command.</span></span>

`-l|--logger <LoggerUri/FriendlyName>`

<span data-ttu-id="7011e-187">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-187">Specifies a logger for test results.</span></span>

`--no-build`

<span data-ttu-id="7011e-188">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-188">Doesn't build the test project before running it.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7011e-189">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-189">Directory in which to find the binaries to run.</span></span>

`-s|--settings <SETTINGS_FILE>`

<span data-ttu-id="7011e-190">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-190">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="7011e-191">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-191">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file?view=vs-2019)

`-t|--list-tests`

<span data-ttu-id="7011e-192">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-192">List all of the discovered tests in the current project.</span></span>

`-v|--verbosity <LEVEL>`

<span data-ttu-id="7011e-193">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-193">Sets the verbosity level of the command.</span></span> <span data-ttu-id="7011e-194">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-194">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7011e-195">예제</span><span class="sxs-lookup"><span data-stu-id="7011e-195">Examples</span></span>

<span data-ttu-id="7011e-196">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-196">Run the tests in the project in the current directory:</span></span>

`dotnet test`

<span data-ttu-id="7011e-197">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-197">Run the tests in the `test1` project:</span></span>

`dotnet test ~/projects/test1/test1.csproj`

<span data-ttu-id="7011e-198">현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-198">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

`dotnet test --logger:trx`

## <a name="filter-option-details"></a><span data-ttu-id="7011e-199">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="7011e-199">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="7011e-200">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-200">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="7011e-201">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-201">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="7011e-202">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-202">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="7011e-203">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="7011e-203">Test Framework</span></span> | <span data-ttu-id="7011e-204">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="7011e-204">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="7011e-205">MSTest</span><span class="sxs-lookup"><span data-stu-id="7011e-205">MSTest</span></span>         | <ul><li><span data-ttu-id="7011e-206">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="7011e-206">FullyQualifiedName</span></span></li><li><span data-ttu-id="7011e-207">name</span><span class="sxs-lookup"><span data-stu-id="7011e-207">Name</span></span></li><li><span data-ttu-id="7011e-208">ClassName</span><span class="sxs-lookup"><span data-stu-id="7011e-208">ClassName</span></span></li><li><span data-ttu-id="7011e-209">우선 순위</span><span class="sxs-lookup"><span data-stu-id="7011e-209">Priority</span></span></li><li><span data-ttu-id="7011e-210">TestCategory</span><span class="sxs-lookup"><span data-stu-id="7011e-210">TestCategory</span></span></li></ul> |
| <span data-ttu-id="7011e-211">xUnit</span><span class="sxs-lookup"><span data-stu-id="7011e-211">xUnit</span></span>          | <ul><li><span data-ttu-id="7011e-212">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="7011e-212">FullyQualifiedName</span></span></li><li><span data-ttu-id="7011e-213">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7011e-213">DisplayName</span></span></li><li><span data-ttu-id="7011e-214">특성</span><span class="sxs-lookup"><span data-stu-id="7011e-214">Traits</span></span></li></ul>                                   |

<span data-ttu-id="7011e-215">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-215">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="7011e-216">연산자</span><span class="sxs-lookup"><span data-stu-id="7011e-216">Operator</span></span> | <span data-ttu-id="7011e-217">함수</span><span class="sxs-lookup"><span data-stu-id="7011e-217">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="7011e-218">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="7011e-218">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="7011e-219">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="7011e-219">Not exact match</span></span> |
| `~`      | <span data-ttu-id="7011e-220">포함</span><span class="sxs-lookup"><span data-stu-id="7011e-220">Contains</span></span>        |

<span data-ttu-id="7011e-221">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-221">`<value>` is a string.</span></span> <span data-ttu-id="7011e-222">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-222">All the lookups are case insensitive.</span></span>

<span data-ttu-id="7011e-223">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="7011e-223">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="7011e-224">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7011e-224">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="7011e-225">연산자</span><span class="sxs-lookup"><span data-stu-id="7011e-225">Operator</span></span>            | <span data-ttu-id="7011e-226">함수</span><span class="sxs-lookup"><span data-stu-id="7011e-226">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="7011e-227">또는</span><span class="sxs-lookup"><span data-stu-id="7011e-227">OR</span></span>       |
| `&`                 | <span data-ttu-id="7011e-228">AND</span><span class="sxs-lookup"><span data-stu-id="7011e-228">AND</span></span>      |

<span data-ttu-id="7011e-229">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="7011e-229">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="7011e-230">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7011e-230">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7011e-231">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7011e-231">See also</span></span>

- [<span data-ttu-id="7011e-232">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="7011e-232">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="7011e-233">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="7011e-233">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
