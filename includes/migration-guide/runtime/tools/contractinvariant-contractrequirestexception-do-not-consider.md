---
ms.openlocfilehash: 29c66edfeb1690199aac39b9c3076d161b2075d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621345"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="354fc-101">Contract.Invariant 또는 Contract.Requires\<TException>는 String.IsNullOrEmpty를 순수형으로 간주하지 않습니다</span><span class="sxs-lookup"><span data-stu-id="354fc-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="354fc-102">설명</span><span class="sxs-lookup"><span data-stu-id="354fc-102">Details</span></span>

<span data-ttu-id="354fc-103">.NET Framework 4.6.1을 대상으로 하는 앱의 경우 <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType>의 고정 계약 또는 <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)>의 사전 조건 계약이 <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> 메서드를 호출하는 경우 재작성기에서 CC1036 컴파일러 경고: &quot;메서드에서 [순수형] 없이 'System.String.IsNullOrWhteSpace(System.String)' 메서드에 대한 호출이 감지되었습니다.&quot;를 내보냅니다. 이는 컴파일러 오류가 아닌 컴파일러 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="354fc-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="354fc-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="354fc-104">Suggestion</span></span>

<span data-ttu-id="354fc-105">이 동작에서는 [GitHub 문제 #339](https://github.com/Microsoft/CodeContracts/issues/339)가 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="354fc-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="354fc-106">이 경고를 제거하려면 [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md)에서 코드 계약 도구에 대한 소스 코드를 다운로드 및 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="354fc-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="354fc-107">다운로드 정보는 페이지 하단에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="354fc-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="354fc-108">이름</span><span class="sxs-lookup"><span data-stu-id="354fc-108">Name</span></span>    | <span data-ttu-id="354fc-109">값</span><span class="sxs-lookup"><span data-stu-id="354fc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="354fc-110">Scope</span><span class="sxs-lookup"><span data-stu-id="354fc-110">Scope</span></span>   |<span data-ttu-id="354fc-111">부</span><span class="sxs-lookup"><span data-stu-id="354fc-111">Minor</span></span>|
|<span data-ttu-id="354fc-112">버전</span><span class="sxs-lookup"><span data-stu-id="354fc-112">Version</span></span>|<span data-ttu-id="354fc-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="354fc-113">4.6.1</span></span>|
|<span data-ttu-id="354fc-114">형식</span><span class="sxs-lookup"><span data-stu-id="354fc-114">Type</span></span>|<span data-ttu-id="354fc-115">런타임</span><span class="sxs-lookup"><span data-stu-id="354fc-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="354fc-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="354fc-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
