---
title: 디버깅 프로파일링 구성 설정
description: .NET Core 앱의 디버깅 및 프로파일링을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998860"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a><span data-ttu-id="76040-103">디버깅 및 프로파일링을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="76040-103">Run-time configuration options for debugging and profiling</span></span>

## <a name="enable-diagnostics"></a><span data-ttu-id="76040-104">진단 사용</span><span class="sxs-lookup"><span data-stu-id="76040-104">Enable diagnostics</span></span>

- <span data-ttu-id="76040-105">디버거, 프로파일러 및 EventPipe 진단이 사용 또는 사용하지 않도록 설정되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-105">Configures whether the debugger, the profiler, and EventPipe diagnostics are enabled or disabled.</span></span>
- <span data-ttu-id="76040-106">기본값: 사용(`1`).</span><span class="sxs-lookup"><span data-stu-id="76040-106">Default: Enabled (`1`).</span></span>

| | <span data-ttu-id="76040-107">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-107">Setting name</span></span> | <span data-ttu-id="76040-108">값</span><span class="sxs-lookup"><span data-stu-id="76040-108">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-109">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="76040-109">**runtimeconfig.json**</span></span> | <span data-ttu-id="76040-110">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-110">N/A</span></span> | <span data-ttu-id="76040-111">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-111">N/A</span></span> |
| <span data-ttu-id="76040-112">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-112">**Environment variable**</span></span> | `COMPlus_EnableDiagnostics` | <span data-ttu-id="76040-113">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="76040-113">`1` - enabled</span></span><br/><span data-ttu-id="76040-114">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="76040-114">`0` - disabled</span></span> |

## <a name="enable-profiling"></a><span data-ttu-id="76040-115">프로파일링 사용</span><span class="sxs-lookup"><span data-stu-id="76040-115">Enable profiling</span></span>

- <span data-ttu-id="76040-116">현재 실행 중인 프로세스에서 프로파일링이 사용하도록 설정되는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-116">Configures whether profiling is enabled for the currently running process.</span></span>
- <span data-ttu-id="76040-117">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="76040-117">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="76040-118">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-118">Setting name</span></span> | <span data-ttu-id="76040-119">값</span><span class="sxs-lookup"><span data-stu-id="76040-119">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-120">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="76040-120">**runtimeconfig.json**</span></span> | <span data-ttu-id="76040-121">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-121">N/A</span></span> | <span data-ttu-id="76040-122">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-122">N/A</span></span> |
| <span data-ttu-id="76040-123">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-123">**Environment variable**</span></span> | `CORECLR_ENABLE_PROFILING` | <span data-ttu-id="76040-124">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="76040-124">`0` - disabled</span></span><br/><span data-ttu-id="76040-125">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="76040-125">`1` - enabled</span></span> |

## <a name="profiler-guid"></a><span data-ttu-id="76040-126">프로파일러 GUID</span><span class="sxs-lookup"><span data-stu-id="76040-126">Profiler GUID</span></span>

- <span data-ttu-id="76040-127">현재 실행 중인 프로세스에 로드할 프로파일러의 GUID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-127">Specifies the GUID of the profiler to load into the currently running process.</span></span>

| | <span data-ttu-id="76040-128">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-128">Setting name</span></span> | <span data-ttu-id="76040-129">값</span><span class="sxs-lookup"><span data-stu-id="76040-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="76040-130">**runtimeconfig.json**</span></span> | <span data-ttu-id="76040-131">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-131">N/A</span></span> | <span data-ttu-id="76040-132">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-132">N/A</span></span> |
| <span data-ttu-id="76040-133">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-133">**Environment variable**</span></span> | `CORECLR_PROFILER` | <span data-ttu-id="76040-134">*string-guid*</span><span class="sxs-lookup"><span data-stu-id="76040-134">*string-guid*</span></span> |

## <a name="profiler-location"></a><span data-ttu-id="76040-135">프로파일러 위치</span><span class="sxs-lookup"><span data-stu-id="76040-135">Profiler location</span></span>

