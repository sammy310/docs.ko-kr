---
title: '방법: 변환 연산자 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 2fabcf6c6ceb38fe77d4eed4f02dcb5a5e447bf1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085674"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>방법: 변환 연산자 정의(Visual Basic)

클래스 또는 구조체를 정의한 경우 클래스 또는 구조체의 형식과 다른 데이터 형식 (예: `Integer` , 또는) 사이에 형식 변환 연산자를 정의할 수 있습니다 `Double` `String` .  
  
 형식 변환을 클래스 또는 구조체 내에서 [CType 함수](../../../language-reference/functions/ctype-function.md) 프로시저로 정의 합니다. 모든 변환 프로시저는 여야 `Public Shared` 하 고 각각은 [확대](../../../language-reference/modifiers/widening.md) / [축소](../../../language-reference/modifiers/narrowing.md)를 지정 해야 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 및 라는 구조체 간에 변환 연산자를 정의 합니다 `digit` `Byte` .  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 다음 코드를 사용 하 여 구조체를 테스트할 수 있습니다 `digit` .  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참조

- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../language-reference/statements/operator-statement.md)
- [Structure 문](../../../language-reference/statements/structure-statement.md)
- [방법: 구조 선언](../data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
