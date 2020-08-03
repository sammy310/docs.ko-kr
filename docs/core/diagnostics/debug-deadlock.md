---
title: 디버깅 교착 상태 - .NET Core
description: .NET Core의 잠금 문제를 디버깅하는 과정을 안내하는 자습서입니다.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 247521176297254180d794d4d4fc850f30e343b0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2020
ms.locfileid: "86926369"
---
# <a name="debug-a-deadlock-in-net-core"></a><span data-ttu-id="6d5d7-103">.NET Core의 교착 상태 디버그</span><span class="sxs-lookup"><span data-stu-id="6d5d7-103">Debug a deadlock in .NET Core</span></span>

<span data-ttu-id="6d5d7-104">**이 문서의 적용 대상: ✔️** .NET Core 3.1. SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="6d5d7-104">**This article applies to: ✔️** .NET Core 3.1 SDK and later versions</span></span>

<span data-ttu-id="6d5d7-105">이 자습서에서는 교착 상태 시나리오를 디버그하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-105">In this tutorial, you'll learn how to debug a deadlock scenario.</span></span> <span data-ttu-id="6d5d7-106">제공된 예제 [ASP.NET Core 웹앱](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) 소스 코드 리포지토리를 사용하면 교착 상태를 의도적으로 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-106">Using the provided example [ASP.NET Core web app](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) source code repository, you can cause a deadlock intentionally.</span></span> <span data-ttu-id="6d5d7-107">엔드포인트에서 중단 및 스레드 누적이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-107">The endpoint will experience a hang and thread accumulation.</span></span> <span data-ttu-id="6d5d7-108">다양한 도구를 사용하여 코어 덤프, 코어 덤프 분석 및 프로세스 추적과 같은 문제를 분석하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-108">You'll learn how you can use various tools to analyze the problem, such as core dumps, core dump analysis, and process tracing.</span></span>

<span data-ttu-id="6d5d7-109">이 자습서에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-109">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="6d5d7-110">앱 중단 조사</span><span class="sxs-lookup"><span data-stu-id="6d5d7-110">Investigate an app hang</span></span>
> - <span data-ttu-id="6d5d7-111">코어 덤프 파일 생성</span><span class="sxs-lookup"><span data-stu-id="6d5d7-111">Generate a core dump file</span></span>
> - <span data-ttu-id="6d5d7-112">덤프 파일의 프로세스 스레드 분석</span><span class="sxs-lookup"><span data-stu-id="6d5d7-112">Analyze process threads in the dump file</span></span>
> - <span data-ttu-id="6d5d7-113">호출 스택 및 동기화 블록 분석</span><span class="sxs-lookup"><span data-stu-id="6d5d7-113">Analyze callstacks and sync blocks</span></span>
> - <span data-ttu-id="6d5d7-114">교착 상태 진단 및 해결</span><span class="sxs-lookup"><span data-stu-id="6d5d7-114">Diagnose and solve a deadlock</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6d5d7-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d5d7-115">Prerequisites</span></span>

<span data-ttu-id="6d5d7-116">이 자습서에서는 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-116">The tutorial uses:</span></span>

