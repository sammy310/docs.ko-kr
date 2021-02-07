---
description: '다음에 대 한 자세한 정보:  <<= 연산자 (Visual Basic)'
title: <<= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: 40d0b69c3af672383230db5beadbcd3f3391db7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665642"
---
# <a name="-operator-visual-basic"></a>\<\<= 연산자 (Visual Basic)

변수 또는 속성 값에서 산술 왼쪽 시프트를 수행 하 고 결과를 다시 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>부분  

 `variableorproperty`  
 필수 사항입니다. 정수 계열 형식 ( `SByte` , `Byte` ,,,,, `Short` `UShort` 또는 `Integer` )의 `UInteger` `Long` 변수 또는 속성 `ULong` 입니다.  
  
 `amount`  
 필수 사항입니다. 로 확대 되는 데이터 형식의 숫자 식입니다 `Integer` .  
  
## <a name="remarks"></a>설명  

 연산자의 좌 변에 있는 요소는 `<<=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.  
  
 `<<=`연산자는 먼저 변수나 속성의 값에 산술 왼쪽 시프트를 수행 합니다. 그런 다음 연산자는 해당 작업의 결과를 해당 변수 또는 속성에 다시 할당 합니다.  
  
 산술 시프트는 순환 하지 않습니다. 즉, 결과의 한쪽 끝에서 이동 하는 비트가 다른 쪽 끝에서는 다시 계산 되지 않습니다. 산술 왼쪽 시프트에서 결과 데이터 형식의 범위를 벗어나 이동 하는 비트는 무시 되 고 오른쪽에서 비워진 비트 위치는 0으로 설정 됩니다.  
  
## <a name="overloading"></a>오버로딩  

 [<< 연산자](left-shift-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. 연산자를 오버 로드 하면 `<<` 연산자의 동작에 영향을 줍니다 `<<=` . `<<=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `<<` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 다음 예에서는 연산자를 사용 `<<=` 하 여 변수의 비트 패턴을 `Integer` 지정한 양만큼 왼쪽으로 이동 하 고 결과를 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>참고 항목

- [<< 연산자](left-shift-operator.md)
- [할당 연산자](assignment-operators.md)
- [비트 시프트 연산자](bit-shift-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [문](../../programming-guide/language-features/statements.md)
