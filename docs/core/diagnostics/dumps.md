---
title: 덤프 - .NET
description: .NET의 덤프에 대한 소개입니다.
ms.date: 10/12/2020
ms.openlocfilehash: 56cf4085d10658c828bac39be93eed3f774e00d5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242775"
---
# <a name="dumps"></a><span data-ttu-id="b614d-103">덤프</span><span class="sxs-lookup"><span data-stu-id="b614d-103">Dumps</span></span>

<span data-ttu-id="b614d-104">덤프는 프로세스가 생성된 시점의 프로세스 스냅샷을 포함하는 파일이며, 애플리케이션의 상태를 검사하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-104">A dump is a file that contains a snapshot of the process at the time it was created and can be useful for examining the state of your application.</span></span> <span data-ttu-id="b614d-105">프로덕션 환경이나 CI 환경과 같이 디버거를 연결하기 어려운 경우에는 덤프를 사용하여 .NET 애플리케이션을 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-105">Dumps can be used to debug your .NET application when it is difficult to attach a debugger to it such as production or CI environments.</span></span> <span data-ttu-id="b614d-106">덤프를 사용하면 문제가 있는 프로세스의 상태를 캡처하여 애플리케이션을 중지하지 않고도 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-106">Using dumps allows you to capture the state of the problematic process and examine it without having to stop the application.</span></span>

## <a name="collect-dumps"></a><span data-ttu-id="b614d-107">덤프 수집</span><span class="sxs-lookup"><span data-stu-id="b614d-107">Collect dumps</span></span>

<span data-ttu-id="b614d-108">덤프는 앱을 실행하는 플랫폼에 따라 다양한 방법으로 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-108">Dumps can be collected in a variety of ways depending on which platform you are running your app on.</span></span>

> [!NOTE]
> <span data-ttu-id="b614d-109">컨테이너 내에서 덤프를 수집하려면 PTRACE 기능이 필요하며, 이 기능은 `--cap-add=SYS_PTRACE` 또는 `--privileged`를 통해 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-109">Collecting a dump inside a container requires PTRACE capability, which can be added via `--cap-add=SYS_PTRACE` or `--privileged`.</span></span>

> [!NOTE]
> <span data-ttu-id="b614d-110">덤프는 실행 중인 프로세스의 전체 메모리를 포함할 수 있기 때문에 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-110">Dumps may contain sensitive information because they can contain the full memory of the running process.</span></span> <span data-ttu-id="b614d-111">덤프를 처리할 때는 모든 보안 제한 사항과 지침을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-111">Handle them with any security restrictions and guidances in mind.</span></span>

### <a name="collecting-dumps-on-crash"></a><span data-ttu-id="b614d-112">크래시 발생 시 덤프 수집</span><span class="sxs-lookup"><span data-stu-id="b614d-112">Collecting dumps on crash</span></span>

<span data-ttu-id="b614d-113">환경 변수를 사용하여 크래시 발생 시 덤프를 수집하도록 애플리케이션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-113">You can use environment variables to configure your application to collect a dump upon a crash.</span></span> <span data-ttu-id="b614d-114">그러면 크래시가 발생한 이유를 파악하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-114">This is helpful when you want to get an understanding of why a crash happened.</span></span> <span data-ttu-id="b614d-115">예를 들어 예외가 throw될 때 덤프를 캡처하면 크래시된 앱의 상태를 검사하여 문제를 식별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-115">For example, capturing a dump when an exception is thrown helps you identify an issue by examining the state of the app when it crashed.</span></span>

<span data-ttu-id="b614d-116">다음 표에서는 크래시 발생 시 덤프를 수집하기 위해 구성할 수 있는 환경 변수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-116">The following table shows the environment variables you can configure for collecting dumps on a crash.</span></span>

