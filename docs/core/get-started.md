---
title: .NET Core 시작
description: Windows, Linux 및 macOS에서 .NET Core 애플리케이션을 빌드하는 방법을 알아볼 수 있는 리소스를 찾아보세요.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 0968d9db1dbfbdc8c586328ee8e02315f17950b9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714389"
---
# <a name="get-started-with-net-core"></a><span data-ttu-id="a4743-103">.NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="a4743-103">Get started with .NET Core</span></span>

<span data-ttu-id="a4743-104">이 문서에서는 .NET Core로 시작하는 데 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-104">This article provides information on getting started with .NET Core.</span></span> <span data-ttu-id="a4743-105">Windows, Linux 및 macOS에서 .NET Core를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-105">.NET Core can be installed on Windows, Linux, and macOS.</span></span> <span data-ttu-id="a4743-106">원하는 텍스트 편집기에서 코딩하고 플랫폼 간 라이브러리 및 애플리케이션을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-106">You can code in your favorite text editor and produce cross-platform libraries and applications.</span></span>

<span data-ttu-id="a4743-107">.NET Core가 무엇인지 또는 다른 .NET 기술과 어떻게 관련있는지에 대해 잘 모를 경우 [.NET이란](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) 개요로 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-107">If you're unsure what .NET Core is, or how it relates to other .NET technologies, start with the [What is .NET](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet) overview.</span></span> <span data-ttu-id="a4743-108">간단히 말해 .NET Core는 오픈 소스의 플랫폼 간 .NET의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-108">Put simply, .NET Core is an open-source, cross-platform implementation of .NET.</span></span>

## <a name="create-an-application"></a><span data-ttu-id="a4743-109">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="a4743-109">Create an application</span></span>

