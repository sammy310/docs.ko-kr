---
title: 디버깅 프로파일링 구성 설정
description: .NET Core 앱의 디버깅 및 프로파일링을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761995"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="1d637-103">디버깅 및 프로파일링을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="1d637-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="1d637-104">진단 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-104">Enable diagnostics</span></span>

- <span data-ttu-id="1d637-105">디버거, 프로파일러 및 EventPipe 진단이 사용 또는 사용하지 않도록 설정되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="1d637-106">이 설정을 생략하면 진단이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-106">If you omit this setting, diagnostics are enabled.</span></span> <span data-ttu-id="1d637-107">이는 값을 `1`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-107">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="1d637-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-108">Setting name</span></span> | <span data-ttu-id="1d637-109">값</span><span class="sxs-lookup"><span data-stu-id="1d637-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1d637-110">**runtimeconfig.json**</span></span> | <span data-ttu-id="1d637-111">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-111">N/A</span></span> | <span data-ttu-id="1d637-112">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-112">N/A</span></span> |
| <span data-ttu-id="1d637-113">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-113">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="1d637-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-114">`1` - enabled</span></span><br/><span data-ttu-id="1d637-115">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d637-115">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="1d637-116">프로파일링 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-116">Enable profiling</span></span>

- <span data-ttu-id="1d637-117">현재 실행 중인 프로세스에서 프로파일링이 사용하도록 설정되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-117">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="1d637-118">이 설정을 생략하면 프로파일링을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-118">If you omit this setting, profiling is disabled.</span></span> <span data-ttu-id="1d637-119">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-119">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1d637-120">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-120">Setting name</span></span> | <span data-ttu-id="1d637-121">값</span><span class="sxs-lookup"><span data-stu-id="1d637-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1d637-122">**runtimeconfig.json**</span></span> | <span data-ttu-id="1d637-123">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-123">N/A</span></span> | <span data-ttu-id="1d637-124">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-124">N/A</span></span> |
| <span data-ttu-id="1d637-125">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-125">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="1d637-126">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d637-126">`0` - disabled</span></span><br/><span data-ttu-id="1d637-127">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-127">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="1d637-128">프로파일러 GUID</span><span class="sxs-lookup"><span data-stu-id="1d637-128">Profiler GUID</span></span>

- <span data-ttu-id="1d637-129">현재 실행 중인 프로세스에 로드할 프로파일러의 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-129">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="1d637-130">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-130">Setting name</span></span> | <span data-ttu-id="1d637-131">값</span><span class="sxs-lookup"><span data-stu-id="1d637-131">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-132">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1d637-132">**runtimeconfig.json**</span></span> | <span data-ttu-id="1d637-133">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-133">N/A</span></span> | <span data-ttu-id="1d637-134">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-134">N/A</span></span> |
| <span data-ttu-id="1d637-135">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-135">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="1d637-136">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="1d637-136">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="1d637-137">프로파일러 위치</span><span class="sxs-lookup"><span data-stu-id="1d637-137">Profiler location</span></span>

- <span data-ttu-id="1d637-138">현재 실행 중인 프로세스(또는 32비트 또는 64비트 프로세스)에 로드할 프로파일러 DLL의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-138">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="1d637-139">변수가 둘 이상 설정된 경우, 비트 수 관련 변수가 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-139">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="1d637-140">이들 변수는 프로파일러의 어느 비트 수를 로드할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-140">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="1d637-141">자세한 내용은 [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)(프로파일러 라이브러리 찾기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d637-141">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="1d637-142">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-142">Setting name</span></span> | <span data-ttu-id="1d637-143">값</span><span class="sxs-lookup"><span data-stu-id="1d637-143">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-144">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="1d637-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1d637-145">*string-path*</span></span> |
| <span data-ttu-id="1d637-146">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="1d637-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1d637-147">*string-path*</span></span> |
| <span data-ttu-id="1d637-148">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-148">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="1d637-149">*string-path*</span><span class="sxs-lookup"><span data-stu-id="1d637-149">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="1d637-150">perf 맵 작성</span><span class="sxs-lookup"><span data-stu-id="1d637-150">Write perf map</span></span>

- <span data-ttu-id="1d637-151">Linux 시스템에서 */tmp/perf-$pid.map*의 작성을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-151">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="1d637-152">이 설정을 생략하면 perf 맵을 작성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-152">If you omit this setting, writing the perf map is disabled.</span></span> <span data-ttu-id="1d637-153">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-153">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1d637-154">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-154">Setting name</span></span> | <span data-ttu-id="1d637-155">값</span><span class="sxs-lookup"><span data-stu-id="1d637-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1d637-156">**runtimeconfig.json**</span></span> | <span data-ttu-id="1d637-157">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-157">N/A</span></span> | <span data-ttu-id="1d637-158">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-158">N/A</span></span> |
| <span data-ttu-id="1d637-159">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-159">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="1d637-160">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d637-160">`0` - disabled</span></span><br/><span data-ttu-id="1d637-161">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-161">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="1d637-162">Perf 로그 마커</span><span class="sxs-lookup"><span data-stu-id="1d637-162">Perf log markers</span></span>

- <span data-ttu-id="1d637-163">Perf 로그에서 마커로 사용되거나 무시될 지정된 신호를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-163">Enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="1d637-164">이 설정을 생략하면 지정된 신호는 무시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-164">If you omit this setting, the specified signal is not ignored.</span></span> <span data-ttu-id="1d637-165">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-165">This is equivalent to setting the value to `0`.</span></span>

| | <span data-ttu-id="1d637-166">설정 이름</span><span class="sxs-lookup"><span data-stu-id="1d637-166">Setting name</span></span> | <span data-ttu-id="1d637-167">값</span><span class="sxs-lookup"><span data-stu-id="1d637-167">Values</span></span> |
| - | - | - |
| <span data-ttu-id="1d637-168">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="1d637-168">**runtimeconfig.json**</span></span> | <span data-ttu-id="1d637-169">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-169">N/A</span></span> | <span data-ttu-id="1d637-170">N/A</span><span class="sxs-lookup"><span data-stu-id="1d637-170">N/A</span></span> |
| <span data-ttu-id="1d637-171">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="1d637-171">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="1d637-172">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="1d637-172">`0` - disabled</span></span><br/><span data-ttu-id="1d637-173">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="1d637-173">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="1d637-174">[COMPlus_PerfMapEnabled](#write-perf-map)를 생략하거나 `0`(즉, 사용 안 함)으로 설정하면 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d637-174">This setting is ignored if [COMPlus_PerfMapEnabled](#write-perf-map) is omitted or set to `0` (that is, disabled).</span></span>
