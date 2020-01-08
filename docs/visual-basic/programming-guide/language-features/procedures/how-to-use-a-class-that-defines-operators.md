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
ms.openlocfilehash: 455c839702b90738ec5aea37c1b09d72eba42ff4
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347885"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>방법: 연산자를 정의하는 클래스 사용(Visual Basic)
자체 연산자를 정의 하는 클래스 또는 구조체를 사용 하는 경우 Visual Basic에서 해당 연산자에 액세스할 수 있습니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
## <a name="example"></a>예  
 다음 예에서는 sql 문자열과 Visual Basic 문자열 사이에서 양방향으로 변환 연산자 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 정의 하는 sql 구조 <xref:System.Data.SqlTypes.SqlString>에 액세스 합니다. Sql 문자열 *식*`CType(`를 사용 하 여 sql 문자열을 Visual Basic 문자열로 변환 하 고 Visual Basic *문자열 식*`CType(`<xref:System.Data.SqlTypes.SqlString>를 사용 하 여 다른 방향으로 변환할 `String)` 있습니다.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 <xref:System.Data.SqlTypes.SqlString> 구조는 `String`에서 <xref:System.Data.SqlTypes.SqlString> 사이에 변환 연산자 ([CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md))를 정의 하 고 다른 <xref:System.Data.SqlTypes.SqlString>에서 `String`로 변환 합니다. `jobTitle`에 `title`를 할당 하는 문은 첫 번째 연산자를 사용 하 고 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 함수 호출은 두 번째 연산자를 사용 합니다.  
  
## <a name="compile-the-code"></a>코드 컴파일  
 사용 중인 클래스 또는 구조체에서 사용 하려는 연산자를 정의 해야 합니다. 클래스 또는 구조체에서 오버 로드에 사용할 수 있는 모든 연산자를 정의 했다고 가정해 서는 안 됩니다. 사용 가능한 연산자 목록은 [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)을 참조 하세요.  
  
 소스 파일의 시작 부분에 SQL 문자열에 대 한 적절 한 `Imports` 문을 포함 합니다 (이 경우 <xref:System.Data.SqlTypes>).  
  
 프로젝트에는 System.object 및 SYSTEM.XML에 대 한 참조가 있어야 합니다.  
  
## <a name="see-also"></a>참조

- [연산자 프로시저](./operator-procedures.md)
- [방법: 연산자 정의](./how-to-define-an-operator.md)
- [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [확장](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
