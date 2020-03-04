---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 02/27/2020
ms.openlocfilehash: 6e906ab396a788905c99f50e73390b765b240efc
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157013"
---
# <a name="dotnet-test"></a><span data-ttu-id="76236-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="76236-103">dotnet test</span></span>

<span data-ttu-id="76236-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="76236-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="76236-105">이름</span><span class="sxs-lookup"><span data-stu-id="76236-105">Name</span></span>

<span data-ttu-id="76236-106">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="76236-107">개요</span><span class="sxs-lookup"><span data-stu-id="76236-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT>] [-a|--test-adapter-path] [--blame]
    [-c|--configuration] [--collect] [-d|--diag] [-f|--framework]
    [--filter] [-l|--logger] [--no-build] [--no-restore]
    [-o|--output] [-r|--results-directory] [-s|--settings]
    [-t|--list-tests] [-v|--verbosity] [-- <RunSettings arguments>]

dotnet test [-h|--help]
```

## <a name="description"></a><span data-ttu-id="76236-108">설명</span><span class="sxs-lookup"><span data-stu-id="76236-108">Description</span></span>

<span data-ttu-id="76236-109">`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-109">The `dotnet test` command is used to execute unit tests in a given project.</span></span> <span data-ttu-id="76236-110">`dotnet test` 명령은 프로젝트에 대해 지정된 테스트 러너 콘솔 애플리케이션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-110">The `dotnet test` command launches the test runner console application specified for a project.</span></span> <span data-ttu-id="76236-111">테스트 러너는 단위 테스트 프레임워크(예: MSTest, NUnit 또는 xUnit)에 대해 정의된 테스트를 실행하고 각 테스트의 성공 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-111">The test runner executes the tests defined for a unit test framework (for example, MSTest, NUnit, or xUnit) and reports the success or failure of each test.</span></span> <span data-ttu-id="76236-112">모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span> <span data-ttu-id="76236-113">테스트 러너와 단위 테스트 라이브러리는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-113">The test runner and the unit test library are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="76236-114">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-114">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a><span data-ttu-id="76236-115">인수</span><span class="sxs-lookup"><span data-stu-id="76236-115">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="76236-116">테스트 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-116">Path to the test project.</span></span> <span data-ttu-id="76236-117">지정하지 않으면 현재 디렉터리로 기본 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-117">If not specified, it defaults to current directory.</span></span>

## <a name="options"></a><span data-ttu-id="76236-118">옵션</span><span class="sxs-lookup"><span data-stu-id="76236-118">Options</span></span>

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  <span data-ttu-id="76236-119">테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-119">Use the custom test adapters from the specified path in the test run.</span></span>

- **`-blame`**

  <span data-ttu-id="76236-120">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-120">Runs the tests in blame mode.</span></span> <span data-ttu-id="76236-121">이 옵션은 테스트 호스트의 크래시를 유발하는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-121">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="76236-122">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="76236-122">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`c|--configuration {Debug|Release}`**

  <span data-ttu-id="76236-123">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-123">Defines the build configuration.</span></span> <span data-ttu-id="76236-124">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-124">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  <span data-ttu-id="76236-125">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-125">Enables data collector for the test run.</span></span> <span data-ttu-id="76236-126">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76236-126">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  <span data-ttu-id="76236-127">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-127">Enables diagnostic mode for the test platform and write diagnostic messages to the specified file.</span></span>

- **`f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76236-128">특정 [프레임워크](../../standard/frameworks.md)에 대한 테스트 이진 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-128">Looks for test binaries for a specific [framework](../../standard/frameworks.md).</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="76236-129">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-129">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="76236-130">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76236-130">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="76236-131">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76236-131">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`h|--help`**

  <span data-ttu-id="76236-132">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-132">Prints out a short help for the command.</span></span>

- **`l|--logger <LoggerUri/FriendlyName>`**

  <span data-ttu-id="76236-133">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-133">Specifies a logger for test results.</span></span>

- **`--no-build`**

  <span data-ttu-id="76236-134">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-134">Doesn't build the test project before running it.</span></span> <span data-ttu-id="76236-135">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-135">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--no-restore`**

  <span data-ttu-id="76236-136">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-136">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="76236-137">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-137">Directory in which to find the binaries to run.</span></span>

- **`-r|--results-directory <PATH>`**

  <span data-ttu-id="76236-138">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-138">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="76236-139">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-139">If the specified directory doesn't exist, it's created.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="76236-140">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-140">The `.runsettings` file to use for running the tests.</span></span> [<span data-ttu-id="76236-141">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-141">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  <span data-ttu-id="76236-142">현재 프로젝트에서 검색된 테스트를 모두 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-142">List all of the discovered tests in the current project.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="76236-143">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-143">Sets the verbosity level of the command.</span></span> <span data-ttu-id="76236-144">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-144">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

