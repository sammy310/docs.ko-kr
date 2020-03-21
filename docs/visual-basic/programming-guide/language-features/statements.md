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
ms.openlocfilehash: f63f0f0212913f95baab2a8a43c4b7f25a859cd9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401468"
---
# <a name="statements-in-visual-basic"></a>Visual Basic의 문

Visual Basic의 문은 완전한 명령입니다. 키워드, 연산자, 변수, 상수 및 식을 포함할 수 있습니다. 각 문은 다음 범주 중 하나에 속합니다.

- **Declaration Statements**변수, 상수 또는 프로시저의 이름을 지정하고 데이터 형식을 지정할 수도 있습니다.

- 작업을 시작하는 **실행 문입니다.** 이러한 문은 메서드 또는 함수를 호출할 수 있으며 코드 블록을 통해 루프 또는 분기할 수 있습니다. 실행 가능한 문에는 변수 또는 상수에 값 또는 식을 할당하는 **할당 문이**포함됩니다.

이 항목에서는 각 범주에 대해 설명합니다. 또한 이 항목에서는 한 줄에 여러 문을 결합하는 방법과 여러 줄을 통해 문을 계속 하는 방법에 대해 설명합니다.

## <a name="declaration-statements"></a>선언문

선언 문을 사용하여 프로시저, 변수, 속성, 배열 및 상수의 이름을 지정하고 정의합니다. 프로그래밍 요소를 선언할 때 해당 데이터 형식, 액세스 수준 및 범위를 정의할 수도 있습니다. 자세한 내용은 [선언된 요소 특성](./declared-elements/declared-element-characteristics.md)을 참조하십시오.

다음 예제에는 세 개의 선언이 포함되어 있습니다.

