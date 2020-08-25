---
title: '명령줄 도구를 사용 하 여 F # 시작'
description: '운영 체제 (Windows, macOS 또는 Linux)에서 .NET Core CLI 사용 하 여 F #에서 간단한 다중 프로젝트 솔루션을 빌드하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: e652b66337a3122de8e6bd4d62d86fb6082b759d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811992"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a>.NET Core CLI를 사용 하 여 F # 시작

이 문서에서는 .NET Core CLI를 사용 하 여 모든 운영 체제 (Windows, macOS 또는 Linux)에서 F #을 시작 하는 방법을 설명 합니다. 콘솔 응용 프로그램에서 호출 하는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션을 빌드하는 과정을 거칩니다.

## <a name="prerequisites"></a>사전 요구 사항

시작 하려면 최신 [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치 해야 합니다.

이 문서에서는 명령줄을 사용 하는 방법 및 기본 텍스트 편집기를 사용 하는 방법을 알고 있다고 가정 합니다. 아직 사용 하지 않는 경우 F #의 텍스트 편집기로 [Visual Studio Code](get-started-vscode.md) 을 사용 하는 것이 좋습니다.

## <a name="build-a-simple-multi-project-solution"></a>간단한 다중 프로젝트 솔루션 빌드

명령 프롬프트/터미널을 열고 [dotnet new](../../core/tools/dotnet-new.md) 명령을 사용 하 여 라는 새 솔루션 파일을 만듭니다 `FSNetCore` .

```dotnetcli
dotnet new sln -o FSNetCore
```

다음 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a>클래스 라이브러리 작성

디렉터리를 *Fsnetcore*로 변경 합니다.

명령을 사용 하 여 `dotnet new` 이름이 library 인 **src** 폴더에 클래스 라이브러리 프로젝트를 만듭니다.

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

다음 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

의 내용을 `Library.fs` 다음 코드로 바꿉니다.

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    let json = JsonConvert.SerializeObject(value)
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value json
```

NuGet 패키지에 대 한 Newtonsoft.Js를 라이브러리 프로젝트에 추가 합니다.

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

`Library` `FSNetCore` [Dotnet sln add](../../core/tools/dotnet-sln.md) 명령을 사용 하 여 솔루션에 프로젝트를 추가 합니다.

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

`dotnet build`을 실행 하 여 프로젝트를 빌드합니다. 확인할 수 없는 종속성은 빌드할 때 복원 됩니다.

### <a name="write-a-console-application-that-consumes-the-class-library"></a>클래스 라이브러리를 사용 하는 콘솔 응용 프로그램 작성

명령을 사용 하 여 `dotnet new` App 이라는 **src** 폴더에 콘솔 응용 프로그램을 만듭니다.

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

다음 디렉터리 구조는 이전 명령을 실행 한 후에 생성 됩니다.

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

`Program.fs` 파일의 내용을 다음 코드로 바꿉니다.

```fsharp
open System
open Library

[<EntryPoint>]
let main argv =
    printfn "Nice command-line arguments! Here's what JSON.NET has to say about them:"

    for arg in argv do
        let value = getJsonNetJson arg
        printfn "%s" value

    0 // return an integer exit code
```

`Library` [Dotnet add 참조](../../core/tools/dotnet-add-reference.md)를 사용 하 여 프로젝트에 대 한 참조를 추가 합니다.

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

`App` `FSNetCore` 명령을 사용 하 여 솔루션에 프로젝트를 추가 합니다 `dotnet sln add` .

```dotnetcli
dotnet sln add src/App/App.fsproj
```

NuGet 종속성을 복원 하 `dotnet restore` 고 `dotnet build` 를 실행 하 여 프로젝트를 빌드합니다.

디렉터리를 `src/App` 콘솔 프로젝트로 변경 하 고 인수로 전달 되는 프로젝트를 실행 합니다 `Hello World` .

```dotnetcli
cd src/App
dotnet run Hello World
```

다음 결과가 보일 것입니다.

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a>다음 단계

다음으로 f [# 둘러보기](../tour.md) 를 확인 하 여 다른 f # 기능에 대해 자세히 알아보세요.
