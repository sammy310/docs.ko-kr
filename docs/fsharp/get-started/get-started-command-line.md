---
title: 명령줄 도구를 사용하여 F# 시작
description: 운영 체제 (Windows, macOS 또는 Linux)에서 F# .NET Core CLI 사용 하 여 간단한 다중 프로젝트 솔루션을 빌드하는 방법에 대해 알아봅니다.
ms.date: 03/26/2018
ms.openlocfilehash: aa3ed84660a951eeafc11a00ea3831f587b6d876
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559489"
---
# <a name="get-started-with-f-with-the-net-core-cli"></a><span data-ttu-id="e6ef4-103">.NET Core CLI를 사용하여 F# 시작</span><span class="sxs-lookup"><span data-stu-id="e6ef4-103">Get started with F# with the .NET Core CLI</span></span>

<span data-ttu-id="e6ef4-104">이 문서에서는 .NET Core CLI를 사용 하 여 운영 F# 체제 (Windows, Macos 또는 Linux)에서를 시작 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-104">This article covers how you can get started with F# on any operating system (Windows, macOS, or Linux) with the .NET Core CLI.</span></span> <span data-ttu-id="e6ef4-105">콘솔 응용 프로그램에서 호출 하는 클래스 라이브러리를 사용 하 여 다중 프로젝트 솔루션을 빌드하는 과정을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-105">It goes through building a multi-project solution with a class library that is called by a console application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6ef4-106">전제 조건</span><span class="sxs-lookup"><span data-stu-id="e6ef4-106">Prerequisites</span></span>

