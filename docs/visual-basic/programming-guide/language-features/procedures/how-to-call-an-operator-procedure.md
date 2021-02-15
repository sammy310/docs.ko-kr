---
description: '자세한 정보: 방법: 연산자 프로시저 호출 (Visual Basic)'
title: '방법: 연산자 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
ms.openlocfilehash: f58d12ac5e4c9071646073184f7824946c00b39b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472607"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>방법: 연산자 프로시저 호출(Visual Basic)

식에서 연산자 기호를 사용 하 여 연산자 프로시저를 호출 합니다. 변환 연산자의 경우 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 호출 하 여 값을 한 데이터 형식에서 다른 데이터 형식으로 변환 합니다.  
  
 연산자 프로시저를 명시적으로 호출 하지 않습니다. `CType`일반적으로 연산자를 사용 하는 것과 같은 방법으로 연산자 또는 함수를 대입문 또는 식에 사용 합니다. Visual Basic 연산자 프로시저에 대 한 호출을 수행 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
### <a name="to-call-an-operator-procedure"></a>연산자 프로시저를 호출 하려면  
  
1. 일반적인 방법으로 식에 연산자 기호를 사용 합니다.  
  
2. 피연산자의 데이터 형식이 연산자에 적합 하 고 올바른 순서로 되어 있어야 합니다.  
  
3. 연산자는 예상 대로 식의 값에 기여 합니다.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>변환 연산자 프로시저를 호출 하려면  
  
1. `CType`식 내에서를 사용 합니다.  
  
2. 피연산자의 데이터 형식이 변환에 적합 하 고 올바른 순서 대로 되어 있어야 합니다.  
  
3. `CType` 변환 연산자 프로시저를 호출 하 고 변환 된 값을 반환 합니다.  
  
## <a name="example"></a>예  

 다음 예에서는 두 개의 <xref:System.TimeSpan> 구조체를 만들고 함께 추가 하 고 그 결과를 세 번째 구조에 저장 합니다 <xref:System.TimeSpan> . <xref:System.TimeSpan>구조는 여러 표준 연산자를 오버 로드 하는 연산자 프로시저를 정의 합니다.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 는 <xref:System.TimeSpan> 표준 연산자를 오버 로드 하기 때문에 `+` 이전 예에서는의 값을 계산할 때 연산자 프로시저를 호출 합니다 `combinedSpan` .  
  
 대화 연산자 프로시저를 호출 하는 예제는 [방법: 연산자를 정의 하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)을 참조 하세요.  
  
## <a name="compile-the-code"></a>코드 컴파일  

 사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다.  
  
## <a name="see-also"></a>추가 정보

- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Structure 문](../../../language-reference/statements/structure-statement.md)
- [방법: 구조 선언](../data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
