---
description: 다음에 대 한 자세한 정보:/= 연산자 (Visual Basic)
title: /= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: 3020372be18f554df18fa6dac539ab9d0b2f725e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666032"
---
# <a name="-operator-visual-basic"></a>/= 연산자(Visual Basic)

변수 또는 속성의 값을 식의 값으로 나누고 부동 소수점 결과를 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>부분  

 `variableorproperty`  
 필수 사항입니다. 임의의 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  

 연산자의 좌 변에 있는 요소는 `/=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.  
  
 연산자는 먼저 연산자의 왼쪽에 있는 `/=` 변수 또는 속성의 값을 연산자의 오른쪽에 있는 식의 값으로 나눕니다 (연산자의 왼쪽에 있는). 그런 다음 연산자는 해당 작업의 부동 소수점 결과를 변수나 속성에 할당 합니다.  
  
 이 문은 `Double` 왼쪽의 변수 또는 속성에 값을 할당 합니다. `Option Strict`가 이면 `On` 는 여야 `variableorproperty` 합니다 `Double` . `Option Strict`가 이면 `Off` Visual Basic 암시적 변환을 수행 하 고 결과 값을에 할당 합니다 `variableorproperty` .이 경우 런타임에 오류가 발생할 수 있습니다. 자세한 내용은 [확대/축소 변환](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [Option Strict 문](../statements/option-strict-statement.md)을 참조 하세요.  
  
## <a name="overloading"></a>오버로딩  

 [/연산자 (Visual Basic)](floating-point-division-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다. 연산자를 오버 로드 하면 `/` 연산자의 동작에 영향을 줍니다 `/=` . `/=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `/` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 다음 예에서는 연산자를 사용 하 여 `/=` 한 `Integer` 변수를 두 번째로 나누고 몫을 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>참고 항목

- [/연산자 (Visual Basic)](floating-point-division-operator.md)
- [\\= 연산자](integer-division-assignment-operator.md)
- [할당 연산자](assignment-operators.md)
- [산술 연산자](arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [문](../../programming-guide/language-features/statements.md)
