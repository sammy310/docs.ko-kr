---
title: 진단 도구 개요 - .NET Core
description: .NET Core 애플리케이션을 진단하는 데 사용할 수 있는 도구 및 기술에 대한 개요입니다.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: e97acccbe3bdd577ee600cefb9f1f0528d3c1ac0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538529"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="bc1e7-103">.NET Core에서 사용할 수 있는 진단 도구는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="bc1e7-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="bc1e7-104">소프트웨어가 항상 예상한 대로 작동하지는 않지만 .NET Core에는 이러한 문제를 빠르고 효과적으로 진단할 수 있는 도구 및 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="bc1e7-105">이 문서는 필요한 다양한 도구를 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="bc1e7-106">관리형 디버거</span><span class="sxs-lookup"><span data-stu-id="bc1e7-106">Managed debuggers</span></span>

<span data-ttu-id="bc1e7-107">[관리형 디버거](managed-debuggers.md)를 사용하여 프로그램과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="bc1e7-108">일시 중지, 증분 실행, 검사 및 다시 시작은 코드 동작에 대한 인사이트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="bc1e7-109">디버거는 쉽게 재현될 수 있는 기능 문제를 진단하는 데 사용되는 첫 번째 선택 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="bc1e7-110">로깅 및 추적</span><span class="sxs-lookup"><span data-stu-id="bc1e7-110">Logging and tracing</span></span>

<span data-ttu-id="bc1e7-111">[로깅 및 추적](logging-tracing.md)은 관련된 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="bc1e7-112">계측 코드를 참조하여 로그 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="bc1e7-113">파일에는 프로그램에서 수행하는 작업에 대한 세부 정보가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-113">The files record the details of what a program does.</span></span> <span data-ttu-id="bc1e7-114">해당 세부 정보를 사용하여 가장 복잡한 문제를 진단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="bc1e7-115">타임스탬프와 결합할 경우 이러한 기술은 성능 조사에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="bc1e7-116">단위 테스트</span><span class="sxs-lookup"><span data-stu-id="bc1e7-116">Unit testing</span></span>

<span data-ttu-id="bc1e7-117">[유닛 테스트](../testing/index.md)는 고품질 소프트웨어의 연속 통합 및 배포를 위한 핵심 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="bc1e7-118">단위 테스트는 항목을 중단할 때 조기 경고를 제공하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="bc1e7-119">Linux 덤프 디버그</span><span class="sxs-lookup"><span data-stu-id="bc1e7-119">Debug Linux dumps</span></span>

<span data-ttu-id="bc1e7-120">[Linux 덤프 디버그](debug-linux-dumps.md)는 Linux에서 덤프를 수집 및 분석하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-120">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="bc1e7-121">.NET Core 진단 전역 도구</span><span class="sxs-lookup"><span data-stu-id="bc1e7-121">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="bc1e7-122">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="bc1e7-122">dotnet-counters</span></span>

<span data-ttu-id="bc1e7-123">[dotnet-counters](dotnet-counters.md)는 1단계 상태 모니터링 및 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-123">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="bc1e7-124"><xref:System.Diagnostics.Tracing.EventCounter>API를 통해 게시된 성능 카운터 값을 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-124">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="bc1e7-125">예를 들어 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 발생률과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-125">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="bc1e7-126">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="bc1e7-126">dotnet-dump</span></span>

<span data-ttu-id="bc1e7-127">[dotnet dump](dotnet-dump.md) 도구는 네이티브 디버거 없이 Windows 및 Linux 코어 덤프를 수집하 고 분석하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-127">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="bc1e7-128">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="bc1e7-128">dotnet-gcdump</span></span>

<span data-ttu-id="bc1e7-129">[dotnet-gcdump](dotnet-gcdump.md) 도구로 라이브 .NET 프로세스의 GC(가비지 수집기) 덤프를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-129">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="bc1e7-130">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="bc1e7-130">dotnet-trace</span></span>

<span data-ttu-id="bc1e7-131">.NET Core에는 진단 데이터가 노출되는 `EventPipe`라고 하는 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-131">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="bc1e7-132">[dotnet-trace](dotnet-trace.md) 도구를 사용하면 앱에서 흥미로운 프로파일링 데이터를 사용하여 앱 속도가 느려지는 근본 원인이 되는 시나리오를 찾는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-132">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="bc1e7-133">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="bc1e7-133">dotnet-symbol</span></span>

<span data-ttu-id="bc1e7-134">[dotnet-symbol](dotnet-symbol.md)은 코어 덤프 또는 미니덤프를 여는 데 필요한 파일(기호, DAC/DBI, 호스트 파일 등)을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-134">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="bc1e7-135">다른 컴퓨터에서 캡처된 덤프 파일을 디버깅하기 위한 기호 및 모듈이 필요하면 이 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-135">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="bc1e7-136">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="bc1e7-136">dotnet-sos</span></span>

<span data-ttu-id="bc1e7-137">[dotnet-sos](dotnet-sos.md)는 Linux 또는 MacOS(또는 이전 디버깅 도구를 사용할 경우 Windows)에 [SOS 디버깅 확장](../../framework/tools/sos-dll-sos-debugging-extension.md)을 설치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-137">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="bc1e7-138">.NET Core 진단 자습서</span><span class="sxs-lookup"><span data-stu-id="bc1e7-138">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="bc1e7-139">메모리 누수 디버그</span><span class="sxs-lookup"><span data-stu-id="bc1e7-139">Debug a memory leak</span></span>

<span data-ttu-id="bc1e7-140">[자습서: 메모리 누수 디버그](debug-memory-leak.md)에서는 메모리 누수를 검색하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-140">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="bc1e7-141">[dotnet-counters](dotnet-counters.md) 도구는 누수를 확인하는 데 사용되고, [dotnet-dump](dotnet-dump.md) 도구는 누수를 진단하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-141">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="bc1e7-142">높은 CPU 사용량 디버그</span><span class="sxs-lookup"><span data-stu-id="bc1e7-142">Debug high CPU usage</span></span>

<span data-ttu-id="bc1e7-143">[자습서: 높은 CPU 사용량 디버그](debug-highcpu.md)는 높은 CPU 사용량을 조사하는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-143">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="bc1e7-144">[dotnet-counters](dotnet-counters.md) 도구를 사용하여 높은 CPU 사용량을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-144">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="bc1e7-145">그런 다음 [성능 분석 유틸리티(`dotnet-trace`)](dotnet-trace.md) 또는 Linux `perf`를 사용하여 CPU 사용량 프로필을 수집하고 보는 과정을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-145">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="bc1e7-146">교착 상태 디버그</span><span class="sxs-lookup"><span data-stu-id="bc1e7-146">Debug deadlock</span></span>

<span data-ttu-id="bc1e7-147">[자습서: 교착 상태 디버그](debug-deadlock.md)는 [dotnet-dump](dotnet-dump.md) 도구를 사용하여 스레드와 잠금을 조사하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e7-147">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>
