---
ms.openlocfilehash: 8c739d8f355ffa6a6e09cbe4c531b188acede5bd
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720307"
---
### <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="bd3d7-101">OSPlatform 특성이 제거되었거나 특성 이름이 바뀜</span><span class="sxs-lookup"><span data-stu-id="bd3d7-101">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="bd3d7-102">.NET 5.0 미리 보기 8에 도입된 `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, `ObsoletedInOSPlatformAttribute` 특성은 제거되었거나 그 이름이 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-102">The following attributes that were introduced in .NET 5.0 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="bd3d7-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="bd3d7-103">Change description</span></span>

<span data-ttu-id="bd3d7-104">.NET 5.0 미리 보기 8에서는 <xref:System.Runtime.Versioning> 네임스페이스에 다음과 같은 특성을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-104">.NET 5.0 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="bd3d7-105">.NET 5.0 미리 보기 8에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../docs/standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 `System.Runtime.Versioning.MinimumOSPlatformAttribute` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-105">In .NET 5.0 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="bd3d7-106">.NET 5.0 RC1에서는 `ObsoletedInOSPlatformAttribute`가 제거되었고 `MinimumOSPlatformAttribute` 및 `RemovedInOSPlatformAttribute`의 이름이 다음과 같이 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-106">In .NET 5.0 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="bd3d7-107">미리 보기 8 이름</span><span class="sxs-lookup"><span data-stu-id="bd3d7-107">Preview 8 name</span></span> | <span data-ttu-id="bd3d7-108">RC1 이상 이름</span><span class="sxs-lookup"><span data-stu-id="bd3d7-108">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="bd3d7-109">.NET 5.0 RC1 이상에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../docs/standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-109">In .NET 5.0 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../docs/standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="bd3d7-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="bd3d7-110">Reason for change</span></span>

<span data-ttu-id="bd3d7-111">.NET 5.0 미리 보기 8에는 API에 지원되는 플랫폼을 지정하는 특성이 <xref:System.Runtime.Versioning>에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-111">.NET 5.0 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="bd3d7-112">이 특성은 이러한 API를 지원하지 않는 플랫폼에서 플랫폼별 API가 사용되는 경우 [플랫폼 호환성 분석기](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility)에서 빌드 경고를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-112">The attributes are consumed by the [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) to produce build warnings when platform-specific APIs are consumed on platforms that don't supported those APIs.</span></span>

<span data-ttu-id="bd3d7-113">.NET 5.0 RC1의 경우 플랫폼을 제외하는 기능이 플랫폼 호환성 분석기에 더 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-113">For .NET 5.0 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="bd3d7-114">이 기능을 통해 API가 OS 플랫폼에서 완전히 지원되지 않는 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-114">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="bd3d7-115">이 기능으로 인해 더 적절한 이름을 사용하는 등 특성을 변경하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-115">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="bd3d7-116">`ObsoletedInOSPlatformAttribute`는 더 이상 필요하지 않아 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-116">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="bd3d7-117">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="bd3d7-117">Version introduced</span></span>

<span data-ttu-id="bd3d7-118">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="bd3d7-118">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="bd3d7-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="bd3d7-119">Recommended action</span></span>

<span data-ttu-id="bd3d7-120">이러한 변경으로 인해 프로젝트 대상을 .NET 5.0 미리 보기 8에서 .NET 5.0 RC1로 바꿀 때 빌드 오류나 런타임 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-120">When you retarget your project from .NET 5.0 Preview 8 to .NET 5.0 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="bd3d7-121">예를 들어 `MinimumOSPlatformAttribute`의 이름을 바꾸면 오류가 발생할 수 있습니다. 빌드 시 특성이 플랫폼별 어셈블리에 적용되지만, 이전 빌드 아티팩트가 여전히 이전 API 이름을 참조하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-121">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="bd3d7-122">빌드 시 오류 예:</span><span class="sxs-lookup"><span data-stu-id="bd3d7-122">Example build-time errors:</span></span>

- <span data-ttu-id="bd3d7-123">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘MinimumOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="bd3d7-123">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="bd3d7-124">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘RemovedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="bd3d7-124">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="bd3d7-125">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘ObsoletedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="bd3d7-125">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="bd3d7-126">런타임 오류 예:</span><span class="sxs-lookup"><span data-stu-id="bd3d7-126">Example run-time error:</span></span>

<span data-ttu-id="bd3d7-127">**처리되지 않은 예외: System.TypeLoadException: 어셈블리 ‘System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a’에서 형식 ‘System.Runtime.Versioning.MinimumOSPlatformAttribute’를 로드할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="bd3d7-127">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="bd3d7-128">이러한 오류를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-128">To resolve these errors:</span></span>

- <span data-ttu-id="bd3d7-129">`MinimumOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-129">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="bd3d7-130">`RemovedInOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-130">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="bd3d7-131">`ObsoletedInOSPlatformAttribute`에 대한 모든 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3d7-131">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="bd3d7-132">이전 빌드 아티팩트를 삭제하려면 프로젝트를 다시 빌드합니다(또는 정리 + 빌드 수행).</span><span class="sxs-lookup"><span data-stu-id="bd3d7-132">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

#### <a name="category"></a><span data-ttu-id="bd3d7-133">범주</span><span class="sxs-lookup"><span data-stu-id="bd3d7-133">Category</span></span>

<span data-ttu-id="bd3d7-134">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="bd3d7-134">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="bd3d7-135">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="bd3d7-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

#### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
