---
title: 가비지 수집기 구성 설정
description: 가비지 수집기가 .NET Core 앱의 메모리를 관리하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: 24e5c47de781e7eed5f76d2c551cac2dce1e8f05
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900105"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a><span data-ttu-id="418c2-103">가비지 수집을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="418c2-103">Run-time configuration options for garbage collection</span></span>

<span data-ttu-id="418c2-104">이 페이지에는 런타임에 변경할 수 있는 가비지 수집기(GC) 설정에 관한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-104">This page contains information about garbage collector (GC) settings that can be changed at run time.</span></span> <span data-ttu-id="418c2-105">실행 중인 앱의 최고 성능을 달성하려는 경우 이러한 설정을 사용해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-105">If you're trying to achieve peak performance of a running app, consider using these settings.</span></span> <span data-ttu-id="418c2-106">그러나 기본값으로도 일반적인 상황에 있는 대부분의 애플리케이션에서 최적의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-106">However, the defaults provide optimum performance for most applications in typical situations.</span></span>

<span data-ttu-id="418c2-107">이 페이지에서는 설정이 그룹별로 정리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-107">Settings are arranged into groups on this page.</span></span> <span data-ttu-id="418c2-108">각 그룹에 포함된 설정은 특정 결과를 얻기 위해 서로 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-108">The settings within each group are commonly used in conjunction with each other to achieve a specific result.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="418c2-109">이러한 설정은 앱이 실행 중일 때 동적으로 변경될 수도 있으므로 사용자가 설정한 런타임 설정이 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-109">These settings can also be changed dynamically by the app as it's running, so any run-time settings you set may be overridden.</span></span>
> - <span data-ttu-id="418c2-110">[대기 시간 수준](../../standard/garbage-collection/latency.md)과 같은 일부 설정은 디자인 타임에 API를 통해서만 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-110">Some settings, such as [latency level](../../standard/garbage-collection/latency.md), are typically set only through the API at design time.</span></span> <span data-ttu-id="418c2-111">이러한 설정은 이 페이지에 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-111">Such settings are omitted from this page.</span></span>
> - <span data-ttu-id="418c2-112">숫자 값의 경우, *runtimeconfig.json* 파일에 있는 설정에는 10진수 표기법을 사용하고, 환경 변수 설정에는 16진수 표기법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-112">For number values, use decimal notation for settings in the *runtimeconfig.json* file and hexadecimal notation for environment variable settings.</span></span> <span data-ttu-id="418c2-113">16진수 값의 경우 “0x” 접두사를 사용하거나 사용하지 않고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-113">For hexadecimal values, you can specify them with or without the "0x" prefix.</span></span>

## <a name="flavors-of-garbage-collection"></a><span data-ttu-id="418c2-114">가비지 수집 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-114">Flavors of garbage collection</span></span>

<span data-ttu-id="418c2-115">가비지 수집의 2가지 주요 버전은 워크스테이션 GC와 서버 GC입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-115">The two main flavors of garbage collection are workstation GC and server GC.</span></span> <span data-ttu-id="418c2-116">둘 사이의 차이점에 대한 자세한 내용은 [가비지 수집 기본 사항](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-116">For more information about differences between the two, see [Fundamentals of garbage collection](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).</span></span>

<span data-ttu-id="418c2-117">가비지 수집의 하위 버전은 백그라운드와 비동시입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-117">The subflavors of garbage collection are background and non-concurrent.</span></span>

<span data-ttu-id="418c2-118">다음 설정을 사용하여 가비지 수집의 버전을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-118">Use the following settings to select flavors of garbage collection:</span></span>

### <a name="systemgcservercomplus_gcserver"></a><span data-ttu-id="418c2-119">System.GC.Server/COMPlus_gcServer</span><span class="sxs-lookup"><span data-stu-id="418c2-119">System.GC.Server/COMPlus_gcServer</span></span>

- <span data-ttu-id="418c2-120">애플리케이션이 워크스테이션 가비지 수집과 서버 가비지 수집 중 어느 것을 사용하는지 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-120">Configures whether the application uses workstation garbage collection or server garbage collection.</span></span>
- <span data-ttu-id="418c2-121">기본값: 워크스테이션 가비지 수집(`false`).</span><span class="sxs-lookup"><span data-stu-id="418c2-121">Default: Workstation garbage collection (`false`).</span></span>

