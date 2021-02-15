---
description: '자세한 정보: 매개 변수 디자인'
title: 매개 변수 디자인
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines [.NET Framework], parameters
- members [.NET Framework], parameters
- names [.NET Framework], parameters
- parameters, design guidelines
- reserved parameters
ms.assetid: 3f33bf46-4a7b-43b3-bb78-1ffebe0dcfa6
ms.openlocfilehash: 9663ef8146054985374fdb3e2974fcd996fd1402
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731827"
---
# <a name="parameter-design"></a>매개 변수 디자인

이 섹션에서는 인수 확인 지침이 포함된 섹션을 포함하여 매개 변수 디자인에 대한 광범위한 지침을 제공합니다. 또한 [매개 변수 이름 지정](naming-parameters.md)에 설명된 지침도 참조해야 합니다.

 ✔️ 멤버에 필요한 기능을 제공하는 최소 파생 매개 변수 형식을 사용하세요.

 예를 들어 컬렉션을 열거하고 각 항목을 콘솔에 출력하는 메서드를 디자인하려는 경우를 가정해 보겠습니다. 이러한 메서드는 <xref:System.Collections.ArrayList> 또는 <xref:System.Collections.IList>가 아닌 <xref:System.Collections.IEnumerable>을 매개 변수로 사용해야 합니다.

 ❌ 예약된 매개 변수를 사용하지 마세요.

 일부 이후 버전에서 멤버에 대한 추가 입력이 필요한 경우 새 오버로드를 추가할 수 있습니다.

 ❌ 포인터, 포인터 배열 또는 다차원 배열을 매개 변수로 사용하는 공개적으로 노출된 메서드가 없도록 하세요.

 포인터 및 다차원 배열은 제대로 사용하기가 비교적 어렵습니다. 거의 모든 경우에 API는 이러한 형식을 매개 변수로 사용하지 않도록 다시 디자인할 수 있습니다.

 ✔️ 오버로드([멤버 오버로드](member-overloading.md) 참조) 간에 매개 변수 순서가 일치하지 않게 되더라도 모든 by-value 및 `ref` 매개 변수(매개 변수 배열 제외) 다음에 모든 `out` 매개 변수를 배치하세요.

 `out` 매개 변수는 추가 반환 값으로 확인할 수 있으며, 이러한 매개 변수를 그룹화하면 메서드 시그니처를 더 쉽게 이해할 수 있습니다.

 ✔️ 멤버를 재정의하거나 인터페이스 멤버를 구현할 때 매개 변수 이름을 일관되게 지정하세요.

 그러면 메서드 간의 관계가 더 잘 전달됩니다.

### <a name="choosing-between-enum-and-boolean-parameters"></a>열거형 및 부울 매개 변수 중에서 선택  

 ✔️ 멤버에 둘 이상의 부울 매개 변수가 있는 경우 열거형을 사용하세요.

 ❌ 셋 이상의 값이 필요하지 않다고 확신할 수 있는 경우에만 부울을 사용하세요.

 열거형을 사용하면 나중에 값을 추가할 수 있지만 열거형에 값을 추가할 경우 미칠 수 있는 모든 영향을 알고 있어야 합니다. 자세한 내용은 [열거형 디자인](enum.md)에 설명되어 있습니다.

 ✔️ 실제로 두 가지 상태 값이며 부울 속성을 초기화하는 데만 사용되는 생성자 매개 변수에는 부울을 사용하는 것이 좋습니다.

