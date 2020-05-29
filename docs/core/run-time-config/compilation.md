---
title: 컴파일 구성 설정
description: .NET Core 앱에 대해 JIT 컴파일러가 작동하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: cfcf9b5fc8d11a4ae35ab9b152f32133cd6930bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762008"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="38c39-103">컴파일을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="38c39-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="38c39-104">계층화된 컴파일</span><span class="sxs-lookup"><span data-stu-id="38c39-104">Tiered compilation</span></span>

- <span data-ttu-id="38c39-105">JIT(Just-In-Time) 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-105">Configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="38c39-106">계층화된 컴파일은 두 계층을 통해 메서드를 전환합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-106">Tiered compilation transitions methods through two tiers:</span></span>
  - <span data-ttu-id="38c39-107">첫 번째 계층은 코드를 더 빠르게 생성([빠른 JIT](#quick-jit))하거나 미리 컴파일된 코드([ReadyToRun](#readytorun))를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-107">The first tier generates code more quickly ([quick JIT](#quick-jit)) or loads pre-compiled code ([ReadyToRun](#readytorun)).</span></span>
  - <span data-ttu-id="38c39-108">두 번째 계층은 백그라운드에서 최적화된 코드를 생성합니다("JIT 최적화").</span><span class="sxs-lookup"><span data-stu-id="38c39-108">The second tier generates optimized code in the background ("optimizing JIT").</span></span>
- <span data-ttu-id="38c39-109">.NET Core 3.0 이상에서는 기본적으로 계층화된 컴파일이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-109">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="38c39-110">.NET Core 2.1 및 2.2에서는 기본적으로 계층화된 컴파일이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-110">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>
- <span data-ttu-id="38c39-111">자세한 내용은 [계층화된 컴파일 가이드](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38c39-111">For more information, see the [Tiered compilation guide](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation.md).</span></span>

| | <span data-ttu-id="38c39-112">설정 이름</span><span class="sxs-lookup"><span data-stu-id="38c39-112">Setting name</span></span> | <span data-ttu-id="38c39-113">값</span><span class="sxs-lookup"><span data-stu-id="38c39-113">Values</span></span> |
| - | - | - |
| <span data-ttu-id="38c39-114">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="38c39-114">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="38c39-115">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-115">`true` - enabled</span></span><br/><span data-ttu-id="38c39-116">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-116">`false` - disabled</span></span> |
| <span data-ttu-id="38c39-117">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="38c39-117">**MSBuild property**</span></span> | `TieredCompilation` | <span data-ttu-id="38c39-118">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-118">`true` - enabled</span></span><br/><span data-ttu-id="38c39-119">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-119">`false` - disabled</span></span> |
| <span data-ttu-id="38c39-120">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="38c39-120">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="38c39-121">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-121">`1` - enabled</span></span><br/><span data-ttu-id="38c39-122">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-122">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="38c39-123">예</span><span class="sxs-lookup"><span data-stu-id="38c39-123">Examples</span></span>

<span data-ttu-id="38c39-124">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-124">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation": false
      }
   }
}
```

<span data-ttu-id="38c39-125">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-125">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilation>false</TieredCompilation>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit"></a><span data-ttu-id="38c39-126">빠른 JIT</span><span class="sxs-lookup"><span data-stu-id="38c39-126">Quick JIT</span></span>

- <span data-ttu-id="38c39-127">JIT 컴파일러가 *빠른 JIT*를 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-127">Configures whether the JIT compiler uses *quick JIT*.</span></span> <span data-ttu-id="38c39-128">루프를 포함되어 있지 않고 미리 컴파일된 코드를 사용할 수 없는 메서드의 경우 빠른 JIT는 최적화하지 않고도 빠르게 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-128">For methods that don't contain loops and for which pre-compiled code is not available, quick JIT compiles them more quickly but without optimizations.</span></span>
- <span data-ttu-id="38c39-129">빠른 JIT를 사용하도록 설정하면 시작 시간이 단축되지만 성능 특성이 저하된 코드가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-129">Enabling quick JIT decreases startup time but can produce code with degraded performance characteristics.</span></span> <span data-ttu-id="38c39-130">예를 들어 코드에서 더 많은 스택 공간을 사용하고, 더 많은 메모리를 할당하며 느리게 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-130">For example, the code may use more stack space, allocate more memory, and run slower.</span></span>
- <span data-ttu-id="38c39-131">빠른 JIT를 사용하지 않도록 설정하고 [계층화된 컴파일](#tiered-compilation)을 사용하도록 설정한 경우에는 미리 컴파일된 코드만 계층화된 컴파일에 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-131">If quick JIT is disabled but [tiered compilation](#tiered-compilation) is enabled, only pre-compiled code participates in tiered compilation.</span></span> <span data-ttu-id="38c39-132">메서드를 [ReadyToRun](#readytorun)으로 미리 컴파일하지 않은 경우 JIT 동작은 [계층화된 컴파일](#tiered-compilation)이 사용하지 않도록 설정된 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-132">If a method is not pre-compiled with [ReadyToRun](#readytorun), the JIT behavior is the same as if [tiered compilation](#tiered-compilation) were disabled.</span></span>
- <span data-ttu-id="38c39-133">.NET Core 3.0 이상에서는 기본적으로 빠른 JIT가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-133">In .NET Core 3.0 and later, quick JIT is enabled by default.</span></span>
- <span data-ttu-id="38c39-134">.NET Core 2.1 및 2.2에서는 기본적으로 빠른 JIT가 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-134">In .NET Core 2.1 and 2.2, quick JIT is disabled by default.</span></span>

| | <span data-ttu-id="38c39-135">설정 이름</span><span class="sxs-lookup"><span data-stu-id="38c39-135">Setting name</span></span> | <span data-ttu-id="38c39-136">값</span><span class="sxs-lookup"><span data-stu-id="38c39-136">Values</span></span> |
| - | - | - |
| <span data-ttu-id="38c39-137">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="38c39-137">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJit` | <span data-ttu-id="38c39-138">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-138">`true` - enabled</span></span><br/><span data-ttu-id="38c39-139">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-139">`false` - disabled</span></span> |
| <span data-ttu-id="38c39-140">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="38c39-140">**MSBuild property**</span></span> | `TieredCompilationQuickJit` | <span data-ttu-id="38c39-141">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-141">`true` - enabled</span></span><br/><span data-ttu-id="38c39-142">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-142">`false` - disabled</span></span> |
| <span data-ttu-id="38c39-143">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="38c39-143">**Environment variable**</span></span> | `COMPlus_TC_QuickJit` | <span data-ttu-id="38c39-144">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-144">`1` - enabled</span></span><br/><span data-ttu-id="38c39-145">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-145">`0` - disabled</span></span> |

