---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366882"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a><span data-ttu-id="d7567-101">IEnumerable\<T>를 사용하는 확장 메서드에 GroupCollection을 전달하려면 명확성 필요</span><span class="sxs-lookup"><span data-stu-id="d7567-101">Passing GroupCollection to extension methods taking IEnumerable\<T> requires disambiguation</span></span>

<span data-ttu-id="d7567-102"><xref:System.Text.RegularExpressions.GroupCollection>에서 `IEnumerable<T>`를 사용하는 확장 메서드를 호출하는 경우 캐스트를 사용하여 형식을 명확하게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-102">When calling an extension method that takes an `IEnumerable<T>` on a <xref:System.Text.RegularExpressions.GroupCollection>, you must disambiguate the type using a cast.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d7567-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d7567-103">Change description</span></span>

<span data-ttu-id="d7567-104">.NET Core 3.0부터 <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType>은 구현하는 `IEnumerable<Group>`을 비롯한 기타 형식 외에 `IEnumerable<KeyValuePair<String,Group>>`도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-104">Starting in .NET Core 3.0, <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType> implements `IEnumerable<KeyValuePair<String,Group>>` in addition to the other types it implements, including `IEnumerable<Group>`.</span></span> <span data-ttu-id="d7567-105">따라서 <xref:System.Collections.Generic.IEnumerable%601>를 사용하는 확장 메서드를 호출할 때 모호성이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-105">This results in ambiguity when calling an extension method that takes an <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="d7567-106"><xref:System.Text.RegularExpressions.GroupCollection> 인스턴스에서 이러한 확장 메서드(예: <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>)를 호출하는 경우 다음과 같은 컴파일러 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-106">If you call such an extension method on a <xref:System.Text.RegularExpressions.GroupCollection> instance, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>, you'll see the following compiler error:</span></span>

<span data-ttu-id="d7567-107">**CS1061: ‘GroupCollection’에 ‘Count’에 대한 정의가 없고 ‘GroupCollection’ 형식의 첫 번째 인수를 허용하는 액세스 가능한 확장 메서드 ‘Count’가 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하세요.**</span><span class="sxs-lookup"><span data-stu-id="d7567-107">**CS1061: 'GroupCollection' does not contain a definition for 'Count' and no accessible extension method 'Count' accepting a first argument of type 'GroupCollection' could be found (are you missing a using directive or an assembly reference?)**</span></span>

<span data-ttu-id="d7567-108">이전 버전의 .NET에서는 모호성이 없어서 컴파일러 오류가 발생하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-108">In previous versions of .NET, there was no ambiguity and no compiler error.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d7567-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d7567-109">Version introduced</span></span>

<span data-ttu-id="d7567-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d7567-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d7567-111">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d7567-111">Reason for change</span></span>

<span data-ttu-id="d7567-112">이는 [호환성이 손상되는 의도치 않은 변경](https://github.com/dotnet/corefx/pull/30077)이었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-112">This was an [unintentional breaking change](https://github.com/dotnet/corefx/pull/30077).</span></span> <span data-ttu-id="d7567-113">이와 같은 상황은 한동안 지속되어 왔으므로 되돌릴 계획이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-113">Because it has been like this for some time, we don't plan to revert it.</span></span> <span data-ttu-id="d7567-114">또한 되돌리는 변경 자체로도 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-114">In addition, such a change would itself be breaking.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d7567-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d7567-115">Recommended action</span></span>

<span data-ttu-id="d7567-116"><xref:System.Text.RegularExpressions.GroupCollection> 인스턴스의 경우 `IEnumerable<T>`를 허용하는 확장 메서드의 호출을 캐스트를 사용하여 명확하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-116">For <xref:System.Text.RegularExpressions.GroupCollection> instances, disambiguate calls to extension methods that accept an `IEnumerable<T>` with a cast.</span></span>

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a><span data-ttu-id="d7567-117">범주</span><span class="sxs-lookup"><span data-stu-id="d7567-117">Category</span></span>

<span data-ttu-id="d7567-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="d7567-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7567-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d7567-119">Affected APIs</span></span>

<span data-ttu-id="d7567-120"><xref:System.Collections.Generic.IEnumerable%601>를 허용하는 모든 확장 메서드가 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="d7567-120">Any extension method that accepts an <xref:System.Collections.Generic.IEnumerable%601> is affected.</span></span> <span data-ttu-id="d7567-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d7567-121">For example:</span></span>

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- <span data-ttu-id="d7567-122">대부분의 `System.Linq.Enumerable` 메서드. 예: <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d7567-122">Most of the `System.Linq.Enumerable` methods, for example, <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName></span></span>
- <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName>
- <xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName>

<!--

#### Affected APIs

- ``M:System.Collections.Immutable.ImmutableArray.ToImmutableArray``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary`
- `Overload:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet`
- ``M:System.Collections.Immutable.ImmutableList.ToImmutableList``1(System.Collections.Generic.IEnumerable{``0})``
- `Overload:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary`
- `Overload:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet`
- `Overload:System.Data.DataTableExtensions.CopyToDataTable`
- `Overload:System.Linq.Enumerable.Count`
- `Overload:System.Linq.ParallelEnumerable.AsParallel`
- `Overload:System.Linq.Queryable.AsQueryable`

-->
