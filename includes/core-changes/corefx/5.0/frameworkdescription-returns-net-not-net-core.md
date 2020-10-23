---
ms.openlocfilehash: 80d13609f1b02ae0ac875b2028e745670bb8f503
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050570"
---
### <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a><span data-ttu-id="e6420-101">FrameworkDescription의 값은 .NET Core가 아닌 .NET입니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-101">FrameworkDescription's value is .NET instead of .NET Core</span></span>

<span data-ttu-id="e6420-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 이제 ".NET Core" 대신 ".NET"을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-102"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> now returns ".NET" instead of ".NET Core".</span></span>

#### <a name="change-description"></a><span data-ttu-id="e6420-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e6420-103">Change description</span></span>

<span data-ttu-id="e6420-104">이전 .NET 버전에서 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET Core 3.1.1`과 같은 설명 문자열의 일부로 ".NET Core"를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-104">In previous .NET versions, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET Core" as part of the description string, for example, `.NET Core 3.1.1`.</span></span>

<span data-ttu-id="e6420-105">.NET 5.0부터 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>은 `.NET 5.0.0`과 같은 설명 문자열의 일부로 ".NET Core"를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-105">Starting in .NET 5.0, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> returns ".NET" as part of the description string, for example, `.NET 5.0.0`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e6420-106">변경 이유</span><span class="sxs-lookup"><span data-stu-id="e6420-106">Reason for change</span></span>

<span data-ttu-id="e6420-107">.NET 5에서 `netcoreapp`은 짧은 대상 프레임워크 모니커인 `net`으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-107">With .NET 5, `netcoreapp` is replaced by `net` as the short target-framework moniker.</span></span> <span data-ttu-id="e6420-108">일관성을 위해 프레임워크의 설명도 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-108">For consistency, the framework's description has also been updated.</span></span> <span data-ttu-id="e6420-109">`FrameworkName`이 <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> 속성 이외의 다른 곳에서는 인코딩되지 않기 때문에 외관만 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-109">The change is cosmetic, as the `FrameworkName` isn't encoded anywhere else than in the <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> property.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e6420-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e6420-110">Version introduced</span></span>

<span data-ttu-id="e6420-111">5.0</span><span class="sxs-lookup"><span data-stu-id="e6420-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e6420-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e6420-112">Recommended action</span></span>

<span data-ttu-id="e6420-113"><xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>에서 반환된 문자열에서 ".NET Core"를 검색하는 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="e6420-113">Update any code that searches for ".NET Core" in the string returned by <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription>.</span></span>

#### <a name="category"></a><span data-ttu-id="e6420-114">범주</span><span class="sxs-lookup"><span data-stu-id="e6420-114">Category</span></span>

<span data-ttu-id="e6420-115">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="e6420-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e6420-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e6420-116">Affected APIs</span></span>

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
