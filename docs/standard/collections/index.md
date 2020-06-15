---
title: 컬렉션 및 데이터 구조
description: .NET에서 컬렉션 및 데이터 구조를 사용하는 방법에 대해 알아보세요. 스레드로부터 안전한 작업에서 제네릭 컬렉션 및 제네릭이 아닌 컬렉션을 사용합니다.
ms.date: 04/30/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- grouping data in collections
- objects [.NET Framework], grouping in collections
- Array class, grouping data in collections
- threading [.NET Framework], safety
- Collections classes
- collections [.NET Framework]
ms.assetid: 60cc581f-1db5-445b-ba04-a173396bf872
ms.openlocfilehash: 3d5b16dccdd9867293a52c74a2d379c807fd93e7
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662747"
---
# <a name="collections-and-data-structures"></a>컬렉션 및 데이터 구조

비슷한 데이터는 컬렉션으로 저장 및 조작하면 보다 효율적으로 처리할 수 있는 경우가 많습니다. <xref:System.Array?displayProperty=nameWithType> 클래스 또는 <xref:System.Collections>, <xref:System.Collections.Generic>, <xref:System.Collections.Concurrent> 및 <xref:System.Collections.Immutable> 네임스페이스의 클래스를 사용하여 개별 요소나 컬렉션 내의 요소 범위를 추가, 제거 및 수정할 수 있습니다.

컬렉션에는 제네릭 컬렉션과 제네릭이 아닌 컬렉션의 두 가지 기본 유형이 있습니다. .NET Framework 2.0에서 추가된 제네릭 컬렉션은 컴파일 타임에 형식이 안전한 컬렉션을 제공합니다. 이로 인해 제네릭 컬렉션은 일반적으로 성능이 더 뛰어납니다. 제네릭 컬렉션은 생성 시 형식 매개 변수를 허용하며, 컬렉션에서 항목을 추가하거나 제거할 때 <xref:System.Object> 형식과의 캐스팅을 수행하지 않아도 됩니다.  또한 대부분의 제네릭 컬렉션은 Windows 스토어 앱에서 지원됩니다. 제네릭이 아닌 컬렉션은 항목을 <xref:System.Object>로 저장하며, 캐스팅을 수행해야 합니다. 또한 이러한 컬렉션은 대부분 Windows 스토어 앱 개발용으로 지원되지 않습니다. 그러나 이전 코드에는 제네릭이 아닌 컬렉션이 포함되어 있는 경우도 있습니다.

