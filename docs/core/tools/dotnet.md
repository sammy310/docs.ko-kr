---
title: dotnet 명령
description: dotnet 명령(.NET Core CLI의 일반 드라이버) 및 사용법에 대해 알아봅니다.
ms.date: 02/13/2020
ms.openlocfilehash: 88e92b3ff5e8f68b980015a817434dd2d67df93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378837"
---
# <a name="dotnet-command"></a>dotnet 명령

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet` - .NET Core CLI에 대한 일반 드라이버입니다.

## <a name="synopsis"></a>개요

사용 가능한 명령 및 환경에 대한 정보를 얻으려면 다음을 수행합니다.

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

명령을 실행하려면(SDK를 설치해야 함) 다음을 수행합니다.

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

애플리케이션을 실행하려면 다음을 수행합니다.

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward`는 .NET Core 3.x 이후로 사용할 수 있습니다. .NET Core 2.x의 경우 `--roll-forward-on-no-candidate-fx`를 사용합니다.

## <a name="description"></a>설명

`dotnet` 명령에는 두 가지 기능이 있습니다.

- .NET Core 프로젝트 작업을 위한 명령을 제공합니다.

  예를 들어 [`dotnet build`](dotnet-build.md)는 프로젝트를 빌드합니다. 각 명령은 자체 옵션과 인수를 정의합니다. 모든 명령은 명령을 사용하는 방법에 대해 간략한 설명서를 출력하는 `--help` 옵션을 지원합니다.

- .NET Core 애플리케이션을 실행합니다.

  애플리케이션을 실행할 애플리케이션 `.dll` 파일의 경로를 지정합니다.  애플리케이션을 실행하는 것은 진입점을 찾아서 실행하는 것이며 콘솔 앱의 경우에는 `Main` 메서드입니다. 예를 들어 `dotnet myapp.dll`은 `myapp` 애플리케이션을 실행합니다. 배포 옵션에 대해 자세히 알아보려면 [.NET Core 애플리케이션 배포](../deploying/index.md)를 참조하세요.

## <a name="options"></a>옵션

명령 실행, 애플리케이션 실행을 위해 `dotnet` 자체에 사용할 수 있는 다양한 옵션이 있습니다.

### <a name="options-for-dotnet-by-itself"></a>dotnet 자체에 대한 옵션

`dotnet` 자체에 대한 옵션은 다음과 같습니다. 예: `dotnet --info`. 환경에 대한 정보를 출력합니다.

- **`--info`**

  .NET Core 설치 및 머신 환경(예: 현재 운영 체제)에 대한 자세한 정보를 인쇄하고 .NET Core 버전의 SHA를 커밋합니다.

- **`--version`**

  사용 중인 .NET Core SDK 버전을 출력합니다.

- **`--list-runtimes`**

  설치된 .NET Core 런타임의 목록을 출력합니다. x86 버전 SDK는 x86 런타임만 나열하며 x64 버전 SDK는 x64 런타임만 나열합니다.

- **`--list-sdks`**

  설치된 .NET Core SDK의 목록을 출력합니다.

- **`-h|--help`**

  사용 가능한 명령 목록을 출력합니다.

### <a name="sdk-options-for-running-a-command"></a>명령을 실행하기 위한 SDK 옵션

명령과 함께 사용하는 `dotnet`의 옵션은 다음과 같습니다. 예: `dotnet build --help`.

- **`-d|--diagnostics`**

  진단 출력을 사용합니다.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다. 모든 명령에서 지원되지는 않습니다. 이 옵션을 사용할 수 있는지 확인하려면 특정 명령 페이지를 참조하세요.

- **`-h|--help`**

  `dotnet build --help`와 같은 지정된 명령에 대한 설명서를 인쇄합니다.

- **`command options`**

  각 명령은 해당 명령과 관련된 옵션을 정의합니다. 사용 가능한 옵션 목록은 특정 명령 페이지를 참조하세요.

### <a name="runtime-options"></a>런타임 옵션

`dotnet`이 애플리케이션을 실행할 때 사용할 수 있는 옵션은 다음과 같습니다. 예: `dotnet myapp.dll --roll-forward Major`.

- **`--additionalprobingpath <PATH>`**

  검색 정책 및 검색할 어셈블리를 포함하는 경로입니다.

