---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 04/29/2020
ms.openlocfilehash: 5ecfa24905537a663cd967142b765c258495fb22
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537741"
---
# <a name="dotnet-test"></a><span data-ttu-id="ed8d2-103">dotnet test</span><span class="sxs-lookup"><span data-stu-id="ed8d2-103">dotnet test</span></span>

<span data-ttu-id="ed8d2-104">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="ed8d2-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ed8d2-105">이름</span><span class="sxs-lookup"><span data-stu-id="ed8d2-105">Name</span></span>

<span data-ttu-id="ed8d2-106">`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-106">`dotnet test` - .NET test driver used to execute unit tests.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ed8d2-107">개요</span><span class="sxs-lookup"><span data-stu-id="ed8d2-107">Synopsis</span></span>

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <ADAPTER_PATH>] [--blame] [--blame-crash]
    [--blame-crash-dump-type <DUMP_TYPE>] [--blame-crash-collect-always]
    [--blame-hang] [--blame-hang-dump-type <DUMP_TYPE>]
    [--blame-hang-timeout <TIMESPAN>]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_NAME>]
    [-d|--diag <LOG_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <RESULTS_DIR>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a><span data-ttu-id="ed8d2-108">설명</span><span class="sxs-lookup"><span data-stu-id="ed8d2-108">Description</span></span>

<span data-ttu-id="ed8d2-109">`dotnet test` 명령은 지정된 솔루션에서 단위 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-109">The `dotnet test` command is used to execute unit tests in a given solution.</span></span> <span data-ttu-id="ed8d2-110">`dotnet test` 명령은 솔루션을 빌드하고 솔루션의 각 테스트 프로젝트에 대해 테스트 호스트 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-110">The `dotnet test` command builds the solution and runs a test host application for each test project in the solution.</span></span> <span data-ttu-id="ed8d2-111">테스트 호스트는 테스트 프레임워크를 사용하여 지정된 프로젝트에서 MSTest, NUnit 또는 xUnit 등의 테스트를 실행하고 각 테스트의 성공이나 실패를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-111">The test host executes tests in the given project using a test framework, for example: MSTest, NUnit, or xUnit, and reports the success or failure of each test.</span></span> <span data-ttu-id="ed8d2-112">모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-112">If all tests are successful, the test runner returns 0 as an exit code; otherwise if any test fails, it returns 1.</span></span>

<span data-ttu-id="ed8d2-113">멀티 타기팅 프로젝트의 경우 각 대상 프레임워크에 대해 테스트가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-113">For multi-targeted projects, tests are run for each targeted framework.</span></span> <span data-ttu-id="ed8d2-114">테스트 호스트와 단위 테스트 프레임워크는 NuGet 패키지로 패키징되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-114">The test host and the unit test framework are packaged as NuGet packages and are restored as ordinary dependencies for the project.</span></span>

<span data-ttu-id="ed8d2-115">테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-115">Test projects specify the test runner using an ordinary `<PackageReference>` element, as seen in the following sample project file:</span></span>

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

<span data-ttu-id="ed8d2-116">여기서 `Microsoft.NET.Test.Sdk`는 테스트 호스트이고 `xunit`은 테스트 프레임워크입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-116">Where `Microsoft.NET.Test.Sdk` is the test host, `xunit` is the test framework.</span></span> <span data-ttu-id="ed8d2-117">`xunit.runner.visualstudio`는 xUnit 프레임워크가 테스트 호스트와 함께 작동할 수 있도록 하는 테스트 어댑터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-117">And `xunit.runner.visualstudio` is a test adapter, which allows the xUnit framework to work with the test host.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="ed8d2-118">암시적 복원</span><span class="sxs-lookup"><span data-stu-id="ed8d2-118">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="ed8d2-119">인수</span><span class="sxs-lookup"><span data-stu-id="ed8d2-119">Arguments</span></span>

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - <span data-ttu-id="ed8d2-120">테스트 프로젝트의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-120">Path to the test project.</span></span>
  - <span data-ttu-id="ed8d2-121">솔루션의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-121">Path to the solution.</span></span>
  - <span data-ttu-id="ed8d2-122">프로젝트 또는 솔루션이 포함된 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-122">Path to a directory that contains a project or a solution.</span></span>
  - <span data-ttu-id="ed8d2-123">테스트 프로젝트 *.dll* 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-123">Path to a test project *.dll* file.</span></span>

  <span data-ttu-id="ed8d2-124">지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 또는 솔루션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-124">If not specified, it searches for a project or a solution in the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="ed8d2-125">옵션</span><span class="sxs-lookup"><span data-stu-id="ed8d2-125">Options</span></span>

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  <span data-ttu-id="ed8d2-126">추가 테스트 어댑터를 검색할 디렉터리의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-126">Path to a directory to be searched for additional test adapters.</span></span> <span data-ttu-id="ed8d2-127">접미사가 `.TestAdapter.dll`인 *.dll* 파일만 검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-127">Only *.dll* files with suffix `.TestAdapter.dll` are inspected.</span></span> <span data-ttu-id="ed8d2-128">지정하지 않으면 테스트 *.dll*의 디렉터리가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-128">If not specified, the directory of the test *.dll* is searched.</span></span>

- **`--blame`**

  <span data-ttu-id="ed8d2-129">테스트를 원인 모드로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-129">Runs the tests in blame mode.</span></span> <span data-ttu-id="ed8d2-130">이 옵션은 테스트 호스트의 크래시를 유발하는 문제가 있는 테스트를 격리하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-130">This option is helpful in isolating problematic tests that cause the test host to crash.</span></span> <span data-ttu-id="ed8d2-131">크래시가 감지되면 크래시 전에 실행된 테스트의 순서를 캡처하는 시퀀스 파일이 `TestResults/<Guid>/<Guid>_Sequence.xml`에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-131">When a crash is detected, it creates a sequence file in `TestResults/<Guid>/<Guid>_Sequence.xml` that captures the order of tests that were run before the crash.</span></span>

- <span data-ttu-id="ed8d2-132">**`--blame-crash`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-132">**`--blame-crash`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-133">테스트를 원인 모드를 실행하고 테스트 호스트가 예기치 않게 종료될 때 크래시 덤프를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-133">Runs the tests in blame mode and collects a crash dump when the test host exits unexpectedly.</span></span> <span data-ttu-id="ed8d2-134">해당 옵션은 Windows에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-134">This option is only supported on Windows.</span></span> <span data-ttu-id="ed8d2-135">*procdump.exe* 및 *procdump64.exe*를 포함하는 디렉터리가 PATH 또는 PROCDUMP_PATH 환경 변수에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-135">A directory that contains *procdump.exe* and *procdump64.exe* must be in the PATH or PROCDUMP_PATH environment variable.</span></span> <span data-ttu-id="ed8d2-136">[도구 다운로드](/sysinternals/downloads/procdump).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-136">[Download the tools](/sysinternals/downloads/procdump).</span></span> <span data-ttu-id="ed8d2-137">`--blame`을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-137">Implies `--blame`.</span></span>

- <span data-ttu-id="ed8d2-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-138">**`--blame-crash-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-139">수집할 크래시 덤프의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-139">The type of crash dump to be collected.</span></span> <span data-ttu-id="ed8d2-140">`--blame-crash`를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-140">Implies `--blame-crash`.</span></span>