<span data-ttu-id="e6ef4-107">시작하려면 최신 [.NET Core SDK](https://dotnet.microsoft.com/download)를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-107">To begin, you must install the latest [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>

<span data-ttu-id="e6ef4-108">이 문서에서는 명령줄과 원하는 텍스트 편집기의 사용 방법을 알고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-108">This article assumes that you know how to use a command line and have a preferred text editor.</span></span> <span data-ttu-id="e6ef4-109">아직 사용하고 있지 않은 경우라면, [Visual Studio Code](get-started-vscode.md)는 F#용 텍스트 편집기로 선택할 수 있는 훌륭한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-109">If you don't already use it, [Visual Studio Code](get-started-vscode.md) is a great option as a text editor for F#.</span></span>

## <a name="build-a-simple-multi-project-solution"></a><span data-ttu-id="e6ef4-110">간단한 다중 프로젝트 솔루션 구축</span><span class="sxs-lookup"><span data-stu-id="e6ef4-110">Build a simple multi-project solution</span></span>

<span data-ttu-id="e6ef4-111">명령 프롬프트나 터미널을 열고 `FSNetCore`라는 새 솔루션 파일을 만들기 위해 [dotnet new](../../core/tools/dotnet-new.md) 명령을 다음과 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-111">Open a command prompt/terminal and use the [dotnet new](../../core/tools/dotnet-new.md) command to create new solution file called `FSNetCore`:</span></span>

```dotnetcli
dotnet new sln -o FSNetCore
```

<span data-ttu-id="e6ef4-112">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-112">The following directory structure is produced after running the previous command:</span></span>

```console
FSNetCore
    ├── FSNetCore.sln
```

### <a name="write-a-class-library"></a><span data-ttu-id="e6ef4-113">클래스 라이브러리 작성</span><span class="sxs-lookup"><span data-stu-id="e6ef4-113">Write a class library</span></span>

<span data-ttu-id="e6ef4-114">*FSNetCore*로 디렉터리를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-114">Change directories to *FSNetCore*.</span></span>

<span data-ttu-id="e6ef4-115">`dotnet new` 명령어를 사용하여 **src** 폴더에 Library라는 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-115">Use the `dotnet new` command, create a class library project in the **src** folder named Library.</span></span>

```dotnetcli
dotnet new classlib -lang "F#" -o src/Library
```

<span data-ttu-id="e6ef4-116">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-116">The following directory structure is produced after running the previous command:</span></span>

```console
└── FSNetCore
    ├── FSNetCore.sln
    └── src
        └── Library
            ├── Library.fs
            └── Library.fsproj
```

<span data-ttu-id="e6ef4-117">`Library.fs`의 내용을 다음 코드로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-117">Replace the contents of `Library.fs` with the following code:</span></span>

```fsharp
module Library

open Newtonsoft.Json

let getJsonNetJson value =
    sprintf "I used to be %s but now I'm %s thanks to JSON.NET!" value (JsonConvert.SerializeObject(value))
```

<span data-ttu-id="e6ef4-118">라이브러리 프로젝트에 Newtonsoft.json NuGet 패키지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-118">Add the Newtonsoft.Json NuGet package to the Library project.</span></span>

```dotnetcli
dotnet add src/Library/Library.fsproj package Newtonsoft.Json
```

<span data-ttu-id="e6ef4-119">다음과 같이 [dotnet sln add](../../core/tools/dotnet-sln.md)명령을 사용하여 `FSNetCore` 솔루션에 `Library` 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-119">Add the `Library` project to the `FSNetCore` solution using the [dotnet sln add](../../core/tools/dotnet-sln.md) command:</span></span>

```dotnetcli
dotnet sln add src/Library/Library.fsproj
```

<span data-ttu-id="e6ef4-120">`dotnet build`를 실행하여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-120">Run `dotnet build` to build the project.</span></span> <span data-ttu-id="e6ef4-121">확인되지 않은 종속성은 빌드할 때 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-121">Unresolved dependencies will be restored when building.</span></span>

### <a name="write-a-console-application-that-consumes-the-class-library"></a><span data-ttu-id="e6ef4-122">클래스 라이브러리를 사용하는 콘솔 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="e6ef4-122">Write a console application that consumes the class library</span></span>

<span data-ttu-id="e6ef4-123">다음과 같이 `dotnet new` 명령을 사용하여 **src**의 App 폴더에 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-123">Use the `dotnet new` command, create a console application in the **src** folder named App.</span></span>

```dotnetcli
dotnet new console -lang "F#" -o src/App
```

<span data-ttu-id="e6ef4-124">위의 명령을 실행하면 다음과 같은 디렉터리 구조가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-124">The following directory structure is produced after running the previous command:</span></span>

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

<span data-ttu-id="e6ef4-125">`Program.fs`파일의 내용을 다음 코드로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-125">Replace the contents of the `Program.fs` file with the following code:</span></span>

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

<span data-ttu-id="e6ef4-126">다음과 같이 [dotnet add reference](../../core/tools/dotnet-add-reference.md)를 사용하여 `Library`에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-126">Add a reference to the `Library` project using [dotnet add reference](../../core/tools/dotnet-add-reference.md).</span></span>

```dotnetcli
dotnet add src/App/App.fsproj reference src/Library/Library.fsproj
```

<span data-ttu-id="e6ef4-127">다음과 같이 `dotnet sln add` 명령을 사용하여 `FSNetCore`솔루션에 `App` 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-127">Add the `App` project to the `FSNetCore` solution using the `dotnet sln add` command:</span></span>

```dotnetcli
dotnet sln add src/App/App.fsproj
```

<span data-ttu-id="e6ef4-128">`dotnet restore`로 NuGet 종속성을 복원하고 `dotnet build`을 실해하여 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-128">Restore the NuGet dependencies, `dotnet restore` and run `dotnet build` to build the project.</span></span>

<span data-ttu-id="e6ef4-129">다음과 같이 `src/App` 콘솔 프로젝트로 디렉터리를 변경하고, `Hello World` 인수를 전달하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-129">Change directory to the `src/App` console project and run the project passing `Hello World` as arguments:</span></span>

```console
cd src/App
dotnet run Hello World
```

<span data-ttu-id="e6ef4-130">다음 결과가 보일 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-130">You should see the following results:</span></span>

```console
Nice command-line arguments! Here's what JSON.NET has to say about them:

I used to be Hello but now I'm ""Hello"" thanks to JSON.NET!
I used to be World but now I'm ""World"" thanks to JSON.NET!
```

## <a name="next-steps"></a><span data-ttu-id="e6ef4-131">다음 단계</span><span class="sxs-lookup"><span data-stu-id="e6ef4-131">Next steps</span></span>

<span data-ttu-id="e6ef4-132">다음으로 다양한 F#기능을 알아보기 위해 [F# 둘러보기](../tour.md)를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e6ef4-132">Next, check out the [Tour of F#](../tour.md) to learn more about different F# features.</span></span>
