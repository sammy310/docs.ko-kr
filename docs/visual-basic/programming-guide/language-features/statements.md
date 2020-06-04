---
title: 문
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- colons (:) [Visual Basic]
- constants [Visual Basic], defining
- underlines
- constants [Visual Basic], statements
- blue underline [Visual Basic]
- procedures [Visual Basic], statements
- variables [Visual Basic], assigning
- line breaks [Visual Basic], in code
- executable statements [Visual Basic]
- variables [Visual Basic], defining
- statements [Visual Basic], about statements
ms.assetid: fcfdee1a-82b7-4846-98f7-9ca3f5160089
ms.openlocfilehash: 09fe53f4bc2b6d025b762c6595c5337263456bae
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401981"
---
# <a name="statements-in-visual-basic"></a>Visual Basic의 문

Visual Basic 문은 전체 명령입니다. 키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다. 각 문은 다음 범주 중 하나에 속합니다.

- 변수, 상수 또는 프로시저의 이름을 지정 하는 **선언문**을 지정 하 고 데이터 형식을 지정할 수도 있습니다.

- 작업을 시작 하는 **실행 가능한 문** 이러한 문은 메서드나 함수를 호출할 수 있으며 코드 블록을 통해 루프 또는 분기할 수 있습니다. 실행 문에는 변수나 상수에 값 또는 식을 할당 하는 **대입문**이 포함 됩니다.

이 항목에서는 각 범주에 대해 설명 합니다. 또한이 항목에서는 여러 문을 한 줄에 결합 하는 방법과 문을 여러 줄로 계속 하는 방법에 대해 설명 합니다.

## <a name="declaration-statements"></a>선언문

선언 문을 사용 하 여 프로시저, 변수, 속성, 배열 및 상수를 이름 지정 하 고 정의 합니다. 프로그래밍 요소를 선언 하는 경우 해당 데이터 형식, 액세스 수준 및 범위를 정의할 수도 있습니다. 자세한 내용은 [선언 된 요소 특성](./declared-elements/declared-element-characteristics.md)을 참조 하세요.

다음 예제에는 세 개의 선언이 포함 되어 있습니다.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

첫 번째 선언은 `Sub` 문입니다. 일치 하는 `End Sub` 문과 함께 이라는 프로시저를 선언 `applyFormat` 합니다. 또한 `applyFormat` 이 `Public` 를 참조 하는 모든 코드가이를 호출할 수 있음을 의미 하는를 지정 합니다.

두 번째 선언은 `Const` `limit` `Integer` 데이터 형식 및 값 33를 지정 하 여 상수를 선언 하는 문입니다.

세 번째 선언은 변수를 `Dim` 선언 하는 문입니다 `thisWidget` . 데이터 형식은 특정 개체, 즉 클래스에서 만든 개체입니다 `Widget` . 변수를 기본 데이터 형식이 나 사용 중인 응용 프로그램에 노출 되는 모든 개체 형식으로 선언할 수 있습니다.

### <a name="initial-values"></a>초기 값

선언 문을 포함 하는 코드를 실행 하면 Visual Basic는 선언 된 요소에 필요한 메모리를 예약 합니다. 요소가 값을 포함 하는 경우에는 Visual Basic 해당 데이터 형식에 대 한 기본값으로 초기화 합니다. 자세한 내용은 [Dim 문의](../../language-reference/statements/dim-statement.md)"Behavior"를 참조 하십시오.

다음 예제와 같이 변수의 초기 값을 선언의 일부로 할당할 수 있습니다.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

변수가 개체 변수인 경우에는 다음 예제와 같이 [New Operator](../../language-reference/operators/new-operator.md) 키워드를 사용 하 여 선언할 때 해당 클래스의 인스턴스를 명시적으로 만들 수 있습니다.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

선언 문에 지정 하는 초기 값은 실행이 해당 선언문에 도달할 때까지 변수에 할당 되지 않습니다. 이 시간까지 변수는 해당 데이터 형식에 대 한 기본값을 포함 합니다.

## <a name="executable-statements"></a>실행 문

실행 문은 동작을 수행 합니다. 프로시저를 호출 하 고, 코드의 다른 위치로 분기 하거나, 여러 문을 반복 하거나, 식을 계산할 수 있습니다. 대입문은 실행 가능한 문의 특수 한 경우입니다.

