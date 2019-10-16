---
title: 진단 도구 개요 - .NET Core
description: .NET Core 애플리케이션을 진단하는 데 사용할 수 있는 도구 및 기술에 대한 개요입니다.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.topic: overview
ms.openlocfilehash: c0a45a1bfe866ad42890db576b5dd5098b1dbc3d
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318339"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="e91f2-103">.NET Core에서 사용할 수 있는 진단 도구는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="e91f2-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="e91f2-104">소프트웨어가 항상 예상한 대로 작동하지는 않지만 .NET Core에는 이러한 문제를 빠르고 효과적으로 진단할 수 있는 도구 및 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="e91f2-105">이 문서는 필요한 다양한 도구를 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="e91f2-106">관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="e91f2-106">Managed debuggers</span></span>

<span data-ttu-id="e91f2-107">[관리형 디버거](managed-debuggers.md)를 사용하여 프로그램과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="e91f2-108">일시 중지, 증분 실행, 검사 및 다시 시작은 코드 동작에 대한 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="e91f2-109">디버거는 쉽게 재현될 수 있는 기능 문제를 진단하는 데 사용되는 첫 번째 선택 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="e91f2-110">로깅 및 추적</span><span class="sxs-lookup"><span data-stu-id="e91f2-110">Logging and tracing</span></span>

<span data-ttu-id="e91f2-111">[로깅 및 추적](logging-tracing.md)은 관련된 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="e91f2-112">계측 코드를 참조하여 로그 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="e91f2-113">파일에는 프로그램에서 수행하는 작업에 대한 세부 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-113">The files record the details of what a program does.</span></span> <span data-ttu-id="e91f2-114">해당 세부 정보를 사용하여 가장 복잡한 문제를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="e91f2-115">타임스탬프와 결합할 경우 이러한 기술은 성능 조사에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="e91f2-116">단위 테스트</span><span class="sxs-lookup"><span data-stu-id="e91f2-116">Unit testing</span></span>

<span data-ttu-id="e91f2-117">[유닛 테스트](../testing/index.md)는 고품질 소프트웨어의 연속 통합 및 배포를 위한 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="e91f2-118">단위 테스트는 항목을 중단할 때 조기 경고를 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="net-core-dotnet-diagnostic-global-tools"></a><span data-ttu-id="e91f2-119">.NET Core dotnet 진단 전역 도구</span><span class="sxs-lookup"><span data-stu-id="e91f2-119">.NET Core dotnet diagnostic Global Tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="e91f2-120">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="e91f2-120">dotnet-counters</span></span>

<span data-ttu-id="e91f2-121">[dotnet-counters](dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-121">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="e91f2-122"><xref:System.Diagnostics.Tracing.EventCounter>API를 통해 게시된 성능 카운터 값을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-122">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="e91f2-123">예를 들어 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 발생률과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="e91f2-124">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="e91f2-124">dotnet-dump</span></span>

<span data-ttu-id="e91f2-125">[dotnet dump](dotnet-dump.md) 도구는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하 고 분석하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-125">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="e91f2-126">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="e91f2-126">dotnet-trace</span></span>

<span data-ttu-id="e91f2-127">.NET Core에는 진단 데이터가 노출되는 `EventPipe`라고 하는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-127">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="e91f2-128">[dotnet-trace](dotnet-trace.md) 도구를 사용하면 앱에서 흥미로운 프로파일링 데이터를 사용하여 앱 속도가 느려지는 근본 원인이 되는 시나리오를 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e91f2-128">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>
