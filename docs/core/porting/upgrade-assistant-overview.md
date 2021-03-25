---
title: .NET 업그레이드 도우미 개요
description: .NET Framework에서 마이그레이션하는 데 도움이 되고 프로젝트를 .NET 5로 업그레이드하는 .NET 업그레이드 도우미 도구를 소개합니다.
author: ardalis
ms.date: 03/08/2021
ms.openlocfilehash: c667cfce40d4f740bc23606826eb2a058643b7be
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604777"
---
# <a name="overview-of-the-net-upgrade-assistant"></a><span data-ttu-id="59354-103">.NET 업그레이드 도우미 개요</span><span class="sxs-lookup"><span data-stu-id="59354-103">Overview of the .NET Upgrade Assistant</span></span>

<span data-ttu-id="59354-104">현재 .NET Framework에서 실행되는 앱을 .NET 5로 이동해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-104">You might have apps that currently run on the .NET Framework that you're interested in porting to .NET 5.</span></span> <span data-ttu-id="59354-105">.NET 업그레이드 도우미 도구가 해당 프로세스를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-105">The .NET Upgrade Assistant tool can assist with this process.</span></span> <span data-ttu-id="59354-106">이 문서에서는 다음을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-106">This article provides:</span></span>

- <span data-ttu-id="59354-107">.NET 업그레이드 도우미의 개요</span><span class="sxs-lookup"><span data-stu-id="59354-107">An overview of the .NET Upgrade Assistant.</span></span>
- <span data-ttu-id="59354-108">.NET 업그레이드 도우미를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="59354-108">How to install the .NET Upgrade Assistant.</span></span>

## <a name="what-is-the-net-upgrade-assistant"></a><span data-ttu-id="59354-109">.NET 업그레이드 도우미란?</span><span class="sxs-lookup"><span data-stu-id="59354-109">What is the .NET Upgrade Assistant</span></span>

<span data-ttu-id="59354-110">.NET 업그레이드 도우미는 다양한 종류의 .NET Framework 앱에서 실행할 수 있는 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="59354-110">The .NET Upgrade Assistant is a command-line tool that can be run on different kinds of .NET Framework apps.</span></span> <span data-ttu-id="59354-111">해당 도구는 .NET Framework 앱을 .NET 5로 업그레이드하는 데 도움이 되도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-111">It's designed to assist with upgrading .NET Framework apps to .NET 5.</span></span> <span data-ttu-id="59354-112">도구를 실행한 후 **앱 마이그레이션을 완료하려면 더 많은 작업이 필요한 경우가 대부분** 입니다.</span><span class="sxs-lookup"><span data-stu-id="59354-112">After running the tool, **in most cases the app will require more effort to complete the migration**.</span></span> <span data-ttu-id="59354-113">도구는 마이그레이션을 완료하는 데 도움이 될 수 있는 분석기 설치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-113">The tool includes the installation of analyzers that can assist with completing the migration.</span></span>

<span data-ttu-id="59354-114">현재 해당 도구는 다음 .NET Framework 앱 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-114">Currently the tool supports the following .NET Framework app types:</span></span>

- <span data-ttu-id="59354-115">.NET Framework Windows Forms 앱</span><span class="sxs-lookup"><span data-stu-id="59354-115">.NET Framework Windows Forms apps</span></span>
- <span data-ttu-id="59354-116">.NET Framework WPF 앱</span><span class="sxs-lookup"><span data-stu-id="59354-116">.NET Framework WPF apps</span></span>
- <span data-ttu-id="59354-117">.NET Framework ASP.NET MVC 앱</span><span class="sxs-lookup"><span data-stu-id="59354-117">.NET Framework ASP.NET MVC apps</span></span>
- <span data-ttu-id="59354-118">.NET Framework 콘솔 앱</span><span class="sxs-lookup"><span data-stu-id="59354-118">.NET Framework console apps</span></span>
- <span data-ttu-id="59354-119">.NET Framework 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="59354-119">.NET Framework class libraries</span></span>

<span data-ttu-id="59354-120">.NET 업그레이드 도우미는 현재 시험판이며 빈번한 업데이트를 받고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-120">The .NET Upgrade Assistant is currently prerelease and is receiving frequent updates.</span></span> <span data-ttu-id="59354-121">도구를 사용하여 문제를 발견하는 경우 도구의 [GitHub 리포지토리](https://github.com/dotnet/upgrade-assistant)에서 문제를 신고하세요.</span><span class="sxs-lookup"><span data-stu-id="59354-121">If you discover problems using the tool, please report them in the tool's [GitHub repository](https://github.com/dotnet/upgrade-assistant).</span></span>

