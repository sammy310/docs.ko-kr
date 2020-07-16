---
title: .NET Core 소개 및 개요
description: .NET Core는 Windows, Linux, macOS 앱을 만들기 위한 모듈식 고성능 .NET 구현입니다. 시작하려면 .NET Core에 관해 알아봅니다.
author: richlander
ms.date: 03/26/2020
ms.custom: updateeachrelease
ms.openlocfilehash: b28ad965e54680e2e1134c389266741ade28084f
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226584"
---
# <a name="introduction-to-net-core"></a><span data-ttu-id="0cfa4-104">.NET Core 소개</span><span class="sxs-lookup"><span data-stu-id="0cfa4-104">Introduction to .NET Core</span></span>

<span data-ttu-id="0cfa4-105">[.NET Core](about.md)는 [오픈 소스](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT) 범용 개발 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform.</span></span> <span data-ttu-id="0cfa4-106">여러 프로그래밍 언어를 사용하여 x64, x86, ARM32, ARM64 프로세서의 Windows, macOS 및 Linux용 .NET Core 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-106">You can create .NET Core apps for Windows, macOS, and Linux for x64, x86, ARM32, and ARM64 processors using multiple programming languages.</span></span> <span data-ttu-id="0cfa4-107">[클라우드](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [클라이언트 UI](../desktop-wpf/overview/index.md) 및 [기계 학습](/dotnet/machine-learning/)용 프레임워크 및 API가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-107">Frameworks and APIs are provided for [cloud](/aspnet/core/), [IoT](/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), [client UI](../desktop-wpf/overview/index.md), and [machine learning](/dotnet/machine-learning/).</span></span>

<span data-ttu-id="0cfa4-108">[.NET Core SDK를 다운로드](https://dotnet.microsoft.com/download)하여 머신에서 .NET Core를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-108">[Download the .NET Core SDK](https://dotnet.microsoft.com/download) to try .NET Core on your machine.</span></span> <span data-ttu-id="0cfa4-109">최신 버전은 [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/)입니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-109">The latest version is [.NET Core 3.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-1/).</span></span>

## <a name="download-net-core"></a><span data-ttu-id="0cfa4-110">.NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="0cfa4-110">Download .NET Core</span></span>

<span data-ttu-id="0cfa4-111">다음 방법으로 .NET Core를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-111">You can get .NET Core in the following ways:</span></span>

* [<span data-ttu-id="0cfa4-112">Windows 및 macOS용 설치 프로그램</span><span class="sxs-lookup"><span data-stu-id="0cfa4-112">Installers for Windows and macOS</span></span>](https://dotnet.microsoft.com/download)
* [<span data-ttu-id="0cfa4-113">Linux 패키지</span><span class="sxs-lookup"><span data-stu-id="0cfa4-113">Linux packages</span></span>](https://docs.microsoft.com/dotnet/core/install/linux-package-managers)
* [<span data-ttu-id="0cfa4-114">Docker 컨테이너</span><span class="sxs-lookup"><span data-stu-id="0cfa4-114">Docker containers</span></span>](https://hub.docker.com/_/microsoft-dotnet-core/)
* [<span data-ttu-id="0cfa4-115">Zip 및 tarball</span><span class="sxs-lookup"><span data-stu-id="0cfa4-115">Zips and tarballs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* [<span data-ttu-id="0cfa4-116">스크립트 설치</span><span class="sxs-lookup"><span data-stu-id="0cfa4-116">Install scripts</span></span>](https://dotnet.microsoft.com/download/dotnet-core/scripts)
* [<span data-ttu-id="0cfa4-117">릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="0cfa4-117">Release notes</span></span>](https://github.com/dotnet/core/tree/master/release-notes)

## <a name="create-your-first-application"></a><span data-ttu-id="0cfa4-118">첫 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="0cfa4-118">Create your first application</span></span>

<span data-ttu-id="0cfa4-119">.NET Core SDK를 설치한 후 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-119">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="0cfa4-120">다음 명령을 사용하여 애플리케이션을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-120">Use the following commands to create and run an application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="0cfa4-121">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-121">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="contribute"></a><span data-ttu-id="0cfa4-122">참가</span><span class="sxs-lookup"><span data-stu-id="0cfa4-122">Contribute</span></span>

<span data-ttu-id="0cfa4-123">.NET Core는 개방형 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-123">.NET Core is an open platform.</span></span> <span data-ttu-id="0cfa4-124">누구나 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-124">Everyone is welcome to participate.</span></span>

* <span data-ttu-id="0cfa4-125">[개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/61/index.html)에서 제품 문제 및 질문을 게시하세요.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-125">File product issues and questions at [Developer Community](https://developercommunity.visualstudio.com/spaces/61/index.html).</span></span>
* <span data-ttu-id="0cfa4-126">제품 기여는 [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn) 또는 [aspnetcore](https://github.com/dotnet/aspnetcore)와 같은 프로젝트 리포지토리 중 하나에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-126">Product contributions should be made on one of the project repositories, such as [dotnet/runtime](https://github.com/dotnet/runtime), [dotnet/sdk](https://github.com/dotnet/sdk), [dotnet/rosyln](https://github.com/dotnet/roslyn), or [aspnetcore](https://github.com/dotnet/aspnetcore).</span></span> <span data-ttu-id="0cfa4-127">자세한 내용은 [.NET Core 리포지토리](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-127">For more information, see [.NET Core repos](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md).</span></span>

## <a name="support"></a><span data-ttu-id="0cfa4-128">고객 지원팀</span><span class="sxs-lookup"><span data-stu-id="0cfa4-128">Support</span></span>

<span data-ttu-id="0cfa4-129">.NET Core는 Windows, macOS 및 Linux의 경우 Microsoft에서 지원하며 Red Hat Enterprise Linux의 경우 Red Hat에서 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="0cfa4-129">.NET Core is supported by Microsoft on Windows, macOS, and Linux and by Red Hat on Red Hat Enterprise Linux.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0cfa4-130">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0cfa4-130">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0cfa4-131">.NET Core 자습서</span><span class="sxs-lookup"><span data-stu-id="0cfa4-131">.NET Core tutorials</span></span>](tutorials/index.md)

> [!div class="nextstepaction"]
> [<span data-ttu-id="0cfa4-132">브라우저에서 .NET Core 사용해 보기</span><span class="sxs-lookup"><span data-stu-id="0cfa4-132">Try .NET Core in your browser</span></span>](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)