다음 예제에서는 컨트롤 구조를 사용 하 여 `If...Then...Else` 변수 값을 기반으로 여러 코드 블록을 실행 합니다. 각 코드 블록 내에서 루프는 `For...Next` 지정 된 횟수 만큼 실행 됩니다.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

`If`위의 예에 있는 문은 매개 변수의 값을 확인 합니다 `clockwise` . 값이 이면는 `True` 의 메서드를 호출 합니다 `spinClockwise` `aWidget` . 값이 이면는 `False` 의 메서드를 호출 합니다 `spinCounterClockwise` `aWidget` . `If...Then...Else`컨트롤 구조는로 끝납니다 `End If` .

`For...Next`각 블록 내의 루프는 매개 변수의 값과 같은 횟수 만큼 적절 한 메서드를 호출 합니다 `revolutions` .

## <a name="assignment-statements"></a>대입문

대입문은 다음 예제와 같이 대입 연산자의 오른쪽에 있는 값 ()을 가져와 왼쪽의 요소에 저장 하는 것으로 구성 된 할당 작업을 수행 `=` 합니다.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

위의 예에서 대입문은 변수에 리터럴 값 42를 저장 합니다 `v` .

### <a name="eligible-programming-elements"></a>적합 한 프로그래밍 요소

할당 연산자의 좌 변에 있는 프로그래밍 요소는 값을 허용 하 고 저장할 수 있어야 합니다. 즉, [ReadOnly](../../language-reference/modifiers/readonly.md)이거나 배열 요소 여야 하는 변수 또는 속성 이어야 합니다. 대입문의 컨텍스트에서 "left value"의 경우 이러한 요소를 *lvalue*라고도 합니다.

대입 연산자의 오른쪽에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소, 기타 식 또는 함수 호출의 조합으로 구성 될 수 있는 식에 의해 생성 됩니다. 다음은 이에 대한 예입니다.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

앞의 예제에서는 변수에 저장 된 값을 `y` 변수에 저장 된 값에 추가 하 `z` 고 함수에 대 한 호출에서 반환 된 값을 추가 합니다 `findResult` . 그런 다음이 식의 합계 값이 변수에 저장 됩니다 `x` .

### <a name="data-types-in-assignment-statements"></a>대입문의 데이터 형식

다음 예제와 같이 숫자 값 외에도 할당 연산자는 `String` 값을 할당할 수 있습니다.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

`Boolean` `Boolean` `Boolean` 다음 예제에 나와 있는 것 처럼 리터럴 또는 식을 사용 하 여 값을 할당할 수도 있습니다.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

마찬가지로 `Char` , `Date` 또는 데이터 형식의 프로그래밍 요소에 적절 한 값을 할당할 수 있습니다 `Object` . 또한 해당 인스턴스가 생성 된 클래스로 선언 된 요소에 개체 인스턴스를 할당할 수 있습니다.

### <a name="compound-assignment-statements"></a>복합 대입문

*복합 대입문* 은 먼저 식에 대해 작업을 수행한 다음 프로그래밍 요소에 할당 합니다. 다음 예에서는 `+=` 연산자의 좌 변에 있는 변수의 값을 오른쪽에 있는 식의 값으로 증가 시키는 이러한 연산자 중 하나를 보여 줍니다.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

앞의 예제에서는의 값에 1을 추가한 `n` 다음 새 값을에 저장 `n` 합니다. 이는 다음 문과 동일한 의미를 갖습니다.

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

이 형식의 연산자를 사용 하 여 다양 한 복합 할당 작업을 수행할 수 있습니다. 이러한 연산자의 목록과 이러한 연산자에 대 한 자세한 내용은 [할당 연산자](../../language-reference/operators/assignment-operators.md)를 참조 하세요.

연결 할당 연산자 ( `&=` )는 다음 예제에 나와 있는 것 처럼 기존 문자열의 끝에 문자열을 추가 하는 데 유용 합니다.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>대입문의 형식 변환

변수, 속성 또는 배열 요소에 할당 하는 값은 해당 대상 요소에 적합 한 데이터 형식 이어야 합니다. 일반적으로 대상 요소와 동일한 데이터 형식의 값을 생성 하려고 합니다. 그러나 할당 하는 동안 일부 형식을 다른 형식으로 변환할 수 있습니다.