- **`--additional-deps <PATH>`**

  추가적인 *.deps.json* 파일의 경로입니다. *deps.json* 파일에는 어셈블리 충돌을 해결하는 데 사용되는 종속성, 컴파일 종속성 및 버전 정보 목록이 포함됩니다. 자세한 내용은 GitHub에서 [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)을 참조하세요.

- **`--depsfile <PATH_TO_DEPSFILE>`**

  *deps.json* 파일의 경로입니다. *deps.json* 파일은 애플리케이션을 실행하는 데 필요한 종속성에 대한 정보를 포함하는 구성 파일입니다. 이 파일은 .NET Core SDK에 의해 생성됩니다.

- **`--runtimeconfig`**

  *runtimeconfig.json* 파일의 경로입니다. *runtimeconfig.json* 파일은 런타임 설정을 포함하는 구성 파일입니다. 자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.

- **`--roll-forward <SETTING>`** **.NET Core SDK 3.0부터 사용할 수 있습니다.**

  앱에 롤포워드가 적용되는 방법을 제어합니다. `SETTING`은 다음 값 중 하나일 수 있습니다. 지정하지 않으면 `Minor`이 기본값입니다.

  - `LatestPatch` - 가장 높은 패치 버전으로 롤포워드합니다. 부 버전 롤포워드를 사용하지 않도록 설정합니다.
  - `Minor` - 요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다. 요청된 부 버전이 있다면 LatestPatch 정책이 사용됩니다.
  - `Major` - 요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다. 요청된 주 버전이 있다면 Minor 정책이 사용됩니다.
  - `LatestMinor` - 요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다. 구성 요소 호스팅 시나리오를 위한 것입니다.
  - `LatestMajor` - 요청된 주 버전이 있는 경우에도 가장 높은 주 버전, 가장 높은 부 버전으로 롤포워드합니다. 구성 요소 호스팅 시나리오를 위한 것입니다.
  - `Disable` - 롤포워드하지 않습니다. 지정된 버전에만 바인딩합니다. 이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다. 이 값은 테스트용으로만 사용하는 것이 좋습니다.

  `Disable`을 제외하고, 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.

  롤포워드 동작은 프로젝트 파일 속성, 런타임 구성 파일 속성 및 환경 변수에서도 구성할 수 있습니다. 자세한 내용은 [주 버전 런타임 롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)를 참조하세요.

- **`--roll-forward-on-no-candidate-fx <N>`** **.NET Core 2.x SDK에서 사용할 수 있습니다.**

  필요한 공유 프레임워크를 사용할 수 없을 때 동작을 정의합니다. `N`는 다음이 될 수 있습니다.

  - `0` - 부 버전 롤포워드도 사용하지 않도록 설정합니다.
  - `1` - 부 버전에서는 롤포워드하지만 주 버전에서는 롤포워드하지 않습니다. 이것은 기본적인 동작입니다.
  - `2` - 부 버전과 주 버전에서 롤포워드합니다.

  자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.

  .NET Core 3.0부터 이 옵션은 `--roll-forward`로 대체되었으므로 이 옵션을 대신 사용해야 합니다.

- **`--fx-version <VERSION>`**

  애플리케이션 실행에 사용할 .NET Core 런타임의 버전입니다.

  이 옵션은 애플리케이션의 `.runtimeconfig.json` 파일에 있는 첫 번째 프레임워크 참조의 버전을 재정의합니다. 그러므로 프레임워크 참조가 하나만 있는 경우에만 예상대로 작동합니다. 애플리케이션에 둘 이상의 프레임워크 참조가 있는 경우 이 옵션을 사용하면 오류가 발생할 수 있습니다.

## <a name="dotnet-commands"></a>dotnet 명령

### <a name="general"></a>일반

