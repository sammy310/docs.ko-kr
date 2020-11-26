---
title: EventPipe 개요
description: EventPipe에 대해 알아보고 성능 문제를 진단하기 위해 .NET 애플리케이션 추적에 이를 사용하는 방법을 알아봅니다.
ms.date: 11/09/2020
ms.topic: overview
ms.openlocfilehash: 00378c4f409b307afa9183e40de6078cdafd3ae7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94820620"
---
# <a name="eventpipe"></a><span data-ttu-id="8f600-103">EventPipe</span><span class="sxs-lookup"><span data-stu-id="8f600-103">EventPipe</span></span>

<span data-ttu-id="8f600-104">EventPipe는 ETW 또는 LTTng처럼 추적 데이터를 수집하는 데 사용할 수 있는 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-104">EventPipe is a runtime component that can be used to collect tracing data, similar to ETW or LTTng.</span></span> <span data-ttu-id="8f600-105">EventPipe의 목표는 .NET 개발자가 ETW 또는 LTTng처럼 플랫폼별 OS 네이티브 구성 요소를 사용하지 않고도 .NET 애플리케이션을 쉽게 추적할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-105">The goal of EventPipe is to allow .NET developers to easily trace their .NET applications without having to rely on platform-specific OS-native components such as ETW or LTTng.</span></span>

<span data-ttu-id="8f600-106">EventPipe는 많은 진단 도구에서 사용되는 메커니즘으로, 런타임에서 내보낸 이벤트뿐만 아니라 [EventSource](xref:System.Diagnostics.Tracing.EventSource)로 작성된 사용자 지정 이벤트를 사용하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-106">EventPipe is the mechanism behind many of the diagnostic tools and can be used for consuming events emitted by the runtime as well as custom events written with [EventSource](xref:System.Diagnostics.Tracing.EventSource).</span></span>

<span data-ttu-id="8f600-107">이 문서는 EventPipe에 대한 개요로, EventPipe를 사용하는 시기 및 방법, 요구 사항에 가장 적합하도록 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-107">This article is a high-level overview of EventPipe describing when and how to use EventPipe, and how to configure it to best suit your needs.</span></span>

## <a name="eventpipe-basics"></a><span data-ttu-id="8f600-108">EventPipe 기본 사항</span><span class="sxs-lookup"><span data-stu-id="8f600-108">EventPipe basics</span></span>

<span data-ttu-id="8f600-109">EventPipe는 Just-In-Time 컴파일러나 가비지 수집기와 같은 런타임 구성 요소에서 내보낸 이벤트와 라이브러리 및 사용자 코드에서 [EventSource](xref:System.Diagnostics.Tracing.EventSource) 인스턴스로 작성된 이벤트를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-109">EventPipe aggregates events emitted by runtime components - for example, the Just-In-Time compiler or the garbage collector - and events written from [EventSource](xref:System.Diagnostics.Tracing.EventSource) instances in the libraries and user code.</span></span>

<span data-ttu-id="8f600-110">그런 다음 이벤트를 직렬화하고 파일에 직접 쓰거나 out-of-process에서 진단 포트를 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-110">The events are then serialized and can be written directly to a file or consumed through a Diagnostics Port from out-of-proces.</span></span> <span data-ttu-id="8f600-111">Windows에서 진단 포트는 `NamedPipe`로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-111">On Windows, Diagnostic Ports are implemented as `NamedPipe`s.</span></span> <span data-ttu-id="8f600-112">Linux 또는 macOS와 같은 Windows가 아닌 플랫폼에서는 Unix 도메인 소켓을 사용하여 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-112">On non-Windows platforms, such as Linux or macOS, it is implemented using Unix Domain Sockets.</span></span> <span data-ttu-id="8f600-113">진단 포트 및 사용자 지정 프로세스 간 통신 프로토콜을 통해 상호 작용하는 방법에 대한 자세한 내용은 [진단 IPC 프로토콜 설명서](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f600-113">For more information about the Diagnostics Port and how to interact with it via its custom inter-process communication protocol, see the [diagnostics IPC protocol documentation](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md).</span></span>

