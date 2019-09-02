---
title: dotnet vstest 명령
description: dotnet vtest 명령은 프로젝트와 모든 종속성을 빌드합니다.
author: mairaw
ms.date: 05/30/2018
ms.openlocfilehash: 4630982ba21ab37b051895faf3dc0fcd8784cb18
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202782"
---
# <a name="dotnet-vstest"></a><span data-ttu-id="664b9-103">dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="664b9-103">dotnet vstest</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="664b9-104">name</span><span class="sxs-lookup"><span data-stu-id="664b9-104">Name</span></span>

<span data-ttu-id="664b9-105">`dotnet-vstest` - 지정한 파일에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-105">`dotnet-vstest` - Runs tests from the specified files.</span></span>

## <a name="synopsis"></a><span data-ttu-id="664b9-106">개요</span><span class="sxs-lookup"><span data-stu-id="664b9-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="664b9-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="664b9-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [--Blame|/Blame] [--InIsolation|/InIsolation]
    [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="664b9-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="664b9-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath] 
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger]
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="664b9-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="664b9-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet vstest [<TEST_FILE_NAMES>] [--Settings|/Settings] [--Tests|/Tests] [--TestAdapterPath|/TestAdapterPath]
    [--Platform|/Platform] [--Framework|/Framework] [--Parallel|/Parallel] [--TestCaseFilter|/TestCaseFilter] [--logger|/logger] 
    [-lt|--ListTests|/lt|/ListTests] [--ParentProcessId|/ParentProcessId] [--Port|/Port] [--Diag|/Diag] [[--] <args>...]] [-?|--Help|/?|/Help]
```

---

## <a name="description"></a><span data-ttu-id="664b9-110">설명</span><span class="sxs-lookup"><span data-stu-id="664b9-110">Description</span></span>

<span data-ttu-id="664b9-111">`dotnet-vstest` 명령은 `VSTest.Console` 명령줄 애플리케이션을 실행하여 자동화된 단위 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-111">The `dotnet-vstest` command runs the `VSTest.Console` command-line application to run automated unit tests.</span></span>

## <a name="arguments"></a><span data-ttu-id="664b9-112">인수</span><span class="sxs-lookup"><span data-stu-id="664b9-112">Arguments</span></span>

`TEST_FILE_NAMES`

<span data-ttu-id="664b9-113">지정한 어셈블리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-113">Run tests from the specified assemblies.</span></span> <span data-ttu-id="664b9-114">여러 테스트 어셈블리 이름을 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-114">Separate multiple test assembly names with spaces.</span></span>

## <a name="options"></a><span data-ttu-id="664b9-115">옵션</span><span class="sxs-lookup"><span data-stu-id="664b9-115">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="664b9-116">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="664b9-116">.NET Core 2.1</span></span>](#tab/netcore21)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="664b9-117">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-117">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="664b9-118">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-118">Run tests with names that match the provided values.</span></span> <span data-ttu-id="664b9-119">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-119">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="664b9-120">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-120">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="664b9-121">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-121">Target platform architecture used for test execution.</span></span> <span data-ttu-id="664b9-122">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-122">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="664b9-123">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-123">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="664b9-124">유효한 값의 예는 `.NETFramework,Version=v4.6` 또는 `.NETCoreApp,Version=v1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-124">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="664b9-125">지원되는 기타 값에는 `Framework40`, `Framework45`, `FrameworkCore10` 및 `FrameworkUap10`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-125">Other supported values are `Framework40`, `Framework45`, `FrameworkCore10`, and `FrameworkUap10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="664b9-126">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-126">Execute tests in parallel.</span></span> <span data-ttu-id="664b9-127">기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-127">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="664b9-128">runsettings 파일에서 RunConfiguration 노드 아래의 MaxCpuCount 속성을 설정하여 코어의 개수를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-128">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="664b9-129">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-129">Run tests that match the given expression.</span></span> <span data-ttu-id="664b9-130">`<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-130">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="664b9-131">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-131">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="664b9-132">하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-132">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="664b9-133">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-133">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="664b9-134">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-134">Specify a logger for test results.</span></span>