- <span data-ttu-id="76236-145">`RunSettings` 인수</span><span class="sxs-lookup"><span data-stu-id="76236-145">`RunSettings` arguments</span></span>

  <span data-ttu-id="76236-146">인수는 테스트의 `RunSettings` 구성으로서 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-146">Arguments are passed as `RunSettings` configurations for the test.</span></span> <span data-ttu-id="76236-147">인수는 “-- ” 뒤에 `[name]=[value]` 쌍으로 지정됩니다(-- 뒤 공백 주의).</span><span class="sxs-lookup"><span data-stu-id="76236-147">Arguments are specified as `[name]=[value]` pairs after "-- " (note the space after --).</span></span> <span data-ttu-id="76236-148">공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76236-148">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="76236-149">예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="76236-149">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="76236-150">자세한 내용은 [vstest.console.exe: Passing RunSettings args(vstest.console.exe: RunSettings 인수 전달)](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76236-150">For more information, see [vstest.console.exe: Passing RunSettings args](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="76236-151">예</span><span class="sxs-lookup"><span data-stu-id="76236-151">Examples</span></span>

- <span data-ttu-id="76236-152">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-152">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="76236-153">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-153">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="76236-154">현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-154">Run the tests in the project in the current directory and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

## <a name="filter-option-details"></a><span data-ttu-id="76236-155">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="76236-155">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="76236-156">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-156">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="76236-157">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-157">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="76236-158">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-158">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="76236-159">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="76236-159">Test Framework</span></span> | <span data-ttu-id="76236-160">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="76236-160">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="76236-161">MSTest</span><span class="sxs-lookup"><span data-stu-id="76236-161">MSTest</span></span>         | <ul><li><span data-ttu-id="76236-162">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="76236-162">FullyQualifiedName</span></span></li><li><span data-ttu-id="76236-163">이름</span><span class="sxs-lookup"><span data-stu-id="76236-163">Name</span></span></li><li><span data-ttu-id="76236-164">ClassName</span><span class="sxs-lookup"><span data-stu-id="76236-164">ClassName</span></span></li><li><span data-ttu-id="76236-165">우선 순위</span><span class="sxs-lookup"><span data-stu-id="76236-165">Priority</span></span></li><li><span data-ttu-id="76236-166">TestCategory</span><span class="sxs-lookup"><span data-stu-id="76236-166">TestCategory</span></span></li></ul> |
| <span data-ttu-id="76236-167">xUnit</span><span class="sxs-lookup"><span data-stu-id="76236-167">xUnit</span></span>          | <ul><li><span data-ttu-id="76236-168">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="76236-168">FullyQualifiedName</span></span></li><li><span data-ttu-id="76236-169">DisplayName</span><span class="sxs-lookup"><span data-stu-id="76236-169">DisplayName</span></span></li><li><span data-ttu-id="76236-170">특성</span><span class="sxs-lookup"><span data-stu-id="76236-170">Traits</span></span></li></ul>                                   |

<span data-ttu-id="76236-171">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-171">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="76236-172">연산자</span><span class="sxs-lookup"><span data-stu-id="76236-172">Operator</span></span> | <span data-ttu-id="76236-173">기능</span><span class="sxs-lookup"><span data-stu-id="76236-173">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="76236-174">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="76236-174">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="76236-175">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="76236-175">Not exact match</span></span> |
| `~`      | <span data-ttu-id="76236-176">포함</span><span class="sxs-lookup"><span data-stu-id="76236-176">Contains</span></span>        |
| `!~`     | <span data-ttu-id="76236-177">포함하지 않음</span><span class="sxs-lookup"><span data-stu-id="76236-177">Not contains</span></span>    |

<span data-ttu-id="76236-178">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="76236-178">`<value>` is a string.</span></span> <span data-ttu-id="76236-179">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="76236-179">All the lookups are case insensitive.</span></span>

<span data-ttu-id="76236-180">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="76236-180">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="76236-181">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76236-181">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="76236-182">연산자</span><span class="sxs-lookup"><span data-stu-id="76236-182">Operator</span></span>            | <span data-ttu-id="76236-183">기능</span><span class="sxs-lookup"><span data-stu-id="76236-183">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="76236-184">또는</span><span class="sxs-lookup"><span data-stu-id="76236-184">OR</span></span>       |
| `&`                 | <span data-ttu-id="76236-185">AND</span><span class="sxs-lookup"><span data-stu-id="76236-185">AND</span></span>      |

<span data-ttu-id="76236-186">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="76236-186">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="76236-187">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76236-187">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76236-188">참조</span><span class="sxs-lookup"><span data-stu-id="76236-188">See also</span></span>

- [<span data-ttu-id="76236-189">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="76236-189">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="76236-190">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="76236-190">.NET Core Runtime IDentifier (RID) catalog</span></span>](../rid-catalog.md)
