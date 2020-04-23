---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: dfb641eeda03d1acaa4771bd6253fcb33c4082a6
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607812"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="0523e-103">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="0523e-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="0523e-104">이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="0523e-105">실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="0523e-106">그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="0523e-107">이 페이지에서는 설정이 그룹별로 정리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="0523e-108">각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0523e-109">이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="0523e-110">[대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="0523e-111">이러한 설정은 이 페이지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="0523e-112">숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="0523e-113">16진수 값의 경우 “0x” 접두사를 사용하거나 사용하지 않고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="0523e-114">가비지 수집 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-114">Flavors of garbage collection</span></span>

<span data-ttu-id="0523e-115">가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="0523e-116">둘 사이의 차이점에 대한 자세한 내용은 [가비지 수집 기본 사항](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="0523e-117">가비지 수집의 하위 버전은 백그라운드와 비동시입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="0523e-118">다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="0523e-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="0523e-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="0523e-120">애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="0523e-121">기본값: 워크스테이션 가비지 수집(`false`).</span><span class="sxs-lookup"><span data-stu-id="0523e-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="0523e-122">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-122">Setting name</span></span> | <span data-ttu-id="0523e-123">값</span><span class="sxs-lookup"><span data-stu-id="0523e-123">Values</span></span> | <span data-ttu-id="0523e-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="0523e-126">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="0523e-126">`false` - workstation</span></span><br/><span data-ttu-id="0523e-127">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="0523e-127">`true` - server</span></span> | <span data-ttu-id="0523e-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-129">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="0523e-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="0523e-130">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="0523e-130">`false` - workstation</span></span><br/><span data-ttu-id="0523e-131">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="0523e-131">`true` - server</span></span> | <span data-ttu-id="0523e-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-133">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="0523e-134">`0` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="0523e-134">`0` - workstation</span></span><br/><span data-ttu-id="0523e-135">`1` - 서버</span><span class="sxs-lookup"><span data-stu-id="0523e-135">`1` - server</span></span> | <span data-ttu-id="0523e-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-137">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="0523e-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="0523e-139">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="0523e-139">`false` - workstation</span></span><br/><span data-ttu-id="0523e-140">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="0523e-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="0523e-141">예</span><span class="sxs-lookup"><span data-stu-id="0523e-141">Examples</span></span>

<span data-ttu-id="0523e-142">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="0523e-143">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="0523e-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="0523e-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="0523e-145">백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="0523e-146">기본값: 사용(`true`).</span><span class="sxs-lookup"><span data-stu-id="0523e-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="0523e-147">자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) 및 [백그라운드 서버 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="0523e-148">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-148">Setting name</span></span> | <span data-ttu-id="0523e-149">값</span><span class="sxs-lookup"><span data-stu-id="0523e-149">Values</span></span> | <span data-ttu-id="0523e-150">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="0523e-152">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-152">`true` - background GC</span></span><br/><span data-ttu-id="0523e-153">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="0523e-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-155">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="0523e-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="0523e-156">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-156">`true` - background GC</span></span><br/><span data-ttu-id="0523e-157">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="0523e-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-159">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="0523e-160">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-160">`true` - background GC</span></span><br/><span data-ttu-id="0523e-161">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="0523e-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-163">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="0523e-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="0523e-165">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-165">`true` - background GC</span></span><br/><span data-ttu-id="0523e-166">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="0523e-167">예</span><span class="sxs-lookup"><span data-stu-id="0523e-167">Examples</span></span>

<span data-ttu-id="0523e-168">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="0523e-169">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="0523e-170">리소스 사용량 관리</span><span class="sxs-lookup"><span data-stu-id="0523e-170">Manage resource usage</span></span>

<span data-ttu-id="0523e-171">이 섹션에서 설명하는 설정은 가비지 수집기의 메모리 및 프로세서 사용량을 관리하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="0523e-172">이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="0523e-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="0523e-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="0523e-174">가비지 수집기가 생성하는 힙의 개수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="0523e-175">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="0523e-176">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-176">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="0523e-177">(정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 [선호도 지정 마스크](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) 또는 [선호도 지정 범위](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) 설정을 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="0523e-177">(Use the [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) or [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="0523e-178">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-178">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="0523e-179">자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="0523e-180">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-180">Setting name</span></span> | <span data-ttu-id="0523e-181">값</span><span class="sxs-lookup"><span data-stu-id="0523e-181">Values</span></span> | <span data-ttu-id="0523e-182">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="0523e-184">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-184">*decimal value*</span></span> | <span data-ttu-id="0523e-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-186">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="0523e-187">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-187">*hexadecimal value*</span></span> | <span data-ttu-id="0523e-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-189">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="0523e-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="0523e-191">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-191">*decimal value*</span></span> | <span data-ttu-id="0523e-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="0523e-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="0523e-193">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-193">Example:</span></span>

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
> <span data-ttu-id="0523e-194">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="0523e-195">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="0523e-196">예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 0x10 또는 10으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="0523e-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="0523e-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="0523e-198">가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="0523e-199">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-199">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="0523e-200">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="0523e-201">값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="0523e-202">예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 0x3FF 또는 3FF)은 이진 표기법으로 0011 1111 1111입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="0523e-203">이는 처음 10개의 프로세서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="0523e-204">다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 0xFFC00 또는 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="0523e-205">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-205">Setting name</span></span> | <span data-ttu-id="0523e-206">값</span><span class="sxs-lookup"><span data-stu-id="0523e-206">Values</span></span> | <span data-ttu-id="0523e-207">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="0523e-209">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-209">*decimal value*</span></span> | <span data-ttu-id="0523e-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-211">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="0523e-212">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-212">*hexadecimal value*</span></span> | <span data-ttu-id="0523e-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-214">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="0523e-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="0523e-216">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-216">*decimal value*</span></span> | <span data-ttu-id="0523e-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="0523e-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="0523e-218">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="0523e-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="0523e-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="0523e-220">가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="0523e-221">이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask)와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-221">This setting is similar to [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="0523e-222">Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="0523e-223">[GC 프로세서 선호도](#systemgcnoaffinitizecomplus_gcnoaffinitize)를 사용하지 않도록 설정하면 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-223">If [GC processor affinity](#systemgcnoaffinitizecomplus_gcnoaffinitize) is disabled, this setting is ignored.</span></span>
- <span data-ttu-id="0523e-224">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="0523e-225">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="0523e-226">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-226">Setting name</span></span> | <span data-ttu-id="0523e-227">값</span><span class="sxs-lookup"><span data-stu-id="0523e-227">Values</span></span> | <span data-ttu-id="0523e-228">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="0523e-230">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="0523e-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="0523e-231">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="0523e-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="0523e-232">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="0523e-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="0523e-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-234">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="0523e-235">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="0523e-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="0523e-236">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="0523e-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="0523e-237">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="0523e-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="0523e-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-238">.NET Core 3.0</span></span> |

<span data-ttu-id="0523e-239">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="0523e-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="0523e-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="0523e-241">가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="0523e-242">64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="0523e-243">가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="0523e-244">64비트 Windows 운영 체제의 서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="0523e-245">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="0523e-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="0523e-246">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="0523e-247">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-247">Setting name</span></span> | <span data-ttu-id="0523e-248">값</span><span class="sxs-lookup"><span data-stu-id="0523e-248">Values</span></span> | <span data-ttu-id="0523e-249">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="0523e-251">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-251">N/A</span></span> | <span data-ttu-id="0523e-252">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-252">N/A</span></span> | <span data-ttu-id="0523e-253">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-253">N/A</span></span> |
| <span data-ttu-id="0523e-254">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="0523e-255">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-255">`0` - disabled</span></span><br/><span data-ttu-id="0523e-256">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="0523e-256">`1` - enabled</span></span> | <span data-ttu-id="0523e-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-258">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="0523e-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="0523e-260">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-260">`false` - disabled</span></span><br/><span data-ttu-id="0523e-261">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="0523e-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="0523e-262">모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="0523e-263">.NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="0523e-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="0523e-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="0523e-265">가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="0523e-266">GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="0523e-267">각 GC 스레드에 대해 힙이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="0523e-268">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="0523e-269">기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정(`false`).</span><span class="sxs-lookup"><span data-stu-id="0523e-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="0523e-270">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-270">Setting name</span></span> | <span data-ttu-id="0523e-271">값</span><span class="sxs-lookup"><span data-stu-id="0523e-271">Values</span></span> | <span data-ttu-id="0523e-272">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="0523e-274">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="0523e-274">`false` - affinitize</span></span><br/><span data-ttu-id="0523e-275">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-275">`true` - don't affinitize</span></span> | <span data-ttu-id="0523e-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-277">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="0523e-278">`0` - 선호</span><span class="sxs-lookup"><span data-stu-id="0523e-278">`0` - affinitize</span></span><br/><span data-ttu-id="0523e-279">`1` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-279">`1` - don't affinitize</span></span> | <span data-ttu-id="0523e-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-281">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="0523e-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="0523e-283">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="0523e-283">`false` - affinitize</span></span><br/><span data-ttu-id="0523e-284">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-284">`true` - don't affinitize</span></span> | <span data-ttu-id="0523e-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="0523e-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="0523e-286">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="0523e-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="0523e-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="0523e-288">GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>
- <span data-ttu-id="0523e-289">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-289">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="0523e-290">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 작은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-290">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="0523e-291">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-291">The default value applies if:</span></span>

  - <span data-ttu-id="0523e-292">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="0523e-292">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="0523e-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="0523e-293">[System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent) is not set.</span></span>

| | <span data-ttu-id="0523e-294">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-294">Setting name</span></span> | <span data-ttu-id="0523e-295">값</span><span class="sxs-lookup"><span data-stu-id="0523e-295">Values</span></span> | <span data-ttu-id="0523e-296">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-296">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-297">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-297">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="0523e-298">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-298">*decimal value*</span></span> | <span data-ttu-id="0523e-299">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-299">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-300">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-300">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="0523e-301">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-301">*hexadecimal value*</span></span> | <span data-ttu-id="0523e-302">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-302">.NET Core 3.0</span></span> |

<span data-ttu-id="0523e-303">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-303">Example:</span></span>

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
> <span data-ttu-id="0523e-304">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-304">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="0523e-305">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-305">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="0523e-306">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-306">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="0523e-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="0523e-307">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="0523e-308">허용되는 GC 힙 사용량을 총 실제 메모리의 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-308">Specifies the allowable GC heap usage as a percentage of the total physical memory.</span></span>
- <span data-ttu-id="0523e-309">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)이 설정되는 경우에도 이 설정이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-309">If [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is also set, this setting is ignored.</span></span>
- <span data-ttu-id="0523e-310">이 설정은 64비트 컴퓨터에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-310">This setting only applies to 64-bit computers.</span></span>
- <span data-ttu-id="0523e-311">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우 백분율은 해당 메모리 제한의 백분율로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-311">If the process is running inside a container that has a specified memory limit, the percentage is calculated as a percentage of that memory limit.</span></span>
- <span data-ttu-id="0523e-312">특정 경우에만 적용되는 기본값은 컨테이너에 대한 메모리 제한의 20MB 또는 75% 중 더 작은 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-312">The default value, which only applies in certain cases, is the lesser of 20 MB or 75% of the memory limit on the container.</span></span> <span data-ttu-id="0523e-313">기본값은 다음 경우에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-313">The default value applies if:</span></span>

  - <span data-ttu-id="0523e-314">프로세스가 지정된 메모리 제한이 있는 컨테이너 내에서 실행되는 경우.</span><span class="sxs-lookup"><span data-stu-id="0523e-314">The process is running inside a container that has a specified memory limit.</span></span>
  - <span data-ttu-id="0523e-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit)가 설정되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="0523e-315">[System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit) is not set.</span></span>

