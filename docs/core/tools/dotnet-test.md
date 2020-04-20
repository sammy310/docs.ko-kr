---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 02/27/2020
ms.openlocfilehash: f9df03cda01bdaf649394a58e96903e764193338
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463371"
---
# <a name="dotnet-test"></a><span data-ttu-id="84e87-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="84e87-103">dotnet test</span></span>

<span data-ttu-id="84e87-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="84e87-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="84e87-105">이름</span><span class="sxs-lookup"><span data-stu-id="84e87-105">Name</span></span>

<span data-ttu-id="84e87-106">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="84e87-107">개요</span><span class="sxs-lookup"><span data-stu-id="84e87-107">Synopsis</span></span>

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

## <a name="description"></a><span data-ttu-id="84e87-108">설명</span><span class="sxs-lookup"><span data-stu-id="84e87-108">Description</span></span>

<span data-ttu-id="84e87-109">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="84e87-110">`dotnet test` 명령은 프로젝트에 대해 지정된 테스트 러너 콘솔 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="84e87-111">테스트 러너는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit)에 대해 정의된 테스트를 실행하고 각 테스트의 성공 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="84e87-112">모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="84e87-113">테스트 러너와 단위 테스트 라이브러리는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="84e87-114">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="84e87-115">인수</span><span class="sxs-lookup"><span data-stu-id="84e87-115">Arguments</span></span>

- **`PROJECT | SOLUTION`**

  <span data-ttu-id="84e87-116">테스트 프로젝트 또는 솔루션의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-116">Path to the test project or solution.</span></span> <span data-ttu-id="84e87-117">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="84e87-118">옵션</span><span class="sxs-lookup"><span data-stu-id="84e87-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="84e87-119">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`--blame`**

  <span data-ttu-id="84e87-120">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="84e87-121">이 옵션은 테스트 호스트의 크래시를 유발하는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="84e87-122">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="84e87-123">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-123">Defines the build configuration.</span></span> <span data-ttu-id="84e87-124">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="84e87-125">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-125">Enables data collector for the test run.</span></span> <span data-ttu-id="84e87-126">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="84e87-127">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="84e87-128">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="84e87-129">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="84e87-130">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="84e87-131">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="84e87-132">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-132">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="84e87-133">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-133">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="84e87-134">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-134">For example, to complete authentication.</span></span> <span data-ttu-id="84e87-135">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-135">Available since .NET Core 3.0 SDK.</span></span>