### <a name="validating-arguments"></a>인수 유효성 검사

 ✔️ 퍼블릭 멤버, 보호된 멤버 또는 명시적으로 구현된 멤버에 전달된 인수의 유효성을 검사하세요. 유효성 검사가 실패하는 경우 <xref:System.ArgumentException?displayProperty=nameWithType> 또는 해당 서브클래스 중 하나가 throw됩니다.

 퍼블릭 또는 보호된 멤버 자체에서 실제 유효성 검사가 수행될 필요는 없습니다. 일부 프라이빗 또는 내부 루틴의 하위 수준에서 수행될 수 있습니다. 중요한 점은 최종 사용자에게 노출되는 전체 노출 영역에서 인수를 확인한다는 점입니다.

 ✔️ null 인수가 전달된 경우 멤버에서 null 인수를 지원하지 않으면 <xref:System.ArgumentNullException>을 throw하세요.

 ✔️ 열거형 매개 변수의 유효성을 검사하세요.

 열거형 인수가 열거형에 의해 정의된 범위 내에 있다고 가정하지 마세요. CLR에서는 값이 열거형에 정의되지 않은 경우에도 정수 값을 열거형 값으로 캐스팅할 수 있습니다.

 ❌ 열거형 범위 확인에 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType>를 사용하지 마세요.

 ✔️ 변경 가능한 인수는 유효성이 검사된 후 변경될 수 있음을 인식해야 합니다.

 보안이 중요한 멤버인 경우 복사본을 만든 다음 인수의 유효성을 검사하고 처리하는 것이 좋습니다.

### <a name="parameter-passing"></a>매개 변수 전달

 프레임워크 디자이너의 관점에서 by-value 매개 변수, `ref` 매개 변수, `out` 매개 변수의 세 가지 기본 매개 변수 그룹이 있습니다.

 by-value 매개 변수를 통해 인수를 전달하면 멤버는 전달된 실제 인수의 복사본을 받습니다. 인수가 값 형식인 경우 인수의 복사본이 스택에 배치됩니다. 인수가 참조 형식이면 참조의 복사본이 스택에 배치됩니다. C#, VB.NET, C++ 등 가장 널리 사용되는 CLR 언어는 기본적으로 매개 변수를 값으로 전달합니다.

 `ref` 매개 변수를 통해 인수를 전달하면 멤버는 전달된 실제 인수에 대한 참조를 받습니다. 인수가 값 형식인 경우 인수에 대한 참조가 스택에 배치됩니다. 인수가 참조 형식이면 참조에 대한 참조가 스택에 배치됩니다. `Ref` 매개 변수를 사용하면 호출자가 전달한 인수를 멤버가 수정할 수 있습니다.

 `Out` 매개 변수는 `ref` 매개 변수와 유사하며, 약간의 차이가 있습니다. 처음에 이 매개 변수는 할당되지 않은 것으로 간주되며, 일부 값이 할당된 다음에야 멤버 본문에서 읽을 수 있습니다. 또한 멤버에서 반환하기 전에 일부 값을 매개 변수에 할당해야 합니다.

 ❌ `out` 또는 `ref` 매개 변수를 사용하면 안 됩니다.

 `out` 또는 `ref` 매개 변수를 사용하려면 포인터 사용 방법을 알고 있어야 하고, 값 형식과 참조 형식이 어떻게 다른지 알고 있어야 하며, 반환 값이 여러 개인 메서드를 처리할 수 있어야 합니다. 또한 `out` 매개 변수와 `ref` 매개 변수의 차이점은 잘 알려져 있지 않습니다. 일반 사용자를 대상으로 디자인하는 프레임워크 설계자는 사용자가 `out` 또는 `ref` 매개 변수를 사용하는 작업에 능숙할 것이라고 기대해서는 안 됩니다.

 ❌ 참조로 참조 형식을 전달하지 마세요.

 참조를 교환하는 데 사용할 수 있는 메서드와 같이 규칙에는 몇 가지 제한된 예외가 있습니다.

### <a name="members-with-variable-number-of-parameters"></a>매개 변수 개수가 가변적인 멤버

 가변적인 개수의 인수를 사용하는 멤버는 배열 매개 변수를 제공하여 표현됩니다. 예를 들어 <xref:System.String>은 다음과 같은 메서드를 제공합니다.

```csharp
public class String {
    public static string Format(string format, object[] parameters);
}
```

 사용자는 다음과 같이 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드를 호출할 수 있습니다.

 `String.Format("File {0} not found in {1}",new object[]{filename,directory});`

 C# params 키워드를 배열 매개 변수에 추가하면 매개 변수가 소위 params 배열 매개 변수로 변경되고 임시 배열을 만드는 바로 가기를 제공합니다.

