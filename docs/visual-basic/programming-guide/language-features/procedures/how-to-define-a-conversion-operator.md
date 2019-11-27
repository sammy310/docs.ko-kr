---
title: 'How to: Define a Conversion Operator'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344895"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>방법: 변환 연산자 정의(Visual Basic)
클래스 또는 구조체를 정의한 경우 클래스 또는 구조체의 형식과 다른 데이터 형식 (예: `Integer`, `Double`또는 `String`) 사이에 형식 변환 연산자를 정의할 수 있습니다.  
  
 형식 변환을 클래스 또는 구조체 내에서 [CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 프로시저로 정의 합니다. 모든 변환 프로시저는 `Public Shared`해야 하며 각각은 [확대](../../../../visual-basic/language-reference/modifiers/widening.md) / [축소](../../../../visual-basic/language-reference/modifiers/narrowing.md)를 지정 해야 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `digit` 구조체와 `Byte`간에 변환 연산자를 정의 합니다.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 다음 코드를 사용 하 여 `digit` 구조를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>참고 항목

- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
- [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
