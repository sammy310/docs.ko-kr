---
title: Enum 문
ms.date: 07/20/2015
f1_keywords:
- vb.Enum
helpviewer_keywords:
- enumerated constants [Visual Basic]
- Enum statement [Visual Basic]
- Private keyword [Visual Basic], Enum statements
- Public keyword [Visual Basic], in Enum statement
- variables [Visual Basic], enumeration
- constants [Visual Basic], enumerated
ms.assetid: a45e51f1-65ff-48e1-bf32-79130f137377
ms.openlocfilehash: 48220fd1e88cf38e67db5dd3a2ad90638eb6b6df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343708"
---
# <a name="enum-statement-visual-basic"></a>Enum 문(Visual Basic)

열거형을 선언 하 고 해당 멤버의 값을 정의 합니다.

## <a name="syntax"></a>구문

```vb
[ <attributelist> ] [ accessmodifier ]  [ Shadows ]
Enum enumerationname [ As datatype ]
   memberlist
End Enum
```

## <a name="parts"></a>요소

- `attributelist`

  (선택 사항) 이 열거형에 적용 되는 특성의 목록입니다. [특성 목록을](../../../visual-basic/language-reference/statements/attribute-list.md) 꺾쇠 괄호 ("`<`" 및 "`>`")로 묶어야 합니다.

  <xref:System.FlagsAttribute> 특성은 열거형의 인스턴스 값에 여러 열거형 멤버가 포함 될 수 있고 각 멤버가 열거형 값의 비트 필드를 나타내는지 여부를 나타냅니다.

- `accessmodifier`

  (선택 사항) 이 열거형에 액세스할 수 있는 코드를 지정 합니다. 다음 중 하나일 수 있습니다.

  - [Public](../../../visual-basic/language-reference/modifiers/public.md)

  - [Protected](../../../visual-basic/language-reference/modifiers/protected.md)

  - [Friend](../../../visual-basic/language-reference/modifiers/friend.md)

  - [Private](../../../visual-basic/language-reference/modifiers/private.md)

  - [Protected Friend](../../language-reference/modifiers/protected-friend.md)

  - [Private Protected](../../language-reference/modifiers/private-protected.md)

- `Shadows`

  (선택 사항) 이 열거형이 기본 클래스에서 동일 하 게 명명 된 프로그래밍 요소 또는 오버 로드 된 요소 집합을 요소가 하 고 숨기도록 지정 합니다. 열거형은 해당 멤버가 아니라 열거형 자체 [에서만 지정할 수](../../../visual-basic/language-reference/modifiers/shadows.md) 있습니다.

- `enumerationname`

  필수입니다. 열거형의 이름입니다. 올바른 이름에 대 한 자세한 내용은 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조 하세요.

- `datatype`

  (선택 사항) 열거형 및 모든 해당 멤버의 데이터 형식입니다.

- `memberlist`

  필수입니다. 이 문에서 선언 되는 멤버 상수 목록입니다. 개별 소스 코드 줄에 여러 멤버가 표시 됩니다.

  각 `member`에는 다음과 같은 구문과 파트가 있습니다. `[<attribute list>] member name [ = initializer ]`

  |파트|설명|
  |---|---|
  |`membername`|필수입니다. 이 멤버의 이름입니다.|
  |`initializer`|(선택 사항) 컴파일 시간에 평가 되 고이 멤버에 할당 되는 식입니다.|

- `End` `Enum`

  `Enum` 블록을 종료합니다.

## <a name="remarks"></a>주의

논리적으로 서로 관련 된 변경 되지 않은 값 집합이 있는 경우 열거형에서 함께 정의할 수 있습니다. 이는 열거형 및 해당 멤버에 대 한 의미 있는 이름을 제공 하며, 값 보다 쉽게 기억할 수 있습니다. 그런 다음 코드의 여러 위치에서 열거형 멤버를 사용할 수 있습니다.

열거를 사용 하는 이점은 다음과 같습니다.

- 바꾸려면 또는 잘못 된 숫자로 인 한 오류를 줄입니다.

- 를 사용 하면 나중에 값을 쉽게 변경할 수 있습니다.

- 코드를 더 쉽게 읽을 수 있습니다. 즉, 오류가 발생할 가능성이 낮습니다.

