---
title: dotnet tool update 명령
description: dotnet tool update 명령은 컴퓨터에서 지정된 .NET Core 도구를 업데이트합니다.
ms.date: 07/08/2020
ms.openlocfilehash: 7c4bde44ac9964828074baeb1a697ba64ed17887
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226623"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet tool update` - 컴퓨터에서 지정된 [.NET Core 도구](global-tools.md)를 업데이트합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--configfile <FILE>] [--framework <FRAMEWORK>]
    [--add-source <SOURCE>] [--disable-parallel]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a>설명

`dotnet tool update` 명령은 컴퓨터의 .NET Core 도구를 패키지의 안정적인 최신 버전으로 업데이트하는 방법을 제공합니다. 이 명령은 도구를 제거하고 다시 설치하여 효과적으로 업데이트합니다. 이 명령을 사용하려면 다음 옵션 중 하나를 지정합니다.

* 기본 위치에 설치된 전역 도구를 업데이트하려면 `--global` 옵션을 사용합니다.
* 사용자 지정 위치에 설치된 전역 도구를 업데이트하려면 `--tool-path` 옵션을 사용합니다.
* 로컬 도구를 업데이트하려면 `--local` 옵션을 사용합니다.

**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**

## <a name="arguments"></a>인수

- **`PACKAGE_ID`**

  업데이트할 .NET Core 전역 도구를 포함하는 NuGet 패키지의 이름/ID입니다. [dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.

## <a name="options"></a>옵션

- **`--add-source <SOURCE>`**

  설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.

- **`--configfile <FILE>`**

  사용할 NuGet 구성(*nuget.config*) 파일입니다.

- **`--disable-parallel`**

  여러 프로젝트를 병렬로 복원하지 않습니다.

- **`--framework <FRAMEWORK>`**

  도구를 업데이트할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.

- **`--ignore-failed-sources`**

  패키지 소스 오류를 경고로 처리합니다.

- **`--interactive`**

  명령이 중지되고 사용자 입력 또는 작업을 대기할 수 있도록 허용합니다(예: 인증 완료).

- **`--local`**

  도구 및 로컬 도구 매니페스트를 업데이트합니다. `--global` 옵션과 함께 사용할 수 없습니다.

- **`--no-cache`**

  패키지 및 HTTP 요청을 캐시하지 않습니다.

- **`--tool-manifest <PATH>`**

  매니페스트 파일 경로입니다.

- **`--tool-path <PATH>`**

  전역 도구가 설치되는 위치를 지정합니다. PATH는 절대적이거나 상대적일 수 있습니다. `--global` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.

- **`--version <VERSION>`**

  업데이트할 도구 패키지의 버전 범위입니다. 버전을 다운그레이드하는 데 사용할 수 없으며, 먼저 최신 버전을 `uninstall`(제거)해야 합니다.

- **`-g|--global`**

  업데이트가 사용자 수준 도구에 대한 것임을 지정합니다. `--tool-path` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`-v|--verbosity <LEVEL>`**

  명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예

- **`dotnet tool update -g dotnetsay`**

  [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  특정 Windows 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  특정 Linux/macOS 디렉터리에 있는 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 업데이트합니다.

- **`dotnet tool update dotnetsay`**

  현재 디렉터리에 대해 설치된 [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 로컬 도구를 업데이트합니다.

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 최신 패치 버전(주 버전 `2` 및 부 버전 `0`)으로 업데이트합니다.

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  [dotnetsay](https://www.nuget.org/packages/dotnetsay/) 전역 도구를 지정된 범위 `(> 2.0.0 && < 2.1.4)` 내의 최하위 버전으로 업데이트합니다. `2.1.0` 버전이 설치됩니다. 유의적 버전 범위에 관한 자세한 내용은 [NuGet 패키징 버전 범위](/nuget/concepts/package-versioning#version-ranges)를 참조하세요.

## <a name="see-also"></a>참조

- [.NET Core 도구](global-tools.md)
- [유의적 버전](https://semver.org)
- [자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용](global-tools-how-to-use.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
