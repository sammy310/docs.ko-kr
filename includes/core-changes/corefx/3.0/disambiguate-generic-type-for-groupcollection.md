---
ms.openlocfilehash: 97fab784acac4331894547eea27fc21b485597fb
ms.sourcegitcommit: fcbe432482464b1639decad78cc4dc8387c6269e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "97366882"
---
### <a name="passing-groupcollection-to-extension-methods-taking-ienumerablet-requires-disambiguation"></a>IEnumerable\<T>를 사용하는 확장 메서드에 GroupCollection을 전달하려면 명확성 필요

<xref:System.Text.RegularExpressions.GroupCollection>에서 `IEnumerable<T>`를 사용하는 확장 메서드를 호출하는 경우 캐스트를 사용하여 형식을 명확하게 해야 합니다.

#### <a name="change-description"></a>변경 내용 설명

.NET Core 3.0부터 <xref:System.Text.RegularExpressions.GroupCollection?displayProperty=nameWithType>은 구현하는 `IEnumerable<Group>`을 비롯한 기타 형식 외에 `IEnumerable<KeyValuePair<String,Group>>`도 구현합니다. 따라서 <xref:System.Collections.Generic.IEnumerable%601>를 사용하는 확장 메서드를 호출할 때 모호성이 발생합니다. <xref:System.Text.RegularExpressions.GroupCollection> 인스턴스에서 이러한 확장 메서드(예: <xref:System.Linq.Enumerable.Count%2A?displayProperty=nameWithType>)를 호출하는 경우 다음과 같은 컴파일러 오류가 표시됩니다.

**CS1061: ‘GroupCollection’에 ‘Count’에 대한 정의가 없고 ‘GroupCollection’ 형식의 첫 번째 인수를 허용하는 액세스 가능한 확장 메서드 ‘Count’가 없습니다. using 지시문 또는 어셈블리 참조가 있는지 확인하세요.**

이전 버전의 .NET에서는 모호성이 없어서 컴파일러 오류가 발생하지 않았습니다.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="reason-for-change"></a>변경 이유

이는 [호환성이 손상되는 의도치 않은 변경](https://github.com/dotnet/corefx/pull/30077)이었습니다. 이와 같은 상황은 한동안 지속되어 왔으므로 되돌릴 계획이 없습니다. 또한 되돌리는 변경 자체로도 호환성이 손상될 수 있습니다.

#### <a name="recommended-action"></a>권장 조치

<xref:System.Text.RegularExpressions.GroupCollection> 인스턴스의 경우 `IEnumerable<T>`를 허용하는 확장 메서드의 호출을 캐스트를 사용하여 명확하게 합니다.

```csharp
// Without a cast - causes CS1061.
match.Groups.Count(_ => true)

// With a disambiguating cast.
((IEnumerable<Group>)m.Groups).Count(_ => true);
```

#### <a name="category"></a>범주

핵심 .NET 라이브러리

#### <a name="affected-apis"></a>영향을 받는 API

<xref:System.Collections.Generic.IEnumerable%601>를 허용하는 모든 확장 메서드가 영향을 받습니다. 예를 들어:

- <xref:System.Collections.Immutable.ImmutableArray.ToImmutableArray%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableDictionary.ToImmutableDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableHashSet.ToImmutableHashSet%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableList.ToImmutableList%60%601(System.Collections.Generic.IEnumerable{%60%600})?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedDictionary.ToImmutableSortedDictionary%2A?displayProperty=fullName>
- <xref:System.Collections.Immutable.ImmutableSortedSet.ToImmutableSortedSet%2A?displayProperty=fullName>
- <xref:System.Data.DataTableExtensions.CopyToDataTable%2A?displayProperty=fullName>
- 대부분의 `System.Linq.Enumerable` 메서드. 예: <xref:System.Linq.Enumerable.Count%2A?displayProperty=fullName>
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
