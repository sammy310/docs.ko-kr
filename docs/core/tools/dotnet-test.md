---
title: dotnet test 명령
description: dotnet test 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다.
ms.date: 04/29/2020
ms.openlocfilehash: 9b1e190579902dda71547b01f31dd5adcc22fe9c
ms.sourcegitcommit: c8c3e1c63a00b7d27f76f5e50ee6469e6bdc8987
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251194"
---
# <a name="dotnet-test"></a>dotnet test

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet test` - 단위 테스트를 실행하는 데 사용하는 .NET 테스트 드라이버입니다.

## <a name="synopsis"></a>개요

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

## <a name="description"></a>설명

`dotnet test` 명령은 지정된 솔루션에서 단위 테스트를 실행하는 데 사용됩니다. `dotnet test` 명령은 솔루션을 빌드하고 솔루션의 각 테스트 프로젝트에 대해 테스트 호스트 애플리케이션을 실행합니다. 테스트 호스트는 테스트 프레임워크를 사용하여 지정된 프로젝트에서 MSTest, NUnit 또는 xUnit 등의 테스트를 실행하고 각 테스트의 성공이나 실패를 보고합니다. 모든 테스트에 성공하면 Test Runner가 종료 코드로 0을 반환합니다. 테스트가 하나라도 실패하면 1을 반환합니다.

멀티 타기팅 프로젝트의 경우 각 대상 프레임워크에 대해 테스트가 실행됩니다. 테스트 호스트와 단위 테스트 프레임워크는 NuGet 패키지로 패키징되고 프로젝트에 대한 일반적인 종속성으로 복원됩니다.

테스트 프로젝트는 다음 샘플 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 테스트 러너를 지정합니다.

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

여기서 `Microsoft.NET.Test.Sdk`는 테스트 호스트이고 `xunit`은 테스트 프레임워크입니다. `xunit.runner.visualstudio`는 xUnit 프레임워크가 테스트 호스트와 함께 작동할 수 있도록 하는 테스트 어댑터입니다.

### <a name="implicit-restore"></a>암시적 복원

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>인수

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - 테스트 프로젝트의 경로입니다.
  - 솔루션의 경로입니다.
  - 프로젝트 또는 솔루션이 포함된 디렉터리의 경로입니다.
  - 테스트 프로젝트 *.dll* 파일의 경로입니다.

  지정하지 않으면 이 명령은 현재 디렉터리에서 프로젝트 또는 솔루션을 검색합니다.

## <a name="options"></a>옵션

- **`-a|--test-adapter-path <ADAPTER_PATH>`**

  추가 테스트 어댑터를 검색할 디렉터리의 경로입니다. 접미사가 `.TestAdapter.dll`인 *.dll* 파일만 검사됩니다. 지정하지 않으면 테스트 *.dll*의 디렉터리가 검색됩니다.

- **`--blame`**

  테스트를 원인 모드로 실행합니다. 이 옵션은 테스트 호스트의 크래시를 유발하는 문제가 있는 테스트를 격리하는 데 유용합니다. 크래시가 감지되면 크래시 전에 실행된 테스트의 순서를 캡처하는 시퀀스 파일이 `TestResults/<Guid>/<Guid>_Sequence.xml`에 만들어집니다.

- **`--blame-crash`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  테스트를 원인 모드를 실행하고 테스트 호스트가 예기치 않게 종료될 때 크래시 덤프를 수집합니다. 해당 옵션은 Windows에서만 지원됩니다. *procdump.exe* 및 *procdump64.exe*를 포함하는 디렉터리가 PATH 또는 PROCDUMP_PATH 환경 변수에 있어야 합니다. [도구 다운로드](https://docs.microsoft.com/sysinternals/downloads/procdump). `--blame`을 의미합니다.

- **`--blame-crash-dump-type <DUMP_TYPE>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  수집할 크래시 덤프의 유형입니다. `--blame-crash`를 의미합니다.

- **`--blame-crash-collect-always`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  예상된 테스트 호스트 종료와 예기치 않은 테스트 호스트 종료시 크래시 덤프를 수집합니다.

- **`--blame-hang`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  테스트를 원인 모드로 실행하고 테스트가 지정된 시간 제한을 초과하는 경우 중단 덤프를 수집합니다.

