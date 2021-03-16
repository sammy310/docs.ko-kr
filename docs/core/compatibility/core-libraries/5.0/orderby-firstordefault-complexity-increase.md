---
title: '호환성이 손상되는 변경: LINQ OrderBy.First{OrDefault}의 복잡성이 증가함'
description: OrderBy.First의 구현이 변경된 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 4cd2dda5f60976f935505d6a6cb1e4c23d150d09
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257273"
---
# <a name="complexity-of-linq-orderbyfirstordefault-increased"></a><span data-ttu-id="50d32-103">LINQ OrderBy.First{OrDefault}의 복잡성이 증가함</span><span class="sxs-lookup"><span data-stu-id="50d32-103">Complexity of LINQ OrderBy.First{OrDefault} increased</span></span>

<span data-ttu-id="50d32-104"><xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 및 <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>의 구현이 변경되어 연산의 복잡성이 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-104">The implementation of <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> and <xref:System.Linq.Enumerable.OrderBy%2A>`.`<xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> has changed, resulting in increased complexity for the operation.</span></span>

## <a name="change-description"></a><span data-ttu-id="50d32-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="50d32-105">Change description</span></span>

<span data-ttu-id="50d32-106">.NET Core 1.x~3.x에서 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)` 복잡도로 연산됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-106">In .NET Core 1.x - 3.x, calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N)` complexity.</span></span> <span data-ttu-id="50d32-107">첫 번째(또는 기본) 요소만 필요하므로 이를 찾는 데는 하나의 열거형만 하나만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-107">Since only the first (or default) element is required, only one enumeration is required to find it.</span></span> <span data-ttu-id="50d32-108">그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 정확히 `N`번 호출됩니다. 여기서 `N`은 시퀀스의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-108">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> is invoked exactly `N` times, where `N` is the length of the sequence.</span></span>

<span data-ttu-id="50d32-109">.NET 5 이상 버전에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 또는 <xref:System.Linq.Enumerable.OrderByDescending%2A> 뒤에 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>을 호출하면 `O(N)`의 복잡도 대신 `O(N log N)`의 복잡도로 연산되도록 [변경이 적용](https://github.com/dotnet/runtime/pull/36643)되었습니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-109">In .NET 5 and later versions, a [change was made](https://github.com/dotnet/runtime/pull/36643) such that calling <xref:System.Linq.Enumerable.OrderBy%2A> or <xref:System.Linq.Enumerable.OrderByDescending%2A> followed by <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> operates with `O(N log N)` complexity instead of `O(N)` complexity.</span></span> <span data-ttu-id="50d32-110">그러나 <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> 또는 <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})>에 제공된 조건자가 `N`번보다 적게 호출될 수 있는데, 이는 전체 성능에 더 중요한 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-110">However, the predicate that's supplied to <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> or <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})> may be invoked *less* than `N` times, which is more important for overall performance.</span></span>

> [!NOTE]
> <span data-ttu-id="50d32-111">이 변경 사항은 .NET Framework의 연산의 구현 및 복잡도와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-111">This change matches the implementation and complexity of the operation in .NET Framework.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="50d32-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="50d32-112">Reason for change</span></span>

<span data-ttu-id="50d32-113">조건자를 보다 적게 호출하는 것의 이점은 전체적인 복잡도 감소의 이점을 능가하므로, .NET Core 1.0에 적용된 구현이 되돌려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-113">The benefit of invoking the predicate fewer times outweighs a lower overall complexity, so the implementation that was introduced in .NET Core 1.0 was reverted.</span></span> <span data-ttu-id="50d32-114">자세한 내용은 [이 dotnet/런타임 문제](https://github.com/dotnet/runtime/issues/31554)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50d32-114">For more information, see [this dotnet/runtime issue](https://github.com/dotnet/runtime/issues/31554).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="50d32-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="50d32-115">Version introduced</span></span>

<span data-ttu-id="50d32-116">5.0</span><span class="sxs-lookup"><span data-stu-id="50d32-116">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="50d32-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="50d32-117">Recommended action</span></span>

<span data-ttu-id="50d32-118">개발자는 아무 작업도 수행하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50d32-118">No action is required on the developer's part.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="50d32-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="50d32-119">Affected APIs</span></span>

- <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=fullName>
- <xref:System.Linq.Enumerable.First%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>
- <xref:System.Linq.Enumerable.FirstOrDefault%60%601(System.Collections.Generic.IEnumerable{%60%600},System.Func{%60%600,System.Boolean})?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Linq.Enumerable.OrderBy`
- `Overload:System.Linq.Enumerable.OrderByDescending`
- `M:System.Linq.Enumerable.First``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`
- `M:System.Linq.Enumerable.FirstOrDefault``1(System.Collections.Generic.IEnumerable{``0},System.Func{``0,System.Boolean})`

-->
