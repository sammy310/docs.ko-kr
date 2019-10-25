---
title: dotnet-counters - .NET Core
description: dotnet-counter 명령줄 도구를 설치하고 사용하는 방법에 대해 알아봅니다.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: b2fab239713d9d19c580580496e73a91ceafcc52
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321539"
---
# <a name="dotnet-counters"></a><span data-ttu-id="51017-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="51017-103">dotnet-counters</span></span>

<span data-ttu-id="51017-104">**이 문서 적용 대상: ✓** .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="51017-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="51017-105">dotnet-counters 설치</span><span class="sxs-lookup"><span data-stu-id="51017-105">Install dotnet-counters</span></span>

<span data-ttu-id="51017-106">`dotnet-counters` [NuGet 패키지](https://www.nuget.org/packages/dotnet-counters)의 최신 릴리스 버전을 설치하려면 [dotnet 도구 설치](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="51017-107">개요</span><span class="sxs-lookup"><span data-stu-id="51017-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="51017-108">설명</span><span class="sxs-lookup"><span data-stu-id="51017-108">Description</span></span>

<span data-ttu-id="51017-109">`dotnet-counters`는 임시 상태 모니터링 및 1단계 수준 성능 조사를 위한 성능 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="51017-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="51017-110"><xref:System.Diagnostics.Tracing.EventCounter> API를 통해 게시된 성능 카운터 값을 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51017-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="51017-111">예를 들어, `PerfView` 또는 `dotnet-trace`를 사용하여 보다 심각한 성능 조사를 살펴보기 전에 의심스러운 내용이 있는지 확인하기 위해 .NET Core 애플리케이션에서 throw되는 CPU 사용량 또는 예외 비율과 같은 항목을 신속하게 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51017-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="51017-112">옵션</span><span class="sxs-lookup"><span data-stu-id="51017-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="51017-113">dotnet-counters 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="51017-114">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="51017-115">명령</span><span class="sxs-lookup"><span data-stu-id="51017-115">Commands</span></span>

| <span data-ttu-id="51017-116">명령</span><span class="sxs-lookup"><span data-stu-id="51017-116">Command</span></span>                                             |
| --------------------------------------------------- |
| [<span data-ttu-id="51017-117">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="51017-117">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="51017-118">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="51017-118">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |

## <a name="dotnet-counters-list"></a><span data-ttu-id="51017-119">dotnet-counters 목록</span><span class="sxs-lookup"><span data-stu-id="51017-119">dotnet-counters list</span></span>

<span data-ttu-id="51017-120">공급자별로 그룹화된 카운터 이름 및 설명 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-120">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="51017-121">개요</span><span class="sxs-lookup"><span data-stu-id="51017-121">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="51017-122">예</span><span class="sxs-lookup"><span data-stu-id="51017-122">Example</span></span>

```console
> dotnet-counters list

    Showing well-known counters only. Specific processes may support additional counters.
    System.Runtime
        cpu-usage                    Amount of time the process has utilized the CPU (ms)
        working-set                  Amount of working set used by the process (MB)
        gc-heap-size                 Total heap size reported by the GC (MB)
        gen-0-gc-count               Number of Gen 0 GCs / sec
        gen-1-gc-count               Number of Gen 1 GCs / sec
        gen-2-gc-count               Number of Gen 2 GCs / sec
        exception-count              Number of Exceptions / sec
```

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="51017-123">dotnet-counters 모니터</span><span class="sxs-lookup"><span data-stu-id="51017-123">dotnet-counters monitor</span></span>

<span data-ttu-id="51017-124">선택한 카운터의 값을 주기적으로 새로 고치는 방법을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-124">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="51017-125">개요</span><span class="sxs-lookup"><span data-stu-id="51017-125">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="51017-126">옵션</span><span class="sxs-lookup"><span data-stu-id="51017-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="51017-127">모니터링할 프로세스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51017-127">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="51017-128">표시된 카운터 업데이트 사이의 지연 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="51017-128">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="51017-129">공백으로 구분된 카운터의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="51017-129">A space separated list of counters.</span></span> <span data-ttu-id="51017-130">카운터는 `provider_name[:counter_name]`을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51017-130">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="51017-131">한정된 `counter_name` 없이 `provider_name`을 사용하면 모든 카운터가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="51017-131">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="51017-132">공급자 및 카운터 이름을 검색하려면 [dotnet-counters 목록](#dotnet-counters-list) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-132">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="51017-133">예</span><span class="sxs-lookup"><span data-stu-id="51017-133">Examples</span></span>

- <span data-ttu-id="51017-134">3초의 새로 고침 간격으로 `System.Runtime`의 모든 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-134">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="51017-135">`System.Runtime`에서 CPU 사용량 및 GC 힙 크기만 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-135">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="51017-136">사용자 정의 `EventSource`에서 `EventCounter` 값을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="51017-136">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="51017-137">자세한 내용은 [자습서: EventCounters를 사용하여 매우 자주 발생하는 이벤트의 성능을 측정하는 방법](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51017-137">For more information, see [Tutorial: How to measure performance for very frequent events using EventCounters](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