- 이전 버전과의 호환성을 보장 합니다. 열거를 사용 하는 경우 나중에 누군가가 멤버 이름에 해당 하는 값을 변경 하면 코드가 실패할 가능성이 낮아집니다.

열거형에는 이름, 기본 데이터 형식 및 멤버 집합이 있습니다. 각 멤버는 상수를 나타냅니다.

프로시저 외부의 클래스, 구조체, 모듈 또는 인터페이스 수준에서 선언 된 열거형은 *멤버 열거형*입니다. 선언 하는 클래스, 구조체, 모듈 또는 인터페이스의 멤버입니다.

멤버 열거형은 클래스, 구조체, 모듈 또는 인터페이스 내의 어디에서 나 액세스할 수 있습니다. 클래스, 구조체 또는 모듈 외부의 코드는 해당 클래스, 구조체 또는 모듈의 이름을 사용 하 여 멤버 열거형의 이름을 한정 해야 합니다. 소스 파일에 [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 문을 추가 하 여 정규화 된 이름을 사용 하지 않아도 되는 것을 방지할 수 있습니다.

모든 클래스, 구조체, 모듈 또는 인터페이스 외부에서 네임 스페이스 수준에 선언 된 열거형은 해당 열거형이 표시 되는 네임 스페이스의 멤버입니다.

열거형의 *선언 컨텍스트* 는 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스 여야 하며 프로시저 일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.

특성을 열거형 전체에 적용할 수 있지만 해당 멤버를 개별적으로 적용할 수는 없습니다. 특성은 어셈블리의 메타 데이터에 정보를 제공 합니다.

## <a name="data-type"></a>데이터 형식

`Enum` 문은 열거형의 데이터 형식을 선언할 수 있습니다. 각 멤버는 열거형의 데이터 형식을 사용 합니다. `Byte`, `Integer`, `Long`, `SByte`, `Short`, `UInteger`, `ULong`또는 `UShort`지정할 수 있습니다.

열거형에 `datatype` 지정 하지 않으면 각 멤버가 해당 `initializer`의 데이터 형식을 사용 합니다. `datatype`와 `initializer`를 모두 지정 하는 경우 `initializer`의 데이터 형식을 `datatype`로 변환할 수 있어야 합니다. `datatype` 또는 `initializer` 모두 없는 경우에는 데이터 형식이 기본적으로 `Integer`됩니다.

## <a name="initializing-members"></a>멤버 초기화

`Enum` 문은 `memberlist`에서 선택 된 멤버의 콘텐츠를 초기화할 수 있습니다. `initializer`를 사용 하 여 멤버에 할당할 식을 제공 합니다.

멤버에 대 한 `initializer` 지정 하지 않으면 Visual Basic는 0 (`memberlist`의 첫 번째 `member`)으로 초기화 하거나 바로 앞의 `member`보다 큰 값으로 초기화 합니다.

각 `initializer`에 제공 되는 식은 리터럴, 이미 정의 된 다른 상수 및이 열거형의 이전 멤버를 포함 하 여 이미 정의 된 열거형 멤버의 조합일 수 있습니다. 산술 연산자와 논리 연산자를 사용 하 여 이러한 요소를 결합할 수 있습니다.

`initializer`변수나 함수는 사용할 수 없습니다. 그러나 `CByte` 및 `CShort`와 같은 변환 키워드를 사용할 수 있습니다. 상수 `String` 또는 `Char` 인수를 사용 하 여 호출 하는 경우 컴파일 시간에 계산할 수 있기 때문에 `AscW`를 사용할 수도 있습니다.

열거형에는 부동 소수점 값을 사용할 수 없습니다. 멤버에 부동 소수점 값이 할당 되 고 `Option Strict`가 on으로 설정 된 경우 컴파일러 오류가 발생 합니다. `Option Strict` 해제 되어 있으면 값이 자동으로 `Enum` 형식으로 변환 됩니다.

멤버의 값이 기본 데이터 형식에 대해 허용 가능한 범위를 초과 하거나 멤버를 기본 데이터 형식에서 허용 하는 최대 값으로 초기화 하는 경우 컴파일러에서 오류를 보고 합니다.

## <a name="modifiers"></a>한정자

클래스, 구조체, 모듈 및 인터페이스 멤버 열거형은 기본적으로 공용 액세스로 사용 됩니다. 액세스 한정자를 사용 하 여 액세스 수준을 조정할 수 있습니다. 네임 스페이스 멤버 열거형은 기본적으로 friend 액세스를 사용 합니다. 액세스 수준을 공용으로 조정할 수 있지만 비공개 또는 protected로는 조정할 수 없습니다. 자세한 내용은 [Visual Basic의 액세스 수준](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.

모든 열거형 멤버는 공용 액세스 권한을 가지 며 액세스 한정자를 사용할 수 없습니다. 그러나 열거 자체의 액세스 수준이 더 제한적인 경우에는 지정 된 열거형 액세스 수준이 우선 적용 됩니다.

기본적으로 모든 열거형은 형식이 고 해당 필드는 상수입니다. 따라서 열거형 또는 해당 멤버를 선언 하는 경우 `Shared`, `Static`및 `ReadOnly` 키워드를 사용할 수 없습니다.

## <a name="assigning-multiple-values"></a>다중 값 할당

열거형은 일반적으로 상호 배타적인 값을 나타냅니다. `Enum` 선언에 <xref:System.FlagsAttribute> 특성을 포함 하 여 대신 열거형의 인스턴스에 여러 값을 할당할 수 있습니다. <xref:System.FlagsAttribute> 특성은 열거형을 비트 필드 즉, 플래그 집합으로 처리 하도록 지정 합니다. 이를 *비트* 열거형 이라고 합니다.

<xref:System.FlagsAttribute> 특성을 사용 하 여 열거형을 선언 하는 경우 값에 대해 1, 2, 4, 8, 16 등의 제곱을 사용 하는 것이 좋습니다. 또한 값이 0 인 멤버의 이름을 "None"으로 지정할 것을 권장 합니다. 추가 지침은 <xref:System.FlagsAttribute> 및 <xref:System.Enum>를 참조 하세요.

## <a name="example"></a>예제

다음 예제에서는 `Enum` 문을 사용하는 방법을 보여 줍니다. 멤버는 `Medium`아닌 `EggSizeEnum.Medium`이라고 합니다.

[!code-vb[VbEnumsTask#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#41)]

## <a name="example"></a>예제

다음 예제의 메서드는 `Egg` 클래스 외부에 있습니다. 따라서 `EggSizeEnum`은 `Egg.EggSizeEnum`으로 정규화 됩니다.

[!code-vb[VbEnumsTask#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#42)]

## <a name="example"></a>예제

다음 예에서는 `Enum` 문을 사용 하 여 명명 된 상수 값의 관련 된 집합을 정의 합니다. 이 경우 값은 데이터베이스에 대 한 데이터 입력 양식을 디자인 하도록 선택할 수 있는 색입니다.

[!code-vb[VbEnumsTask#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#30)]

## <a name="example"></a>예제

다음 예에서는 양수 및 음수를 모두 포함 하는 값을 보여 줍니다.

[!code-vb[VbEnumsTask#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#31)]

## <a name="example"></a>예제

다음 예제에서는 `As` 절을 사용 하 여 열거형의 `datatype`를 지정 합니다.

[!code-vb[VbEnumsTask#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#6)]

## <a name="example"></a>예제

다음 예제에서는 비트 열거를 사용 하는 방법을 보여 줍니다. 비트 열거의 인스턴스에 여러 값을 할당할 수 있습니다. `Enum` 선언에는 열거형을 플래그 집합으로 처리할 수 있음을 나타내는 <xref:System.FlagsAttribute> 특성이 포함 되어 있습니다.

[!code-vb[VbEnumsTask#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#61)]

## <a name="example"></a>예제

다음 예제에서는 열거형을 반복 합니다. <xref:System.Enum.GetNames%2A> 메서드를 사용 하 여 열거형에서 멤버 이름 배열을 검색 하 고 <xref:System.Enum.GetValues%2A> 멤버 값의 배열을 검색 합니다.

[!code-vb[VbEnumsTask#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class1.vb#51)]

## <a name="see-also"></a>참고 항목

- <xref:System.Enum>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)
- [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)
- [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [CString](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [상수 및 열거형](../../../visual-basic/language-reference/constants-and-enumerations.md)
