---
title: .NET Core RID(런타임 식별자) 카탈로그
description: RID(런타임 식별자) 및 .NET Core에서 RID의 사용 방법에 관해 알아봅니다.
ms.date: 02/22/2019
ms.openlocfilehash: 4369e263f1f46c73f04c65e4124f63c68d133520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789902"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="b77f3-103">.NET Core RID 카탈로그</span><span class="sxs-lookup"><span data-stu-id="b77f3-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="b77f3-104">RID는 *Runtime IDentifier(런타임 식별자)* 의 약어입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="b77f3-105">RID 값은 애플리케이션을 실행하는 대상 플랫폼을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="b77f3-106">NuGet 패키지에서 .NET 패키지의 플랫폼 관련 자산을 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="b77f3-107">RID 값의 예로 `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, `osx.10.12-x64` 등을 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="b77f3-108">기본 종속성이 있는 패키지의 경우 RID는 패키지를 복원할 수 있는 플랫폼을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="b77f3-109">단일 RID는 프로젝트 파일의 `<RuntimeIdentifier>` 요소에 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="b77f3-110">여러 RID는 프로젝트 파일의 `<RuntimeIdentifiers>` 요소에서 세미콜론으로 구분된 목록으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="b77f3-111">다음과 같은 [.NET Core CLI 명령](./tools/index.md)을 사용하여 `--runtime` 옵션을 통해서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="b77f3-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="b77f3-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="b77f3-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="b77f3-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="b77f3-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="b77f3-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="b77f3-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="b77f3-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="b77f3-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="b77f3-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="b77f3-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="b77f3-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="b77f3-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="b77f3-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="b77f3-119">구체적인 운영 체제를 나타내는 RID는 일반적으로 `[os].[version]-[architecture]-[additional qualifiers]`의 패턴을 따릅니다. 각각은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="b77f3-120">`[os]` - 운영 체제/플랫폼 모니커입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="b77f3-121">예: `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="b77f3-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="b77f3-122">`[version]` - 점으로 구분된(`.`) 버전 번호 형식의 운영 체제 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="b77f3-123">예: `15.10`.</span><span class="sxs-lookup"><span data-stu-id="b77f3-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="b77f3-124">버전은 마케팅 버전이어서는 **안 됩니다**. 마케팅 버전은 종종 다양한 플랫폼 API 노출 영역이 있는 운영 체제의 여러 개별 버전을 나타내기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="b77f3-125">`[architecture]` - 프로세서 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="b77f3-126">예를 들면 `x86`, `x64`, `arm`, `arm64` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="b77f3-127">`[additional qualifiers]` - 다른 플랫폼을 추가로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="b77f3-128">예를 들어 `aot`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b77f3-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="b77f3-129">RID 그래프</span><span class="sxs-lookup"><span data-stu-id="b77f3-129">RID graph</span></span>

