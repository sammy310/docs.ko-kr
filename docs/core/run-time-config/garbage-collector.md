---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915993"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="c5bfa-103">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="c5bfa-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="c5bfa-104">이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="c5bfa-105">실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="c5bfa-106">그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="c5bfa-107">이 페이지에서는 설정이 그룹별로 정리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="c5bfa-108">각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="c5bfa-109">이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="c5bfa-110">[대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="c5bfa-111">이러한 설정은 이 페이지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="c5bfa-112">숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="c5bfa-113">16진수 값의 경우 “0x” 접두사를 사용하거나 사용하지 않고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="c5bfa-114">가비지 수집 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-114">Flavors of garbage collection</span></span>

<span data-ttu-id="c5bfa-115">가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="c5bfa-116">둘 사이의 차이점에 대한 자세한 내용은 [워크스테이션 및 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="c5bfa-117">가비지 수집의 하위 버전은 백그라운드와 비동시입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="c5bfa-118">다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-118">Use the following settings to select flavors of garbage collection:</span></span>

- [<span data-ttu-id="c5bfa-119">워크스테이션과 서버 GC 비교</span><span class="sxs-lookup"><span data-stu-id="c5bfa-119">Workstation vs. server GC</span></span>](#workstation-vs-server)
- [<span data-ttu-id="c5bfa-120">백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-120">Background GC</span></span>](#background-gc)

### <a name="workstation-vs-server"></a><span data-ttu-id="c5bfa-121">워크스테이션과 서버 비교</span><span class="sxs-lookup"><span data-stu-id="c5bfa-121">Workstation vs. server</span></span>

- <span data-ttu-id="c5bfa-122">애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-122">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="c5bfa-123">기본값: 워크스테이션 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-123">Default: Workstation garbage collection.</span></span> <span data-ttu-id="c5bfa-124">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-124">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="c5bfa-125">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-125">Setting name</span></span> | <span data-ttu-id="c5bfa-126">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-126">Values</span></span> | <span data-ttu-id="c5bfa-127">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-127">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-128">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="c5bfa-129">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="c5bfa-129">`false` - workstation</span></span><br/><span data-ttu-id="c5bfa-130">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="c5bfa-130">`true` - server</span></span> | <span data-ttu-id="c5bfa-131">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-131">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-132">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-132">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="c5bfa-133">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="c5bfa-133">`false` - workstation</span></span><br/><span data-ttu-id="c5bfa-134">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="c5bfa-134">`true` - server</span></span> | <span data-ttu-id="c5bfa-135">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-135">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-136">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-136">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="c5bfa-137">`0` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="c5bfa-137">`0` - workstation</span></span><br/><span data-ttu-id="c5bfa-138">`1` - 서버</span><span class="sxs-lookup"><span data-stu-id="c5bfa-138">`1` - server</span></span> | <span data-ttu-id="c5bfa-139">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-139">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-140">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-140">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-141">GCServer</span><span class="sxs-lookup"><span data-stu-id="c5bfa-141">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="c5bfa-142">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="c5bfa-142">`false` - workstation</span></span><br/><span data-ttu-id="c5bfa-143">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="c5bfa-143">`true` - server</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="c5bfa-144">예</span><span class="sxs-lookup"><span data-stu-id="c5bfa-144">Examples</span></span>

<span data-ttu-id="c5bfa-145">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-145">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="c5bfa-146">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-146">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a><span data-ttu-id="c5bfa-147">백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-147">Background GC</span></span>

- <span data-ttu-id="c5bfa-148">백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-148">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="c5bfa-149">기본값: 백그라운드 GC를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-149">Default: Use background GC.</span></span> <span data-ttu-id="c5bfa-150">이는 값을 `true`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-150">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="c5bfa-151">자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/background-gc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-151">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="c5bfa-152">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-152">Setting name</span></span> | <span data-ttu-id="c5bfa-153">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-153">Values</span></span> | <span data-ttu-id="c5bfa-154">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-154">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-155">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-155">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="c5bfa-156">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-156">`true` - background GC</span></span><br/><span data-ttu-id="c5bfa-157">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="c5bfa-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-159">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-159">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="c5bfa-160">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-160">`true` - background GC</span></span><br/><span data-ttu-id="c5bfa-161">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="c5bfa-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-163">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-163">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="c5bfa-164">`1` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-164">`1` - background GC</span></span><br/><span data-ttu-id="c5bfa-165">`0` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-165">`0` - non-concurrent GC</span></span> | <span data-ttu-id="c5bfa-166">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-166">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-167">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-167">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-168">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="c5bfa-168">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="c5bfa-169">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-169">`true` - background GC</span></span><br/><span data-ttu-id="c5bfa-170">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-170">`false` - non-concurrent GC</span></span> |  |

#### <a name="examples"></a><span data-ttu-id="c5bfa-171">예</span><span class="sxs-lookup"><span data-stu-id="c5bfa-171">Examples</span></span>

<span data-ttu-id="c5bfa-172">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-172">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="c5bfa-173">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-173">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="c5bfa-174">리소스 사용량 관리</span><span class="sxs-lookup"><span data-stu-id="c5bfa-174">Manage resource usage</span></span>

<span data-ttu-id="c5bfa-175">다음 설정을 사용하여 가비지 수집기의 메모리 및 프로세서 사용량을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-175">Use the following settings to manage the garbage collector's memory and processor usage:</span></span>

- [<span data-ttu-id="c5bfa-176">선호도 지정</span><span class="sxs-lookup"><span data-stu-id="c5bfa-176">Affinitize</span></span>](#affinitize)
- [<span data-ttu-id="c5bfa-177">선호도 지정 마스크</span><span class="sxs-lookup"><span data-stu-id="c5bfa-177">Affinitize mask</span></span>](#affinitize-mask)
- [<span data-ttu-id="c5bfa-178">선호도 지정 범위</span><span class="sxs-lookup"><span data-stu-id="c5bfa-178">Affinitize ranges</span></span>](#affinitize-ranges)
- [<span data-ttu-id="c5bfa-179">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="c5bfa-179">CPU groups</span></span>](#cpu-groups)
- [<span data-ttu-id="c5bfa-180">힙 수</span><span class="sxs-lookup"><span data-stu-id="c5bfa-180">Heap count</span></span>](#heap-count)
- [<span data-ttu-id="c5bfa-181">힙 제한</span><span class="sxs-lookup"><span data-stu-id="c5bfa-181">Heap limit</span></span>](#heap-limit)
- [<span data-ttu-id="c5bfa-182">힙 제한 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-182">Heap limit percent</span></span>](#heap-limit-percent)
- [<span data-ttu-id="c5bfa-183">최소 메모리 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-183">High memory percent</span></span>](#high-memory-percent)
- [<span data-ttu-id="c5bfa-184">개체별 힙 제한</span><span class="sxs-lookup"><span data-stu-id="c5bfa-184">Per-object-heap limits</span></span>](#per-object-heap-limits)
- [<span data-ttu-id="c5bfa-185">개체별-힙 제한 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-185">Per-object-heap limit percents</span></span>](#per-object-heap-limit-percents)
- [<span data-ttu-id="c5bfa-186">VM 유지</span><span class="sxs-lookup"><span data-stu-id="c5bfa-186">Retain VM</span></span>](#retain-vm)

<span data-ttu-id="c5bfa-187">이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-187">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="heap-count"></a><span data-ttu-id="c5bfa-188">힙 수</span><span class="sxs-lookup"><span data-stu-id="c5bfa-188">Heap count</span></span>

- <span data-ttu-id="c5bfa-189">가비지 수집기가 생성하는 힙의 개수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-189">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="c5bfa-190">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-190">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c5bfa-191">[GC 프로세서 선호도](#affinitize)가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-191">If [GC processor affinity](#affinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="c5bfa-192">(정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 [선호도 지정 마스크](#affinitize-mask) 또는 [선호도 지정 범위](#affinitize-ranges) 설정을 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="c5bfa-192">(Use the [affinitize mask](#affinitize-mask) or [affinitize ranges](#affinitize-ranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="c5bfa-193">[GC 프로세서 선호도](#affinitize)를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-193">If [GC processor affinity](#affinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="c5bfa-194">자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-194">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="c5bfa-195">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-195">Setting name</span></span> | <span data-ttu-id="c5bfa-196">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-196">Values</span></span> | <span data-ttu-id="c5bfa-197">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-197">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-198">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-198">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="c5bfa-199">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-199">*decimal value*</span></span> | <span data-ttu-id="c5bfa-200">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-200">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-201">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-201">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="c5bfa-202">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-202">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-203">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-203">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-204">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-204">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-205">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="c5bfa-205">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="c5bfa-206">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-206">*decimal value*</span></span> | <span data-ttu-id="c5bfa-207">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c5bfa-207">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c5bfa-208">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-208">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="c5bfa-209">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-209">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-210">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-210">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-211">예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 0x10 또는 10으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-211">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="affinitize-mask"></a><span data-ttu-id="c5bfa-212">선호도 지정 마스크</span><span class="sxs-lookup"><span data-stu-id="c5bfa-212">Affinitize mask</span></span>

- <span data-ttu-id="c5bfa-213">가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-213">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="c5bfa-214">[GC 프로세서 선호도](#affinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-214">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="c5bfa-215">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-215">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c5bfa-216">값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-216">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="c5bfa-217">예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 0x3FF 또는 3FF)은 이진 표기법으로 0011 1111 1111입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-217">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="c5bfa-218">이는 처음 10개의 프로세서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-218">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="c5bfa-219">다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 0xFFC00 또는 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-219">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="c5bfa-220">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-220">Setting name</span></span> | <span data-ttu-id="c5bfa-221">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-221">Values</span></span> | <span data-ttu-id="c5bfa-222">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-222">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-223">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-223">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="c5bfa-224">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-224">*decimal value*</span></span> | <span data-ttu-id="c5bfa-225">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-225">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-226">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-226">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="c5bfa-227">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-227">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-228">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-228">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-229">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-229">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-230">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="c5bfa-230">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="c5bfa-231">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-231">*decimal value*</span></span> | <span data-ttu-id="c5bfa-232">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c5bfa-232">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c5bfa-233">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-233">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a><span data-ttu-id="c5bfa-234">선호도 지정 범위</span><span class="sxs-lookup"><span data-stu-id="c5bfa-234">Affinitize ranges</span></span>

- <span data-ttu-id="c5bfa-235">가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-235">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="c5bfa-236">이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 [System.GC.HeapAffinitizeMask](#affinitize-mask)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-236">This setting is similar to [System.GC.HeapAffinitizeMask](#affinitize-mask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="c5bfa-237">Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-237">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="c5bfa-238">[GC 프로세서 선호도](#affinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-238">If [GC processor affinity](#affinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="c5bfa-239">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-239">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c5bfa-240">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-240">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="c5bfa-241">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-241">Setting name</span></span> | <span data-ttu-id="c5bfa-242">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-242">Values</span></span> | <span data-ttu-id="c5bfa-243">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-243">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-244">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-244">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="c5bfa-245">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-245">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="c5bfa-246">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="c5bfa-246">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="c5bfa-247">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="c5bfa-247">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="c5bfa-248">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-248">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-249">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-249">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="c5bfa-250">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-250">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="c5bfa-251">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="c5bfa-251">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="c5bfa-252">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="c5bfa-252">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="c5bfa-253">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-253">.NET Core 3.0</span></span> |

<span data-ttu-id="c5bfa-254">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-254">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a><span data-ttu-id="c5bfa-255">CPU 그룹</span><span class="sxs-lookup"><span data-stu-id="c5bfa-255">CPU groups</span></span>

- <span data-ttu-id="c5bfa-256">가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-256">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="c5bfa-257">64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-257">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="c5bfa-258">가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-258">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="c5bfa-259">64비트 Windows 운영 체제의 서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-259">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="c5bfa-260">기본값: GC가 CPU 그룹 간에 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-260">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="c5bfa-261">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-261">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="c5bfa-262">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-262">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="c5bfa-263">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-263">Setting name</span></span> | <span data-ttu-id="c5bfa-264">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-264">Values</span></span> | <span data-ttu-id="c5bfa-265">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-265">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-266">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-266">**runtimeconfig.json**</span></span> | `System.GC.CpuGroup` | <span data-ttu-id="c5bfa-267">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-267">`0` - disabled</span></span><br/><span data-ttu-id="c5bfa-268">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-268">`1` - enabled</span></span> | <span data-ttu-id="c5bfa-269">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-269">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-270">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-270">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="c5bfa-271">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-271">`0` - disabled</span></span><br/><span data-ttu-id="c5bfa-272">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-272">`1` - enabled</span></span> | <span data-ttu-id="c5bfa-273">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-273">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-274">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-274">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-275">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="c5bfa-275">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="c5bfa-276">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-276">`false` - disabled</span></span><br/><span data-ttu-id="c5bfa-277">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-277">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="c5bfa-278">모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-278">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="c5bfa-279">.NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-279">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="affinitize"></a><span data-ttu-id="c5bfa-280">선호도 지정</span><span class="sxs-lookup"><span data-stu-id="c5bfa-280">Affinitize</span></span>

- <span data-ttu-id="c5bfa-281">가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-281">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="c5bfa-282">GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-282">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="c5bfa-283">각 GC 스레드에 대해 힙이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-283">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="c5bfa-284">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-284">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="c5bfa-285">기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-285">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="c5bfa-286">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-286">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="c5bfa-287">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-287">Setting name</span></span> | <span data-ttu-id="c5bfa-288">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-288">Values</span></span> | <span data-ttu-id="c5bfa-289">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-289">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-290">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-290">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="c5bfa-291">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="c5bfa-291">`false` - affinitize</span></span><br/><span data-ttu-id="c5bfa-292">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-292">`true` - don't affinitize</span></span> | <span data-ttu-id="c5bfa-293">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-293">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-294">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-294">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="c5bfa-295">`0` - 선호</span><span class="sxs-lookup"><span data-stu-id="c5bfa-295">`0` - affinitize</span></span><br/><span data-ttu-id="c5bfa-296">`1` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-296">`1` - don't affinitize</span></span> | <span data-ttu-id="c5bfa-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-298">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-298">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-299">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="c5bfa-299">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="c5bfa-300">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="c5bfa-300">`false` - affinitize</span></span><br/><span data-ttu-id="c5bfa-301">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-301">`true` - don't affinitize</span></span> | <span data-ttu-id="c5bfa-302">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="c5bfa-302">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="c5bfa-303">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-303">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a><span data-ttu-id="c5bfa-304">힙 제한</span><span class="sxs-lookup"><span data-stu-id="c5bfa-304">Heap limit</span></span>

- <span data-ttu-id="c5bfa-305">GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-305">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="c5bfa-306">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-306">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="c5bfa-307">[개체별 힙 제한](#per-object-heap-limits)을 구성하면 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-307">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="c5bfa-308">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 큰 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-308">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="c5bfa-309">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-309">The default value applies if:</span></span>

  - <span data-ttu-id="c5bfa-310">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-310">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="c5bfa-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-311">[System.GC.HeapHardLimitPercent](#heap-limit-percent) is not set.</span></span>

| | <span data-ttu-id="c5bfa-312">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-312">Setting name</span></span> | <span data-ttu-id="c5bfa-313">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-313">Values</span></span> | <span data-ttu-id="c5bfa-314">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-314">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-315">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-315">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="c5bfa-316">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-316">*decimal value*</span></span> | <span data-ttu-id="c5bfa-317">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-317">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-318">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-318">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="c5bfa-319">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-319">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-320">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-320">.NET Core 3.0</span></span> |

<span data-ttu-id="c5bfa-321">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-321">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="c5bfa-322">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-322">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-323">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-323">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-324">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-324">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="heap-limit-percent"></a><span data-ttu-id="c5bfa-325">힙 제한 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-325">Heap limit percent</span></span>

- <span data-ttu-id="c5bfa-326">허용되는 GC 힙 사용량을 총 실제 메모리의 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-326">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="c5bfa-327">[System.GC.HeapHardLimit](#heap-limit)이 설정되는 경우에도 이 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-327">If [System.GC.HeapHardLimit](#heap-limit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="c5bfa-328">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-328">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="c5bfa-329">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우 백분율은 해당 메모리 제한의 백분율로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-329">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="c5bfa-330">[개체별 힙 제한](#per-object-heap-limits)을 구성하면 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-330">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="c5bfa-331">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 작은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-331">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="c5bfa-332">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-332">The default value applies if:</span></span>

  - <span data-ttu-id="c5bfa-333">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-333">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="c5bfa-334">[System.GC.HeapHardLimit](#heap-limit)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-334">[System.GC.HeapHardLimit](#heap-limit) is not set.</span></span>

| | <span data-ttu-id="c5bfa-335">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-335">Setting name</span></span> | <span data-ttu-id="c5bfa-336">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-336">Values</span></span> | <span data-ttu-id="c5bfa-337">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-337">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-338">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-338">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="c5bfa-339">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-339">*decimal value*</span></span> | <span data-ttu-id="c5bfa-340">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-340">.NET Core 3.0</span></span> |
| <span data-ttu-id="c5bfa-341">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-341">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="c5bfa-342">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-342">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-343">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-343">.NET Core 3.0</span></span> |

<span data-ttu-id="c5bfa-344">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-344">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="c5bfa-345">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-345">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-346">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-346">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-347">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-347">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="c5bfa-348">개체별 힙 제한</span><span class="sxs-lookup"><span data-stu-id="c5bfa-348">Per-object-heap limits</span></span>

<span data-ttu-id="c5bfa-349">개체별 힙을 기준으로 GC의 허용되는 힙 사용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-349">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="c5bfa-350">LOH(대형 개체 힙), SOH(작은 개체 힙), POH(고정 개체 힙) 등의 다양한 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-350">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="c5bfa-351">`COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` 또는 `COMPLUS_GCHeapHardLimitPOH` 설정 중 하나의 값을 지정하는 경우 `COMPLUS_GCHeapHardLimitSOH` 및 `COMPLUS_GCHeapHardLimitLOH`의 값도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-351">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="c5bfa-352">그러지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-352">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="c5bfa-353">`COMPLUS_GCHeapHardLimitPOH`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-353">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="c5bfa-354">`COMPLUS_GCHeapHardLimitSOH` 및 `COMPLUS_GCHeapHardLimitLOH`에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-354">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="c5bfa-355">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-355">Setting name</span></span> | <span data-ttu-id="c5bfa-356">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-356">Values</span></span> | <span data-ttu-id="c5bfa-357">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-358">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOH` | <span data-ttu-id="c5bfa-359">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-359">*decimal value*</span></span> | <span data-ttu-id="c5bfa-360">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-360">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-361">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-361">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="c5bfa-362">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-362">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-363">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-363">.NET 5.0</span></span> |

| | <span data-ttu-id="c5bfa-364">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-364">Setting name</span></span> | <span data-ttu-id="c5bfa-365">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-365">Values</span></span> | <span data-ttu-id="c5bfa-366">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-366">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-367">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-367">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOH` | <span data-ttu-id="c5bfa-368">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-368">*decimal value*</span></span> | <span data-ttu-id="c5bfa-369">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-369">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-370">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-370">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="c5bfa-371">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-371">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-372">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-372">.NET 5.0</span></span> |

| | <span data-ttu-id="c5bfa-373">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-373">Setting name</span></span> | <span data-ttu-id="c5bfa-374">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-374">Values</span></span> | <span data-ttu-id="c5bfa-375">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-375">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-376">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-376">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOH` | <span data-ttu-id="c5bfa-377">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-377">*decimal value*</span></span> | <span data-ttu-id="c5bfa-378">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-378">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-379">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-379">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="c5bfa-380">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-380">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-381">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-381">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="c5bfa-382">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-382">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-383">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-383">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-384">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-384">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="per-object-heap-limit-percents"></a><span data-ttu-id="c5bfa-385">개체별-힙 제한 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-385">Per-object-heap limit percents</span></span>

<span data-ttu-id="c5bfa-386">개체별 힙을 기준으로 GC의 허용되는 힙 사용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-386">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="c5bfa-387">LOH(대형 개체 힙), SOH(작은 개체 힙), POH(고정 개체 힙) 등의 다양한 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-387">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

- <span data-ttu-id="c5bfa-388">`COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` 또는 `COMPLUS_GCHeapHardLimitPOHPercent` 설정 중 하나의 값을 지정하는 경우 `COMPLUS_GCHeapHardLimitSOHPercent` 및 `COMPLUS_GCHeapHardLimitLOHPercent`의 값도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-388">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="c5bfa-389">그러지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-389">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="c5bfa-390">`COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` 및 `COMPLUS_GCHeapHardLimitPOH`를 지정하면 해당 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-390">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="c5bfa-391">값이 1이면 GC가 해당 개체 힙의 총 실제 메모리 중 1%를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-391">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="c5bfa-392">각 값은 0보다 크고 100보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-392">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="c5bfa-393">또한 백분율 값 3개의 합계는 100보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-393">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="c5bfa-394">그렇지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-394">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="c5bfa-395">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-395">Setting name</span></span> | <span data-ttu-id="c5bfa-396">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-396">Values</span></span> | <span data-ttu-id="c5bfa-397">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-397">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-398">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-398">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitSOHPercent` | <span data-ttu-id="c5bfa-399">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-399">*decimal value*</span></span> | <span data-ttu-id="c5bfa-400">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-400">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-401">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-401">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="c5bfa-402">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-402">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-403">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-403">.NET 5.0</span></span> |

| | <span data-ttu-id="c5bfa-404">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-404">Setting name</span></span> | <span data-ttu-id="c5bfa-405">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-405">Values</span></span> | <span data-ttu-id="c5bfa-406">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-406">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-407">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-407">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitLOHPercent` | <span data-ttu-id="c5bfa-408">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-408">*decimal value*</span></span> | <span data-ttu-id="c5bfa-409">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-409">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-410">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-410">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="c5bfa-411">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-411">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-412">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-412">.NET 5.0</span></span> |

| | <span data-ttu-id="c5bfa-413">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-413">Setting name</span></span> | <span data-ttu-id="c5bfa-414">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-414">Values</span></span> | <span data-ttu-id="c5bfa-415">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-416">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPOHPercent` | <span data-ttu-id="c5bfa-417">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-417">*decimal value*</span></span> | <span data-ttu-id="c5bfa-418">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-418">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-419">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-419">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="c5bfa-420">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-420">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-421">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-421">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="c5bfa-422">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-422">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-423">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-423">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-424">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-424">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="high-memory-percent"></a><span data-ttu-id="c5bfa-425">최소 메모리 비율</span><span class="sxs-lookup"><span data-stu-id="c5bfa-425">High memory percent</span></span>

<span data-ttu-id="c5bfa-426">메모리 로드는 사용 중인 실제 메모리의 비율로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-426">Memory load is indicated by the percentage of physical memory in use.</span></span> <span data-ttu-id="c5bfa-427">기본적으로 실제 메모리 부하가 **90%** 에 도달하면 가비지 수집은 페이징이 발생하지 않도록 더 적극적으로 가비지 수집을 꽉 채우고 완전히 압축하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-427">By default, when the physical memory load reaches **90%**, garbage collection becomes more aggressive about doing full, compacting garbage collections to avoid paging.</span></span> <span data-ttu-id="c5bfa-428">메모리 부하가 90% 미만이면 GC는 전체 가비지 수집을 백그라운드에서 수행하여 일시 중지 시간을 줄이면서 전체 힙 크기는 크게 줄이지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-428">When memory load is below 90%, GC favors background collections for full garbage collections, which have shorter pauses but don't reduce the total heap size by much.</span></span> <span data-ttu-id="c5bfa-429">많은 양의 메모리(80GB 이상)를 사용하는 머신에서 기본 부하 임계값은 90~97%입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-429">On machines with a significant amount of memory (80GB or more), the default load threshold is between 90% and 97%.</span></span>

<span data-ttu-id="c5bfa-430">높은 메모리 부하 임계값은 `COMPlus_GCHighMemPercent` 환경 변수 또는 `System.GC.HighMemoryPercent` JSON 구성 설정으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-430">The high memory load threshold can be adjusted by the `COMPlus_GCHighMemPercent` environment variable or `System.GC.HighMemoryPercent` JSON configuration setting.</span></span> <span data-ttu-id="c5bfa-431">힙 크기를 제어하려면 임계값을 조정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-431">Consider adjusting the threshold if you want to control heap size.</span></span> <span data-ttu-id="c5bfa-432">예를 들어 메모리가 64GB인 컴퓨터의 주요 프로세스의 경우, 가용 메모리가 10%가 되면 GC가 반응하기 시작하는 것이 합당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-432">For example, for the dominant process on a machine with 64GB of memory, it's reasonable for GC to start reacting when there's 10% of memory available.</span></span> <span data-ttu-id="c5bfa-433">그러나 작은 프로세스(예: 1GB 메모리만 사용하는 프로세스)의 경우 가용 메모리가 10% 미만일 때도 GC가 최적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-433">But for smaller processes, for example, a process that only consumes 1GB of memory, GC can comfortably run with less than 10% of memory available.</span></span> <span data-ttu-id="c5bfa-434">이러한 작은 프로세스의 경우 임계값을 높게 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-434">For these smaller processes, consider setting the threshold higher.</span></span> <span data-ttu-id="c5bfa-435">반면, 큰 프로세스의 힙 크기를 더 작게 유지하려는 경우(사용할 수 있는 실제 메모리가 많은 경우에도) 이 임계값을 낮추는 것은 GC가 더 빠르게 반응하여 힙을 압축하게 되는 효과적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-435">On the other hand, if you want larger processes to have smaller heap sizes (even when there's plenty of physical memory available), lowering this threshold is an effective way for GC to react sooner to compact the heap down.</span></span>

> [!NOTE]
> <span data-ttu-id="c5bfa-436">컨테이너에서 실행되는 프로세스의 경우 GC는 컨테이너 제한을 기준으로 실제 메모리를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-436">For processes running in a container, GC considers the physical memory based on the container limit.</span></span>

| | <span data-ttu-id="c5bfa-437">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-437">Setting name</span></span> | <span data-ttu-id="c5bfa-438">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-438">Values</span></span> | <span data-ttu-id="c5bfa-439">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-439">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-440">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-440">**runtimeconfig.json**</span></span> | `System.GC.HighMemoryPercent` | <span data-ttu-id="c5bfa-441">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-441">*decimal value*</span></span> | <span data-ttu-id="c5bfa-442">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-442">.NET 5.0</span></span> |
| <span data-ttu-id="c5bfa-443">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-443">**Environment variable**</span></span> | `COMPlus_GCHighMemPercent` | <span data-ttu-id="c5bfa-444">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-444">*hexadecimal value*</span></span> | |

> [!TIP]
> <span data-ttu-id="c5bfa-445">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-445">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-446">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-446">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-447">예를 들어 높은 메모리 임계값을 75%로 설정하려면 JSON 파일의 경우 값을 75로 지정하고, 환경 변수의 경우 값을 0x4B 또는 4B로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-447">For example, to set the high memory threshold to 75%, the values would be 75 for the JSON file and 0x4B or 4B for the environment variable.</span></span>

### <a name="retain-vm"></a><span data-ttu-id="c5bfa-448">VM 유지</span><span class="sxs-lookup"><span data-stu-id="c5bfa-448">Retain VM</span></span>

- <span data-ttu-id="c5bfa-449">삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-449">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="c5bfa-450">기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-450">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="c5bfa-451">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-451">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="c5bfa-452">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-452">Setting name</span></span> | <span data-ttu-id="c5bfa-453">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-453">Values</span></span> | <span data-ttu-id="c5bfa-454">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-454">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-455">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-455">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="c5bfa-456">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="c5bfa-456">`false` - release to OS</span></span><br/><span data-ttu-id="c5bfa-457">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="c5bfa-457">`true` - put on standby</span></span> | <span data-ttu-id="c5bfa-458">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-458">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-459">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-459">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="c5bfa-460">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="c5bfa-460">`false` - release to OS</span></span><br/><span data-ttu-id="c5bfa-461">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="c5bfa-461">`true` - put on standby</span></span> | <span data-ttu-id="c5bfa-462">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-462">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-463">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-463">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="c5bfa-464">`0` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="c5bfa-464">`0` - release to OS</span></span><br/><span data-ttu-id="c5bfa-465">`1` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="c5bfa-465">`1` - put on standby</span></span> | <span data-ttu-id="c5bfa-466">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-466">.NET Core 1.0</span></span> |

#### <a name="examples"></a><span data-ttu-id="c5bfa-467">예</span><span class="sxs-lookup"><span data-stu-id="c5bfa-467">Examples</span></span>

<span data-ttu-id="c5bfa-468">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-468">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="c5bfa-469">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-469">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="c5bfa-470">큰 페이지</span><span class="sxs-lookup"><span data-stu-id="c5bfa-470">Large pages</span></span>

- <span data-ttu-id="c5bfa-471">힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-471">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="c5bfa-472">기본값: 힙 하드 한도가 설정된 경우 대용량 페이지를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-472">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="c5bfa-473">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-473">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="c5bfa-474">이것은 실험적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-474">This is an experimental setting.</span></span>

| | <span data-ttu-id="c5bfa-475">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-475">Setting name</span></span> | <span data-ttu-id="c5bfa-476">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-476">Values</span></span> | <span data-ttu-id="c5bfa-477">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-477">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-478">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-478">**runtimeconfig.json**</span></span> | <span data-ttu-id="c5bfa-479">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-479">N/A</span></span> | <span data-ttu-id="c5bfa-480">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-480">N/A</span></span> | <span data-ttu-id="c5bfa-481">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-481">N/A</span></span> |
| <span data-ttu-id="c5bfa-482">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-482">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="c5bfa-483">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-483">`0` - disabled</span></span><br/><span data-ttu-id="c5bfa-484">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-484">`1` - enabled</span></span> | <span data-ttu-id="c5bfa-485">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-485">.NET Core 3.0</span></span> |

## <a name="allow-large-objects"></a><span data-ttu-id="c5bfa-486">대형 개체 허용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-486">Allow large objects</span></span>

- <span data-ttu-id="c5bfa-487">64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-487">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="c5bfa-488">기본값: GC가 2GB를 초과하는 배열을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-488">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="c5bfa-489">이는 값을 `1`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-489">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="c5bfa-490">이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-490">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="c5bfa-491">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-491">Setting name</span></span> | <span data-ttu-id="c5bfa-492">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-492">Values</span></span> | <span data-ttu-id="c5bfa-493">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-493">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-494">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-494">**runtimeconfig.json**</span></span> | <span data-ttu-id="c5bfa-495">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-495">N/A</span></span> | <span data-ttu-id="c5bfa-496">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-496">N/A</span></span> | <span data-ttu-id="c5bfa-497">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-497">N/A</span></span> |
| <span data-ttu-id="c5bfa-498">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-498">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="c5bfa-499">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-499">`1` - enabled</span></span><br/> <span data-ttu-id="c5bfa-500">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-500">`0` - disabled</span></span> | <span data-ttu-id="c5bfa-501">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-501">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-502">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-502">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-503">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="c5bfa-503">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="c5bfa-504">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="c5bfa-504">`1` - enabled</span></span><br/> <span data-ttu-id="c5bfa-505">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="c5bfa-505">`0` - disabled</span></span> | <span data-ttu-id="c5bfa-506">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="c5bfa-506">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="c5bfa-507">큰 개체 힙 임계값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-507">Large object heap threshold</span></span>

- <span data-ttu-id="c5bfa-508">개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-508">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="c5bfa-509">기본 임계값은 85,000바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-509">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="c5bfa-510">사용자가 지정하는 값은 기본 임계값보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-510">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="c5bfa-511">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-511">Setting name</span></span> | <span data-ttu-id="c5bfa-512">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-512">Values</span></span> | <span data-ttu-id="c5bfa-513">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-513">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-514">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-514">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="c5bfa-515">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-515">*decimal value*</span></span> | <span data-ttu-id="c5bfa-516">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-516">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-517">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-517">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="c5bfa-518">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-518">*hexadecimal value*</span></span> | <span data-ttu-id="c5bfa-519">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-519">.NET Core 1.0</span></span> |
| <span data-ttu-id="c5bfa-520">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-520">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="c5bfa-521">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="c5bfa-521">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="c5bfa-522">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-522">*decimal value*</span></span> | <span data-ttu-id="c5bfa-523">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="c5bfa-523">.NET Framework 4.8</span></span> |

<span data-ttu-id="c5bfa-524">예:</span><span class="sxs-lookup"><span data-stu-id="c5bfa-524">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> <span data-ttu-id="c5bfa-525">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-525">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="c5bfa-526">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-526">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="c5bfa-527">예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 0x1D4C0 또는 1D4C0으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-527">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="c5bfa-528">독립 실행형 GC</span><span class="sxs-lookup"><span data-stu-id="c5bfa-528">Standalone GC</span></span>

- <span data-ttu-id="c5bfa-529">런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-529">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="c5bfa-530">자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5bfa-530">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="c5bfa-531">설정 이름</span><span class="sxs-lookup"><span data-stu-id="c5bfa-531">Setting name</span></span> | <span data-ttu-id="c5bfa-532">값</span><span class="sxs-lookup"><span data-stu-id="c5bfa-532">Values</span></span> | <span data-ttu-id="c5bfa-533">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c5bfa-533">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="c5bfa-534">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-534">**runtimeconfig.json**</span></span> | <span data-ttu-id="c5bfa-535">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-535">N/A</span></span> | <span data-ttu-id="c5bfa-536">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-536">N/A</span></span> | <span data-ttu-id="c5bfa-537">N/A</span><span class="sxs-lookup"><span data-stu-id="c5bfa-537">N/A</span></span> |
| <span data-ttu-id="c5bfa-538">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="c5bfa-538">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="c5bfa-539">*string_path*</span><span class="sxs-lookup"><span data-stu-id="c5bfa-539">*string_path*</span></span> | <span data-ttu-id="c5bfa-540">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c5bfa-540">.NET Core 2.0</span></span> |
