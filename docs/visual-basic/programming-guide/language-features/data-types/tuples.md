---
title: Visual Basic의 튜플
ms.date: 04/23/2017
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
ms.openlocfilehash: fdca36e47d0b1234a8964d7475354a726a61f085
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524584"
---
# <a name="tuples-visual-basic"></a>튜플 (Visual Basic)

Visual Basic 2017부터 Visual Basic 언어는 튜플을 만들고 튜플 요소에 더 쉽게 액세스할 수 있도록 하는 튜플에 대 한 기본 제공 지원을 제공 합니다. 튜플은 값의 특정 개수와 시퀀스를 포함 하는 간단한 데이터 구조입니다. 튜플을 인스턴스화할 때 각 값 (또는 요소)의 숫자와 데이터 형식을 정의 합니다. 예를 들어 2 튜플 (또는 쌍)에는 두 개의 요소가 있습니다. 첫 번째 값은 `Boolean` 값이 고, 두 번째 값은 `String`입니다. 튜플을 사용 하면 여러 값을 단일 개체에 쉽게 저장할 수 있으므로 일반적으로 메서드에서 여러 값을 반환 하는 간단한 방법으로 사용 됩니다.

> [!IMPORTANT]
> 튜플 지원에는 <xref:System.ValueTuple> 형식이 필요 합니다. .NET Framework 4.7가 설치 되지 않은 경우 nuget 갤러리에서 사용할 수 있는 `System.ValueTuple` NuGet 패키지를 추가 해야 합니다. 이 패키지가 없으면 "미리 정의 된 유형 ' System.valuetuple (Of,,,) '이 (가) 정의 되지 않았거나 가져오지 않았습니다."와 유사한 컴파일 오류가 발생할 수 있습니다.

## <a name="instantiating-and-using-a-tuple"></a>튜플 인스턴스화 및 사용

쉼표로 구분 된 값 im 괄호를 포함 하 여 튜플을 인스턴스화합니다. 이러한 각 값은 튜플의 필드가 됩니다. 예를 들어 다음 코드는 첫 번째 값으로 `Date`를 사용 하 여 삼중 (또는 3 튜플)을 정의 하 고, `String` 두 번째 값으로, `Boolean`를 세 번째 값으로 정의 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

기본적으로 튜플의 각 필드 이름은 튜플의 필드의 1부터 시작 하는 위치와 함께 `Item` 문자열로 구성 됩니다. 이 3 튜플의 경우 `Date` 필드가 `Item1` 되 고 `String` 필드가 `Item2` 되며 `Boolean` 필드가 `Item3` 됩니다. 다음 예제에서는 이전 코드 줄에서 인스턴스화된 튜플의 필드 값을 표시 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Visual Basic 튜플의 필드는 읽기/쓰기입니다. 튜플을 인스턴스화한 후에는 해당 값을 수정할 수 있습니다. 다음 예제에서는 이전 예제에서 만든 튜플의 세 필드 중 두 개를 수정 하 고 결과를 표시 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>명명 된 튜플 인스턴스화 및 사용

튜플의 필드에 대해 기본 이름을 사용 하는 대신 튜플의 요소에 고유한 이름을 할당 하 여 *명명 된 튜플을* 인스턴스화할 수 있습니다. 그러면 지정 된 이름이 *나* 기본 이름으로 튜플의 필드에 액세스할 수 있습니다. 다음 예제에서는 첫 번째 필드 `EventDate`, 두 번째 `Name` 및 세 번째 `IsHoliday`의 이름을 명시적으로 지정할 때를 제외 하 고 이전 처럼 동일한 3 튜플을 인스턴스화합니다. 그런 다음 필드 값을 표시 하 고 수정 하 고 필드 값을 다시 표시 합니다.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>유추된 튜플 요소 이름

Visual Basic 15.3부터 Visual Basic 튜플 요소의 이름을 유추할 수 있습니다. 명시적으로 할당할 필요는 없습니다. 유추 된 튜플 이름은 변수 집합에서 튜플을 초기화 하 고 튜플 요소 이름이 변수 이름과 동일 하 게 하려는 경우에 유용 합니다.

다음 예에서는 명시적으로 명명 된 세 요소인 `state`, `stateName` 및 `capital`를 포함 하는 `stateInfo` 튜플을 만듭니다. 요소 이름을 지정 하는 경우 튜플 초기화 문은 명명 된 요소에 동일한 이름의 변수 값을 할당 하기만 하면 됩니다.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]

요소와 변수는 이름이 동일 하기 때문에 Visual Basic 컴파일러는 다음 예제와 같이 필드의 이름을 유추할 수 있습니다.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

유추 된 튜플 요소 이름을 사용 하려면 Visual Basic 프로젝트 (\* .vbproj) 파일에서 사용할 Visual Basic 컴파일러의 버전을 정의 해야 합니다.

```xml
<PropertyGroup>
  <LangVersion>15.3</LangVersion>
</PropertyGroup>
```

