---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 044083d69601f5092724a46d358b2ee5673d428d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733524"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="d1f9b-103">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="d1f9b-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="d1f9b-104">이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="d1f9b-105">실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="d1f9b-106">그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="d1f9b-107">이 페이지에서는 설정이 그룹별로 정리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="d1f9b-108">각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="d1f9b-109">이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="d1f9b-110">[대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="d1f9b-111">이러한 설정은 이 페이지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="d1f9b-112">숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="d1f9b-113">16진수 값의 경우 “0x” 접두사를 사용하거나 사용하지 않고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="d1f9b-114">가비지 수집 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-114">Flavors of garbage collection</span></span>

<span data-ttu-id="d1f9b-115">가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="d1f9b-116">둘 사이의 차이점에 대한 자세한 내용은 [가비지 수집 기본 사항](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="d1f9b-117">가비지 수집의 하위 버전은 백그라운드와 비동시입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="d1f9b-118">다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="d1f9b-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="d1f9b-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="d1f9b-120">애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="d1f9b-121">기본값: 워크스테이션 가비지 수집(`false`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="d1f9b-122">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-122">Setting name</span></span> | <span data-ttu-id="d1f9b-123">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-123">Values</span></span> | <span data-ttu-id="d1f9b-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="d1f9b-126">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="d1f9b-126">`false` - workstation</span></span><br/><span data-ttu-id="d1f9b-127">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="d1f9b-127">`true` - server</span></span> | <span data-ttu-id="d1f9b-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-129">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-129">**MSBuild property**</span></span> | `ServerGarbageCollection` | <span data-ttu-id="d1f9b-130">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="d1f9b-130">`false` - workstation</span></span><br/><span data-ttu-id="d1f9b-131">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="d1f9b-131">`true` - server</span></span> | <span data-ttu-id="d1f9b-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-133">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-133">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="d1f9b-134">`0` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="d1f9b-134">`0` - workstation</span></span><br/><span data-ttu-id="d1f9b-135">`1` - 서버</span><span class="sxs-lookup"><span data-stu-id="d1f9b-135">`1` - server</span></span> | <span data-ttu-id="d1f9b-136">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-136">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-137">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-137">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-138">GCServer</span><span class="sxs-lookup"><span data-stu-id="d1f9b-138">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="d1f9b-139">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="d1f9b-139">`false` - workstation</span></span><br/><span data-ttu-id="d1f9b-140">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="d1f9b-140">`true` - server</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d1f9b-141">예</span><span class="sxs-lookup"><span data-stu-id="d1f9b-141">Examples</span></span>

<span data-ttu-id="d1f9b-142">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-142">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

<span data-ttu-id="d1f9b-143">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-143">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="d1f9b-144">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d1f9b-144">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="d1f9b-145">백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-145">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="d1f9b-146">기본값: 사용(`true`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-146">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="d1f9b-147">자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) 및 [백그라운드 서버 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-147">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="d1f9b-148">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-148">Setting name</span></span> | <span data-ttu-id="d1f9b-149">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-149">Values</span></span> | <span data-ttu-id="d1f9b-150">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-150">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-151">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-151">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="d1f9b-152">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-152">`true` - background GC</span></span><br/><span data-ttu-id="d1f9b-153">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-153">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d1f9b-154">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-154">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-155">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-155">**MSBuild property**</span></span> | `ConcurrentGarbageCollection` | <span data-ttu-id="d1f9b-156">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-156">`true` - background GC</span></span><br/><span data-ttu-id="d1f9b-157">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-157">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d1f9b-158">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-158">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-159">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-159">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="d1f9b-160">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-160">`true` - background GC</span></span><br/><span data-ttu-id="d1f9b-161">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-161">`false` - non-concurrent GC</span></span> | <span data-ttu-id="d1f9b-162">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-162">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-163">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-163">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-164">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="d1f9b-164">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="d1f9b-165">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-165">`true` - background GC</span></span><br/><span data-ttu-id="d1f9b-166">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-166">`false` - non-concurrent GC</span></span> |  |

### <a name="examples"></a><span data-ttu-id="d1f9b-167">예</span><span class="sxs-lookup"><span data-stu-id="d1f9b-167">Examples</span></span>

<span data-ttu-id="d1f9b-168">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

<span data-ttu-id="d1f9b-169">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a><span data-ttu-id="d1f9b-170">리소스 사용량 관리</span><span class="sxs-lookup"><span data-stu-id="d1f9b-170">Manage resource usage</span></span>

<span data-ttu-id="d1f9b-171">이 섹션에서 설명하는 설정은 가비지 수집기의 메모리 및 프로세서 사용량을 관리하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-171">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="d1f9b-172">이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-172">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="d1f9b-173">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d1f9b-173">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="d1f9b-174">가비지 수집기가 생성하는 힙의 개수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-174">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="d1f9b-175">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-175">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d1f9b-176">GC 프로세서 선호도가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-176">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="d1f9b-177">(정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 선호도 지정 마스크 또는 선호도 지정 범위 설정을 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="d1f9b-177">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="d1f9b-178">GC 프로세서 선호도를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-178">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="d1f9b-179">자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-179">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="d1f9b-180">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-180">Setting name</span></span> | <span data-ttu-id="d1f9b-181">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-181">Values</span></span> | <span data-ttu-id="d1f9b-182">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-182">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-183">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-183">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="d1f9b-184">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-184">*decimal value*</span></span> | <span data-ttu-id="d1f9b-185">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-185">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-186">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-186">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="d1f9b-187">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-187">*hexadecimal value*</span></span> | <span data-ttu-id="d1f9b-188">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-188">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-189">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-189">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-190">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="d1f9b-190">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="d1f9b-191">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-191">*decimal value*</span></span> | <span data-ttu-id="d1f9b-192">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1f9b-192">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d1f9b-193">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-193">Example:</span></span>

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
> <span data-ttu-id="d1f9b-194">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-194">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d1f9b-195">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-195">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d1f9b-196">예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 0x10 또는 10으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-196">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="d1f9b-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d1f9b-197">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="d1f9b-198">가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-198">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="d1f9b-199">`System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-199">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="d1f9b-200">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-200">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d1f9b-201">값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-201">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="d1f9b-202">예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 0x3FF 또는 3FF)은 이진 표기법으로 0011 1111 1111입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-202">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="d1f9b-203">이는 처음 10개의 프로세서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-203">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="d1f9b-204">다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 0xFFC00 또는 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-204">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="d1f9b-205">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-205">Setting name</span></span> | <span data-ttu-id="d1f9b-206">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-206">Values</span></span> | <span data-ttu-id="d1f9b-207">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-207">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-208">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-208">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="d1f9b-209">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-209">*decimal value*</span></span> | <span data-ttu-id="d1f9b-210">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-210">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-211">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-211">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="d1f9b-212">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-212">*hexadecimal value*</span></span> | <span data-ttu-id="d1f9b-213">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-213">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-214">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-214">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-215">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="d1f9b-215">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="d1f9b-216">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-216">*decimal value*</span></span> | <span data-ttu-id="d1f9b-217">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1f9b-217">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d1f9b-218">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-218">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="d1f9b-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="d1f9b-219">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="d1f9b-220">가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-220">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="d1f9b-221">이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 `System.GC.HeapAffinitizeMask`와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-221">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="d1f9b-222">Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-222">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="d1f9b-223">`System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-223">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="d1f9b-224">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-224">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d1f9b-225">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-225">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d1f9b-226">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-226">Setting name</span></span> | <span data-ttu-id="d1f9b-227">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-227">Values</span></span> | <span data-ttu-id="d1f9b-228">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-228">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-229">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-229">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="d1f9b-230">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-230">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d1f9b-231">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="d1f9b-231">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d1f9b-232">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="d1f9b-232">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d1f9b-233">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-233">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-234">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-234">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="d1f9b-235">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-235">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="d1f9b-236">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="d1f9b-236">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="d1f9b-237">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="d1f9b-237">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="d1f9b-238">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-238">.NET Core 3.0</span></span> |

<span data-ttu-id="d1f9b-239">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-239">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="d1f9b-240">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d1f9b-240">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="d1f9b-241">가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-241">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="d1f9b-242">64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-242">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="d1f9b-243">가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-243">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="d1f9b-244">64비트 Windows 운영 체제의 서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-244">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="d1f9b-245">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-245">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="d1f9b-246">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-246">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="d1f9b-247">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-247">Setting name</span></span> | <span data-ttu-id="d1f9b-248">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-248">Values</span></span> | <span data-ttu-id="d1f9b-249">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-249">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-250">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-250">**runtimeconfig.json**</span></span> | <span data-ttu-id="d1f9b-251">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-251">N/A</span></span> | <span data-ttu-id="d1f9b-252">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-252">N/A</span></span> | <span data-ttu-id="d1f9b-253">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-253">N/A</span></span> |
| <span data-ttu-id="d1f9b-254">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-254">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="d1f9b-255">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-255">`0` - disabled</span></span><br/><span data-ttu-id="d1f9b-256">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="d1f9b-256">`1` - enabled</span></span> | <span data-ttu-id="d1f9b-257">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-257">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-258">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-258">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-259">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="d1f9b-259">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="d1f9b-260">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-260">`false` - disabled</span></span><br/><span data-ttu-id="d1f9b-261">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="d1f9b-261">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="d1f9b-262">모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-262">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="d1f9b-263">.NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-263">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="d1f9b-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d1f9b-264">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="d1f9b-265">가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-265">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="d1f9b-266">GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-266">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="d1f9b-267">각 GC 스레드에 대해 힙이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-267">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="d1f9b-268">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-268">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="d1f9b-269">기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정(`false`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-269">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="d1f9b-270">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-270">Setting name</span></span> | <span data-ttu-id="d1f9b-271">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-271">Values</span></span> | <span data-ttu-id="d1f9b-272">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-272">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-273">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-273">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="d1f9b-274">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="d1f9b-274">`false` - affinitize</span></span><br/><span data-ttu-id="d1f9b-275">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-275">`true` - don't affinitize</span></span> | <span data-ttu-id="d1f9b-276">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-276">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-277">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-277">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="d1f9b-278">`0` - 선호</span><span class="sxs-lookup"><span data-stu-id="d1f9b-278">`0` - affinitize</span></span><br/><span data-ttu-id="d1f9b-279">`1` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-279">`1` - don't affinitize</span></span> | <span data-ttu-id="d1f9b-280">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-280">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-281">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-281">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-282">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="d1f9b-282">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="d1f9b-283">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="d1f9b-283">`false` - affinitize</span></span><br/><span data-ttu-id="d1f9b-284">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-284">`true` - don't affinitize</span></span> | <span data-ttu-id="d1f9b-285">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="d1f9b-285">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="d1f9b-286">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-286">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="d1f9b-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="d1f9b-287">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="d1f9b-288">GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-288">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="d1f9b-289">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-289">Setting name</span></span> | <span data-ttu-id="d1f9b-290">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-290">Values</span></span> | <span data-ttu-id="d1f9b-291">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-291">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-292">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-292">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="d1f9b-293">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-293">*decimal value*</span></span> | <span data-ttu-id="d1f9b-294">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-294">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-295">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-295">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="d1f9b-296">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-296">*hexadecimal value*</span></span> | <span data-ttu-id="d1f9b-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-297">.NET Core 3.0</span></span> |

<span data-ttu-id="d1f9b-298">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-298">Example:</span></span>

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
> <span data-ttu-id="d1f9b-299">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-299">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d1f9b-300">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-300">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d1f9b-301">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-301">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="d1f9b-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="d1f9b-302">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="d1f9b-303">GC 힙의 사용량을 총 메모리의 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-303">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="d1f9b-304">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-304">Setting name</span></span> | <span data-ttu-id="d1f9b-305">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-305">Values</span></span> | <span data-ttu-id="d1f9b-306">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-306">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-307">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-307">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="d1f9b-308">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-308">*decimal value*</span></span> | <span data-ttu-id="d1f9b-309">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-309">.NET Core 3.0</span></span> |
| <span data-ttu-id="d1f9b-310">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-310">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="d1f9b-311">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-311">*hexadecimal value*</span></span> | <span data-ttu-id="d1f9b-312">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-312">.NET Core 3.0</span></span> |

<span data-ttu-id="d1f9b-313">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-313">Example:</span></span>

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
> <span data-ttu-id="d1f9b-314">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-314">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d1f9b-315">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-315">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d1f9b-316">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-316">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="d1f9b-317">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="d1f9b-317">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="d1f9b-318">삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-318">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="d1f9b-319">기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-319">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="d1f9b-320">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-320">Setting name</span></span> | <span data-ttu-id="d1f9b-321">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-321">Values</span></span> | <span data-ttu-id="d1f9b-322">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-322">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-323">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-323">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="d1f9b-324">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="d1f9b-324">`false` - release to OS</span></span><br/><span data-ttu-id="d1f9b-325">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="d1f9b-325">`true` - put on standby</span></span> | <span data-ttu-id="d1f9b-326">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-326">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-327">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-327">**MSBuild property**</span></span> | `RetainVMGarbageCollection` | <span data-ttu-id="d1f9b-328">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="d1f9b-328">`false` - release to OS</span></span><br/><span data-ttu-id="d1f9b-329">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="d1f9b-329">`true` - put on standby</span></span> | <span data-ttu-id="d1f9b-330">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-330">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-331">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-331">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="d1f9b-332">`0` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="d1f9b-332">`0` - release to OS</span></span><br/><span data-ttu-id="d1f9b-333">`1` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="d1f9b-333">`1` - put on standby</span></span> | <span data-ttu-id="d1f9b-334">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-334">.NET Core 1.0</span></span> |

### <a name="examples"></a><span data-ttu-id="d1f9b-335">예</span><span class="sxs-lookup"><span data-stu-id="d1f9b-335">Examples</span></span>

<span data-ttu-id="d1f9b-336">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-336">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

<span data-ttu-id="d1f9b-337">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-337">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a><span data-ttu-id="d1f9b-338">큰 페이지</span><span class="sxs-lookup"><span data-stu-id="d1f9b-338">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="d1f9b-339">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="d1f9b-339">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="d1f9b-340">힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-340">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="d1f9b-341">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-341">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="d1f9b-342">이것은 실험적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-342">This is an experimental setting.</span></span>

| | <span data-ttu-id="d1f9b-343">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-343">Setting name</span></span> | <span data-ttu-id="d1f9b-344">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-344">Values</span></span> | <span data-ttu-id="d1f9b-345">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-345">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-346">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-346">**runtimeconfig.json**</span></span> | <span data-ttu-id="d1f9b-347">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-347">N/A</span></span> | <span data-ttu-id="d1f9b-348">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-348">N/A</span></span> | <span data-ttu-id="d1f9b-349">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-349">N/A</span></span> |
| <span data-ttu-id="d1f9b-350">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-350">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="d1f9b-351">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-351">`0` - disabled</span></span><br/><span data-ttu-id="d1f9b-352">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="d1f9b-352">`1` - enabled</span></span> | <span data-ttu-id="d1f9b-353">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-353">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="d1f9b-354">큰 개체</span><span class="sxs-lookup"><span data-stu-id="d1f9b-354">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="d1f9b-355">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d1f9b-355">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="d1f9b-356">64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-356">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="d1f9b-357">기본값: 사용(`1`).</span><span class="sxs-lookup"><span data-stu-id="d1f9b-357">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="d1f9b-358">이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-358">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="d1f9b-359">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-359">Setting name</span></span> | <span data-ttu-id="d1f9b-360">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-360">Values</span></span> | <span data-ttu-id="d1f9b-361">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-361">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-362">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-362">**runtimeconfig.json**</span></span> | <span data-ttu-id="d1f9b-363">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-363">N/A</span></span> | <span data-ttu-id="d1f9b-364">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-364">N/A</span></span> | <span data-ttu-id="d1f9b-365">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-365">N/A</span></span> |
| <span data-ttu-id="d1f9b-366">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-366">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="d1f9b-367">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="d1f9b-367">`1` - enabled</span></span><br/> <span data-ttu-id="d1f9b-368">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-368">`0` - disabled</span></span> | <span data-ttu-id="d1f9b-369">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-369">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-370">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-370">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-371">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="d1f9b-371">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="d1f9b-372">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="d1f9b-372">`1` - enabled</span></span><br/> <span data-ttu-id="d1f9b-373">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d1f9b-373">`0` - disabled</span></span> | <span data-ttu-id="d1f9b-374">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d1f9b-374">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="d1f9b-375">큰 개체 힙 임계값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-375">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="d1f9b-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d1f9b-376">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="d1f9b-377">개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-377">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="d1f9b-378">기본 임계값은 85,000바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-378">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="d1f9b-379">사용자가 지정하는 값은 기본 임계값보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-379">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="d1f9b-380">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-380">Setting name</span></span> | <span data-ttu-id="d1f9b-381">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-381">Values</span></span> | <span data-ttu-id="d1f9b-382">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-382">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-383">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-383">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="d1f9b-384">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-384">*decimal value*</span></span> | <span data-ttu-id="d1f9b-385">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-385">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-386">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-386">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="d1f9b-387">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-387">*hexadecimal value*</span></span> | <span data-ttu-id="d1f9b-388">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-388">.NET Core 1.0</span></span> |
| <span data-ttu-id="d1f9b-389">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-389">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="d1f9b-390">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="d1f9b-390">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="d1f9b-391">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-391">*decimal value*</span></span> | <span data-ttu-id="d1f9b-392">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="d1f9b-392">.NET Framework 4.8</span></span> |

<span data-ttu-id="d1f9b-393">예:</span><span class="sxs-lookup"><span data-stu-id="d1f9b-393">Example:</span></span>

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
> <span data-ttu-id="d1f9b-394">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-394">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="d1f9b-395">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-395">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="d1f9b-396">예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 0x1D4C0 또는 1D4C0으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-396">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="d1f9b-397">독립 실행형 GC</span><span class="sxs-lookup"><span data-stu-id="d1f9b-397">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="d1f9b-398">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="d1f9b-398">COMPlus_GCName</span></span>

- <span data-ttu-id="d1f9b-399">런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-399">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="d1f9b-400">자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d1f9b-400">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="d1f9b-401">설정 이름</span><span class="sxs-lookup"><span data-stu-id="d1f9b-401">Setting name</span></span> | <span data-ttu-id="d1f9b-402">값</span><span class="sxs-lookup"><span data-stu-id="d1f9b-402">Values</span></span> | <span data-ttu-id="d1f9b-403">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d1f9b-403">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d1f9b-404">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-404">**runtimeconfig.json**</span></span> | <span data-ttu-id="d1f9b-405">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-405">N/A</span></span> | <span data-ttu-id="d1f9b-406">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-406">N/A</span></span> | <span data-ttu-id="d1f9b-407">N/A</span><span class="sxs-lookup"><span data-stu-id="d1f9b-407">N/A</span></span> |
| <span data-ttu-id="d1f9b-408">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="d1f9b-408">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="d1f9b-409">*string_path*</span><span class="sxs-lookup"><span data-stu-id="d1f9b-409">*string_path*</span></span> | <span data-ttu-id="d1f9b-410">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="d1f9b-410">.NET Core 2.0</span></span> |