| 명령                                       | 기능                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | .NET Core 애플리케이션을 빌드합니다.                                     |
| [dotnet build-server](dotnet-build-server.md) | 빌드에서 시작된 서버와 상호 작용합니다.                          |
| [dotnet clean](dotnet-clean.md)               | 빌드 출력을 정리합니다.                                                |
| [dotnet help](dotnet-help.md)                 | 명령에 대한 자세한 온라인 설명서를 표시합니다.           |
| [dotnet migrate](dotnet-migrate.md)           | 유효한 Preview 2 프로젝트를 .NET Core SDK 1.0 프로젝트로 마이그레이션합니다.  |
| [dotnet msbuild](dotnet-msbuild.md)           | MSBuild 명령줄에 대한 액세스 권한을 제공합니다.                        |
| [dotnet new](dotnet-new.md)                   | 지정한 템플릿에 대해 C# 또는 F# 프로젝트를 초기화합니다.                |
| [dotnet pack](dotnet-pack.md)                 | 코드의 NuGet 패키지를 만듭니다.                               |
| [dotnet publish](dotnet-publish.md)           | .NET Framework 종속형 또는 자체 포함 애플리케이션을 게시합니다. |
| [dotnet restore](dotnet-restore.md)           | 지정된 애플리케이션에 대한 종속성을 복원합니다.                  |
| [dotnet run](dotnet-run.md)                   | 소스에서 애플리케이션을 실행합니다.                                   |
| [dotnet sln](dotnet-sln.md)                   | 솔루션 파일에 프로젝트를 추가, 제거 및 나열하는 옵션입니다.       |
| [dotnet store](dotnet-store.md)               | 어셈블리를 런타임 패키지 저장소에 저장합니다.                     |
| [dotnet test](dotnet-test.md)                 | Test Runner를 사용하여 테스트를 실행합니다.                                     |

### <a name="project-references"></a>프로젝트 참조

명령 | 기능
--- | ---
[dotnet add reference](dotnet-add-reference.md) | 프로젝트 참조를 추가합니다.
[dotnet list reference](dotnet-list-reference.md) | 프로젝트 참조를 나열합니다.
[dotnet remove reference](dotnet-remove-reference.md) | 프로젝트 참조를 제거합니다.

### <a name="nuget-packages"></a>NuGet 패키지

명령 | 기능
--- | ---
[dotnet add package](dotnet-add-package.md) | NuGet 패키지를 추가합니다.
[dotnet remove package](dotnet-remove-package.md) | NuGet 패키지를 제거합니다.

### <a name="nuget-commands"></a>NuGet 명령

명령 | 기능
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
[dotnet nuget push](dotnet-nuget-push.md) | 서버에 패키지를 푸시하고 게시합니다.
[dotnet nuget locals](dotnet-nuget-locals.md) | http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.
[dotnet nuget add source](dotnet-nuget-add-source.md) | NuGet 소스를 추가합니다.
[dotnet nuget disable source](dotnet-nuget-disable-source.md) | NuGet 소스를 사용하지 않도록 설정합니다.
[dotnet nuget enable source](dotnet-nuget-enable-source.md) | NuGet 소스를 사용하도록 설정합니다.
[dotnet nuget list source](dotnet-nuget-list-source.md) | 구성된 NuGet 소스를 모두 나열합니다.
[dotnet nuget remove source](dotnet-nuget-remove-source.md) | NuGet 소스를 제거합니다.
[dotnet nuget update source](dotnet-nuget-update-source.md) | NuGet 소스를 업데이트합니다.

### <a name="global-tool-path-and-local-tools-commands"></a>전역, 도구 경로 및 로컬 도구 명령

도구는 NuGet 패키지에서 설치되고 명령 프롬프트에서 호출되는 콘솔 애플리케이션입니다. 도구를 직접 작성하거나 타사에서 작성한 도구를 설치할 수 있습니다. 도구를 전역 도구, 도구 경로 도구 및 로컬 도구라고도 합니다. 자세한 내용은 [.NET Core 도구 개요](global-tools.md)를 참조하세요. 전역 및 도구 경로 도구는 .NET Core SDK 2.1부터 사용할 수 있습니다. 로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.

명령 | 기능
--- | ---
[dotnet tool install](dotnet-tool-install.md) | 컴퓨터에 도구를 설치합니다.
[dotnet tool list](dotnet-tool-list.md) | 컴퓨터에 현재 설치되어 있는 모든 전역, 도구 경로 또는 로컬 도구를 나열합니다.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | 컴퓨터에서 도구를 제거합니다.
[dotnet tool update](dotnet-tool-update.md) | 컴퓨터에 설치된 도구를 업데이트합니다.

### <a name="additional-tools"></a>추가 도구

.NET Core SDK 2.1.300부터는 `DotnetCliToolReference`을 사용하여 프로젝트별로만 사용할 수 있었던 여러 도구를 .NET Core SDK의 일부로 사용할 수 있습니다. 이러한 도구는 다음 표에 나열되어 있습니다.

