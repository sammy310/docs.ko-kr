---
title: '방법: 연산자를 정의하는 클래스 사용'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: 083916a420bf4ad182536363ea46448f6b4c1da5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071354"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>방법: 연산자를 정의하는 클래스 사용(Visual Basic)

자체 연산자를 정의 하는 클래스 또는 구조체를 사용 하는 경우 Visual Basic에서 해당 연산자에 액세스할 수 있습니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
## <a name="example"></a>예제  

 다음 예에서는 sql <xref:System.Data.SqlTypes.SqlString> 문자열과 Visual Basic 문자열 사이에서 양방향으로 변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))를 정의 하는 sql 구조에 액세스 합니다. Sql 문자열 식을 사용 하 여 `CType(` *SQL string expression* `String)` sql 문자열을 Visual Basic 문자열로 변환 하 고 `CType(` *문자열 식을 Visual Basic*하 여 <xref:System.Data.SqlTypes.SqlString> `)` 다른 방향으로 변환 합니다.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString>구조는에서로 변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))를 정의 하 `String` <xref:System.Data.SqlTypes.SqlString> 고 다른에서 <xref:System.Data.SqlTypes.SqlString> 로 변환 `String` 합니다. 에를 할당 하는 문은 `title` `jobTitle` 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출은 두 번째 연산자를 사용 합니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  

 사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다. 클래스 또는 구조체에서 오버 로드에 사용할 수 있는 모든 연산자를 정의 했다고 가정해 서는 안 됩니다. 사용 가능한 연산자 목록은 [Operator 문](../../../language-reference/statements/operator-statement.md)을 참조 하세요.  
  
 `Imports`소스 파일의 시작 부분에 SQL 문자열에 대 한 적절 한 문을 포함 합니다 (이 경우 <xref:System.Data.SqlTypes> ).  
  
 프로젝트에는 System.object와 System.XML에 대 한 참조가 있어야 합니다.  
  
## <a name="see-also"></a>참조

- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Structure 문](../../../language-reference/statements/structure-statement.md)
- [방법: 구조 선언](../data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