- **`--blame-hang-dump-type <DUMP_TYPE>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  수집할 크래시 덤프의 유형입니다. `full`, `mini` 또는 `none`이어야 합니다. `none`을 지정하면 테스트 호스트가 시간 초과시 종료되지만 덤프를 수집하지 않습니다. `--blame-hang`을 의미합니다.

- **`--blame-hang-timeout <TIMESPAN>`** (.NET 5.0 미리 보기 SDK 이후 사용 가능)

  중단 덤프가 트리거되고 테스트 호스트 프로세스가 종료되는 테스트별 시간 제한입니다. 시간 제한 값은 다음 형식 중 하나로 지정됩니다.
  
  - 1.5h
  - 90m
  - 5400s
  - 5400000ms

  단위를 사용하지 않으면(예: 5400000) 값은 밀리초 단위로 간주합니다. 데이터 기반 테스트와 함께 사용되는 경우 시간 제한 동작은 사용되는 테스트 어댑터에 따라 다릅니다. xUnit 및 NUnit의 경우 모든 테스트 사례 후에 시간 제한이 갱신됩니다. MSTest의 경우 모든 테스트 사례에 시간 제한이 사용됩니다. 이 옵션은 현재 netcoreapp2.1 이상이 사용되는 Windows와 netcoreapp3.1 이상이 사용되는 Linux에서 지원됩니다. macOS는 지원되지 않습니다.

- **`-c|--configuration <CONFIGURATION>`**

  빌드 구성을 정의합니다. 기본값은 `Debug`이지만 프로젝트의 구성으로 이 기본 SDK 설정이 재정의될 수 있습니다.

- **`--collect <DATA_COLLECTOR_NAME>`**

  테스트 실행에 대한 데이터 수집기를 사용하도록 설정합니다. 자세한 내용은 [테스트 실행 모니터링 및 분석](https://aka.ms/vstest-collect)을 참조하세요.
  
  .NET Core가 지원하는 플랫폼에서 코드 검사를 수집하려면 [Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/README.md)을 설치하고 `--collect:"XPlat Code Coverage"` 옵션을 사용하세요.

  Windows에서는 `--collect "Code Coverage"` 옵션을 사용하여 코드 검사를 수집할 수 있습니다. 이 옵션은 Visual Studio 2019 Enterprise에서 열 수 있는 *.coverage* 파일을 생성합니다. 자세한 내용은 [코드 검사 사용](/visualstudio/test/using-code-coverage-to-determine-how-much-code-is-being-tested) 및 [코드 검사 분석 사용자 지정](/visualstudio/test/customizing-code-coverage-analysis)을 참조하세요.

- **`-d|--diag <LOG_FILE>`**

  테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에, 그리고 옆의 파일에 진단 메시지를 기록합니다. 메시지를 기록하는 프로세스에 따라 생성되는 파일이 결정됩니다(예를 들어 테스트 호스트 로그의 경우 `*.host_<date>.txt`, 데이터 수집기 로그의 경우 `*.datacollector_<date>.txt`).

- **`-f|--framework <FRAMEWORK>`**

  테스트 이진 파일에 `dotnet` 또는 .NET Framework 테스트 호스트를 사용하도록 합니다. 이 옵션은 사용할 호스트 유형만 결정합니다. 사용할 실제 프레임워크 버전은 테스트 프로젝트의 *runtimeconfig.json*에 의해 결정됩니다. 지정하지 않으면 [TargetFramework 어셈블리 특성](/dotnet/api/system.runtime.versioning.targetframeworkattribute)이 사용되어 호스트 유형이 결정됩니다. 해당 특성이 *.dll*에서 제거되면 .NET Framework 호스트가 사용됩니다.

- **`--filter <EXPRESSION>`**

  지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다. 자세한 내용은 [필터 옵션 세부 정보](#filter-option-details) 섹션을 참조하세요. 선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다. 예를 들어 인증을 완료합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-l|--logger <LOGGER>`**

  테스트 결과에 대해 로거를 지정합니다. MSBuild와 달리 dotnet 테스트에서는 약어를 사용하지 않습니다. `-l "console;v=d"` 대신 `-l "console;verbosity=detailed"`를 사용합니다.

- **`--no-build`**

  테스트 프로젝트를 실행하기 전에 빌드하지 않습니다. 또한 `--no-restore` 플래그를 암시적으로 설정합니다.

- **`--nologo`**

  Microsoft TestPlatform 배너를 표시하지 않고 테스트를 실행합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`--no-restore`**

  명령을 실행할 때 암시적 복원을 실행하지 않습니다.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  실행할 이진 파일을 찾을 디렉터리입니다. 지정하지 않으면 기본 경로는 `./bin/<configuration>/<framework>/`입니다.  `TargetFrameworks` 속성을 통해 여러 개의 대상 프레임워크가 지정된 프로젝트의 경우 이 옵션을 지정할 때 `--framework`도 정의해야 합니다. `dotnet test`는 항상 출력 디렉터리에서 테스트를 실행합니다. <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>를 사용하여 출력 디렉터리에서 테스트 자산을 사용할 수 있습니다.

- **`-r|--results-directory <RESULTS_DIR>`**

  테스트 결과가 배치될 디렉터리입니다. 지정한 디렉터리가 없으면 생성됩니다. 기본값은 프로젝트 파일이 포함된 디렉터리의 `TestResults`입니다.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  테스트할 대상 런타임입니다.

