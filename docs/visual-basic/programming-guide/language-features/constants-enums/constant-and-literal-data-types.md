---
description: '다음에 대 한 자세한 정보: 상수 및 리터럴 데이터 형식 (Visual Basic)'
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
ms.openlocfilehash: e750b1e5746f935c7878e186d064060d0fa055dc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475437"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>상수 및 리터럴 데이터 형식(Visual Basic)

리터럴은 변수 값 또는 식의 결과 (예: 숫자 3 또는 문자열 "Hello")가 아니라 자체로 표현 되는 값입니다. 상수는 리터럴 자리를 사용 하 고 값이 변경 될 수 있는 변수와 달리 프로그램 전체에서 동일한 값을 유지 하는 의미 있는 이름입니다.  
  
 [Option 유추](../../../language-reference/statements/option-infer-statement.md) 는이 `Off` 고 [option Strict](../../../language-reference/statements/option-strict-statement.md) 는 이면 `On` 모든 상수를 데이터 형식으로 명시적으로 선언 해야 합니다. 다음 예제에서의 데이터 형식은 `MyByte` 데이터 형식으로 명시적으로 선언 됩니다 `Byte` .  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 `Option Infer`가 `On` 이거나 `Option Strict` 가 인 경우 `Off` 절을 사용 하 여 데이터 형식을 지정 하지 않고 상수를 선언할 수 있습니다 `As` . 컴파일러는 식의 형식에서 상수의 형식을 결정 합니다. 숫자 정수 리터럴은 기본적으로 데이터 형식으로 캐스팅 됩니다 `Integer` . 부동 소수점 숫자의 기본 데이터 형식은이 `Double` 고 키워드 `True` 와는 `False` 상수를 지정 합니다 `Boolean` .  
  
## <a name="literals-and-type-coercion"></a>리터럴 및 형식 강제 변환  

 경우에 따라 리터럴을 특정 데이터 형식으로 강제 지정할 수 있습니다. 예를 들어, 형식의 변수에 특히 긴 정수 리터럴 값을 할당 하는 경우 `Decimal` 입니다. 다음 예에서는 오류를 생성 합니다.  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 리터럴 표현에서 발생 하는 오류입니다. `Decimal`이 값은 데이터 형식에 포함 될 수 있지만 리터럴은 암시적으로로 표현 될 `Long` 수 없습니다.  
  
 리터럴를 특정 데이터 형식으로 강제 변환할 수 있습니다. 여기에는 형식 문자를 추가 하거나 묶기 문자 내에 배치 하는 방법입니다. 형식 문자 또는 바깥쪽 문자는 문자를 사용 하지 않고 리터럴 앞뒤에 바로 앞 이나 뒤에와 야 합니다.  
  
 이전 예제가 작동 하도록 하려면 형식 문자를 리터럴에 추가 하면 `D` 됩니다. 그러면 다음과 같이 표시 됩니다 `Decimal` .  
  
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
  
## <a name="see-also"></a>추가 정보

- [사용자 정의 상수](user-defined-constants.md)
- [방법: 상수 선언](how-to-declare-a-constant.md)
- [상수 개요](constants-overview.md)
- [Option Strict 문](../../../language-reference/statements/option-strict-statement.md)
- [Option Explicit 문](../../../language-reference/statements/option-explicit-statement.md)
- [열거형 개요](enumerations-overview.md)
- [방법: 열거형 선언](how-to-declare-enumerations.md)
- [열거형 및 이름 한정](enumerations-and-name-qualification.md)
- [데이터 형식](../../../language-reference/data-types/index.md)
- [상수 및 열거형](../../../language-reference/constants-and-enumerations.md)
