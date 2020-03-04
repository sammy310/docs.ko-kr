---
title: dotnet vstest 명령
description: dotnet vtest 명령은 프로젝트와 모든 종속성을 빌드합니다.
ms.date: 02/27/2020
ms.openlocfilehash: 88e5b6a8966d78d0746f9ea5ccbccab142a2e0f6
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156935"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="d6379-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="d6379-103">dotnet vstest</span></span>

<span data-ttu-id="d6379-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="d6379-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d6379-105">이름</span><span class="sxs-lookup"><span data-stu-id="d6379-105">Name</span></span>

<span data-ttu-id="d6379-106">`dotnet-vstest` - 지정한 파일에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-106">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d6379-107">개요</span><span class="sxs-lookup"><span data-stu-id="d6379-107">Synopsis</span></span>

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Settings] [--Tests]
    [--TestAdapterPath] [--Platform] [--Framework] [--Parallel]
    [--TestCaseFilter] [--logger] [-lt|--ListTests]
    [--ParentProcessId] [--Port] [--Diag] [--Blame]
    [--InIsolation] [[--] <args>...]] [-?|--Help]
```

## <a name="description"></a><span data-ttu-id="d6379-108">설명</span><span class="sxs-lookup"><span data-stu-id="d6379-108">Description</span></span>

<span data-ttu-id="d6379-109">`dotnet-vstest` 명령은 `VSTest.Console` 명령줄 애플리케이션을 실행하여 자동화된 단위 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-109">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="d6379-110">인수</span><span class="sxs-lookup"><span data-stu-id="d6379-110">Arguments</span></span>

- **`TEST_FILE_NAMES`**

  <span data-ttu-id="d6379-111">지정한 어셈블리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-111">Run tests from the specified assemblies.</span></span> <span data-ttu-id="d6379-112">여러 테스트 어셈블리 이름을 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-112">Separate multiple test assembly names with spaces.</span></span> <span data-ttu-id="d6379-113">와일드카드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-113">Wildcards are supported.</span></span>

## <a name="options"></a><span data-ttu-id="d6379-114">옵션</span><span class="sxs-lookup"><span data-stu-id="d6379-114">Options</span></span>

- **`--Settings <Settings File>`**

  <span data-ttu-id="d6379-115">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-115">Settings to use when running tests.</span></span>

- **`--Tests <Test Names>`**

  <span data-ttu-id="d6379-116">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-116">Run tests with names that match the provided values.</span></span> <span data-ttu-id="d6379-117">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-117">Separate multiple values with commas.</span></span>

- **`--TestAdapterPath`**

  <span data-ttu-id="d6379-118">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-118">Use custom test adapters from a given path (if any) in the test run.</span></span>

- **`--Platform <Platform type>`**

  <span data-ttu-id="d6379-119">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-119">Target platform architecture used for test execution.</span></span> <span data-ttu-id="d6379-120">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-120">Valid values are `x86`, `x64`, and `ARM`.</span></span>

- **`--Framework <Framework Version>`**

  <span data-ttu-id="d6379-121">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-121">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="d6379-122">유효한 값의 예는 `.NETFramework,Version=v4.6` 또는 `.NETCoreApp,Version=v1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-122">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="d6379-123">지원되는 기타 값에는 `Framework40`, `Framework45`, `FrameworkCore10` 및 `FrameworkUap10`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-123">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

- **`--Parallel`**

  <span data-ttu-id="d6379-124">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-124">Run tests in parallel.</span></span> <span data-ttu-id="d6379-125">기본적으로 머신의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-125">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="d6379-126">*runsettings* 파일에서 `RunConfiguration`. 노드 아래의 `MaxCpuCount` 속성을 설정하여 코어의 개수를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-126">Specify an explicit number of cores by setting the `MaxCpuCount` property under the `RunConfiguration` node in the *runsettings* file.</span></span>

- **`--TestCaseFilter <Expression>`**

  <span data-ttu-id="d6379-127">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-127">Run tests that match the given expression.</span></span> <span data-ttu-id="d6379-128">`<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-128">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="d6379-129">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-129">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="d6379-130">하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-130">Parenthesis `()` are used to group subexpressions.</span></span>

- **`-?|--Help`**

  <span data-ttu-id="d6379-131">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-131">Prints out a short help for the command.</span></span>

- **`--logger <Logger Uri/FriendlyName>`**

  <span data-ttu-id="d6379-132">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-132">Specify a logger for test results.</span></span>

  - <span data-ttu-id="d6379-133">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-133">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - <span data-ttu-id="d6379-134">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-134">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="d6379-135">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-135">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="d6379-136">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-136">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`-lt|--ListTests <File Name>`**

  <span data-ttu-id="d6379-137">지정된 테스트 컨테이너에서 검색된 모든 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-137">Lists all discovered tests from the given test container.</span></span>

- **`--ParentProcessId <ParentProcessId>`**

  <span data-ttu-id="d6379-138">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-138">Process ID of the parent process responsible for launching the current process.</span></span>

- **`--Port <Port>`**

  <span data-ttu-id="d6379-139">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-139">Specifies the port for the socket connection and receiving the event messages.</span></span>

- **`--Diag <Path to log file>`**

  <span data-ttu-id="d6379-140">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-140">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="d6379-141">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-141">Logs are written to the provided file.</span></span>

- **`--Blame`**

  <span data-ttu-id="d6379-142">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-142">Runs the tests in blame mode.</span></span> <span data-ttu-id="d6379-143">이 옵션은 테스트 호스트를 충돌시키는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-143">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="d6379-144">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-144">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

- **`--InIsolation`**

  <span data-ttu-id="d6379-145">격리 모드에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-145">Runs the tests in an isolated process.</span></span> <span data-ttu-id="d6379-146">이렇게 하면 *vstest.console.exe* 프로세스가 테스트 시 오류에서 중지될 가능성은 매우 적지만 테스트 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-146">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

- **`@<file>`**

  <span data-ttu-id="d6379-147">추가 옵션에 대한 지시 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-147">Reads response file for more options.</span></span>

- **`args`**

  <span data-ttu-id="d6379-148">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-148">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="d6379-149">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-149">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="d6379-150">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-150">Use a space to separate multiple arguments.</span></span>

## <a name="examples"></a><span data-ttu-id="d6379-151">예</span><span class="sxs-lookup"><span data-stu-id="d6379-151">Examples</span></span>

<span data-ttu-id="d6379-152">*mytestproject.dll*에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-152">Run tests in *mytestproject.dll*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll
```

<span data-ttu-id="d6379-153">*mytestproject.dll*에서 테스트를 실행하고 사용자 지정 이름을 갖는 사용자 지정 폴더로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-153">Run tests in *mytestproject.dll*, exporting to custom folder with custom name:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

<span data-ttu-id="d6379-154">*mytestproject.dll* 및 *myothertestproject.exe*에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-154">Run tests in *mytestproject.dll* and *myothertestproject.exe*:</span></span>

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

<span data-ttu-id="d6379-155">`TestMethod1` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-155">Run `TestMethod1` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

<span data-ttu-id="d6379-156">`TestMethod1` 및 `TestMethod2` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6379-156">Run `TestMethod1` and `TestMethod2` tests:</span></span>

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```