.NET Framework 4부터 <xref:System.Collections.Concurrent> 네임스페이스의 컬렉션은 여러 스레드에서 컬렉션 항목에 액세스하기 위한 효율적이고 스레드로부터 안전한 작업을 제공합니다. <xref:System.Collections.Immutable> 네임스페이스에서 사용되는 변경할 수 없는 컬렉션 클래스([NuGet 패키지](https://www.nuget.org/packages/System.Collections.Immutable))는 기본적으로 스레드로부터 안전합니다. 작업이 원본 컬렉션의 복사본에 대해 수행되며 원본 컬렉션은 수정할 수 없기 때문입니다.

<a name="BKMK_Commoncollectionfeatures"></a>
## <a name="common-collection-features"></a>일반 컬렉션 기능

모든 컬렉션에서는 컬렉션의 항목을 추가, 제거 또는 찾는 방법을 제공합니다. 또한 직접/간접적으로 <xref:System.Collections.ICollection> 인터페이스 또는 <xref:System.Collections.Generic.ICollection%601> 인터페이스 공유를 구현하는 모든 컬렉션은 다음 기능을 공유합니다.

- **컬렉션을 열거하는 기능**

    .NET Framework 컬렉션은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>을 구현하므로 컬렉션을 반복할 수 있습니다. 열거자는 컬렉션의 모든 요소에 대한 이동 가능 포인터라고 할 수 있습니다. [foreach, in](../../csharp/language-reference/keywords/foreach-in.md) 문과 [For Each...Next 문](../../visual-basic/language-reference/statements/for-each-next-statement.md)은 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드가 노출하는 열거자를 사용하며 해당 열거자를 조작하는 복잡한 작업을 숨깁니다. 또한 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>을 구현하는 모든 컬렉션은 *쿼리 가능 형식*으로 간주할 수 있으며 LINQ를 사용하여 쿼리할 수 있습니다. LINQ 쿼리는 데이터 액세스를 위한 일반 패턴을 제공합니다. 이러한 쿼리는 대개 표준 `foreach` 루프보다 간결하고 읽기 쉬우며 필터링, 순서 지정 및 그룹화 기능을 제공합니다. 또한 LINQ 쿼리를 통해 성능을 향상시킬 수도 있습니다. 자세한 내용은 [LINQ to Objects(C#)](../../csharp/programming-guide/concepts/linq/linq-to-objects.md), [LINQ to Objects(Visual Basic)](../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md), [PLINQ (병렬 LINQ)](../parallel-programming/introduction-to-plinq.md), [LINQ 쿼리 소개(C#)](../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) 및 [기본 쿼리 작업(Visual Basic)](../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)을 참조하세요.

- **컬렉션의 내용을 배열에 복사하는 기능**

    **CopyTo** 메서드를 사용하면 컬렉션을 배열에 복사할 수 있습니다. 그러나 새 배열의 요소 순서는 열거자가 요소를 반환하는 순서를 기준으로 합니다. 결과 배열은 항상 1차원이며 하한은 0입니다.

또한 다수의 컬렉션 클래스에는 다음 기능도 포함되어 있습니다.

- **Capacity 및 Count 속성**

    컬렉션의 용량은 컬렉션에 포함할 수 있는 요소의 수이고, 컬렉션의 카운트는 컬렉션에 실제로 포함되어 있는 요소의 수입니다. 용량이나 카운트 중 하나 또는 둘 다를 숨기는 컬렉션도 있습니다.

    대부분의 컬렉션은 현재 용량에 도달하면 자동으로 용량을 확장합니다. 이때 메모리가 다시 할당되며 요소는 이전 컬렉션에서 새 컬렉션으로 복사됩니다. 따라서 컬렉션을 사용하는 데 필요한 코드는 감소하지만 컬렉션 성능이 저하될 수 있습니다. 예를 들어 <xref:System.Collections.Generic.List%601>의 경우 <xref:System.Collections.Generic.List%601.Count%2A>가 <xref:System.Collections.Generic.List%601.Capacity%2A>보다 작으면 항목을 추가하는 것은 O(1) 작업이 됩니다. 새 요소를 포함할 수 있도록 용량을 늘려야 하는 경우 항목을 추가하는 것은 O(`n`) 작업이 됩니다. 여기서 `n`은 <xref:System.Collections.Generic.List%601.Count%2A>입니다. 메모리가 여러 번 다시 할당되어 성능이 저하되는 현상을 방지하는 가장 좋은 방법은 초기 용량을 컬렉션의 예상 크기로 설정하는 것입니다.

    <xref:System.Collections.BitArray>는 해당 용량과 길이 및 카운트가 모두 같은 특수한 경우입니다.

- **일관된 하한**

    컬렉션의 하한은 첫 번째 요소의 인덱스입니다. <xref:System.Collections> 네임스페이스의 모든 인덱싱된 컬렉션은 하한이 0입니다(0부터 인덱싱됨). <xref:System.Array>의 기본 하한은 0이지만 <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType>를 사용하여 **Array** 클래스의 인스턴스를 만들 때 다른 하한을 정의할 수 있습니다.

- **여러 스레드로부터의 액세스를 위한 동기화**(<xref:System.Collections> 클래스에만 해당됨).

    <xref:System.Collections> 네임스페이스의 제네릭이 아닌 컬렉션 형식은 동기화와 관련하여 어느 정도의 스레드 보안을 제공합니다(일반적으로 <xref:System.Collections.ICollection.SyncRoot%2A> 및 <xref:System.Collections.ICollection.IsSynchronized%2A> 멤버를 통해 노출됨). 이러한 컬렉션은 기본적으로 스레드로부터 안전하지 않습니다. 확장 가능하며 효율적인 다중 스레드 방식으로 컬렉션에 액세스해야 하는 경우에는 <xref:System.Collections.Concurrent> 네임스페이스의 클래스 중 하나를 사용하거나 변경할 수 없는 컬렉션을 사용하는 것이 좋습니다. 자세한 내용은 [스레드로부터 안전한 컬렉션](thread-safe/index.md)을 참조하세요.

<a name="BKMK_Choosingacollection"></a>
## <a name="choose-a-collection"></a>컬렉션 선택

일반적으로는 제네릭 컬렉션을 사용해야 합니다. 다음 표에는 몇 가지 일반적인 컬렉션 시나리오와 이러한 시나리오에서 사용할 수 있는 컬렉션 클래스에 대해 설명합니다. 제네릭 컬렉션을 처음 사용하는 경우 이 표의 내용을 참조하여 작업에 가장 적합한 제네릭 컬렉션을 선택할 수 있습니다.

|수행할 작업|제네릭 컬렉션 옵션|제네릭이 아닌 컬렉션 옵션|스레드로부터 안전하거나 변경할 수 없는 컬렉션 옵션|
|-|-|-|-|
|키별로 빠르게 조회할 수 있도록 항목을 키/값 쌍으로 저장|<xref:System.Collections.Generic.Dictionary%602>|<xref:System.Collections.Hashtable><br /><br /> (키의 해시 코드를 기준으로 구성되는 키/값 쌍 컬렉션)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602><br /><br /> <xref:System.Collections.ObjectModel.ReadOnlyDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableDictionary%602>|
|인덱스별로 항목 액세스|<xref:System.Collections.Generic.List%601>|<xref:System.Array><br /><br /> <xref:System.Collections.ArrayList>|<xref:System.Collections.Immutable.ImmutableList%601><br /><br /> <xref:System.Collections.Immutable.ImmutableArray>|
|FIFO(선입 선출) 방식으로 항목 사용|<xref:System.Collections.Generic.Queue%601>|<xref:System.Collections.Queue>|<xref:System.Collections.Concurrent.ConcurrentQueue%601><br /><br /> <xref:System.Collections.Immutable.ImmutableQueue%601>|
|LIFO(후입 선출) 방식으로 데이터 사용|<xref:System.Collections.Generic.Stack%601>|<xref:System.Collections.Stack>|<xref:System.Collections.Concurrent.ConcurrentStack%601><br /><br /> <xref:System.Collections.Immutable.ImmutableStack%601>|
|순서대로 항목 액세스|<xref:System.Collections.Generic.LinkedList%601>|권장 사항 없음|권장 사항 없음|
|항목을 컬렉션에 추가하거나 컬렉션에서 제거할 때 알림이 표시됩니다. (<xref:System.ComponentModel.INotifyPropertyChanged> 및 <xref:System.Collections.Specialized.INotifyCollectionChanged> 구현)|<xref:System.Collections.ObjectModel.ObservableCollection%601>|권장 사항 없음|권장 사항 없음|
|정렬된 컬렉션|<xref:System.Collections.Generic.SortedList%602>|<xref:System.Collections.SortedList>|<xref:System.Collections.Immutable.ImmutableSortedDictionary%602><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|
|수학 함수용 집합|<xref:System.Collections.Generic.HashSet%601><br /><br /> <xref:System.Collections.Generic.SortedSet%601>|권장 사항 없음|<xref:System.Collections.Immutable.ImmutableHashSet%601><br /><br /> <xref:System.Collections.Immutable.ImmutableSortedSet%601>|

### <a name="algorithmic-complexity-of-collections"></a>컬렉션의 알고리즘 복잡성

[컬렉션 클래스](selecting-a-collection-class.md)를 선택할 때 성능과 관련된 잠재적 장단점을 고려하는 것이 좋습니다. 다음 표에서 변경 가능한 다양한 컬렉션 형식이 상응하는 변경할 수 없는 컬렉션과 알고리즘 복잡성이 어떻게 다른지 참조하세요. 종종 변경할 수 없는 컬렉션 형식은 성능이 떨어지지만 불변성 덕분에 상대적으로 유효한 이익이 되는 경우가 많습니다.

| 변경 가능                   | 분할  | 최악의 경우                | 변경할 수 없음                          | 복잡성 |
|---------------------------|------------|---------------------------|------------------------------------|------------|
| `Stack<T>.Push`           | O(1)       | O(`n`)                    | `ImmutableStack<T>.Push`           | O(1)       |
| `Queue<T>.Enqueue`        | O(1)       | O(`n`)                    | `ImmutableQueue<T>.Enqueue`        | O(1)       |
| `List<T>.Add`             | O(1)       | O(`n`)                    | `ImmutableList<T>.Add`             | O(log `n`) |
| `List<T>.Item[Int32]`     | O(1)       | O(1)                      | `ImmutableList<T>.Item[Int32]`     | O(log `n`) |
| `List<T>.Enumerator`      | O(`n`)     | O(`n`)                    | `ImmutableList<T>.Enumerator`      | O(`n`)     |
| `HashSet<T>.Add`, lookup  | O(1)       | O(`n`)                    | `ImmutableHashSet<T>.Add`          | O(log `n`) |
| `SortedSet<T>.Add`        | O(log `n`) | O(`n`)                    | `ImmutableSortedSet<T>.Add`        | O(log `n`) |
| `Dictionary<T>.Add`       | O(1)       | O(`n`)                    | `ImmutableDictionary<T>.Add`       | O(log `n`) |
| `Dictionary<T>` lookup    | O(1)       | O(1) – 또는 엄격하게 O(`n`) | `ImmutableDictionary<T>` lookup    | O(log `n`) |
| `SortedDictionary<T>.Add` | O(log `n`) | O(`n` log `n`)            | `ImmutableSortedDictionary<T>.Add` | O(log `n`) |

`List<T>`는 `for` 루프 또는 `foreach` 루프를 사용하여 효율적으로 열거할 수 있습니다. 그러나 `ImmutableList<T>`는 인덱서의 O(log `n`) 시간 때문에 `for` 루프 내에서 작업이 제대로 수행되지 않습니다. `foreach` 루프를 사용하여 `ImmutableList<T>`를 열거하면 효과적인데, `ImmutableList<T>`는 `List<T>`에서 사용하는 것과 같은 단순 배열이 아니라 이진 트리를 사용하여 데이터를 저장하기 때문입니다. 배열은 매우 빠르게 인덱싱할 수 있는 반면 이진 트리는 필요한 인덱스가 있는 노드를 찾을 때까지 검사해야 합니다.

또한 `SortedSet<T>`는 `ImmutableSortedSet<T>`와 복잡성이 같습니다. 둘 다 이진 트리를 사용하기 때문입니다. 물론 중요한 차이점은 `ImmutableSortedSet<T>`는 변경 불가능한 이진 트리를 사용한다는 것입니다. `ImmutableSortedSet<T>`는 변경을 허용하는 <xref:System.Collections.Immutable.ImmutableSortedSet%601.Builder?displayProperty=nameWithType> 클래스도 제공하므로 불변성과 성능을 모두 얻을 수 있습니다.

<a name="BKMK_RelatedTopics"></a>
## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[Collection 클래스 선택](selecting-a-collection-class.md)|다양한 컬렉션에 대해 설명하고 시나리오에 맞는 컬렉션을 선택하는 데 도움이 되는 정보를 제공합니다.|
|[일반적으로 사용되는 컬렉션 형식](commonly-used-collection-types.md)|<xref:System.Array?displayProperty=nameWithType>, <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>와 같이 일반적으로 사용되는 제네릭 및 제네릭이 아닌 컬렉션 형식을 설명합니다.|
|[제네릭 컬렉션 사용 기준](when-to-use-generic-collections.md)|제네릭 컬렉션 형식의 사용을 설명합니다.|
|[컬렉션 내에서 비교 및 정렬](comparisons-and-sorts-within-collections.md)|컬렉션에서 같음 비교 및 정렬 비교를 사용하는 방법을 설명합니다.|
|[Sorted 컬렉션 형식](sorted-collection-types.md)|정렬된 컬렉션의 성능 및 특징에 대해 설명합니다.|
|[Hashtable 및 Dictionary 컬렉션 형식](hashtable-and-dictionary-collection-types.md)|제네릭 및 제네릭이 아닌 해시 기반 사전 형식의 기능을 설명합니다.|
|[스레드로부터 안전한 컬렉션](thread-safe/index.md)|여러 스레드의 안전하고 효율적인 동시 액세스를 지원하는 <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>과 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType> 같은 컬렉션 형식에 대해 설명합니다.|
|System.Collections.Immutable|변경 불가능은 컬렉션을 소개하고 컬렉션 형식에 대한 링크를 제공합니다.|

<a name="BKMK_Reference"></a>
## <a name="reference"></a>참고
<xref:System.Array?displayProperty=nameWithType>
<xref:System.Collections?displayProperty=nameWithType>
<xref:System.Collections.Concurrent?displayProperty=nameWithType>
<xref:System.Collections.Generic?displayProperty=nameWithType>
<xref:System.Collections.Specialized?displayProperty=nameWithType>
<xref:System.Linq?displayProperty=nameWithType>
<xref:System.Collections.Immutable>
