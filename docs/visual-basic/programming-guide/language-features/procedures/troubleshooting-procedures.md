---
description: '자세한 정보: 문제 해결 절차 (Visual Basic)'
title: 프로시저 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: a36e2ef9442fc0e76c9a98e83007976393e7957b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471151"
---
# <a name="troubleshooting-procedures-visual-basic"></a>프로시저 문제 해결 (Visual Basic)

이 페이지에는 프로시저 작업 시 발생할 수 있는 몇 가지 일반적인 문제가 나열 되어 있습니다.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>함수 프로시저에서 배열 형식 반환

프로시저에서 `Function` 배열 데이터 형식을 반환 하는 경우 이름을 사용 하 여 `Function` 배열의 요소에 값을 저장할 수 없습니다. 이 작업을 수행 하려고 하면 컴파일러가이를에 대 한 호출로 해석 합니다 `Function` . 다음 예제에서는 컴파일러 오류를 생성 합니다.
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

문은 `AllOnes(i) = 1` `AllOnes` 잘못 된 데이터 형식의 인수 (배열 대신 스칼라)를 사용 하 여를 호출 하는 것 처럼 보이지만 컴파일러 오류를 생성 `Integer` `Integer` 합니다. 문은 `Return AllOnes()` 인수 없이를 호출 하는 것 처럼 보이지만 컴파일러 오류를 생성 합니다 `AllOnes` .  
  
 **올바른 방법:** 반환 될 배열의 요소를 수정할 수 있으려면 내부 배열을 지역 변수로 정의 합니다. 다음 예제는 오류 없이 컴파일됩니다.

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a>인수가 프로시저 호출에 의해 수정 되지 않았습니다.

프로시저에서 호출 코드의 인수를 기반으로 하는 프로그래밍 요소를 변경할 수 있도록 하려면이를 참조로 전달 해야 합니다. 그러나 프로시저는 값으로 전달 하는 경우에도 참조 형식 인수의 요소에 액세스할 수 있습니다.

- **기본 변수** 입니다. 프로시저가 기본 변수 요소 자체의 값을 바꿀 수 있도록 하려면 프로시저에서 [ByRef](../../../language-reference/modifiers/byref.md)매개 변수를 선언 해야 합니다. 또한 호출 하는 코드는 전달 메커니즘을 재정의 하기 때문에 인수를 괄호로 묶지 않아야 합니다 `ByRef` .

- **참조 형식 요소** 입니다. [ByVal](../../../language-reference/modifiers/byval.md)매개 변수를 선언 하는 경우 프로시저는 기본 변수 요소 자체를 수정할 수 없습니다. 그러나 인수가 참조 형식인 경우 프로시저는 변수의 값을 바꿀 수 없더라도 가리키는 개체의 멤버를 수정할 수 있습니다. 예를 들어 인수가 배열 변수인 경우 프로시저는 새 배열을 변수에 할당할 수 없지만 하나 이상의 요소를 변경할 수 있습니다. 변경 된 요소는 호출 코드의 기본 배열 변수에 반영 됩니다.

다음 예제에서는 배열 변수를 값으로 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 정의 합니다. 프로시저는 `increase` 각 요소에 하나씩만 추가 합니다. 프로시저는 `replace` 새 배열을 매개 변수에 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다. 그러나가 선언 되었기 때문에 재할당은 호출 코드의 기본 배열 변수에 영향을 주지 않습니다 `a()` `ByVal` .

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

다음 예제에서는 및에 대 한 호출을 수행 합니다 `increase` `replace` .

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다. `n`는 참조 형식이 기 때문에 `increase` 전달 된 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .

두 번째 `MsgBox` 호출은 "Replace After (n): 11, 21, 31, 41"를 표시 합니다. 가 전달 되기 때문에는 `n` `ByVal` `replace` 새 배열을 할당 하 여 변수를 수정할 수 없습니다 `n` . 에서 `replace` 새 배열 인스턴스를 만들고 `k` 지역 변수에 할당 하면 `a` 호출 코드에서 전달 하는 참조가 손실 `n` 됩니다. 의 멤버가 증가 하면 `a` 로컬 배열에만 `k` 영향을 줍니다.

**올바른 방법:** 기본 변수 요소 자체를 수정할 수 있으려면 참조로 전달 합니다. 다음 예제에서는 `replace` 호출 코드에서 한 배열을 다른 배열로 바꿀 수 있도록 하는의 선언 변경 내용을 보여 줍니다.

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a>오버 로드를 정의할 수 없습니다.

프로시저의 오버 로드 된 버전을 정의 하려면 동일한 이름을 사용 하지만 다른 서명을 사용 해야 합니다. 컴파일러가 동일한 서명을 사용 하는 오버 로드의 선언과 구별할 수 없는 경우 오류를 생성 합니다.

프로시저의 *서명은* 프로시저 이름 및 매개 변수 목록에 의해 결정 됩니다. 각 오버 로드는 다른 모든 오버 로드와 동일한 이름을 가져야 하지만 시그니처의 다른 구성 요소 중 하나 이상에서 모든 오버 로드와 달라 야 합니다. 자세한 내용은 [Procedure Overloading](./procedure-overloading.md)을 참조하세요.

다음 항목은 매개 변수 목록과 관련 된 경우에도 프로시저 시그니처의 구성 요소가 아닙니다.

- 프로시저 한정자 키워드 (예: `Public` , `Shared` 및) `Static`
- 매개 변수 이름.
- 매개 변수 한정자 키워드 (예: `ByRef` 및) `Optional`
- 반환 값의 데이터 형식 (변환 연산자 제외)입니다.