* <span data-ttu-id="664b9-135">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-135">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="664b9-136">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-136">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="664b9-137">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-137">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="664b9-138">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-138">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="664b9-139">지정된 테스트 컨테이너에서 검색된 모든 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-139">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="664b9-140">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-140">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="664b9-141">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-141">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="664b9-142">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-142">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="664b9-143">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-143">Logs are written to the provided file.</span></span>

`--Blame|/Blame`

<span data-ttu-id="664b9-144">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-144">Runs the tests in blame mode.</span></span> <span data-ttu-id="664b9-145">이 옵션은 테스트 호스트를 충돌시키는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-145">This option is helpful in isolating the problematic tests causing test host to crash.</span></span> <span data-ttu-id="664b9-146">현재 디렉터리에 크래시 전에 테스트 실행 순서를 캡처하는 *Sequence.xml*이라는 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-146">It creates an output file in the current directory as *Sequence.xml* that captures the order of tests execution before the crash.</span></span>

`--InIsolation|/InIsolation`

<span data-ttu-id="664b9-147">격리 모드에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-147">Runs the tests in an isolated process.</span></span> <span data-ttu-id="664b9-148">이렇게 하면 *vstest.console.exe* 프로세스가 테스트 시 오류에서 중지될 가능성은 매우 적지만 테스트 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-148">This makes *vstest.console.exe* process less likely to be stopped on an error in the tests, but tests may run slower.</span></span>

`@<file>`

<span data-ttu-id="664b9-149">추가 옵션에 대한 지시 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-149">Reads response file for more options.</span></span>

`args`

<span data-ttu-id="664b9-150">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-150">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="664b9-151">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-151">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="664b9-152">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-152">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="664b9-153">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="664b9-153">.NET Core 2.0</span></span>](#tab/netcore20)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="664b9-154">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-154">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="664b9-155">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-155">Run tests with names that match the provided values.</span></span> <span data-ttu-id="664b9-156">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-156">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="664b9-157">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-157">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="664b9-158">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-158">Target platform architecture used for test execution.</span></span> <span data-ttu-id="664b9-159">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-159">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="664b9-160">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-160">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="664b9-161">유효한 값의 예는 `.NETFramework,Version=v4.6` 또는 `.NETCoreApp,Version=v1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-161">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="664b9-162">그 밖의 지원되는 값은 `Framework40`, `Framework45` 및 `FrameworkCore10`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-162">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="664b9-163">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-163">Execute tests in parallel.</span></span> <span data-ttu-id="664b9-164">기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-164">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="664b9-165">runsettings 파일에서 RunConfiguration 노드 아래의 MaxCpuCount 속성을 설정하여 코어의 개수를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-165">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="664b9-166">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-166">Run tests that match the given expression.</span></span> <span data-ttu-id="664b9-167">`<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-167">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="664b9-168">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-168">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="664b9-169">하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-169">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="664b9-170">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-170">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="664b9-171">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-171">Specify a logger for test results.</span></span>