- **`-s|--settings <SETTINGS_FILE>`**

  테스트 실행에 사용할 `.runsettings` 파일입니다. `TargetPlatform` 요소(x86|x64)는 `dotnet test`에 영향을 주지 않습니다. X86을 대상으로 하는 테스트를 실행하려면 x86 버전의 .NET Core를 설치합니다. 경로에 있는 *dotnet.exe*의 비트 수는 테스트를 실행하는 데 사용됩니다. 자세한 내용은 다음 자료를 참조하세요.

  - [`.runsettings` 파일을 사용하여 단위 테스트를 구성합니다.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [테스트 실행 구성](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  테스트 실행 대신 검색한 테스트를 나열합니다.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 기본값은 `minimal`입니다. 자세한 내용은 <xref:Microsoft.Build.Framework.LoggerVerbosity>를 참조하세요.

- **`RunSettings`** 인수

 인라인 `RunSettings`는 명령줄에서 “-- ” 뒤에 마지막 인수로 전달됩니다(-- 다음에 공백 있음). 인라인 `RunSettings`는 `[name]=[value]` 쌍으로 지정됩니다. 공백은 여러 `[name]=[value]` 쌍을 구분하는 데 사용됩니다.

  예: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  자세한 내용은 [명령줄을 통해 RunSettings 인수 전달](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)을 참조하세요.

## <a name="examples"></a>예

- 현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.

  ```dotnetcli
  dotnet test
  ```

- `test1` 프로젝트에서 테스트를 실행합니다.

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- 현재 디렉터리의 프로젝트에서 테스트를 실행하고 trx 형식으로 테스트 결과 파일을 생성합니다.

  ```dotnetcli
  dotnet test --logger trx
  ```

- 현재 디렉터리의 프로젝트에서 테스트를 실행하고 코드 검사 파일을 생성합니다([Coverlet](https://github.com/coverlet-coverage/coverlet/blob/master/Documentation/VSTestIntegration.md) 수집기 통합 설치 후).

  ```dotnetcli
  dotnet test --collect:"XPlat Code Coverage"
  ```

- 현재 디렉터리의 프로젝트에서 테스트를 실행하고 코드 검사 파일을 생성합니다(Windows만 해당).

  ```dotnetcli
  dotnet test --collect "Code Coverage"
  ```

- 현재 디렉터리의 프로젝트에서 테스트를 실행하고 콘솔에 세부 정보를 기록합니다.

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

- 현재 디렉터리의 프로젝트에서 테스트를 실행하고 테스트 호스트에서 크래시 발생 시 진행 중이던 테스트를 보고합니다.

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a>필터 옵션 세부 정보

`--filter <EXPRESSION>`

`<Expression>`에 `<property><operator><value>[|&<Expression>]` 형식이 있습니다.

`<property>`은(는) `Test Case`의 특성입니다. 다음은 인기 있는 단위 테스트 프레임 워크에서 지원되는 속성입니다.

| 테스트 프레임워크 | 지원되는 속성                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>이름</li><li>ClassName</li><li>우선 순위</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>특성</li></ul>                                   |
| NUnit          | <ul><li>FullyQualifiedName</li><li>이름</li><li>TestCategory</li><li>우선 순위</li></ul>                                   |

`<operator>`은(는) 속성과 값 사이의 관계를 설명합니다.

| 연산자 | 기능        |
| :------: | --------------- |
| `=`      | 정확하게 일치     |
| `!=`     | 정확하게 일치하지 않음 |
| `~`      | 포함        |
| `!~`     | 포함하지 않음    |

`<value>`는 문자열입니다. 모든 조회는 대/소문자를 구분합니다.

`<operator>`이(가) 없는 식은 `FullyQualifiedName` 속성의 `contains`(으)로 자동으로 간주됩니다(예를 들어 `dotnet test --filter xyz`과(와) `dotnet test --filter FullyQualifiedName~xyz`이(가) 동일).

식은 조건부 연산자와 조인할 수 있습니다.

| 연산자            | 기능 |
| ------------------- | -------- |
| <code>&#124;</code> | 또는       |
| `&`                 | AND      |

조건부 연산자를 사용 하는 경우 식을 괄호로 묶을 수 있습니다(예: `(Name~TestMethod1) | (Name~TestMethod2)`).

선택적 단위 테스트 필터링을 사용하는 방법에 대한 자세한 내용 및 예제는 [선택적 단위 테스트 실행](../testing/selective-unit-tests.md)을 참조하세요.

## <a name="see-also"></a>참조

- [프레임워크 및 대상](../../standard/frameworks.md)
- [.NET Core RID(런타임 식별자) 카탈로그](../rid-catalog.md)
- [명령줄을 통해 runsettings 인수 전달](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