버전 번호는 15.3부터 시작 하는 Visual Basic 컴파일러의 모든 버전이 될 수 있습니다. 특정 컴파일러 버전을 하드 코딩 하는 대신 "최신"을 `LangVersion` 값으로 지정 하 여 시스템에 설치 된 Visual Basic 컴파일러의 최신 버전으로 컴파일할 수도 있습니다.

자세한 내용은 [Visual Basic 언어 버전 설정](../../../language-reference/configure-language-version.md)을 참조 하세요.

경우에 따라 Visual Basic 컴파일러는 후보 이름에서 튜플 요소 이름을 유추할 수 없으며 튜플 필드는 `Item1`, `Item2` 등의 기본 이름을 사용해 서만 참조할 수 있습니다. 여기에는 다음이 포함 됩니다.

- 후보 이름은 `Item3`, `Rest` 또는 `ToString`와 같은 튜플 멤버의 이름과 동일 합니다.

- 후보 이름이 튜플에 중복 됩니다.

필드 이름 유추가 실패 하면 Visual Basic는 컴파일러 오류를 생성 하지 않으며 런타임에 예외가 throw 되지 않습니다. 대신 `Item1` 및 `Item2`와 같이 미리 정의 된 이름으로 튜플 필드를 참조 해야 합니다.

## <a name="tuples-versus-structures"></a>튜플 및 구조체

Visual Basic 튜플은 **system.valuetuple** 제네릭 형식 중 하나의 인스턴스인 값 형식입니다. 예를 들어 이전 예제에서 정의 된 `holiday` 튜플은 <xref:System.ValueTuple%603> 구조체의 인스턴스입니다. 데이터에 대 한 간단한 컨테이너로 설계 되었습니다. 튜플은 여러 데이터 항목을 사용 하 여 개체를 쉽게 만들 수 있도록 하기 때문에 사용자 지정 구조에 포함 될 수 있는 일부 기능이 부족 합니다. 여기에는 다음이 포함됩니다.

- 사용자 지정 멤버. 튜플에 대해 고유한 속성, 메서드 또는 이벤트를 정의할 수 없습니다.

- 유효성 검사. 필드에 할당 된 데이터의 유효성을 검사할 수 없습니다.

- 불변성. Visual Basic 튜플을 변경할 수 있습니다. 반면, 사용자 지정 구조를 사용 하면 인스턴스를 변경할 수 있는지 여부를 제어할 수 있습니다.

사용자 지정 멤버, 속성 및 필드 유효성 검사 또는 불변성이 중요 한 경우에는 Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) 문을 사용 하 여 사용자 지정 값 형식을 정의 해야 합니다.

Visual Basic 튜플은 **system.valuetuple** 형식의 멤버를 상속 합니다. 이러한 필드 외에도 다음과 같은 메서드가 포함 됩니다.

| 멤버 | 설명 |
| ---|---|
| CompareTo | 현재 튜플을 동일한 수의 요소를 사용 하는 다른 튜플로 비교 합니다. |
| 같음 | 현재 튜플이 다른 튜플 또는 개체와 같은지 여부를 확인 합니다. |
| GetHashCode | 현재 인스턴스에 대 한 해시 코드를 계산 합니다. |
| ToString | @No__t_0 형식을 사용 하는이 튜플의 문자열 표현을 반환 합니다. 여기에서 `Item1` 및 `Item2` 튜플의 필드 값을 나타냅니다. |

또한 **system.valuetuple** 형식은 고객 비교자를 정의 하는 데 사용할 수 있는 <xref:System.Collections.IStructuralComparable> 및 <xref:System.Collections.IStructuralEquatable> 인터페이스를 구현 합니다.

## <a name="assignment-and-tuples"></a>할당 및 튜플

Visual Basic는 필드 수가 같은 튜플 형식 간의 할당을 지원 합니다. 다음 조건 중 하나에 해당 하는 경우 필드 형식을 변환할 수 있습니다.

- 원본 및 대상 필드의 형식이 동일 합니다.

- 원본 형식에서 대상 형식으로의 확대 또는 암시적 변환이 정의 됩니다.

- `Option Strict` `On` 되 고 소스 형식에서 대상 형식으로의 축소 또는 명시적 변환이 정의 됩니다. 소스 값이 대상 형식의 범위를 벗어나면이 변환에서 예외를 throw 할 수 있습니다.

다른 변환은 할당에 고려되지 않습니다. 튜플 형식 간에 허용되는 할당 종류를 살펴보겠습니다.

다음 예제에서 사용되는 이러한 변수를 살펴보세요.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

처음 두 변수 `unnamed` 및 `anonymous`에는 필드에 대해 제공 되는 의미 체계 이름이 없습니다. 필드 이름은 기본 `Item1` `Item2`입니다. 마지막 두 변수인 `named` 및 `differentName`에는 의미 체계 필드 이름이 있습니다. 이러한 두 튜플의 필드 이름은 서로 다릅니다.

