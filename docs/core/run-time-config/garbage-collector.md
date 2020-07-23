---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 6ae5b7447fb0df4978ea9dcaa5e76fcc7a6cc4ca
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441411"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="21a9f-103">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="21a9f-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="21a9f-104">이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="21a9f-105">실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="21a9f-106">그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="21a9f-107">이 페이지에서는 설정이 그룹별로 정리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="21a9f-108">각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="21a9f-109">이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="21a9f-110">[대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="21a9f-111">이러한 설정은 이 페이지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="21a9f-112">숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="21a9f-113">16진수 값의 경우 “0x” 접두사를 사용하거나 사용하지 않고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="21a9f-114">가비지 수집 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-114">Flavors of garbage collection</span></span>

<span data-ttu-id="21a9f-115">가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="21a9f-116">둘 사이의 차이점에 대한 자세한 내용은 [워크스테이션 및 가비지 수집](../../standard/garbage-collection/workstation-server-gc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-116">For more information about differences between the two, see [Workstation and server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span>

<span data-ttu-id="21a9f-117">가비지 수집의 하위 버전은 백그라운드와 비동시입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="21a9f-118">다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="21a9f-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="21a9f-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="21a9f-120">애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="21a9f-121">기본값: 워크스테이션 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="21a9f-121">Default: Workstation garbage collection.</span></span> <span data-ttu-id="21a9f-122">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-122">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="21a9f-123">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-123">Setting name</span></span> | <span data-ttu-id="21a9f-124">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-124">Values</span></span> | <span data-ttu-id="21a9f-125">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-125">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-126">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="21a9f-127">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="21a9f-127">`false` - workstation</span></span><br/><span data-ttu-id="21a9f-128">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="21a9f-128">`true` - server</span></span> | <span data-ttu-id="21a9f-129">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-129">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-130">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="21a9f-130">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="21a9f-131">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="21a9f-131">`false` - workstation</span></span><br/><span data-ttu-id="21a9f-132">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="21a9f-132">`true` - server</span></span> | <span data-ttu-id="21a9f-133">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-133">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-134">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-134">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="21a9f-135">`0` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="21a9f-135">`0` - workstation</span></span><br/><span data-ttu-id="21a9f-136">`1` - 서버</span><span class="sxs-lookup"><span data-stu-id="21a9f-136">`1` - server</span></span> | <span data-ttu-id="21a9f-137">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-137">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-138">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-138">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-139">GCServer</span><span class="sxs-lookup"><span data-stu-id="21a9f-139">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="21a9f-140">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="21a9f-140">`false` - workstation</span></span><br/><span data-ttu-id="21a9f-141">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="21a9f-141">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="21a9f-142">예</span><span class="sxs-lookup"><span data-stu-id="21a9f-142">Examples</span></span>

<span data-ttu-id="21a9f-143">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-143">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="21a9f-144">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-144">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="21a9f-145">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="21a9f-145">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="21a9f-146">백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-146">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="21a9f-147">기본값: 백그라운드 GC를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-147">Default: Use background GC.</span></span> <span data-ttu-id="21a9f-148">이는 값을 `true`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-148">This is equivalent to setting the value to `true`.</span></span>
- <span data-ttu-id="21a9f-149">자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/background-gc.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-149">For more information, see [Background garbage collection](../../standard/garbage-collection/background-gc.md).</span></span>

| | <span data-ttu-id="21a9f-150">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-150">Setting name</span></span> | <span data-ttu-id="21a9f-151">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-151">Values</span></span> | <span data-ttu-id="21a9f-152">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-152">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-153">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-153">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="21a9f-154">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-154">`true` - background GC</span></span><br/><span data-ttu-id="21a9f-155">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-155">`false` - non-concurrent GC</span></span> | <span data-ttu-id="21a9f-156">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-156">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-157">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="21a9f-157">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="21a9f-158">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-158">`true` - background GC</span></span><br/><span data-ttu-id="21a9f-159">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-159">`false` - non-concurrent GC</span></span> | <span data-ttu-id="21a9f-160">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-160">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-161">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-161">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="21a9f-162">`1` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-162">`1` - background GC</span></span><br/><span data-ttu-id="21a9f-163">`0` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-163">`0` - non-concurrent GC</span></span> | <span data-ttu-id="21a9f-164">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-164">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-165">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-165">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-166">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="21a9f-166">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="21a9f-167">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-167">`true` - background GC</span></span><br/><span data-ttu-id="21a9f-168">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-168">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="21a9f-169">예</span><span class="sxs-lookup"><span data-stu-id="21a9f-169">Examples</span></span>

<span data-ttu-id="21a9f-170">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-170">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="21a9f-171">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-171">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="21a9f-172">리소스 사용량 관리</span><span class="sxs-lookup"><span data-stu-id="21a9f-172">Manage resource usage</span></span>

<span data-ttu-id="21a9f-173">이 섹션에서 설명하는 설정은 가비지 수집기의 메모리 및 프로세서 사용량을 관리하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-173">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="21a9f-174">이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-174">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="21a9f-175">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="21a9f-175">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="21a9f-176">가비지 수집기가 생성하는 힙의 개수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-176">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="21a9f-177">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-177">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="21a9f-178">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="21a9f-179">(정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 [선호도 지정 마스크](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) 또는 [선호도 지정 범위](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) 설정을 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="21a9f-179">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="21a9f-180">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-180">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="21a9f-181">자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-181">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="21a9f-182">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-182">Setting name</span></span> | <span data-ttu-id="21a9f-183">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-183">Values</span></span> | <span data-ttu-id="21a9f-184">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-184">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-185">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-185">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="21a9f-186">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-186">*decimal value*</span></span> | <span data-ttu-id="21a9f-187">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-187">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-188">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-188">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="21a9f-189">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-189">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-190">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-190">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-191">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-191">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-192">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="21a9f-192">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="21a9f-193">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-193">*decimal value*</span></span> | <span data-ttu-id="21a9f-194">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="21a9f-194">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="21a9f-195">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-195">Example:</span></span>

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
> <span data-ttu-id="21a9f-196">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-196">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="21a9f-197">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-197">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-198">예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 0x10 또는 10으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-198">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="21a9f-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="21a9f-199">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="21a9f-200">가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-200">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="21a9f-201">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-201">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="21a9f-202">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-202">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="21a9f-203">값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-203">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="21a9f-204">예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 0x3FF 또는 3FF)은 이진 표기법으로 0011 1111 1111입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-204">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="21a9f-205">이는 처음 10개의 프로세서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-205">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="21a9f-206">다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 0xFFC00 또는 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-206">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="21a9f-207">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-207">Setting name</span></span> | <span data-ttu-id="21a9f-208">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-208">Values</span></span> | <span data-ttu-id="21a9f-209">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-209">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-210">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-210">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="21a9f-211">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-211">*decimal value*</span></span> | <span data-ttu-id="21a9f-212">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-212">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-213">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-213">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="21a9f-214">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-214">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-215">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-215">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-216">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-216">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-217">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="21a9f-217">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="21a9f-218">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-218">*decimal value*</span></span> | <span data-ttu-id="21a9f-219">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="21a9f-219">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="21a9f-220">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-220">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="21a9f-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="21a9f-221">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="21a9f-222">가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-222">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="21a9f-223">이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-223">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="21a9f-224">Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-224">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="21a9f-225">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-225">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="21a9f-226">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-226">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="21a9f-227">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-227">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="21a9f-228">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-228">Setting name</span></span> | <span data-ttu-id="21a9f-229">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-229">Values</span></span> | <span data-ttu-id="21a9f-230">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-230">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-231">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-231">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="21a9f-232">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="21a9f-232">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="21a9f-233">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="21a9f-233">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="21a9f-234">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="21a9f-234">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="21a9f-235">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-235">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-236">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-236">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="21a9f-237">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="21a9f-237">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="21a9f-238">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="21a9f-238">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="21a9f-239">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="21a9f-239">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="21a9f-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-240">.NET Core 3.0</span></span> |

<span data-ttu-id="21a9f-241">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-241">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="21a9f-242">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="21a9f-242">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="21a9f-243">가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-243">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="21a9f-244">64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-244">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="21a9f-245">가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-245">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="21a9f-246">64비트 Windows 운영 체제의 서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-246">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="21a9f-247">기본값: GC가 CPU 그룹 간에 확장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-247">Default: GC does not extend across CPU groups.</span></span> <span data-ttu-id="21a9f-248">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-248">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="21a9f-249">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-249">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="21a9f-250">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-250">Setting name</span></span> | <span data-ttu-id="21a9f-251">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-251">Values</span></span> | <span data-ttu-id="21a9f-252">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-252">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-253">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-253">**runtimeconfig.json**</span></span> | <span data-ttu-id="21a9f-254">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-254">N/A</span></span> | <span data-ttu-id="21a9f-255">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-255">N/A</span></span> | <span data-ttu-id="21a9f-256">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-256">N/A</span></span> |
| <span data-ttu-id="21a9f-257">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-257">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="21a9f-258">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-258">`0` - disabled</span></span><br/><span data-ttu-id="21a9f-259">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="21a9f-259">`1` - enabled</span></span> | <span data-ttu-id="21a9f-260">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-260">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-261">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-261">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-262">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="21a9f-262">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="21a9f-263">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-263">`false` - disabled</span></span><br/><span data-ttu-id="21a9f-264">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="21a9f-264">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="21a9f-265">모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-265">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="21a9f-266">.NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-266">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="21a9f-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="21a9f-267">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="21a9f-268">가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-268">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="21a9f-269">GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-269">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="21a9f-270">각 GC 스레드에 대해 힙이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-270">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="21a9f-271">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-271">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="21a9f-272">기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-272">Default: Affinitize garbage collection threads with processors.</span></span> <span data-ttu-id="21a9f-273">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-273">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="21a9f-274">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-274">Setting name</span></span> | <span data-ttu-id="21a9f-275">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-275">Values</span></span> | <span data-ttu-id="21a9f-276">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-276">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-277">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-277">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="21a9f-278">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="21a9f-278">`false` - affinitize</span></span><br/><span data-ttu-id="21a9f-279">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-279">`true` - don't affinitize</span></span> | <span data-ttu-id="21a9f-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-281">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-281">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="21a9f-282">`0` - 선호</span><span class="sxs-lookup"><span data-stu-id="21a9f-282">`0` - affinitize</span></span><br/><span data-ttu-id="21a9f-283">`1` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-283">`1` - don't affinitize</span></span> | <span data-ttu-id="21a9f-284">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-284">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-285">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-285">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-286">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="21a9f-286">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="21a9f-287">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="21a9f-287">`false` - affinitize</span></span><br/><span data-ttu-id="21a9f-288">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-288">`true` - don't affinitize</span></span> | <span data-ttu-id="21a9f-289">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="21a9f-289">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="21a9f-290">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-290">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="21a9f-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="21a9f-291">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="21a9f-292">GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-292">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="21a9f-293">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-293">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="21a9f-294">[개체별 힙 제한](#per-object-heap-limits)을 구성하면 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-294">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="21a9f-295">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 큰 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-295">The default value, which only applies in certain cases, is the greater of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="21a9f-296">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-296">The default value applies if:</span></span>

  - <span data-ttu-id="21a9f-297">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="21a9f-297">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="21a9f-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="21a9f-298">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="21a9f-299">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-299">Setting name</span></span> | <span data-ttu-id="21a9f-300">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-300">Values</span></span> | <span data-ttu-id="21a9f-301">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-301">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-302">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-302">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="21a9f-303">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-303">*decimal value*</span></span> | <span data-ttu-id="21a9f-304">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-304">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-305">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-305">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="21a9f-306">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-306">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-307">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-307">.NET Core 3.0</span></span> |

<span data-ttu-id="21a9f-308">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-308">Example:</span></span>

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
> <span data-ttu-id="21a9f-309">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-309">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="21a9f-310">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-310">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-311">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-311">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="21a9f-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="21a9f-312">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="21a9f-313">허용되는 GC 힙 사용량을 총 실제 메모리의 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-313">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="21a9f-314">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)이 설정되는 경우에도 이 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-314">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="21a9f-315">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-315">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="21a9f-316">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우 백분율은 해당 메모리 제한의 백분율로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-316">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="21a9f-317">[개체별 힙 제한](#per-object-heap-limits)을 구성하면 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-317">This setting is ignored if the [Per-object-heap limits](#per-object-heap-limits) are configured.</span></span>
- <span data-ttu-id="21a9f-318">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 작은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-318">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="21a9f-319">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-319">The default value applies if:</span></span>

  - <span data-ttu-id="21a9f-320">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="21a9f-320">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="21a9f-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="21a9f-321">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="21a9f-322">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-322">Setting name</span></span> | <span data-ttu-id="21a9f-323">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-323">Values</span></span> | <span data-ttu-id="21a9f-324">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-324">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-325">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-325">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="21a9f-326">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-326">*decimal value*</span></span> | <span data-ttu-id="21a9f-327">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-327">.NET Core 3.0</span></span> |
| <span data-ttu-id="21a9f-328">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-328">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="21a9f-329">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-329">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-330">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-330">.NET Core 3.0</span></span> |

<span data-ttu-id="21a9f-331">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-331">Example:</span></span>

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
> <span data-ttu-id="21a9f-332">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-332">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="21a9f-333">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-333">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-334">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-334">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="per-object-heap-limits"></a><span data-ttu-id="21a9f-335">개체별 힙 제한</span><span class="sxs-lookup"><span data-stu-id="21a9f-335">Per-object-heap limits</span></span>

<span data-ttu-id="21a9f-336">개체별 힙을 기준으로 GC의 허용되는 힙 사용량을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-336">You can specify the GC's allowable heap usage on a per-object-heap basis.</span></span> <span data-ttu-id="21a9f-337">LOH(대형 개체 힙), SOH(작은 개체 힙), POH(고정 개체 힙) 등의 다양한 힙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-337">The different heaps are the large object heap (LOH), small object heap (SOH), and pinned object heap (POH).</span></span>

#### <a name="complus_gcheaphardlimitsoh-complus_gcheaphardlimitloh-complus_gcheaphardlimitpoh"></a><span data-ttu-id="21a9f-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span><span class="sxs-lookup"><span data-stu-id="21a9f-338">COMPLUS_GCHeapHardLimitSOH, COMPLUS_GCHeapHardLimitLOH, COMPLUS_GCHeapHardLimitPOH</span></span>

- <span data-ttu-id="21a9f-339">`COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` 또는 `COMPLUS_GCHeapHardLimitPOH` 설정 중 하나의 값을 지정하는 경우 `COMPLUS_GCHeapHardLimitSOH` 및 `COMPLUS_GCHeapHardLimitLOH`의 값도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-339">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, or `COMPLUS_GCHeapHardLimitPOH` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH`.</span></span> <span data-ttu-id="21a9f-340">그러지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-340">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="21a9f-341">`COMPLUS_GCHeapHardLimitPOH`의 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-341">The default value for `COMPLUS_GCHeapHardLimitPOH` is 0.</span></span> <span data-ttu-id="21a9f-342">`COMPLUS_GCHeapHardLimitSOH` 및 `COMPLUS_GCHeapHardLimitLOH`에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-342">`COMPLUS_GCHeapHardLimitSOH` and `COMPLUS_GCHeapHardLimitLOH` don't have default values.</span></span>

| | <span data-ttu-id="21a9f-343">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-343">Setting name</span></span> | <span data-ttu-id="21a9f-344">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-344">Values</span></span> | <span data-ttu-id="21a9f-345">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-346">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-346">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOH` | <span data-ttu-id="21a9f-347">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-347">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-348">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-348">.NET 5.0</span></span> |
| <span data-ttu-id="21a9f-349">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-349">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOH` | <span data-ttu-id="21a9f-350">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-350">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-351">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-351">.NET 5.0</span></span> |
| <span data-ttu-id="21a9f-352">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-352">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOH` | <span data-ttu-id="21a9f-353">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-353">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-354">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-354">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="21a9f-355">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-355">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-356">예를 들어 힙 하드 제한인 200MiB(메비바이트)를 지정하려면 값은 0xC800000 또는 C800000이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-356">For example, to specify a heap hard limit of 200 mebibytes (MiB), the value would be 0xC800000 or C800000.</span></span>

#### <a name="complus_gcheaphardlimitsohpercent-complus_gcheaphardlimitlohpercent-complus_gcheaphardlimitpohpercent"></a><span data-ttu-id="21a9f-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span><span class="sxs-lookup"><span data-stu-id="21a9f-357">COMPLUS_GCHeapHardLimitSOHPercent, COMPLUS_GCHeapHardLimitLOHPercent, COMPLUS_GCHeapHardLimitPOHPercent</span></span>

- <span data-ttu-id="21a9f-358">`COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` 또는 `COMPLUS_GCHeapHardLimitPOHPercent` 설정 중 하나의 값을 지정하는 경우 `COMPLUS_GCHeapHardLimitSOHPercent` 및 `COMPLUS_GCHeapHardLimitLOHPercent`의 값도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-358">If you specify a value for any of the `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent`, or `COMPLUS_GCHeapHardLimitPOHPercent` settings, you must also specify a value for `COMPLUS_GCHeapHardLimitSOHPercent` and `COMPLUS_GCHeapHardLimitLOHPercent`.</span></span> <span data-ttu-id="21a9f-359">그러지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-359">If you don't, the runtime will fail to initialize.</span></span>
- <span data-ttu-id="21a9f-360">`COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` 및 `COMPLUS_GCHeapHardLimitPOH`를 지정하면 해당 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-360">These settings are ignored if `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH`, and `COMPLUS_GCHeapHardLimitPOH` are specified.</span></span>
- <span data-ttu-id="21a9f-361">값이 1이면 GC가 해당 개체 힙의 총 실제 메모리 중 1%를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-361">A value of 1 means that GC uses 1% of total physical memory for that object heap.</span></span>
- <span data-ttu-id="21a9f-362">각 값은 0보다 크고 100보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-362">Each value must be greater than zero and less than 100.</span></span> <span data-ttu-id="21a9f-363">또한 백분율 값 3개의 합계는 100보다 작아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-363">Additionally, the sum of the three percentage values must be less than 100.</span></span> <span data-ttu-id="21a9f-364">그렇지 않으면 런타임이 초기화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-364">Otherwise, the runtime will fail to initialize.</span></span>

| | <span data-ttu-id="21a9f-365">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-365">Setting name</span></span> | <span data-ttu-id="21a9f-366">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-366">Values</span></span> | <span data-ttu-id="21a9f-367">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-367">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-368">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-368">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitSOHPercent` | <span data-ttu-id="21a9f-369">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-369">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-370">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-370">.NET 5.0</span></span> |
| <span data-ttu-id="21a9f-371">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-371">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitLOHPercent` | <span data-ttu-id="21a9f-372">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-372">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-373">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-373">.NET 5.0</span></span> |
| <span data-ttu-id="21a9f-374">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-374">**Environment variable**</span></span> | `COMPLUS_GCHeapHardLimitPOHPercent` | <span data-ttu-id="21a9f-375">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-375">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-376">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-376">.NET 5.0</span></span> |

> [!TIP]
> <span data-ttu-id="21a9f-377">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-378">예를 들어 힙 사용량을 30%로 제한하려면 값은 0x1E 또는 1E가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-378">For example, to limit the heap usage to 30%, the value would be 0x1E or 1E.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="21a9f-379">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="21a9f-379">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="21a9f-380">삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-380">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="21a9f-381">기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-381">Default: Release segments back to the operating system.</span></span> <span data-ttu-id="21a9f-382">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-382">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="21a9f-383">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-383">Setting name</span></span> | <span data-ttu-id="21a9f-384">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-384">Values</span></span> | <span data-ttu-id="21a9f-385">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-386">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="21a9f-387">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="21a9f-387">`false` - release to OS</span></span><br/><span data-ttu-id="21a9f-388">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="21a9f-388">`true` - put on standby</span></span> | <span data-ttu-id="21a9f-389">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-389">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-390">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="21a9f-390">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="21a9f-391">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="21a9f-391">`false` - release to OS</span></span><br/><span data-ttu-id="21a9f-392">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="21a9f-392">`true` - put on standby</span></span> | <span data-ttu-id="21a9f-393">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-393">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-394">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-394">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="21a9f-395">`0` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="21a9f-395">`0` - release to OS</span></span><br/><span data-ttu-id="21a9f-396">`1` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="21a9f-396">`1` - put on standby</span></span> | <span data-ttu-id="21a9f-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-397">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="21a9f-398">예</span><span class="sxs-lookup"><span data-stu-id="21a9f-398">Examples</span></span>

<span data-ttu-id="21a9f-399">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-399">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="21a9f-400">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="21a9f-400">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="21a9f-401">큰 페이지</span><span class="sxs-lookup"><span data-stu-id="21a9f-401">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="21a9f-402">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="21a9f-402">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="21a9f-403">힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-403">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="21a9f-404">기본값: 힙 하드 한도가 설정된 경우 대용량 페이지를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-404">Default: Don't use large pages when a heap hard limit is set.</span></span> <span data-ttu-id="21a9f-405">이는 값을 `0`으로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-405">This is equivalent to setting the value to `0`.</span></span>
- <span data-ttu-id="21a9f-406">이것은 실험적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-406">This is an experimental setting.</span></span>

| | <span data-ttu-id="21a9f-407">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-407">Setting name</span></span> | <span data-ttu-id="21a9f-408">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-408">Values</span></span> | <span data-ttu-id="21a9f-409">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-409">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-410">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-410">**runtimeconfig.json**</span></span> | <span data-ttu-id="21a9f-411">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-411">N/A</span></span> | <span data-ttu-id="21a9f-412">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-412">N/A</span></span> | <span data-ttu-id="21a9f-413">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-413">N/A</span></span> |
| <span data-ttu-id="21a9f-414">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-414">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="21a9f-415">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-415">`0` - disabled</span></span><br/><span data-ttu-id="21a9f-416">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="21a9f-416">`1` - enabled</span></span> | <span data-ttu-id="21a9f-417">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-417">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="21a9f-418">큰 개체</span><span class="sxs-lookup"><span data-stu-id="21a9f-418">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="21a9f-419">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="21a9f-419">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="21a9f-420">64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-420">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="21a9f-421">기본값: GC가 2GB를 초과하는 배열을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-421">Default: GC supports arrays greater than 2-GB.</span></span> <span data-ttu-id="21a9f-422">이는 값을 `1`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-422">This is equivalent to setting the value to `1`.</span></span>
- <span data-ttu-id="21a9f-423">이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-423">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="21a9f-424">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-424">Setting name</span></span> | <span data-ttu-id="21a9f-425">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-425">Values</span></span> | <span data-ttu-id="21a9f-426">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-426">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-427">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-427">**runtimeconfig.json**</span></span> | <span data-ttu-id="21a9f-428">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-428">N/A</span></span> | <span data-ttu-id="21a9f-429">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-429">N/A</span></span> | <span data-ttu-id="21a9f-430">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-430">N/A</span></span> |
| <span data-ttu-id="21a9f-431">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-431">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="21a9f-432">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="21a9f-432">`1` - enabled</span></span><br/> <span data-ttu-id="21a9f-433">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-433">`0` - disabled</span></span> | <span data-ttu-id="21a9f-434">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-434">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-435">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-435">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-436">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="21a9f-436">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="21a9f-437">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="21a9f-437">`1` - enabled</span></span><br/> <span data-ttu-id="21a9f-438">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="21a9f-438">`0` - disabled</span></span> | <span data-ttu-id="21a9f-439">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="21a9f-439">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="21a9f-440">큰 개체 힙 임계값</span><span class="sxs-lookup"><span data-stu-id="21a9f-440">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="21a9f-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="21a9f-441">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="21a9f-442">개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-442">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="21a9f-443">기본 임계값은 85,000바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-443">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="21a9f-444">사용자가 지정하는 값은 기본 임계값보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-444">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="21a9f-445">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-445">Setting name</span></span> | <span data-ttu-id="21a9f-446">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-446">Values</span></span> | <span data-ttu-id="21a9f-447">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-447">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-448">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-448">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="21a9f-449">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-449">*decimal value*</span></span> | <span data-ttu-id="21a9f-450">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-450">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-451">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-451">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="21a9f-452">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-452">*hexadecimal value*</span></span> | <span data-ttu-id="21a9f-453">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-453">.NET Core 1.0</span></span> |
| <span data-ttu-id="21a9f-454">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="21a9f-454">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="21a9f-455">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="21a9f-455">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="21a9f-456">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="21a9f-456">*decimal value*</span></span> | <span data-ttu-id="21a9f-457">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="21a9f-457">.NET Framework 4.8</span></span> |

<span data-ttu-id="21a9f-458">예:</span><span class="sxs-lookup"><span data-stu-id="21a9f-458">Example:</span></span>

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
> <span data-ttu-id="21a9f-459">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-459">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="21a9f-460">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-460">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="21a9f-461">예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 0x1D4C0 또는 1D4C0으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-461">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="21a9f-462">독립 실행형 GC</span><span class="sxs-lookup"><span data-stu-id="21a9f-462">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="21a9f-463">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="21a9f-463">COMPlus_GCName</span></span>

- <span data-ttu-id="21a9f-464">런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="21a9f-464">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="21a9f-465">자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a9f-465">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="21a9f-466">설정 이름</span><span class="sxs-lookup"><span data-stu-id="21a9f-466">Setting name</span></span> | <span data-ttu-id="21a9f-467">값</span><span class="sxs-lookup"><span data-stu-id="21a9f-467">Values</span></span> | <span data-ttu-id="21a9f-468">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="21a9f-468">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="21a9f-469">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="21a9f-469">**runtimeconfig.json**</span></span> | <span data-ttu-id="21a9f-470">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-470">N/A</span></span> | <span data-ttu-id="21a9f-471">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-471">N/A</span></span> | <span data-ttu-id="21a9f-472">N/A</span><span class="sxs-lookup"><span data-stu-id="21a9f-472">N/A</span></span> |
| <span data-ttu-id="21a9f-473">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="21a9f-473">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="21a9f-474">*string_path*</span><span class="sxs-lookup"><span data-stu-id="21a9f-474">*string_path*</span></span> | <span data-ttu-id="21a9f-475">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="21a9f-475">.NET Core 2.0</span></span> |
