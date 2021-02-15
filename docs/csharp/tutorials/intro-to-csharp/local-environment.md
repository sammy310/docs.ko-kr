---
title: C# 소개 - 개발 도구 익히기
description: 이 문서에서는 머신에서 C# 및 .NET 애플리케이션을 개발하는 데 사용할 도구의 기본 사항을 소개합니다.
ms.date: 02/02/2021
ms.openlocfilehash: d5fbd23679fc11f4e4c207c59858a71ab753c038
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585327"
---
# <a name="set-up-your-local-environment"></a><span data-ttu-id="4dcd3-103">로컬 환경 설정</span><span class="sxs-lookup"><span data-stu-id="4dcd3-103">Set up your local environment</span></span>

<span data-ttu-id="4dcd3-104">머신에서 자습서를 실행하는 첫 번째 단계는 개발 환경을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-104">The first step in running a tutorial on your machine is to set up a development environment.</span></span> <span data-ttu-id="4dcd3-105">다음 대체 방법 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-105">Choose one of the following alternatives:</span></span>

* <span data-ttu-id="4dcd3-106">.NET CLI와 원하는 텍스트 또는 코드 편집기를 사용하려면 .NET 자습서 [Hello World 10분 완성](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-106">To use the .NET CLI and your choice of text or code editor, see the .NET tutorial [Hello World in 10 minutes](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro).</span></span> <span data-ttu-id="4dcd3-107">이 자습서에는 Windows, Linux 또는 macOS에서 개발 환경을 설정하기 위한 지침이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-107">The tutorial has instructions for setting up a development environment on Windows, Linux, or macOS.</span></span>
* <span data-ttu-id="4dcd3-108">.NET CLI와 Visual Studio Code를 사용하려면 [.NET SDK](https://dotnet.microsoft.com/download)와 [Visual Studio Code](https://code.visualstudio.com/)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-108">To use the .NET CLI and Visual Studio Code, install the [.NET SDK](https://dotnet.microsoft.com/download) and [Visual Studio Code](https://code.visualstudio.com/).</span></span>
* <span data-ttu-id="4dcd3-109">Windows에서 Visual Studio 2019를 사용하려면 [자습서: Visual Studio에서 간단한 C# 콘솔 앱 만들기](/visualstudio/get-started/csharp/tutorial-console)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-109">To use Visual Studio 2019 on Windows, see [Tutorial: Create a simple C# console app in Visual Studio](/visualstudio/get-started/csharp/tutorial-console).</span></span>

## <a name="basic-application-development-flow"></a><span data-ttu-id="4dcd3-110">기본 애플리케이션 개발 흐름</span><span class="sxs-lookup"><span data-stu-id="4dcd3-110">Basic application development flow</span></span>

<span data-ttu-id="4dcd3-111">이러한 자습서의 지침에서는 .NET CLI를 사용하여 애플리케이션을 만들고, 빌드하고, 실행한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-111">The instructions in these tutorials assume that you're using the .NET CLI to create, build, and run applications.</span></span> <span data-ttu-id="4dcd3-112">다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-112">You'll use the following commands:</span></span>

* <span data-ttu-id="4dcd3-113">[`dotnet new`](../../../core/tools/dotnet-new.md)는 애플리케이션 로더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-113">[`dotnet new`](../../../core/tools/dotnet-new.md) creates an application.</span></span> <span data-ttu-id="4dcd3-114">이 명령은 애플리케이션에 필요한 파일과 자산을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-114">This command generates the files and assets necessary for your application.</span></span> <span data-ttu-id="4dcd3-115">C# 소개 자습서에서는 모두 `console` 애플리케이션 유형을 모두 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-115">The introduction to C# tutorials all use the `console` application type.</span></span> <span data-ttu-id="4dcd3-116">기본 사항을 알고 나면 다른 애플리케이션 유형으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-116">Once you've got the basics, you can expand to other application types.</span></span>
* <span data-ttu-id="4dcd3-117">[`dotnet build`](../../../core/tools/dotnet-build.md)는 실행 파일을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-117">[`dotnet build`](../../../core/tools/dotnet-build.md) builds the executable.</span></span>
* <span data-ttu-id="4dcd3-118">[`dotnet run`](../../../core/tools/dotnet-run.md)은 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-118">[`dotnet run`](../../../core/tools/dotnet-run.md) runs the executable.</span></span>

<span data-ttu-id="4dcd3-119">이러한 자습서를 위해 Visual Studio 2019을 사용하는 경우 자습서에서 다음 CLI 명령 중 하나를 실행하도록 지시하는 경우 Visual Studio 메뉴 선택을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-119">If you use Visual Studio 2019 for these tutorials, you'll choose a Visual Studio menu selection when a tutorial directs you to run one of these CLI commands:</span></span>

* <span data-ttu-id="4dcd3-120">**파일** > **새로 만들기** > **프로젝트** 는 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-120">**File** > **New** > **Project** creates an application.</span></span>
* <span data-ttu-id="4dcd3-121">**빌드** >  **솔루션 빌드** 는 실행 파일을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-121">**Build** >  **Build Solution** builds the executable.</span></span>
* <span data-ttu-id="4dcd3-122">**디버그** > **디버깅하지 않고 시작** 은 실행 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-122">**Debug** > **Start Without Debugging** runs the executable.</span></span>

## <a name="pick-your-tutorial"></a><span data-ttu-id="4dcd3-123">자습서 선택</span><span class="sxs-lookup"><span data-stu-id="4dcd3-123">Pick your tutorial</span></span>

<span data-ttu-id="4dcd3-124">다음과 같은 자습서 중 하나를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-124">You can start with any of the following tutorials:</span></span>

## <a name="numbers-in-c"></a><span data-ttu-id="4dcd3-125">C\#의 숫자</span><span class="sxs-lookup"><span data-stu-id="4dcd3-125">Numbers in C\#</span></span>

<span data-ttu-id="4dcd3-126">[C#의 숫자](numbers-in-csharp-local.md) 자습서에서는 컴퓨터가 숫자를 저장하는 방법과 여러 숫자 형식으로 계산을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-126">In the [Numbers in C#](numbers-in-csharp-local.md) tutorial, you'll learn how computers store numbers and how to perform calculations with different numeric types.</span></span> <span data-ttu-id="4dcd3-127">반올림의 기본 사항과 C#을 사용하여 수학 계산을 수행하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-127">You'll learn the basics of rounding and how to perform mathematical calculations using C#.</span></span>

<span data-ttu-id="4dcd3-128">이 자습서에서는 [Hello World](hello-world.yml) 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-128">This tutorial assumes that you have finished the [Hello world](hello-world.yml) lesson.</span></span>

## <a name="branches-and-loops"></a><span data-ttu-id="4dcd3-129">분기 및 루프</span><span class="sxs-lookup"><span data-stu-id="4dcd3-129">Branches and loops</span></span>

<span data-ttu-id="4dcd3-130">[분기 및 루프](branches-and-loops-local.md) 자습서에서는 변수에 저장된 값에 따라 코드 실행의 여러 경로를 선택하는 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-130">The [Branches and loops](branches-and-loops-local.md) tutorial teaches the basics of selecting different paths of code execution based on the values stored in variables.</span></span> <span data-ttu-id="4dcd3-131">프로그램에서 결정하고 여러 작업을 선택하는 방법에 대한 기본 사항인 제어 흐름의 기본 사항에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-131">You'll learn the basics of control flow, which is the basis of how programs make decisions and choose different actions.</span></span>

<span data-ttu-id="4dcd3-132">이 자습서에서는 [Hello World](hello-world.yml) 및 [C#의 숫자](numbers-in-csharp-local.md) 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-132">This tutorial assumes that you have finished the [Hello world](hello-world.yml) and [Numbers in C#](numbers-in-csharp-local.md) lessons.</span></span>

## <a name="list-collection"></a><span data-ttu-id="4dcd3-133">목록 컬렉션</span><span class="sxs-lookup"><span data-stu-id="4dcd3-133">List collection</span></span>

<span data-ttu-id="4dcd3-134">[목록 컬렉션](arrays-and-collections.md) 단원에서는 데이터 시퀀스를 저장하는 목록 컬렉션 형식을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-134">The [List collection](arrays-and-collections.md) lesson gives you a tour of the List collection type that stores sequences of data.</span></span> <span data-ttu-id="4dcd3-135">항목을 추가 및 제거하고, 항목을 검색하고, 목록을 정렬하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-135">You'll learn how to add and remove items, search for items, and sort the lists.</span></span> <span data-ttu-id="4dcd3-136">여러 종류의 목록을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-136">You'll explore different kinds of lists.</span></span>

<span data-ttu-id="4dcd3-137">이 자습서에서는 위에 나열된 단원을 완료했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-137">This tutorial assumes that you have finished the lessons listed above.</span></span>

## <a name="introduction-to-classes"></a><span data-ttu-id="4dcd3-138">클래스 소개</span><span class="sxs-lookup"><span data-stu-id="4dcd3-138">Introduction to classes</span></span>

<span data-ttu-id="4dcd3-139">[클래스 소개](introduction-to-classes.md)에서는 콘솔 애플리케이션을 빌드하고 C# 언어의 일부인 기본 개체 지향 기능을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-139">In [Introduction to classes](introduction-to-classes.md), you'll build a console application and see the basic object-oriented features that are part of the C# language.</span></span> <span data-ttu-id="4dcd3-140">C# 자습서에 대한 마지막 소개입니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-140">This is the final introduction to C# tutorial.</span></span> <span data-ttu-id="4dcd3-141">이 자습서는 자체 로컬 개발 환경 및 .NET을 사용하여 컴퓨터에서만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4dcd3-141">It's only available to run on your machine, using your own local development environment and .NET.</span></span>