```csharp
public class String {
    public static string Format(string format, params object[] parameters);
}
```

 이렇게 하면 사용자가 인수 목록에서 직접 배열 요소를 전달하여 메서드를 호출할 수 있습니다.

 `String.Format("File {0} not found in {1}",filename,directory);`

 params 키워드는 매개 변수 목록의 마지막 매개 변수에만 추가할 수 있습니다.

 ✔️ 최종 사용자가 적은 수의 요소로 배열을 전달할 것으로 예상되는 경우 배열 매개 변수에 params 키워드를 추가하는 것이 좋습니다. 일반적인 시나리오에서 많은 요소가 전달될 것으로 예상되는 경우 사용자는 이러한 요소를 인라인으로 전달할 수 없으므로 params 키워드가 필요하지 않습니다.

 ❌ 호출자가 거의 항상 배열에 미리 입력하는 경우에는 params 배열을 사용하면 안 됩니다.

 예를 들어 바이트 배열 매개 변수를 사용하는 멤버는 개별 바이트를 전달하여 거의 호출되지 않습니다. 따라서 .NET Framework의 바이트 배열 매개 변수는 params 키워드를 사용하지 않습니다.

 ❌ 배열이 params 배열 매개 변수를 사용하는 멤버에 의해 수정되는 경우 params 배열을 사용하지 마세요.

 대부분의 컴파일러는 멤버에 대한 인수를 호출 사이트에서 임시 배열로 변환하기 때문에 배열이 임시 개체가 되어 배열에 대한 수정 내용이 손실됩니다.

 ✔️ 더 복잡한 오버로드에서 사용할 수 없는 경우 간단한 오버로드에서 params 키워드를 사용하는 것이 좋습니다.

 모든 오버로드에 포함되지 않은 경우에도 사용자가 하나의 오버로드에 params 배열을 포함하고 있는지 확인하세요.

 ✔️ params 키워드를 사용할 수 있도록 매개 변수의 순서를 지정하세요.

 ✔️ 성능이 매우 중요한 API에서는 적은 수의 인수를 사용하는 호출에 대해 특별한 오버로드 및 코드 경로를 제공하는 것이 좋습니다.

 그러면 적은 수의 인수를 사용하여 API를 호출할 때 배열 개체가 생성되지 않도록 할 수 있습니다. 단수 형태의 배열 매개 변수를 사용하고 숫자 접미사를 추가하여 매개 변수의 이름을 구성합니다.

 배열을 만들고 더욱 일반적인 메서드를 호출하는 것만이 아니라 전체 코드 경로를 특별히 처리하려는 경우에만 이 작업을 수행해야 합니다.

 ✔️ params 배열 인수로 null을 전달할 수 있음을 인식하세요.

 처리하기 전에 배열이 null이 아닌지 확인해야 합니다.

 ❌ 줄임표로도 알려져 있는 `varargs` 메서드를 사용하지 마세요.

 C++과 같은 일부 CLR 언어에서는 `varargs` 메서드라는 변수 매개 변수 목록을 전달하는 대체 규칙을 지원합니다. 규칙은 CLS 규격이 아니기 때문에 프레임워크에서 사용해서는 안 됩니다.

### <a name="pointer-parameters"></a>포인터 매개 변수

 일반적으로 포인터는 잘 디자인된 관리 코드 프레임워크의 퍼블릭 노출 영역에 표시되면 안 됩니다. 대부분의 경우 포인터를 캡슐화해야 합니다. 그러나 상호 운용성을 위해 포인터가 필요한 경우가 있으며 이런 경우 포인터를 사용하기에 적합합니다.

 ✔️ 포인터는 CLS 규격이 아니므로 포인터 인수를 사용하는 모든 멤버의 대안을 제공하세요.

 ❌ 포인터 인수에 대해서는 비용이 많이 드는 인수 확인을 수행하면 안 됩니다.

 ✔️ 포인터를 사용하여 멤버를 디자인할 때는 일반적인 포인터 관련 규칙을 따르세요.

 예를 들어 간단한 포인터 산술을 사용하여 동일한 결과를 얻을 수 있으므로 시작 인덱스를 전달할 필요가 없습니다.

 *Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*

 *Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*

## <a name="see-also"></a>참고 항목

- [멤버 디자인 지침](member.md)
- [프레임워크 디자인 지침](index.md)