데이터 형식 간의 변환에 대 한 자세한 내용은 [Visual Basic 형식 변환](./data-types/type-conversions.md)을 참조 하세요. 간단히 말해서 Visual Basic는 지정 된 형식의 값을 자동으로 확대 되는 다른 형식으로 변환 합니다. *확대 변환은* 항상 런타임에 성공 하 고 데이터를 손실 하지 않는의 하나입니다. 예를 들어 Visual Basic는 `Integer` `Double` 로 확대 되기 때문에 적절 한 경우 값을로 변환 `Integer` `Double` 합니다. 자세한 내용은 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)을 참조하세요.

*축소 변환* (확대 되지 않은 변환)은 런타임에 오류가 발생 하거나 데이터 손실이 발생할 수 있습니다. 형식 변환 함수를 사용 하 여 명시적으로 축소 변환을 수행 하거나를 설정 하 여 모든 변환을 암시적으로 수행 하도록 컴파일러에 지시할 수 있습니다 `Option Strict Off` . 자세한 내용은 [암시적 변환과 명시적 변환](./data-types/implicit-and-explicit-conversions.md)을 참조 하세요.

## <a name="putting-multiple-statements-on-one-line"></a>여러 문을 한 줄에 배치

한 줄에 콜론 () 문자로 구분 된 문이 여러 개 있을 수 있습니다 `:` . 다음은 이에 대한 예입니다.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

이러한 형태의 구문을 사용 하면 코드를 읽고 유지 관리 하기가 어렵습니다. 따라서 문을 한 줄에 유지 하는 것이 좋습니다.

## <a name="continuing-a-statement-over-multiple-lines"></a>문을 여러 줄에 걸쳐 계속

문은 일반적으로 한 줄에 배치 되지만 너무 길면 줄 연속 시퀀스를 사용 하 여 다음 줄로 계속 진행할 수 있습니다 .이 시퀀스는 공백 뒤에 밑줄 문자 ()와 캐리지 리턴이 차례로 오는 줄 연속 시퀀스를 사용 합니다 `_` . 다음 예에서는 `MsgBox` 실행 가능한 문이 두 줄에 걸쳐 계속 됩니다.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>암시적 줄 연속

대부분의 경우 밑줄 문자 ()를 사용 하지 않고 다음 연속 줄에서 문을 계속할 수 있습니다 `_` . 다음 구문 요소는 코드의 다음 줄에서 문을 암시적으로 계속 합니다.