| 도구                                              | 기능                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | 개발 인증서를 만들고 관리합니다.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Entity Framework Core 명령줄 도구입니다.                    |
| sql-cache                                         | SQL Server 캐시 명령줄 도구입니다.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | 개발 사용자 비밀을 관리합니다.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | 파일이 변경될 때 명령을 실행하는 파일 감시자를 시작합니다. |

각 도구에 대한 자세한 내용을 보려면 `dotnet <tool-name> --help`를 입력합니다.

## <a name="examples"></a>예

새 .NET Core 콘솔 애플리케이션을 만듭니다.

```dotnetcli
dotnet new console
```

지정된 디렉터리에서 프로젝트 및 해당 종속성을 빌드합니다.

```dotnetcli
dotnet build
```

애플리케이션을 실행합니다.

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a>환경 변수

- `DOTNET_ROOT`, `DOTNET_ROOT(x86)`

  기본 위치에 설치되어 있지 않은 경우 .NET Core 런타임의 위치를 지정합니다. Windows에서 기본 위치는 `C:\Program Files\dotnet`입니다. Linux 및 macOS에서 기본 위치는 `/usr/share/dotnet`입니다. 이 환경 변수는 생성된 실행 파일(apphost)을 통해 앱을 실행할 때만 사용됩니다. 64비트 OS에서 32비트 실행 파일을 실행할 때는 대신 `DOTNET_ROOT(x86)`가 사용됩니다.

- `DOTNET_PACKAGES`

  글로벌 패키지 폴더입니다. 설정하지 않으면 기본적으로 Unix에서는 `~/.nuget/packages`, Windows에서는 `%userprofile%\.nuget\packages`로 지정됩니다.

- `DOTNET_SERVICING`

  런타임을 로드할 때 공유 호스트에서 사용할 서비스 인덱스의 위치를 지정합니다.

- `DOTNET_NOLOGO`

  처음 실행할 때 .NET Core 시작 및 원격 분석 메시지를 표시할지 여부를 지정합니다. 이러한 메시지를 음소거하려면 `true`로 설정하고(`true`, `1` 또는 `yes` 값 사용) 허용하려면 `false`로 설정합니다(`false`, `0` 또는 `no` 값 사용). 설정되지 않은 경우 기본값은 `false`이고 처음 실행될 때 메시지가 표시됩니다. 이 플래그는 원격 분석에는 영향을 주지 않습니다(원격 분석 보내기를 옵트아웃하는 경우 `DOTNET_CLI_TELEMETRY_OPTOUT` 참조).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  .NET Core 도구 사용에 대한 데이터를 수집하여 Microsoft에 전송할지 여부를 지정합니다. 원격 분석 기능을 옵트아웃하려면 `true`로 설정합니다(값 `true`, `1` 또는 `yes`가 허용됨). 이외의 경우 원격 분석 기능을 옵트인하려면 `false`로 설정합니다(`false`, `0` 또는 `no`가 허용됨). 설정하지 않으면 기본적으로 `false`이고 원격 분석 기능은 활성화됩니다.

- `DOTNET_MULTILEVEL_LOOKUP`

  전역 위치에서 .NET Core 런타임, 공유 프레임워크 또는 SDK가 확인되는지 여부를 지정합니다. 설정하지 않은 경우 기본값은 1(논리적 `true`)입니다. 전역 위치에서 확인하지 않고 격리된 .NET Core 설치를 사용하려면 0(논리적 `false`)으로 설정합니다. 다중 수준의 조회에 대한 자세한 내용은 [다중 수준 SharedFX 조회](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md)를 참조하세요.

- `DOTNET_ROLL_FORWARD` **.NET Core 3.x부터 사용할 수 있습니다.**

  롤포워드 동작을 결정합니다. 자세한 내용은 이 문서 앞부분에서 `--roll-forward` 옵션을 참조하세요.