| | <span data-ttu-id="0523e-316">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-316">Setting name</span></span> | <span data-ttu-id="0523e-317">값</span><span class="sxs-lookup"><span data-stu-id="0523e-317">Values</span></span> | <span data-ttu-id="0523e-318">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-318">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-319">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-319">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="0523e-320">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-320">*decimal value*</span></span> | <span data-ttu-id="0523e-321">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-321">.NET Core 3.0</span></span> |
| <span data-ttu-id="0523e-322">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-322">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="0523e-323">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-323">*hexadecimal value*</span></span> | <span data-ttu-id="0523e-324">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-324">.NET Core 3.0</span></span> |

<span data-ttu-id="0523e-325">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-325">Example:</span></span>

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
> <span data-ttu-id="0523e-326">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-326">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="0523e-327">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-327">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="0523e-328">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-328">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="0523e-329">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="0523e-329">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="0523e-330">삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-330">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="0523e-331">기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="0523e-331">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="0523e-332">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-332">Setting name</span></span> | <span data-ttu-id="0523e-333">값</span><span class="sxs-lookup"><span data-stu-id="0523e-333">Values</span></span> | <span data-ttu-id="0523e-334">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-334">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-335">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-335">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="0523e-336">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="0523e-336">`false` - release to OS</span></span><br/><span data-ttu-id="0523e-337">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="0523e-337">`true` - put on standby</span></span> | <span data-ttu-id="0523e-338">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-338">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-339">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="0523e-339">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="0523e-340">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="0523e-340">`false` - release to OS</span></span><br/><span data-ttu-id="0523e-341">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="0523e-341">`true` - put on standby</span></span> | <span data-ttu-id="0523e-342">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-342">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-343">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-343">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="0523e-344">`0` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="0523e-344">`0` - release to OS</span></span><br/><span data-ttu-id="0523e-345">`1` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="0523e-345">`1` - put on standby</span></span> | <span data-ttu-id="0523e-346">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-346">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="0523e-347">예</span><span class="sxs-lookup"><span data-stu-id="0523e-347">Examples</span></span>

