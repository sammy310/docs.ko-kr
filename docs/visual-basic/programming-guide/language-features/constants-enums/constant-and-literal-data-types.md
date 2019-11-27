---
title: 상수 및 리터럴 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333726"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>상수 및 리터럴 데이터 형식(Visual Basic)
리터럴은 변수 값 또는 식의 결과 (예: 숫자 3 또는 문자열 "Hello")가 아니라 자체로 표현 되는 값입니다. 상수는 리터럴 자리를 사용 하 고 값이 변경 될 수 있는 변수와 달리 프로그램 전체에서 동일한 값을 유지 하는 의미 있는 이름입니다.  
  
 [옵션 유추](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 가 `Off` 되 고 [option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 가 `On`경우 데이터 형식을 사용 하 여 명시적으로 모든 상수를 선언 해야 합니다. 다음 예에서는 `MyByte` 데이터 형식이 명시적으로 `Byte`데이터 형식으로 선언 됩니다.  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 `Option Infer` `On` 또는 `Option Strict` `Off`경우에는 `As` 절을 사용 하 여 데이터 형식을 지정 하지 않고 상수를 선언할 수 있습니다. 컴파일러는 식의 형식에서 상수의 형식을 결정 합니다. 숫자 정수 리터럴은 기본적으로 `Integer` 데이터 형식으로 캐스팅 됩니다. 부동 소수점 숫자의 기본 데이터 형식은 `Double`되며 키워드 `True` 및 `False` `Boolean` 상수를 지정 합니다.  
  
## <a name="literals-and-type-coercion"></a>리터럴 및 형식 강제 변환  
 경우에 따라 리터럴을 특정 데이터 형식으로 강제 지정할 수 있습니다. 예를 들어 `Decimal`형식의 변수에 특히 긴 정수 리터럴 값을 할당 하는 경우입니다. 다음 예에서는 오류를 생성 합니다.  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 리터럴 표현에서 발생 하는 오류입니다. `Decimal` 데이터 형식에는이 값이 너무 클 수 있지만 리터럴은 암시적으로 `Long`으로 표현 됩니다.  
  
 리터럴를 특정 데이터 형식으로 강제 변환할 수 있습니다. 여기에는 형식 문자를 추가 하거나 묶기 문자 내에 배치 하는 방법입니다. 형식 문자 또는 바깥쪽 문자는 문자를 사용 하지 않고 리터럴 앞뒤에 바로 앞 이나 뒤에와 야 합니다.  
  
 이전 예제를 사용 하려면 `D` 형식 문자를 리터럴에 추가 하 여 `Decimal`으로 표시 되도록 할 수 있습니다.  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 다음 예제에서는 형식 문자 및 묶기 문자를 올바르게 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 다음 표에서는 Visual Basic에서 사용할 수 있는 바깥쪽 문자 및 형식 문자를 보여 줍니다.  
  
|데이터 형식|묶기 문자|추가 된 형식 문자|  
|---|---|---|  
|`Boolean`|(없음)|(없음)|  
|`Byte`|(없음)|(없음)|  
|`Char`|"|C|  
|`Date`|#|(없음)|  
|`Decimal`|(없음)|D 또는 @|  
|`Double`|(없음)|R 또는 #|  
|`Integer`|(없음)|I 또는%|  
|`Long`|(없음)|L 또는 &|  
|`Short`|(없음)|S|  
|`Single`|(없음)|F 또는!|  
|`String`|"|(없음)|  
  
## <a name="see-also"></a>참고 항목

- [사용자 정의 상수](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit 문](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)
- [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