* <span data-ttu-id="664b9-172">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-172">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="664b9-173">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-173">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="664b9-174">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-174">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="664b9-175">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-175">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="664b9-176">지정된 테스트 컨테이너에서 검색된 모든 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-176">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="664b9-177">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-177">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="664b9-178">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-178">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="664b9-179">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-179">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="664b9-180">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-180">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="664b9-181">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-181">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="664b9-182">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-182">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="664b9-183">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-183">Use a space to separate multiple arguments.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="664b9-184">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="664b9-184">.NET Core 1.x</span></span>](#tab/netcore1x)

`--Settings|/Settings:<Settings File>`

<span data-ttu-id="664b9-185">테스트를 실행할 때 사용할 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-185">Settings to use when running tests.</span></span>

`--Tests|/Tests:<Test Names>`

<span data-ttu-id="664b9-186">제공된 값과 같은 이름의 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-186">Run tests with names that match the provided values.</span></span> <span data-ttu-id="664b9-187">여러 값을 쉼표로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-187">Separate multiple values with commas.</span></span>

`--TestAdapterPath|/TestAdapterPath`

<span data-ttu-id="664b9-188">테스트 실행에서 지정된 경로(있는 경우)의 사용자 지정 테스트 어댑터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-188">Use custom test adapters from a given path (if any) in the test run.</span></span>

`--Platform|/Platform:<Platform type>`

<span data-ttu-id="664b9-189">테스트를 실행하는 데 사용되는 대상 플랫폼 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-189">Target platform architecture used for test execution.</span></span> <span data-ttu-id="664b9-190">유효한 값은 `x86`, `x64` 및 `ARM`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-190">Valid values are `x86`, `x64`, and `ARM`.</span></span>

`--Framework|/Framework:<Framework Version>`

<span data-ttu-id="664b9-191">테스트 실행에 사용되는 대상 .NET Framework 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-191">Target .NET Framework version used for test execution.</span></span> <span data-ttu-id="664b9-192">유효한 값의 예는 `.NETFramework,Version=v4.6` 또는 `.NETCoreApp,Version=v1.0`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-192">Examples of valid values are `.NETFramework,Version=v4.6` or `.NETCoreApp,Version=v1.0`.</span></span> <span data-ttu-id="664b9-193">그 밖의 지원되는 값은 `Framework40`, `Framework45` 및 `FrameworkCore10`입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-193">Other supported values are `Framework40`, `Framework45`, and `FrameworkCore10`.</span></span>

`--Parallel|/Parallel`

<span data-ttu-id="664b9-194">테스트를 병렬로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-194">Execute tests in parallel.</span></span> <span data-ttu-id="664b9-195">기본적으로 컴퓨터의 사용 가능한 모든 코어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-195">By default, all available cores on the machine are available for use.</span></span> <span data-ttu-id="664b9-196">runsettings 파일에서 RunConfiguration 노드 아래의 MaxCpuCount 속성을 설정하여 코어의 개수를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-196">Specify an explicit number of cores by setting the MaxCpuCount property under the RunConfiguration node in the runsettings file.</span></span>

`--TestCaseFilter|/TestCaseFilter:<Expression>`

<span data-ttu-id="664b9-197">지정된 식과 일치하는 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-197">Run tests that match the given expression.</span></span> <span data-ttu-id="664b9-198">`<Expression>`은 `<property>Operator<value>[|&<Expression>]` 형식입니다. 여기서 Operator는 `=`, `!=` 또는 `~` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-198">`<Expression>` is of the format `<property>Operator<value>[|&<Expression>]`, where Operator is one of `=`, `!=`, or `~`.</span></span> <span data-ttu-id="664b9-199">연산자 `~`는 '포함' 의미 체계를 가지며 `DisplayName`과 같은 문자열 속성에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-199">Operator `~` has 'contains' semantics and is applicable for string properties like `DisplayName`.</span></span> <span data-ttu-id="664b9-200">하위 식을 그룹으로 묶는 데 괄호 `()`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-200">Parenthesis `()` are used to group sub-expressions.</span></span>

`-?|--Help|/?|/Help`

<span data-ttu-id="664b9-201">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-201">Prints out a short help for the command.</span></span>

`--logger|/logger:<Logger Uri/FriendlyName>`

<span data-ttu-id="664b9-202">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-202">Specify a logger for test results.</span></span>

* <span data-ttu-id="664b9-203">Team Foundation Server에 테스트 결과를 게시하려면 `TfsPublisher` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-203">To publish test results to Team Foundation Server, use the `TfsPublisher` logger provider:</span></span>

  ```console
  /logger:TfsPublisher;
      Collection=<team project collection url>;
      BuildName=<build name>;
      TeamProject=<team project name>
      [;Platform=<Defaults to "Any CPU">]
      [;Flavor=<Defaults to "Debug">]
      [;RunTitle=<title>]
  ```

* <span data-ttu-id="664b9-204">Visual Studio 테스트 결과 파일(TRX)에 결과를 기록하려면 `trx` 로거 공급자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-204">To log results to a Visual Studio Test Results File (TRX), use the `trx` logger provider.</span></span> <span data-ttu-id="664b9-205">이 스위치는 지정된 로그 파일 이름을 사용하여 테스트 결과 디렉터리에 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-205">This switch creates a file in the test results directory with given log file name.</span></span> <span data-ttu-id="664b9-206">`LogFileName`이 제공되지 않으면 테스트 결과를 포함할 고유한 파일 이름이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-206">If `LogFileName` isn't provided, a unique file name is created to hold the test results.</span></span>

  ```console
  /logger:trx [;LogFileName=<Defaults to unique file name>]
  ```

`-lt|--ListTests|/lt|/ListTests:<File Name>`

<span data-ttu-id="664b9-207">지정된 테스트 컨테이너에서 검색된 모든 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-207">Lists all discovered tests from the given test container.</span></span>

`--ParentProcessId|/ParentProcessId:<ParentProcessId>`

<span data-ttu-id="664b9-208">현재 프로세스를 시작하는 일을 담당하는 부모 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-208">Process ID of the parent process responsible for launching the current process.</span></span>

`--Port|/Port:<Port>`

<span data-ttu-id="664b9-209">소켓 연결 및 이벤트 메시지를 받기 위한 포트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-209">Specifies the port for the socket connection and receiving the event messages.</span></span>

`--Diag|/Diag:<Path to log file>`

<span data-ttu-id="664b9-210">테스트 플랫폼에 대한 자세한 정보 로그를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-210">Enables verbose logs for the test platform.</span></span> <span data-ttu-id="664b9-211">로그는 제공된 파일에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-211">Logs are written to the provided file.</span></span>

`args`

<span data-ttu-id="664b9-212">어댑터에 전달될 추가 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-212">Specifies extra arguments to pass to the adapter.</span></span> <span data-ttu-id="664b9-213">인수는 `<n>=<v>` 형식의 이름-값 쌍으로 지정됩니다. 여기서 `<n>`은 인수 이름이고 `<v>`는 인수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-213">Arguments are specified as name-value pairs of the form `<n>=<v>`, where `<n>` is the argument name and `<v>` is the argument value.</span></span> <span data-ttu-id="664b9-214">여러 개의 인수를 구분하려면 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-214">Use a space to separate multiple arguments.</span></span>

---

## <a name="examples"></a><span data-ttu-id="664b9-215">예제</span><span class="sxs-lookup"><span data-stu-id="664b9-215">Examples</span></span>

<span data-ttu-id="664b9-216">`mytestproject.dll`에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-216">Run tests in `mytestproject.dll`:</span></span>

`dotnet vstest mytestproject.dll`

<span data-ttu-id="664b9-217">사용자 지정 이름으로 사용자 지정 폴더로 내보내 `mytestproject.dll`에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-217">Run tests in `mytestproject.dll`, exporting to custom folder with custom name:</span></span>

`dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path`

<span data-ttu-id="664b9-218">`mytestproject.dll` 및 `myothertestproject.exe`에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-218">Run tests in `mytestproject.dll` and `myothertestproject.exe`:</span></span>

`dotnet vstest mytestproject.dll myothertestproject.exe`

<span data-ttu-id="664b9-219">`TestMethod1` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-219">Run `TestMethod1` tests:</span></span>

`dotnet vstest /Tests:TestMethod1`

<span data-ttu-id="664b9-220">`TestMethod1` 및 `TestMethod2` 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="664b9-220">Run `TestMethod1` and `TestMethod2` tests:</span></span>

`dotnet vstest /Tests:TestMethod1,TestMethod2`