- `DOTNET_ROLL_FORWARD_TO_PRERELEASE` **.NET Core 3.x부터 사용할 수 있습니다.**

  `1`(사용)로 설정된 경우 릴리스 버전에서 시험판 버전으로 롤포워드를 사용하도록 설정합니다. 기본적으로(`0` - 사용 안 함), .NET Core 런타임의 릴리스 버전이 요청되면 롤포워드는 설치된 릴리스 버전만 고려합니다.

  자세한 내용은 [롤포워드](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward)를 참조하세요.

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **.NET Core 2.x에서 사용할 수 있습니다.**

  `0`으로 설정된 경우 부 버전 롤포워드를 사용하지 않도록 설정합니다. 자세한 내용은 [롤포워드](../whats-new/dotnet-core-2-1.md#roll-forward)를 참조하세요.

  이 설정은 .NET Core 3.0에서 `DOTNET_ROLL_FORWARD`로 대체되었습니다. 새 설정을 대신 사용해야 합니다.

- `DOTNET_CLI_UI_LANGUAGE`

  `en-us`와 같은 로캘 값을 사용하여 CLI UI의 언어를 설정합니다. 지원되는 값은 Visual Studio의 경우와 동일합니다. 자세한 내용은 [Visual Studio 설치 설명서](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019)에서 설치 프로그램 언어 변경에 대한 섹션을 참조하세요. .NET 리소스 관리자 규칙이 적용되므로, 정확한 일치를 선택할 필요가 없습니다. `CultureInfo` 트리에서 하위 항목을 선택할 수도 있습니다. 예를 들어 `fr-CA`로 설정하면 CLI에서 `fr` 번역을 찾아 사용합니다. 지원되지 않는 언어로 설정하면 CLI는 영어로 대체됩니다.

- `DOTNET_DISABLE_GUI_ERRORS`

  GUI 지원 생성된 실행 파일의 경우 일반적으로 특정 오류 클래스에 대해 표시하는 대화 상자 팝업을 사용하지 않도록 설정합니다. `stderr`에만 쓰고 이러한 경우에는 종료됩니다.
  
- `DOTNET_ADDITIONAL_DEPS`

  CLI 옵션 `--additional-deps`와 같습니다.

- `DOTNET_RUNTIME_ID`

  검색된 RID를 재정의합니다.

- `DOTNET_SHARED_STORE`

  일부 경우에는 어셈블리 확인이 대체되는 "공유 저장소"의 위치입니다.

- `DOTNET_STARTUP_HOOKS`

  시작 후크를 로드하고 실행하는 어셈블리의 목록입니다.

- `DOTNET_BUNDLE_EXTRACT_BASE_DIR` **.NET Core 3.x부터 사용할 수 있습니다.**

  단일 파일 애플리케이션이 실행되기 전에 추출되는 디렉터리를 지정합니다.

  자세한 내용은 [단일 파일 실행 파일](../whats-new/dotnet-core-3-0.md#single-file-executables)을 참조하세요.

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  호스팅 구성 요소(예: `dotnet.exe`, `hostfxr`, `hostpolicy`)에서 진단 추적을 제어합니다.

  * `COREHOST_TRACE=[0/1]` -기본값은 `0`(추적 사용 안 함)입니다. `1`로 설정된 경우 진단 추적이 사용됩니다.
  * `COREHOST_TRACEFILE=<file path>` - `COREHOST_TRACE=1`을 통해 추적을 사용하도록 설정한 경우에만 유효합니다. 설정되면 추적 정보가 지정된 파일에 기록되고, 그렇지 않으면 추적 정보가 `stderr`에 기록됩니다. **.NET Core 3.x부터 사용할 수 있습니다.**
  * `COREHOST_TRACE_VERBOSITY=[1/2/3/4]` - 기본값은 `4`입니다. 이 설정은 `COREHOST_TRACE=1`을 통해 추적을 사용하도록 설정한 경우에만 사용됩니다. **.NET Core 3.x부터 사용할 수 있습니다.**
    * `4` - 모든 추적 정보가 기록됩니다.
    * `3` - 정보, 경고 및 오류 메시지만 기록됩니다.
    * `2` - 경고 및 오류 메시지만 기록됩니다.
    * `1` - 오류 메시지만 기록됩니다.

  애플리케이션 시작에 대한 자세한 추적 정보를 얻는 일반적인 방법은 `COREHOST_TRACE=1` 및 `COREHOST_TRACEFILE=host_trace.txt`를 설정하고 애플리케이션을 실행하는 것입니다. 현재 디렉터리에 새 파일 `host_trace.txt`가 생성되어 자세한 정보가 기록됩니다.

## <a name="see-also"></a>참조

- [런타임 구성 파일](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [.NET Core 런타임 구성 설정](../run-time-config/index.md)
