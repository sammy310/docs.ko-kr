---
title: dotnet sln 명령
description: dotnet-sln 명령은 솔루션 파일의 프로젝트를 추가, 제거 및 나열하는 간편한 옵션을 제공합니다.
ms.date: 02/14/2020
ms.openlocfilehash: 898c53772a28b8cc3b65532dfc3d9bd6e73d467c
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634372"
---
# <a name="dotnet-sln"></a>dotnet sln

**이 문서의 적용 대상:** ✔️ .NET Core 2.x SDK 이상 버전

## <a name="name"></a>이름

`dotnet sln` - .NET 솔루션 파일의 프로젝트를 나열하거나 수정합니다.

## <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a>설명

`dotnet sln` 명령은 솔루션 파일의 프로젝트를 나열 및 수정하는 간편한 옵션을 제공합니다.

`dotnet sln` 명령을 사용하려면 솔루션 파일이 이미 있어야 합니다. 파일을 생성해야 하는 경우, 다음 예제와 같이 [dotnet new](dotnet-new.md) 명령을 사용합니다.

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 이 인수를 생략하면 명령은 현재 디렉터리에서 파일을 검색합니다. 솔루션 파일이 없거나 여러 개 있는 경우 명령이 실패합니다.

## <a name="options"></a>옵션

- **`-h|--help`**

  명령을 사용하는 방법에 대한 설명을 출력합니다.

## <a name="commands"></a>명령

### `list`

솔루션 파일의 모든 프로젝트를 나열합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 이 인수를 생략하면 명령은 현재 디렉터리에서 파일을 검색합니다. 솔루션 파일이 없거나 여러 개 있는 경우 명령이 실패합니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령을 사용하는 방법에 대한 설명을 출력합니다.
  
### `add`

솔루션 파일에 하나 이상의 프로젝트를 추가합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정되지 않은 경우 이 명령은 현재 디렉터리를 검색하고, 여러 솔루션 파일이 있을 경우 실패합니다.

- **`PROJECT_PATH`**

  솔루션에 추가할 프로젝트의 경로입니다. Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령을 사용하는 방법에 대한 설명을 출력합니다.

- **`--in-root`**

  솔루션 폴더를 만드는 대신, 솔루션의 루트에 프로젝트를 배치합니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

- **`-s|--solution-folder <PATH>`**

  프로젝트를 추가하려는 대상 솔루션 폴더 경로입니다. .NET Core 3.0 SDK 이후 사용할 수 있습니다.

### `remove`

솔루션 파일에서 하나 이상의 프로젝트를 제거합니다.

#### <a name="synopsis"></a>개요

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>인수

- **`SOLUTION_FILE`**

  사용할 솔루션 파일입니다. 지정되지 않은 경우 이 명령은 현재 디렉터리를 검색하고, 여러 솔루션 파일이 있을 경우 실패합니다.

- **`PROJECT_PATH`**

  솔루션에 추가할 프로젝트의 경로입니다. Unix/Linux 셸 [와일드카드 패턴](https://en.wikipedia.org/wiki/Glob_(programming)) 확장은 `dotnet sln` 명령에 의해 올바르게 처리됩니다.

#### <a name="options"></a>옵션

- **`-h|--help`**

  명령을 사용하는 방법에 대한 설명을 출력합니다.

## <a name="examples"></a>예

- 솔루션의 프로젝트를 나열합니다.

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- 솔루션에 C# 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- 솔루션에서 C# 프로젝트를 제거합니다.

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- 솔루션의 루트에 여러 C# 프로젝트를 추가합니다.

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
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

- 와일드카드 사용 패턴을 사용하여 솔루션에 여러 C# 프로젝트를 추가합니다(Windows PowerShell만 해당).

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- 와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다(Unix/Linux만 해당).

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- 와일드카드 사용 패턴을 사용하여 솔루션에서 여러 C# 프로젝트를 제거합니다(Windows PowerShell만 해당).

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```
