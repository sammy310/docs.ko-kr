---
title: 컬렉션에 대한 지침
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 50497de6569b448ab036af8a1fbf76a47565e2bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741869"
---
# <a name="guidelines-for-collections"></a>컬렉션에 대한 지침
몇 가지 공통적인 특징이 있는 개체 그룹을 조작 하도록 특별히 디자인 된 모든 형식은 컬렉션으로 간주할 수 있습니다. <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601>를 구현 하는 이러한 형식에는 거의 항상 적합 합니다. 따라서이 섹션에서는 이러한 인터페이스 중 하나 또는 둘 다를 구현 하는 형식만 컬렉션으로 간주 합니다.

 공용 Api에서 약하게 형식화 된 컬렉션을 사용 하지 ❌.

 컬렉션 항목을 나타내는 모든 반환 값 및 매개 변수의 형식은 기본 형식이 아닌 정확한 항목 형식 이어야 합니다 .이는 컬렉션의 public 멤버에만 적용 됩니다.

 ❌ 공용 Api에서 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.Generic.List%601>를 사용 하지 않습니다.

 이러한 형식은 공용 Api가 아닌 내부 구현에서 사용 하도록 디자인 된 데이터 구조입니다. `List<T>`는 Api 및 유연성의 정리 비용으로 성능 및 기능에 최적화 되어 있습니다. 예를 들어 `List<T>`반환 하는 경우 클라이언트 코드에서 컬렉션을 수정할 때 알림을 받을 수 없습니다. 또한 `List<T>`는 <xref:System.Collections.Generic.List%601.BinarySearch%2A>와 같이 많은 시나리오에서 유용 하지 않거나 적용 되지 않는 많은 멤버를 노출 합니다. 다음 두 섹션에서는 공용 Api에서 사용 하기 위해 특별히 설계 된 형식 (추상화)을 설명 합니다.

 ❌ 공용 Api에서 `Hashtable` 또는 `Dictionary<TKey,TValue>`를 사용 하지 않습니다.

 이러한 형식은 내부 구현에서 사용 하도록 디자인 된 데이터 구조입니다. 공용 Api는 인터페이스 중 하나 또는 둘 다를 구현 하는 <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`또는 사용자 지정 형식을 사용 해야 합니다.

 `GetEnumerator` 메서드의 반환 형식을 제외 하 고 이러한 인터페이스 중 하나를 구현 하는 <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>또는 다른 형식을 사용 하지 ❌.

 `GetEnumerator` 아닌 메서드에서 열거자를 반환 하는 형식은 `foreach` 문과 함께 사용할 수 없습니다.

 ❌는 `IEnumerator<T>`와 `IEnumerable<T>`을 동일한 형식으로 구현 하지 않습니다. `IEnumerator` 및 `IEnumerable`제네릭이 아닌 인터페이스에도 동일 하 게 적용 됩니다.

## <a name="collection-parameters"></a>컬렉션 매개 변수
 ✔️ 매개 변수 형식으로 사용할 수 있는 최소 특수화 된 형식을 사용 합니다. 컬렉션을 매개 변수로 사용 하는 대부분의 멤버는 `IEnumerable<T>` 인터페이스를 사용 합니다.

 ❌ <xref:System.Collections.Generic.ICollection%601> 또는 <xref:System.Collections.ICollection>를 매개 변수로 사용 하 여 `Count` 속성에 액세스 하지 않도록 합니다.

 대신 `IEnumerable<T>` 또는 `IEnumerable`를 사용 하 고 개체가 `ICollection<T>` 또는 `ICollection`를 구현 하는지 여부를 동적으로 확인 하는 것이 좋습니다.

## <a name="collection-properties-and-return-values"></a>컬렉션 속성 및 반환 값
 ❌ 설정할 수 있는 컬렉션 속성을 제공 하지 않습니다.

 사용자는 컬렉션을 먼저 지운 다음 새 내용을 추가 하 여 컬렉션의 콘텐츠를 바꿀 수 있습니다. 전체 컬렉션을 바꾸는 것이 일반적인 시나리오 인 경우 컬렉션에 `AddRange` 메서드를 제공 하는 것이 좋습니다.

 속성 또는 읽기/쓰기 컬렉션을 나타내는 반환 값에 대해 `Collection<T>`의 서브 클래스 또는 `Collection<T>`를 사용 ✔️ 합니다.

 `Collection<T>` 일부 요구 사항 (예: 컬렉션에서 <xref:System.Collections.IList>를 구현 하지 않아야 함)을 충족 하지 않는 경우 `IEnumerable<T>`, `ICollection<T>`또는 <xref:System.Collections.Generic.IList%601>을 구현 하 여 사용자 지정 컬렉션을 사용 합니다.

 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, `ReadOnlyCollection<T>`의 서브 클래스를 사용 하거나, 드문 경우 이지만 속성 또는 읽기 전용 컬렉션을 나타내는 값을 반환 하는 `IEnumerable<T>` 경우를 ✔️ 합니다.

 일반적으로 `ReadOnlyCollection<T>`를 사용 하는 것이 좋습니다. 일부 요구 사항 (예: 컬렉션에서 `IList`을 구현 하지 않아야 함)을 충족 하지 않는 경우 `IEnumerable<T>`, `ICollection<T>`또는 `IList<T>`를 구현 하 여 사용자 지정 컬렉션을 사용 합니다. 사용자 지정 읽기 전용 컬렉션을 구현 하는 경우 `true`을 반환 하 `ICollection<T>.IsReadOnly`를 구현 합니다.

 지원 하려는 시나리오가 앞 으로만 반복 되는 경우에만 `IEnumerable<T>`를 사용 하면 됩니다.

 컬렉션을 직접 사용 하는 대신 제네릭 기본 컬렉션의 서브 클래스를 사용 하는 것이 좋습니다 ✔️.

 이를 통해 더 나은 이름을 제공 하 고 기본 컬렉션 형식에 없는 도우미 멤버를 추가할 수 있습니다. 이는 특히 높은 수준의 Api에 적용 됩니다.

 ✔️ 일반적으로 사용 되는 메서드 및 속성에서 `Collection<T>` 또는 `ReadOnlyCollection<T>`의 서브 클래스를 반환 하는 것이 좋습니다.

 이를 통해 도우미 메서드를 추가 하거나 나중에 컬렉션 구현을 변경할 수 있습니다.

 컬렉션에 저장 된 항목에 고유 키 (이름, Id 등)가 있는 경우 키가 지정 된 컬렉션을 사용 하는 것이 좋습니다. ✔️ 키가 지정 된 컬렉션은 정수 및 키 둘 다로 인덱싱할 수 있는 컬렉션이 며 일반적으로 `KeyedCollection<TKey,TItem>`에서 상속 하 여 구현 됩니다.

 키 컬렉션은 일반적으로 더 큰 메모리 차지을 가지 며, 메모리 오버 헤드가 키가 있는 이점 보다 큰 경우에는 사용 하지 않아야 합니다.

 ❌ 컬렉션 속성 또는 컬렉션을 반환 하는 메서드에서 null 값을 반환 하지 않습니다. 대신 빈 컬렉션이 나 빈 배열을 반환 합니다.

 일반 규칙은 null 및 비어 있는 (0 개 항목) 컬렉션 또는 배열을 동일 하 게 처리 해야 한다는 것입니다.

### <a name="snapshots-versus-live-collections"></a>스냅숏과 라이브 컬렉션 비교
 특정 시점의 상태를 나타내는 컬렉션을 스냅숏 컬렉션 이라고 합니다. 예를 들어 데이터베이스 쿼리에서 반환 된 행을 포함 하는 컬렉션은 스냅숏이 됩니다. 항상 현재 상태를 나타내는 컬렉션을 라이브 컬렉션 이라고 합니다. 예를 들어 `ComboBox` 항목의 컬렉션은 라이브 컬렉션입니다.

 ❌는 속성에서 스냅숏 컬렉션을 반환 하지 않습니다. 속성은 라이브 컬렉션을 반환 해야 합니다.

 Getter 속성은 매우 간단한 작업 이어야 합니다. 스냅숏을 반환 하려면 O (n) 작업에서 내부 컬렉션의 복사본을 만들어야 합니다.

 ✔️는 스냅숏 컬렉션이 나 라이브 `IEnumerable<T>` (또는 해당 하위 형식)를 사용 하 여 휘발성 컬렉션을 나타냅니다. 즉, 컬렉션을 명시적으로 수정 하지 않고 변경할 수 있습니다.

 일반적으로 공유 리소스를 나타내는 모든 컬렉션 (예: 디렉터리의 파일)은 일시적입니다. 구현이 단순히 전방 전용 열거자 인 경우를 제외 하 고 이러한 컬렉션을 라이브 컬렉션으로 구현 하는 것은 매우 어렵거나 불가능 합니다.

## <a name="choosing-between-arrays-and-collections"></a>배열 및 컬렉션 중에서 선택
 ✔️ 배열에 대 한 컬렉션을 선호 합니다.

 컬렉션은 내용에 대 한 제어를 강화 하 고, 시간이 지남에 따라 진화 하 고, 더 사용할 수 있습니다. 또한 읽기 전용 시나리오에 배열을 사용 하지 않는 것이 좋습니다. 배열을 복제 하는 비용이 너무 높을 수 있기 때문입니다. 유용성 연구에서는 일부 개발자가 컬렉션 기반 Api를 사용 하는 것이 더 편안 하다는 것을 보여 줍니다.

 그러나 낮은 수준의 Api를 개발 하는 경우 읽기/쓰기 시나리오에 배열을 사용 하는 것이 더 좋을 수 있습니다. 배열의 메모리 공간이 작을수록 작업 집합을 줄이고 배열의 요소에 대 한 액세스는 런타임에 의해 최적화 되기 때문에 더 빠릅니다.

 메모리 사용을 최소화 하 고 성능을 최대화 하려면 하위 수준 Api의 배열을 사용 하는 것이 좋습니다. ✔️

 ✔️ 바이트 컬렉션 대신 바이트 배열을 사용 합니다.

 속성이 getter를 호출할 때마다 속성이 새 배열 (예: 내부 배열의 복사본)을 반환 해야 하는 경우 속성에 배열을 사용 하지 ❌.

## <a name="implementing-custom-collections"></a>사용자 지정 컬렉션 구현
 ✔️ 새 컬렉션을 디자인할 때 `Collection<T>`, `ReadOnlyCollection<T>`또는 `KeyedCollection<TKey,TItem>`에서 상속 하는 것이 좋습니다.

 새 컬렉션을 디자인할 때 `IEnumerable<T>` 구현 ✔️ 합니다. `ICollection<T>` 또는 `IList<T>`를 구현 하는 것이 좋습니다.

 이러한 사용자 지정 컬렉션을 구현 하는 경우 `Collection<T>`에 의해 설정 된 API 패턴을 따르고 최대한 긴밀 하 게 `ReadOnlyCollection<T>` 합니다. 즉, 동일한 멤버를 명시적으로 구현 하 고, 이러한 두 컬렉션과 같은 매개 변수의 이름을로 지정할 수 있습니다.

 이러한 인터페이스를 입력으로 사용할 때 컬렉션을 Api에 자주 전달 하는 경우 제네릭이 아닌 컬렉션 인터페이스 (`IList` 및 `ICollection`)를 구현 하는 것이 좋습니다. ✔️

 컬렉션의 개념과 관련이 없는 복잡 한 Api를 사용 하 여 형식에 컬렉션 인터페이스를 구현 하지 않도록 ❌ 합니다.

 ❌ `CollectionBase`와 같은 제네릭이 아닌 기본 컬렉션에서 상속 되지 않습니다. 대신 `Collection<T>`, `ReadOnlyCollection<T>`및 `KeyedCollection<TKey,TItem>`를 사용 해야 합니다.

### <a name="naming-custom-collections"></a>사용자 지정 컬렉션 이름 지정
 컬렉션 (`IEnumerable`을 구현 하는 형식)은 주로 (1) 구조 관련 작업을 포함 하는 새 데이터 구조를 만들고 기존 데이터 구조 (예: <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>)와 다른 성능 특성을 만들고 (2) 특정 항목 집합을 포함 하는 특수 한 컬렉션을 만드는 (예: <xref:System.Collections.Specialized.StringCollection>) 두 가지 이유로 생성 됩니다. 데이터 구조는 응용 프로그램 및 라이브러리의 내부 구현에서 주로 사용 됩니다. 특수 컬렉션은 주로 Api (속성 및 매개 변수 형식)로 노출 됩니다.

 ✔️ `IDictionary` 또는 `IDictionary<TKey,TValue>`를 구현 하는 추상화 이름에 "Dictionary" 접미사를 사용 합니다.

 ✔️ `IEnumerable` (또는 해당 하위 항목)를 구현 하 고 항목 목록을 나타내는 형식의 이름에 "Collection" 접미사를 사용 합니다.

 사용자 지정 데이터 구조에 적합 한 데이터 구조 이름을 사용 ✔️ 합니다.

 ❌ 컬렉션 추상화 이름에 "System.collections.generic.linkedlist" 또는 "Hashtable"와 같은 접미사의 특정 구현을 사용 하지 않는 것이 좋습니다.

 컬렉션 이름에 항목 형식의 이름을 접두사로 사용 하는 것이 좋습니다 ✔️. 예를 들어 `Address` 형식의 항목을 저장 하는 컬렉션 (`IEnumerable<Address>`구현)은 `AddressCollection`이름 이어야 합니다. 항목 형식이 인터페이스 이면 항목 형식의 "I" 접두사를 생략할 수 있습니다. 따라서 <xref:System.IDisposable> 항목의 컬렉션을 `DisposableCollection`호출할 수 있습니다.

 해당 하는 쓰기 가능한 컬렉션이 추가 될 수도 있고 프레임 워크에 이미 있는 경우 읽기 전용 컬렉션의 이름에 "ReadOnly" 접두사를 사용 하는 것이 좋습니다. ✔️

 예를 들어 `ReadOnlyStringCollection`읽기 전용 문자열 컬렉션을 호출 해야 합니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
- [사용 지침](../../../docs/standard/design-guidelines/usage-guidelines.md)
