---
description: '자세한 정보: 컬렉션에 대한 지침'
title: 컬렉션에 대한 지침
ms.date: 10/22/2008
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: fa189068e9f3e06b3e88999bd4b0ea0998cd16e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642034"
---
# <a name="guidelines-for-collections"></a>컬렉션에 대한 지침

몇 가지 공통 특성이 있는 개체 그룹을 조작하도록 특별히 설계된 모든 형식을 컬렉션으로 간주할 수 있습니다. <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 형식에 거의 항상 적합합니다. 따라서 이 섹션에서는 해당 인터페이스 중 하나 또는 둘 다를 구현하는 형식만 컬렉션으로 간주합니다.

 ❌ 퍼블릭 API에서 약한 형식의 컬렉션을 사용하지 마세요.

 컬렉션 항목을 나타내는 모든 반환 값 및 매개 변수의 형식은 기본 형식이 아니라 정확한 항목 형식이어야 합니다. 이 지침은 컬렉션의 퍼블릭 멤버에만 적용됩니다.

 ❌ 퍼블릭 API에서 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.Generic.List%601>를 사용하지 마세요.

 이러한 형식은 공용 API가 아닌 내부 구현에서 사용하도록 설계된 데이터 구조입니다. `List<T>`는 API의 정리 및 유연성 대신 성능 및 강력한 기능에 맞게 최적화되었습니다. 예를 들어 `List<T>`를 반환하면 클라이언트 코드에서 컬렉션을 수정할 때 알림을 받을 수 없습니다. 또한 `List<T>`는 <xref:System.Collections.Generic.List%601.BinarySearch%2A>와 같이 많은 시나리오에서 유용하지 않거나 적용되지 않는 많은 멤버를 노출합니다. 다음 두 섹션에서는 퍼블릭 API에서 사용하도록 특별히 설계된 형식(추상화)에 대해 설명합니다.

 ❌ 퍼블릭 API에서 `Hashtable` 또는 `Dictionary<TKey,TValue>`를 사용하지 마세요.

 이러한 형식은 내부 구현에서 사용하도록 설계된 데이터 구조입니다. 퍼블릭 API는 인터페이스 중 하나 또는 둘 다를 구현하는 <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>` 또는 사용자 지정 형식을 사용해야 합니다.

 ❌ `GetEnumerator` 메서드의 반환 형식인 경우를 제외하고 <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator> 또는 이러한 인터페이스 중 하나를 구현하는 다른 모든 형식을 사용하지 마세요.

 `GetEnumerator` 이외의 메서드에서 열거자를 반환하는 형식은 `foreach` 문과 함께 사용할 수 없습니다.

 ❌ `IEnumerator<T>` 및 `IEnumerable<T>`을 동일한 형식으로 구현하지 마세요. 제네릭이 아닌 인터페이스 `IEnumerator` 및 `IEnumerable`에도 동일하게 적용됩니다.

## <a name="collection-parameters"></a>컬렉션 매개 변수

 ✔️ 최소로 특수화된 형식을 매개 변수 형식으로 사용하세요. 컬렉션을 매개 변수로 사용하는 대부분의 멤버는 `IEnumerable<T>` 인터페이스를 사용합니다.

 ❌ `Count` 속성에 액세스하기 위해 <xref:System.Collections.Generic.ICollection%601> 또는 <xref:System.Collections.ICollection>을 매개 변수로 사용하면 안 됩니다.

 대신 `IEnumerable<T>` 또는 `IEnumerable`을 사용하고 개체가 `ICollection<T>` 또는 `ICollection`을 구현하는지를 동적으로 확인하는 것이 좋습니다.

## <a name="collection-properties-and-return-values"></a>컬렉션 속성 및 반환 값

 ❌ 설정 가능한 컬렉션 속성을 제공하지 마세요.

 사용자는 먼저 컬렉션을 지운 다음 새 콘텐츠를 추가하여 컬렉션의 콘텐츠를 바꿀 수 있습니다. 전체 컬렉션을 바꾸는 것이 일반적인 시나리오인 경우 컬렉션에서 `AddRange` 메서드를 제공하는 것이 좋습니다.

 ✔️ 읽기/쓰기 컬렉션을 나타내는 반환 값 또는 속성에 `Collection<T>`의 서브클래스 또는 `Collection<T>`을 사용하세요.

 `Collection<T>`이 일부 요구 사항(예: 컬렉션은 <xref:System.Collections.IList>를 구현하면 안 됨)을 충족하지 않는 경우 `IEnumerable<T>`, `ICollection<T>` 또는 <xref:System.Collections.Generic.IList%601>를 구현하여 사용자 지정 컬렉션을 사용하세요.

 ✔️ 읽기 전용 컬렉션을 나타내는 반환 값 또는 속성에 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, `ReadOnlyCollection<T>`의 서브클래스 또는 드문 경우이지만 `IEnumerable<T>`을 사용하세요.

 일반적으로 `ReadOnlyCollection<T>`을 사용하는 것이 좋습니다. 일부 요구 사항(예: 컬렉션은 `IList`를 구현하면 안 됨)을 충족하지 않는 경우 `IEnumerable<T>`, `ICollection<T>` 또는 `IList<T>`를 구현하여 사용자 지정 컬렉션을 사용하세요. 사용자 지정 읽기 전용 컬렉션을 구현하는 경우 `true`를 반환하려면 `ICollection<T>.IsReadOnly`을 구현하세요.

 지원하려는 시나리오가 정방향으로만 반복되는 경우에는 `IEnumerable<T>`을 사용하면 됩니다.

 ✔️ 컬렉션을 직접 사용하는 대신 제네릭 기본 컬렉션의 서브클래스를 사용하는 것이 좋습니다.

 그러면 더 나은 이름이 허용되고 기본 컬렉션 형식에 없는 도우미 멤버를 추가할 수 있습니다. 이 지침은 상위 수준 API에 특히 적합합니다.

 ✔️ 매우 일반적으로 사용되는 메서드 및 속성에서 `Collection<T>` 또는 `ReadOnlyCollection<T>`의 서브클래스를 반환하는 것이 좋습니다.

 그러면 도우미 메서드를 추가하거나 나중에 컬렉션 구현을 변경할 수 있습니다.

 ✔️ 컬렉션에 저장된 항목에 고유 키(이름, ID 등)가 있는 경우 키가 지정된 컬렉션을 사용하는 것이 좋습니다. 키가 지정된 컬렉션은 정수와 키로 인덱싱할 수 있는 컬렉션이며 일반적으로 `KeyedCollection<TKey,TItem>`에서 상속하여 구현됩니다.

 키가 지정된 컬렉션은 일반적으로 메모리 공간이 더 크며 메모리 오버헤드가 키가 있다는 이점보다 더 큰 경우에는 사용하지 않아야 합니다.

 ❌ 컬렉션 속성 또는 컬렉션을 반환하는 메서드에서 null 값을 반환하지 마세요. 대신 빈 컬렉션이나 빈 배열을 반환합니다.

 일반적인 규칙에 따르면 null 컬렉션이나 배열과 항목이 0개인 빈 컬렉션이나 배열을 동일하게 처리해야 합니다.

### <a name="snapshots-versus-live-collections"></a>스냅샷과 라이브 컬렉션 비교

 특정 시점의 상태를 나타내는 컬렉션을 스냅샷 컬렉션이라고 합니다. 예를 들어 데이터베이스 쿼리에서 반환된 행을 포함하는 컬렉션은 스냅샷이 됩니다. 항상 현재 상태를 나타내는 컬렉션을 라이브 컬렉션이라고 합니다. 예를 들어 `ComboBox` 항목의 컬렉션은 라이브 컬렉션입니다.

 ❌ 속성에서 스냅샷 컬렉션을 반환하지 마세요. 속성은 라이브 컬렉션을 반환해야 합니다.

 속성 getter는 매우 간단한 작업이어야 합니다. 스냅샷을 반환하려면 O(n) 작업에서 내부 컬렉션의 복사본을 만들어야 합니다.

 ✔️ 컬렉션을 명시적으로 수정하지 않고도 변경될 수 있는 휘발성인 컬렉션을 나타내려면 스냅샷 컬렉션이나 라이브 `IEnumerable<T>`(또는 하위 형식)을 사용하세요.

 일반적으로 공유 리소스(예: 디렉터리의 파일)를 나타내는 모든 컬렉션은 휘발성입니다. 구현이 단순한 정방향 전용 열거자인 경우가 아니라면 이러한 컬렉션을 라이브 컬렉션으로 구현하는 것은 매우 어렵거나 불가능합니다.

## <a name="choosing-between-arrays-and-collections"></a>배열 및 컬렉션 중에서 선택

 ✔️ 배열보다 컬렉션을 사용하세요.

 컬렉션은 콘텐츠를 더 세부적으로 제어할 수 있으며, 시간에 따라 개선되고, 더욱 유용해집니다. 또한 배열을 복제하는 비용이 너무 많이 들기 때문에 읽기 전용 시나리오에는 배열을 사용하지 않는 것이 좋습니다. 유용성 연구에 따르면 일부 개발자는 컬렉션 기반 API를 사용할 때 더 편안하다고 합니다.

 그러나 하위 수준 API를 개발하는 경우에는 읽기/쓰기 시나리오에 배열을 사용하는 것이 더 좋을 수 있습니다. 배열은 메모리 공간이 더 작기 때문에 작업 세트를 줄일 수 있고, 배열의 요소에 대한 액세스가 런타임에서 최적화되기 때문에 더 빨라집니다.

 ✔️ 메모리 사용을 최소화하고 성능을 최대화하려면 하위 수준 API에서는 배열을 사용하는 것이 좋습니다.

 ✔️ 바이트 컬렉션 대신 바이트 배열을 사용하세요.

 ❌ 속성 getter가 호출될 때마다 속성이 새 배열(예: 내부 배열의 복사본)을 반환해야 하는 경우에는 속성에 배열을 사용하지 마세요.

## <a name="implementing-custom-collections"></a>사용자 지정 컬렉션 구현

 ✔️ 새 컬렉션을 설계할 때는 `Collection<T>`, `ReadOnlyCollection<T>` 또는 `KeyedCollection<TKey,TItem>`에서 상속하는 것이 좋습니다.

 ✔️ 새 컬렉션을 설계할 때 `IEnumerable<T>`을 구현하세요. 필요한 경우 `ICollection<T>` 또는 `IList<T>`를 구현하는 것이 좋습니다.

 이러한 사용자 지정 컬렉션을 구현하는 경우 `Collection<T>` 및 `ReadOnlyCollection<T>`에서 설정된 API 패턴을 최대한 비슷하게 따라야 합니다. 즉, 동일한 멤버를 명시적으로 구현하고, 이러한 두 컬렉션처럼 매개 변수의 이름을 지정하고, 해당 멤버의 이름을 지정하는 등입니다.

 ✔️ 이러한 인터페이스를 입력으로 사용하는 API에 컬렉션을 자주 전달하는 경우 제네릭이 아닌 컬렉션 인터페이스(`IList` 및 `ICollection`)를 구현하는 것이 좋습니다.

 ❌ 컬렉션의 개념과 관련이 없는 복잡한 API를 사용하여 형식에 컬렉션 인터페이스를 구현하면 안 됩니다.

 ❌ `CollectionBase`와 같은 제네릭이 아닌 기본 컬렉션에서 상속하지 마세요. 대신 `Collection<T>`, `ReadOnlyCollection<T>` 및 `KeyedCollection<TKey,TItem>`를 사용해야 합니다.

### <a name="naming-custom-collections"></a>사용자 지정 컬렉션 이름 지정

 컬렉션(`IEnumerable`을 구현하는 형식)을 만드는 두 가지 주요 이유는 (1) 구조 관련 작업이 있고 종종 기존 데이터 구조와 다른 성능 특성을 갖는 새 데이터 구조(예: <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>)를 만들고 (2) 특정 항목 세트(예: <xref:System.Collections.Specialized.StringCollection>)를 보유하는 특수 컬렉션을 만드는 것입니다. 데이터 구조는 애플리케이션 및 라이브러리의 내부 구현에서 주로 사용됩니다. 특수 컬렉션은 주로 API에서 속성 및 매개 변수 형식으로 노출됩니다.

 ✔️ `IDictionary` 또는 `IDictionary<TKey,TValue>`를 구현하는 추상화 이름에 “Dictionary” 접미사를 사용하세요.

 ✔️ `IEnumerable`(또는 해당 하위 항목)을 구현하고 항목 목록을 나타내는 형식 이름에 “Collection” 접미사를 사용하세요.

 ✔️ 사용자 지정 데이터 구조에 적합한 데이터 구조 이름을 사용하세요.

 ❌ 컬렉션 추상화 이름에 “LinkedList” 또는 “Hashtable” 같이 특정 구현을 의미하는 접미사를 사용하면 안 됩니다.

 ✔️ 항목 형식의 이름을 컬렉션 이름의 접두사로 사용하는 것이 좋습니다. 예를 들어 `Address`(`IEnumerable<Address>` 구현) 형식의 항목을 저장하는 컬렉션 이름은 `AddressCollection`으로 지정해야 합니다. 항목 형식이 인터페이스인 경우 항목 형식의 “I” 접두사는 생략할 수 있습니다. 따라서 <xref:System.IDisposable> 항목의 컬렉션을 `DisposableCollection`이라고 할 수 있습니다.

 ✔️ 해당되는 쓰기 가능 컬렉션을 추가할 수 있거나 해당 컬렉션이 프레임워크에 이미 있는 경우 읽기 전용 컬렉션의 이름에 “ReadOnly” 접두사를 사용하는 것이 좋습니다.

 예를 들어 문자열의 읽기 전용 컬렉션은 `ReadOnlyStringCollection`이라고 합니다.

 *Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [프레임워크 디자인 지침](index.md)
- [사용 지침](usage-guidelines.md)