## <a name="how-to-install-the-net-upgrade-assistant"></a><span data-ttu-id="59354-122">.NET 업그레이드 도우미를 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="59354-122">How to install the .NET Upgrade Assistant</span></span>

<span data-ttu-id="59354-123">[시작 자습서](https://aka.ms/dotnet-upgrade-assistant-install)에서는 .NET 업그레이드 도우미를 설치하고 사용하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-123">The [Get Started tutorial](https://aka.ms/dotnet-upgrade-assistant-install) walks through how to install and use the .NET Upgrade Assistant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="59354-124">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="59354-124">Prerequisites</span></span>

1. <span data-ttu-id="59354-125">해당 도구는 MSBuild를 사용하여 프로젝트 파일 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-125">This tool uses MSBuild to work with project files.</span></span> <span data-ttu-id="59354-126">최신 버전의 MSBuild가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-126">Make sure that a recent version of MSBuild is installed.</span></span> <span data-ttu-id="59354-127">해당 작업을 손쉽게 수행하려면 [Visual Studio 2019를 설치](https://visualstudio.microsoft.com/downloads/)합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-127">An easy way to do this is to [install Visual Studio 2019](https://visualstudio.microsoft.com/downloads/).</span></span>
1. <span data-ttu-id="59354-128">해당 도구는 [try-convert](https://github.com/dotnet/try-convert)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-128">This tool depends on [try-convert](https://github.com/dotnet/try-convert).</span></span> <span data-ttu-id="59354-129">도구를 올바르게 실행하려면 프로젝트 파일을 새 SDK 스타일로 변환하기 위한 try-convert 도구를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59354-129">In order for the tool to run correctly, you must install the try-convert tool for converting project files to the new SDK style.</span></span> <span data-ttu-id="59354-130">이미 **try-convert** 가 설치되어 있는 경우 대신 업데이트해야 할 수 있습니다(**upgrade-assistant** 가 _0.7.212201_ 이상 버전을 사용하기 때문).</span><span class="sxs-lookup"><span data-stu-id="59354-130">If you already have **try-convert** installed, you may need to update it instead (since **upgrade-assistant** depends on version _0.7.212201_ or later)</span></span>
    1. <span data-ttu-id="59354-131">try-convert를 설치하려면: `dotnet tool install -g try-convert`</span><span class="sxs-lookup"><span data-stu-id="59354-131">To install try-convert: `dotnet tool install -g try-convert`</span></span>
    1. <span data-ttu-id="59354-132">try-convert를 업데이트하려면: `dotnet tool update -g try-convert`</span><span class="sxs-lookup"><span data-stu-id="59354-132">To update try-convert: `dotnet tool update -g try-convert`</span></span>

### <a name="installation-steps"></a><span data-ttu-id="59354-133">설치 단계</span><span class="sxs-lookup"><span data-stu-id="59354-133">Installation steps</span></span>

<span data-ttu-id="59354-134">이 도구는 다음을 실행하여 .NET CLI 도구로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-134">The tool can be installed as a .NET CLI tool by running:</span></span>

```dotnet
dotnet tool install -g upgrade-assistant
```

<span data-ttu-id="59354-135">마찬가지로 .NET 업그레이드 도우미가 .NET CLI 도구로 설치되기 때문에 다음을 실행하여 쉽게 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59354-135">Similarly, because the .NET Upgrade Assistant is installed as a .NET CLI tool, it can be easily updated by running:</span></span>

```dotnet
dotnet tool update -g upgrade-assistant
```

<span data-ttu-id="59354-136">자세한 설치 지침은 프로젝트의 [추가 정보](https://github.com/dotnet/upgrade-assistant)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59354-136">For detailed installation instructions, please refer to the project's [README](https://github.com/dotnet/upgrade-assistant).</span></span>

## <a name="see-also"></a><span data-ttu-id="59354-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="59354-137">See also</span></span>

- [<span data-ttu-id="59354-138">.NET 업그레이드 도우미를 사용하여 WPF 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="59354-138">Upgrade a WPF App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-wpf-framework.md)
- [<span data-ttu-id="59354-139">.NET 업그레이드 도우미를 사용하여 Windows Forms 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="59354-139">Upgrade a Windows Forms App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-winforms-framework.md)
- [<span data-ttu-id="59354-140">.NET 업그레이드 도우미를 사용하여 ASP.NET MVC 앱을 .NET 5로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="59354-140">Upgrade an ASP.NET MVC App to .NET 5 with the .NET Upgrade Assistant</span></span>](upgrade-assistant-aspnetmvc.md)
- [<span data-ttu-id="59354-141">.NET 업그레이드 도우미 GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="59354-141">.NET Upgrade Assistant GitHub Repository</span></span>](https://github.com/dotnet/upgrade-assistant)
