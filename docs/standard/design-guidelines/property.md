---
title: 속성 디자인
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 8b6570b1b7c292729b78f2fe52f24f73319efe6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743663"
---
# <a name="property-design"></a>속성 디자인
속성은 기술적으로 메서드와 매우 유사 하지만 사용 시나리오 측면에서 상당히 다릅니다. 스마트 필드로 표시 되어야 합니다. 여기에는 필드의 호출 구문과 메서드의 유연성이 있습니다.

 호출자가 속성의 값을 변경할 수 없어야 하는 경우에는 get 전용 속성을 만드는 ✔️ 합니다.

 속성의 형식이 변경 가능한 참조 형식이 면 속성이 get 전용 이더라도 속성 값을 변경할 수 있습니다.

 ❌에는 getter 보다 더 광범위 한 액세스 가능성이 있는 setter를 사용 하 여 설정 전용 속성 또는 속성을 제공 하지 않습니다.

 예를 들어 public setter와 protected getter에는 속성을 사용 하지 마십시오.

 Getter 속성을 제공할 수 없는 경우 대신 기능을 메서드로 구현 합니다. `Set`으로 메서드 이름을 시작 하 고 속성의 이름을 지정 하는 것이 좋습니다. 예를 들어 <xref:System.AppDomain>에는 `CachePath`라는 집합 전용 속성이 아닌 `SetCachePath` 라는 메서드가 있습니다.

 모든 속성에 대해 적절 한 기본값을 제공 하 여 기본값이 보안 구멍이 나 매우 비효율적인 코드를 생성 하지 않도록 합니다. ✔️

 이로 인해 개체가 일시적으로 유효 하지 않은 상태가 되는 경우에도 모든 순서로 속성을 설정할 수 ✔️.

 동일한 개체의 다른 속성 값을 지정 하 여 한 속성의 일부 값이 유효 하지 않을 수 있는 지점과 두 개 이상의 속성을 상호 관련 시킬 수 있는 것이 일반적입니다. 이러한 경우 유효 하지 않은 상태로 인해 발생 하는 예외는 상호 관련 된 속성이 실제로 개체에서 함께 사용 될 때까지 연기 되어야 합니다.

 속성 setter가 예외를 throw 하는 경우 이전 값을 유지 ✔️.

 ❌ 속성 getter에서 예외가 throw 되지 않도록 합니다.

 Getter 속성은 단순 작업 이어야 하며 사전 조건이 없어야 합니다. Getter가 예외를 throw 할 수 있는 경우에는 메서드로 다시 디자인 해야 합니다. 이 규칙은 인수 유효성 검사의 결과로 예외가 발생할 것으로 간주 되는 인덱서에는 적용 되지 않습니다.

### <a name="indexed-property-design"></a>인덱싱된 속성 디자인
 인덱싱된 속성은 매개 변수를 가질 수 있으며 배열 인덱싱과 유사한 특수 구문을 사용 하 여 호출할 수 있는 특수 속성입니다.

 인덱싱된 속성을 일반적으로 인덱서 라고 합니다. 인덱서는 논리적 컬렉션의 항목에 대 한 액세스를 제공 하는 Api 에서만 사용 해야 합니다. 예를 들어 문자열은 문자 컬렉션 이며, <xref:System.String?displayProperty=nameWithType>의 인덱서는 문자를 액세스 하기 위해 추가 되었습니다.

 ✔️ 인덱서를 사용 하 여 내부 배열에 저장 된 데이터에 대 한 액세스를 제공 하는 것이 좋습니다.

 항목의 컬렉션을 나타내는 형식에 인덱서를 제공 하는 것이 좋습니다 ✔️.

 ❌ 둘 이상의 매개 변수를 사용 하 여 인덱싱된 속성을 사용 하지 않습니다.

 디자인에 여러 매개 변수가 필요한 경우 속성이 실질적으로 논리적 컬렉션에 대 한 접근자를 나타내는지 여부를 고려해 야 합니다. 그렇지 않은 경우 메서드를 대신 사용 합니다. `Get` 또는 `Set`를 사용 하 여 메서드 이름을 시작 하는 것이 좋습니다.

 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Int64?displayProperty=nameWithType>, <xref:System.String?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>또는 열거형이 아닌 매개 변수 형식이 있는 인덱서를 사용 하지 ❌ 합니다.

 디자인에서 다른 형식의 매개 변수를 요구 하는 경우 API가 실질적으로 논리적 컬렉션에 대 한 접근자를 나타내는지 여부를 강력 하 게 다시 평가 합니다. 그렇지 않은 경우 메서드를 사용 합니다. `Get` 또는 `Set`를 사용 하 여 메서드 이름을 시작 하는 것이 좋습니다.

 분명히 좋은 이름이 없으면 (예: `System.String`에서 <xref:System.String.Chars%2A> 속성을 참조 하는 경우) 인덱싱된 속성에 대해 이름 `Item`를 사용 ✔️ 합니다.

 에서 C#인덱서는 기본적으로 명명 된 항목입니다. <xref:System.Runtime.CompilerServices.IndexerNameAttribute>를 사용 하 여이 이름을 사용자 지정할 수 있습니다.

 ❌은 의미상 동일한 인덱서와 메서드를 모두 제공 하지 않습니다.

 한 형식에서 오버 로드 된 인덱서의 패밀리를 두 개 이상 제공 하지 ❌.

 이는 컴파일러에 C# 의해 적용 됩니다.

 ❌ 기본이 아닌 인덱싱된 속성을 사용 하지 않습니다.

 이는 컴파일러에 C# 의해 적용 됩니다.

### <a name="property-change-notification-events"></a>속성 변경 알림 이벤트
 속성 값의 변경 내용을 사용자에 게 알리는 이벤트를 제공 하는 것이 유용한 경우도 있습니다. 예를 들어 `System.Windows.Forms.Control`는 `Text` 속성 값이 변경 된 후 `TextChanged` 이벤트를 발생 시킵니다.

 상위 수준 Api (일반적으로 디자이너 구성 요소)의 속성 값이 수정 될 때 변경 알림 이벤트를 발생 시키는 것이 좋습니다. ✔️

 사용자가 개체의 속성을 변경 하는 시기를 알아야 하는 경우 개체는 속성에 대 한 변경 알림 이벤트를 발생 시켜야 합니다.

 그러나 기본 형식 또는 컬렉션과 같은 하위 수준 Api에 대해서는 이러한 이벤트를 발생 시킬 필요가 없습니다. 예를 들어 새 항목이 목록에 추가 되 고 `Count` 속성이 변경 될 때 <xref:System.Collections.Generic.List%601>는 이러한 이벤트를 발생 시 키 지 않습니다.

 ✔️ 속성 값이 외부를 통해 변경 되는 경우 변경 알림 이벤트를 발생 시키는 것이 좋습니다.

 개체에서 메서드를 호출 하는 것 이외의 방식으로 일부 외부 force를 통해 속성 값이 변경 되 면 이벤트 발생은 값이 변경 되 고 변경 되었음을 개발자에 게 표시 합니다. 텍스트 상자 컨트롤의 `Text` 속성은 좋은 예입니다. 사용자가 `TextBox`텍스트를 입력 하면 속성 값이 자동으로 변경 됩니다.

 *2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참조

- [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)
- [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