위의 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.

**올바른 방법:** 프로시저 오버 로드를 정의 하려면 서명을 변경 해야 합니다. 동일한 이름을 사용 해야 하므로 매개 변수의 개수, 순서 또는 데이터 형식을 변경 해야 합니다. 제네릭 프로시저에서 형식 매개 변수의 수를 다르게 지정할 수 있습니다. 변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))에서 반환 형식을 변경할 수 있습니다.

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인

하나 이상의 [선택적](../../../language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수를 사용 하 여 프로시저를 오버 로드 하는 경우 *암시적 오버 로드* 를 복제 하지 않아야 합니다. 자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)을 참조 하세요.

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a>잘못 된 버전의 오버 로드 된 프로시저 호출

프로시저에 오버 로드 된 버전이 여러 개 있는 경우 모든 매개 변수 목록을 숙지 하 고 Visual Basic 오버 로드 간의 호출을 확인 하는 방법을 이해 해야 합니다. 그렇지 않으면 의도 한 오버 로드 이외의 오버 로드를 호출할 수 있습니다.

호출 하려는 오버 로드를 결정 한 후에는 다음 규칙을 유의 해야 합니다.

- 올바른 순서 대로 올바른 개수의 인수를 제공 합니다.  
- 가장 적합 한 인수는 해당 매개 변수와 정확히 동일한 데이터 형식을 가져야 합니다. 어떤 경우 든 각 인수의 데이터 형식이 해당 매개 변수의 데이터 형식으로 확장 되어야 합니다. [Option Strict 문이](../../../language-reference/statements/option-strict-statement.md) 로 설정 된 경우에도 마찬가지입니다 `Off` . 오버 로드에서 인수 목록에 대 한 축소 변환이 필요한 경우에는 해당 오버 로드를 호출할 수 없습니다.
- 확대/축소 해야 하는 인수를 제공 하는 경우 해당 데이터 형식을 해당 매개 변수 데이터 형식에 최대한 가깝게 만듭니다. 두 개 이상의 오버 로드가 인수 데이터 형식을 허용 하는 경우 컴파일러는 최소한의 확대를 호출 하는 오버 로드에 대 한 호출을 확인 합니다.

인수를 준비할 때 [CType 함수](../../../language-reference/functions/ctype-function.md) 변환 키워드를 사용 하 여 데이터 형식이 일치 하지 않을 가능성을 줄일 수 있습니다.

### <a name="overload-resolution-failure"></a>오버 로드 확인 실패

오버 로드 된 프로시저를 호출 하는 경우 컴파일러는 오버 로드 중 하나를 제외 하 고 모두 제거 하려고 시도 합니다. 성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다. 모든 오버 로드를 제거 하거나 적합 한 오버 로드를 단일 후보로 줄일 수 없는 경우 오류를 생성 합니다.

다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
첫 번째 호출에서 컴파일러는 첫 번째 인수 ()의 형식이 `Short` 해당 매개 변수 ()의 형식으로 축소 되기 때문에 첫 번째 오버 로드를 제거 합니다 `Byte` . 그런 다음 두 번째 오버 로드 (및)의 각 인수 형식이 세 번째 `Short` 오버 `Single` 로드 (및)에서 해당 형식으로 확대 되기 때문에 세 번째 오버 로드를 제거 합니다 `Integer` `Single` . 두 번째 오버 로드는 더 적게 확대 해야 하므로 컴파일러에서 호출에이 오버 로드를 사용 합니다.

두 번째 호출에서 컴파일러는 축소를 기준으로 오버 로드를 제거할 수 없습니다. 첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다 .이는 두 번째 오버 로드를 사용 하 여 인수 형식의 확대/축소를 줄일 수 있기 때문입니다. 그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 사이를 확인할 수 없습니다. 각각에는 다른의 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식이 있습니다 ( `Byte` `Short` 에서로 `Single` `Double` ). 따라서 컴파일러는 오버 로드 확인 오류를 생성 합니다.

**올바른 방법:** 모호성 없이 오버 로드 된 프로시저를 호출할 수 있으려면 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 사용 하 여 인수 데이터 형식을 매개 변수 형식과 일치 시킵니다. 다음 예제에서는 `z` 두 번째 오버 로드에 대 한 해결을 강제 하는 호출을 보여 줍니다.

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인

프로시저의 두 오버 로드에 동일한 시그니처가 있는 경우, 즉 마지막 매개 변수가 하나에서 [선택적](../../../language-reference/modifiers/optional.md) 으로 선언 되는 경우를 제외 하 고, 컴파일러는 가장 일치 하는 [항목에 따라](../../../language-reference/modifiers/paramarray.md) 해당 프로시저에 대 한 호출을 확인 합니다. 자세한 내용은 [Overload Resolution](./overload-resolution.md)을 참조하세요.

## <a name="see-also"></a>추가 정보

- [절차](index.md)
- [하위 프로시저](sub-procedures.md)
- [함수 프로시저](function-procedures.md)
- [속성 프로시저](property-procedures.md)
- [연산자 프로시저](operator-procedures.md)
- [프로시저 매개 변수 및 인수](procedure-parameters-and-arguments.md)
- [프로시저 오버로딩](procedure-overloading.md)
- [프로시저 오버로드에서 고려해야 할 사항](considerations-in-overloading-procedures.md)
- [Overload Resolution](overload-resolution.md)
