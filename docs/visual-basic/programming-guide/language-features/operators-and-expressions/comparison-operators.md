---
title: 비교 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- comparison operators [Visual Basic], comparing strings
- comparison operators [Visual Basic], comparing objects
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- string comparison [Visual Basic], operators
- objects [Visual Basic], comparing
- numbers [Visual Basic], comparing
- Visual Basic code, operators
- string comparison [Visual Basic]
- numeric values [Visual Basic], comparing
- comparison operators [Visual Basic], comparing numeric values
- operators [Visual Basic], comparison
ms.assetid: 0b570339-5407-474f-8421-e183a8b303ee
ms.openlocfilehash: 7a93928ff95e307c64149da7ab21476ffd4fa77d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388831"
---
# <a name="comparison-operators-in-visual-basic"></a>Comparison Operators in Visual Basic
비교 연산자는 두 식을 비교 하 고 `Boolean` 해당 값의 관계를 나타내는 값을 반환 합니다. 숫자 값을 비교 하는 연산자, 문자열 비교 연산자 및 개체 비교 연산자가 있습니다. 이 세 가지 유형의 연산자는 모두 여기에 설명 되어 있습니다.  
  
## <a name="comparing-numeric-values"></a>숫자 값 비교  
 Visual Basic는 숫자 비교 연산자 6 개를 사용 하 여 숫자 값을 비교 합니다. 각 연산자는 숫자 값으로 계산 되는 두 식을 피연산자로 사용 합니다. 다음 표에서는 연산자를 나열 하 고 각각에 대 한 예제를 보여 줍니다.  
  
|연산자|테스트 된 조건|예제|  
|--------------|----------------------|--------------|  
|`=`연산|첫 번째 식의 값이 두 번째 식의 값과 같은지 여부를 확인 합니다.|`23`   `=`   `33    ' False`<br /><br /> `23`   `=`   `23    ' True`<br /><br /> `23`   `=`   `12    ' False`|  
|`<>`연산|첫 번째 식의 값이 두 번째 식의 값과 같지 않은지 여부를 확인 합니다.|`23`   `<>`   `33    ' True`<br /><br /> `23`   `<>`   `23    ' False`<br /><br /> `23`   `<>`   `12    ' True`|  
|`<`(보다 작음)|첫 번째 식의 값이 두 번째 식의 값 보다 작은 가요?|`23`   `<`   `33    ' True`<br /><br /> `23`   `<`   `23    ' False`<br /><br /> `23`   `<`   `12    ' False`|  
|`>`(보다 큼)|첫 번째 식의 값이 두 번째 식의 값 보다 큰지 여부를 확인 합니다.|`23`   `>`   `33    ' False`<br /><br /> `23`   `>`   `23    ' False`<br /><br /> `23`   `>`   `12    ' True`|  
|`<=`(작거나 같음)|첫 번째 식의 값이 두 번째 식의 값 보다 작거나 같은지 여부를 확인 합니다.|`23`   `<=`   `33    ' True`<br /><br /> `23`   `<=`   `23    ' True`<br /><br /> `23`   `<=`   `12    ' False`|  
|`>=`(크거나 같음)|첫 번째 식의 값이 두 번째 식의 값 보다 크거나 같은지 여부를 확인 합니다.|`23`   `>=`   `33    ' False`<br /><br /> `23`   `>=`   `23    ' True`<br /><br /> `23`   `>=`   `12    ' True`|  
  