<span data-ttu-id="a4743-110">먼저 사용자의 컴퓨터에 [.NET Core SDK](https://dotnet.microsoft.com/download)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-110">First, download and install the [.NET Core SDK](https://dotnet.microsoft.com/download) on your computer.</span></span>

<span data-ttu-id="a4743-111">다음으로 **PowerShell**, **명령 프롬프트** 또는 **Bash**와 같은 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-111">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="a4743-112">다음 `dotnet` 명령을 입력하여 C# 애플리케이션을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-112">Type the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="a4743-113">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-113">You should see the following output:</span></span>

```console
Hello World!
```

<span data-ttu-id="a4743-114">지금까지</span><span class="sxs-lookup"><span data-stu-id="a4743-114">Congratulations!</span></span> <span data-ttu-id="a4743-115">간단한 .NET Core 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-115">You've created a simple .NET Core application.</span></span> <span data-ttu-id="a4743-116">또한 [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md)(Windows만 해당) 또는 [Mac용 Visual Studio](./tutorials/using-on-mac-vs.md)(macOS만 해당)를 사용하여 .NET Core 애플리케이션을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-116">You can also use [Visual Studio Code](./tutorials/with-visual-studio-code.md), [Visual Studio](./tutorials/with-visual-studio.md) (Windows only), or [Visual Studio for Mac](./tutorials/using-on-mac-vs.md) (macOS only), to create a .NET Core application.</span></span>

## <a name="tutorials"></a><span data-ttu-id="a4743-117">자습서</span><span class="sxs-lookup"><span data-stu-id="a4743-117">Tutorials</span></span>

<span data-ttu-id="a4743-118">다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-118">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="a4743-119">Windows</span><span class="sxs-lookup"><span data-stu-id="a4743-119">Windows</span></span>](#tab/windows)

- [<span data-ttu-id="a4743-120">Visual Studio 2019에서 첫 번째 .NET Core 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="a4743-120">Create your first .NET Core console application in Visual Studio 2019</span></span>](./tutorials/with-visual-studio.md)
- [<span data-ttu-id="a4743-121">Visual Studio에서 .NET Standard를 사용하여 클래스 라이브러리 빌드</span><span class="sxs-lookup"><span data-stu-id="a4743-121">Build a class library with .NET Standard in Visual Studio</span></span>](./tutorials/library-with-visual-studio.md)
- [<span data-ttu-id="a4743-122">.NET Core CLI를 사용하여 .NET Core 시작하기</span><span class="sxs-lookup"><span data-stu-id="a4743-122">Get started with .NET Core using the .NET Core CLI</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="a4743-123">![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청")</span><span class="sxs-lookup"><span data-stu-id="a4743-123">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a4743-124">Channel 9에서 [Visual Studio Code 및 .NET Core 설치 방법](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/)을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-124">Watch the [how to install and use Visual Studio Code and .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) video on Channel 9.</span></span> |
| <span data-ttu-id="a4743-125">![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청")</span><span class="sxs-lookup"><span data-stu-id="a4743-125">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a4743-126">YouTube에서 [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) 동영상을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-126">Watch the [.NET Core 101](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) videos on YouTube.</span></span> |

<span data-ttu-id="a4743-127">지원되는 Windows 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-windows) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-127">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-windows) article for a list of the supported Windows versions.</span></span>

# <a name="linux"></a>[<span data-ttu-id="a4743-128">Linux</span><span class="sxs-lookup"><span data-stu-id="a4743-128">Linux</span></span>](#tab/linux)

<span data-ttu-id="a4743-129">다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-129">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="a4743-130">명령줄을 사용하여 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="a4743-130">Get started with .NET Core using the command line</span></span>](./tutorials/cli-create-console-app.md)

|   |   |
|---|---|
| <span data-ttu-id="a4743-131">![동영상에 대한 비디오 카메라 아이콘](./media/video-icon.png "비디오 시청")</span><span class="sxs-lookup"><span data-stu-id="a4743-131">![movie camera icon for video](./media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a4743-132">[Ubuntu에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu)에 관한 비디오 시청.</span><span class="sxs-lookup"><span data-stu-id="a4743-132">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span> |

<span data-ttu-id="a4743-133">지원되는 Linux 배포판 및 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-linux) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-133">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-linux) article for a list of the supported Linux distros and versions.</span></span>

# <a name="macos"></a>[<span data-ttu-id="a4743-134">macOS</span><span class="sxs-lookup"><span data-stu-id="a4743-134">macOS</span></span>](#tab/macos)

<span data-ttu-id="a4743-135">다음 단계별 자습서에 따라 .NET Core 애플리케이션 개발을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a4743-135">Get started developing .NET Core applications by following these step-by-step tutorials:</span></span>

- [<span data-ttu-id="a4743-136">Visual Studio Code를 사용하여 macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="a4743-136">Get started with .NET Core on macOS using Visual Studio Code</span></span>](./tutorials/using-on-macos.md)
- [<span data-ttu-id="a4743-137">명령줄을 사용하여 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="a4743-137">Get started with .NET Core using the command-line</span></span>](./tutorials/cli-create-console-app.md)
- [<span data-ttu-id="a4743-138">Mac용 Visual Studio를 사용하여 macOS에서 .NET Core 시작</span><span class="sxs-lookup"><span data-stu-id="a4743-138">Get started with .NET Core on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs.md)
- [<span data-ttu-id="a4743-139">Mac용 Visual Studio를 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드</span><span class="sxs-lookup"><span data-stu-id="a4743-139">Build a complete .NET Core solution on macOS using Visual Studio for Mac</span></span>](./tutorials/using-on-mac-vs-full-solution.md)

|   |   |
|---|---|
| <span data-ttu-id="a4743-140">![동영상에 대한 비디오 카메라 아이콘](media/video-icon.png "비디오 시청")</span><span class="sxs-lookup"><span data-stu-id="a4743-140">![movie camera icon for video](media/video-icon.png "Watch a video")</span></span> | <span data-ttu-id="a4743-141">[macOS에서 C# 및 .NET Core를 사용하여 Visual Studio Code 시작](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac)에 관한 동영상을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-141">Watch a video on [getting started with Visual Studio Code using C# and .NET Core on macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).</span></span> |

<span data-ttu-id="a4743-142">지원되는 OS X/macOS 버전 목록은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?pivots=os-macos) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4743-142">See the [.NET Core dependencies and requirements](install/dependencies.md?pivots=os-macos) article for a list of the supported OS X / macOS versions.</span></span>

---
