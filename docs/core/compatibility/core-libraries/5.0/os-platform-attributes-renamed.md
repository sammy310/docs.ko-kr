---
title: '호환성이 손상되는 변경: OSPlatform 특성이 제거되었거나 특성 이름이 바뀜'
description: 미리 보기 버전에 도입된 OS 플랫폼 특성이 제거되었거나 이름이 바뀐 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 118c5360eb02c1b4d57fccbd3b2cfdeff0b9fe12
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257260"
---
# <a name="osplatform-attributes-renamed-or-removed"></a><span data-ttu-id="fc161-103">OSPlatform 특성이 제거되었거나 특성 이름이 바뀜</span><span class="sxs-lookup"><span data-stu-id="fc161-103">OSPlatform attributes renamed or removed</span></span>

<span data-ttu-id="fc161-104">.NET 5 미리 보기 8에 도입된 `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, `ObsoletedInOSPlatformAttribute` 특성은 제거되었거나 그 이름이 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-104">The following attributes that were introduced in .NET 5 Preview 8 have been removed or renamed: `MinimumOSPlatformAttribute`, `RemovedInOSPlatformAttribute`, and `ObsoletedInOSPlatformAttribute`.</span></span>

## <a name="change-description"></a><span data-ttu-id="fc161-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="fc161-105">Change description</span></span>

<span data-ttu-id="fc161-106">.NET 5 미리 보기 8에서는 <xref:System.Runtime.Versioning> 네임스페이스에 다음과 같은 특성을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-106">.NET 5 Preview 8 introduced the following attributes in the <xref:System.Runtime.Versioning> namespace:</span></span>

- `MinimumOSPlatformAttribute`
- `RemovedInOSPlatformAttribute`
- `ObsoletedInOSPlatformAttribute`

<span data-ttu-id="fc161-107">.NET 5 미리 보기 8에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 `System.Runtime.Versioning.MinimumOSPlatformAttribute` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-107">In .NET 5 Preview 8, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level `System.Runtime.Versioning.MinimumOSPlatformAttribute` attribute.</span></span>

<span data-ttu-id="fc161-108">.NET 5 RC1에서는 `ObsoletedInOSPlatformAttribute`가 제거되었고 `MinimumOSPlatformAttribute` 및 `RemovedInOSPlatformAttribute`의 이름이 다음과 같이 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-108">In .NET 5 RC1, the `ObsoletedInOSPlatformAttribute` has been removed, and `MinimumOSPlatformAttribute` and `RemovedInOSPlatformAttribute` have been renamed as follows:</span></span>

| <span data-ttu-id="fc161-109">미리 보기 8 이름</span><span class="sxs-lookup"><span data-stu-id="fc161-109">Preview 8 name</span></span> | <span data-ttu-id="fc161-110">RC1 이상 이름</span><span class="sxs-lookup"><span data-stu-id="fc161-110">RC1 and later name</span></span> |
| - | - |
| `MinimumOSPlatformAttribute` | <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> |
| `RemovedInOSPlatformAttribute` | <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute> |

<span data-ttu-id="fc161-111">.NET 5 RC1 이상에서 프로젝트가 `net5.0-windows` 같은 [대상 프레임워크 모니커](../../../../standard/frameworks.md)를 사용하여 OS별 .NET 5 버전을 대상으로 하는 경우 빌드는 어셈블리 수준 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-111">In .NET 5 RC1 and later, when a project targets an OS-specific flavor of .NET 5 by using a [target framework moniker](../../../../standard/frameworks.md) such as `net5.0-windows`, the build adds an assembly-level <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute> attribute.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="fc161-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="fc161-112">Reason for change</span></span>

<span data-ttu-id="fc161-113">.NET 5 미리 보기 8에는 API에 지원되는 플랫폼을 지정하는 특성이 <xref:System.Runtime.Versioning>에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-113">.NET 5 Preview 8 introduced attributes in <xref:System.Runtime.Versioning> to specify supported platforms for APIs.</span></span> <span data-ttu-id="fc161-114">이 특성은 이러한 API를 지원하지 않는 플랫폼에서 플랫폼별 API가 사용되는 경우 [플랫폼 호환성 분석기](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md)에서 빌드 경고를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-114">The attributes are consumed by the [Platform compatibility analyzer](../../code-analysis/5.0/ca1416-platform-compatibility-analyzer.md) to produce build warnings when platform-specific APIs are consumed on platforms that don't support those APIs.</span></span>

<span data-ttu-id="fc161-115">.NET 5 RC1의 경우 플랫폼을 제외하는 기능이 플랫폼 호환성 분석기에 더 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-115">For .NET 5 RC1, an additional feature was added to the platform compatibility analyzer for platform exclusion.</span></span> <span data-ttu-id="fc161-116">이 기능을 통해 API가 OS 플랫폼에서 완전히 지원되지 않는 것으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-116">The feature allows APIs to be marked as entirely unsupported on OS platforms.</span></span> <span data-ttu-id="fc161-117">이 기능으로 인해 더 적절한 이름을 사용하는 등 특성을 변경하게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-117">That feature prompted changes to the attributes, including using more suitable names.</span></span> <span data-ttu-id="fc161-118">`ObsoletedInOSPlatformAttribute`는 더 이상 필요하지 않아 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-118">The `ObsoletedInOSPlatformAttribute` was removed because it was no longer needed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="fc161-119">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="fc161-119">Version introduced</span></span>

<span data-ttu-id="fc161-120">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="fc161-120">5.0 RC1</span></span>

## <a name="recommended-action"></a><span data-ttu-id="fc161-121">권장 조치</span><span class="sxs-lookup"><span data-stu-id="fc161-121">Recommended action</span></span>

<span data-ttu-id="fc161-122">해당 변경으로 인해 프로젝트 대상을 .NET 5 미리 보기 8에서 .NET 5 RC1로 바꿀 때 빌드 오류나 런타임 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-122">When you retarget your project from .NET 5 Preview 8 to .NET 5 RC1, you might encounter build or run-time errors due to these changes.</span></span> <span data-ttu-id="fc161-123">예를 들어 `MinimumOSPlatformAttribute`의 이름을 바꾸면 오류가 발생할 수 있습니다. 빌드 시 특성이 플랫폼별 어셈블리에 적용되지만, 이전 빌드 아티팩트가 여전히 이전 API 이름을 참조하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-123">For example, the renaming of `MinimumOSPlatformAttribute` is likely to produce errors, because the attribute is applied to platform-specific assemblies at build time, and old build artifacts will still reference the old API name.</span></span>

<span data-ttu-id="fc161-124">빌드 시 오류 예:</span><span class="sxs-lookup"><span data-stu-id="fc161-124">Example build-time errors:</span></span>

- <span data-ttu-id="fc161-125">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘MinimumOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="fc161-125">**error CS0246: The type or namespace name 'MinimumOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="fc161-126">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘RemovedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="fc161-126">**error CS0246: The type or namespace name 'RemovedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>
- <span data-ttu-id="fc161-127">**오류 CS0246: 형식 또는 네임스페이스 이름 ‘ObsoletedInOSPlatformAttribute’를 찾을 수 없습니다. (사용 중인 지시문 또는 어셈블리 참조가 없습니까?)**</span><span class="sxs-lookup"><span data-stu-id="fc161-127">**error CS0246: The type or namespace name 'ObsoletedInOSPlatformAttribute' could not be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="fc161-128">런타임 오류 예:</span><span class="sxs-lookup"><span data-stu-id="fc161-128">Example run-time error:</span></span>

<span data-ttu-id="fc161-129">**처리되지 않은 예외: System.TypeLoadException: 어셈블리 ‘System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a’에서 형식 ‘System.Runtime.Versioning.MinimumOSPlatformAttribute’를 로드할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="fc161-129">**Unhandled exception. System.TypeLoadException: Could not load type 'System.Runtime.Versioning.MinimumOSPlatformAttribute' from assembly 'System.Runtime, Version=5.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a'.**</span></span>

<span data-ttu-id="fc161-130">이러한 오류를 해결하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-130">To resolve these errors:</span></span>

- <span data-ttu-id="fc161-131">`MinimumOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-131">Update any references of `MinimumOSPlatformAttribute` to <xref:System.Runtime.Versioning.SupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="fc161-132">`RemovedInOSPlatformAttribute`의 모든 참조를 <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-132">Update any references of `RemovedInOSPlatformAttribute` to <xref:System.Runtime.Versioning.UnsupportedOSPlatformAttribute>.</span></span>
- <span data-ttu-id="fc161-133">`ObsoletedInOSPlatformAttribute`에 대한 모든 참조를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="fc161-133">Remove any references to `ObsoletedInOSPlatformAttribute`.</span></span>
- <span data-ttu-id="fc161-134">이전 빌드 아티팩트를 삭제하려면 프로젝트를 다시 빌드합니다(또는 정리 + 빌드 수행).</span><span class="sxs-lookup"><span data-stu-id="fc161-134">Rebuild your project (or perform clean + build) to delete old build artifacts.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="fc161-135">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="fc161-135">Affected APIs</span></span>

- `System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `System.Runtime.Versioning.RemovedInOSPlatformAttribute`

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Runtime.Versioning.MinimumOSPlatformAttribute`
- `T:System.Runtime.Versioning.ObsoletedInOSPlatformAttribute`
- `T:System.Runtime.Versioning.RemovedInOSPlatformAttribute`

-->