|<span data-ttu-id="b614d-117">환경 변수</span><span class="sxs-lookup"><span data-stu-id="b614d-117">Environment variable</span></span>|<span data-ttu-id="b614d-118">Description</span><span class="sxs-lookup"><span data-stu-id="b614d-118">Description</span></span>|<span data-ttu-id="b614d-119">기본값</span><span class="sxs-lookup"><span data-stu-id="b614d-119">Default value</span></span>|
|-------|---------|---|
|`COMPlus_DbgEnableMiniDump`|<span data-ttu-id="b614d-120">1로 설정하면 코어 덤프 생성을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-120">If set to 1, enable core dump generation.</span></span>|<span data-ttu-id="b614d-121">0</span><span class="sxs-lookup"><span data-stu-id="b614d-121">0</span></span>|
|`COMPlus_DbgMiniDumpType`|<span data-ttu-id="b614d-122">수집할 덤프의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-122">Type of dump to be collected.</span></span> <span data-ttu-id="b614d-123">자세한 내용은 아래 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b614d-123">For more information, see the table below</span></span>|<span data-ttu-id="b614d-124">2(`MiniDumpWithPrivateReadWriteMemory`)</span><span class="sxs-lookup"><span data-stu-id="b614d-124">2 (`MiniDumpWithPrivateReadWriteMemory`)</span></span>|
|`COMPlus_DbgMiniDumpName`|<span data-ttu-id="b614d-125">덤프를 쓸 대상 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-125">Path to a file to write the dump to.</span></span>|`/tmp/coredump.<pid>`|
|`COMPlus_CreateDumpDiagnostics`|<span data-ttu-id="b614d-126">1로 설정하면 덤프 프로세스의 진단 로깅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-126">If set to 1, enable diagnostic logging of dump process.</span></span>|<span data-ttu-id="b614d-127">0</span><span class="sxs-lookup"><span data-stu-id="b614d-127">0</span></span>|

<span data-ttu-id="b614d-128">다음 표에서는 값으로 지정할 수 있는 `COMPlus_DbgMiniDumpType`에 사용할 수 있는 모든 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-128">The table below shows all the options you may use for `COMPlus_DbgMiniDumpType` which can be specified as a value.</span></span> <span data-ttu-id="b614d-129">예를 들어 `COMPlus_DbgMiniDumpType`을 1로 설정하면 크래시 발생 시 `MiniDumpNormal` 유형 덤프가 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-129">For example, setting `COMPlus_DbgMiniDumpType` to 1 means `MiniDumpNormal` type dump will be collected on a crash.</span></span>

|<span data-ttu-id="b614d-130">값</span><span class="sxs-lookup"><span data-stu-id="b614d-130">Value</span></span>|<span data-ttu-id="b614d-131">Name</span><span class="sxs-lookup"><span data-stu-id="b614d-131">Name</span></span>|<span data-ttu-id="b614d-132">설명</span><span class="sxs-lookup"><span data-stu-id="b614d-132">Description</span></span>|
|-----|----|-----------|
|<span data-ttu-id="b614d-133">1</span><span class="sxs-lookup"><span data-stu-id="b614d-133">1</span></span>|`MiniDumpNormal`|<span data-ttu-id="b614d-134">프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 정보만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-134">Include just the information necessary to capture stack traces for all existing threads in a process.</span></span> <span data-ttu-id="b614d-135">제한된 GC 힙 메모리 및 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-135">Limited GC heap memory and information.</span></span>|
|<span data-ttu-id="b614d-136">2</span><span class="sxs-lookup"><span data-stu-id="b614d-136">2</span></span>|`MiniDumpWithPrivateReadWriteMemory`|<span data-ttu-id="b614d-137">프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 GC 힙 및 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-137">Includes the GC heaps and information necessary to capture stack traces for all existing threads in a process.</span></span>|
|<span data-ttu-id="b614d-138">3</span><span class="sxs-lookup"><span data-stu-id="b614d-138">3</span></span>|`MiniDumpFilterTriage`|<span data-ttu-id="b614d-139">프로세스의 모든 기존 스레드에 대한 스택 추적을 캡처하는 데 필요한 정보만 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-139">Include just the information necessary to capture stack traces for all existing threads in a process.</span></span> <span data-ttu-id="b614d-140">제한된 GC 힙 메모리 및 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-140">Limited GC heap memory and information.</span></span>|
|<span data-ttu-id="b614d-141">4</span><span class="sxs-lookup"><span data-stu-id="b614d-141">4</span></span>|`MiniDumpWithFullMemory`|<span data-ttu-id="b614d-142">프로세스의 액세스할 수 있는 모든 메모리를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-142">Include all accessible memory in the process.</span></span> <span data-ttu-id="b614d-143">원시 메모리 데이터는 끝에 포함되므로 원시 메모리 정보 없이 초기 구조를 직접 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-143">The raw memory data is included at the end, so that the initial structures can be mapped directly without the raw memory information.</span></span> <span data-ttu-id="b614d-144">이 옵션을 선택하면 매우 큰 파일이 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-144">This option can result in a very large file.</span></span>|

