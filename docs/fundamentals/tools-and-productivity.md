---
title: .NET의 도구 및 진단
author: IEvangelist
description: .NET 개발자가 사용할 수 있는 개발 및 진단 도구에 대해 알아봅니다.
ms.author: dapine
ms.date: 10/21/2020
ms.topic: overview
ms.openlocfilehash: 07c1a161a0bb429403db6852fe77749d83c19ec0
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "96593835"
---
# <a name="tools-and-diagnostics-in-net"></a><span data-ttu-id="3ce2d-103">.NET의 도구 및 진단</span><span class="sxs-lookup"><span data-stu-id="3ce2d-103">Tools and diagnostics in .NET</span></span>

<span data-ttu-id="3ce2d-104">이 문서에서는 .NET 개발자가 사용할 수 있는 다양 한 도구에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-104">In this article, you'll learn about the various tools available to .NET developers.</span></span> <span data-ttu-id="3ce2d-105">.NET을 사용 하면 CLI (명령줄 인터페이스)를 포함 하는 강력한 SDK (소프트웨어 개발 키트)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-105">With .NET, you have a robust software development kit (SDK) that includes a command-line interface (CLI).</span></span> <span data-ttu-id="3ce2d-106">.NET CLI는 전체에서 다양 한 기능을 사용할 수 있도록 합니다. NET ready Ide (통합 개발 환경)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-106">The .NET CLI enables many of the features throughout the .NET-ready integrated development environments (IDEs).</span></span> <span data-ttu-id="3ce2d-107">이 문서에서는 성능 문제를 진단 하기 위한 .NET CLI 도구, 메모리 누수, 높은 CPU, 교착 상태 및 코드 분석을 위한 도구 지원과 같은 생산성 기능에도 리소스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-107">This article also provides resources to productivity capabilities, such as .NET CLI tools for diagnosing performance issues, memory leaks, high CPU, deadlocks, and tooling support for code analysis.</span></span>

## <a name="net-sdk"></a><span data-ttu-id="3ce2d-108">.NET SDK</span><span class="sxs-lookup"><span data-stu-id="3ce2d-108">.NET SDK</span></span>

