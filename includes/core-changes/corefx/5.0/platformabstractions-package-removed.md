---
ms.openlocfilehash: a635e2ed6a735b5234c92fd8f5ffa1685fe9373e
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558184"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="54919-101">Microsoft.DotNet.PlatformAbstractions 패키지 제거됨</span><span class="sxs-lookup"><span data-stu-id="54919-101">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="54919-102">[Microsoft.DotNet.PlatformAbstractions NuGet 패키지](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/)의 새 버전이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-102">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

#### <a name="change-description"></a><span data-ttu-id="54919-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="54919-103">Change description</span></span>

<span data-ttu-id="54919-104">이전에는 <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리의 새 버전이 새 버전의 .NET Core와 함께 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-104">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="54919-105">앞으로는 라이브러리에 새로운 기능이 추가되지 않으며 새로운 주 버전이 출시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-105">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="54919-106">그러나 라이브러리의 기존 버전은 계속 작동하고 서비스됩니다.</span><span class="sxs-lookup"><span data-stu-id="54919-106">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="54919-107"><xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리는 System.\* 네임스페이스에 이미 설정된 API와 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="54919-107">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="54919-108">또한 일부 <xref:Microsoft.DotNet.PlatformAbstractions> API는 조사 및 장기 지원 수준이 나머지 System.\* API와 동일하게 설계되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-108">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="54919-109">예를 들어 <xref:Microsoft.DotNet.PlatformAbstractions>는 `Platform` 열거형을 사용하여 현재 운영 체제 플랫폼을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="54919-109">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="54919-110">이 열거형 설계는 <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API를 설계할 때 새로운 플랫폼과 향후 유연성을 위해 명시적으로 거부되었습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-110">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="54919-111"><xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> 라이브러리에서 사용하도록 설정된 시나리오를 이제 이 열거형 없이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-111">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="54919-112">기존 버전은 .NET 5.0 이상에서도 계속 작동하며, 이전 버전의 .NET Core와 함께 서비스됩니다.</span><span class="sxs-lookup"><span data-stu-id="54919-112">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="54919-113">그러나 라이브러리에 새로운 기능은 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-113">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="54919-114">대신, 새로운 기능은 다른 라이브러리와 API에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="54919-114">Instead, new functionality will be added to other libraries and APIs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="54919-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="54919-115">Version introduced</span></span>

<span data-ttu-id="54919-116">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="54919-116">5.0 Preview 6</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54919-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="54919-117">Recommended action</span></span>

- <span data-ttu-id="54919-118">요구 사항에 맞는 경우 이전 버전의 라이브러리를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-118">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="54919-119">이전 버전이 요구 사항에 맞지 않으면 `PlatformAbstractions` API 사용을 권장되는 대체 항목으로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="54919-119">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="54919-120">`PlatformAbstractions` API</span><span class="sxs-lookup"><span data-stu-id="54919-120">`PlatformAbstractions` API</span></span> | <span data-ttu-id="54919-121">권장된 대체</span><span class="sxs-lookup"><span data-stu-id="54919-121">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="54919-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> 및 <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="54919-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="54919-123">`RuntimeEnvironment.OperatingSystem` 및 `RuntimeEnvironment.OperatingSystemVersion`의 사용 사례 대부분은 표시(예: 사용자, 로깅 및 원격 분석에 표시)가 그 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="54919-123">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="54919-124">OS(운영 체제) 버전에 따라 런타임 결정을 내리는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-124">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="54919-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType>에서 이제 Windows 및 macOS 운영 체제의 [올바른 버전이 반환](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version)됩니다.</span><span class="sxs-lookup"><span data-stu-id="54919-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now [returns the correct version](../../../../docs/core/compatibility/corefx.md#environmentosversion-returns-the-correct-operating-system-version) for Windows and macOS operating systems.</span></span> <span data-ttu-id="54919-126">그러나 대부분의 Unix 배포에서는 무엇을 “OS 버전”으로 간주할지가 간단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-126">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="54919-127">예를 들어 Linux 커널 버전이거나 배포판 버전이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-127">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="54919-128">대부분의 Unix 플랫폼에서 <xref:System.Environment.OSVersion?displayProperty=nameWithType> 및 <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType>는 `uname`에서 반환된 버전을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="54919-128">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="54919-129">Linux 배포판 이름 및 버전 정보를 가져오려면 */etc/os-release* 파일을 읽는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="54919-129">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

#### <a name="category"></a><span data-ttu-id="54919-130">범주</span><span class="sxs-lookup"><span data-stu-id="54919-130">Category</span></span>

<span data-ttu-id="54919-131">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="54919-131">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54919-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="54919-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