## <a name="comparing-strings"></a>문자열 비교  
 Visual Basic는 [Like 연산자](../../../language-reference/operators/like-operator.md) 및 숫자 비교 연산자를 사용 하 여 문자열을 비교 합니다. 연산자를 사용 하 여 `Like` 패턴을 지정할 수 있습니다. 그런 다음이 문자열을 패턴과 비교 하 여 일치 하는 경우 결과는 `True` 입니다. 그렇지 않으면 결과는 `False`입니다. 숫자 연산자를 사용 하면 `String` 다음 예제와 같이 정렬 순서에 따라 값을 비교할 수 있습니다.  
  
 `"73" < "9"`  
  
 `' The result of the preceding comparison is True.`  
  
 앞의 예제에서 결과는 `True` 첫 번째 문자열의 첫 번째 문자가 두 번째 문자열의 첫 번째 문자 앞에 정렬 되기 때문입니다. 첫 번째 문자가 같으면 비교는 두 문자열의 다음 문자로 계속 됩니다. 다음 예제와 같이 같음 연산자를 사용 하 여 문자열의 같음 여부를 테스트할 수도 있습니다.  
  
 `"734" = "734"`  
  
 `' The result of the preceding comparison is True.`  
  
 한 문자열이 다른 문자열의 접두사 (예: "aa" 및 "aaa") 이면 긴 문자열이 짧은 문자열 보다 큰 것으로 간주 됩니다. 다음은 이에 대한 예입니다.  
  
 `"aaa" > "aa"`  
  
 `' The result of the preceding comparison is True.`  
  
 정렬 순서는의 설정에 따라 이진 비교 또는 텍스트 비교를 기반으로 합니다 `Option Compare` . 자세한 내용은 [Option Compare 문](../../../language-reference/statements/option-compare-statement.md)을 참조 하세요.  
  
## <a name="comparing-objects"></a>개체 비교  
 Visual Basic [는 Is 연산자](../../../language-reference/operators/is-operator.md) 와 [IsNot 연산자](../../../language-reference/operators/isnot-operator.md)를 사용 하 여 두 개체 참조 변수를 비교 합니다. 이러한 연산자 중 하나를 사용 하 여 두 참조 변수가 동일한 개체 인스턴스를 참조 하는지 확인할 수 있습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#65)]  
  
 위의 예제에서는 `x Is y` `True` 두 변수가 모두 동일한 인스턴스를 참조 하기 때문에를 반환 합니다. 이 결과와 다음 예제를 대조 합니다.  
  
 [!code-vb[VbVbalrOperators#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#66)]  
  
 위의 예제에서는 `x Is y` `False` 변수가 동일한 형식의 개체를 참조 하지만 해당 형식의 다른 인스턴스를 참조 하기 때문에가로 평가 됩니다.  
  
 동일한 인스턴스를 가리키지 않는 두 개체를 테스트 하려는 경우 연산자를 사용 하 여 `IsNot` 및의 문법적 괴로운 조합을 방지할 수 있습니다 `Not` `Is` . 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#67)]  
  
 앞의 예제에서 `If a IsNot b` 는와 동일 `If Not a Is b` 합니다.  
  
### <a name="comparing-object-type"></a>개체 형식 비교  
 개체가 `TypeOf` ... 식이 있는 특정 형식 인지 여부를 테스트할 수 있습니다. `Is` 구문은 다음과 같습니다.  
  
 `TypeOf <objectexpression> Is <typename>`  
  
 에서 `typename` 인터페이스 형식을 지정 하는 경우 `TypeOf` ... `Is` 식은 `True` 개체가 인터페이스 형식을 구현 하는 경우를 반환 합니다. `typename`가 클래스 형식이 면 해당 개체가 지정 된 클래스 `True` 또는 지정 된 클래스에서 파생 된 클래스의 인스턴스인 경우에는를 반환 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#68)]  
  
 앞의 예제에서 `TypeOf x Is Control` 식은로 계산 됩니다 `True` .의 형식은 `x` `Button` 에서 상속 됩니다 `Control` .  
  
 자세한 내용은 [TypeOf 연산자](../../../language-reference/operators/typeof-operator.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [값 비교](value-comparisons.md)
- [비교 연산자](../../../language-reference/operators/comparison-operators.md)
- [연산자](../../../language-reference/operators/index.md)
- [Visual Basic의 산술 연산자](arithmetic-operators.md)
- [Visual Basic의 연결 연산자](concatenation-operators.md)
- [Visual Basic의 논리 및 비트 연산자](logical-and-bitwise-operators.md)