이러한 튜플 중 4 개는 동일한 수의 필드 (' 인자 ' 라고 함)를 포함 하 고 이러한 필드의 형식은 동일 합니다. 따라서 다음 할당이 모든 작동합니다.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

튜플 이름은 할당되지 않습니다. 필드 값은 튜플의 필드 순서에 따라 할당됩니다.

마지막으로, `named`의 첫 번째 필드가 `Integer`이 고 `conversion`의 첫 번째 필드가 `Long` 이더라도 `named` 튜플을 `conversion` 튜플에 할당할 수 있습니다. 이 할당은 `Integer`를 `Long`으로 변환 하는 것이 확대 변환 이기 때문에 성공 합니다.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

필드 수가 다른 튜플은 할당할 수 없습니다.

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>메서드 반환 값으로의 튜플

메서드는 단일 값만 반환할 수 있습니다. 그러나 메서드를 호출 하 여 여러 값을 반환 하는 경우가 많습니다. 이 제한 사항을 해결 하는 데는 여러 가지 방법이 있습니다.

- 속성이 나 필드가 메서드에서 반환 된 값을 나타내는 사용자 지정 클래스 또는 구조체를 만들 수 있습니다. 따라서는 고중량 솔루션입니다. 메서드 호출에서 값을 검색 하는 용도로만 사용 되는 사용자 지정 형식을 정의 해야 합니다.

- 메서드에서 단일 값을 반환 하 고, 메서드에 대 한 참조로 전달 하 여 나머지 값을 반환할 수 있습니다. 여기에는 변수를 인스턴스화하는 오버 헤드가 발생 하며 실수로 참조로 전달 하는 변수의 값을 덮어쓰는 위험이 포함 됩니다.

- 여러 반환 값을 검색 하는 간단한 솔루션을 제공 하는 튜플을 사용할 수 있습니다.

예를 들어 .NET의 **TryParse** 메서드는 구문 분석 작업이 성공 했는지 여부를 나타내는 `Boolean` 값을 반환 합니다. 구문 분석 작업의 결과는 메서드에 대 한 참조로 전달 된 변수에 반환 됩니다. 일반적으로 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>와 같은 구문 분석 메서드를 호출 하는 것은 다음과 같습니다.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

사용자의 메서드에서 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드에 대 한 호출을 래핑하는 경우 구문 분석 작업에서 튜플을 반환할 수 있습니다. 다음 예제에서 `NumericLibrary.ParseInteger`은 <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> 메서드를 호출 하 고 두 개의 요소가 포함 된 명명 된 튜플을 반환 합니다.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

그런 다음 다음과 같은 코드를 사용 하 여 메서드를 호출할 수 있습니다.

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>.NET Framework에서 튜플 및 튜플 Visual Basic

Visual Basic 튜플은 .NET Framework 4.7에 도입 된 **system.valuetuple** 제네릭 형식 중 하나의 인스턴스입니다. 또한 .NET Framework에 **는 제네릭 system.string** 클래스 집합이 포함 되어 있습니다. 그러나 이러한 클래스는 Visual Basic 튜플 및 여러 가지 방법으로 **system.valuetuple** 제네릭 형식과 다릅니다.

- **튜플** 클래스의 요소는 `Item1`, `Item2` 등과 같은 속성입니다. Visual Basic 튜플 및 **system.valuetuple** 형식에서 튜플 요소는 필드입니다.

- **튜플** 인스턴스 또는 **system.valuetuple** 인스턴스의 요소에 의미 있는 이름을 할당할 수 없습니다. Visual Basic를 사용 하 여 필드의 의미를 전달 하는 이름을 할당할 수 있습니다.

- **튜플** 인스턴스의 속성은 읽기 전용입니다. 튜플을 변경할 수 없습니다. Visual Basic 튜플 및 **system.valuetuple** 형식에서 튜플 필드는 읽기/쓰기입니다. 튜플을 변경할 수 있습니다.

- 제네릭 **튜플** 형식은 참조 형식입니다. 이러한 **튜플** 형식을 사용 하면 개체 할당을 의미 합니다. 실행 부하 과다 경로에서는 이로 인해 애플리케이션 성능이 크게 영향을 받을 수 있습니다. Visual Basic 튜플 및 **system.valuetuple** 형식은 값 형식입니다.

@No__t_0 클래스의 확장 메서드를 사용 하면 Visual Basic 튜플 및 .NET **튜플** 개체 간에 쉽게 변환할 수 있습니다. **Totuple** 메서드는 Visual Basic 튜플을 .net **튜플** 개체로 변환 하 고, **ToValueTuple** 메서드는 .net **튜플** 개체를 Visual Basic 튜플로 변환 합니다.

다음 예제에서는 튜플을 만들고 .NET **튜플** 개체로 변환한 다음 다시 Visual Basic 튜플로 변환 합니다. 그런 다음이 튜플을 원래 튜플과 비교 하 여 동일한 지 확인 합니다.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>참조

- [Visual Basic 언어 참조](index.md)
