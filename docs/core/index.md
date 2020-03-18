---
title: .NET Core 가이드
description: .NET Core는 Windows, Linux, macOS 앱을 만들기 위한 모듈식 고성능 .NET 구현입니다. 시작하려면 .NET Core에 관해 알아봅니다.
author: richlander
ms.date: 12/04/2019
ms.custom: updateeachrelease
ms.openlocfilehash: 3db98d21a7cdc80d8a98b23782a81ffa37520937
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75740752"
---
# <a name="net-core-guide"></a><span data-ttu-id="aff94-104">.NET Core 가이드</span><span class="sxs-lookup"><span data-stu-id="aff94-104">.NET Core guide</span></span>

<span data-ttu-id="aff94-105">[.NET Core](about.md)는 Microsoft 및 [GitHub](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)의 .NET 커뮤니티에서 유지 관리하는 [오픈 소스](https://github.com/dotnet/core) 범용 개발 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-105">[.NET Core](about.md) is an [open-source](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), general-purpose development platform maintained by Microsoft and the .NET community on [GitHub](https://github.com/dotnet/core).</span></span> <span data-ttu-id="aff94-106">플랫폼 간으로 Windows, macOS 및 Linux를 지원하며 디바이스, 클라우드 및 IoT 애플리케이션을 빌드하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-106">It's cross-platform (supporting Windows, macOS, and Linux) and can be used to build device, cloud, and IoT applications.</span></span>

<span data-ttu-id="aff94-107">특성, 지원되는 언어 및 프레임워크, 키 API를 비롯한 .NET Core에 대한 자세한 내용은 [.NET Core 정보](about.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-107">See [About .NET Core](about.md) to learn more about .NET Core, including its characteristics, supported languages and frameworks, and key APIs.</span></span>

<span data-ttu-id="aff94-108">.NET Core 애플리케이션을 만드는 방법은 [.NET Core 자습서](tutorials/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-108">Check out [.NET Core Tutorials](tutorials/index.md) to learn how to create a simple .NET Core application.</span></span> <span data-ttu-id="aff94-109">첫 번째 앱을 만들고 실행하는 데 몇 분밖에 걸리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-109">It only takes a few minutes to get your first app up and running.</span></span> <span data-ttu-id="aff94-110">브라우저에서 .NET Core를 사용하려면 [C#의 숫자](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) 온라인 자습서를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-110">If you want to try .NET Core in your browser, look at the [Numbers in C#](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml) online tutorial.</span></span>

## <a name="download-net-core"></a><span data-ttu-id="aff94-111">.NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="aff94-111">Download .NET Core</span></span>

<span data-ttu-id="aff94-112">[.NET Core SDK](https://www.microsoft.com/net/download)를 다운로드하여 Windows, macOS 또는 Linux 머신에서 .NET Core를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-112">Download the [.NET Core SDK](https://www.microsoft.com/net/download) to try .NET Core on your Windows, macOS, or Linux machine.</span></span> <span data-ttu-id="aff94-113">Docker 컨테이너를 사용하려면 [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-113">And if you prefer to use Docker containers, visit the [.NET Core Docker Hub](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span>

<span data-ttu-id="aff94-114">다른 .NET Core 버전을 찾는 경우 [.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core)에서 모든 .NET Core 버전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-114">All .NET Core versions are available at [.NET Core Downloads](https://dotnet.microsoft.com/download/dotnet-core) if you're looking for another .NET Core version.</span></span>

## <a name="net-core-31"></a><span data-ttu-id="aff94-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="aff94-115">.NET Core 3.1</span></span>

<span data-ttu-id="aff94-116">최신 버전은 .NET Core 3.1입니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-116">The latest version is .NET Core 3.1.</span></span> <span data-ttu-id="aff94-117">3.1에는 .NET Core 3.0 대비 향상된 주요 기능은 없지만, .NET Core 3.1은 [장기적으로 지원되는 릴리스](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)입니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-117">3.1 includes minor improvements over .NET Core 3.0, however, .NET Core 3.1 is a [long-term supported release](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span> <span data-ttu-id="aff94-118">.NET Core 3.1 릴리스에 대한 자세한 내용은 [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md)(.NET Core 3.1의 새로운 기능)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="aff94-118">For more information about the .NET Core 3.1 release, see [What's new in .NET Core 3.1](./whats-new/dotnet-core-3-1.md).</span></span>

## <a name="create-your-first-application"></a><span data-ttu-id="aff94-119">첫 번째 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="aff94-119">Create your first application</span></span>

<span data-ttu-id="aff94-120">.NET Core SDK를 설치한 후 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-120">After installing the .NET Core SDK, open a command prompt.</span></span> <span data-ttu-id="aff94-121">다음 `dotnet` 명령을 입력하여 C# 애플리케이션을 만들고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-121">Enter the following `dotnet` commands to create and run a C# application:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="aff94-122">다음과 같은 내용이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-122">You should see the following output:</span></span>

```output
Hello World!
```

## <a name="support"></a><span data-ttu-id="aff94-123">지원</span><span class="sxs-lookup"><span data-stu-id="aff94-123">Support</span></span>

<span data-ttu-id="aff94-124">.NET Core는 [Microsoft에 의해](https://dotnet.microsoft.com/platform/support/policy) Windows, macOS 및 Linux에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-124">.NET Core is [supported by Microsoft](https://dotnet.microsoft.com/platform/support/policy), on Windows, macOS, and Linux.</span></span> <span data-ttu-id="aff94-125">보안 및 품질을 위해 1년에 여러 번, 일반적으로 매월 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-125">It's updated for security and quality several times a year, typically monthly.</span></span>

<span data-ttu-id="aff94-126">.NET Core 이진 배포는 Azure의 Microsoft가 유지 관리하는 서버에서 빌드 및 테스트되고 Microsoft 제품처럼 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-126">.NET Core binary distributions are built and tested on Microsoft-maintained servers in Azure and supported just like any Microsoft product.</span></span>

<span data-ttu-id="aff94-127">RHEL(Red Hat Enterprise Linux)에서 [Red Hat이 .NET Core를 지원](http://redhatloves.net/)합니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-127">[Red Hat supports .NET Core](http://redhatloves.net/) on Red Hat Enterprise Linux (RHEL).</span></span> <span data-ttu-id="aff94-128">Red Hat은 소스에서 .NET Core를 빌드하여 [Red Hat 소프트웨어 컬렉션](https://developers.redhat.com/products/softwarecollections/overview/)에서 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-128">Red Hat builds .NET Core from source and makes it available in the [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/).</span></span> <span data-ttu-id="aff94-129">Red Hat 및 Microsoft는 협력하여 RHEL에서 .NET Core가 잘 작동하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aff94-129">Red Hat and Microsoft collaborate to ensure that .NET Core works well on RHEL.</span></span>
