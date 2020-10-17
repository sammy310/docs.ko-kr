---
title: .NET 시작
description: Hello World .NET 앱을 만듭니다.
author: adegeo
ms.author: adegeo
ms.date: 09/29/2020
ms.custom: vs-dotnet
ms.openlocfilehash: 6ad2b96e668c52ee80b707e31a63eac2433f3c9e
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756093"
---
# <a name="get-started-with-net"></a><span data-ttu-id="1f880-103">.NET 시작</span><span class="sxs-lookup"><span data-stu-id="1f880-103">Get started with .NET</span></span>

<span data-ttu-id="1f880-104">이 문서에서는 “Hello World!”</span><span class="sxs-lookup"><span data-stu-id="1f880-104">This article teaches you how to create and run a "Hello World!"</span></span> <span data-ttu-id="1f880-105">.NET 앱을 만들고 실행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-105">.NET app.</span></span>

<span data-ttu-id="1f880-106">.NET이 무엇인지 잘 모른다면 [.NET 소개](introduction.md)에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-106">If you're unsure what .NET is, start with the [.NET introduction](introduction.md).</span></span>

## <a name="create-an-application"></a><span data-ttu-id="1f880-107">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="1f880-107">Create an application</span></span>

<span data-ttu-id="1f880-108">먼저 컴퓨터에 [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core)를 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-108">First, download and install the [.NET SDK](https://dotnet.microsoft.com/download/dotnet-core) on your computer.</span></span>

<span data-ttu-id="1f880-109">다음으로 **PowerShell**, **명령 프롬프트** 또는 **Bash**와 같은 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-109">Next, open a terminal such as **PowerShell**, **Command Prompt**, or **bash**.</span></span> <span data-ttu-id="1f880-110">다음 `dotnet` 명령을 입력하여 C# 애플리케이션을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-110">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

<span data-ttu-id="1f880-111">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-111">You see the following output:</span></span>

```output
Hello World!
```

<span data-ttu-id="1f880-112">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="1f880-112">Congratulations!</span></span> <span data-ttu-id="1f880-113">간단한 .NET 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-113">You've created a simple .NET application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1f880-114">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1f880-114">Next steps</span></span>

<span data-ttu-id="1f880-115">[단계별 자습서](../standard/get-started.md)를 따르거나 YouTube에서 [.NET 101 동영상](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80)을 보면서 .NET 애플리케이션 개발을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1f880-115">Get started developing .NET applications by following a [step-by-step tutorial](../standard/get-started.md) or by watching [.NET 101 videos](https://www.youtube.com/playlist?list=PLdo4fOcmZ0oWoazjhXQzBKMrFuArxpW80) on YouTube.</span></span>