- <span data-ttu-id="ed8d2-141">**`--blame-crash-collect-always`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-141">**`--blame-crash-collect-always`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-142">예상된 테스트 호스트 종료와 예기치 않은 테스트 호스트 종료시 크래시 덤프를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-142">Collects a crash dump on expected as well as unexpected test host exit.</span></span>

- <span data-ttu-id="ed8d2-143">**`--blame-hang`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-143">**`--blame-hang`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-144">테스트를 원인 모드로 실행하고 테스트가 지정된 시간 제한을 초과하는 경우 중단 덤프를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-144">Run the tests in blame mode and collects a hang dump when a test exceeds the given timeout.</span></span>

- <span data-ttu-id="ed8d2-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-145">**`--blame-hang-dump-type <DUMP_TYPE>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-146">수집할 크래시 덤프의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-146">The type of crash dump to be collected.</span></span> <span data-ttu-id="ed8d2-147">`full`, `mini` 또는 `none`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-147">It should be `full`, `mini`, or `none`.</span></span> <span data-ttu-id="ed8d2-148">`none`을 지정하면 테스트 호스트가 시간 초과시 종료되지만 덤프를 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-148">When `none` is specified, test host is terminated on timeout, but no dump is collected.</span></span> <span data-ttu-id="ed8d2-149">`--blame-hang`을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-149">Implies `--blame-hang`.</span></span>

- <span data-ttu-id="ed8d2-150">**`--blame-hang-timeout <TIMESPAN>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)</span><span class="sxs-lookup"><span data-stu-id="ed8d2-150">**`--blame-hang-timeout <TIMESPAN>`** (Available since .NET 5.0 preview SDK)</span></span>

  <span data-ttu-id="ed8d2-151">중단 덤프가 트리거되고 테스트 호스트 프로세스가 종료되는 테스트별 시간 제한입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-151">Per-test timeout, after which a hang dump is triggered and the test host process is terminated.</span></span> <span data-ttu-id="ed8d2-152">시간 제한 값은 다음 형식 중 하나로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-152">The timeout value is specified in one of the following formats:</span></span>
  
  - <span data-ttu-id="ed8d2-153">1.5h</span><span class="sxs-lookup"><span data-stu-id="ed8d2-153">1.5h</span></span>
  - <span data-ttu-id="ed8d2-154">90m</span><span class="sxs-lookup"><span data-stu-id="ed8d2-154">90m</span></span>
  - <span data-ttu-id="ed8d2-155">5400s</span><span class="sxs-lookup"><span data-stu-id="ed8d2-155">5400s</span></span>
  - <span data-ttu-id="ed8d2-156">5400000ms</span><span class="sxs-lookup"><span data-stu-id="ed8d2-156">5400000ms</span></span>

  <span data-ttu-id="ed8d2-157">단위를 사용하지 않으면(예: 5400000) 값은 밀리초 단위로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-157">When no unit is used (for example, 5400000), the value is assumed to be in milliseconds.</span></span> <span data-ttu-id="ed8d2-158">데이터 기반 테스트와 함께 사용되는 경우 시간 제한 동작은 사용되는 테스트 어댑터에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-158">When used together with data driven tests, the timeout behavior depends on the test adapter used.</span></span> <span data-ttu-id="ed8d2-159">xUnit 및 NUnit의 경우 모든 테스트 사례 후에 시간 제한이 갱신됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-159">For xUnit and NUnit the timeout is renewed after every test case.</span></span> <span data-ttu-id="ed8d2-160">MSTest의 경우 모든 테스트 사례에 시간 제한이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-160">For MSTest, the timeout is used for all test cases.</span></span> <span data-ttu-id="ed8d2-161">이 옵션은 현재 netcoreapp2.1 이상이 사용되는 Windows와 netcoreapp3.1 이상이 사용되는 Linux에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-161">This option is supported on Windows with netcoreapp2.1 and later, and on Linux with netcoreapp3.1 and later.</span></span> <span data-ttu-id="ed8d2-162">macOS는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-162">macOS is not supported.</span></span>

