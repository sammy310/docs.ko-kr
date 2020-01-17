---
title: Sub 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Sub procedures [Visual Basic], about Sub procedures
- statement blocks
- Sub procedures [Visual Basic], calling
- procedures [Visual Basic], calling
- Sub procedures [Visual Basic], syntax
- Sub procedures
- procedures [Visual Basic], Sub
- syntax [Visual Basic], Sub procedures
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
ms.openlocfilehash: 9ca1d302a0bc8e989e0b2dddf8cce68e89211d57
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163815"
---
# <a name="sub-procedures-visual-basic"></a>하위 프로시저 (Visual Basic)

`Sub` 프로시저는 `Sub` 및 `End Sub` 문으로 묶인 일련의 Visual Basic 문입니다. `Sub` 프로시저는 작업을 수행 하 고 컨트롤을 호출 코드에 반환 하지만 호출 코드에는 값을 반환 하지 않습니다.

프로시저가 호출 될 때마다 문이 실행 되 고,이 문은 `Sub` 문 다음의 첫 번째 실행 문부터 시작 하 여 첫 번째 `End Sub`, `Exit Sub`또는 `Return` 문으로 끝납니다.

모듈, 클래스 및 구조체에서 `Sub` 프로시저를 정의할 수 있습니다. 기본적으로 `Public`입니다. 즉, 응용 프로그램에서 정의 된 모듈, 클래스 또는 구조체에 대 한 액세스 권한이 있는 어디에서 나 호출할 수 있습니다. 용어 *메서드* 는 정의 모듈, 클래스 또는 구조체 외부에서 액세스 하는 `Sub` 또는 `Function` 프로시저에 대해 설명 합니다. 자세한 내용은 [프로시저](./index.md)를 참조하세요.

`Sub` 프로시저는 호출 코드를 통해 전달 되는 상수, 변수 또는 식과 같은 인수를 사용할 수 있습니다.

## <a name="declaration-syntax"></a>선언 구문

`Sub` 프로시저를 선언 하는 구문은 다음과 같습니다.

```vb
[modifiers] Sub SubName[(parameterList)]
    ' Statements of the Sub procedure.
End Sub
```

`modifiers`는 액세스 수준 및 오버 로드, 재정의, 공유 및 숨김에 대 한 정보를 지정할 수 있습니다. 자세한 내용은 [Sub 문](../../../language-reference/statements/sub-statement.md)을 참조 하세요.

## <a name="parameter-declaration"></a>매개 변수 선언

매개 변수 이름 및 데이터 형식을 지정 하 여 변수를 선언 하는 방법과 유사 하 게 각 프로시저 매개 변수를 선언 합니다. 전달 메커니즘을 지정 하 고 매개 변수가 선택적 요소 인지 아니면 매개 변수 배열 인지를 지정할 수도 있습니다.

매개 변수 목록의 각 매개 변수에 대 한 구문은 다음과 같습니다.

```vb
[Optional] [ByVal | ByRef] [ParamArray] parameterName As DataType
```

매개 변수가 선택 사항인 경우에는 해당 선언의 일부로도 기본값을 제공 해야 합니다. 기본값을 지정 하는 구문은 다음과 같습니다.

```vb
Optional [ByVal | ByRef]  parameterName As DataType = defaultValue
```

### <a name="parameters-as-local-variables"></a>로컬 변수로 서의 매개 변수

제어가 프로시저에 전달 되 면 각 매개 변수는 지역 변수로 처리 됩니다. 즉, 수명이 프로시저와 동일 하 고 해당 범위가 전체 프로시저 임을 의미 합니다.

## <a name="calling-syntax"></a>호출 구문

독립형 호출 문을 사용 하 여 `Sub` 프로시저를 명시적으로 호출 합니다. 식에서 해당 이름을 사용 하 여 호출할 수 없습니다. 선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하며 인수 목록을 괄호로 묶어야 합니다. 인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다. `Call` 키워드는 선택 사항 이지만 사용 하지 않는 것이 좋습니다.

`Sub` 프로시저에 대 한 호출 구문은 다음과 같습니다.

```vb
[Call] SubName[(argumentlist)]
```

`Sub` 메서드를 정의 하는 클래스 외부에서이 메서드를 호출할 수 있습니다. 먼저 `New` 키워드를 사용 하 여 클래스의 인스턴스를 만들거나 클래스의 인스턴스를 반환 하는 메서드를 호출 해야 합니다. 자세한 내용은 [New Operator](../../../language-reference/operators/new-operator.md)를 참조 하세요. 그런 다음, 다음 구문을 사용 하 여 인스턴스 개체에 대해 `Sub` 메서드를 호출할 수 있습니다.

```vb
object.MethodName[(argumentList)]
```

### <a name="illustration-of-declaration-and-call"></a>선언 및 호출에 대 한 그림

다음 `Sub` 절차에서는 응용 프로그램에서 수행 하려는 작업을 컴퓨터 운영자에 게 알려 주며 타임 스탬프를 표시 합니다. 모든 작업을 시작할 때이 코드를 복제 하는 대신 응용 프로그램은 다양 한 위치에서 `tellOperator`를 호출 합니다. 각 호출은 시작 중인 작업을 식별 하는 `task` 인수에서 문자열을 전달 합니다.

[!code-vb[VbVbcnProcedures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#2)]

다음 예제에서는 `tellOperator`에 대 한 일반적인 호출을 보여 줍니다.

[!code-vb[VbVbcnProcedures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#3)]

## <a name="see-also"></a>참조

- [절차](./index.md)
- [Function 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
- [방법: Visual Basic에서 이벤트 처리기 호출](./how-to-call-an-event-handler.md)
