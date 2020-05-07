---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 04/29/2020
ms.openlocfilehash: a8218b6596601069b89a60ad018adf89a1f47cf6
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624893"
---
# <a name="dotnet-test"></a><span data-ttu-id="0b641-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="0b641-103">dotnet test</span></span>

<span data-ttu-id="0b641-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0b641-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0b641-105">이름</span><span class="sxs-lookup"><span data-stu-id="0b641-105">Name</span></span>

<span data-ttu-id="0b641-106">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0b641-107">개요</span><span class="sxs-lookup"><span data-stu-id="0b641-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="0b641-108">설명</span><span class="sxs-lookup"><span data-stu-id="0b641-108">Description</span></span>

<span data-ttu-id="0b641-109">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="0b641-110">`dotnet test` 명령은 프로젝트에 대해 지정된 테스트 러너 콘솔 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="0b641-111">테스트 러너는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit)에 대해 정의된 테스트를 실행하고 각 테스트의 성공 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="0b641-112">모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="0b641-113">멀티 타기팅 프로젝트의 경우 각 대상 프레임워크에 대해 테스트가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="0b641-114">테스트 러너와 단위 테스트 라이브러리는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-114">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="0b641-115">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

### <a name="implicit-restore"></a><span data-ttu-id="0b641-116">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="0b641-116">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="0b641-117">인수</span><span class="sxs-lookup"><span data-stu-id="0b641-117">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="0b641-118">테스트 프로젝트 또는 솔루션의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-118">Path to the test project or solution.</span></span> <span data-ttu-id="0b641-119">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-119">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="0b641-120">옵션</span><span class="sxs-lookup"><span data-stu-id="0b641-120">Options</span></span>

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="0b641-121">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-121">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="0b641-122">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-122">Runs the tests in blame mode.</span></span> <span data-ttu-id="0b641-123">이 옵션은 테스트 호스트의 크래시를 유발하는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-123">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="0b641-124">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-124">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="0b641-125">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-125">Defines the build configuration.</span></span> <span data-ttu-id="0b641-126">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-126">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="0b641-127">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-127">Enables data collector for the test run.</span></span> <span data-ttu-id="0b641-128">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-128">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="0b641-129">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-129">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0b641-130">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-130">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="0b641-131">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-131">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="0b641-132">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-132">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="0b641-133">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-133">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="0b641-134">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-134">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="0b641-135">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-135">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="0b641-136">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-136">For example, to complete authentication.</span></span> <span data-ttu-id="0b641-137">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="0b641-138">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-138">Specifies a logger for test results.</span></span> <span data-ttu-id="0b641-139">MSBuild와 달리 dotnet 테스트에서는 약어를 사용하지 않습니다. `-l "console;v=d"` 대신 `-l "console;verbosity=detailed"`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-139">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="0b641-140">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-140">Doesn't build the test project before running it.</span></span> <span data-ttu-id="0b641-141">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-141">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="0b641-142">Microsoft TestPlatform 배너를 표시하지 않고 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-142">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="0b641-143">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="0b641-144">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-144">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="0b641-145">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-145">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="0b641-146">지정하지 않으면 기본 경로는 `./bin/<configuration>/<framework>/`입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-146">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="0b641-147">`TargetFrameworks` 속성을 통해 여러 개의 대상 프레임워크가 지정된 프로젝트의 경우 이 옵션을 지정할 때 `--framework`도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-147">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="0b641-148">`dotnet test`는 항상 출력 디렉터리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-148">`dotnet test` always run tests from the output directory.</span></span> <span data-ttu-id="0b641-149"><xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>를 사용하여 출력 디렉터리에서 테스트 자산을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-149">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="0b641-150">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-150">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="0b641-151">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-151">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="0b641-152">기본값은 프로젝트 파일이 포함된 디렉터리의 `TestResults`입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-152">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="0b641-153">테스트할 대상 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-153">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="0b641-154">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-154">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="0b641-155">`TargetPlatform` 요소(x86|x64)는 `dotnet test`에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-155">Note that the `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="0b641-156">X86을 대상으로 하는 테스트를 실행하려면 x86 버전의 .NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-156">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="0b641-157">경로에 있는 *dotnet.exe*의 비트 수는 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-157">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="0b641-158">자세한 내용은 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-158">for more information, see the following resources:</span></span>

  - [<span data-ttu-id="0b641-159">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-159">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="0b641-160">테스트 실행 구성</span><span class="sxs-lookup"><span data-stu-id="0b641-160">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="0b641-161">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-161">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="0b641-162">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="0b641-163">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="0b641-164">기본값은 `minimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-164">The default is `minimal`.</span></span> <span data-ttu-id="0b641-165">자세한 내용은 <xref:Microsoft.Build.Framework.LoggerVerbosity>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-165">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="0b641-166">**`RunSettings`** 인수</span><span class="sxs-lookup"><span data-stu-id="0b641-166">**`RunSettings`** arguments</span></span>

  <span data-ttu-id="0b641-167">인수는 테스트의 `RunSettings` 구성으로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-167">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="0b641-168">인수는 “-- ” 뒤에 `[name]=[value]` 쌍으로 지정됩니다(-- 뒤 공백 주의).</span><span class="sxs-lookup"><span data-stu-id="0b641-168">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="0b641-169">공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-169">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="0b641-170">예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="0b641-170">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="0b641-171">자세한 내용은 [명령줄을 통해 RunSettings 인수 전달](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-171">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="0b641-172">예</span><span class="sxs-lookup"><span data-stu-id="0b641-172">Examples</span></span>

- <span data-ttu-id="0b641-173">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-173">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="0b641-174">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-174">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="0b641-175">현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-175">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="0b641-176">현재 디렉터리의 프로젝트에서 테스트를 실행하고 콘솔에 세부 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-176">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="0b641-177">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="0b641-177">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="0b641-178">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-178">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="0b641-179">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-179">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="0b641-180">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-180">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="0b641-181">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="0b641-181">Test Framework</span></span> | <span data-ttu-id="0b641-182">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="0b641-182">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="0b641-183">MSTest</span><span class="sxs-lookup"><span data-stu-id="0b641-183">MSTest</span></span>         | <ul><li><span data-ttu-id="0b641-184">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0b641-184">FullyQualifiedName</span></span></li><li><span data-ttu-id="0b641-185">이름</span><span class="sxs-lookup"><span data-stu-id="0b641-185">Name</span></span></li><li><span data-ttu-id="0b641-186">ClassName</span><span class="sxs-lookup"><span data-stu-id="0b641-186">ClassName</span></span></li><li><span data-ttu-id="0b641-187">우선 순위</span><span class="sxs-lookup"><span data-stu-id="0b641-187">Priority</span></span></li><li><span data-ttu-id="0b641-188">TestCategory</span><span class="sxs-lookup"><span data-stu-id="0b641-188">TestCategory</span></span></li></ul> |
| <span data-ttu-id="0b641-189">xUnit</span><span class="sxs-lookup"><span data-stu-id="0b641-189">xUnit</span></span>          | <ul><li><span data-ttu-id="0b641-190">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="0b641-190">FullyQualifiedName</span></span></li><li><span data-ttu-id="0b641-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="0b641-191">DisplayName</span></span></li><li><span data-ttu-id="0b641-192">특성</span><span class="sxs-lookup"><span data-stu-id="0b641-192">Traits</span></span></li></ul>                                   |

<span data-ttu-id="0b641-193">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-193">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="0b641-194">연산자</span><span class="sxs-lookup"><span data-stu-id="0b641-194">Operator</span></span> | <span data-ttu-id="0b641-195">기능</span><span class="sxs-lookup"><span data-stu-id="0b641-195">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="0b641-196">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="0b641-196">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="0b641-197">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="0b641-197">Not exact match</span></span> |
| `~`      | <span data-ttu-id="0b641-198">포함</span><span class="sxs-lookup"><span data-stu-id="0b641-198">Contains</span></span>        |
| `!~`     | <span data-ttu-id="0b641-199">포함하지 않음</span><span class="sxs-lookup"><span data-stu-id="0b641-199">Not contains</span></span>    |

<span data-ttu-id="0b641-200">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-200">`<value>` is a string.</span></span> <span data-ttu-id="0b641-201">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-201">All the lookups are case insensitive.</span></span>

<span data-ttu-id="0b641-202">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="0b641-202">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="0b641-203">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b641-203">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="0b641-204">연산자</span><span class="sxs-lookup"><span data-stu-id="0b641-204">Operator</span></span>            | <span data-ttu-id="0b641-205">기능</span><span class="sxs-lookup"><span data-stu-id="0b641-205">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="0b641-206">또는</span><span class="sxs-lookup"><span data-stu-id="0b641-206">OR</span></span>       |
| `&`                 | <span data-ttu-id="0b641-207">AND</span><span class="sxs-lookup"><span data-stu-id="0b641-207">AND</span></span>      |

<span data-ttu-id="0b641-208">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="0b641-208">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="0b641-209">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0b641-209">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0b641-210">참조</span><span class="sxs-lookup"><span data-stu-id="0b641-210">See also</span></span>

- [<span data-ttu-id="0b641-211">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="0b641-211">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="0b641-212">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="0b641-212">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="0b641-213">명령줄을 통해 runsettings 인수 전달</span><span class="sxs-lookup"><span data-stu-id="0b641-213">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