- **`l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="84e87-136">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-136">Specifies a logger for test results.</span></span> <span data-ttu-id="84e87-137">MSBuild와 달리 dotnet 테스트에서는 약어를 사용하지 않습니다. `-l "console;v=d"` 대신 `-l "console;verbosity=detailed"`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-137">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="84e87-138">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-138">Doesn't build the test project before running it.</span></span> <span data-ttu-id="84e87-139">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-139">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="84e87-140">Microsoft TestPlatform 배너를 표시하지 않고 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-140">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="84e87-141">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-141">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="84e87-142">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-142">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="84e87-143">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-143">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="84e87-144">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-144">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="84e87-145">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-145">If the specified directory doesn't exist, it's created.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="84e87-146">테스트할 대상 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-146">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="84e87-147">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-147">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="84e87-148">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-148">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="84e87-149">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-149">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="84e87-150">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-150">Sets the verbosity level of the command.</span></span> <span data-ttu-id="84e87-151">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="84e87-152">기본값은 `minimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-152">The default is `minimal`.</span></span> <span data-ttu-id="84e87-153">자세한 내용은 <xref:Microsoft.Build.Framework.LoggerVerbosity>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-153">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="84e87-154">`RunSettings` 인수</span><span class="sxs-lookup"><span data-stu-id="84e87-154">`RunSettings` arguments</span></span>

  <span data-ttu-id="84e87-155">인수는 테스트의 `RunSettings` 구성으로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-155">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="84e87-156">인수는 “-- ” 뒤에 `[name]=[value]` 쌍으로 지정됩니다(-- 뒤 공백 주의).</span><span class="sxs-lookup"><span data-stu-id="84e87-156">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="84e87-157">공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-157">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="84e87-158">예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="84e87-158">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="84e87-159">자세한 내용은 [vstest.console.exe: Passing RunSettings args(vstest.console.exe: RunSettings 인수 전달)](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-159">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="84e87-160">예</span><span class="sxs-lookup"><span data-stu-id="84e87-160">Examples</span></span>

- <span data-ttu-id="84e87-161">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-161">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="84e87-162">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-162">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="84e87-163">현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-163">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="84e87-164">현재 디렉터리의 프로젝트에서 테스트를 실행하고 콘솔에 세부 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-164">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a><span data-ttu-id="84e87-165">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="84e87-165">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="84e87-166">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-166">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="84e87-167">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-167">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="84e87-168">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-168">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="84e87-169">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="84e87-169">Test Framework</span></span> | <span data-ttu-id="84e87-170">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="84e87-170">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="84e87-171">MSTest</span><span class="sxs-lookup"><span data-stu-id="84e87-171">MSTest</span></span>         | <ul><li><span data-ttu-id="84e87-172">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="84e87-172">FullyQualifiedName</span></span></li><li><span data-ttu-id="84e87-173">이름</span><span class="sxs-lookup"><span data-stu-id="84e87-173">Name</span></span></li><li><span data-ttu-id="84e87-174">ClassName</span><span class="sxs-lookup"><span data-stu-id="84e87-174">ClassName</span></span></li><li><span data-ttu-id="84e87-175">우선 순위</span><span class="sxs-lookup"><span data-stu-id="84e87-175">Priority</span></span></li><li><span data-ttu-id="84e87-176">TestCategory</span><span class="sxs-lookup"><span data-stu-id="84e87-176">TestCategory</span></span></li></ul> |
| <span data-ttu-id="84e87-177">xUnit</span><span class="sxs-lookup"><span data-stu-id="84e87-177">xUnit</span></span>          | <ul><li><span data-ttu-id="84e87-178">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="84e87-178">FullyQualifiedName</span></span></li><li><span data-ttu-id="84e87-179">DisplayName</span><span class="sxs-lookup"><span data-stu-id="84e87-179">DisplayName</span></span></li><li><span data-ttu-id="84e87-180">특성</span><span class="sxs-lookup"><span data-stu-id="84e87-180">Traits</span></span></li></ul>                                   |

<span data-ttu-id="84e87-181">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-181">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="84e87-182">연산자</span><span class="sxs-lookup"><span data-stu-id="84e87-182">Operator</span></span> | <span data-ttu-id="84e87-183">기능</span><span class="sxs-lookup"><span data-stu-id="84e87-183">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="84e87-184">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="84e87-184">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="84e87-185">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="84e87-185">Not exact match</span></span> |
| `~`      | <span data-ttu-id="84e87-186">포함</span><span class="sxs-lookup"><span data-stu-id="84e87-186">Contains</span></span>        |
| `!~`     | <span data-ttu-id="84e87-187">포함하지 않음</span><span class="sxs-lookup"><span data-stu-id="84e87-187">Not contains</span></span>    |

<span data-ttu-id="84e87-188">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-188">`<value>` is a string.</span></span> <span data-ttu-id="84e87-189">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-189">All the lookups are case insensitive.</span></span>

<span data-ttu-id="84e87-190">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="84e87-190">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="84e87-191">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84e87-191">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="84e87-192">연산자</span><span class="sxs-lookup"><span data-stu-id="84e87-192">Operator</span></span>            | <span data-ttu-id="84e87-193">기능</span><span class="sxs-lookup"><span data-stu-id="84e87-193">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="84e87-194">또는</span><span class="sxs-lookup"><span data-stu-id="84e87-194">OR</span></span>       |
| `&`                 | <span data-ttu-id="84e87-195">AND</span><span class="sxs-lookup"><span data-stu-id="84e87-195">AND</span></span>      |

<span data-ttu-id="84e87-196">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="84e87-196">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="84e87-197">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84e87-197">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84e87-198">참조</span><span class="sxs-lookup"><span data-stu-id="84e87-198">See also</span></span>

- [<span data-ttu-id="84e87-199">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="84e87-199">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="84e87-200">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="84e87-200">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="84e87-201">명령줄을 통해 runsettings 인수 전달</span><span class="sxs-lookup"><span data-stu-id="84e87-201">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