<span data-ttu-id="8f600-114">EventPipe는 직렬화된 이벤트를 `.nettrace` 파일 형식으로 기록하며, 진단 포트를 통해 스트림으로 기록하거나 파일에 직접 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-114">EventPipe then writes the serialized events in the `.nettrace` file format, either as a stream via Diagnostic Ports or directly to a file.</span></span> <span data-ttu-id="8f600-115">EventPipe serialization 형식에 대한 자세한 내용은 [EventPipe format documentation](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md)(EventPipe 형식 설명서)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f600-115">To learn more about the EventPipe serialization format, refer to the [EventPipe format documentation](https://github.com/microsoft/perfview/blob/master/src/TraceEvent/EventPipe/EventPipeFormat.md).</span></span>

## <a name="eventpipe-vs-etwlttng"></a><span data-ttu-id="8f600-116">EventPipe 및 ETW/LTTng</span><span class="sxs-lookup"><span data-stu-id="8f600-116">EventPipe vs. ETW/LTTng</span></span>

<span data-ttu-id="8f600-117">EventPipe는 .NET 런타임(CoreCLR)의 일부이며 .NET Core에서 지원하는 모든 플랫폼에서 동일한 방식으로 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-117">EventPipe is part of the .NET runtime (CoreCLR) and is designed to work the same way across all the platforms .NET Core supports.</span></span> <span data-ttu-id="8f600-118">따라서 `dotnet-counters`, `dotnet-gcdump`, `dotnet-trace` 같은 EventPipe 기반 추적 도구가 여러 플랫폼에서 원활하게 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-118">This allows tracing tools based on EventPipe, such as `dotnet-counters`, `dotnet-gcdump`, and `dotnet-trace`, to work seamlessly across platforms.</span></span>

<span data-ttu-id="8f600-119">그러나 EventPipe는 런타임 기본 제공 구성 요소이기 때문에 범위는 관리 코드와 런타임 자체로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-119">However, because EventPipe is a runtime built-in component, its scope is limited to managed code and the runtime itself.</span></span> <span data-ttu-id="8f600-120">EventPipe는 네이티브 코드 스택 확인이나 다양한 커널 이벤트 가져오기와 같은 하위 수준 이벤트를 추적하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-120">EventPipe cannot be used for tracking some lower-level events, such as resolving native code stack or getting various kernel events.</span></span> <span data-ttu-id="8f600-121">앱에서 C/C++ interop을 사용하거나 C++로 작성된 런타임 자체를 추적하거나 커널 이벤트(즉, 네이티브 스레드 컨텍스트 전환 이벤트)가 필요한 앱의 동작을 심층 진단하려는 경우 ETW 또는 [perf/LTTng](./trace-perfcollect-lttng.md)를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-121">If you use C/C++ interop in your app or you want to trace the runtime itself (which is written in C++), or want deeper diagnostics into the behavior of the app that requires kernel events (that is, native-thread context-switching events) you should use ETW or [perf/LTTng](./trace-perfcollect-lttng.md).</span></span>

<span data-ttu-id="8f600-122">EventPipe와 ETW/LTTng의 또 다른 주요 차이점은 관리자/루트 권한 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-122">Another major difference between EventPipe and ETW/LTTng is admin/root privilege requirement.</span></span> <span data-ttu-id="8f600-123">ETW 또는 LTTng를 사용하여 애플리케이션을 추적하려면 관리자/루트여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-123">To trace an application using ETW or LTTng you need to be an admin/root.</span></span> <span data-ttu-id="8f600-124">추적 프로그램(예: `dotnet-trace`)이 애플리케이션을 시작한 사용자와 동일한 사용자로 실행되는 한 EventPipe를 사용하여 애플리케이션을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-124">Using EventPipe, you can trace applications as long as the tracer (for example, `dotnet-trace`) is run as the same user as the user that launched the application.</span></span>

<span data-ttu-id="8f600-125">다음 표에서는 EventPipe와 ETW/LTTng의 차이점을 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-125">The following table is a summary of the differences between EventPipe and ETW/LTTng.</span></span>

|<span data-ttu-id="8f600-126">기능</span><span class="sxs-lookup"><span data-stu-id="8f600-126">Feature</span></span>|<span data-ttu-id="8f600-127">EventPipe</span><span class="sxs-lookup"><span data-stu-id="8f600-127">EventPipe</span></span>|<span data-ttu-id="8f600-128">ETW</span><span class="sxs-lookup"><span data-stu-id="8f600-128">ETW</span></span>|<span data-ttu-id="8f600-129">LTTng</span><span class="sxs-lookup"><span data-stu-id="8f600-129">LTTng</span></span>|
|-------|---------|---|-----------|
|<span data-ttu-id="8f600-130">플랫폼 간</span><span class="sxs-lookup"><span data-stu-id="8f600-130">Cross-platform</span></span>|<span data-ttu-id="8f600-131">예</span><span class="sxs-lookup"><span data-stu-id="8f600-131">Yes</span></span>|<span data-ttu-id="8f600-132">아니요(Windows에서만)</span><span class="sxs-lookup"><span data-stu-id="8f600-132">No (only on Windows)</span></span>|<span data-ttu-id="8f600-133">아니요(지원되는 Linux 배포판에서만)</span><span class="sxs-lookup"><span data-stu-id="8f600-133">No (only on supported Linux distros)</span></span>|
|<span data-ttu-id="8f600-134">관리자/루트 권한 필요</span><span class="sxs-lookup"><span data-stu-id="8f600-134">Require admin/root privilege</span></span>|<span data-ttu-id="8f600-135">아니요</span><span class="sxs-lookup"><span data-stu-id="8f600-135">No</span></span>|<span data-ttu-id="8f600-136">예</span><span class="sxs-lookup"><span data-stu-id="8f600-136">Yes</span></span>|<span data-ttu-id="8f600-137">예</span><span class="sxs-lookup"><span data-stu-id="8f600-137">Yes</span></span>|
|<span data-ttu-id="8f600-138">OS/커널 이벤트를 가져올 수 있음</span><span class="sxs-lookup"><span data-stu-id="8f600-138">Can get OS/kernel events</span></span>|<span data-ttu-id="8f600-139">아니요</span><span class="sxs-lookup"><span data-stu-id="8f600-139">No</span></span>|<span data-ttu-id="8f600-140">예</span><span class="sxs-lookup"><span data-stu-id="8f600-140">Yes</span></span>|<span data-ttu-id="8f600-141">예</span><span class="sxs-lookup"><span data-stu-id="8f600-141">Yes</span></span>|
|<span data-ttu-id="8f600-142">기본 호출 스택을 확인할 수 있음</span><span class="sxs-lookup"><span data-stu-id="8f600-142">Can resolve native callstacks</span></span>|<span data-ttu-id="8f600-143">아니요</span><span class="sxs-lookup"><span data-stu-id="8f600-143">No</span></span>|<span data-ttu-id="8f600-144">예</span><span class="sxs-lookup"><span data-stu-id="8f600-144">Yes</span></span>|<span data-ttu-id="8f600-145">예</span><span class="sxs-lookup"><span data-stu-id="8f600-145">Yes</span></span>|

## <a name="use-eventpipe-to-trace-your-net-application"></a><span data-ttu-id="8f600-146">EventPipe를 사용하여 .NET 애플리케이션 추적</span><span class="sxs-lookup"><span data-stu-id="8f600-146">Use EventPipe to trace your .NET application</span></span>

<span data-ttu-id="8f600-147">EventPipe를 사용하여 다음과 같은 여러 가지 방법으로 .NET 애플리케이션을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-147">You can use EventPipe to trace your .NET application in many ways:</span></span>

* <span data-ttu-id="8f600-148">EventPipe를 기반으로 빌드되는 [진단 도구](#tools-that-use-eventpipe) 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-148">Use one of the [diagnostics tools](#tools-that-use-eventpipe) that are built on top of EventPipe.</span></span>

* <span data-ttu-id="8f600-149">[Microsoft.Diagnostics.NETCore.Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md) 라이브러리를 사용하여 EventPipe 세션을 구성하고 시작하는 고유한 도구를 직접 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-149">Use [Microsoft.Diagnostics.NETCore.Client](https://github.com/dotnet/diagnostics/blob/master/documentation/diagnostics-client-library-instructions.md) library to write your own tool to configure and start EventPipe sessions yourself.</span></span>

* <span data-ttu-id="8f600-150">[환경 변수](#trace-using-environment-variables)를 사용하여 EventPipe를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-150">Use [environment variables](#trace-using-environment-variables) to start EventPipe.</span></span>

<span data-ttu-id="8f600-151">EventPipe 이벤트를 포함하는 `nettrace` 파일을 생성한 후에는 [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) 또는 Visual Studio에서 파일을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-151">After you've produced a `nettrace` file that contains your EventPipe events, you can view the file in [`PerfView`](https://github.com/Microsoft/perfview#perfview-overview) or Visual Studio.</span></span> <span data-ttu-id="8f600-152">Windows가 아닌 플랫폼에서는 [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) 명령을 사용하여 `nettrace` 파일을 `speedscope` 또는 `Chromium` 추적 형식으로 변환하고 [`speedscope`](https://www.speedscope.app/) 또는 Chrome DevTools를 사용하여 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-152">On non-Windows platforms, you can convert the `nettrace` file to a `speedscope` or `Chromium` trace format by using [`dotnet-trace convert`](./dotnet-trace.md#dotnet-trace-convert) command and view it with [`speedscope`](https://www.speedscope.app/) or Chrome DevTools.</span></span>

<span data-ttu-id="8f600-153">[TraceEvent](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md)를 사용하여 프로그래밍 방식으로 EventPipe 추적을 분석할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-153">You can also analyze EventPipe traces programmatically with [TraceEvent](https://github.com/Microsoft/perfview/blob/master/documentation/TraceEvent/TraceEventLibrary.md).</span></span>

### <a name="tools-that-use-eventpipe"></a><span data-ttu-id="8f600-154">EventPipe를 사용하는 도구</span><span class="sxs-lookup"><span data-stu-id="8f600-154">Tools that use EventPipe</span></span>

<span data-ttu-id="8f600-155">EventPipe를 사용하여 애플리케이션을 추적하는 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-155">This is the easiest way to use EventPipe to trace your application.</span></span> <span data-ttu-id="8f600-156">이러한 각 도구를 사용하는 방법에 대한 자세한 내용은 각 도구의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f600-156">To learn more about how to use each of these tools, refer to each tool's documentation.</span></span>

* <span data-ttu-id="8f600-157">[dotnet-counters](./dotnet-counters.md)를 사용하면 .NET 런타임 및 핵심 라이브러리에서 내보낸 다양한 메트릭뿐만 아니라 직접 작성할 수 있는 사용자 지정 메트릭을 모니터링하고 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-157">[dotnet-counters](./dotnet-counters.md) lets you monitor and collect various metrics emitted by the .NET runtime and core libraries, as well as custom metrics you can write.</span></span>

* <span data-ttu-id="8f600-158">[dotnet-gcdump](./dotnet-gcdump.md)를 사용하면 라이브 프로세스의 GC 힙 덤프를 수집하여 애플리케이션의 관리되는 힙을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-158">[dotnet-gcdump](./dotnet-gcdump.md) lets you collect GC heap dumps of live processes for analyzing an application's managed heap.</span></span>

* <span data-ttu-id="8f600-159">[dotnet-trace](./dotnet-trace.md)를 사용하면 애플리케이션의 추적을 수집하여 성능을 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-159">[dotnet-trace](./dotnet-trace.md) lets you collect traces of applications to analyze for performance.</span></span>

## <a name="trace-using-environment-variables"></a><span data-ttu-id="8f600-160">환경 변수를 사용하여 추적</span><span class="sxs-lookup"><span data-stu-id="8f600-160">Trace using environment variables</span></span>

<span data-ttu-id="8f600-161">EventPipe를 사용하는 기본 메커니즘은 `dotnet-trace` 또는 `Microsoft.Diagnostics.NETCore.Client` 라이브러리를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-161">The preferred mechanism for using EventPipe is to use `dotnet-trace` or the `Microsoft.Diagnostics.NETCore.Client` library.</span></span>

<span data-ttu-id="8f600-162">그러나 다음 환경 변수를 사용하여 앱에서 EventPipe 세션을 설정하고 파일에 직접 추적을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-162">However, you can use the following environment variables to set up an EventPipe session on an app and have it write the trace directly to a file.</span></span> <span data-ttu-id="8f600-163">추적을 중지하려면 애플리케이션을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-163">To stop tracing, exit the application.</span></span>

* <span data-ttu-id="8f600-164">`COMPlus_EnableEventPipe`: 파일에 직접 기록하는 EventPipe 세션을 시작하려면 `1`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-164">`COMPlus_EnableEventPipe`: Set this to `1` to start an EventPipe session that writes directly to a file.</span></span> <span data-ttu-id="8f600-165">기본값은 `0`입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-165">The default value is `0`.</span></span>

* <span data-ttu-id="8f600-166">`COMPlus_EventPipeOutputPath`: `COMPlus_EnableEventPipe`를 통해 실행하도록 구성된 경우 출력 EventPipe 추적 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-166">`COMPlus_EventPipeOutputPath`: The path to the output EventPipe trace file when it's configured to run via `COMPlus_EnableEventPipe`.</span></span> <span data-ttu-id="8f600-167">기본값은 `trace.nettrace`이며, 앱이 실행되는 것과 동일한 디렉터리에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-167">The default value is `trace.nettrace`, which will be created in the same directory that the app is running from.</span></span>

* <span data-ttu-id="8f600-168">`COMPlus_CircularBufferMB`: `COMPlus_EnableEventPipe`를 통해 실행하도록 구성된 경우 EventPipe에서 사용하는 내부 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-168">`COMPlus_CircularBufferMB`: The size of the internal buffer that is used by EventPipe when it's configured to run via `COMPlus_EnableEventPipe`.</span></span>

* <span data-ttu-id="8f600-169">`COMPlus_EventPipeConfig`: `COMPlus_EnableEventPipe`를 사용하여 EventPipe 세션을 시작할 때 EventPipe 세션 구성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-169">`COMPlus_EventPipeConfig`: Sets up the EventPipe session configuration when starting an EventPipe session with `COMPlus_EnableEventPipe`.</span></span>

  <span data-ttu-id="8f600-170">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-170">The syntax is as follows:</span></span>

  `<provider>:<keyword>:<level>`

  <span data-ttu-id="8f600-171">쉼표로 연결하여 여러 공급자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-171">You can also specify multiple providers by concatenating them with a comma:</span></span>

  `<provider1>:<keyword1>:<level1>,<provider2>:<keyword2>:<level2>`

  <span data-ttu-id="8f600-172">이 환경 변수는 설정되지 않았지만 `COMPlus_EnableEventPipe`에서 EventPipe를 사용하도록 설정한 경우 다음 키워드 및 수준으로 다음 공급자를 사용하도록 설정하여 추적을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8f600-172">If this environment variable is not set but EventPipe is enabled by `COMPlus_EnableEventPipe`, it will start tracing by enabling the following providers with the following keywords and levels:</span></span>

  - `Microsoft-Windows-DotNETRuntime:4c14fccbd:5`
  - `Microsoft-Windows-DotNETRuntimePrivate:4002000b:5`
  - `Microsoft-DotNETCore-SampleProfiler:0:5`