[!code-vb[VbVbalrStatements#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#80)]

첫 번째 선언은 명령문입니다. `Sub` 일치 `End Sub` 하는 문과 함께 `applyFormat`라는 프로시저를 선언 합니다. 또한 참조할 수 `applyFormat` `Public`있는 모든 코드가 호출할 수 있음을 의미하는 것을 지정합니다.

두 번째 선언은 `Const` `limit` `Integer` 데이터 형식과 값 33을 지정하는 상수를 선언하는 문입니다.

세 번째 선언은 변수를 `Dim` `thisWidget`선언하는 문입니다. 데이터 형식은 특정 개체, 즉 클래스에서 `Widget` 만든 개체입니다. 변수를 기본 데이터 형식또는 사용 중인 응용 프로그램에서 노출되는 개체 형식의 변수로 선언할 수 있습니다.

### <a name="initial-values"></a>초기 값

선언 문을 포함하는 코드가 실행되면 Visual Basic은 선언된 요소에 필요한 메모리를 보유합니다. 요소에 값이 있는 경우 Visual Basic은 해당 데이터 형식의 기본값으로 초기화합니다. 자세한 내용은 [Dim 명령문의](../../language-reference/statements/dim-statement.md)"동작"을 참조하십시오.

다음 예제에서 와 같이 선언의 일부로 변수에 초기 값을 할당할 수 있습니다.

[!code-vb[VbVbalrStatements#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#81)]

변수가 개체 변수인 경우 다음 예제에서 와 같이 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 사용하여 선언할 때 해당 클래스의 인스턴스를 명시적으로 만들 수 있습니다.

[!code-vb[VbVbalrStatements#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#82)]

선언 문에 지정 한 초기 값실행선언문에 도달할 때까지 변수에 할당되지 않습니다. 이 때까지 변수에는 데이터 형식에 대한 기본값이 포함됩니다.

## <a name="executable-statements"></a>실행 문

실행 문이 작업을 수행합니다. 프로시저를 호출하거나 코드의 다른 위치에 분기하거나 여러 문을 반복하거나 식을 평가할 수 있습니다. 할당 문은 실행 문특수의 경우입니다.

다음 예제에서는 `If...Then...Else` 컨트롤 구조를 사용하여 변수 값을 기반으로 다양한 코드 블록을 실행합니다. 각 코드 블록 내에서 `For...Next` 루프는 지정된 횟수를 실행합니다.

[!code-vb[VbVbalrStatements#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#83)]

앞의 예제에서 `If` 문은 매개 변수의 `clockwise`값을 확인합니다. 값이 `True`있는 경우 의 `spinClockwise` 메서드를 `aWidget`호출합니다. 값이 `False`있는 경우 의 `spinCounterClockwise` 메서드를 `aWidget`호출합니다. 제어 `If...Then...Else` 구조는 `End If`로 끝납니다.

각 `For...Next` 블록 내의 루프는 `revolutions` 적절한 메서드를 매개 변수 값과 동일한 횟수를 호출합니다.

## <a name="assignment-statements"></a>대입문

할당 문은 다음 예제와 같이 할당 연산자()의`=`오른쪽에 있는 값을 가져 와서 왼쪽의 요소에 저장하는 할당 작업을 수행합니다.

[!code-vb[VbVbalrStatements#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#73)]

앞의 예제에서 할당 문은 변수에 `v`리터럴 값 42를 저장합니다.

### <a name="eligible-programming-elements"></a>적격 프로그래밍 요소

할당 연산자의 왼쪽에 있는 프로그래밍 요소는 값을 수락하고 저장할 수 있어야 합니다. 즉, [ReadOnly가](../../../visual-basic/language-reference/modifiers/readonly.md)아닌 변수 또는 속성이거나 배열 요소여야 합니다. 할당 문의 컨텍스트에서 이러한 요소를 "왼쪽 값"에 대해 *lvalue라고도*합니다.

할당 연산자의 오른쪽에 있는 값은 리터럴, 상수, 변수, 속성, 배열 요소, 기타 식 또는 함수 호출의 조합으로 구성될 수 있는 식에 의해 생성됩니다. 다음은 이에 대한 예입니다.

[!code-vb[VbVbalrStatements#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#74)]

앞의 예제에서는 변수에 보유된 값을 `y` 변수에 `z`보유한 값에 추가한 다음 함수 `findResult`호출에서 반환된 값을 추가합니다. 이 식의 총 값은 변수에 `x`저장됩니다.

### <a name="data-types-in-assignment-statements"></a>할당 문의 데이터 형식

할당 연산자는 숫자 값 외에도 다음 `String` 예제에서 설명하는 것처럼 값을 할당할 수도 있습니다.

[!code-vb[VbVbalrStatements#75](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#75)]

다음 예제에서 `Boolean` 와 같이 리터럴 또는 `Boolean` 식을 `Boolean` 사용하여 값을 할당할 수도 있습니다.

[!code-vb[VbVbalrStatements#76](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#76)]

`Char`마찬가지로, 에 `Date`대한 정보 또는 `Object` 데이터 형식의 프로그래밍 요소에 적절한 값을 할당할 수 있습니다. 해당 인스턴스가 생성되는 클래스로 선언된 요소에 개체 인스턴스를 할당할 수도 있습니다.

### <a name="compound-assignment-statements"></a>복합 할당 문

*복합 할당 문은* 먼저 식에 대한 작업을 수행한 후 프로그래밍 요소에 할당합니다. 다음 예제에서는 이러한 연산자 `+=`중 하나를 보여 주며, 이 연산자의 왼쪽에 있는 변수 값을 오른쪽의 식 값으로 증분합니다.

[!code-vb[VbVbalrStatements#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#77)]

앞의 예제에서는 `n`의 값에 1을 추가한 다음 `n`해당 새 값을 에 저장합니다. 다음 명령문과 동일한 약어입니다.

[!code-vb[VbVbalrStatements#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#78)]

이 유형의 연산자를 사용하여 다양한 복합 할당 작업을 수행할 수 있습니다. 이러한 연산자 목록과 해당 연산자에 대한 자세한 내용은 [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)를 참조하십시오.

연결 할당 연산자`&=`() 는 다음 예제에서 와 같이 이미 기존 문자열의 끝에 문자열을 추가하는 데 유용합니다.

[!code-vb[VbVbalrStatements#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#79)]

### <a name="type-conversions-in-assignment-statements"></a>할당 명세서에서 변환 유형

변수, 속성 또는 배열 요소에 할당하는 값은 해당 대상 요소에 적합한 데이터 형식이어야 합니다. 일반적으로 대상 요소와 동일한 데이터 형식의 값을 생성해야 합니다. 그러나 일부 형식은 할당 하는 동안 다른 유형으로 변환할 수 있습니다.

데이터 형식 간의 변환에 대한 자세한 내용은 [Visual Basic의 변환 유형을](./data-types/type-conversions.md)참조하십시오. 간단히 말해서 Visual Basic은 지정된 형식의 값을 확대되는 다른 유형으로 자동으로 변환합니다. *확대 변환은* 항상 런타임에 성공하고 데이터를 잃지 않는 변환입니다. 예를 들어 Visual Basic은 `Integer` 값을 `Double` 로 확장하기 `Integer` 때문에 `Double`적절한 경우 값으로 변환합니다. 자세한 내용은 [Widening and Narrowing Conversions](./data-types/widening-and-narrowing-conversions.md)을 참조하세요.

*축소* 변환(확장되지 않은 전환)은 런타임에 실패하거나 데이터 손실이 발생할 위험이 있습니다. 형식 변환 함수를 사용하여 명시적으로 축소 변환을 수행하거나 컴파일러를 설정하여 `Option Strict Off`암시적으로 모든 변환을 수행하도록 지시할 수 있습니다. 자세한 내용은 [암시적 및 명시적 변환을](./data-types/implicit-and-explicit-conversions.md)참조하십시오.

## <a name="putting-multiple-statements-on-one-line"></a>한 줄에 여러 명령문 배치

콜론 ()`:`문자로 구분 된 한 줄에 여러 문을 가질 수 있습니다. 다음은 이에 대한 예입니다.

[!code-vb[VbVbalrStatements#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#70)]

때때로 편리하지만 이러한 형태의 구문은 코드를 읽고 유지 관리하기 어렵게 만듭니다. 따라서 한 문을 한 줄에 유지하는 것이 좋습니다.

## <a name="continuing-a-statement-over-multiple-lines"></a>여러 줄에 걸쳐 문 계속

문은 일반적으로 한 줄에 맞지만 너무 길면 밑줄 문자 ()`_`뒤에 캐리지 반환이 뒤따르는 공백으로 구성된 줄 연속 시퀀스를 사용하여 다음 줄로 계속할 수 있습니다. 다음 예제에서는 `MsgBox` 실행 문이 두 줄로 계속됩니다.

[!code-vb[VbVbalrStatements#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#71)]

### <a name="implicit-line-continuation"></a>암시적 줄 연속

대부분의 경우 밑줄 문자()를`_`사용하지 않고 다음 연속 줄에 문을 계속 사용할 수 있습니다. 다음 구문 요소는 다음 코드 줄에서 문을 암시적으로 계속합니다.

- 쉼표 후`,`(). 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#1)]

- 열린 괄호 후 ()`(`또는 닫는 괄호`)`전 (). 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#2)]

- 열린 곱슬 버팀대`{`후 () 또는 닫기 곱슬 대괄호 ()`}`전에. 다음은 그 예입니다.

    [!code-vb[VbVbalrLineContinuation#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#3)]

    자세한 내용은 [개체 초기화자: 명명된 및 익명 형식](./objects-and-classes/object-initializers-named-and-anonymous-types.md) 또는 컬렉션 [초기화 자를 참조하십시오.](./collection-initializers/index.md)

- 열린 임베디드`<%=`식 () 후 ()`%>`또는 XML 리터럴 내에서 임베디드 식 ()의 닫기 전에. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#4)]

   자세한 내용은 [XML의 임베디드 식을](./xml/embedded-expressions-in-xml.md)참조하십시오.

- 연결 연산자 ()를`&`참조하십시오. 다음은 그 예입니다.

   [!code-vb[VbVbcnConventions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/vb/Class1.vb#9)]

   자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.

- 할당 후 연산자 `:=` `+=` `-=`(, `*=` `/=` `\=` `^=``=` `&=`" , `<<=` `>>=`" , " , " , ) . 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.

- [이진 연산자] `*` `Mod`[이진연산자] `<>` `<` `>` `<=` `>=` `^` `>>` `<<` `And` `AndAlso` `Or``+` `-` `/` `OrElse` `Like` `Xor` 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#7)]

   자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.

- `Is` 및 `IsNot` 연산자 후. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#8)]

   자세한 내용은 [기능별로 나열된 연산자](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)를 참조하십시오.

- 멤버 한정자 문자`.`() 및 멤버 이름 앞에 있습니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#5)]

   그러나 `With` 문을 사용하거나 형식의 초기화 목록에`_`값을 제공할 때 멤버 한정자 문자 다음에 줄 연속 문자 () 를 포함해야 합니다. 문 또는 개체 초기화 목록을 사용하는 `=` `With` 경우 할당 연산자(예:) 다음으로 선을 끊는 것이 좋습니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#14)]

   자세한 내용은 [다음을 참조하십시오. 명령문](../../../visual-basic/language-reference/statements/with-end-with-statement.md) 또는 [개체 초기화자로 끝: 명명된 형식 및 익명 형식.](./objects-and-classes/object-initializers-named-and-anonymous-types.md)

- XML 축 속성 한정자(또는`.` 또는)를 `.@` `...`사용합니다. 그러나 키워드를 사용할 때 멤버 한정자를`_`지정할 때 줄 연속 문자 () 를 `With` 포함해야 합니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#9)]

   자세한 내용은 [XML 축 속성](../../../visual-basic/language-reference/xml-axis/index.md)을 참조하십시오.

- 특성을 지정할 때 보다 작은 기호(<)`>`또는 보다 큰 기호() 앞에 있습니다. 또한 특성을 지정할`>`때 보다 큰 기호 () 후에. 그러나 어셈블리 수준 또는 모듈 수준 특성을 지정할 때 선 연속 문자 ()`_`포함 해야 합니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#10)]

   자세한 내용은 [특성 개요를](../../../visual-basic/programming-guide/concepts/attributes/index.md)참조하십시오.

- `Aggregate`[] [ ] `Distinct` `From` `Group By` `Group Join` `Join` `Let` `Order By` `Select` `Skip` `Skip While` `Take` `Take While` `Where` `In` `Into` `On` `Ascending` `Descending` 여러`Order By`키워드 (, `Group Join`및)로 `Take While` `Skip While`구성된 쿼리 연산자의 키워드 사이의 선을 끊을 수 없습니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#11)]

   자세한 내용은 [쿼리 를](../../../visual-basic/language-reference/queries/index.md)참조하십시오.

- `For Each` 명령문의 `In` 키워드 다음. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#12)]

   자세한 내용은 [각 에 대해 참조하세요... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md).

- 컬렉션 `From` 초기화의 키워드 다음입니다. 다음은 그 예입니다.

   [!code-vb[VbVbalrLineContinuation#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrlinecontinuation/vb/module1.vb#13)]

   자세한 내용은 [컬렉션 이니셜라이저](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)를 참조하세요.

## <a name="adding-comments"></a>댓글 추가

소스 코드가 항상 자명한 것은 아니며, 심지어 소스를 작성한 프로그래머에게도 설명이 될 수 있습니다. 따라서 대부분의 프로그래머는 코드를 문서화하기 위해 임베디드 주석을 자유롭게 사용합니다. 코드의 주석은 나중에 읽거나 작업하는 모든 사람에게 프로시저 또는 특정 명령을 설명할 수 있습니다. Visual Basic은 컴파일 하는 동안 주석을 무시 하 고 컴파일된 코드에 영향을 주지 않습니다.

주석 줄은 아포스트로피()`'`또는 `REM` 공백 뒤에 시작됩니다. 문자열 을 제외한 코드의 아무 곳에나 추가할 수 있습니다. 명령문에 주석을 추가하려면 아포스트로피를 삽입하거나 `REM` 문 뒤에 주석을 삽입합니다. 주석은 별도의 줄로 진행할 수도 있습니다. 다음 예제에서는 이러한 가능성을 보여 줍니다.

[!code-vb[VbVbalrStatements#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#72)]

## <a name="checking-compilation-errors"></a>컴파일 오류 확인

코드 줄을 입력한 후 줄에 물결 모양의 파란색 밑줄이 표시되면(오류 메시지도 나타날 수 있음) 문에 구문 오류가 있습니다. 명령문에 무엇이 잘못되었는지 (작업 목록에서 보거나 마우스 포인터로 오류를 가리키고 오류 메시지를 읽으면) 오류를 수정해야합니다. 코드의 모든 구문 오류를 수정할 때까지 프로그램이 올바르게 컴파일되지 않습니다.

## <a name="related-sections"></a>관련 단원

|용어|정의|
|---|---|
|[대입 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)|Provides links to language reference pages covering assignment operators such as `=`, `*=`, and `&=`.|
|[연산자 및 식](./operators-and-expressions/index.md)|요소를 연산자와 결합하여 새 값을 산출하는 방법을 보여 주어집니다.|
|[방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)|단일 문을 여러 줄로 나누는 방법과 동일한 줄에 여러 문을 배치하는 방법을 보여 주시면 됩니다.|
|[방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)|코드 줄에 레이블을 지정하는 방법을 보여 주습니다.|