| | <span data-ttu-id="418c2-122">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-122">Setting name</span></span> | <span data-ttu-id="418c2-123">값</span><span class="sxs-lookup"><span data-stu-id="418c2-123">Values</span></span> | <span data-ttu-id="418c2-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-124">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-125">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-125">**runtimeconfig.json**</span></span> | `System.GC.Server` | <span data-ttu-id="418c2-126">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="418c2-126">`false` - workstation</span></span><br/><span data-ttu-id="418c2-127">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="418c2-127">`true` - server</span></span> | <span data-ttu-id="418c2-128">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-128">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-129">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-129">**Environment variable**</span></span> | `COMPlus_gcServer` | <span data-ttu-id="418c2-130">`0` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="418c2-130">`0` - workstation</span></span><br/><span data-ttu-id="418c2-131">`1` - 서버</span><span class="sxs-lookup"><span data-stu-id="418c2-131">`1` - server</span></span> | <span data-ttu-id="418c2-132">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-132">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-133">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-133">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-134">GCServer</span><span class="sxs-lookup"><span data-stu-id="418c2-134">GCServer</span></span>](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | <span data-ttu-id="418c2-135">`false` - 워크스테이션</span><span class="sxs-lookup"><span data-stu-id="418c2-135">`false` - workstation</span></span><br/><span data-ttu-id="418c2-136">`true` - 서버</span><span class="sxs-lookup"><span data-stu-id="418c2-136">`true` - server</span></span> |  |

<span data-ttu-id="418c2-137">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-137">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a><span data-ttu-id="418c2-138">System.GC.Concurrent/COMPlus_gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="418c2-138">System.GC.Concurrent/COMPlus_gcConcurrent</span></span>

- <span data-ttu-id="418c2-139">백그라운드(동시) 가비지 수집이 사용하도록 설정되었는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-139">Configures whether background (concurrent) garbage collection is enabled.</span></span>
- <span data-ttu-id="418c2-140">기본값: 사용(`true`).</span><span class="sxs-lookup"><span data-stu-id="418c2-140">Default: Enabled (`true`).</span></span>
- <span data-ttu-id="418c2-141">자세한 내용은 [백그라운드 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) 및 [백그라운드 서버 가비지 수집](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-141">For more information, see [Background garbage collection](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) and [Background server garbage collection](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).</span></span>

| | <span data-ttu-id="418c2-142">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-142">Setting name</span></span> | <span data-ttu-id="418c2-143">값</span><span class="sxs-lookup"><span data-stu-id="418c2-143">Values</span></span> | <span data-ttu-id="418c2-144">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-144">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-145">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-145">**runtimeconfig.json**</span></span> | `System.GC.Concurrent` | <span data-ttu-id="418c2-146">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-146">`true` - background GC</span></span><br/><span data-ttu-id="418c2-147">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-147">`false` - non-concurrent GC</span></span> | <span data-ttu-id="418c2-148">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-148">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-149">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-149">**Environment variable**</span></span> | `COMPlus_gcConcurrent` | <span data-ttu-id="418c2-150">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-150">`true` - background GC</span></span><br/><span data-ttu-id="418c2-151">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-151">`false` - non-concurrent GC</span></span> | <span data-ttu-id="418c2-152">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-152">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-153">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-153">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-154">gcConcurrent</span><span class="sxs-lookup"><span data-stu-id="418c2-154">gcConcurrent</span></span>](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | <span data-ttu-id="418c2-155">`true` - 백그라운드 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-155">`true` - background GC</span></span><br/><span data-ttu-id="418c2-156">`false` - 비동시 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-156">`false` - non-concurrent GC</span></span> |  |

<span data-ttu-id="418c2-157">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-157">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

## <a name="manage-resource-usage"></a><span data-ttu-id="418c2-158">리소스 사용량 관리</span><span class="sxs-lookup"><span data-stu-id="418c2-158">Manage resource usage</span></span>

<span data-ttu-id="418c2-159">이 섹션에서 설명하는 설정은 가비지 수집기의 메모리 및 프로세서 사용량을 관리하는 데 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-159">Use the settings described in this section to manage the garbage collector's memory and processor usage.</span></span>

<span data-ttu-id="418c2-160">이들 중 일부 설정에 대한 자세한 내용은 [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/)(워크스테이션 및 서버 GC의 중간 지점) 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-160">For more information about some of these settings, see the [Middle ground between workstation and server GC](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/) blog entry.</span></span>

### <a name="systemgcheapcountcomplus_gcheapcount"></a><span data-ttu-id="418c2-161">System.GC.HeapCount/COMPlus_GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="418c2-161">System.GC.HeapCount/COMPlus_GCHeapCount</span></span>

- <span data-ttu-id="418c2-162">가비지 수집기가 생성하는 힙의 개수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-162">Limits the number of heaps created by the garbage collector.</span></span>
- <span data-ttu-id="418c2-163">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-163">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="418c2-164">GC 프로세서 선호도가 사용하도록 설정된 경우(기본값), 힙 개수 설정은 `n` GC 힙/스레드의 선호도를 처음 `n`개의 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-164">If GC processor affinity is enabled, which is the default, the heap count setting affinitizes `n` GC heaps/threads to the first `n` processors.</span></span> <span data-ttu-id="418c2-165">(정확히 어떤 프로세서의 선호도를 지정하려는지 지정하려면 선호도 지정 마스크 또는 선호도 지정 범위 설정을 사용하세요.)</span><span class="sxs-lookup"><span data-stu-id="418c2-165">(Use the affinitize mask or affinitize ranges settings to specify exactly which processors to affinitize.)</span></span>
- <span data-ttu-id="418c2-166">GC 프로세서 선호도를 사용하지 않도록 설정하는 경우, 이 설정으로 GC 힙 개수가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-166">If GC processor affinity is disabled, this setting limits the number of GC heaps.</span></span>
- <span data-ttu-id="418c2-167">자세한 내용은 [GCHeapCount 설명](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-167">For more information, see the [GCHeapCount remarks](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).</span></span>

| | <span data-ttu-id="418c2-168">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-168">Setting name</span></span> | <span data-ttu-id="418c2-169">값</span><span class="sxs-lookup"><span data-stu-id="418c2-169">Values</span></span> | <span data-ttu-id="418c2-170">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-170">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-171">**runtimeconfig.json**</span></span> | `System.GC.HeapCount` | <span data-ttu-id="418c2-172">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-172">*decimal value*</span></span> | <span data-ttu-id="418c2-173">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-173">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-174">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-174">**Environment variable**</span></span> | `COMPlus_GCHeapCount` | <span data-ttu-id="418c2-175">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-175">*hexadecimal value*</span></span> | <span data-ttu-id="418c2-176">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-176">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-177">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-177">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-178">GCHeapCount</span><span class="sxs-lookup"><span data-stu-id="418c2-178">GCHeapCount</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | <span data-ttu-id="418c2-179">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-179">*decimal value*</span></span> | <span data-ttu-id="418c2-180">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="418c2-180">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="418c2-181">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-181">Example:</span></span>

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
> <span data-ttu-id="418c2-182">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-182">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="418c2-183">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-183">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="418c2-184">예를 들어, 힙의 개수를 16으로 제한하려면 JSON 파일의 경우 값을 16으로 지정하고 환경 변수의 경우 값을 0x10 또는 10으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-184">For example, to limit the number of heaps to 16, the values would be 16 for the JSON file and 0x10 or 10 for the environment variable.</span></span>

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a><span data-ttu-id="418c2-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="418c2-185">System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask</span></span>

- <span data-ttu-id="418c2-186">가비지 수집기 스레드가 사용할 정확한 프로세서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-186">Specifies the exact processors that garbage collector threads should use.</span></span>
- <span data-ttu-id="418c2-187">`System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-187">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="418c2-188">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-188">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="418c2-189">값은 프로세스에서 사용할 수 있는 프로세서를 정의하는 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-189">The value is a bit mask that defines the processors that are available to the process.</span></span> <span data-ttu-id="418c2-190">예를 들어, 10진수 값 1023(환경 변수를 사용하는 경우에는 16진수 값 0x3FF 또는 3FF)은 이진 표기법으로 0011 1111 1111입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-190">For example, a decimal value of 1023 (or a hexadecimal value of 0x3FF or 3FF if you're using the environment variable) is 0011 1111 1111 in binary notation.</span></span> <span data-ttu-id="418c2-191">이는 처음 10개의 프로세서를 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-191">This specifies that the first 10 processors are to be used.</span></span> <span data-ttu-id="418c2-192">다음 10개의 프로세서, 즉 프로세서 10~19를 지정하려면 10진수 값 1047552(또는 16진수 값 0xFFC00 또는 FFC00)을 지정합니다. 이는 이진수 값 1111 1111 1100 0000 0000과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-192">To specify the next 10 processors, that is, processors 10-19, specify a decimal value of 1047552 (or a hexadecimal value of 0xFFC00 or FFC00), which is equivalent to a binary value of 1111 1111 1100 0000 0000.</span></span>

| | <span data-ttu-id="418c2-193">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-193">Setting name</span></span> | <span data-ttu-id="418c2-194">값</span><span class="sxs-lookup"><span data-stu-id="418c2-194">Values</span></span> | <span data-ttu-id="418c2-195">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-195">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-196">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-196">**runtimeconfig.json**</span></span> | `System.GC.HeapAffinitizeMask` | <span data-ttu-id="418c2-197">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-197">*decimal value*</span></span> | <span data-ttu-id="418c2-198">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-198">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-199">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-199">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeMask` | <span data-ttu-id="418c2-200">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-200">*hexadecimal value*</span></span> | <span data-ttu-id="418c2-201">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-201">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-202">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-202">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-203">GCHeapAffinitizeMask</span><span class="sxs-lookup"><span data-stu-id="418c2-203">GCHeapAffinitizeMask</span></span>](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | <span data-ttu-id="418c2-204">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-204">*decimal value*</span></span> | <span data-ttu-id="418c2-205">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="418c2-205">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="418c2-206">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-206">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a><span data-ttu-id="418c2-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span><span class="sxs-lookup"><span data-stu-id="418c2-207">System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges</span></span>

- <span data-ttu-id="418c2-208">가비지 수집기 스레드가 사용할 프로세서 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-208">Specifies the list of processors to use for garbage collector threads.</span></span>
- <span data-ttu-id="418c2-209">이 설정은 64개가 넘는 프로세서를 지정할 수 있다는 점을 제외하면 `System.GC.HeapAffinitizeMask`와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-209">This setting is similar to `System.GC.HeapAffinitizeMask`, except it allows you to specify more than 64 processors.</span></span>
- <span data-ttu-id="418c2-210">Windows 운영 체제에서는 번호 또는 범위 앞에 해당하는 [CPU 그룹](/windows/win32/procthread/processor-groups)(예: “0:1-10,0:12,1:50-52,1:70”)을 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-210">For Windows operating systems, prefix the processor number or range with the corresponding [CPU group](/windows/win32/procthread/processor-groups), for example, "0:1-10,0:12,1:50-52,1:70".</span></span>
- <span data-ttu-id="418c2-211">`System.GC.NoAffinitize`를 `true`로 설정하여 프로세서 선호도를 사용하지 않도록 설정한 경우, 이 설정은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-211">If processor affinity is disabled by setting `System.GC.NoAffinitize` to `true`, this setting is ignored.</span></span>
- <span data-ttu-id="418c2-212">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-212">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="418c2-213">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-213">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="418c2-214">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-214">Setting name</span></span> | <span data-ttu-id="418c2-215">값</span><span class="sxs-lookup"><span data-stu-id="418c2-215">Values</span></span> | <span data-ttu-id="418c2-216">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-216">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-217">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-217">**runtimeconfig.json**</span></span> | `System.GC.GCHeapAffinitizeRanges` | <span data-ttu-id="418c2-218">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="418c2-218">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="418c2-219">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="418c2-219">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="418c2-220">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="418c2-220">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="418c2-221">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-221">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-222">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-222">**Environment variable**</span></span> | `COMPlus_GCHeapAffinitizeRanges` | <span data-ttu-id="418c2-223">쉼표로 구분된 프로세서 번호 또는 프로세서 번호 범위 목록.</span><span class="sxs-lookup"><span data-stu-id="418c2-223">Comma-separated list of processor numbers or ranges of processor numbers.</span></span><br/><span data-ttu-id="418c2-224">Unix 예: “1-10,12,50-52,70”</span><span class="sxs-lookup"><span data-stu-id="418c2-224">Unix example: "1-10,12,50-52,70"</span></span><br/><span data-ttu-id="418c2-225">Windows 예: “0:1-10,0:12,1:50-52,1:70”</span><span class="sxs-lookup"><span data-stu-id="418c2-225">Windows example: "0:1-10,0:12,1:50-52,1:70"</span></span> | <span data-ttu-id="418c2-226">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-226">.NET Core 3.0</span></span> |

<span data-ttu-id="418c2-227">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-227">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="complus_gccpugroup"></a><span data-ttu-id="418c2-228">COMPlus_GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="418c2-228">COMPlus_GCCpuGroup</span></span>

- <span data-ttu-id="418c2-229">가비지 수집기가 [CPU 그룹](/windows/win32/procthread/processor-groups)을 사용하는지 여부는 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-229">Configures whether the garbage collector uses [CPU groups](/windows/win32/procthread/processor-groups) or not.</span></span>

  <span data-ttu-id="418c2-230">64비트 Windows 컴퓨터에 여러 개의 CPU 그룹이 있는 경우, 다시 말해서 64개가 넘는 프로세서가 있는 경우, 이 요소를 사용하도록 설정하면 가비지 수집이 모든 CPU 그룹으로 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-230">When a 64-bit Windows computer has multiple CPU groups, that is, there are more than 64 processors, enabling this element extends garbage collection across all CPU groups.</span></span> <span data-ttu-id="418c2-231">가비지 수집기는 모든 코어를 사용하여 힙을 만들고 분산합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-231">The garbage collector uses all cores to create and balance heaps.</span></span>

- <span data-ttu-id="418c2-232">64비트 Windows 운영 체제의 서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-232">Applies to server garbage collection on 64-bit Windows operation systems only.</span></span>
- <span data-ttu-id="418c2-233">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="418c2-233">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="418c2-234">자세한 내용은 Maoni Stephens의 블로그에서 [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/)(CPU가 64개가 넘는 머신에서 GC를 위한 CPU 구성 개선하기) 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-234">For more information, see [Making CPU configuration better for GC on machines with > 64 CPUs](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/) on Maoni Stephens' blog.</span></span>

| | <span data-ttu-id="418c2-235">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-235">Setting name</span></span> | <span data-ttu-id="418c2-236">값</span><span class="sxs-lookup"><span data-stu-id="418c2-236">Values</span></span> | <span data-ttu-id="418c2-237">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-237">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-238">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-238">**runtimeconfig.json**</span></span> | <span data-ttu-id="418c2-239">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-239">N/A</span></span> | <span data-ttu-id="418c2-240">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-240">N/A</span></span> | <span data-ttu-id="418c2-241">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-241">N/A</span></span> |
| <span data-ttu-id="418c2-242">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-242">**Environment variable**</span></span> | `COMPlus_GCCpuGroup` | <span data-ttu-id="418c2-243">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-243">`0` - disabled</span></span><br/><span data-ttu-id="418c2-244">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="418c2-244">`1` - enabled</span></span> | <span data-ttu-id="418c2-245">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-245">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-246">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-246">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-247">GCCpuGroup</span><span class="sxs-lookup"><span data-stu-id="418c2-247">GCCpuGroup</span></span>](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | <span data-ttu-id="418c2-248">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-248">`false` - disabled</span></span><br/><span data-ttu-id="418c2-249">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="418c2-249">`true` - enabled</span></span> |  |

> [!NOTE]
> <span data-ttu-id="418c2-250">모든 CPU 그룹의 스레드 풀에서도 스레드를 분산하도록 CLR(공용 언어 런타임)을 구성하려면 [Thread_UseAllCpuGroups 요소](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) 옵션을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-250">To configure the common language runtime (CLR) to also distribute threads from the thread pool across all CPU groups, enable the [Thread_UseAllCpuGroups element](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md) option.</span></span> <span data-ttu-id="418c2-251">.NET Core 앱의 경우, `COMPlus_Thread_UseAllCpuGroups` 환경 변수의 값을 `1`로 설정하여 이 옵션을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-251">For .NET Core apps, you can enable this option by setting the value of the `COMPlus_Thread_UseAllCpuGroups` environment variable to `1`.</span></span>

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a><span data-ttu-id="418c2-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="418c2-252">System.GC.NoAffinitize/COMPlus_GCNoAffinitize</span></span>

- <span data-ttu-id="418c2-253">가비지 수집 스레드가 프로세서를 *선호*하도록 지정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-253">Specifies whether to *affinitize* garbage collection threads with processors.</span></span> <span data-ttu-id="418c2-254">GC 스레드의 선호도를 지정한다는 것은 특정 CPU에서만 실행할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-254">To affinitize a GC thread means that it can only run on its specific CPU.</span></span> <span data-ttu-id="418c2-255">각 GC 스레드에 대해 힙이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-255">A heap is created for each GC thread.</span></span>
- <span data-ttu-id="418c2-256">서버 가비지 수집에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-256">Applies to server garbage collection only.</span></span>
- <span data-ttu-id="418c2-257">기본값: 가비지 수집 스레드가 프로세서를 선호하도록 지정(`false`).</span><span class="sxs-lookup"><span data-stu-id="418c2-257">Default: Affinitize garbage collection threads with processors (`false`).</span></span>

| | <span data-ttu-id="418c2-258">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-258">Setting name</span></span> | <span data-ttu-id="418c2-259">값</span><span class="sxs-lookup"><span data-stu-id="418c2-259">Values</span></span> | <span data-ttu-id="418c2-260">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-260">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-261">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-261">**runtimeconfig.json**</span></span> | `System.GC.NoAffinitize` | <span data-ttu-id="418c2-262">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="418c2-262">`false` - affinitize</span></span><br/><span data-ttu-id="418c2-263">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-263">`true` - don't affinitize</span></span> | <span data-ttu-id="418c2-264">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-264">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-265">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-265">**Environment variable**</span></span> | `COMPlus_GCNoAffinitize` | <span data-ttu-id="418c2-266">`0` - 선호</span><span class="sxs-lookup"><span data-stu-id="418c2-266">`0` - affinitize</span></span><br/><span data-ttu-id="418c2-267">`1` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-267">`1` - don't affinitize</span></span> | <span data-ttu-id="418c2-268">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-268">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-269">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-269">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-270">GCNoAffinitize</span><span class="sxs-lookup"><span data-stu-id="418c2-270">GCNoAffinitize</span></span>](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | <span data-ttu-id="418c2-271">`false` - 선호</span><span class="sxs-lookup"><span data-stu-id="418c2-271">`false` - affinitize</span></span><br/><span data-ttu-id="418c2-272">`true` - 선호 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-272">`true` - don't affinitize</span></span> | <span data-ttu-id="418c2-273">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="418c2-273">.NET Framework 4.6.2</span></span> |

<span data-ttu-id="418c2-274">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-274">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a><span data-ttu-id="418c2-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span><span class="sxs-lookup"><span data-stu-id="418c2-275">System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit</span></span>

- <span data-ttu-id="418c2-276">GC 힙 및 GC 기록의 최대 커밋 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-276">Specifies the maximum commit size, in bytes, for the GC heap and GC bookkeeping.</span></span>

| | <span data-ttu-id="418c2-277">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-277">Setting name</span></span> | <span data-ttu-id="418c2-278">값</span><span class="sxs-lookup"><span data-stu-id="418c2-278">Values</span></span> | <span data-ttu-id="418c2-279">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-279">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-280">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-280">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimit` | <span data-ttu-id="418c2-281">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-281">*decimal value*</span></span> | <span data-ttu-id="418c2-282">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-282">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-283">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-283">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimit` | <span data-ttu-id="418c2-284">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-284">*hexadecimal value*</span></span> | <span data-ttu-id="418c2-285">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-285">.NET Core 3.0</span></span> |

<span data-ttu-id="418c2-286">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-286">Example:</span></span>

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
> <span data-ttu-id="418c2-287">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-287">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="418c2-288">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-288">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="418c2-289">예를 들어, 힙의 하드 한도를 200메비바이트(MiB) 지정하려면 JSON 파일의 경우 값을 209715200으로 지정하고 환경 변수의 경우 값을 0xC800000 또는 C800000으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-289">For example, to specify a heap hard limit of 200 mebibytes (MiB), the values would be 209715200 for the JSON file and 0xC800000 or C800000 for the environment variable.</span></span>

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a><span data-ttu-id="418c2-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span><span class="sxs-lookup"><span data-stu-id="418c2-290">System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent</span></span>

- <span data-ttu-id="418c2-291">GC 힙의 사용량을 총 메모리의 백분율로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-291">Specifies the GC heap usage as a percentage of the total memory.</span></span>

| | <span data-ttu-id="418c2-292">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-292">Setting name</span></span> | <span data-ttu-id="418c2-293">값</span><span class="sxs-lookup"><span data-stu-id="418c2-293">Values</span></span> | <span data-ttu-id="418c2-294">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-294">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-295">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-295">**runtimeconfig.json**</span></span> | `System.GC.HeapHardLimitPercent` | <span data-ttu-id="418c2-296">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-296">*decimal value*</span></span> | <span data-ttu-id="418c2-297">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-297">.NET Core 3.0</span></span> |
| <span data-ttu-id="418c2-298">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-298">**Environment variable**</span></span> | `COMPlus_GCHeapHardLimitPercent` | <span data-ttu-id="418c2-299">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-299">*hexadecimal value*</span></span> | <span data-ttu-id="418c2-300">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-300">.NET Core 3.0</span></span> |

<span data-ttu-id="418c2-301">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-301">Example:</span></span>

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
> <span data-ttu-id="418c2-302">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-302">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="418c2-303">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-303">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="418c2-304">예를 들어, 힙의 사용량을 30%로 제한하려면 JSON 파일의 경우 값을 30으로 지정하고 환경 변수의 경우 값을 0x1E 또는 1E로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-304">For example, to limit the heap usage to 30%, the values would be 30 for the JSON file and 0x1E or 1E for the environment variable.</span></span>

### <a name="systemgcretainvmcomplus_gcretainvm"></a><span data-ttu-id="418c2-305">System.GC.RetainVM/COMPlus_GCRetainVM</span><span class="sxs-lookup"><span data-stu-id="418c2-305">System.GC.RetainVM/COMPlus_GCRetainVM</span></span>

- <span data-ttu-id="418c2-306">삭제해야 할 세그먼트를 나중에 사용할 수 있도록 대기 목록에 둘지 아니면 해제하여 운영 체제(OS)로 돌려보낼지를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-306">Configures whether segments that should be deleted are put on a standby list for future use or are released back to the operating system (OS).</span></span>
- <span data-ttu-id="418c2-307">기본값: 세그먼트를 해제하여 운영 체제로 돌려보냅니다(`false`).</span><span class="sxs-lookup"><span data-stu-id="418c2-307">Default: Release segments back to the operating system (`false`).</span></span>

| | <span data-ttu-id="418c2-308">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-308">Setting name</span></span> | <span data-ttu-id="418c2-309">값</span><span class="sxs-lookup"><span data-stu-id="418c2-309">Values</span></span> | <span data-ttu-id="418c2-310">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-310">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-311">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-311">**runtimeconfig.json**</span></span> | `System.GC.RetainVM` | <span data-ttu-id="418c2-312">`false` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="418c2-312">`false` - release to OS</span></span><br/><span data-ttu-id="418c2-313">`true` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="418c2-313">`true` - put on standby</span></span>| <span data-ttu-id="418c2-314">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-314">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-315">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-315">**Environment variable**</span></span> | `COMPlus_GCRetainVM` | <span data-ttu-id="418c2-316">`0` - OS로 해제</span><span class="sxs-lookup"><span data-stu-id="418c2-316">`0` - release to OS</span></span><br/><span data-ttu-id="418c2-317">`1` - 대기 목록에 두기</span><span class="sxs-lookup"><span data-stu-id="418c2-317">`1` - put on standby</span></span> | <span data-ttu-id="418c2-318">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-318">.NET Core 1.0</span></span> |

<span data-ttu-id="418c2-319">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-319">Example:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

## <a name="large-pages"></a><span data-ttu-id="418c2-320">큰 페이지</span><span class="sxs-lookup"><span data-stu-id="418c2-320">Large pages</span></span>

### <a name="complus_gclargepages"></a><span data-ttu-id="418c2-321">COMPlus_GCLargePages</span><span class="sxs-lookup"><span data-stu-id="418c2-321">COMPlus_GCLargePages</span></span>

- <span data-ttu-id="418c2-322">힙의 하드 한도가 설정된 경우 큰 페이지를 사용할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-322">Specifies whether large pages should be used when a heap hard limit is set.</span></span>
- <span data-ttu-id="418c2-323">기본값: 사용 안 함(`0`).</span><span class="sxs-lookup"><span data-stu-id="418c2-323">Default: Disabled (`0`).</span></span>
- <span data-ttu-id="418c2-324">이것은 실험적인 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-324">This is an experimental setting.</span></span>

| | <span data-ttu-id="418c2-325">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-325">Setting name</span></span> | <span data-ttu-id="418c2-326">값</span><span class="sxs-lookup"><span data-stu-id="418c2-326">Values</span></span> | <span data-ttu-id="418c2-327">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-327">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-328">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-328">**runtimeconfig.json**</span></span> | <span data-ttu-id="418c2-329">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-329">N/A</span></span> | <span data-ttu-id="418c2-330">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-330">N/A</span></span> | <span data-ttu-id="418c2-331">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-331">N/A</span></span> |
| <span data-ttu-id="418c2-332">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-332">**Environment variable**</span></span> | `COMPlus_GCLargePages` | <span data-ttu-id="418c2-333">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-333">`0` - disabled</span></span><br/><span data-ttu-id="418c2-334">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="418c2-334">`1` - enabled</span></span> | <span data-ttu-id="418c2-335">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="418c2-335">.NET Core 3.0</span></span> |

## <a name="large-objects"></a><span data-ttu-id="418c2-336">큰 개체</span><span class="sxs-lookup"><span data-stu-id="418c2-336">Large objects</span></span>

### <a name="complus_gcallowverylargeobjects"></a><span data-ttu-id="418c2-337">COMPlus_gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="418c2-337">COMPlus_gcAllowVeryLargeObjects</span></span>

- <span data-ttu-id="418c2-338">64비트 플랫폼에서 총 크기가 2기가바이트(GB)보다 큰 배열에 대한 가비지 수집기 지원을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-338">Configures garbage collector support on 64-bit platforms for arrays that are greater than 2 gigabytes (GB) in total size.</span></span>
- <span data-ttu-id="418c2-339">기본값: 사용(`1`).</span><span class="sxs-lookup"><span data-stu-id="418c2-339">Default: Enabled (`1`).</span></span>
- <span data-ttu-id="418c2-340">이 옵션은 이후 버전의 .NET에서 더 이상 사용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-340">This option may become obsolete in a future version of .NET.</span></span>

| | <span data-ttu-id="418c2-341">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-341">Setting name</span></span> | <span data-ttu-id="418c2-342">값</span><span class="sxs-lookup"><span data-stu-id="418c2-342">Values</span></span> | <span data-ttu-id="418c2-343">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-343">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-344">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-344">**runtimeconfig.json**</span></span> | <span data-ttu-id="418c2-345">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-345">N/A</span></span> | <span data-ttu-id="418c2-346">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-346">N/A</span></span> | <span data-ttu-id="418c2-347">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-347">N/A</span></span> |
| <span data-ttu-id="418c2-348">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-348">**Environment variable**</span></span> | `COMPlus_gcAllowVeryLargeObjects` | <span data-ttu-id="418c2-349">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="418c2-349">`1` - enabled</span></span><br/> <span data-ttu-id="418c2-350">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-350">`0` - disabled</span></span> | <span data-ttu-id="418c2-351">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-351">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-352">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-352">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-353">gcAllowVeryLargeObjects</span><span class="sxs-lookup"><span data-stu-id="418c2-353">gcAllowVeryLargeObjects</span></span>](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | <span data-ttu-id="418c2-354">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="418c2-354">`1` - enabled</span></span><br/> <span data-ttu-id="418c2-355">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="418c2-355">`0` - disabled</span></span> | <span data-ttu-id="418c2-356">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="418c2-356">.NET Framework 4.5</span></span> |

## <a name="large-object-heap-threshold"></a><span data-ttu-id="418c2-357">큰 개체 힙 임계값</span><span class="sxs-lookup"><span data-stu-id="418c2-357">Large object heap threshold</span></span>

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a><span data-ttu-id="418c2-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="418c2-358">System.GC.LOHThreshold/COMPlus_GCLOHThreshold</span></span>

- <span data-ttu-id="418c2-359">개체가 큰 개체 힙(LOH)으로 이동되도록 하는 임계값 크기를 바이트 단위로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-359">Specifies the threshold size, in bytes, that causes objects to go on the large object heap (LOH).</span></span>
- <span data-ttu-id="418c2-360">기본 임계값은 85,000바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-360">The default threshold is 85,000 bytes.</span></span>
- <span data-ttu-id="418c2-361">사용자가 지정하는 값은 기본 임계값보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-361">The value you specify must be larger than the default threshold.</span></span>

| | <span data-ttu-id="418c2-362">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-362">Setting name</span></span> | <span data-ttu-id="418c2-363">값</span><span class="sxs-lookup"><span data-stu-id="418c2-363">Values</span></span> | <span data-ttu-id="418c2-364">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-364">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-365">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-365">**runtimeconfig.json**</span></span> | `System.GC.LOHThreshold` | <span data-ttu-id="418c2-366">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-366">*decimal value*</span></span> | <span data-ttu-id="418c2-367">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-367">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-368">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-368">**Environment variable**</span></span> | `COMPlus_GCLOHThreshold` | <span data-ttu-id="418c2-369">*16진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-369">*hexadecimal value*</span></span> | <span data-ttu-id="418c2-370">.NET Core 1.0</span><span class="sxs-lookup"><span data-stu-id="418c2-370">.NET Core 1.0</span></span> |
| <span data-ttu-id="418c2-371">**.NET Framework의 app.config**</span><span class="sxs-lookup"><span data-stu-id="418c2-371">**app.config for .NET Framework**</span></span> | [<span data-ttu-id="418c2-372">GCLOHThreshold</span><span class="sxs-lookup"><span data-stu-id="418c2-372">GCLOHThreshold</span></span>](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | <span data-ttu-id="418c2-373">*10진수 값*</span><span class="sxs-lookup"><span data-stu-id="418c2-373">*decimal value*</span></span> | <span data-ttu-id="418c2-374">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="418c2-374">.NET Framework 4.8</span></span> |

<span data-ttu-id="418c2-375">예:</span><span class="sxs-lookup"><span data-stu-id="418c2-375">Example:</span></span>

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
> <span data-ttu-id="418c2-376">*runtimeconfig.json*의 옵션을 설정할 때는 10진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-376">If you're setting the option in *runtimeconfig.json*, specify a decimal value.</span></span> <span data-ttu-id="418c2-377">옵션을 환경 변수로 설정할 때는 16진수 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-377">If you're setting the option as an environment variable, specify a hexadecimal value.</span></span> <span data-ttu-id="418c2-378">예를 들어, 임계값 크기를 120,000바이트로 설정하려면 JSON 파일의 경우 값을 120000으로 지정하고 환경 변수의 경우 값을 0x1D4C0 또는 1D4C0으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-378">For example, to set a threshold size of 120,000 bytes, the values would be 120000 for the JSON file and 0x1D4C0 or 1D4C0 for the environment variable.</span></span>

## <a name="standalone-gc"></a><span data-ttu-id="418c2-379">독립 실행형 GC</span><span class="sxs-lookup"><span data-stu-id="418c2-379">Standalone GC</span></span>

### <a name="complus_gcname"></a><span data-ttu-id="418c2-380">COMPlus_GCName</span><span class="sxs-lookup"><span data-stu-id="418c2-380">COMPlus_GCName</span></span>

- <span data-ttu-id="418c2-381">런타임이 로드하려는 가비지 수집기를 포함하는 라이브러리의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="418c2-381">Specifies a path to the library containing the garbage collector that the runtime intends to load.</span></span>
- <span data-ttu-id="418c2-382">자세한 내용은 [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md)(독립 실행형 GC 로더 설계)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="418c2-382">For more information, see [Standalone GC loader design](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).</span></span>

| | <span data-ttu-id="418c2-383">설정 이름</span><span class="sxs-lookup"><span data-stu-id="418c2-383">Setting name</span></span> | <span data-ttu-id="418c2-384">값</span><span class="sxs-lookup"><span data-stu-id="418c2-384">Values</span></span> | <span data-ttu-id="418c2-385">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="418c2-385">Version introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="418c2-386">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="418c2-386">**runtimeconfig.json**</span></span> | <span data-ttu-id="418c2-387">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-387">N/A</span></span> | <span data-ttu-id="418c2-388">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-388">N/A</span></span> | <span data-ttu-id="418c2-389">N/A</span><span class="sxs-lookup"><span data-stu-id="418c2-389">N/A</span></span> |
| <span data-ttu-id="418c2-390">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="418c2-390">**Environment variable**</span></span> | `COMPlus_GCName` | <span data-ttu-id="418c2-391">*string_path*</span><span class="sxs-lookup"><span data-stu-id="418c2-391">*string_path*</span></span> | <span data-ttu-id="418c2-392">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="418c2-392">.NET Core 2.0</span></span> |
