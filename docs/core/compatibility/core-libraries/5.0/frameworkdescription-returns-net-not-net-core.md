---
title: '호환성이 손상되는 변경: FrameworkDescription의 값은 .NET Core가 아닌 .NET입니다.'
description: RuntimeInformation.FrameworkDescription에서 “.NET Core” 대신 “.NET”을 반환하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 18aa9a30a149b3c38d4bbfe4a0c99446f4372f07
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257520"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="b277d-103">FrameworkDescription의 값은 .NET Core가 아닌 .NET입니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-103">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="b277d-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 이제 ".NET Core" 대신 ".NET"을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-104"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

## <a name="change-description"></a><span data-ttu-id="b277d-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="b277d-105">Change description</span></span>

<span data-ttu-id="b277d-106">이전 .NET 버전에서 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET Core 3.1.1`과 같은 설명 문자열의 일부로 ".NET Core"를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-106">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="b277d-107">.NET 5부터 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET 5.0.0`과 같은 설명 문자열의 일부로 ".NET"을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-107">Starting in .NET 5, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="b277d-108">변경 이유</span><span class="sxs-lookup"><span data-stu-id="b277d-108">Reason for change</span></span>

<span data-ttu-id="b277d-109">.NET 5에서 `netcoreapp`은 짧은 대상 프레임워크 모니커인 `net`으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-109">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="b277d-110">일관성을 위해 프레임워크의 설명도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-110">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="b277d-111">`FrameworkName`이 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 속성 이외의 다른 곳에서는 인코딩되지 않기 때문에 외관만 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-111">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b277d-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="b277d-112">Version introduced</span></span>

<span data-ttu-id="b277d-113">5.0</span><span class="sxs-lookup"><span data-stu-id="b277d-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b277d-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="b277d-114">Recommended action</span></span>

<span data-ttu-id="b277d-115"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>에서 반환된 문자열에서 ".NET Core"를 검색하는 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b277d-115">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b277d-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="b277d-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
