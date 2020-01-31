---
title: dotnet sln 명령
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
ms.date: 10/29/2019
ms.openlocfilehash: e344deaae0867202a79a3c38df48a2be8d4d7d13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733077"
---
# <a name="dotnet-sln"></a>dotnet sln

**이 문서의 적용 대상:**  ✔️ .NET Core 1.x SDK 이상 버전

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>이름

`dotnet sln` - .NET Core 솔루션 파일을 수정합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>설명

`dotnet sln` 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.

`dotnet sln` 명령을 사용하려면 솔루션 파일이 이미 있어야 합니다. 하나를 생성해야 하는 경우, 다음 예제와 같이 [dotnet new](dotnet-new.md) 명령을 사용합니다.

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="commands"></a>명령

### `add`

솔루션 파일에 하나 이상의 프로젝트를 추가합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

- **`PROJECT_PATH`**

  솔루션에 추가할 프로젝트의 경로입니다. 공백으로 구분된 다른 경로를 추가하여 여러 프로젝트를 추가합니다. Unix/Linux 셸 [GLOB 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

- **`--in-root`**

  솔루션 폴더를 만드는 대신, 솔루션의 루트에 프로젝트를 배치합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-s|--solution-folder`**

  프로젝트를 추가하려는 대상 솔루션 폴더 경로입니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

### `remove`

솔루션 파일에서 하나 이상의 프로젝트를 제거합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

- **`PROJECT_PATH`**

  솔루션에서 제거할 프로젝트 경로입니다. 공백으로 구분된 다른 경로를 추가하여 여러 프로젝트를 제거합니다. Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

### `list`

솔루션 파일의 모든 프로젝트를 나열합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다. 디렉터리에 여러 솔루션 파일이 있으면 하나를 지정해야 합니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령에 대한 간단한 도움말을 출력합니다.

## <a name="examples"></a>예

- 솔루션에 C# 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- 솔루션에서 C# 프로젝트를 제거합니다.

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
  ```

- 솔루션에 여러 C# 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- 솔루션에서 여러 C# 프로젝트를 제거합니다.

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- 와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다(Unix/Linux만 해당).

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- 와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다(Unix/Linux만 해당).

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
