---
title: dotnet tool list 명령
description: dotnet tool list 명령은 컴퓨터에 설치된 .NET Core 도구를 나열합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 7ca894ab0f5daf0118ff92fb39e0118b952b3d83
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768276"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전

## <a name="name"></a>이름

`dotnet tool list` - 컴퓨터에 현재 설치되어 있는 지정된 유형의 모든 [.NET Core 도구](global-tools.md)를 나열합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a>설명

`dotnet tool list` 명령을 사용하면 머신에 설치된 모든 .NET Core 전역, 도구 경로 또는 로컬 도구를 나열할 수 있습니다. 이 명령은 패키지 이름, 설치된 버전 및 도구 명령을 나열합니다.  이 명령을 사용하려면 다음 중 하나를 지정합니다.

* 기본 위치에 설치된 전역 도구를 나열하려면 `--global` 옵션을 사용합니다.
* 사용자 지정 위치에 설치된 전역 도구를 나열하려면 `--tool-path` 옵션을 사용합니다.
* 로컬 도구를 나열하려면 `--local` 옵션을 사용하거나 `--global`, `--tool-path` 및 `--local` 옵션을 생략합니다.

**로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.**

## <a name="options"></a>옵션

- **`-g|--global`**

  사용자 수준 전역 도구를 나열합니다. `--tool-path` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--local`**

  현재 디렉터리에 대한 로컬 도구를 나열합니다. `--global` 또는 `--tool-path` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path`를 둘 다 생략하면 `--local`을 지정하지 않아도 로컬 도구가 나열됩니다.

- **`--tool-path <PATH>`**

  전역 도구를 찾을 사용자 지정 위치를 지정합니다. PATH는 절대적이거나 상대적일 수 있습니다. `--global` 옵션과 함께 사용할 수 없습니다. `--global` 및 `--tool-path` 옵션을 모두 생략하면 로컬 도구가 나열됩니다.

## <a name="examples"></a>예

- **`dotnet tool list -g`**

  사용자 수준에서 컴퓨터에 설치된 모든 전역 도구를 나열합니다(현재 사용자 프로필).

- **`dotnet tool list --tool-path c:\global-tools`**

  특정 Windows 디렉터리의 전역 도구를 나열합니다.

- **`dotnet tool list --tool-path ~/bin`**

  특정 Linux/macOS 디렉터리의 전역 도구를 나열합니다.

- **`dotnet tool list`** 또는 **`dotnet tool list --local`**

  현재 디렉터리에서 사용할 수 있는 모든 로컬 도구를 나열합니다.

## <a name="see-also"></a>참조

- [.NET Core 도구](global-tools.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 전역 도구 설치 및 사용](global-tools-how-to-use.md)
- [자습서: .NET Core CLI를 사용하여 .NET Core 로컬 도구 설치 및 사용](local-tools-how-to-use.md)