- 쉼표 () 뒤 `,` . 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- 여는 괄호 ( `(` ) 또는 닫는 괄호 () 앞에 `)` 있습니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- 여는 중괄호 ( `{` ) 또는 닫는 중괄호 () 앞에 `}` 있습니다. 예를 들면 다음과 같습니다.

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    자세한 내용은 [개체 이니셜라이저: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 [컬렉션 이니셜라이저](./collection-initializers/index.md)를 참조 하세요.

- XML 리터럴 내에서 포함 된 식 ( `<%=` ) 또는 포함 된 식 ()이 가까이 있는 경우 `%>` 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   자세한 내용은 [XML의 포함 식](./xml/embedded-expressions-in-xml.md)을 참조 하세요.

- 연결 연산자 () 다음에 `&` 예를 들면 다음과 같습니다.

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.

- 할당 연산자 (,,,,,,,,, `=` `&=` ,)를 지정 `:=` `+=` `-=` `*=` `/=` `\=` `^=` `<<=` `>>=` 합니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.

- 식 내에서 이항 연산자 (,,,,,,,,,,,,,,,,,, `+` `-` `/` `*` `Mod` `<>` `<` `>` `<=` `>=` )가 `^` `>>` `<<` `And` `AndAlso` `Or` `OrElse` `Like` `Xor` 발생 했습니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.

- `Is`및 연산자 뒤 `IsNot` 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   자세한 내용은 [기능에 나열 된 연산자](../../language-reference/operators/operators-listed-by-functionality.md)를 참조 하세요.

- 멤버 한정자 문자 ( `.` )와 멤버 이름 앞에 있습니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   그러나 `_` `With` 문을 사용 하거나 형식에 대 한 초기화 목록에 값을 제공 하는 경우 멤버 한정자 문자 뒤에 줄 연속 문자 ()를 포함 해야 합니다. `=`문이나 개체 초기화 목록을 사용 하는 경우 할당 연산자 (예:) 뒤의 줄을 분리 하는 것이 좋습니다 `With` . 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   자세한 내용은 다음 [을 참조 하세요. 문](../../language-reference/statements/with-end-with-statement.md) 또는 [개체 이니셜라이저가 있는 End: 명명 된 형식과 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md)입니다.

- XML 축 속성 한정자 ( `.` 또는 `.@` 또는 `...` ) 뒤 그러나 `_` 키워드를 사용할 때 멤버 한정자를 지정 하는 경우에는 줄 연속 문자 ()를 포함 해야 합니다 `With` . 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   자세한 내용은 [XML 축 속성](../../language-reference/xml-axis/index.md)을 참조 하세요.

- 특성을 지정할 때 보다 작음 기호 (<) 또는 보다 큼 부호 () 앞에 `>` 있습니다. 또한 특성을 지정할 때 보다 큼 기호 () 뒤에 `>` . 그러나 `_` 어셈블리 수준 또는 모듈 수준 특성을 지정 하는 경우에는 줄 연속 문자 ()를 포함 해야 합니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   자세한 내용은 [특성 개요](../concepts/attributes/index.md)를 참조 하세요.

- Before 및 after 쿼리 연산자 (,,,,,,,,,,,,,,,,,, `Aggregate` `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending` ) 여러 키워드 ( `Order By` ,, `Group Join` `Take While` 및)로 구성 된 쿼리 연산자의 키워드 사이에 줄을 나눌 수 없습니다 `Skip While` . 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   자세한 내용은 [쿼리](../../language-reference/queries/index.md)를 참조 하세요.

- `In`문의 키워드 뒤에 `For Each` 있습니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   자세한 내용은 For Each ...를 참조 하십시오. [ 다음 문](../../language-reference/statements/for-each-next-statement.md).

- `From`컬렉션 이니셜라이저의 키워드 뒤에 있습니다. 예를 들면 다음과 같습니다.

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   자세한 내용은 [컬렉션 이니셜라이저](collection-initializers/index.md)를 참조하세요.

## <a name="adding-comments"></a>주석 추가

소스 코드는 코드를 작성 하는 프로그래머에 게는 항상 설명이 포함 되지 않습니다. 따라서 대부분의 프로그래머는 코드를 문서화할 수 있도록 포함 된 주석을 자유롭게 사용 합니다. 코드의 주석은 나중에 읽거나 작업 하는 모든 사용자에 게 프로시저 또는 특정 지침을 설명할 수 있습니다. 컴파일하는 동안 Visual Basic는 주석을 무시 하 고 컴파일된 코드에는 영향을 주지 않습니다.

주석 줄은 아포스트로피 ()로 시작 `'` 하거나 `REM` 뒤에 공백이 붙습니다. 문자열 내에서를 제외 하 고 코드의 모든 위치에 추가할 수 있습니다. 문에 주석을 추가 하려면 아포스트로피 또는 `REM` 문 뒤에 주석을 삽입 합니다. 주석은 별도의 줄로 이동할 수도 있습니다. 다음 예제에서는 이러한 가능성을 보여 줍니다.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>컴파일 오류 확인

코드 줄을 입력 한 후 물결선이 파란색 물결선으로 표시 되 면 (오류 메시지가 표시 될 수 있음) 문에 구문 오류가 있습니다. 문에 무엇이 잘못 되었는지 확인 해야 합니다 (작업 목록에서 확인 하거나 마우스 포인터로 오류를 가리키고 오류 메시지를 읽은 후). 코드의 모든 구문 오류를 해결할 때까지 프로그램을 올바르게 컴파일하지 못합니다.

## <a name="related-sections"></a>관련 단원

|용어|정의|
|---|---|
|[할당 연산자](../../language-reference/operators/assignment-operators.md)|, 및와 같은 할당 연산자를 다루는 언어 참조 페이지에 대 한 링크를 제공 `=` `*=` `&=` 합니다.|
|[연산자 및 식](./operators-and-expressions/index.md)|요소와 연산자를 결합 하 여 새 값을 생성 하는 방법을 보여 줍니다.|
|[방법: 코드에서 명령문 분리 및 결합](../program-structure/how-to-break-and-combine-statements-in-code.md)|단일 문을 여러 줄로 나누고 여러 문을 같은 줄에 넣는 방법을 보여 줍니다.|
|[방법: Label 문](../program-structure/how-to-label-statements.md)|코드 줄에 레이블을 표시 하는 방법을 보여 줍니다.|
