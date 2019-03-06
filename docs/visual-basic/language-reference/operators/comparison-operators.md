---
title: 비교 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: c8835d1c42a02fa65e9acc9bd1c1f06fcfd4af02
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359824"
---
# <a name="comparison-operators-visual-basic"></a>비교 연산자(Visual Basic)
Visual Basic에 정의 된 비교 연산자는 다음과 같습니다.  
  
 `<` 연산자  
  
 `<=` 연산자  
  
 `>` 연산자  
  
 `>=` 연산자  
  
 `=` 연산자  
  
 `<>` 연산자  
  
 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 이러한 연산자는 두 식이 같은지와 그렇지 않은 경우 어떻게 다른 지 여부를 확인 하려면 비교 합니다. `Is`하십시오 `IsNot`, 및 `Like` 별도 도움말 페이지에 자세하게에서 설명 합니다. 관계 비교 연산자는이 페이지에서 자세히 설명 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. `Boolean` 비교의 결과 나타내는 값입니다.  
  
 `expression`  
 필수 요소. 임의의 식입니다.  
  
 `comparisonoperator`  
 필수 요소. 모든 관계 비교 연산자입니다.  
  
 `object1`, `object2`  
 필수 요소. 모든 개체 이름을 참조 합니다.  
  
 `string`  
 필수 요소. 임의의 `String` 식입니다.  
  
 `pattern`  
 필수 요소. 모든 `String` 식 또는 문자 범위입니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 관계 비교 연산자와 결정 하는 조건을의 목록을 포함 여부 `result` 은 `True` 또는 `False`합니다.  
  
|연산자|`True` 경우에|`False` 경우에|  
|--------------|---------------|----------------|  
|`<` (보다 작음)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (보다 작거나 같음)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (보다 큼)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (크거나 같음)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (같음)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (같지 않음)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  합니다 [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md) 대입 연산자로도 사용 됩니다.  
  
 `Is` 연산자는 `IsNot` 연산자 및 `Like` 연산자 앞의 표에 연산자에서 다른 특정 비교 기능을 포함 합니다.  
  
## <a name="comparing-numbers"></a>숫자 비교  
 형식의 식을 비교 하는 경우 `Single` 형식 중 하나로 `Double`의 `Single` 식이 변환 되 `Double`합니다. 이 동작은 Visual Basic 6의 동작과 반대입니다.  
  
 마찬가지로, 형식의 식을 비교할 때 `Decimal` 형식의 식 `Single` 또는 `Double`의 `Decimal` 식이 변환 되 `Single` 또는 `Double`합니다. 에 대 한 `Decimal` 식 소수 값 보다 작거나 1E 28 손실 될 수 있습니다. 이러한 소수 자릿수 값 손실 되지 않은 것으로 비교 하기 위해 두 값을 발생할 수 있습니다. 따라서이 주의 해야 같음을 사용 하는 경우 (`=`) 두 부동 소수점 변수를 비교 합니다. 것의 차이 두 숫자의 절대 값을 허용 오차 보다 작은지 여부를 테스트할 안전 합니다.  
  
### <a name="floating-point-imprecision"></a>부동 소수점 연산이  
 부동 소수점 숫자를 사용 하 여 작업할 때 염두에 항상 없기 정확한 표현을 메모리에서. 값 비교 등의 특정 작업에서 예기치 않은 결과가 발생할 수 있습니다이 고 [Mod 연산자](../../../visual-basic/language-reference/operators/mod-operator.md)합니다. 자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.  
  
## <a name="comparing-strings"></a>문자열 비교  
 문자열 식에 따라 사전순으로 정렬 순서에 따라 평가 문자열을 비교 하는 경우는 `Option Compare` 설정 합니다.  
  
 `Option Compare Binary` 기본 문자의 내부 이진 표현에서 파생 된 정렬 순서에 대 한 비교는 문자열입니다. 정렬 순서는 코드 페이지에 의해 결정 됩니다. 다음 예제에서는 일반적인 이진 정렬 순서를 보여 줍니다.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` 기본 응용 프로그램의 로캘에 따라 결정 되는 대/소문자 구분 텍스트 정렬 순서에 대 한 비교는 문자열입니다. 설정한 경우 `Option Compare Text` 앞의 예제에서 문자를 정렬 하 고, 다음 텍스트 정렬 순서가 적용 됩니다.  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>로캘 종속성  
 설정한 경우 `Option Compare Text`, 문자열 비교의 결과 응용 프로그램이 실행 되는 로캘 종속 될 수 있습니다. 두 문자 한 로캘에서 동일한 것으로 비교 될 수 있습니다. 로그온 시도를 허용할지 여부 등의 중요 한 결정을 내릴 수 문자열 비교를 사용 하는 경우 로캘 구분에 주의 해야 합니다. 설정 하거나 `Option Compare Binary` 호출 또는 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, 계정에 대 한 로캘을 사용 하는 합니다.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>관계 비교 연산자를 사용 하 여 형식 프로그래밍  
 관계 비교 연산자를 사용 `Object` 식이 허용 되지 않습니다 `Option Strict On`합니다. 때 `Option Strict` 됩니다 `Off`, 및 `expression1` 또는 `expression2` 는 `Object` 식 런타임 형식을 비교 방법을 결정 합니다. 다음 표에서 식의 비교 방법 및 피연산자의 런타임 형식에 따라 비교의 결과 보여 줍니다.  
  
|피연산자 인 경우|비교|  
|---------------------|-------------------|  
|둘 다 `String`|문자열 정렬 특성을 기반으로 하는 비교를 정렬 합니다.|  
|두 숫자|개체를 변환할 `Double`, 숫자 비교 합니다.|  
|한 숫자 및 1 `String`|`String` 변환할는 `Double` 숫자 비교가 수행 됩니다. 경우는 `String` 변환할 수 없습니다 `Double`, <xref:System.InvalidCastException> throw 됩니다.|  
|하나 또는 둘 다는 아닌 다른 참조 형식 `String`|<xref:System.InvalidCastException>이 throw됩니다.|  
  
 숫자 비교 처리 `Nothing` 0으로 합니다. 문자열 비교를 처리할 `Nothing` 으로 `""` (빈 문자열)입니다.  
  
## <a name="overloading"></a>오버로딩  
 관계 비교 연산자 (`<`합니다. `<=`를 `>`, `>=`를 `=`, `<>`) 일 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 코드에서는 이러한 연산자는 이러한 클래스 또는 구조체에서 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
 다음에 유의 합니다 [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md) 대입 연산자가 아니라 관계 비교 연산자로 오버 로드 될 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 식을 비교 하는 데 사용할 수 있는 관계 비교 연산자의 다양 한 용도 보여 줍니다. 관계 비교 연산자는 반환 된 `Boolean` 명시 된 식의 결과가 있는지 여부를 나타내는 결과입니다 `True`합니다. 적용 하는 경우는 `>` 고 `<` 연산자를 문자열 비교가 수행 되는 문자열의 일반 사전순 정렬 순서를 사용 하 여 합니다. 이 순서 로캘 설정에 따라 달라질 수 있습니다. 정렬이 대/소문자 구분 인지 여부에 따라 달라 집니다 합니다 [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) 설정 합니다.  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 앞의 예제에서 첫 번째 비교 반환 `False` 나머지 비교 돌아와 `True`합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.InvalidCastException>
- [= 연산자](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