- <span data-ttu-id="76040-136">현재 실행 중인 프로세스(또는 32비트 또는 64비트 프로세스)에 로드할 프로파일러 DLL의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-136">Specifies the path to the profiler DLL to load into the currently running process (or 32-bit or 64-bit process).</span></span>
- <span data-ttu-id="76040-137">변수가 둘 이상 설정된 경우, 비트 수 관련 변수가 우선적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="76040-137">If more than one variable is set, the bitness-specific variables take precedence.</span></span> <span data-ttu-id="76040-138">이들 변수는 프로파일러의 어느 비트 수를 로드할지 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-138">They specify which bitness of profiler to load.</span></span>
- <span data-ttu-id="76040-139">자세한 내용은 [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)(프로파일러 라이브러리 찾기)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76040-139">For more information, see [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).</span></span>

| | <span data-ttu-id="76040-140">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-140">Setting name</span></span> | <span data-ttu-id="76040-141">값</span><span class="sxs-lookup"><span data-stu-id="76040-141">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-142">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-142">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH` | <span data-ttu-id="76040-143">*string-path*</span><span class="sxs-lookup"><span data-stu-id="76040-143">*string-path*</span></span> |
| <span data-ttu-id="76040-144">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-144">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_32` | <span data-ttu-id="76040-145">*string-path*</span><span class="sxs-lookup"><span data-stu-id="76040-145">*string-path*</span></span> |
| <span data-ttu-id="76040-146">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-146">**Environment variable**</span></span> | `CORECLR_PROFILER_PATH_64` | <span data-ttu-id="76040-147">*string-path*</span><span class="sxs-lookup"><span data-stu-id="76040-147">*string-path*</span></span> |

## <a name="write-perf-map"></a><span data-ttu-id="76040-148">perf 맵 작성</span><span class="sxs-lookup"><span data-stu-id="76040-148">Write perf map</span></span>

- <span data-ttu-id="76040-149">Linux 시스템에서 */tmp/perf-$pid.map*의 작성을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-149">Enables or disables writing */tmp/perf-$pid.map* on Linux systems.</span></span>
- <span data-ttu-id="76040-150">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="76040-150">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="76040-151">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-151">Setting name</span></span> | <span data-ttu-id="76040-152">값</span><span class="sxs-lookup"><span data-stu-id="76040-152">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="76040-153">**runtimeconfig.json**</span></span> | <span data-ttu-id="76040-154">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-154">N/A</span></span> | <span data-ttu-id="76040-155">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-155">N/A</span></span> |
| <span data-ttu-id="76040-156">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-156">**Environment variable**</span></span> | `COMPlus_PerfMapEnabled` | <span data-ttu-id="76040-157">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="76040-157">`0` - disabled</span></span><br/><span data-ttu-id="76040-158">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="76040-158">`1` - enabled</span></span> |

## <a name="perf-log-markers"></a><span data-ttu-id="76040-159">Perf 로그 마커</span><span class="sxs-lookup"><span data-stu-id="76040-159">Perf log markers</span></span>

- <span data-ttu-id="76040-160">`COMPlus_PerfMapEnabled`가 `1`로 설정된 경우, perf 로그에서 마커로 사용되거나 무시될 지정된 신호를 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="76040-160">When `COMPlus_PerfMapEnabled` is set to `1`, enables or disables the specified signal to be accepted and ignored as a marker in the perf logs.</span></span>
- <span data-ttu-id="76040-161">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="76040-161">Default: Disabled (`0`).</span></span>

| | <span data-ttu-id="76040-162">설정 이름</span><span class="sxs-lookup"><span data-stu-id="76040-162">Setting name</span></span> | <span data-ttu-id="76040-163">값</span><span class="sxs-lookup"><span data-stu-id="76040-163">Values</span></span> |
| - | - | - |
| <span data-ttu-id="76040-164">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="76040-164">**runtimeconfig.json**</span></span> | <span data-ttu-id="76040-165">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-165">N/A</span></span> | <span data-ttu-id="76040-166">N/A</span><span class="sxs-lookup"><span data-stu-id="76040-166">N/A</span></span> |
| <span data-ttu-id="76040-167">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="76040-167">**Environment variable**</span></span> | `COMPlus_PerfMapIgnoreSignal` | <span data-ttu-id="76040-168">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="76040-168">`0` - disabled</span></span><br/><span data-ttu-id="76040-169">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="76040-169">`1` - enabled</span></span> |