### <a name="collecting-dumps-at-specific-point-in-time"></a><span data-ttu-id="b614d-145">특정 시점에 덤프 수집</span><span class="sxs-lookup"><span data-stu-id="b614d-145">Collecting dumps at specific point in time</span></span>

<span data-ttu-id="b614d-146">앱이 아직 크래시되지 않은 경우에 덤프를 수집하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-146">You may want to collect a dump when the app hasn't crashed yet.</span></span> <span data-ttu-id="b614d-147">예를 들어 교착 상태에 있는 것으로 보이는 애플리케이션의 상태를 검사하려는 경우 크래시 발생 시 덤프를 수집하도록 환경 변수를 구성하면 앱이 계속 실행되고 있기 때문에 유용하지 않게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-147">For example, if you want to examine the state of an application that seems to be in a deadlock, configuring the environment variables to collect dumps on crash will not be helpful because the app is still running.</span></span>

<span data-ttu-id="b614d-148">직접적인 요청에 따라 덤프를 수집하려면 덤프를 수집하고 분석하는 CLI 도구인 `dotnet-dump`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-148">To collect dump at your own request, you can use `dotnet-dump`, which is a CLI tool for collecting and analyzing dumps.</span></span> <span data-ttu-id="b614d-149">`dotnet-dump`를 사용하여 덤프를 수집하는 방법에 대한 자세한 내용은 [Dump collection and analysis utility](dotnet-dump.md)(덤프 수집 및 분석 유틸리티)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b614d-149">For more information on how to use it to collect dumps with `dotnet-dump`, see [Dump collection and analysis utility](dotnet-dump.md).</span></span>

## <a name="analyze-dumps"></a><span data-ttu-id="b614d-150">덤프 분석</span><span class="sxs-lookup"><span data-stu-id="b614d-150">Analyze dumps</span></span>

<span data-ttu-id="b614d-151">덤프는 [`dotnet-dump`](dotnet-dump.md)를 사용하여 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-151">Dumps can be analyzed using [`dotnet-dump`](dotnet-dump.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b614d-152">참조</span><span class="sxs-lookup"><span data-stu-id="b614d-152">See also</span></span>

<span data-ttu-id="b614d-153">덤프를 활용하여 .NET 애플리케이션에서 문제를 진단하는 방법에 대해 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b614d-153">Learn more about how you can leverage dumps to help diagnosing problems in your .NET application.</span></span>

* <span data-ttu-id="b614d-154">[Debug Linux dumps](debug-linux-dumps.md)(Linux 덤프 디버그) 자습서에서는 Linux에서 수집된 덤프를 디버그하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-154">[Debug Linux dumps](debug-linux-dumps.md) tutorial walks you through how to debug a dump that was collected in Linux.</span></span>

* <span data-ttu-id="b614d-155">[Debug deadlock](debug-deadlock.md)(교착 상태 디버그) 자습서에서는 .NET 애플리케이션에서 덤프를 사용하여 교착 상태를 디버그하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="b614d-155">[Debug deadlock](debug-deadlock.md) tutorial walks you through how to debug a deadlock in your .NET application using dumps.</span></span>