- <span data-ttu-id="6d5d7-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="6d5d7-117">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version</span></span>
- <span data-ttu-id="6d5d7-118">시나리오를 트리거하는 [샘플 디버그 대상 - 웹앱](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-118">[Sample debug target - web app](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) to trigger the scenario</span></span>
- <span data-ttu-id="6d5d7-119">프로세스를 나열하는 [dotnet-trace](dotnet-trace.md)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-119">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="6d5d7-120">덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-120">[dotnet-dump](dotnet-dump.md) to collect, and analyze a dump file</span></span>

## <a name="core-dump-generation"></a><span data-ttu-id="6d5d7-121">코어 덤프 생성</span><span class="sxs-lookup"><span data-stu-id="6d5d7-121">Core dump generation</span></span>

<span data-ttu-id="6d5d7-122">애플리케이션 무응답 문제를 조사하기 위해 코어 덤프 또는 메모리 덤프를 사용하면 경합 문제가 있을 수 있는 가능한 모든 잠금과 해당 스레드의 상태를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-122">To investigate application unresponsiveness, a core dump or memory dump allows you to inspect the state of its threads and any possible locks that may have contention issues.</span></span> <span data-ttu-id="6d5d7-123">샘플 루트 디렉터리에서 다음 명령을 사용하여 [샘플 디버그](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-123">Run the [sample debug](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios) application using the following command from the sample root directory:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="6d5d7-124">프로세스 ID를 찾으려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-124">To find the process ID, use the following command:</span></span>

```dotnetcli
dotnet-trace ps
```

<span data-ttu-id="6d5d7-125">명령 출력에서 프로세스 ID를 기록해 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-125">Take note of the process ID from your command output.</span></span> <span data-ttu-id="6d5d7-126">기존 프로세스 ID는 `4807`이었지만 사용자의 프로세스 ID는 다를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-126">Our process ID was `4807`, but yours will be different.</span></span> <span data-ttu-id="6d5d7-127">샘플 사이트의 API 엔드포인트인 다음 URL로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-127">Navigate to the following URL, which is an API endpoint on the sample site:</span></span>

[https://localhost:5001/api/diagscenario/deadlock](https://localhost:5001/api/diagscenario/deadlock)

<span data-ttu-id="6d5d7-128">사이트에 대한 API 요청이 중단되고 응답하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-128">The API request to the site will hang and not respond.</span></span> <span data-ttu-id="6d5d7-129">약 10-15초 동안 요청이 실행되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-129">Let the request run for about 10-15 seconds.</span></span> <span data-ttu-id="6d5d7-130">다음 명령을 실행하여 코어 덤프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-130">Then create the core dump using the following command:</span></span>

### <a name="linux"></a>[<span data-ttu-id="6d5d7-131">Linux</span><span class="sxs-lookup"><span data-stu-id="6d5d7-131">Linux</span></span>](#tab/linux)

```bash
sudo dotnet-dump collect -p 4807
```

### <a name="windows"></a>[<span data-ttu-id="6d5d7-132">Windows</span><span class="sxs-lookup"><span data-stu-id="6d5d7-132">Windows</span></span>](#tab/windows)

```console
dotnet-dump collect -p 4807
```

---

## <a name="analyze-the-core-dump"></a><span data-ttu-id="6d5d7-133">코어 덤프 분석</span><span class="sxs-lookup"><span data-stu-id="6d5d7-133">Analyze the core dump</span></span>

<span data-ttu-id="6d5d7-134">코어 덤프 분석을 시작하려면 다음 `dotnet-dump analyze` 명령을 사용하여 코어 덤프를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-134">To start the core dump analysis, open the core dump using the following `dotnet-dump analyze` command.</span></span> <span data-ttu-id="6d5d7-135">인수는 이전에 수집된 코어 덤프 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-135">The argument is the path to the core dump file that was collected earlier.</span></span>

```dotnetcli
dotnet-dump analyze  ~/.dotnet/tools/core_20190513_143916
```

<span data-ttu-id="6d5d7-136">잠재적 중단을 살펴보고 있으므로 이제 프로세스의 스레드 활동을 전반적으로 파악하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-136">Since you're looking at a potential hang, you want an overall feel for the thread activity in the process.</span></span> <span data-ttu-id="6d5d7-137">아래와 같이 `threads` 명령을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-137">You can use the `threads` command as shown below:</span></span>

```console
> threads
*0 0x1DBFF (121855)
 1 0x1DC01 (121857)
 2 0x1DC02 (121858)
 3 0x1DC03 (121859)
 4 0x1DC04 (121860)
 5 0x1DC05 (121861)
 6 0x1DC06 (121862)
 7 0x1DC07 (121863)
 8 0x1DC08 (121864)
 9 0x1DC09 (121865)
 10 0x1DC0A (121866)
 11 0x1DC0D (121869)
 12 0x1DC0E (121870)
 13 0x1DC10 (121872)
 14 0x1DC11 (121873)
 15 0x1DC12 (121874)
 16 0x1DC13 (121875)
 17 0x1DC14 (121876)
 18 0x1DC15 (121877)
 19 0x1DC1C (121884)
 20 0x1DC1D (121885)
 21 0x1DC1E (121886)
 22 0x1DC21 (121889)
 23 0x1DC22 (121890)
 24 0x1DC23 (121891)
 25 0x1DC24 (121892)
 26 0x1DC25 (121893)
...
...
 317 0x1DD48 (122184)
 318 0x1DD49 (122185)
 319 0x1DD4A (122186)
 320 0x1DD4B (122187)
 321 0x1DD4C (122188)
 ```

<span data-ttu-id="6d5d7-138">출력에는 현재 프로세스에서 실행 중인 모든 스레드가 관련 디버거 스레드 ID 및 운영 체제 스레드 ID와 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-138">The output shows all the threads currently running in the process with their associated debugger thread ID and operating system thread ID.</span></span> <span data-ttu-id="6d5d7-139">출력에 따라 300개가 넘는 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-139">Based on the output, there are over 300 threads.</span></span>

<span data-ttu-id="6d5d7-140">다음 단계는 각 스레드의 호출 스택을 가져와 현재 스레드가 수행하는 작업을 더 잘 이해하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-140">The next step is to get a better understanding of what the threads are currently doing by getting each thread's callstack.</span></span> <span data-ttu-id="6d5d7-141">`clrstack` 명령을 사용하여 호출 스택을 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-141">The `clrstack` command can be used to output callstacks.</span></span> <span data-ttu-id="6d5d7-142">단일 호출 스택 또는 모든 호출 스택을 출력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-142">It can either output a single callstack or all the callstacks.</span></span> <span data-ttu-id="6d5d7-143">다음 명령을 사용하여 프로세스의 모든 스레드에 대한 모든 호출 스택을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-143">Use the following command to output all the callstacks for all the threads in the process:</span></span>

```console
clrstack -all
```

<span data-ttu-id="6d5d7-144">출력의 대표적인 부분은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-144">A representative portion of the output looks like:</span></span>

```console
  ...
  ...
  ...
        Child SP               IP Call Site
00007F2AE37B5680 00007f305abc6360 [GCFrame: 00007f2ae37b5680]
00007F2AE37B5770 00007f305abc6360 [GCFrame: 00007f2ae37b5770]
00007F2AE37B57D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae37b57d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE37B5920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE37B5950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE37B5CA0 00007f30593044af [GCFrame: 00007f2ae37b5ca0]
00007F2AE37B5D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae37b5d70]
OS Thread Id: 0x1dc82
        Child SP               IP Call Site
00007F2AE2FB4680 00007f305abc6360 [GCFrame: 00007f2ae2fb4680]
00007F2AE2FB4770 00007f305abc6360 [GCFrame: 00007f2ae2fb4770]
00007F2AE2FB47D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae2fb47d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE2FB4920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE2FB4950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE2FB4CA0 00007f30593044af [GCFrame: 00007f2ae2fb4ca0]
00007F2AE2FB4D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae2fb4d70]
OS Thread Id: 0x1dc83
        Child SP               IP Call Site
00007F2AE27B3680 00007f305abc6360 [GCFrame: 00007f2ae27b3680]
00007F2AE27B3770 00007f305abc6360 [GCFrame: 00007f2ae27b3770]
00007F2AE27B37D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae27b37d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE27B3920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE27B3950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE27B3CA0 00007f30593044af [GCFrame: 00007f2ae27b3ca0]
00007F2AE27B3D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae27b3d70]
OS Thread Id: 0x1dc84
        Child SP               IP Call Site
00007F2AE1FB2680 00007f305abc6360 [GCFrame: 00007f2ae1fb2680]
00007F2AE1FB2770 00007f305abc6360 [GCFrame: 00007f2ae1fb2770]
00007F2AE1FB27D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae1fb27d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE1FB2920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE1FB2950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE1FB2CA0 00007f30593044af [GCFrame: 00007f2ae1fb2ca0]
00007F2AE1FB2D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae1fb2d70]
OS Thread Id: 0x1dc85
        Child SP               IP Call Site
00007F2AE17B1680 00007f305abc6360 [GCFrame: 00007f2ae17b1680]
00007F2AE17B1770 00007f305abc6360 [GCFrame: 00007f2ae17b1770]
00007F2AE17B17D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae17b17d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE17B1920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE17B1950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE17B1CA0 00007f30593044af [GCFrame: 00007f2ae17b1ca0]
00007F2AE17B1D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae17b1d70]
OS Thread Id: 0x1dc86
        Child SP               IP Call Site
00007F2AE0FB0680 00007f305abc6360 [GCFrame: 00007f2ae0fb0680]
00007F2AE0FB0770 00007f305abc6360 [GCFrame: 00007f2ae0fb0770]
00007F2AE0FB07D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae0fb07d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE0FB0920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE0FB0950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE0FB0CA0 00007f30593044af [GCFrame: 00007f2ae0fb0ca0]
00007F2AE0FB0D70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae0fb0d70]
OS Thread Id: 0x1dc87
        Child SP               IP Call Site
00007F2AE07AF680 00007f305abc6360 [GCFrame: 00007f2ae07af680]
00007F2AE07AF770 00007f305abc6360 [GCFrame: 00007f2ae07af770]
00007F2AE07AF7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2ae07af7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2AE07AF920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2AE07AF950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2AE07AFCA0 00007f30593044af [GCFrame: 00007f2ae07afca0]
00007F2AE07AFD70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2ae07afd70]
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
...
...
```

<span data-ttu-id="6d5d7-145">300개 이상의 모든 스레드에 대한 호출 스택을 관찰하면 대부분의 스레드가 일반적인 호출 스택을 공유하는 패턴이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-145">Observing the callstacks for all 300+ threads shows a pattern where a majority of the threads share a common callstack:</span></span>

```console
OS Thread Id: 0x1dc88
        Child SP               IP Call Site
00007F2ADFFAE680 00007f305abc6360 [GCFrame: 00007f2adffae680]
00007F2ADFFAE770 00007f305abc6360 [GCFrame: 00007f2adffae770]
00007F2ADFFAE7D0 00007f305abc6360 [HelperMethodFrame_1OBJ: 00007f2adffae7d0] System.Threading.Monitor.ReliableEnter(System.Object, Boolean ByRef)
00007F2ADFFAE920 00007F2FE392B31F testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_1() [/home/marioh/webapi/Controllers/diagscenario.cs @ 36]
00007F2ADFFAE950 00007F2FE392B46D System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/__w/3/s/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
00007F2ADFFAECA0 00007f30593044af [GCFrame: 00007f2adffaeca0]
00007F2ADFFAED70 00007f30593044af [DebuggerU2MCatchHandlerFrame: 00007f2adffaed70]
```

<span data-ttu-id="6d5d7-146">호출 스택은 요청이 `Monitor.ReliableEnter`를 호출하는 교착 상태 메서드에 도착했음을 표시하는 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-146">The callstack seems to show that the request arrived in our deadlock method that in turn makes a call to `Monitor.ReliableEnter`.</span></span> <span data-ttu-id="6d5d7-147">이 메서드는 스레드가 모니터 잠금을 시작하려고 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-147">This method indicates that the threads are trying to enter a monitor lock.</span></span> <span data-ttu-id="6d5d7-148">잠금을 사용할 수 있을 때까지 기다리고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-148">They're waiting on the availability of the lock.</span></span> <span data-ttu-id="6d5d7-149">다른 스레드에 의해 잠겨 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-149">It's likely locked by a different thread.</span></span>

<span data-ttu-id="6d5d7-150">다음 단계는 모니터 잠금을 실제로 보유하고 있는 스레드를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-150">The next step then is to find out which thread is actually holding the monitor lock.</span></span> <span data-ttu-id="6d5d7-151">모니터는 일반적으로 동기화 블록 테이블에 잠금 정보를 저장하므로 `syncblk` 명령을 사용하여 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-151">Since monitors typically store lock information in the sync block table, we can use the `syncblk` command to get more information:</span></span>

```console
> syncblk
Index         SyncBlock MonitorHeld Recursion Owning Thread Info          SyncBlock Owner
   43 00000246E51268B8          603         1 0000024B713F4E30 5634  28   00000249654b14c0 System.Object
   44 00000246E5126908            3         1 0000024B713F47E0 51d4  29   00000249654b14d8 System.Object
-----------------------------
Total           344
CCW             1
RCW             2
ComClassFactory 0
Free            0
```

<span data-ttu-id="6d5d7-152">흥미로운 두 가지 열은 **MonitorHeld** 및 **Owning Thread Info**입니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-152">The two interesting columns are **MonitorHeld** and **Owning Thread Info**.</span></span> <span data-ttu-id="6d5d7-153">**MonitorHeld** 열에는 모니터 잠금이 스레드에 의해 획득되는지 여부와 대기 중인 스레드 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-153">The **MonitorHeld** column shows whether a monitor lock is acquired by a thread and the number of waiting threads.</span></span> <span data-ttu-id="6d5d7-154">**Owing Thread Info** 열에는 현재 모니터 잠금을 소유하고 있는 스레드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-154">The **Owning Thread Info** column shows which thread currently owns the monitor lock.</span></span> <span data-ttu-id="6d5d7-155">스레드 정보에는 세 개의 다른 하위 열이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-155">The thread info has three different subcolumns.</span></span> <span data-ttu-id="6d5d7-156">두 번째 하위 열은 운영 체제 스레드 ID를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-156">The second subcolumn shows operating system thread ID.</span></span>

<span data-ttu-id="6d5d7-157">현재 모니터 잠금을 보유하는 다른 두 가지 스레드(0x5634 및 0x51d4)를 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-157">At this point, we know two different threads (0x5634 and 0x51d4) hold a monitor lock.</span></span> <span data-ttu-id="6d5d7-158">다음 단계로 이러한 스레드가 수행하는 작업을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-158">The next step is to take a look at what those threads are doing.</span></span> <span data-ttu-id="6d5d7-159">잠금을 무한정 보유하고 있지 않은지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-159">We need to check if they're stuck indefinitely holding the lock.</span></span> <span data-ttu-id="6d5d7-160">`setthread` 및 `clrstack` 명령을 사용하여 각 스레드로 전환하고 호출 스택을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-160">Let's use the `setthread` and `clrstack` commands to switch to each of the threads and display the callstacks.</span></span>

<span data-ttu-id="6d5d7-161">첫 번째 스레드를 확인하려면 `setthread` 명령을 실행하고 0x5634 스레드의 인덱스를 찾습니다(기존 인덱스: 28).</span><span class="sxs-lookup"><span data-stu-id="6d5d7-161">To look at the first thread, run the `setthread` command, and find the index of the 0x5634 thread (our index was 28).</span></span> <span data-ttu-id="6d5d7-162">교착 상태 함수가 잠금을 획득하려고 대기 중이지만 이미 잠금을 소유하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-162">The deadlock function is waiting to acquire a lock, but it already owns the lock.</span></span> <span data-ttu-id="6d5d7-163">이미 보유하고 있는 잠금을 기다리는 동안 교착 상태가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-163">It's in deadlock waiting for the lock it already holds.</span></span>

```console
> setthread 28
> clrstack
OS Thread Id: 0x5634 (28)
        Child SP               IP Call Site
0000004E46AFEAA8 00007fff43a5cbc4 [GCFrame: 0000004e46afeaa8]
0000004E46AFEC18 00007fff43a5cbc4 [GCFrame: 0000004e46afec18]
0000004E46AFEC68 00007fff43a5cbc4 [HelperMethodFrame_1OBJ: 0000004e46afec68] System.Threading.Monitor.Enter(System.Object)
0000004E46AFEDC0 00007FFE5EAF9C80 testwebapi.Controllers.DiagScenarioController.DeadlockFunc() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 58]
0000004E46AFEE30 00007FFE5EAF9B8C testwebapi.Controllers.DiagScenarioController.<deadlock>b__3_0() [C:\Users\dapine\Downloads\Diagnostic_scenarios_sample_debug_target\Controllers\DiagnosticScenarios.cs @ 26]
0000004E46AFEE80 00007FFEBB251A5B System.Threading.ThreadHelper.ThreadStart_Context(System.Object) [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 44]
0000004E46AFEEB0 00007FFE5EAEEEEC System.Threading.ExecutionContext.RunInternal(System.Threading.ExecutionContext, System.Threading.ContextCallback, System.Object) [/_/src/System.Private.CoreLib/shared/System/Threading/ExecutionContext.cs @ 201]
0000004E46AFEF20 00007FFEBB234EAB System.Threading.ThreadHelper.ThreadStart() [/_/src/System.Private.CoreLib/src/System/Threading/Thread.CoreCLR.cs @ 93]
0000004E46AFF138 00007ffebdcc6b63 [GCFrame: 0000004e46aff138]
0000004E46AFF3A0 00007ffebdcc6b63 [DebuggerU2MCatchHandlerFrame: 0000004e46aff3a0]
```

<span data-ttu-id="6d5d7-164">두 번째 스레드도 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-164">The second thread is similar.</span></span> <span data-ttu-id="6d5d7-165">또한 이미 소유하고 있는 잠금을 획득하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-165">It's also trying to acquire a lock that it already owns.</span></span> <span data-ttu-id="6d5d7-166">전부 대기 중인 나머지 300개 이상의 스레드는 교착 상태를 초래한 잠금 중 하나를 기다리고 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="6d5d7-166">The remaining 300+ threads that are all waiting are most likely also waiting on one of the locks that caused the deadlock.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d5d7-167">참조</span><span class="sxs-lookup"><span data-stu-id="6d5d7-167">See also</span></span>

- <span data-ttu-id="6d5d7-168">프로세스를 나열하는 [dotnet-trace](dotnet-trace.md)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-168">[dotnet-trace](dotnet-trace.md) to list processes</span></span>
- <span data-ttu-id="6d5d7-169">관리되는 메모리 사용량을 검사하는 [dotnet-counters](dotnet-counters.md)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-169">[dotnet-counters](dotnet-counters.md) to check managed memory usage</span></span>
- <span data-ttu-id="6d5d7-170">덤프 파일을 수집 및 분석하는 [dotnet-dump](dotnet-dump.md)</span><span class="sxs-lookup"><span data-stu-id="6d5d7-170">[dotnet-dump](dotnet-dump.md) to collect and analyze a dump file</span></span>
- [<span data-ttu-id="6d5d7-171">dotnet/diagnostics</span><span class="sxs-lookup"><span data-stu-id="6d5d7-171">dotnet/diagnostics</span></span>](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a><span data-ttu-id="6d5d7-172">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6d5d7-172">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6d5d7-173">.NET Core에서 사용할 수 있는 진단 도구는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6d5d7-173">What diagnostic tools are available in .NET Core</span></span>](index.md)
