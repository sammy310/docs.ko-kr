---
title: dotnet tool update 명령
description: dotnet tool update 명령은 컴퓨터에서 지정된 .NET Core 도구를 업데이트합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 80e807a0fc06ad762334f888e701f6d9c448369a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156948"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet tool update` - 컴퓨터에서 지정된 [.NET Core 도구](global-tools.md)를 업데이트합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <PACKAGE_NAME> [--configfile] [--framework] [-v|--verbosity] [--add-source]
dotnet tool update <-h|--help>
```

## <a name="description"></a>설명

`dotnet tool update` 명령은 컴퓨터의 .NET Core 도구를 패키지의 안정적인 최신 버전으로 업데이트하는 방법을 제공합니다. 이 명령은 도구를 제거하고 다시 설치하여 효과적으로 업데이트합니다. 이 명령을 사용하려면 다음 옵션 중 하나를 지정합니다.

* 기본 위치에 설치된 전역 도구를 업데이트하려면 `--global` 옵션을 사용합니다.
* 사용자 지정 위치에 설치된 전역 도구를 업데이트하려면 `--tool-path` 옵션을 사용합니다.
* 로컬 도구를 업데이트하려면 `--global` 및 `--tool-path` 옵션을 생략합니다.

**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**

## <a name="arguments"></a>인수

- **`PACKAGE_NAME`**

  업데이트할 .NET Core 전역 도구를 포함하는 NuGet 패키지의 이름/ID입니다. [dotnet tool list](dotnet-tool-list.md) 명령을 사용하여 패키지 이름을 찾을 수 있습니다.

## <a name="options"></a>옵션

- **`--add-source <SOURCE>`**

  설치 중에 사용할 추가 NuGet 패키지 원본을 추가합니다.

- **`--configfile <FILE>`**

  사용할 NuGet 구성(*nuget.config*) 파일입니다.

- **`--framework <FRAMEWORK>`**

  도구를 업데이트할 [대상 프레임워크](../../standard/frameworks.md)를 지정합니다.

- **`-g|--global`**

  업데이트가 사용자 수준 도구에 대한 것임을 지정합니다. `--tool-path` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--tool-path <PATH>`**

  전역 도구가 설치되는 위치를 지정합니다. PATH는 절대적이거나 상대적일 수 있습니다. `--global` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 업데이트할 도구로 로컬 도구를 지정합니다.

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

## <a name="see-also"></a>참조

- [.NET Core 도구](global-tools.md)
