---
description: '자세한 정보: 함수 프로시저 (Visual Basic)'
title: Function 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 4997059fc33fb5d438519356b2c9fdd9e6a27cce
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100436151"
---
# <a name="function-procedures-visual-basic"></a>함수 프로시저 (Visual Basic)

`Function`프로시저는 및 문으로 묶인 일련의 Visual Basic 문입니다 `Function` `End Function` . `Function`프로시저는 작업을 수행한 다음 호출 코드에 컨트롤을 반환 합니다. 제어를 반환할 때 호출 코드에도 값을 반환 합니다.

프로시저가 호출 될 때마다 문이 실행 되 고 문 뒤의 첫 번째 실행 가능 문부터 시작 `Function` 하 여 첫 번째 `End Function` , `Exit Function` 또는 문으로 끝나는 문이 실행 됩니다 `Return` .

`Function`모듈, 클래스 또는 구조체에서 프로시저를 정의할 수 있습니다. 이는 `Public` 기본적으로 응용 프로그램의 어디에서 나 사용자가 정의한 모듈, 클래스 또는 구조에 대 한 액세스 권한이 있는 모든 위치에서 호출할 수 있음을 의미 합니다.

`Function`프로시저는 호출 코드를 통해 전달 되는 상수, 변수 또는 식과 같은 인수를 사용할 수 있습니다.

## <a name="declaration-syntax"></a>선언 구문

프로시저를 선언 하는 구문은 다음과 같습니다 `Function` .

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

*한정자* 는 오버 로드, 재정의, 공유 및 숨김과 관련 된 정보 및 액세스 수준을 지정할 수 있습니다. 자세한 내용은 [Function 문](../../../language-reference/statements/function-statement.md)을 참조 하세요.

[하위 프로시저](./sub-procedures.md)와 동일한 방식으로 각 매개 변수를 선언 합니다.

### <a name="data-type"></a>데이터 형식

모든 `Function` 프로시저에는 모든 변수와 마찬가지로 데이터 형식이 있습니다. 이 데이터 형식은 문의 절에 의해 지정 `As` `Function` 되며 함수에서 호출 코드에 반환 하는 값의 데이터 형식을 결정 합니다. 다음 샘플 선언에서는이를 보여 줍니다.

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

자세한 내용은 [함수 문의](../../../language-reference/statements/function-statement.md)"Parts"를 참조 하십시오.

### <a name="returning-values"></a>값 반환

`Function`프로시저에서 호출 하는 코드로 다시 전송 하는 값을 해당 반환 값 이라고 합니다. 이 프로시저는 다음 두 가지 방법 중 하나로이 값을 반환 합니다.

- 문을 사용 하 여 `Return` 반환 값을 지정 하 고 제어를 호출 프로그램에 즉시 반환 합니다. 다음은 이에 대한 예입니다.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- 프로시저의 하나 이상의 문에서 고유한 함수 이름에 값을 할당 합니다. 컨트롤은 `Exit Function` 또는 문이 실행 될 때까지 호출 프로그램에 반환 되지 않습니다 `End Function` . 다음은 이에 대한 예입니다.

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

함수 이름에 반환 값을 할당 하는 장점은 컨트롤이 또는 문을 발견할 때까지 프로시저에서 반환 되지 않는다는 것입니다 `Exit Function` `End Function` . 이렇게 하면 예비 값을 할당 하 고 필요한 경우 나중에 해당 값을 조정할 수 있습니다.

값 반환에 대 한 자세한 내용은 [Function 문](../../../language-reference/statements/function-statement.md)을 참조 하십시오. 배열을 반환 하는 방법에 대 한 자세한 내용은 [배열](../arrays/index.md)을 참조 하세요.

## <a name="calling-syntax"></a>호출 구문

`Function`프로시저는 대입문의 오른쪽에 있는 이름 및 인수를 포함 하 여 호출 합니다. 선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하며 인수 목록을 괄호로 묶어야 합니다. 인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.

프로시저에 대 한 호출 구문은 `Function` 다음과 같습니다.

*lvalue* `=` *functionname* `[(` *argumentlist*    `)]`

`If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *식*  `) Then`

프로시저를 호출할 때는 `Function` 해당 반환 값을 사용 하지 않아도 됩니다. 그렇지 않으면 함수의 모든 동작이 수행 되지만 반환 값은 무시 됩니다. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 는 이러한 방식으로 호출 되는 경우가 많습니다.

### <a name="illustration-of-declaration-and-call"></a>선언 및 호출에 대 한 그림

다음 `Function` 프로시저는 다른 두 변의 값을 고려 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

다음 예제에서는에 대 한 일반적인 호출을 보여 줍니다 `hypotenuse` .

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../language-reference/statements/function-statement.md)
- [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)
- [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