<span data-ttu-id="0523e-348">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-348">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="0523e-349">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="0523e-349">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="0523e-350">큰 페이지</span><span class="sxs-lookup"><span data-stu-id="0523e-350">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="0523e-351">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="0523e-351">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="0523e-352">힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-352">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="0523e-353">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="0523e-353">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="0523e-354">이것은 실험적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-354">This is an experimental setting.</span></span>

| | <span data-ttu-id="0523e-355">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-355">Setting name</span></span> | <span data-ttu-id="0523e-356">값</span><span class="sxs-lookup"><span data-stu-id="0523e-356">Values</span></span> | <span data-ttu-id="0523e-357">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-357">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-358">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-358">**runtimeconfig.json**</span></span> | <span data-ttu-id="0523e-359">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-359">N/A</span></span> | <span data-ttu-id="0523e-360">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-360">N/A</span></span> | <span data-ttu-id="0523e-361">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-361">N/A</span></span> |
| <span data-ttu-id="0523e-362">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-362">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="0523e-363">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-363">`0` - disabled</span></span><br/><span data-ttu-id="0523e-364">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="0523e-364">`1` - enabled</span></span> | <span data-ttu-id="0523e-365">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="0523e-365">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="0523e-366">큰 개체</span><span class="sxs-lookup"><span data-stu-id="0523e-366">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="0523e-367">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="0523e-367">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="0523e-368">64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-368">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="0523e-369">기본값: 사용(`1`).</span><span class="sxs-lookup"><span data-stu-id="0523e-369">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="0523e-370">이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-370">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="0523e-371">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-371">Setting name</span></span> | <span data-ttu-id="0523e-372">값</span><span class="sxs-lookup"><span data-stu-id="0523e-372">Values</span></span> | <span data-ttu-id="0523e-373">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-373">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-374">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-374">**runtimeconfig.json**</span></span> | <span data-ttu-id="0523e-375">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-375">N/A</span></span> | <span data-ttu-id="0523e-376">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-376">N/A</span></span> | <span data-ttu-id="0523e-377">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-377">N/A</span></span> |
| <span data-ttu-id="0523e-378">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-378">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="0523e-379">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="0523e-379">`1` - enabled</span></span><br/> <span data-ttu-id="0523e-380">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-380">`0` - disabled</span></span> | <span data-ttu-id="0523e-381">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-381">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-382">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-382">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-383">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="0523e-383">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="0523e-384">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="0523e-384">`1` - enabled</span></span><br/> <span data-ttu-id="0523e-385">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0523e-385">`0` - disabled</span></span> | <span data-ttu-id="0523e-386">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0523e-386">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="0523e-387">큰 개체 힙 임계값</span><span class="sxs-lookup"><span data-stu-id="0523e-387">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="0523e-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="0523e-388">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="0523e-389">개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-389">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="0523e-390">기본 임계값은 85,000바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-390">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="0523e-391">사용자가 지정하는 값은 기본 임계값보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-391">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="0523e-392">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-392">Setting name</span></span> | <span data-ttu-id="0523e-393">값</span><span class="sxs-lookup"><span data-stu-id="0523e-393">Values</span></span> | <span data-ttu-id="0523e-394">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-394">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-395">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-395">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="0523e-396">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-396">*decimal value*</span></span> | <span data-ttu-id="0523e-397">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-397">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-398">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-398">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="0523e-399">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-399">*hexadecimal value*</span></span> | <span data-ttu-id="0523e-400">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="0523e-400">.NET Core 1.0</span></span> |
| <span data-ttu-id="0523e-401">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="0523e-401">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="0523e-402">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="0523e-402">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="0523e-403">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="0523e-403">*decimal value*</span></span> | <span data-ttu-id="0523e-404">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="0523e-404">.NET Framework 4.8</span></span> |

