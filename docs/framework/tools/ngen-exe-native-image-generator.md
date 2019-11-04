---
title: Ngen.exe(네이티브 이미지 생성기)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Native Image Generator
- images [.NET Framework], native
- side-by-side execution, native images
- assemblies [.NET Framework], native image
- Ngen.exe
- native image generation
- native image cache
- publisher policy applied for native images
- invalid images
- BypassNGenAttribute
- System.Runtime.BypassNGenAttribute
ms.assetid: 44bf97aa-a9a4-4eba-9a0d-cfaa6fc53a66
ms.openlocfilehash: e6c4baae854e5997b153e1363ca8ed4204e10e2b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085203"
---
# <a name="ngenexe-native-image-generator"></a><span data-ttu-id="aab82-102">Ngen.exe(네이티브 이미지 생성기)</span><span class="sxs-lookup"><span data-stu-id="aab82-102">Ngen.exe (Native Image Generator)</span></span>

<span data-ttu-id="aab82-103">네이티브 이미지 생성기(Ngen.exe)는 관리되는 애플리케이션의 성능을 향상시키는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-103">The Native Image Generator (Ngen.exe) is a tool that improves the performance of managed applications.</span></span> <span data-ttu-id="aab82-104">Ngen.exe는 컴파일된 프로세서별 컴퓨터 코드가 포함된 파일인 네이티브 이미지를 만들어서 로컬 컴퓨터의 네이티브 이미지 캐시에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-104">Ngen.exe creates native images, which are files containing compiled processor-specific machine code, and installs them into the native image cache on the local computer.</span></span> <span data-ttu-id="aab82-105">런타임은 JIT(Just-In-Time) 컴파일러를 사용하지 않고 캐시의 네이티브 이미지를 사용하여 원본 어셈블리를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-105">The runtime can use native images from the cache instead of using the just-in-time (JIT) compiler to compile the original assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-106">Ngen.exe는 .NET Framework만을 대상으로 하는 어셈블리에 대한 네이티브 이미지를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-106">Ngen.exe compiles native images for assemblies that target the .NET Framework only.</span></span> <span data-ttu-id="aab82-107">.NET Core에 해당하는 네이티브 이미지 생성기는 [CrossGen](https://github.com/dotnet/coreclr/blob/master/Documentation/building/crossgen.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-107">The equivalent native image generator for .NET Core is [CrossGen](https://github.com/dotnet/coreclr/blob/master/Documentation/building/crossgen.md).</span></span> 

<span data-ttu-id="aab82-108">.NET Framework 버전 4에서 Ngen.exe로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-108">Changes to Ngen.exe in the .NET Framework 4:</span></span>

- <span data-ttu-id="aab82-109">이제 Ngen.exe가 완전 신뢰로 어셈블리를 컴파일하고 CAS(코드 액세스 보안) 정책이 더 이상 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-109">Ngen.exe now compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

- <span data-ttu-id="aab82-110">Ngen.exe로 생성되는 네이티브 이미지는 부분 신뢰로 실행되는 애플리케이션에 더 이상 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-110">Native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span>

<span data-ttu-id="aab82-111">.NET Framework 버전 2.0에서 Ngen.exe로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-111">Changes to Ngen.exe in the .NET Framework version 2.0:</span></span>

- <span data-ttu-id="aab82-112">어셈블리를 설치하면 종속성도 함께 설치되어 Ngen.exe의 구문이 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-112">Installing an assembly also installs its dependencies, simplifying the syntax of Ngen.exe.</span></span>

- <span data-ttu-id="aab82-113">이제 애플리케이션 도메인 간에 네이티브 이미지를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-113">Native images can now be shared across application domains.</span></span>

- <span data-ttu-id="aab82-114">새로운 작업인 `update`는 무효화된 이미지를 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-114">A new action, `update`, re-creates images that have been invalidated.</span></span>

- <span data-ttu-id="aab82-115">이미지를 생성하고 설치할 컴퓨터에서 유휴 시간에 서비스 실행 작업을 지연시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-115">Actions can be deferred for execution by a service that uses idle time on the computer to generate and install images.</span></span>

- <span data-ttu-id="aab82-116">이미지를 무효화시키는 몇 가지 원인이 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-116">Some causes of image invalidation have been eliminated.</span></span>

<span data-ttu-id="aab82-117">Windows 8에서는 [네이티브 이미지 작업](#native-image-task)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-117">On Windows 8, see [Native Image Task](#native-image-task).</span></span>

<span data-ttu-id="aab82-118">Ngen.exe 및 네이티브 이미지 서비스 사용에 대한 자세한 내용은 [네이티브 이미지 서비스](#native-image-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-118">For additional information on using Ngen.exe and the native image service, see [Native Image Service](#native-image-service).</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-119">.NET Framework 버전 1.0 및 1.1의 Ngen.exe 구문은 [네이티브 이미지 생성기(Ngen.exe) 레거시 구문](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100))에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-119">Ngen.exe syntax for versions 1.0 and 1.1 of the .NET Framework can be found in [Native Image Generator (Ngen.exe) Legacy Syntax](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms165073(v=vs.100)).</span></span>

<span data-ttu-id="aab82-120">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-120">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="aab82-121">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-121">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="aab82-122">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-122">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="aab82-123">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-123">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="aab82-124">구문</span><span class="sxs-lookup"><span data-stu-id="aab82-124">Syntax</span></span>

```console
ngen action [options]
```

```console
ngen /? | /help
```

## <a name="actions"></a><span data-ttu-id="aab82-125">작업</span><span class="sxs-lookup"><span data-stu-id="aab82-125">Actions</span></span>

<span data-ttu-id="aab82-126">다음 표에서는 각 `action`의 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-126">The following table shows the syntax of each `action`.</span></span> <span data-ttu-id="aab82-127">`action`의 각 부분에 대한 설명은 [인수](#ArgumentTable), [우선 순위 수준](#PriorityTable), [시나리오](#ScenarioTable) 및 [구성](#ConfigTable) 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-127">For descriptions of the individual parts of an `action`, see the [Arguments](#ArgumentTable), [Priority Levels](#PriorityTable), [Scenarios](#ScenarioTable), and [Config](#ConfigTable) tables.</span></span> <span data-ttu-id="aab82-128">[옵션](#OptionTable) 표에서는 `options` 및 도움말 스위치에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-128">The [Options](#OptionTable) table describes the `options` and the help switches.</span></span>

|<span data-ttu-id="aab82-129">작업</span><span class="sxs-lookup"><span data-stu-id="aab82-129">Action</span></span>|<span data-ttu-id="aab82-130">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-130">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="aab82-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span><span class="sxs-lookup"><span data-stu-id="aab82-131">`install` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`] [`/queue`[`:`{`1`&#124;`2`&#124;`3`}]]</span></span>|<span data-ttu-id="aab82-132">어셈블리 및 해당 종속성에 대한 네이티브 이미지를 생성하고 그러한 이미지를 네이티브 이미지 캐시에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-132">Generate native images for an assembly and its dependencies and install the images in the native image cache.</span></span><br /><br /> <span data-ttu-id="aab82-133">`/queue`를 지정하면 네이티브 이미지 서비스에 대한 작업이 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-133">If `/queue` is specified, the action is queued for the native image service.</span></span> <span data-ttu-id="aab82-134">기본 우선 순위는 3입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-134">The default priority is 3.</span></span> <span data-ttu-id="aab82-135">[우선 순위 수준](#PriorityTable) 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-135">See the [Priority Levels](#PriorityTable) table.</span></span>|
|<span data-ttu-id="aab82-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span><span class="sxs-lookup"><span data-stu-id="aab82-136">`uninstall` [`assemblyName` &#124; `assemblyPath`] [`scenarios`] [`config`]</span></span>|<span data-ttu-id="aab82-137">네이티브 이미지 캐시에서 어셈블리에 대한 네이티브 이미지와 그 종속성을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-137">Delete the native images of an assembly and its dependencies from the native image cache.</span></span><br /><br /> <span data-ttu-id="aab82-138">단일 이미지와 그 종속성을 제거하려면 해당 이미지를 설치할 때 사용한 것과 동일한 명령줄 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-138">To uninstall a single image and its dependencies, use the same command-line arguments that were used to install the image.</span></span> <span data-ttu-id="aab82-139">**참고:**  .NET Framework 4부터는 `uninstall` \* 동작이 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-139">**Note:**  Starting with the .NET Framework 4, the action `uninstall` \* is no longer supported.</span></span>|
|<span data-ttu-id="aab82-140">`update` [`/queue`]</span><span class="sxs-lookup"><span data-stu-id="aab82-140">`update` [`/queue`]</span></span>|<span data-ttu-id="aab82-141">무효화된 네이티브 이미지를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-141">Update native images that have become invalid.</span></span><br /><br /> <span data-ttu-id="aab82-142">`/queue`를 지정하면 네이티브 이미지 서비스에 대한 업데이트가 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-142">If `/queue` is specified, the updates are queued for the native image service.</span></span> <span data-ttu-id="aab82-143">업데이트는 항상 우선 순위 3에서 예약되므로 컴퓨터가 유휴 상태일 때 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-143">Updates are always scheduled at priority 3, so they run when the computer is idle.</span></span>|
|<span data-ttu-id="aab82-144">`display` [`assemblyName` &#124; `assemblyPath`]</span><span class="sxs-lookup"><span data-stu-id="aab82-144">`display` [`assemblyName` &#124; `assemblyPath`]</span></span>|<span data-ttu-id="aab82-145">어셈블리에 대한 네이티브 이미지와 그 종속성의 상태를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-145">Display the state of the native images for an assembly and its dependencies.</span></span><br /><br /> <span data-ttu-id="aab82-146">인수를 지정하지 않은 경우 네이티브 이미지 캐시에 있는 모든 것이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-146">If no argument is supplied, everything in the native image cache is displayed.</span></span>|
|<span data-ttu-id="aab82-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span><span class="sxs-lookup"><span data-stu-id="aab82-147">`executeQueuedItems` [<code>1&#124;2&#124;3</code>]</span></span><br /><br /> <span data-ttu-id="aab82-148">또는</span><span class="sxs-lookup"><span data-stu-id="aab82-148">-or-</span></span><br /><br /> <span data-ttu-id="aab82-149">`eqi` [1&#124;2&#124;3]</span><span class="sxs-lookup"><span data-stu-id="aab82-149">`eqi` [1&#124;2&#124;3]</span></span>|<span data-ttu-id="aab82-150">큐에 대기한 컴파일 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-150">Execute queued compilation jobs.</span></span><br /><br /> <span data-ttu-id="aab82-151">우선 순위를 지정하면 우선 순위가 크거나 같은 컴파일 작업이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-151">If a priority is specified, compilation jobs with greater or equal priority are executed.</span></span> <span data-ttu-id="aab82-152">우선 순위를 지정하지 않으면 큐에 대기한 컴파일 작업이 모두 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-152">If no priority is specified, all queued compilation jobs are executed.</span></span>|
|<span data-ttu-id="aab82-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span><span class="sxs-lookup"><span data-stu-id="aab82-153">`queue` {`pause` &#124; `continue` &#124; `status`}</span></span>|<span data-ttu-id="aab82-154">네이티브 이미지 서비스를 일시 중지하거나 일시 중지된 서비스를 계속 수행할 수 있도록 하거나 서비스 상태를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-154">Pause the native image service, allow the paused service to continue, or query the status of the service.</span></span>|

<a name="ArgumentTable"></a>

## <a name="arguments"></a><span data-ttu-id="aab82-155">인수</span><span class="sxs-lookup"><span data-stu-id="aab82-155">Arguments</span></span>

|<span data-ttu-id="aab82-156">인수</span><span class="sxs-lookup"><span data-stu-id="aab82-156">Argument</span></span>|<span data-ttu-id="aab82-157">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-157">Description</span></span>|
|--------------|-----------------|
|`assemblyName`|<span data-ttu-id="aab82-158">어셈블리의 전체 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-158">The full display name of the assembly.</span></span> <span data-ttu-id="aab82-159">예: `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span><span class="sxs-lookup"><span data-stu-id="aab82-159">For example, `"myAssembly, Version=2.0.0.0, Culture=neutral, PublicKeyToken=0038abc9deabfle5"`.</span></span> <span data-ttu-id="aab82-160">**참고:**  `myAssembly` 및 `display` 작업의 경우 `uninstall`와 같은 부분 어셈블리 이름을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-160">**Note:**  You can supply a partial assembly name, such as `myAssembly`, for the `display` and `uninstall` actions.</span></span> <br /><br /> <span data-ttu-id="aab82-161">Ngen.exe 명령줄 당 어셈블리를 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-161">Only one assembly can be specified per Ngen.exe command line.</span></span>|
|`assemblyPath`|<span data-ttu-id="aab82-162">어셈블리의 명시적 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-162">The explicit path of the assembly.</span></span> <span data-ttu-id="aab82-163">전체 또는 상대 경로를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-163">You can specify a full or relative path.</span></span><br /><br /> <span data-ttu-id="aab82-164">경로 없이 파일 이름을 지정하는 경우 어셈블리가 현재 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-164">If you specify a file name without a path, the assembly must be located in the current directory.</span></span><br /><br /> <span data-ttu-id="aab82-165">Ngen.exe 명령줄 당 어셈블리를 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-165">Only one assembly can be specified per Ngen.exe command line.</span></span>|

<a name="PriorityTable"></a>

## <a name="priority-levels"></a><span data-ttu-id="aab82-166">우선 순위 수준</span><span class="sxs-lookup"><span data-stu-id="aab82-166">Priority Levels</span></span>

|<span data-ttu-id="aab82-167">우선 순위</span><span class="sxs-lookup"><span data-stu-id="aab82-167">Priority</span></span>|<span data-ttu-id="aab82-168">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-168">Description</span></span>|
|--------------|-----------------|
|`1`|<span data-ttu-id="aab82-169">네이티브 이미지는 유휴 시간을 기다리지 않고 즉시 생성 및 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-169">Native images are generated and installed immediately, without waiting for idle time.</span></span>|
|`2`|<span data-ttu-id="aab82-170">네이티브 이미지가 유휴 시간을 기다리지 않고 생성 후 설치되지만 모든 우선 순위 1 이후의 작업(및 해당 종속성)은 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-170">Native images are generated and installed without waiting for idle time, but after all priority 1 actions (and their dependencies) have completed.</span></span>|
|`3`|<span data-ttu-id="aab82-171">네이티브 이미지는 네이티브 이미지 서비스에서 컴퓨터의 유휴 상태를 감지할 때 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-171">Native images are installed when the native image service detects that the computer is idle.</span></span> <span data-ttu-id="aab82-172">[네이티브 이미지 서비스](#native-image-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-172">See [Native Image Service](#native-image-service).</span></span>|

<a name="ScenarioTable"></a>

## <a name="scenarios"></a><span data-ttu-id="aab82-173">시나리오</span><span class="sxs-lookup"><span data-stu-id="aab82-173">Scenarios</span></span>

|<span data-ttu-id="aab82-174">시나리오</span><span class="sxs-lookup"><span data-stu-id="aab82-174">Scenario</span></span>|<span data-ttu-id="aab82-175">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-175">Description</span></span>|
|--------------|-----------------|
|`/Debug`|<span data-ttu-id="aab82-176">디버거에서 사용할 수 있는 네이티브 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-176">Generate native images that can be used under a debugger.</span></span>|
|`/Profile`|<span data-ttu-id="aab82-177">프로파일러에서 사용할 수 있는 네이티브 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-177">Generate native images that can be used under a profiler.</span></span>|
|`/NoDependencies`|<span data-ttu-id="aab82-178">지정한 시나리오 옵션에 필요한 최소 네이티브 이미지 수를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-178">Generate the minimum number of native images required by the specified scenario options.</span></span>|

<a name="ConfigTable"></a>

## <a name="config"></a><span data-ttu-id="aab82-179">Config</span><span class="sxs-lookup"><span data-stu-id="aab82-179">Config</span></span>

|<span data-ttu-id="aab82-180">구성</span><span class="sxs-lookup"><span data-stu-id="aab82-180">Configuration</span></span>|<span data-ttu-id="aab82-181">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-181">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="aab82-182">`/ExeConfig:` `exePath`</span><span class="sxs-lookup"><span data-stu-id="aab82-182">`/ExeConfig:` `exePath`</span></span>|<span data-ttu-id="aab82-183">지정한 실행 어셈블리의 구성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-183">Use the configuration of the specified executable assembly.</span></span><br /><br /> <span data-ttu-id="aab82-184">Ngen.exe는 종속성에 바인딩할 때 로더와 같은 결정을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-184">Ngen.exe needs to make the same decisions as the loader when binding to dependencies.</span></span> <span data-ttu-id="aab82-185">공유 구성 요소가 런타임 시 로드되면 애플리케이션의 구성 파일은 <xref:System.Reflection.Assembly.Load%2A> 메서드를 사용하여 공유 구성 요소에 대해 로드된 종속성을 결정합니다(예: 로드된 종속성 버전).</span><span class="sxs-lookup"><span data-stu-id="aab82-185">When a shared component is loaded at run time, using the <xref:System.Reflection.Assembly.Load%2A> method, the application's configuration file determines the dependencies that are loaded for the shared component — for example, the version of a dependency that is loaded.</span></span> <span data-ttu-id="aab82-186">`/ExeConfig` 스위치는 런타임 시 종속성을 로드하는 Ngen.exe 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-186">The `/ExeConfig` switch gives Ngen.exe guidance on which dependencies would be loaded at run time.</span></span>|
|<span data-ttu-id="aab82-187">`/AppBase:` `directoryPath`</span><span class="sxs-lookup"><span data-stu-id="aab82-187">`/AppBase:` `directoryPath`</span></span>|<span data-ttu-id="aab82-188">종속성을 찾을 때 지정된 디렉터리를 애플리케이션 기본 디렉터리로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-188">When locating dependencies, use the specified directory as the application base.</span></span>|

<a name="OptionTable"></a>

## <a name="options"></a><span data-ttu-id="aab82-189">옵션</span><span class="sxs-lookup"><span data-stu-id="aab82-189">Options</span></span>

|<span data-ttu-id="aab82-190">옵션</span><span class="sxs-lookup"><span data-stu-id="aab82-190">Option</span></span>|<span data-ttu-id="aab82-191">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-191">Description</span></span>|
|------------|-----------------|
|`/nologo`|<span data-ttu-id="aab82-192">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-192">Suppress the Microsoft startup banner display.</span></span>|
|`/silent`|<span data-ttu-id="aab82-193">성공 메시지를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-193">Suppress the display of success messages.</span></span>|
|`/verbose`|<span data-ttu-id="aab82-194">디버깅에 대한 자세한 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-194">Display detailed information for debugging.</span></span> <span data-ttu-id="aab82-195">**참고:**  운영 체제 제한으로 인해 이 옵션은 Windows 98 및 Windows Millennium Edition에 대한 추가 정보를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-195">**Note:**  Due to operating system limitations, this option does not display as much additional information on Windows 98 and Windows Millennium Edition.</span></span>|
|<span data-ttu-id="aab82-196">`/help`, `/?`</span><span class="sxs-lookup"><span data-stu-id="aab82-196">`/help`, `/?`</span></span>|<span data-ttu-id="aab82-197">현재 릴리스의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-197">Display command syntax and options for the current release.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aab82-198">설명</span><span class="sxs-lookup"><span data-stu-id="aab82-198">Remarks</span></span>

<span data-ttu-id="aab82-199">Ngen.exe를 실행하려면 관리자 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-199">To run Ngen.exe, you must have administrative privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="aab82-200">완전히 신뢰할 수 없는 어셈블리에서 Ngen.exe를 실행하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-200">Do not run Ngen.exe on assemblies that are not fully trusted.</span></span> <span data-ttu-id="aab82-201">.NET Framework 4부터는 Ngen.exe가 완전 신뢰로 어셈블리를 컴파일하고 CAS(코드 액세스 보안) 정책이 더 이상 평가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-201">Starting with the .NET Framework 4, Ngen.exe compiles assemblies with full trust, and code access security (CAS) policy is no longer evaluated.</span></span>

<span data-ttu-id="aab82-202">.NET Framework 4부터는 Ngen.exe로 생성되는 네이티브 이미지는 부분 신뢰로 실행되는 애플리케이션에 더 이상 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-202">Starting with the .NET Framework 4, the native images that are generated with Ngen.exe can no longer be loaded into applications that are running in partial trust.</span></span> <span data-ttu-id="aab82-203">대신, JIT(Just-In-Time) 컴파일러가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-203">Instead, the just-in-time (JIT) compiler is invoked.</span></span>

<span data-ttu-id="aab82-204">Ngen.exe는 `install` 동작 및 해당하는 모든 종속성에 대한 `assemblyname` 인수로 지정된 네이티브 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-204">Ngen.exe generates native images for the assembly specified by the `assemblyname` argument to the `install` action and all its dependencies.</span></span> <span data-ttu-id="aab82-205">어셈블리 매니페스트의 참조로 종속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-205">Dependencies are determined from references in the assembly manifest.</span></span> <span data-ttu-id="aab82-206">종속성을 별도로 설치해야 하는 경우는 애플리케이션에서 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 호출하는 것과 같은 방법으로 리플렉션을 사용하여 종속성을 로드하는 경우밖에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-206">The only scenario in which you need to install a dependency separately is when the application loads it using reflection, for example by calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aab82-207">네이티브 이미지에 <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-207">Do not use the <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> method with native images.</span></span> <span data-ttu-id="aab82-208">이 메서드로 로드된 이미지는 실행 컨텍스트의 다른 어셈블리에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-208">An image loaded with this method cannot be used by other assemblies in the execution context.</span></span>

<span data-ttu-id="aab82-209">Ngen.exe에서는 종속성 개수가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-209">Ngen.exe maintains a count on dependencies.</span></span> <span data-ttu-id="aab82-210">예를 들어 네이티브 이미지 캐시에 `MyAssembly.exe` 및 `YourAssembly.exe`가 모두 설치되어 있고 이 두 가지 모두에 `OurDependency.dll`에 대한 참조가 있는 경우,</span><span class="sxs-lookup"><span data-stu-id="aab82-210">For example, suppose `MyAssembly.exe` and `YourAssembly.exe` are both installed in the native image cache, and both have references to `OurDependency.dll`.</span></span> <span data-ttu-id="aab82-211">`MyAssembly.exe`를 제거해도 `OurDependency.dll`은 제거되지 않고</span><span class="sxs-lookup"><span data-stu-id="aab82-211">If `MyAssembly.exe` is uninstalled, `OurDependency.dll` is not uninstalled.</span></span> <span data-ttu-id="aab82-212">`YourAssembly.exe`도 제거할 때만 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-212">It is only removed when `YourAssembly.exe` is also uninstalled.</span></span>

<span data-ttu-id="aab82-213">전역 어셈블리 캐시에 어셈블리에 대한 네이티브 이미지를 생성 중인 경우 해당 표시 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-213">If you are generating a native image for an assembly in the global assembly cache, specify its display name.</span></span> <span data-ttu-id="aab82-214"><xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-214">See <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="aab82-215">Ngen.exe에서 생성되는 네이티브 이미지는 애플리케이션 도메인 간에 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-215">The native images that Ngen.exe generates can be shared across application domains.</span></span> <span data-ttu-id="aab82-216">즉, 애플리케이션 도메인 간에 어셈블리를 공유해야 하는 애플리케이션 시나리오에서는 Ngen.exe를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-216">This means you can use Ngen.exe in application scenarios that require assemblies to be shared across application domains.</span></span> <span data-ttu-id="aab82-217">도메인 중립성을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="aab82-217">To specify domain neutrality:</span></span>

- <span data-ttu-id="aab82-218"><xref:System.LoaderOptimizationAttribute> 특성을 애플리케이션에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-218">Apply the <xref:System.LoaderOptimizationAttribute> attribute to your application.</span></span>

- <span data-ttu-id="aab82-219">새 애플리케이션 도메인에 대한 설치 정보를 만드는 경우 <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-219">Set the <xref:System.AppDomainSetup.LoaderOptimization%2A?displayProperty=nameWithType> property when you create setup information for a new application domain.</span></span>

<span data-ttu-id="aab82-220">같은 어셈블리를 여러 애플리케이션 도메인으로 로드할 때 항상 도메인 중립 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-220">Always use domain-neutral code when loading the same assembly into multiple application domains.</span></span> <span data-ttu-id="aab82-221">네이티브 이미지가 공유 도메인으로 로드된 후 비공유 애플리케이션 도메인으로 로드되면 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-221">If a native image is loaded into a nonshared application domain after having been loaded into a shared domain, it cannot be used.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-222">도메인 중립 코드는 특히 정적 멤버에 액세스할 때 언로드할 수 없으며 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-222">Domain-neutral code cannot be unloaded, and performance may be slightly slower, particularly when accessing static members.</span></span>

<span data-ttu-id="aab82-223">설명 섹션 내용:</span><span class="sxs-lookup"><span data-stu-id="aab82-223">In this Remarks section:</span></span>

- [<span data-ttu-id="aab82-224">다른 시나리오에 대한 이미지 생성</span><span class="sxs-lookup"><span data-stu-id="aab82-224">Generating images for different scenarios</span></span>](#Scenarios)

- [<span data-ttu-id="aab82-225">네이티브 이미지 사용 시기 결정</span><span class="sxs-lookup"><span data-stu-id="aab82-225">Determining when to Use native images</span></span>](#WhenToUse)

  - [<span data-ttu-id="aab82-226">향상된 메모리 사용</span><span class="sxs-lookup"><span data-stu-id="aab82-226">Improved memory use</span></span>](#Memory)

  - [<span data-ttu-id="aab82-227">빠른 애플리케이션 시작</span><span class="sxs-lookup"><span data-stu-id="aab82-227">Faster application startup</span></span>](#Startup)

  - [<span data-ttu-id="aab82-228">사용 고려 사항 요약</span><span class="sxs-lookup"><span data-stu-id="aab82-228">Summary of usage considerations</span></span>](#UsageSummary)

- [<span data-ttu-id="aab82-229">어셈블리 기준 주소의 중요성</span><span class="sxs-lookup"><span data-stu-id="aab82-229">Importance of assembly base addresses</span></span>](#BaseAddresses)

- [<span data-ttu-id="aab82-230">하드 바인딩</span><span class="sxs-lookup"><span data-stu-id="aab82-230">Hard binding</span></span>](#HardBinding)

  - [<span data-ttu-id="aab82-231">종속성에 대한 바인딩 힌트 지정</span><span class="sxs-lookup"><span data-stu-id="aab82-231">Specifying a binding hint for a dependency</span></span>](#DependencyHint)

  - [<span data-ttu-id="aab82-232">어셈블리에 대한 기본 바인딩 힌트 지정</span><span class="sxs-lookup"><span data-stu-id="aab82-232">Specifying a default binding hint for an assembly</span></span>](#AssemblyHint)

- [<span data-ttu-id="aab82-233">처리 지연</span><span class="sxs-lookup"><span data-stu-id="aab82-233">Deferred processing</span></span>](#Deferred)

- [<span data-ttu-id="aab82-234">네이티브 이미지 및 JIT 컴파일</span><span class="sxs-lookup"><span data-stu-id="aab82-234">Native images and JIT compilation</span></span>](#JITCompilation)

  - [<span data-ttu-id="aab82-235">잘못된 이미지</span><span class="sxs-lookup"><span data-stu-id="aab82-235">Invalid images</span></span>](#InvalidImages)

- [<span data-ttu-id="aab82-236">문제 해결</span><span class="sxs-lookup"><span data-stu-id="aab82-236">Troubleshooting</span></span>](#Troubleshooting)

  - [<span data-ttu-id="aab82-237">어셈블리 바인딩 로그 뷰어</span><span class="sxs-lookup"><span data-stu-id="aab82-237">Assembly Binding Log Viewer</span></span>](#Fusion)

  - [<span data-ttu-id="aab82-238">JITCompilationStart 관리 디버깅 도우미</span><span class="sxs-lookup"><span data-stu-id="aab82-238">The JITCompilationStart managed debugging assistant</span></span>](#MDA)

  - [<span data-ttu-id="aab82-239">네이티브 이미지 생성 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="aab82-239">Opting out of native image generation</span></span>](#OptOut)

<a name="Scenarios"></a>

## <a name="generating-images-for-----different-scenarios"></a><span data-ttu-id="aab82-240">다른 시나리오에 대한 이미지 생성</span><span class="sxs-lookup"><span data-stu-id="aab82-240">Generating images for     different scenarios</span></span>

<span data-ttu-id="aab82-241">어셈블리의 네이티브 이미지를 생성하면 런타임에서 해당 어셈블리를 실행할 때마다 자동으로 이 네이티브 이미지를 찾아 사용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-241">After you have generated a native image for an assembly, the runtime automatically attempts to locate and use this native   image each time it runs the assembly.</span></span> <span data-ttu-id="aab82-242">사용 시나리오에 따라 여러 이미지를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-242">Multiple images can be generated, depending on usage scenarios.</span></span>

<span data-ttu-id="aab82-243">예를 들어, 디버깅 또는 프로파일링 시나리오에서 어셈블리를 실행하는 경우 런타임은 `/Debug` 및 `/Profile` 옵션을 사용하여 생성한 네이티브 이미지를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-243">For example, if you run an assembly in a debugging or profiling scenario, the runtime looks for a native image that was generated with the `/Debug` or `/Profile` options.</span></span> <span data-ttu-id="aab82-244">일치하는 네이티브 이미지를 찾을 수 없는 경우 런타임은 표준 JIT 컴파일로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-244">If it is unable to find a matching native image, the runtime reverts to standard JIT compilation.</span></span> <span data-ttu-id="aab82-245">네이티브 이미지를 디버깅하는 유일한 방법은 `/Debug` 옵션으로 네이티브 이미지를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-245">The only way to debug native images is to create a native image with the `/Debug` option.</span></span>

<span data-ttu-id="aab82-246">`uninstall` 작업은 시나리오도 인식하므로 시나리오를 모두 제거하거나 선택한 시나리오만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-246">The `uninstall` action also recognize scenarios, so you can uninstall all scenarios or only selected scenarios.</span></span>

<a name="WhenToUse"></a>

## <a name="determining-when-to-use-native-images"></a><span data-ttu-id="aab82-247">네이티브 이미지 사용 시기 결정</span><span class="sxs-lookup"><span data-stu-id="aab82-247">Determining when to Use native images</span></span>

<span data-ttu-id="aab82-248">네이티브 이미지는 향상된 메모리 사용과 시작 시간의 단축으로 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-248">Native images can provide performance improvements in two areas: improved memory use and reduced startup time.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-249">네이티브 이미지의 성능은 코드 및 데이터 액세스 패턴, 모듈 경계에서의 호출 수, 다른 애플리케이션에서 이미 로드한 종속성 수와 같이 분석을 어렵게 하는 여러 가지 요소에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-249">Performance of native images depends on a number of factors that make analysis difficult, such as code and data access patterns, how many calls are made across module boundaries, and how many dependencies have already been loaded by other applications.</span></span> <span data-ttu-id="aab82-250">네이티브 이미지가 애플리케이션에 이점을 제공하는지 여부를 확인하는 유일한 방법은 키 배포 시나리오에서 성능을 측정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-250">The only way to determine whether native images benefit your application is by careful performance measurements in your key deployment scenarios.</span></span>

<a name="Memory"></a>

### <a name="improved-memory-use"></a><span data-ttu-id="aab82-251">향상된 메모리 사용</span><span class="sxs-lookup"><span data-stu-id="aab82-251">Improved memory use</span></span>

<span data-ttu-id="aab82-252">네이티브 이미지는 코드가 프로세스 간에 공유되는 경우 메모리 사용을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-252">Native images can significantly improve memory use when code is shared between processes.</span></span> <span data-ttu-id="aab82-253">네이티브 이미지는 Windows PE 파일이므로 .dll 파일의 단일 복사본은 여러 프로세스에서 공유할 수 있지만 JIT 컴파일러가 생성한 네이티브 이미지는 개인 메모리에 저장되며 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-253">Native images are Windows PE files, so a single copy of a .dll file can be shared by multiple processes; by contrast, native code produced by the JIT compiler is stored in private memory and cannot be shared.</span></span>

<span data-ttu-id="aab82-254">터미널 서비스에서 실행된 애플리케이션은 공유 코드 페이지를 활용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-254">Applications that are run under terminal services can also benefit from shared code pages.</span></span>

<span data-ttu-id="aab82-255">또한 JIT 컴파일러를 로드하지 않으면 각 애플리케이션 인스턴스의 고정 메모리 양을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-255">In addition, not loading the JIT compiler saves a fixed amount of memory for each application instance.</span></span>

<a name="Startup"></a>

### <a name="faster-application-startup"></a><span data-ttu-id="aab82-256">빠른 애플리케이션 시작</span><span class="sxs-lookup"><span data-stu-id="aab82-256">Faster application startup</span></span>

<span data-ttu-id="aab82-257">Ngen.exe로 어셈블리를 미리 컴파일하면 일부 애플리케이션의 시작 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-257">Precompiling assemblies with Ngen.exe can improve the startup time for some applications.</span></span> <span data-ttu-id="aab82-258">일반적으로 애플리케이션을 처음 시작한 후에 공유 구성 요소가 다음 애플리케이션을 위해 이미 로드되므로 애플리케이션이 구성 요소 어셈블리를 공유할 때 이러한 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-258">In general, gains can be made when applications share component assemblies because after the first application has been started the shared components are already loaded for subsequent applications.</span></span> <span data-ttu-id="aab82-259">애플리케이션의 모든 어셈블리를 하드 디스크에서 로드해야 하는 콜드 시작은 하드 디스크 액세스 시간이 우선하므로 네이티브 이미지에서 만큼의 이점은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-259">Cold startup, in which all the assemblies in an application must be loaded from the hard disk, does not benefit as much from native images because the hard disk access time predominates.</span></span>

<span data-ttu-id="aab82-260">하드 바인딩은 주 애플리케이션 어셈블리에 하드 바인딩된 모든 이미지를 동시에 로드해야 하므로 시작 시간에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-260">Hard binding can affect startup time, because all images that are hard bound to the main application assembly must be loaded at the same time.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-261">.NET Framework 3.5 서비스 팩 1 이전에는 로더가 전역 어셈블리 캐시에 없는 강력한 이름의 어셈블리에 대해 추가 유효성 검사를 수행하여 시작 시간에 네이티브 이미지를 통해 얻은 향상된 기능을 모두 제거하기 때문에 전역 어셈블리 캐시에 강력한 이름의 공유 구성 요소를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-261">Before the .NET Framework 3.5 Service Pack 1, you should put shared, strong-named components in the global assembly cache, because the loader performs extra validation on strong-named assemblies that are not in the global assembly cache, effectively eliminating any improvement in startup time gained by using native images.</span></span> <span data-ttu-id="aab82-262">.NET Framework 3.5 SP1에서 도입된 최적화로 인해 추가 유효성 검사가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-262">Optimizations that were introduced in the .NET Framework 3.5 SP1 removed the extra validation.</span></span>

<a name="UsageSummary"></a>

### <a name="summary-of-usage-considerations"></a><span data-ttu-id="aab82-263">사용 고려 사항 요약</span><span class="sxs-lookup"><span data-stu-id="aab82-263">Summary of usage considerations</span></span>

<span data-ttu-id="aab82-264">다음과 같은 일반적인 고려 사항 및 애플리케이션 고려 사항은 애플리케이션에 대한 네이티브 이미지 평가 활동을 수행할지 여부를 결정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-264">The following general considerations and application considerations may assist you in deciding whether to undertake the effort of evaluating native images for your application:</span></span>

- <span data-ttu-id="aab82-265">네이티브 이미지를 로드할 때는 JIT 컴파일 및 형식 안전 확인과 같은 여러 가지 시작 동작이 필요하지 않으므로 MSIL보다 로드 속도가 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-265">Native images load faster than MSIL because they eliminate the need for many startup activities, such as JIT compilation and type-safety verification.</span></span>

- <span data-ttu-id="aab82-266">JIT 컴파일러가 필요 없기 때문에 네이티브 이미지에 필요한 초기 작업 집합의 크기가 작습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-266">Native images require a smaller initial working set because there is no need for the JIT compiler.</span></span>

- <span data-ttu-id="aab82-267">네이티브 이미지를 사용하면 프로세스 간에 코드를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-267">Native images enable code sharing between processes.</span></span>

- <span data-ttu-id="aab82-268">네이티브 이미지에는 MSIL 어셈블리보다 하드 디스크 공간이 더 많이 필요하며 생성 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-268">Native images require more hard disk space than MSIL assemblies and may require considerable time to generate.</span></span>

- <span data-ttu-id="aab82-269">네이티브 이미지를 유지 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-269">Native images must be maintained.</span></span>

  - <span data-ttu-id="aab82-270">원본 어셈블리나 해당 종속성 중 하나가 서비스되는 경우 이미지를 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-270">Images need to be regenerated when the original assembly or one of its dependencies is serviced.</span></span>

  - <span data-ttu-id="aab82-271">한 어셈블리를 여러 애플리케이션이나 여러 가지 시나리오에서 사용하려면 네이티브 이미지가 여러 개 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-271">A single assembly may need multiple native images for use in different applications or different scenarios.</span></span> <span data-ttu-id="aab82-272">예를 들어, 두 애플리케이션에 구성 정보가 있으면 동일한 종속 어셈블리에 대해 여러 가지 바인딩 결정이 내려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-272">For example, the configuration information in two applications might result in different binding decisions for the same dependent assembly.</span></span>

  - <span data-ttu-id="aab82-273">네이티브 이미지는 관리자가 생성해야 합니다. 즉, Administrators 그룹의 Windows 계정을 사용하여 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-273">Native images must be generated by an administrator; that is, from a Windows account in the Administrators group.</span></span>

<span data-ttu-id="aab82-274">네이티브 이미지가 성능 이점을 제공하는지 여부를 결정할 때는 이러한 일반적인 고려 사항 외에 애플리케이션의 특성을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-274">In addition to these general considerations, the nature of your application must be considered when determining whether native images might provide a performance benefit:</span></span>

- <span data-ttu-id="aab82-275">애플리케이션이 여러 공유 구성 요소를 사용하는 환경에서 실행되면 네이티브 이미지를 사용하여 여러 프로세스에서 구성 요소를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-275">If your application runs in an environment that uses many shared components, native images allow the components to be shared by multiple processes.</span></span>

- <span data-ttu-id="aab82-276">애플리케이션이 여러 애플리케이션 도메인을 사용하는 경우 네이티브 이미지를 사용하여 도메인 간에 코드 페이지를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-276">If your application uses multiple application domains, native images allow code pages to be shared across domains.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aab82-277">.NET Framework 버전 1.0 및 1.1에서는 애플리케이션 도메인 간에 네이티브 이미지를 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-277">In the .NET Framework versions 1.0 and 1.1, native images cannot be shared across application domains.</span></span> <span data-ttu-id="aab82-278">버전 2.0 이상에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-278">This is not the case in version 2.0 or later.</span></span>

- <span data-ttu-id="aab82-279">애플리케이션이 터미널 서버에서 실행되면 네이티브 이미지를 사용하여 코드 페이지를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-279">If your application will be run under Terminal Server, native images allow sharing of code pages.</span></span>

- <span data-ttu-id="aab82-280">일반적으로 규모가 큰 애플리케이션은 네이티브 이미지로 컴파일하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-280">Large applications generally benefit from compilation to native images.</span></span> <span data-ttu-id="aab82-281">일반적으로 규모가 작은 애플리케이션에는 유용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-281">Small applications generally do not benefit.</span></span>

- <span data-ttu-id="aab82-282">장기 실행 애플리케이션의 경우 런타임 JIT 컴파일이 네이티브 이미지보다 성능이 약간 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-282">For long-running applications, run-time JIT compilation performs slightly better than native images.</span></span> <span data-ttu-id="aab82-283">하드 바인딩을 사용하면 이러한 성능 차이를 어느 정도 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-283">(Hard binding can mitigate this performance difference to some degree.)</span></span>

<a name="BaseAddresses"></a>

## <a name="importance-of-assembly-base-addresses"></a><span data-ttu-id="aab82-284">어셈블리 기준 주소의 중요성</span><span class="sxs-lookup"><span data-stu-id="aab82-284">Importance of assembly base addresses</span></span>

<span data-ttu-id="aab82-285">네이티브 이미지는 Windows PE 파일이므로 다른 실행 파일과 마찬가지로 동일한 기준 재지정 문제의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-285">Because native images are Windows PE files, they are subject to the same rebasing issues as other executable files.</span></span> <span data-ttu-id="aab82-286">재배치를 위한 성능 비용은 하드 바인딩이 사용된 경우 훨씬 더 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-286">The performance cost of relocation is even more pronounced if hard binding is employed.</span></span>

<span data-ttu-id="aab82-287">네이티브 이미지에 대한 기준 주소를 설정하려면 컴파일러의 해당 옵션을 사용하여 어셈블리에 대한 기준 주소를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-287">To set the base address for a native image, use the appropriate option of your compiler to set the base address for the assembly.</span></span> <span data-ttu-id="aab82-288">Ngen.exe는 네이티브 이미지에 이러한 기준 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-288">Ngen.exe uses this base address for the native image.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-289">네이티브 이미지는 이미지를 만든 관리되는 어셈블리보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-289">Native images are larger than the managed assemblies from which they were created.</span></span> <span data-ttu-id="aab82-290">이러한 큰 크기를 허용할 수 있게 기준 주소를 계산해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-290">Base addresses must be calculated to allow for these larger sizes.</span></span>

<span data-ttu-id="aab82-291">dumpbin.exe와 같은 도구를 사용하여 네이티브 이미지의 기본 기준 주소를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-291">You can use a tool such as dumpbin.exe to view the preferred base address of a native image.</span></span>

<a name="HardBinding"></a>

## <a name="hard-binding"></a><span data-ttu-id="aab82-292">하드 바인딩</span><span class="sxs-lookup"><span data-stu-id="aab82-292">Hard binding</span></span>

<span data-ttu-id="aab82-293">하드 바인딩은 처리량을 늘리고 네이티브 이미지의 작업 집합 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-293">Hard binding increases throughput and reduces working set size for native images.</span></span> <span data-ttu-id="aab82-294">하드 바인딩은 어셈블리에 하드 바인딩된 이미지를 어셈블리가 로드될 때 모두 로드해야 한다는 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-294">The disadvantage of hard binding is that all the images that are hard bound to an assembly must be loaded when the assembly is loaded.</span></span> <span data-ttu-id="aab82-295">이렇게 하면 규모가 큰 애플리케이션을 시작하는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-295">This can significantly increase startup time for a large application.</span></span>

<span data-ttu-id="aab82-296">하드 바인딩은 애플리케이션의 성능이 중요한 모든 시나리오에 있어서 로드된 종속성에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-296">Hard binding is appropriate for dependencies that are loaded in all your application's performance-critical scenarios.</span></span> <span data-ttu-id="aab82-297">네이티브 이미지 사용 시와 마찬가지로 하드 바인딩이 애플리케이션의 성능을 향상시키는지 여부를 확인하는 유일한 방법은 성능을 신중하게 측정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-297">As with any aspect of native image use, careful performance measurements are the only way to determine whether hard binding improves your application's performance.</span></span>

<span data-ttu-id="aab82-298"><xref:System.Runtime.CompilerServices.DependencyAttribute> 및 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 특성을 사용하여 Ngen.exe에 하드 바인딩 힌트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-298">The <xref:System.Runtime.CompilerServices.DependencyAttribute> and <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> attributes allow you to provide hard binding hints to Ngen.exe.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-299">이러한 특성은 명령이 아니라 Ngen.exe에 대한 힌트입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-299">These attributes are hints to Ngen.exe, not commands.</span></span> <span data-ttu-id="aab82-300">이러한 특성을 사용한다고 해서 하드 바인딩이 보장되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-300">Using them does not guarantee hard binding.</span></span> <span data-ttu-id="aab82-301">이러한 특성의 의미는 다음 릴리스에서 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-301">The meaning of these attributes may change in future releases.</span></span>

<a name="DependencyHint"></a>

### <a name="specifying-a-binding-hint-for-a-dependency"></a><span data-ttu-id="aab82-302">종속성에 대한 바인딩 힌트 지정</span><span class="sxs-lookup"><span data-stu-id="aab82-302">Specifying a binding hint for a dependency</span></span>

<span data-ttu-id="aab82-303"><xref:System.Runtime.CompilerServices.DependencyAttribute>를 어셈블리에 적용하여 지정된 종속성이 로드될 가능성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-303">Apply the <xref:System.Runtime.CompilerServices.DependencyAttribute> to an assembly to indicate the likelihood that a specified dependency will be loaded.</span></span> <span data-ttu-id="aab82-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType>는 하드 바인딩이 적합함을, <xref:System.Runtime.CompilerServices.LoadHint.Default>는 종속성에 대한 기본값을 사용해야 함을, <xref:System.Runtime.CompilerServices.LoadHint.Sometimes>는 하드 바인딩이 적합하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-304"><xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> indicates that hard binding is appropriate, <xref:System.Runtime.CompilerServices.LoadHint.Default> indicates that the default for the dependency should be used, and <xref:System.Runtime.CompilerServices.LoadHint.Sometimes> indicates that hard binding is not appropriate.</span></span>

<span data-ttu-id="aab82-305">아래 코드에서는 두 개의 종속성이 있는 어셈블리에 대한 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-305">The following code shows the attributes for an assembly that has two dependencies.</span></span> <span data-ttu-id="aab82-306">첫 번째 종속성(Assembly1)은 하드 바인딩에 적합한 후보이며 두 번째 종속성(Assembly2)은 적합하지 않은 후보입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-306">The first dependency (Assembly1) is an appropriate candidate for hard binding, and the second (Assembly2) is not.</span></span>

```vb
Imports System.Runtime.CompilerServices
<Assembly:DependencyAttribute("Assembly1", LoadHint.Always)>
<Assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)>
```

```csharp
using System.Runtime.CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)]
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)]
```

```cpp
using namespace System::Runtime::CompilerServices;
[assembly:DependencyAttribute("Assembly1", LoadHint.Always)];
[assembly:DependencyAttribute("Assembly2", LoadHint.Sometimes)];
```

<span data-ttu-id="aab82-307">어셈블리 이름에는 파일 이름 확장명이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-307">The assembly name does not include the file name extension.</span></span> <span data-ttu-id="aab82-308">표시 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-308">Display names can be used.</span></span>

<a name="AssemblyHint"></a>

### <a name="specifying-a-default-binding-hint-for-an-assembly"></a><span data-ttu-id="aab82-309">어셈블리에 대한 기본 바인딩 힌트 지정</span><span class="sxs-lookup"><span data-stu-id="aab82-309">Specifying a default binding hint for an assembly</span></span>

<span data-ttu-id="aab82-310">기본 바인딩 힌트는 어셈블리에 대한 종속성이 있는 애플리케이션이 즉시 자주 사용하는 어셈블리에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-310">Default binding hints are only needed for assemblies that will be used immediately and frequently by any application that has a dependency on them.</span></span> <span data-ttu-id="aab82-311">하드 바인딩을 사용하도록 지정할 이러한 어셈블리에 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute>를 사용하여 <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType>를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-311">Apply the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> with <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> to such assemblies to specify that hard binding should be used.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-312"><xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> 이외의 값이 있는 특성을 적용하면 특성을 전혀 적용하지 않았을 때와 효과가 동일하므로 이 범주에 속하지 않는 .dll 어셈블리에 <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType>를 적용할 이유는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-312">There is no reason to apply <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to .dll assemblies that do not fall into this category, because applying the attribute with any value other than <xref:System.Runtime.CompilerServices.LoadHint.Always?displayProperty=nameWithType> has the same effect as not applying the attribute at all.</span></span>

<span data-ttu-id="aab82-313">Microsoft는 <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute>를 사용하여 하드 바인딩이 mscorlib.dll과 같은 .NET Framework의 소수 어셈블리에 대한 기본값이 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-313">Microsoft uses the <xref:System.Runtime.CompilerServices.DefaultDependencyAttribute> to specify that hard binding is the default for a very small number of assemblies in the .NET Framework, such as mscorlib.dll.</span></span>

<a name="Deferred"></a>

## <a name="deferred-processing"></a><span data-ttu-id="aab82-314">처리 지연</span><span class="sxs-lookup"><span data-stu-id="aab82-314">Deferred processing</span></span>

<span data-ttu-id="aab82-315">규모가 큰 애플리케이션의 네이티브 이미지를 생성하는 데 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-315">Generation of native images for a very large application can take considerable time.</span></span> <span data-ttu-id="aab82-316">마찬가지로 공유 구성 요소를 변경하거나 컴파일러 설정을 변경하려면 업데이트할 네이티브 이미지가 여러 개 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-316">Similarly, changes to a shared component or changes to computer settings might require many native images to be updated.</span></span> <span data-ttu-id="aab82-317">`install` 및 `update` 작업에는 네이티브 이미지 서비스가 지연된 실행에 대한 작업을 큐에 대기시키는 `/queue`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-317">The `install` and `update` actions have a `/queue` option that queues the operation for deferred execution by the native image service.</span></span> <span data-ttu-id="aab82-318">또한 Ngen.exe에는 서비스를 일부 제어하는 `queue` 및 `executeQueuedItems` 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-318">In addition, Ngen.exe has `queue` and `executeQueuedItems` actions that provide some control over the service.</span></span> <span data-ttu-id="aab82-319">자세한 내용은 [네이티브 이미지 서비스](#native-image-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-319">For more information, see [Native Image Service](#native-image-service).</span></span>

<a name="JITCompilation"></a>

## <a name="native-images-and-jit-compilation"></a><span data-ttu-id="aab82-320">네이티브 이미지 및 JIT 컴파일</span><span class="sxs-lookup"><span data-stu-id="aab82-320">Native images and JIT compilation</span></span>

<span data-ttu-id="aab82-321">Ngen.exe는 어셈블리에서 생성할 수 없는 메서드를 발견하면 네이티브 이미지에서 이 메서드를 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-321">If Ngen.exe encounters any methods in an assembly that it cannot generate, it excludes them from the native image.</span></span> <span data-ttu-id="aab82-322">런타임에서 이 어셈블리를 실행할 때 네이티브 이미지에 포함되지 않은 메서드에 대한 JIT 컴파일로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-322">When the runtime executes this assembly, it reverts to JIT compilation for the methods that were not included in the native image.</span></span>

<span data-ttu-id="aab82-323">또한 어셈블리가 업그레이드되지 않았거나 이미지가 어떤 이유로 무효화된 경우 네이티브 이미지가 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-323">In addition, native images are not used if the assembly has been upgraded, or if the image has been invalidated for any reason.</span></span>

<a name="InvalidImages"></a>

### <a name="invalid-images"></a><span data-ttu-id="aab82-324">잘못된 이미지</span><span class="sxs-lookup"><span data-stu-id="aab82-324">Invalid images</span></span>

<span data-ttu-id="aab82-325">Ngen.exe를 사용하여 어셈블리의 네이티브 이미지를 만드는 경우 출력은 사용자가 지정한 명령줄 옵션 및 컴퓨터의 특정 설정에 따라 달라지는데</span><span class="sxs-lookup"><span data-stu-id="aab82-325">When you use Ngen.exe to create a native image of an assembly, the output depends upon the command-line options that you specify and certain settings on your computer.</span></span> <span data-ttu-id="aab82-326">이 설정에는 다음 사항이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-326">These settings include the following:</span></span>

- <span data-ttu-id="aab82-327">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="aab82-327">The version of the .NET Framework.</span></span>

- <span data-ttu-id="aab82-328">Windows 9x 제품군에서 Windows NT 제품군으로 변경되는 경우의 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="aab82-328">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

- <span data-ttu-id="aab82-329">어셈블리의 정확한 ID(다시 컴파일하면 ID가 변경됨)</span><span class="sxs-lookup"><span data-stu-id="aab82-329">The exact identity of the assembly (recompilation changes identity).</span></span>

- <span data-ttu-id="aab82-330">어셈블리에서 참조하는 모든 어셈블리의 정확한 ID(다시 컴파일하면 ID가 변경됨)</span><span class="sxs-lookup"><span data-stu-id="aab82-330">The exact identity of all assemblies that the assembly references (recompilation changes identity).</span></span>

- <span data-ttu-id="aab82-331">보안 요소</span><span class="sxs-lookup"><span data-stu-id="aab82-331">Security factors.</span></span>

<span data-ttu-id="aab82-332">Ngen.exe는 네이티브 이미지를 생성할 때 이 정보를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-332">Ngen.exe records this information when it generates a native image.</span></span> <span data-ttu-id="aab82-333">어셈블리를 실행하는 경우 런타임은 컴퓨터의 현재 환경과 일치하는 옵션 및 설정을 사용하여 생성된 네이티브 이미지를 찾고</span><span class="sxs-lookup"><span data-stu-id="aab82-333">When you execute an assembly, the runtime looks for the native image generated with options and settings that match the computer's current environment.</span></span> <span data-ttu-id="aab82-334">일치하는 네이티브 이미지를 찾지 못하는 경우 어셈블리의 JIT 컴파일로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-334">The runtime reverts to JIT compilation of an assembly if it cannot find a matching native image.</span></span> <span data-ttu-id="aab82-335">다음과 같이 컴퓨터 설정과 환경을 변경하면 네이티브 이미지를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-335">The following changes to a computer's settings and environment cause native images to become invalid:</span></span>

- <span data-ttu-id="aab82-336">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="aab82-336">The version of the .NET Framework.</span></span>

     <span data-ttu-id="aab82-337">.NET Framework에 업데이트를 적용하면 Ngen.exe를 사용하여 만든 네이티브 이미지를 모두 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-337">If you apply an update to the .NET Framework, all native images that you have created using Ngen.exe become invalid.</span></span> <span data-ttu-id="aab82-338">따라서 .NET Framework의 모든 업데이트는 `Ngen Update` 명령을 실행하여 네이티브 이미지가 모두 다시 생성되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-338">For this reason, all updates of the .NET Framework execute the `Ngen Update` command, to ensure that all native images are regenerated.</span></span> <span data-ttu-id="aab82-339">.NET Framework는 설치한 .NET Framework 라이브러리에 대한 새로운 네이티브 이미지를 자동으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-339">The .NET Framework automatically creates new native images for the .NET Framework libraries that it installs.</span></span>

- <span data-ttu-id="aab82-340">Windows 9x 제품군에서 Windows NT 제품군으로 변경되는 경우의 운영 체제 버전</span><span class="sxs-lookup"><span data-stu-id="aab82-340">The version of the operating system, if the change is from the Windows 9x family to the Windows NT family.</span></span>

     <span data-ttu-id="aab82-341">예를 들어 컴퓨터에서 실행되는 운영 체제 버전이 Windows 98에서 Windows XP로 변경되면 네이티브 이미지 캐시에 저장된 모든 네이티브 이미지를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-341">For example, if the version of the operating system running on a computer changes from Windows 98 to Windows XP, all native images stored in the native image cache become invalid.</span></span> <span data-ttu-id="aab82-342">그러나 운영 체제가 Windows 2000에서 Windows XP로 변경되는 경우에는 해당 이미지를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-342">However, if the operating system changes from Windows 2000 to Windows XP, the images are not invalidated.</span></span>

- <span data-ttu-id="aab82-343">어셈블리의 정확한 ID</span><span class="sxs-lookup"><span data-stu-id="aab82-343">The exact identity of the assembly.</span></span>

     <span data-ttu-id="aab82-344">어셈블리를 다시 컴파일하면 어셈블리의 해당 네이티브 이미지를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-344">If you recompile an assembly, the assembly's corresponding native image becomes invalid.</span></span>

- <span data-ttu-id="aab82-345">어셈블리에서 참조하는 모든 어셈블리의 정확한 ID</span><span class="sxs-lookup"><span data-stu-id="aab82-345">The exact identity of any assemblies the assembly references.</span></span>

     <span data-ttu-id="aab82-346">관리되는 어셈블리를 업데이트하면 해당 어셈블리에 직접 또는 간접적으로 종속된 네이티브 이미지가 모두 사용할 수 없게 되므로 다시 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-346">If you update a managed assembly, all native images that directly or indirectly depend on that assembly become invalid and need to be regenerated.</span></span> <span data-ttu-id="aab82-347">여기에는 일반 참조와 하드 바인딩된 종속성이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-347">This includes both ordinary references and hard-bound dependencies.</span></span> <span data-ttu-id="aab82-348">소프트웨어 업데이트가 적용될 때마다 설치 프로그램에서 `Ngen Update` 명령을 실행하여 종속된 네이티브 이미지가 모두 다시 생성되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-348">Whenever a software update is applied, the installation program should execute an `Ngen Update` command to ensure that all dependent native images are regenerated.</span></span>

- <span data-ttu-id="aab82-349">보안 요소</span><span class="sxs-lookup"><span data-stu-id="aab82-349">Security factors.</span></span>

     <span data-ttu-id="aab82-350">어셈블리에 이전에 부여되었던 사용 권한을 제한하도록 컴퓨터 보안 정책을 변경하면 이전에 컴파일한 해당 어셈블리의 네이티브 이미지를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-350">Changing machine security policy to restrict permissions previously granted to an assembly can cause a previously compiled native image for that assembly to become invalid.</span></span>

     <span data-ttu-id="aab82-351">공용 언어 런타임에서 코드 액세스 보안을 관리하는 방법과 권한을 사용하는 방법에 대한 자세한 내용은 [코드 액세스 보안](../misc/code-access-security.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-351">For detailed information about how the common language runtime administers code access security and how to use permissions, see [Code Access Security](../misc/code-access-security.md).</span></span>

<a name="Troubleshooting"></a>

## <a name="troubleshooting"></a><span data-ttu-id="aab82-352">문제 해결</span><span class="sxs-lookup"><span data-stu-id="aab82-352">Troubleshooting</span></span>

<span data-ttu-id="aab82-353">다음 문제 해결 항목을 통해 어떤 네이티브 이미지가 사용되고 있는지, 애플리케이션에서 사용할 수 없는지, JIT 컴파일러에서 메서드를 컴파일하는 시기를 결정할 수 있는지, 그리고 지정된 메서드의 네이티브 이미지 컴파일을 옵트아웃하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-353">The following troubleshooting topics allow you to see which native images are being used and which cannot be used by your application, to determine when the JIT compiler starts to compile a method, and shows how to opt out of native image compilation of specified methods.</span></span>

<a name="Fusion"></a>

### <a name="assembly-binding-log-viewer"></a><span data-ttu-id="aab82-354">어셈블리 바인딩 로그 뷰어</span><span class="sxs-lookup"><span data-stu-id="aab82-354">Assembly Binding Log Viewer</span></span>

<span data-ttu-id="aab82-355">애플리케이션에서 네이티브 이미지를 사용하고 있는지 확인하려면 [Fuslogvw.exe(어셈블리 바인딩 로그 뷰어)](fuslogvw-exe-assembly-binding-log-viewer.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-355">To confirm that native images are being used by your application, you can use the [Fuslogvw.exe (Assembly Binding Log Viewer)](fuslogvw-exe-assembly-binding-log-viewer.md).</span></span> <span data-ttu-id="aab82-356">바인딩 로그 뷰어 창의 **로그 범주** 상자에서 **네이티브 이미지**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-356">Select **Native Images** in the **Log Categories** box on the binding log viewer window.</span></span> <span data-ttu-id="aab82-357">Fuslogvw.exe는 네이티브 이미지를 거부하는 이유에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-357">Fuslogvw.exe provides information about why a native image was rejected.</span></span>

<a name="MDA"></a>

### <a name="the-jitcompilationstart-managed-debugging-assistant"></a><span data-ttu-id="aab82-358">JITCompilationStart 관리 디버깅 도우미</span><span class="sxs-lookup"><span data-stu-id="aab82-358">The JITCompilationStart managed debugging assistant</span></span>

<span data-ttu-id="aab82-359">[jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) MDA(관리 디버깅 도우미)를 사용하여 JIT 컴파일러에서 함수 컴파일을 시작하는 시기를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-359">You can use the [jitCompilationStart](../debug-trace-profile/jitcompilationstart-mda.md) managed debugging assistant (MDA) to determine when the JIT compiler starts to compile a function.</span></span>

<a name="OptOut"></a>

### <a name="opting-out-of-native-image-generation"></a><span data-ttu-id="aab82-360">네이티브 이미지 생성 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="aab82-360">Opting out of native image generation</span></span>

<span data-ttu-id="aab82-361">경우에 따라 NGen.exe에서 특정 메서드에 대한 네이티브 이미지를 생성하는 데 문제가 있을 수 있거나, 해당 메서드를 네이티브 이미지로 컴파일하지 않고 JIT 컴파일하려고 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-361">In some cases, NGen.exe may have difficulty generating a native image for a specific method, or you may prefer that the method be JIT compiled rather then compiled to a native image.</span></span> <span data-ttu-id="aab82-362">이 경우 `System.Runtime.BypassNGenAttribute` 특성을 사용하여 NGen.exe에서 특정 메서드에 대한 기본 이미지를 생성하지 못하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-362">In this case, you can use the `System.Runtime.BypassNGenAttribute` attribute to prevent NGen.exe from generating a native image for a particular method.</span></span> <span data-ttu-id="aab82-363">이 특성은 코드에서 네이티브 이미지에 포함하지 않으려는 각 메서드에 개별적으로 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-363">The attribute must be applied individually to each method whose code you do not want to include in the native image.</span></span> <span data-ttu-id="aab82-364">NGen.exe는 특성을 인식하고 해당 메서드의 네이티브 이미지에 코드를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-364">NGen.exe recognizes the attribute and does not generate code in the native image for the corresponding method.</span></span>

<span data-ttu-id="aab82-365">그러나 `BypassNGenAttribute`는 .NET Framework 클래스 라이브러리의 형식으로 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-365">Note, however, that `BypassNGenAttribute` is not defined as a type in the .NET Framework Class Library.</span></span> <span data-ttu-id="aab82-366">코드에서 이 특성을 사용하려면 먼저 다음과 같이 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-366">In order to consume the attribute in your code, you must first define it as follows:</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#1)]
[!code-vb[System.Runtime.BypassNGenAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#1)]

<span data-ttu-id="aab82-367">그런 다음 메서드별로 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-367">You can then apply the attribute on a per-method basis.</span></span> <span data-ttu-id="aab82-368">다음 예제에서는 네이티브 이미지 생성기에 `ExampleClass.ToJITCompile` 메서드에 대한 네이티브 이미지를 생성하지 말아야 한다고 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-368">The following example instructs the Native Image Generator that it should not generate a native image for the `ExampleClass.ToJITCompile` method.</span></span>

[!code-csharp[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/cs/Optout1.cs#2)]
[!code-vb[System.Runtime.BypassNGenAttribute#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/System.Runtime.BypassNGenAttribute/vb/Optout1.vb#2)]

## <a name="examples"></a><span data-ttu-id="aab82-369">예</span><span class="sxs-lookup"><span data-stu-id="aab82-369">Examples</span></span>

<span data-ttu-id="aab82-370">다음 명령은 현재 디렉터리에 있는 `ClientApp.exe`에 대한 네이티브 이미지를 생성하고 그 이미지를 네이티브 이미지 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-370">The following command generates a native image for `ClientApp.exe`, located in the current directory, and installs the image in the native image cache.</span></span> <span data-ttu-id="aab82-371">어셈블리에 대해 구성 파일이 존재하는 경우 Ngen.exe는 해당 파일을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-371">If a configuration file exists for the assembly, Ngen.exe uses it.</span></span> <span data-ttu-id="aab82-372">또한 `ClientApp.exe`에서 참조하는 모든 .dll 파일에 대한 네이티브 이미지가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-372">In addition, native images are generated for any .dll files that `ClientApp.exe` references.</span></span>

```console
ngen install ClientApp.exe
```

<span data-ttu-id="aab82-373">Ngen.exe로 설치된 이미지를 루트라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-373">An image installed with Ngen.exe is also called a root.</span></span> <span data-ttu-id="aab82-374">루트는 애플리케이션 또는 공유 구성 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-374">A root can be an application or a shared component.</span></span>

<span data-ttu-id="aab82-375">다음 명령은 지정된 경로를 사용하여 `MyAssembly.exe`의 네이티브 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-375">The following command generates a native image for `MyAssembly.exe` with the specified path.</span></span>

```console
ngen install c:\myfiles\MyAssembly.exe
```

<span data-ttu-id="aab82-376">어셈블리 및 해당 종속성을 찾을 때 Ngen.exe는 공용 언어 런타임에서 사용한 검색 논리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-376">When locating assemblies and their dependencies, Ngen.exe uses the same probing logic used by the common language runtime.</span></span> <span data-ttu-id="aab82-377">기본적으로 `ClientApp.exe`가 포함된 디렉터리는 애플리케이션 기본 디렉터리로 사용되며 모든 어셈블리 검색은 이 디렉터리에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-377">By default, the directory that contains `ClientApp.exe` is used as the application base directory, and all assembly probing begins in this directory.</span></span> <span data-ttu-id="aab82-378">`/AppBase` 옵션을 사용하여 이 동작을 재지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-378">You can override this behavior by using the `/AppBase` option.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-379">이것은 애플리케이션 기준이 현재 디렉터리로 설정된 .NET Framework 버전 1.0 및 1.1의 Ngen.exe 동작이 바뀐 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-379">This is a change from Ngen.exe behavior in the .NET Framework versions 1.0 and 1.1, where the application base is set to the current directory.</span></span>

<span data-ttu-id="aab82-380">예를 들어, 어셈블리에서 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 사용하여 .dll 파일을 로드하면 종속성이 참조 없이 어셈블리에 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-380">An assembly can have a dependency without a reference, for example if it loads a .dll file by using the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="aab82-381">`/ExeConfig` 옵션을 사용하는 경우 애플리케이션 어셈블리에 대한 구성 정보를 사용하여 그러한 .dll 파일의 네이티브 이미지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-381">You can create a native image for such a .dll file by using configuration information for the application assembly, with the `/ExeConfig` option.</span></span> <span data-ttu-id="aab82-382">다음 명령은 `MyLib.dll,`에서 구성 정보를 사용하여 `MyApp.exe`의 네이티브 이미지를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-382">The following command generates a native image for `MyLib.dll,` using the configuration information from `MyApp.exe`.</span></span>

```console
ngen install c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="aab82-383">이런 식으로 설치한 어셈블리는 애플리케이션을 제거해도 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-383">Assemblies installed in this way are not removed when the application is removed.</span></span>

<span data-ttu-id="aab82-384">종속성을 제거하려면 해당 어셈블리를 설치할 때 사용한 것과 동일한 명령줄 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-384">To uninstall a dependency, use the same command-line options that were used to install it.</span></span> <span data-ttu-id="aab82-385">다음 명령은 이전 예제에서 `MyLib.dll`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-385">The following command uninstalls the `MyLib.dll` from the previous example.</span></span>

```console
ngen uninstall c:\myfiles\MyLib.dll /ExeConfig:c:\myapps\MyApp.exe
```

<span data-ttu-id="aab82-386">전역 어셈블리 캐시에 어셈블리에 대한 네이티브 이미지를 만들려면 어셈블리의 표시 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-386">To create a native image for an assembly in the global assembly cache, use the display name of the assembly.</span></span> <span data-ttu-id="aab82-387">예:</span><span class="sxs-lookup"><span data-stu-id="aab82-387">For example:</span></span>

```console
ngen install "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
```

<span data-ttu-id="aab82-388">NGen.exe는 설치하는 각 시나리오마다 별도의 이미지 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-388">NGen.exe generates a separate set of images for each scenario you install.</span></span> <span data-ttu-id="aab82-389">예를 들어, 다음 명령은 일반적인 작업을 위한 네이티브 이미지의 전체 집합, 디버깅을 위한 또 다른 전체 집합 및 프로파일링을 위한 집합을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-389">For example, the following commands install a complete set of native images for normal operation, another complete set for debugging, and a third for profiling:</span></span>

```console
ngen install MyApp.exe
ngen install MyApp.exe /debug
ngen install MyApp.exe /profile
```

### <a name="displaying-the-native-image-cache"></a><span data-ttu-id="aab82-390">네이티브 이미지 캐시 표시</span><span class="sxs-lookup"><span data-stu-id="aab82-390">Displaying the Native Image Cache</span></span>

<span data-ttu-id="aab82-391">네이티브 이미지가 캐시에 설치된 후에는 Ngen.exe를 사용하여 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-391">Once native images are installed in the cache, they can be displayed using Ngen.exe.</span></span> <span data-ttu-id="aab82-392">다음 명령은 네이티브 이미지 캐시에서 모든 네이티브 이미지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-392">The following command displays all native images in the native image cache.</span></span>

```console
ngen display
```

<span data-ttu-id="aab82-393">`display` 작업은 먼저 루트 어셈블리를 모두 나열한 다음 모든 네이티브 이미지 목록을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-393">The `display` action lists all the root assemblies first, followed by a list of all the native images on the computer.</span></span>

<span data-ttu-id="aab82-394">어셈블리의 단순한 이름을 사용하여 해당 어셈블리에 대한 정보만 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-394">Use the simple name of an assembly to display information only for that assembly.</span></span> <span data-ttu-id="aab82-395">다음 명령은 부분 이름 `MyAssembly`에 일치하는 네이티브 이미지 캐시의 모든 네이티브 이미지, 해당 종속성, `MyAssembly`에서 종속성을 갖는 모든 루트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-395">The following command displays all native images in the native image cache that match the partial name `MyAssembly`, their dependencies, and all roots that have a dependency on `MyAssembly`:</span></span>

```console
ngen display MyAssembly
```

<span data-ttu-id="aab82-396">공유 구성 요소 어셈블리에 의존하는 루트를 알고 있는 것이 공유 구성 요소가 업그레이드된 후 `update` 작업의 영향을 측정하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-396">Knowing what roots depend on a shared component assembly is useful in gauging the impact of an `update` action after the shared component is upgraded.</span></span>

<span data-ttu-id="aab82-397">어셈블리의 파일 확장명을 지정하는 경우 어셈블리가 포함된 디렉터리에서 경로를 지정하거나 Ngen.exe를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-397">If you specify an assembly's file extension, you must either specify the path or execute Ngen.exe from the directory containing the assembly:</span></span>

```console
ngen display c:\myApps\MyAssembly.exe
```

<span data-ttu-id="aab82-398">다음 명령은 이름이 `MyAssembly`이고 버전이 1.0.0.0인 네이티브 이미지 캐시의 네이티브 이미지를 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-398">The following command displays all native images in the native image cache with the name `MyAssembly` and the version 1.0.0.0.</span></span>

```console
ngen display "myAssembly, version=1.0.0.0"
```

### <a name="updating-images"></a><span data-ttu-id="aab82-399">이미지 업데이트</span><span class="sxs-lookup"><span data-stu-id="aab82-399">Updating Images</span></span>

<span data-ttu-id="aab82-400">이미지는 일반적으로 공유 구성 요소가 업그레이드된 후에 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-400">Images are typically updated after a shared component has been upgraded.</span></span> <span data-ttu-id="aab82-401">변경되었거나 종속성이 변경된 네이티브 이미지를 모두 업데이트하려면 인수 없이 `update` 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-401">To update all native images that have changed, or whose dependencies have changed, use the `update` action with no arguments.</span></span>

```console
ngen update
```

<span data-ttu-id="aab82-402">모든 이미지를 업데이트하려면 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-402">Updating all images can be a lengthy process.</span></span> <span data-ttu-id="aab82-403">`/queue` 옵션을 사용하여 네이티브 이미지 서비스에서 실행할 업데이트를 큐에 대기시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-403">You can queue the updates for execution by the native image service by using the `/queue` option.</span></span> <span data-ttu-id="aab82-404">`/queue` 옵션 및 설치 우선 순위에 대한 자세한 내용은 [네이티브 이미지 서비스](#native-image-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-404">For more information on the `/queue` option and installation priorities, see [Native Image Service](#native-image-service).</span></span>

```console
ngen update /queue
```

### <a name="uninstalling-images"></a><span data-ttu-id="aab82-405">이미지 제거</span><span class="sxs-lookup"><span data-stu-id="aab82-405">Uninstalling Images</span></span>

<span data-ttu-id="aab82-406">Ngen.exe가 종속성 목록을 유지 관리하므로 공유 구성 요소는 공유 구성 요소에 의존하는 모든 어셈블리가 제거된 경우에만 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-406">Ngen.exe maintains a list of dependencies, so that shared components are removed only when all assemblies that depend on them have been removed.</span></span> <span data-ttu-id="aab82-407">또한 공유 구성 요소는 루트로 설치된 경우 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-407">In addition, a shared component is not removed if it has been installed as a root.</span></span>

<span data-ttu-id="aab82-408">다음 명령은 루트 `ClientApp.exe`에 대한 시나리오를 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-408">The following command uninstalls all scenarios for the root `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp
```

<span data-ttu-id="aab82-409">`uninstall` 작업은 특정 시나리오를 제거할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-409">The `uninstall` action can be used to remove specific scenarios.</span></span> <span data-ttu-id="aab82-410">다음 명령은 `ClientApp.exe`에 대한 모든 디버그 시나리오를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-410">The following command uninstalls all debug scenarios for `ClientApp.exe`:</span></span>

```console
ngen uninstall ClientApp /debug
```

> [!NOTE]
> <span data-ttu-id="aab82-411">`/debug` 시나리오를 제거해도 `/profile`과 `/debug.`가 모두 포함된 시나리오는 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-411">Uninstalling `/debug` scenarios does not uninstall a scenario that includes both `/profile` and `/debug.`</span></span>

<span data-ttu-id="aab82-412">다음 명령은 `ClientApp.exe`의 특정 버전에 대한 시나리오를 모두 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-412">The following command uninstalls all scenarios for a specific version of `ClientApp.exe`:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0"
```

<span data-ttu-id="aab82-413">다음 명령은 `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",`에 대한 모든 시나리오 또는 해당 어셈블리에 대한 디버그 시나리오만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-413">The following commands uninstall all scenarios for `"ClientApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL",` or just the debug scenario for that assembly:</span></span>

```console
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL"
ngen uninstall "ClientApp, Version=1.0.0.0, Culture=neutral,
  PublicKeyToken=3c7ba247adcd2081, processorArchitecture=MSIL" /debug
```

<span data-ttu-id="aab82-414">`install` 작업과 마찬가지로 확장명을 제공하려면 어셈블리가 포함된 디렉터리에서 Ngen.exe를 실행하거나 전체 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-414">As with the `install` action, supplying an extension requires either executing Ngen.exe from the directory containing the assembly or specifying a full path.</span></span>

<span data-ttu-id="aab82-415">네이티브 이미지 서비스와 관련된 예제는 [네이티브 이미지 서비스](#native-image-service)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aab82-415">For examples relating to the native image service, see [Native Image Service](#native-image-service).</span></span>

## <a name="native-image-task"></a><span data-ttu-id="aab82-416">네이티브 이미지 작업</span><span class="sxs-lookup"><span data-stu-id="aab82-416">Native Image Task</span></span>

<span data-ttu-id="aab82-417">네이티브 이미지 작업은 네이티브 이미지를 생성 및 유지 관리하는 Windows 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-417">The native image task is a Windows task that generates and maintains native images.</span></span> <span data-ttu-id="aab82-418">네이티브 이미지 작업은 지원되는 시나리오에 대해 자동으로 네이티브 이미지를 생성 및 회수합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-418">The native image task generates and reclaims native images automatically for supported scenarios.</span></span> <span data-ttu-id="aab82-419">또한 설치 관리자가 [Ngen.exe(네이티브 이미지 생성기)](ngen-exe-native-image-generator.md)를 사용하여 지연된 시간에 네이티브 이미지를 만들고 업데이트할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-419">It also enables installers to use [Ngen.exe (Native Image Generator)](ngen-exe-native-image-generator.md) to create and update native images at a deferred time.</span></span>

<span data-ttu-id="aab82-420">네이티브 이미지 작업은 각 아키텍처를 대상으로 하는 애플리케이션에 대한 컴파일을 허용하기 위해 컴퓨터에서 지원되는 각 CPU 아키텍처에 대해 한 번 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-420">The native image task is registered once for each CPU architecture supported on a computer, to allow compilation for applications that target each architecture:</span></span>

|<span data-ttu-id="aab82-421">작업 이름</span><span class="sxs-lookup"><span data-stu-id="aab82-421">Task name</span></span>|<span data-ttu-id="aab82-422">32비트 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="aab82-422">32-bit computer</span></span>|<span data-ttu-id="aab82-423">64비트 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="aab82-423">64-bit computer</span></span>|
|---------------|----------------------|----------------------|
|<span data-ttu-id="aab82-424">NET Framework NGEN v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="aab82-424">NET Framework NGEN v4.0.30319</span></span>|<span data-ttu-id="aab82-425">예</span><span class="sxs-lookup"><span data-stu-id="aab82-425">Yes</span></span>|<span data-ttu-id="aab82-426">예</span><span class="sxs-lookup"><span data-stu-id="aab82-426">Yes</span></span>|
|<span data-ttu-id="aab82-427">NET Framework NGEN v4.0.30319 64</span><span class="sxs-lookup"><span data-stu-id="aab82-427">NET Framework NGEN v4.0.30319 64</span></span>|<span data-ttu-id="aab82-428">아니요</span><span class="sxs-lookup"><span data-stu-id="aab82-428">No</span></span>|<span data-ttu-id="aab82-429">예</span><span class="sxs-lookup"><span data-stu-id="aab82-429">Yes</span></span>|

<span data-ttu-id="aab82-430">Windows 8 이상에서 실행되는 경우 네이티브 이미지 작업은 .NET Framework 4.5 이상 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-430">The native image task is available in the .NET Framework 4.5 and later versions, when running on Windows 8 or later.</span></span> <span data-ttu-id="aab82-431">이전 버전의 Windows에서는 .NET Framework에서 [네이티브 이미지 서비스](#native-image-service)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-431">On earlier versions of Windows, the .NET Framework uses the [Native Image Service](#native-image-service).</span></span>

### <a name="task-lifetime"></a><span data-ttu-id="aab82-432">작업 수명</span><span class="sxs-lookup"><span data-stu-id="aab82-432">Task Lifetime</span></span>

<span data-ttu-id="aab82-433">일반적으로 Windows 작업 스케줄러는 매일 밤 컴퓨터가 유휴 상태일 때 네이티브 이미지 작업을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-433">In general, the Windows Task Scheduler starts the native image task every night when the computer is idle.</span></span> <span data-ttu-id="aab82-434">작업은 애플리케이션 설치 관리자가 큐에 대기한 지연된 작업, 지연된 네이티브 이미지 업데이트 요청 및 자동 이미지 생성을 모두 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-434">The task checks for any deferred work that is queued by application installers, any deferred native image update requests, and any automatic image creation.</span></span> <span data-ttu-id="aab82-435">작업은 처리 중인 작업 항목을 완료하고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-435">The task completes outstanding work items and then shuts down.</span></span> <span data-ttu-id="aab82-436">작업이 실행되는 동안 컴퓨터 유휴 상태가 중지되면 작업이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-436">If the computer stops being idle while the task is running, the task stops.</span></span>

<span data-ttu-id="aab82-437">작업 스케줄러 UI를 통해 수동으로 또는 NGen.exe 수동 호출을 통해 네이티브 이미지 작업을 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-437">You can also start the native image task manually through the Task Scheduler UI or through manual calls to NGen.exe.</span></span> <span data-ttu-id="aab82-438">이러한 방법 중 하나로 작업이 시작된 경우 컴퓨터가 더이상 유휴 상태가 아닐 때에도 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-438">If the task is started through either of these methods, it will continue running when the computer is no longer idle.</span></span> <span data-ttu-id="aab82-439">NGen.exe를 사용하여 수동으로 만든 이미지는 애플리케이션 설치 관리자에 대해 예측 가능한 동작을 사용할 수 있도록 우선 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-439">Images created manually by using NGen.exe are prioritized to enable predictable behavior for application installers.</span></span>

## <a name="native-image-service"></a><span data-ttu-id="aab82-440">네이티브 이미지 서비스</span><span class="sxs-lookup"><span data-stu-id="aab82-440">Native Image Service</span></span>

<span data-ttu-id="aab82-441">네이티브 이미지 서비스는 네이티브 이미지를 생성 및 유지 관리하는 Windows 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-441">The native image service is a Windows service that generates and maintains native images.</span></span> <span data-ttu-id="aab82-442">네이티브 이미지 서비스를 통해 개발자는 네이티브 이미지의 설치 및 업데이트를 컴퓨터가 유휴 상태인 기간으로 지연시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-442">The native image service allows the developer to defer the installation and update of native images to periods when the computer is idle.</span></span>

<span data-ttu-id="aab82-443">일반적으로 네이티브 이미지 서비스는 애플리케이션 또는 업데이트 설치 프로그램(설치 관리자)에 의해 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-443">Normally, the native image service is initiated by the installation program (installer) for an application or update.</span></span> <span data-ttu-id="aab82-444">우선 순위 3 작업의 경우 서비스가 컴퓨터의 유휴 시간 중에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-444">For priority 3 actions, the service executes during idle time on the computer.</span></span> <span data-ttu-id="aab82-445">서비스는 상태를 저장하고, 필요한 경우 여러 번 다시 부팅되어도 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-445">The service saves its state and is capable of continuing through multiple reboots if necessary.</span></span> <span data-ttu-id="aab82-446">여러 개의 이미지 컴파일을 큐에 대기시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-446">Multiple image compilations can be queued.</span></span>

<span data-ttu-id="aab82-447">또한 서비스는 수동 Ngen.exe 명령과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-447">The service also interacts with the manual Ngen.exe command.</span></span> <span data-ttu-id="aab82-448">수동 명령이 백그라운드 작업보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-448">Manual commands take precedence over background activity.</span></span>

> [!NOTE]
> <span data-ttu-id="aab82-449">Windows Vista에서 네이티브 이미지 서비스에 대해 표시되는 이름은 "Microsoft.NET Framework NGEN v2.0.50727_X86" 또는 "Microsoft.NET Framework NGEN v2.0.50727_X64"입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-449">On Windows Vista, the name displayed for the native image service is "Microsoft.NET Framework NGEN v2.0.50727_X86" or "Microsoft.NET Framework NGEN v2.0.50727_X64".</span></span> <span data-ttu-id="aab82-450">Microsoft Windows의 모든 이전 버전에서는 이름이 ".NET Runtime Optimization Service v2.0.50727_X86" 또는 ".NET Runtime Optimization Service v2.0.50727_X64"입니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-450">On all earlier versions of Microsoft Windows, the name is ".NET Runtime Optimization Service v2.0.50727_X86" or ".NET Runtime Optimization Service v2.0.50727_X64".</span></span>

### <a name="launching-deferred-operations"></a><span data-ttu-id="aab82-451">지연된 작업 시작</span><span class="sxs-lookup"><span data-stu-id="aab82-451">Launching Deferred Operations</span></span>

<span data-ttu-id="aab82-452">설치 또는 업그레이드를 시작하기 전에 서비스를 일시 중지하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-452">Before beginning an installation or upgrade, pausing the service is recommended.</span></span> <span data-ttu-id="aab82-453">이렇게 하면 설치 관리자가 파일을 복사하거나 어셈블리를 전역 어셈블리 캐시에 저장하는 동안 서비스가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-453">This ensures that the service does not execute while the installer is copying files or putting assemblies in the global assembly cache.</span></span> <span data-ttu-id="aab82-454">다음 Ngen.exe 명령줄은 서비스를 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-454">The following Ngen.exe command line pauses the service:</span></span>

```console
ngen queue pause
```

<span data-ttu-id="aab82-455">지연된 모든 작업이 큐에 대기되고 나면 다음 명령을 통해 서비스를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-455">When all deferred operations have been queued, the following command allows the service to resume:</span></span>

```console
ngen queue continue
```

<span data-ttu-id="aab82-456">새 애플리케이션을 설치하거나 공유 구성 요소를 업데이트할 때 네이티브 이미지 생성을 지연시키려면 `install` 또는 `update` 작업과 함께 `/queue` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-456">To defer native image generation when installing a new application or when updating a shared component, use the `/queue` option with the `install` or `update` actions.</span></span> <span data-ttu-id="aab82-457">다음 Ngen.exe 명령줄은 공유 구성 요소에 대한 네이티브 이미지를 설치하고 영향을 받았을 수 있는 모든 루트의 업데이트를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-457">The following Ngen.exe command lines install a native image for a shared component and perform an update of all roots that may have been affected:</span></span>

```console
ngen install MyComponent /queue
ngen update /queue
```

<span data-ttu-id="aab82-458">`update` 작업은 `MyComponent`를 사용하는 이미지뿐 아니라 무효화된 모든 네이티브 이미지를 재생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-458">The `update` action regenerates all native images that have been invalidated, not just those that use `MyComponent`.</span></span>

<span data-ttu-id="aab82-459">애플리케이션이 많은 루트로 구성된 경우 지연된 작업의 우선 순위를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-459">If your application consists of many roots, you can control the priority of the deferred actions.</span></span> <span data-ttu-id="aab82-460">다음 명령은 세 가지 루트의 설치를 큐에 대기시킵니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-460">The following commands queue the installation of three roots.</span></span> <span data-ttu-id="aab82-461">`Assembly1`은 유휴 시간을 기다리지 않고 첫 번째로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-461">`Assembly1` is installed first, without waiting for idle time.</span></span> <span data-ttu-id="aab82-462">`Assembly2`도 유휴 시간을 기다리지 않고 설치되지만 모든 우선 순위 1 작업이 완료된 후에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-462">`Assembly2` is also installed without waiting for idle time, but after all priority 1 actions have completed.</span></span> <span data-ttu-id="aab82-463">`Assembly3`은 서비스에서 컴퓨터의 유휴 상태를 감지할 때 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-463">`Assembly3` is installed when the service detects that the computer is idle.</span></span>

```console
ngen install Assembly1 /queue:1
ngen install Assembly2 /queue:2
ngen install Assembly3 /queue:3
```

<span data-ttu-id="aab82-464">`executeQueuedItems` 작업을 사용하여 큐에 대기 중인 작업이 동기적으로 발생하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-464">You can force queued actions to occur synchronously by using the `executeQueuedItems` action.</span></span> <span data-ttu-id="aab82-465">선택적 우선 순위를 제공하는 경우 이 작업은 우선 순위가 같거나 낮은 대기 중인 작업에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-465">If you supply the optional priority, this action affects only the queued actions that have equal or lower priority.</span></span> <span data-ttu-id="aab82-466">기본 우선 순위는 3이므로 다음 Ngen.exe 명령은 큐에 대기 중인 모든 작업을 즉시 처리하고 완료될 때까지 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-466">The default priority is 3, so the following Ngen.exe command processes all queued actions immediately, and does not return until they are finished:</span></span>

```console
ngen executeQueuedItems
```

<span data-ttu-id="aab82-467">동기 명령은 Ngen.exe에 의해 실행되며 네이티브 이미지 서비스를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-467">Synchronous commands are executed by Ngen.exe and do not use the native image service.</span></span> <span data-ttu-id="aab82-468">네이티브 이미지 서비스가 실행되는 동안 Ngen.exe를 사용하여 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-468">You can execute actions using Ngen.exe while the native image service is running.</span></span>

### <a name="service-shutdown"></a><span data-ttu-id="aab82-469">서비스 종료</span><span class="sxs-lookup"><span data-stu-id="aab82-469">Service Shutdown</span></span>

<span data-ttu-id="aab82-470">`/queue` 옵션을 포함하는 Ngen.exe 명령을 실행하여 시작된 후 서비스는 모든 작업이 완료 될 때까지 백그라운드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-470">After being initiated by the execution of an Ngen.exe command that includes the `/queue` option, the service runs in the background until all actions have been completed.</span></span> <span data-ttu-id="aab82-471">서비스는 필요한 경우 여러 번 다시 부팅되어도 계속할 수 있도록 상태를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-471">The service saves its state so that it can continue through multiple reboots if necessary.</span></span> <span data-ttu-id="aab82-472">서비스에서 큐에 대기 중인 작업이 더 이상 없음을 감지하면 다음에 컴퓨터가 부팅될 때 다시 시작되지 않도록 상태를 다시 설정하고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-472">When the service detects that there are no more actions queued, it resets its status so that it will not restart the next time the computer is booted, and then it shuts itself down.</span></span>

### <a name="service-interaction-with-clients"></a><span data-ttu-id="aab82-473">클라이언트와 서비스의 상호 작용</span><span class="sxs-lookup"><span data-stu-id="aab82-473">Service Interaction with Clients</span></span>

<span data-ttu-id="aab82-474">.NET Framework 버전 2.0에서 네이티브 이미지 서비스와의 유일한 상호 작용은 명령줄 도구 Ngen.exe를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-474">In the .NET Framework version 2.0, the only interaction with the native image service is through the command-line tool Ngen.exe.</span></span> <span data-ttu-id="aab82-475">설치 스크립트의 명령줄 도구를 사용하여 네이티브 이미지 서비스에 대한 작업을 큐에 대기시키고 서비스와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aab82-475">Use the command-line tool in installation scripts to queue actions for the native image service and to interact with the service.</span></span>

## <a name="see-also"></a><span data-ttu-id="aab82-476">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aab82-476">See also</span></span>

- [<span data-ttu-id="aab82-477">도구</span><span class="sxs-lookup"><span data-stu-id="aab82-477">Tools</span></span>](index.md)
- [<span data-ttu-id="aab82-478">관리되는 실행 프로세스</span><span class="sxs-lookup"><span data-stu-id="aab82-478">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="aab82-479">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="aab82-479">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="aab82-480">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="aab82-480">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
