---
ms.openlocfilehash: 950c69199219cca615e403c6515239de8864d35d
ms.sourcegitcommit: d3c09791297f0edc468a4849a5f11ef62e0e90fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88137491"
---
### <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="002a6-101">LINQ OrderBy.First{OrDefault}의 복잡성이 증가함</span><span class="sxs-lookup"><span data-stu-id="002a6-101">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="002a6-102"><xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 및 <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>의 구현이 변경되어 연산의 복잡성이 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-102">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

#### <a name="change-description"></a><span data-ttu-id="002a6-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="002a6-103">Change description</span></span>

<span data-ttu-id="002a6-104">.NET Core 1.x~3.x에서 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)` 복잡도로 연산됩니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-104">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="002a6-105">첫 번째(또는 기본) 요소만 필요하므로 이를 찾는 데는 하나의 열거형만 하나만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-105">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="002a6-106">그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 정확히 `N`번 호출됩니다. 여기서 `N`은 시퀀스의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-106">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="002a6-107">.NET 5.0 이상 버전에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)`의 복잡도 대신 `O(N log N)`의 복잡도로 연산되도록 [변경이 적용](https://github.com/dotnet/runtime/pull/36643)되었습니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-107">In .NET 5.0 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="002a6-108">그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 `N`번보다 적게 호출될 수 있는데, 이는 전체 성능에 더 중요한 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="002a6-109">이 변경 사항은 .NET Framework의 연산의 구현 및 복잡도와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-109">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="002a6-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="002a6-110">Reason for change</span></span>

<span data-ttu-id="002a6-111">조건자를 보다 적게 호출하는 것의 이점은 전체적인 복잡도 감소의 이점을 능가하므로, .NET Core 1.0에 적용된 구현이 되돌려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-111">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="002a6-112">자세한 내용은 [이 dotnet/런타임 문제](https://github.com/dotnet/runtime/issues/31554)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="002a6-112">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="002a6-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="002a6-113">Version introduced</span></span>

<span data-ttu-id="002a6-114">5.0</span><span class="sxs-lookup"><span data-stu-id="002a6-114">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="002a6-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="002a6-115">Recommended action</span></span>

<span data-ttu-id="002a6-116">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="002a6-116">No action is required on the developer's part.</span></span>

#### <a name="category"></a><span data-ttu-id="002a6-117">범주</span><span class="sxs-lookup"><span data-stu-id="002a6-117">Category</span></span>

<span data-ttu-id="002a6-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="002a6-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="002a6-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="002a6-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
