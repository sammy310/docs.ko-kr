---
title: dotnet vstest 명령
description: dotnet vtest 명령은 프로젝트와 모든 종속성을 빌드합니다.
ms.date: 02/27/2020
ms.openlocfilehash: e8fa94cf12ca2fe5fb99c6e3c1dcdb52185798c0
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463282"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="e6dff-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="e6dff-103">dotnet vstest</span></span>

<span data-ttu-id="e6dff-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e6dff-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e6dff-105">이름</span><span class="sxs-lookup"><span data-stu-id="e6dff-105">Name</span></span>

<span data-ttu-id="e6dff-106">`dotnet-vstest` - 지정한 파일에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e6dff-107">개요</span><span class="sxs-lookup"><span data-stu-id="e6dff-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a><span data-ttu-id="e6dff-108">설명</span><span class="sxs-lookup"><span data-stu-id="e6dff-108">Description</span></span>

<span data-ttu-id="e6dff-109">`dotnet-vstest` 명령은 `VSTest.Console` 명령줄 애플리케이션을 실행하여 자동화된 단위 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="e6dff-110">인수</span><span class="sxs-lookup"><span data-stu-id="e6dff-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="e6dff-111">지정한 어셈블리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="e6dff-112">여러 테스트 어셈블리 이름을 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="e6dff-113">와일드카드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="e6dff-114">옵션</span><span class="sxs-lookup"><span data-stu-id="e6dff-114">Options</span></span>

- **`--Blame`**

  <span data-ttu-id="e6dff-115">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-115">Runs the tests in blame mode.</span></span> <span data-ttu-id="e6dff-116">이 옵션은 테스트 호스트를 충돌시키는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-116">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="e6dff-117">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-117">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--Diag <PATH_TO_LOG_FILE>`**

  <span data-ttu-id="e6dff-118">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-118">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="e6dff-119">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-119">Logs are written to the provided file.</span></span>

- **`--Framework <FRAMEWORK>`**

  <span data-ttu-id="e6dff-120">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-120">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="e6dff-121">유효한 값의 예는 `.NETFramework,Version=v4.6` 또는 `.NETCoreApp,Version=v1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-121">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="e6dff-122">지원되는 기타 값에는 `Framework40`, `Framework45`, `FrameworkCore10` 및 `FrameworkUap10`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-122">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="e6dff-123">격리 모드에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-123">Runs the tests in an isolated process.</span></span> <span data-ttu-id="e6dff-124">이렇게 하면 *vstest.console.exe* 프로세스가 테스트 시 오류에서 중지될 가능성은 매우 적지만 테스트 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-124">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`-lt|--ListTests <FILE_NAME>`**

  <span data-ttu-id="e6dff-125">지정된 테스트 컨테이너에서 검색된 모든 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-125">Lists all discovered tests from the given test container.</span></span>

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  <span data-ttu-id="e6dff-126">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-126">Specify a logger for test results.</span></span>

  - <span data-ttu-id="e6dff-127">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-127">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="e6dff-128">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-128">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="e6dff-129">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-129">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="e6dff-130">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-130">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  <span data-ttu-id="e6dff-131">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-131">Run tests in parallel.</span></span> <span data-ttu-id="e6dff-132">기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-132">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="e6dff-133">*runsettings* 파일에서 `RunConfiguration`. 노드 아래의 `MaxCpuCount` 속성을 설정하여 코어의 개수를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-133">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--ParentProcessId <PROCESS_ID>`**

  <span data-ttu-id="e6dff-134">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-134">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Platform <PLATFORM_TYPE>`**

  <span data-ttu-id="e6dff-135">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-135">Target platform architecture used for test execution.</span></span> <span data-ttu-id="e6dff-136">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-136">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Port <PORT>`**

  <span data-ttu-id="e6dff-137">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-137">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--ResultsDirectory:<PATH>`**

  <span data-ttu-id="e6dff-138">테스트 결과 디렉터리가 존재하지 않는 경우 지정된 경로에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-138">Test results directory will be created in specified path if not exists.</span></span>

- **`--Settings <SETTINGS_FILE>`**

  <span data-ttu-id="e6dff-139">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-139">Settings to use when running tests.</span></span>

- **`--TestAdapterPath <PATH>`**

  <span data-ttu-id="e6dff-140">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-140">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--TestCaseFilter <EXPRESSION>`**

  <span data-ttu-id="e6dff-141">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-141">Run tests that match the given expression.</span></span> <span data-ttu-id="e6dff-142">`<EXPRESSION>`은 `<property>Operator<value>[|&<EXPRESSION>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-142">`<EXPRESSION>` is of the format `<property>Operator<value>[|&<EXPRESSION>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="e6dff-143">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-143">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="e6dff-144">괄호 `()`를 사용하여 하위 식을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-144">Parentheses `()` are used to group subexpressions.</span></span> <span data-ttu-id="e6dff-145">자세한 내용은 [TestCase 필터](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6dff-145">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

- **`--Tests <TEST_NAMES>`**

  <span data-ttu-id="e6dff-146">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-146">Run tests with names that match the provided values.</span></span> <span data-ttu-id="e6dff-147">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-147">Separate multiple values with commas.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="e6dff-148">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-148">Prints out a short help for the command.</span></span>

- **`@<file>`**

  <span data-ttu-id="e6dff-149">추가 옵션에 대한 지시 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-149">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="e6dff-150">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="e6dff-151">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="e6dff-152">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-152">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="e6dff-153">예</span><span class="sxs-lookup"><span data-stu-id="e6dff-153">Examples</span></span>

<span data-ttu-id="e6dff-154">*mytestproject.dll*에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-154">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="e6dff-155">*mytestproject.dll*에서 테스트를 실행하고 사용자 지정 이름을 갖는 사용자 지정 폴더로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-155">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="e6dff-156">*mytestproject.dll* 및 *myothertestproject.exe*에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-156">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="e6dff-157">`TestMethod1` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-157">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="e6dff-158">`TestMethod1` 및 `TestMethod2` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6dff-158">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a><span data-ttu-id="e6dff-159">참조</span><span class="sxs-lookup"><span data-stu-id="e6dff-159">See also</span></span>

- [<span data-ttu-id="e6dff-160">VSTest.Console.exe 명령줄 옵션</span><span class="sxs-lookup"><span data-stu-id="e6dff-160">VSTest.Console.exe command-line options</span></span>](/visualstudio/test/vstest-console-options)
