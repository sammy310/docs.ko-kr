---
title: '>>= 연산자(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator >>= [Visual Basic]
- compound assignment statements [Visual Basic]
- '>>= operator [Visual Basic]'
ms.assetid: 2bcd9abb-7a8c-4229-b75d-8816ff1dc700
ms.openlocfilehash: 1076ce62077391f2c88ebdd621d1dbd6fb40d647
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982386"
---
# <a name="-operator-visual-basic"></a>>> = 연산자 (Visual Basic)
변수 또는 속성의 값에 산술 오른쪽 시프트를 수행 하 고 해당 변수 또는 속성으로 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty >>= amount  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 변수 또는 정수 계열 형식의 속성 (`SByte`, `Byte`, `Short`, `UShort`를 `Integer`를 `UInteger`를 `Long`, 또는 `ULong`).  
  
 `amount`  
 필수 요소. 숫자 식으로 확대 되는 데이터 형식의 `Integer`합니다.  
  
## <a name="remarks"></a>설명  
 왼쪽된에 있는 요소는 `>>=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `>>=` 연산자는 변수 또는 속성의 값에 산술 오른쪽 시프트를 먼저 수행 합니다. 연산자는 다음 변수 또는 속성으로 해당 작업의 결과 할당합니다.  
  
 산술 shifts 순환있지 않습니다 즉, 결과의 한쪽 끝에서 벗어나 이동한 비트는 반대쪽 다시 도입 되지 않습니다. 산술 오른쪽 시프트에서 가장 오른쪽 비트 위치를 넘어 이동 하는 비트는 무시 되 고 왼쪽에 있는 비트 비워진 왼쪽 비트 위치로 전파 됩니다. 즉 `variableorproperty` 음수 값을 가진 비워진된 위치 중 하나로 설정 됩니다. 경우 `variableorproperty` 이 양수인 경우 또는 해당 데이터 형식이 부호 없는 형식이 하는 경우 비워진된 위치 0으로 설정 됩니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 [>> 연산자](../../../visual-basic/language-reference/operators/right-shift-operator.md) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 오버 로드 된 `>>` 연산자의 동작에 영향을 줍니다는 `>>=` 연산자입니다. 코드를 사용 하는 경우 `>>=` 클래스나 구조체에 오버 로드에서 `>>`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 `>>=` 비트 패턴의 시프트 연산자는 `Integer` 오른쪽으로 지정 된 크기 및 결과 변수에 할당 변수입니다.  
  
 [!code-vb[VbVbalrOperators#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>참고자료

- [>> 연산자](../../../visual-basic/language-reference/operators/right-shift-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