- **`-c|--configuration <CONFIGURATION>`**

  <span data-ttu-id="ed8d2-163">빌드 구성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-163">Defines the build configuration.</span></span> <span data-ttu-id="ed8d2-164">기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-164">The default value is `Debug`, but your project's configuration could override this default SDK setting.</span></span>

- **`--collect <DATA_COLLECTOR_NAME>`**

  <span data-ttu-id="ed8d2-165">테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-165">Enables data collector for the test run.</span></span> <span data-ttu-id="ed8d2-166">자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-166">For more information, see [Monitor and analyze test run](https://aka.ms/vstest-collect).</span></span>
  
  <span data-ttu-id="ed8d2-167">.NET Core가 지원하는 플랫폼에서 코드 검사를 수집하려면 [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md)을 설치하고 `--collect:"XPlat Code Coverage"` 옵션을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-167">To collect code coverage on any platform that is supported by .NET Core, install [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md) and use the `--collect:"XPlat Code Coverage"` option.</span></span>

  <span data-ttu-id="ed8d2-168">Windows에서는 `--collect "Code Coverage"` 옵션을 사용하여 코드 검사를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-168">On Windows, you can collect code coverage by using the `--collect "Code Coverage"` option.</span></span> <span data-ttu-id="ed8d2-169">이 옵션은 Visual Studio 2019 Enterprise에서 열 수 있는 *.coverage* 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-169">This option generates a *.coverage* file, which can be opened in Visual Studio 2019 Enterprise.</span></span> <span data-ttu-id="ed8d2-170">자세한 내용은 [코드 검사 사용](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) 및 [코드 검사 분석 사용자 지정](/visualstudio/test/customizing-code-coverage-analysis)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-170">For more information, see [Use code coverage](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) and [Customize code coverage analysis](/visualstudio/test/customizing-code-coverage-analysis).</span></span>

- **`-d|--diag <LOG_FILE>`**

  <span data-ttu-id="ed8d2-171">테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에, 그리고 옆의 파일에 진단 메시지를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-171">Enables diagnostic mode for the test platform and writes diagnostic messages to the specified file and to files next to it.</span></span> <span data-ttu-id="ed8d2-172">메시지를 기록하는 프로세스에 따라 생성되는 파일이 결정됩니다(예를 들어 테스트 호스트 로그의 경우 `*.host_<date>.txt`, 데이터 수집기 로그의 경우 `*.datacollector_<date>.txt`).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-172">The process that is logging the messages determines which files are created, such as `*.host_<date>.txt` for test host log, and `*.datacollector_<date>.txt` for data collector log.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ed8d2-173">테스트 이진 파일에 `dotnet` 또는 .NET Framework 테스트 호스트를 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-173">Forces the use of `dotnet` or .NET Framework test host for the test binaries.</span></span> <span data-ttu-id="ed8d2-174">이 옵션은 사용할 호스트 유형만 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-174">This option only determines which type of host to use.</span></span> <span data-ttu-id="ed8d2-175">사용할 실제 프레임워크 버전은 테스트 프로젝트의 *runtimeconfig.json*에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-175">The actual framework version to be used is determined by the *runtimeconfig.json* of the test project.</span></span> <span data-ttu-id="ed8d2-176">지정하지 않으면 [TargetFramework 어셈블리 특성](/dotnet/api/system.runtime.versioning.targetframeworkattribute)이 사용되어 호스트 유형이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-176">When not specified, the [TargetFramework assembly attribute](/dotnet/api/system.runtime.versioning.targetframeworkattribute) is used to determine the type of host.</span></span> <span data-ttu-id="ed8d2-177">해당 특성이 *.dll*에서 제거되면 .NET Framework 호스트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-177">When that attribute is stripped from the *.dll*, the .NET Framework host is used.</span></span>

- **`--filter <EXPRESSION>`**

  <span data-ttu-id="ed8d2-178">지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-178">Filters out tests in the current project using the given expression.</span></span> <span data-ttu-id="ed8d2-179">자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-179">For more information, see the [Filter option details](#filter-option-details) section.</span></span> <span data-ttu-id="ed8d2-180">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-180">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

- **`-h|--help`**

  <span data-ttu-id="ed8d2-181">명령에 대한 간단한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-181">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="ed8d2-182">명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-182">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="ed8d2-183">예를 들어 인증을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-183">For example, to complete authentication.</span></span> <span data-ttu-id="ed8d2-184">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-184">Available since .NET Core 3.0 SDK.</span></span>

- **`-l|--logger <LOGGER>`**

  <span data-ttu-id="ed8d2-185">테스트 결과에 대해 로거를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-185">Specifies a logger for test results.</span></span> <span data-ttu-id="ed8d2-186">MSBuild와 달리 dotnet 테스트에서는 약어를 사용하지 않습니다. `-l "console;v=d"` 대신 `-l "console;verbosity=detailed"`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-186">Unlike MSBuild, dotnet test doesn't accept abbreviations: instead of `-l "console;v=d"` use `-l "console;verbosity=detailed"`.</span></span>

- **`--no-build`**

  <span data-ttu-id="ed8d2-187">테스트 프로젝트를 실행하기 전에 빌드하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-187">Doesn't build the test project before running it.</span></span> <span data-ttu-id="ed8d2-188">또한 `--no-restore` 플래그를 암시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-188">It also implicitly sets the - `--no-restore` flag.</span></span>

- **`--nologo`**

  <span data-ttu-id="ed8d2-189">Microsoft TestPlatform 배너를 표시하지 않고 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-189">Run tests without displaying the Microsoft TestPlatform banner.</span></span> <span data-ttu-id="ed8d2-190">.NET Core 3.0 SDK 이후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-190">Available since .NET Core 3.0 SDK.</span></span>

- **`--no-restore`**

  <span data-ttu-id="ed8d2-191">명령을 실행할 때 암시적 복원을 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-191">Doesn't execute an implicit restore when running the command.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="ed8d2-192">실행할 이진 파일을 찾을 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-192">Directory in which to find the binaries to run.</span></span> <span data-ttu-id="ed8d2-193">지정하지 않으면 기본 경로는 `./bin/<configuration>/<framework>/`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-193">If not specified, the default path is `./bin/<configuration>/<framework>/`.</span></span>  <span data-ttu-id="ed8d2-194">`TargetFrameworks` 속성을 통해 여러 개의 대상 프레임워크가 지정된 프로젝트의 경우 이 옵션을 지정할 때 `--framework`도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-194">For projects with multiple target frameworks (via the `TargetFrameworks` property), you also need to define `--framework` when you specify this option.</span></span> <span data-ttu-id="ed8d2-195">`dotnet test`는 항상 출력 디렉터리에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-195">`dotnet test` always runs tests from the output directory.</span></span> <span data-ttu-id="ed8d2-196"><xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>를 사용하여 출력 디렉터리에서 테스트 자산을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-196">You can use <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType> to consume test assets in the output directory.</span></span>

- **`-r|--results-directory <RESULTS_DIR>`**

  <span data-ttu-id="ed8d2-197">테스트 결과가 배치될 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-197">The directory where the test results are going to be placed.</span></span> <span data-ttu-id="ed8d2-198">지정한 디렉터리가 없으면 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-198">If the specified directory doesn't exist, it's created.</span></span> <span data-ttu-id="ed8d2-199">기본값은 프로젝트 파일이 포함된 디렉터리의 `TestResults`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-199">The default is `TestResults` in the directory that contains the project file.</span></span>

- **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="ed8d2-200">테스트할 대상 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-200">The target runtime to test for.</span></span>

- **`-s|--settings <SETTINGS_FILE>`**

  <span data-ttu-id="ed8d2-201">테스트 실행에 사용할 `.runsettings` 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-201">The `.runsettings` file to use for running the tests.</span></span> <span data-ttu-id="ed8d2-202">`TargetPlatform` 요소(x86|x64)는 `dotnet test`에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-202">The `TargetPlatform` element (x86|x64) has no effect for `dotnet test`.</span></span> <span data-ttu-id="ed8d2-203">X86을 대상으로 하는 테스트를 실행하려면 x86 버전의 .NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-203">To run tests that target x86, install the x86 version of .NET Core.</span></span> <span data-ttu-id="ed8d2-204">경로에 있는 *dotnet.exe*의 비트 수는 테스트를 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-204">The bitness of the *dotnet.exe* that is on the path is what will be used for running tests.</span></span> <span data-ttu-id="ed8d2-205">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-205">For more information, see the following resources:</span></span>

  - [<span data-ttu-id="ed8d2-206">`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-206">Configure unit tests by using a `.runsettings` file.</span></span>](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [<span data-ttu-id="ed8d2-207">테스트 실행 구성</span><span class="sxs-lookup"><span data-stu-id="ed8d2-207">Configure a test run</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  <span data-ttu-id="ed8d2-208">테스트 실행 대신 검색한 테스트를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-208">List the discovered tests instead of running the tests.</span></span>

- **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="ed8d2-209">명령의 세부 정보 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-209">Sets the verbosity level of the command.</span></span> <span data-ttu-id="ed8d2-210">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-210">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="ed8d2-211">기본값은 `minimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-211">The default is `minimal`.</span></span> <span data-ttu-id="ed8d2-212">자세한 내용은 <xref:Microsoft.Build.Framework.LoggerVerbosity>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-212">For more information, see <xref:Microsoft.Build.Framework.LoggerVerbosity>.</span></span>

- <span data-ttu-id="ed8d2-213">**`RunSettings`** 인수</span><span class="sxs-lookup"><span data-stu-id="ed8d2-213">**`RunSettings`** arguments</span></span>

 <span data-ttu-id="ed8d2-214">인라인 `RunSettings`는 명령줄에서 “-- ” 뒤에 마지막 인수로 전달됩니다(-- 다음에 공백 있음).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-214">Inline `RunSettings` are passed as the last arguments on the command line after "-- " (note the space after --).</span></span> <span data-ttu-id="ed8d2-215">인라인 `RunSettings`는 `[name]=[value]` 쌍으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-215">Inline `RunSettings` are specified as `[name]=[value]` pairs.</span></span> <span data-ttu-id="ed8d2-216">공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-216">A space is used to separate multiple `[name]=[value]` pairs.</span></span>

  <span data-ttu-id="ed8d2-217">예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span><span class="sxs-lookup"><span data-stu-id="ed8d2-217">Example: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`</span></span>

  <span data-ttu-id="ed8d2-218">자세한 내용은 [명령줄을 통해 RunSettings 인수 전달](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-218">For more information, see [Passing RunSettings arguments through command line](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).</span></span>

## <a name="examples"></a><span data-ttu-id="ed8d2-219">예</span><span class="sxs-lookup"><span data-stu-id="ed8d2-219">Examples</span></span>

- <span data-ttu-id="ed8d2-220">현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-220">Run the tests in the project in the current directory:</span></span>

  ```dotnetcli
  dotnet test
  ```

- <span data-ttu-id="ed8d2-221">`test1` 프로젝트에서 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-221">Run the tests in the `test1` project:</span></span>

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- <span data-ttu-id="ed8d2-222">현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-222">Run the tests in the project in the current directory, and generate a test results file in the trx format:</span></span>

  ```dotnetcli
  dotnet test --logger trx
  ```

- <span data-ttu-id="ed8d2-223">현재 디렉터리의 프로젝트에서 테스트를 실행하고 코드 검사 파일을 생성합니다([Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) 수집기 통합 설치 후).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-223">Run the tests in the project in the current directory, and generate a code coverage file (after installing [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) collectors integration):</span></span>

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- <span data-ttu-id="ed8d2-224">현재 디렉터리의 프로젝트에서 테스트를 실행하고 코드 검사 파일을 생성합니다(Windows만 해당).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-224">Run the tests in the project in the current directory, and generate a code coverage file (Windows only):</span></span>

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- <span data-ttu-id="ed8d2-225">현재 디렉터리의 프로젝트에서 테스트를 실행하고 콘솔에 세부 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-225">Run the tests in the project in the current directory, and log with detailed verbosity to the console:</span></span>

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- <span data-ttu-id="ed8d2-226">현재 디렉터리의 프로젝트에서 테스트를 실행하고 테스트 호스트에서 크래시 발생 시 진행 중이던 테스트를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-226">Run the tests in the project in the current directory, and report tests that were in progress when the test host crashed:</span></span>

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a><span data-ttu-id="ed8d2-227">필터 옵션 세부 정보</span><span class="sxs-lookup"><span data-stu-id="ed8d2-227">Filter option details</span></span>

`--filter <EXPRESSION>`

<span data-ttu-id="ed8d2-228">`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-228">`<Expression>` has the format `<property><operator><value>[|&<Expression>]`.</span></span>

<span data-ttu-id="ed8d2-229">`<property>`은(는) `Test Case`의 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-229">`<property>` is an attribute of the `Test Case`.</span></span> <span data-ttu-id="ed8d2-230">다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-230">The following are the properties supported by popular unit test frameworks:</span></span>

| <span data-ttu-id="ed8d2-231">테스트 프레임워크</span><span class="sxs-lookup"><span data-stu-id="ed8d2-231">Test Framework</span></span> | <span data-ttu-id="ed8d2-232">지원되는 속성</span><span class="sxs-lookup"><span data-stu-id="ed8d2-232">Supported properties</span></span>                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ed8d2-233">MSTest</span><span class="sxs-lookup"><span data-stu-id="ed8d2-233">MSTest</span></span>         | <ul><li><span data-ttu-id="ed8d2-234">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ed8d2-234">FullyQualifiedName</span></span></li><li><span data-ttu-id="ed8d2-235">이름</span><span class="sxs-lookup"><span data-stu-id="ed8d2-235">Name</span></span></li><li><span data-ttu-id="ed8d2-236">ClassName</span><span class="sxs-lookup"><span data-stu-id="ed8d2-236">ClassName</span></span></li><li><span data-ttu-id="ed8d2-237">우선 순위</span><span class="sxs-lookup"><span data-stu-id="ed8d2-237">Priority</span></span></li><li><span data-ttu-id="ed8d2-238">TestCategory</span><span class="sxs-lookup"><span data-stu-id="ed8d2-238">TestCategory</span></span></li></ul> |
| <span data-ttu-id="ed8d2-239">xUnit</span><span class="sxs-lookup"><span data-stu-id="ed8d2-239">xUnit</span></span>          | <ul><li><span data-ttu-id="ed8d2-240">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ed8d2-240">FullyQualifiedName</span></span></li><li><span data-ttu-id="ed8d2-241">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ed8d2-241">DisplayName</span></span></li><li><span data-ttu-id="ed8d2-242">특성</span><span class="sxs-lookup"><span data-stu-id="ed8d2-242">Traits</span></span></li></ul>                                   |
| <span data-ttu-id="ed8d2-243">NUnit</span><span class="sxs-lookup"><span data-stu-id="ed8d2-243">NUnit</span></span>          | <ul><li><span data-ttu-id="ed8d2-244">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="ed8d2-244">FullyQualifiedName</span></span></li><li><span data-ttu-id="ed8d2-245">이름</span><span class="sxs-lookup"><span data-stu-id="ed8d2-245">Name</span></span></li><li><span data-ttu-id="ed8d2-246">TestCategory</span><span class="sxs-lookup"><span data-stu-id="ed8d2-246">TestCategory</span></span></li><li><span data-ttu-id="ed8d2-247">우선 순위</span><span class="sxs-lookup"><span data-stu-id="ed8d2-247">Priority</span></span></li></ul>                                   |

<span data-ttu-id="ed8d2-248">`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-248">The `<operator>` describes the relationship between the property and the value:</span></span>

| <span data-ttu-id="ed8d2-249">연산자</span><span class="sxs-lookup"><span data-stu-id="ed8d2-249">Operator</span></span> | <span data-ttu-id="ed8d2-250">기능</span><span class="sxs-lookup"><span data-stu-id="ed8d2-250">Function</span></span>        |
| :------: | --------------- |
| `=`      | <span data-ttu-id="ed8d2-251">정확하게 일치</span><span class="sxs-lookup"><span data-stu-id="ed8d2-251">Exact match</span></span>     |
| `!=`     | <span data-ttu-id="ed8d2-252">정확하게 일치하지 않음</span><span class="sxs-lookup"><span data-stu-id="ed8d2-252">Not exact match</span></span> |
| `~`      | <span data-ttu-id="ed8d2-253">포함</span><span class="sxs-lookup"><span data-stu-id="ed8d2-253">Contains</span></span>        |
| `!~`     | <span data-ttu-id="ed8d2-254">포함하지 않음</span><span class="sxs-lookup"><span data-stu-id="ed8d2-254">Not contains</span></span>    |

<span data-ttu-id="ed8d2-255">`<value>`는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-255">`<value>` is a string.</span></span> <span data-ttu-id="ed8d2-256">모든 조회는 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-256">All the lookups are case insensitive.</span></span>

<span data-ttu-id="ed8d2-257">`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-257">An expression without an `<operator>` is automatically considered as a `contains` on `FullyQualifiedName` property (for example, `dotnet test --filter xyz` is same as `dotnet test --filter FullyQualifiedName~xyz`).</span></span>

<span data-ttu-id="ed8d2-258">식은 조건부 연산자와 조인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-258">Expressions can be joined with conditional operators:</span></span>

| <span data-ttu-id="ed8d2-259">연산자</span><span class="sxs-lookup"><span data-stu-id="ed8d2-259">Operator</span></span>            | <span data-ttu-id="ed8d2-260">기능</span><span class="sxs-lookup"><span data-stu-id="ed8d2-260">Function</span></span> |
| ------------------- | -------- |
| <code>&#124;</code> | <span data-ttu-id="ed8d2-261">또는</span><span class="sxs-lookup"><span data-stu-id="ed8d2-261">OR</span></span>       |
| `&`                 | <span data-ttu-id="ed8d2-262">AND</span><span class="sxs-lookup"><span data-stu-id="ed8d2-262">AND</span></span>      |

<span data-ttu-id="ed8d2-263">조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).</span><span class="sxs-lookup"><span data-stu-id="ed8d2-263">You can enclose expressions in parenthesis when using conditional operators (for example, `(Name~TestMethod1) | (Name~TestMethod2)`).</span></span>

<span data-ttu-id="ed8d2-264">선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ed8d2-264">For more information and examples on how to use selective unit test filtering, see [Running selective unit tests](../testing/selective-unit-tests.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ed8d2-265">참조</span><span class="sxs-lookup"><span data-stu-id="ed8d2-265">See also</span></span>

- [<span data-ttu-id="ed8d2-266">프레임워크 및 대상</span><span class="sxs-lookup"><span data-stu-id="ed8d2-266">Frameworks and Targets</span></span>](../../standard/frameworks.md)
- [<span data-ttu-id="ed8d2-267">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="ed8d2-267">.NET Core Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
- [<span data-ttu-id="ed8d2-268">명령줄을 통해 runsettings 인수 전달</span><span class="sxs-lookup"><span data-stu-id="ed8d2-268">Passing runsettings arguments through commandline</span></span>](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