<span data-ttu-id="b77f3-130">RID 그래프 또는 런타임 Fallback 그래프는 서로 호환되는 RID 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="b77f3-131">RID는 [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) 패키지에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="b77f3-132">지원되는 RID 및 RID 그래프 목록은 `dotnet/runtime` 리포지토리에 있는 [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the `dotnet/runtime` repository.</span></span> <span data-ttu-id="b77f3-133">이 파일에서 기본 RID를 제외하고 모든 RID에 `"#import"` 문이 포함되어 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="b77f3-134">이러한 문은 호환되는 RID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="b77f3-135">NuGet에서 패키지를 복원할 때 지정된 런타임에 대한 정확한 일치를 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="b77f3-136">정확한 일치를 찾을 수 없는 경우 NuGet은 RID 그래프에 따라 가장 가까운 호환 시스템을 찾을 때까지 그래프를 다시 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="b77f3-137">다음 예제는 `osx.10.12-x64` RID의 실제 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="b77f3-138">위의 RID는 `osx.10.12-x64`가 `osx.10.11-x64`를 가져오도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="b77f3-139">따라서 NuGet에서 패키지를 복원할 때 패키지에서 `osx.10.12-x64`와 정확히 일치하는 값을 찾으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="b77f3-140">NuGet이 특정 런타임을 찾을 수 없는 경우 예를 들어 `osx.10.11-x64` 런타임을 지정하는 패키지를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="b77f3-141">다음 예제에서는 마찬가지로 *runtime.json* 파일에 정의된 약간 더 큰 RID 그래프를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="b77f3-142">모든 RID는 결국 루트 `any` RID에 다시 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="b77f3-143">RID를 사용할 때는 RID에 대한 다음과 같은 몇 가지 고려 사항을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="b77f3-144">RID는 **불투명 문자열**이며 블랙 박스로 취급해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="b77f3-145">RID를 프로그래밍 방식으로 빌드하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="b77f3-146">플랫폼에 대해 이미 정의된 RID를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="b77f3-147">RID는 구체적이어야 하므로 실제 RID 값에서 어느 것도 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="b77f3-148">RID 사용</span><span class="sxs-lookup"><span data-stu-id="b77f3-148">Using RIDs</span></span>

<span data-ttu-id="b77f3-149">RID를 사용할 수 있으려면 어떤 RID가 있는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="b77f3-150">새 값이 플랫폼에 정기적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="b77f3-151">완전한 최신 버전을 보려면 `dotnet/runtime` 리포지토리에서 [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

<span data-ttu-id="b77f3-152">.NET Core 2.0 SDK에서는 이식 가능 RID라는 개념을 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="b77f3-153">이식 가능 RID란 RID 그래프에 새로 추가된 값으로서, 아직 특정 버전 또는 OS 배포에 연결되지 않았으며 .NET Core 2.0 이상을 사용할 때 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="b77f3-154">대부분의 배포 RID는 이식 가능 RID에 매핑되므로 이 값은 여러 Linux 배포판을 다룰 때 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="b77f3-155">다음 목록에서는 각 OS에 사용되는 일반적인 RID의 몇 가지 예를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="b77f3-156">Windows RID</span><span class="sxs-lookup"><span data-stu-id="b77f3-156">Windows RIDs</span></span>

<span data-ttu-id="b77f3-157">자주 사용되는 값만 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-157">Only common values are listed.</span></span> <span data-ttu-id="b77f3-158">완전한 최신 버전을 보려면 `dotnet/runtime` 리포지토리에서 [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="b77f3-159">이식 가능(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="b77f3-160">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b77f3-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="b77f3-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b77f3-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="b77f3-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b77f3-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="b77f3-163">자세한 내용은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?tabs=netcore30&pivots=os-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-163">For more information, see [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

## <a name="linux-rids"></a><span data-ttu-id="b77f3-164">Linux RID</span><span class="sxs-lookup"><span data-stu-id="b77f3-164">Linux RIDs</span></span>

<span data-ttu-id="b77f3-165">자주 사용되는 값만 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-165">Only common values are listed.</span></span> <span data-ttu-id="b77f3-166">완전한 최신 버전을 보려면 `dotnet/runtime` 리포지토리에서 [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span> <span data-ttu-id="b77f3-167">아래에 나열되지 않은 배포를 실행하는 디바이스의 경우, 이식 가능 RID 중 하나와 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="b77f3-168">예를 들어, 여기에 나열되지 않은 Linux 배포를 실행하는 Raspberry Pi 디바이스는 `linux-arm`을 사용하여 대상으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="b77f3-169">이식 가능(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-169">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="b77f3-170">`linux-x64`(CentOS, Debian, Fedora, Ubuntu 및 파생 버전을 비롯한 대부분의 데스크톱 배포)</span><span class="sxs-lookup"><span data-stu-id="b77f3-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu, and derivatives)</span></span>
  - <span data-ttu-id="b77f3-171">`linux-musl-x64` (Alpine Linux와 같이 [musl](https://wiki.musl-libc.org/projects-using-musl.html)을 사용하는 간단한 배포)</span><span class="sxs-lookup"><span data-stu-id="b77f3-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="b77f3-172">`linux-arm` (Raspberry Pi와 같이 ARM에서 실행되는 Linux 배포)</span><span class="sxs-lookup"><span data-stu-id="b77f3-172">`linux-arm` (Linux distributions running on ARM like Raspberry Pi)</span></span>
- <span data-ttu-id="b77f3-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="b77f3-173">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="b77f3-174">`rhel-x64` (버전 6보다 상위 RHEL의 경우 `linux-x64`로 대체됨)</span><span class="sxs-lookup"><span data-stu-id="b77f3-174">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - <span data-ttu-id="b77f3-175">`rhel.6-x64`(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="b77f3-176">Tizen(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-176">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="b77f3-177">자세한 내용은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?tabs=netcore30&pivots=os-linux)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-177">For more information, see [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux).</span></span>

## <a name="macos-rids"></a><span data-ttu-id="b77f3-178">macOS RID</span><span class="sxs-lookup"><span data-stu-id="b77f3-178">macOS RIDs</span></span>

<span data-ttu-id="b77f3-179">macOS RID는 이전 "OSX" 브랜딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="b77f3-180">자주 사용되는 값만 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b77f3-180">Only common values are listed.</span></span> <span data-ttu-id="b77f3-181">완전한 최신 버전을 보려면 `dotnet/runtime` 리포지토리에서 [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) 파일을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="b77f3-182">이식 가능(.NET Core 2.0 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-182">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="b77f3-183">`osx-x64` (최소 OS 버전: macOS 10.12 Sierra)</span><span class="sxs-lookup"><span data-stu-id="b77f3-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="b77f3-184">macOS 10.10 Yosemite</span><span class="sxs-lookup"><span data-stu-id="b77f3-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="b77f3-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="b77f3-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="b77f3-186">macOS 10.12 Sierra(.NET Core 1.1 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-186">macOS 10.12 Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="b77f3-187">macOS 10.13 High Sierra(.NET Core 1.1 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-187">macOS 10.13 High Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="b77f3-188">macOS 10.14 Mojave(.NET Core 1.1 이상 버전)</span><span class="sxs-lookup"><span data-stu-id="b77f3-188">macOS 10.14 Mojave (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.14-x64`

<span data-ttu-id="b77f3-189">자세한 내용은 [.NET Core 종속성 및 요구 사항](install/dependencies.md?tabs=netcore30&pivots=os-macos)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b77f3-189">For more information, see [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos).</span></span>

## <a name="see-also"></a><span data-ttu-id="b77f3-190">참조</span><span class="sxs-lookup"><span data-stu-id="b77f3-190">See also</span></span>

- [<span data-ttu-id="b77f3-191">런타임 ID</span><span class="sxs-lookup"><span data-stu-id="b77f3-191">Runtime IDs</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