### <a name="examples"></a><span data-ttu-id="38c39-146">예</span><span class="sxs-lookup"><span data-stu-id="38c39-146">Examples</span></span>

<span data-ttu-id="38c39-147">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-147">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJit": false
      }
   }
}
```

<span data-ttu-id="38c39-148">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-148">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
  </PropertyGroup>

</Project>
```

## <a name="quick-jit-for-loops"></a><span data-ttu-id="38c39-149">루프에 대한 빠른 JIT</span><span class="sxs-lookup"><span data-stu-id="38c39-149">Quick JIT for loops</span></span>

- <span data-ttu-id="38c39-150">JIT 컴파일러가 루프를 포함하는 메서드에서 빠른 JIT를 사용할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-150">Configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span>
- <span data-ttu-id="38c39-151">루프에 대한 빠른 JIT를 사용하도록 설정하면 시작 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-151">Enabling quick JIT for loops may improve startup performance.</span></span> <span data-ttu-id="38c39-152">그러나 장기 실행 루프의 경우 오랜 기간 동안 덜 최적화된 코드에서 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-152">However, long-running loops can get stuck in less-optimized code for long periods.</span></span>
- <span data-ttu-id="38c39-153">[빠른 JIT](#quick-jit)를 사용하지 않도록 설정한 경우에는 이 설정이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-153">If [quick JIT](#quick-jit) is disabled, this setting has no effect.</span></span>
- <span data-ttu-id="38c39-154">이 설정을 생략하면 루프를 포함하는 메서드에 대해 빠른 JIT가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-154">If you omit this setting, quick JIT is not used for methods that contain loops.</span></span> <span data-ttu-id="38c39-155">이는 값을 `false`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-155">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="38c39-156">설정 이름</span><span class="sxs-lookup"><span data-stu-id="38c39-156">Setting name</span></span> | <span data-ttu-id="38c39-157">값</span><span class="sxs-lookup"><span data-stu-id="38c39-157">Values</span></span> |
| - | - | - |
| <span data-ttu-id="38c39-158">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="38c39-158">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation.QuickJitForLoops` | <span data-ttu-id="38c39-159">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-159">`false` - disabled</span></span><br/><span data-ttu-id="38c39-160">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-160">`true` - enabled</span></span> |
| <span data-ttu-id="38c39-161">**MSBuild 속성**</span><span class="sxs-lookup"><span data-stu-id="38c39-161">**MSBuild property**</span></span> | `TieredCompilationQuickJitForLoops` | <span data-ttu-id="38c39-162">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-162">`false` - disabled</span></span><br/><span data-ttu-id="38c39-163">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-163">`true` - enabled</span></span> |
| <span data-ttu-id="38c39-164">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="38c39-164">**Environment variable**</span></span> | `COMPlus_TC_QuickJitForLoops` | <span data-ttu-id="38c39-165">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-165">`0` - disabled</span></span><br/><span data-ttu-id="38c39-166">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-166">`1` - enabled</span></span> |

### <a name="examples"></a><span data-ttu-id="38c39-167">예</span><span class="sxs-lookup"><span data-stu-id="38c39-167">Examples</span></span>

<span data-ttu-id="38c39-168">*runtimeconfig.json* 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-168">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Runtime.TieredCompilation.QuickJitForLoops": false
      }
   }
}
```

<span data-ttu-id="38c39-169">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="38c39-169">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
  </PropertyGroup>

</Project>
```

## <a name="readytorun"></a><span data-ttu-id="38c39-170">ReadyToRun</span><span class="sxs-lookup"><span data-stu-id="38c39-170">ReadyToRun</span></span>

- <span data-ttu-id="38c39-171">.NET Core 런타임이 사용 가능한 ReadyToRun 데이터가 포함된 이미지에 미리 컴파일된 코드를 사용하도록 할지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-171">Configures whether the .NET Core runtime uses pre-compiled code for images with available ReadyToRun data.</span></span> <span data-ttu-id="38c39-172">이 옵션을 사용하지 않도록 설정하면 런타임에서 프레임워크 코드를 강제로 JIT 컴파일하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-172">Disabling this option forces the runtime to JIT-compile framework code.</span></span>
- <span data-ttu-id="38c39-173">자세한 내용은 [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38c39-173">For more information, see [ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images).</span></span>
- <span data-ttu-id="38c39-174">이 설정을 생략하면 .NET은 사용 가능한 경우 ReadyToRun 데이터를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-174">If you omit this setting, .NET uses ReadyToRun data when it's available.</span></span> <span data-ttu-id="38c39-175">이는 값을 `1`로 설정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="38c39-175">This is equivalent to setting the value to `1`.</span></span>

| | <span data-ttu-id="38c39-176">설정 이름</span><span class="sxs-lookup"><span data-stu-id="38c39-176">Setting name</span></span> | <span data-ttu-id="38c39-177">값</span><span class="sxs-lookup"><span data-stu-id="38c39-177">Values</span></span> |
| - | - | - |
| <span data-ttu-id="38c39-178">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="38c39-178">**Environment variable**</span></span> | `COMPlus_ReadyToRun` | <span data-ttu-id="38c39-179">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="38c39-179">`1` - enabled</span></span><br/><span data-ttu-id="38c39-180">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="38c39-180">`0` - disabled</span></span> |
