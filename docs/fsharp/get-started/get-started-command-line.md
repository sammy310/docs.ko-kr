---
title: 시작 F# 명령줄 도구를 사용 하 여
description: 간단한 다중 프로젝트 솔루션을 구축 하는 방법에 알아봅니다 F# .NET Core CLI를 사용 하 여 운영 체제 (Windows, macOs 또는 Linux).
ms.date: 03/26/2018
ms.openlocfilehash: bc9b223fcf133ffe8b19d5284dcbd3c14a426235
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938699"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>.NET Core CLI를 사용하여 F# 시작

이 문서에서는 어떻게 시작할 수 있습니다 사용 하 여 F# .NET Core CLI를 사용 하 여 운영 체제 (Windows, macOS 또는 Linux). 콘솔 응용 프로그램에 의해 호출 되는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션 빌드를 거치게 됩니다.

## <a name="prerequisites"></a>전제 조건

시작하려면 최신 [.NET Core SDK](https://www.microsoft.com/net/download/)를 설치해야 합니다.

이 문서에서는 명령줄과 원하는 텍스트 편집기의 사용 방법을 알고 있다고 가정합니다. 아직 사용하고 있지 않은 경우라면, [Visual Studio Code](get-started-vscode.md)는 F#용 텍스트 편집기로 선택할 수 있는 훌륭한 옵션입니다.

## <a name="build-a-simple-multi-project-solution"></a>간단한 다중 프로젝트 솔루션 구축

명령 프롬프트나 터미널을 열고 `FSNetCore`라는 새 솔루션 파일을 만들기 위해 [dotnet new](../../core/tools/dotnet-new.md) 명령을 다음과 같이 사용합니다.

```console
dotnet new sln -o FSNetCore
```

위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>클래스 라이브러리 작성

디렉터리를 변경 *FSNetCore*합니다.

사용 합니다 `dotnet new` 명령, 클래스 라이브러리 프로젝트를 만들기는 **src** 라이브러리 라는 폴더입니다.

```console
dotnet new classlib -lang F# -o src/Library
```

위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

내용을 바꿉니다 `Library.fs` 다음 코드를 사용 하 여:

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

라이브러리 프로젝트에 Newtonsoft.Json NuGet 패키지를 추가 합니다.

```console
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

추가 합니다 `Library` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 [dotnet sln 추가](../../core/tools/dotnet-sln.md) 명령:

```console
dotnet sln add src/Library/Library.fsproj
```

실행 `dotnet build` 프로젝트를 빌드합니다. 확인 되지 않은 종속성을 빌드할 때 복원 됩니다.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성

사용 합니다 `dotnet new` 명령에서 콘솔 응용 프로그램을 만들기는 **src** 앱 라는 폴더입니다.

```console
dotnet new console -lang F# -o src/App
```

위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        ├── App
        │   ├── App.fsproj
        │   ├── Program.fs
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

내용을 대체 합니다 `Program.fs` 를 다음 코드로 파일:

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    argv
    |> Array.map getJsonNetJson
    |> Array.iter (printfn "%s")

    0 // return an integer exit code
```

에 대 한 참조를 추가 합니다 `Library` 사용 하 여 프로젝트 [참조를 추가 하는 dotnet](../../core/tools/dotnet-add-reference.md)합니다.

```console
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

추가 합니다 `App` 프로젝트를 합니다 `FSNetCore` 사용 하 여 솔루션을 `dotnet sln add` 명령:

```console
dotnet sln add src/App/App.fsproj
```

NuGet 종속성을 복원 `dotnet restore` 실행 `dotnet build` 프로젝트를 빌드합니다.

디렉터리를 변경 합니다 `src/App` 전달 프로젝트를 실행 하 고 프로젝트를 콘솔 `Hello World` 인수로:

```console
cd src/App
dotnet run Hello World
```

다음과 같은 결과가 표시 됩니다.

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>다음 단계

다음으로 체크 아웃 합니다 [둘러보기 F# ](../tour.md) 다양 한에 대해 자세히 알아보려면 F# 기능.