<span data-ttu-id="0523e-405">예:</span><span class="sxs-lookup"><span data-stu-id="0523e-405">Example:</span></span>

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
> <span data-ttu-id="0523e-406">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-406">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="0523e-407">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-407">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="0523e-408">예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 0x1D4C0 또는 1D4C0으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-408">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="0523e-409">독립 실행형 GC</span><span class="sxs-lookup"><span data-stu-id="0523e-409">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="0523e-410">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="0523e-410">COMPlus_GCName</span></span>

- <span data-ttu-id="0523e-411">런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0523e-411">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="0523e-412">자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0523e-412">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="0523e-413">설정 이름</span><span class="sxs-lookup"><span data-stu-id="0523e-413">Setting name</span></span> | <span data-ttu-id="0523e-414">값</span><span class="sxs-lookup"><span data-stu-id="0523e-414">Values</span></span> | <span data-ttu-id="0523e-415">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0523e-415">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="0523e-416">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="0523e-416">**runtimeconfig.json**</span></span> | <span data-ttu-id="0523e-417">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-417">N/A</span></span> | <span data-ttu-id="0523e-418">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-418">N/A</span></span> | <span data-ttu-id="0523e-419">N/A</span><span class="sxs-lookup"><span data-stu-id="0523e-419">N/A</span></span> |
| <span data-ttu-id="0523e-420">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="0523e-420">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="0523e-421">*string_path*</span><span class="sxs-lookup"><span data-stu-id="0523e-421">*string_path*</span></span> | <span data-ttu-id="0523e-422">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0523e-422">.NET Core 2.0</span></span> |
