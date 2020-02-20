---
title: 명령줄 도구를 사용하여 F# 시작
description: 운영 체제 (Windows, macOS 또는 Linux)에서 F# .NET Core CLI 사용 하 여 간단한 다중 프로젝트 솔루션을 빌드하는 방법에 대해 알아봅니다.
ms.date: 03/26/2018
ms.openlocfilehash: 6f67314f49150e20b18734f21f24daa3ce856922
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504137"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="e28ad-103">.NET Core CLI를 사용하여 F# 시작</span><span class="sxs-lookup"><span data-stu-id="e28ad-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="e28ad-104">이 문서에서는 .NET Core CLI를 사용 하 여 운영 F# 체제 (Windows, Macos 또는 Linux)에서를 시작 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="e28ad-105">콘솔 응용 프로그램에서 호출 하는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션을 빌드하는 과정을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e28ad-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="e28ad-106">Prerequisites</span></span>

<span data-ttu-id="e28ad-107">시작 하려면 최신 [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="e28ad-108">이 문서에서는 명령줄과 원하는 텍스트 편집기의 사용 방법을 알고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="e28ad-109">이 옵션을 사용 하지 않는 경우 [Visual Studio Code](get-started-vscode.md) 은의 F#텍스트 편집기 처럼 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="e28ad-110">간단한 다중 프로젝트 솔루션 구축</span><span class="sxs-lookup"><span data-stu-id="e28ad-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="e28ad-111">명령 프롬프트/터미널을 열고 [dotnet new](../../core/tools/dotnet-new.md) 명령을 사용 하 여 `FSNetCore`라는 새 솔루션 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="e28ad-112">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="e28ad-113">클래스 라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="e28ad-113">Write a class library</span></span>

<span data-ttu-id="e28ad-114">디렉터리를 *Fsnetcore*로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="e28ad-115">`dotnet new` 명령을 사용 하 여 Library 라는 **src** 폴더에 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="e28ad-116">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="e28ad-117">`Library.fs` 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="e28ad-118">라이브러리 프로젝트에 Newtonsoft.json NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="e28ad-119">[Dotnet sln add](../../core/tools/dotnet-sln.md) 명령을 사용 하 여 `Library` 프로젝트를 `FSNetCore` 솔루션에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="e28ad-120">`dotnet build`를 실행 하 여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="e28ad-121">확인되지 않은 종속성은 빌드할 때 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="e28ad-122">클래스 라이브러리를 사용하는 콘솔 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="e28ad-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="e28ad-123">`dotnet new` 명령을 사용 하 여 App 이라는 **src** 폴더에 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="e28ad-124">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="e28ad-125">`Program.fs` 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="e28ad-126">[Dotnet add reference](../../core/tools/dotnet-add-reference.md)를 사용 하 여 `Library` 프로젝트에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="e28ad-127">`dotnet sln add` 명령을 사용 하 여 `FSNetCore` 솔루션에 `App` 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="e28ad-128">NuGet 종속성 `dotnet restore` 복원 하 고 `dotnet build`를 실행 하 여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="e28ad-129">디렉터리를 `src/App` 콘솔 프로젝트로 변경 하 고 `Hello World`을 인수로 전달 하는 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```dotnetcli
cd src/App
dotnet run Hello World
```

<span data-ttu-id="e28ad-130">다음 결과가 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="e28ad-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e28ad-131">Next steps</span></span>

<span data-ttu-id="e28ad-132">다음으로, 다른 F# 기능에 대해 자세히 알아보려면 [둘러보기 F# ](../tour.md) 를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e28ad-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