<span data-ttu-id="3ce2d-109">.Net SDK에는 .NET 런타임과 .NET CLI가 모두 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-109">The .NET SDK includes both the .NET Runtime and the .NET CLI.</span></span> <span data-ttu-id="3ce2d-110">Windows, Linux, macOS 또는 Docker 용 [.NET SDK](https://dotnet.microsoft.com/download) 를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-110">You can download the [.NET SDK](https://dotnet.microsoft.com/download) for Windows, Linux, macOS, or Docker.</span></span> <span data-ttu-id="3ce2d-111">자세한 내용은 [.NET SDK 개요](../core/sdk.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-111">For more information, see [.NET SDK overview](../core/sdk.md).</span></span>

## <a name="net-cli"></a><span data-ttu-id="3ce2d-112">.NET CLI</span><span class="sxs-lookup"><span data-stu-id="3ce2d-112">.NET CLI</span></span>

<span data-ttu-id="3ce2d-113">.NET CLI는 .NET 응용 프로그램을 개발, 빌드, 실행 및 게시 하기 위한 플랫폼 간 도구 체인.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-113">The .NET CLI is a cross-platform toolchain for developing, building, running, and publishing .NET applications.</span></span> <span data-ttu-id="3ce2d-114">.NET CLI는 .NET SDK에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-114">The .NET CLI is included with the .NET SDK.</span></span> <span data-ttu-id="3ce2d-115">자세한 내용은 [.NET CLI 개요](../core/tools/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-115">For more information, see [.NET CLI overview](../core/tools/index.md).</span></span>

## <a name="ides"></a><span data-ttu-id="3ce2d-116">IDE</span><span class="sxs-lookup"><span data-stu-id="3ce2d-116">IDEs</span></span>

<span data-ttu-id="3ce2d-117">[Visual Studio Code](https://code.visualstudio.com/docs), [Visual Studio](/visualstudio/windows)또는 [Mac용 Visual Studio](/visualstudio/mac)에서 .net 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-117">You can write .NET applications in [Visual Studio Code](https://code.visualstudio.com/docs), [Visual Studio](/visualstudio/windows), or [Visual Studio for Mac](/visualstudio/mac).</span></span> <span data-ttu-id="3ce2d-118">클라우드 기반 개발 환경에 대 한 자세한 내용은 [Visual Studio Codespaces](/visualstudio/codespaces/overview/what-is-vsonline)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-118">For information on cloud-powered development environments, see [Visual Studio Codespaces](/visualstudio/codespaces/overview/what-is-vsonline).</span></span>

## <a name="additional-tools"></a><span data-ttu-id="3ce2d-119">추가 도구</span><span class="sxs-lookup"><span data-stu-id="3ce2d-119">Additional tools</span></span>

<span data-ttu-id="3ce2d-120">.NET은 보다 일반적인 도구 외에도 특정 시나리오에 대 한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-120">In addition to the more common tools, .NET also provides tools for specific scenarios.</span></span> <span data-ttu-id="3ce2d-121">일부 사용 사례에는 .NET SDK 또는 .NET 런타임을 제거 하 고, WCF (Windows Communication Foundation) 메타 데이터를 검색 하 고, 프록시 소스 코드를 생성 하 고, XML을 serialize 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-121">Some of the use cases include uninstalling the .NET SDK or the .NET Runtime, retrieving Windows Communication Foundation (WCF) metadata, generating proxy source code, and serializing XML.</span></span> <span data-ttu-id="3ce2d-122">자세한 내용은 [.net 추가 도구 개요](../core/additional-tools/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-122">For more information, see [.NET additional tools overview](../core/additional-tools/index.md).</span></span>

## <a name="diagnostics-and-instrumentation"></a><span data-ttu-id="3ce2d-123">진단 및 계측</span><span class="sxs-lookup"><span data-stu-id="3ce2d-123">Diagnostics and instrumentation</span></span>

<span data-ttu-id="3ce2d-124">.NET 개발자는 일반적인 성능 진단 도구를 사용 하 여 응용 프로그램 성능을 모니터링 하 고, 추적을 사용 하 여 앱을 프로 파일링 하 고, 성능 메트릭을 수집 하 고, 덤프 파일을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-124">As a .NET developer, you can make use of common performance diagnostic tools to monitor app performance, profile apps with tracing, collect performance metrics, and analyze dump files.</span></span> <span data-ttu-id="3ce2d-125">이벤트 카운터를 사용 하 여 성능 메트릭을 수집 하 고 프로 파일링 도구를 사용 하 여 앱의 작동 방식에 대 한 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-125">You collect performance metrics with event counters, and use profiling tools to gain insights into how apps perform.</span></span> <span data-ttu-id="3ce2d-126">자세한 내용은 [.net 진단 도구](../core/diagnostics/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-126">For more information, see [.NET diagnostics tools](../core/diagnostics/index.md).</span></span>

## <a name="code-analysis"></a><span data-ttu-id="3ce2d-127">코드 분석</span><span class="sxs-lookup"><span data-stu-id="3ce2d-127">Code analysis</span></span>

<span data-ttu-id="3ce2d-128">Roslyn (.NET 컴파일러 플랫폼) 분석기는 c # 또는 Visual Basic 코드에서 코드 품질 및 코드 스타일 문제를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-128">The .NET compiler platform (Roslyn) analyzers inspect your C# or Visual Basic code for code quality and code style issues.</span></span> <span data-ttu-id="3ce2d-129">자세한 내용은 [.net 소스 코드 분석 개요](code-analysis/overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3ce2d-129">For more information, see [.NET source code analysis overview](code-analysis/overview.md).</span></span>
