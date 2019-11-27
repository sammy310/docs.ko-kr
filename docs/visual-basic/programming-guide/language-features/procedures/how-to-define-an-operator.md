---
title: '방법: 연산자 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: b99af8ff4d5428f1749bfc1a4c51a136f12405ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344870"
---
# <a name="how-to-define-an-operator-visual-basic"></a>방법: 연산자 정의(Visual Basic)
클래스 또는 구조체를 정의한 경우 피연산자 중 하나 또는 둘 모두가 클래스 또는 구조체의 형식인 경우 표준 연산자 (예: `*`, `<>`또는 `And`)의 동작을 정의할 수 있습니다.  
  
 클래스 또는 구조체 내에서 연산자 프로시저로 표준 연산자를 정의 합니다. 모든 연산자 프로시저는 `Shared``Public` 해야 합니다.  
  
 클래스 또는 구조체에서 연산자를 정의 하는 것을 연산자 *오버 로드* 라고도 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `height`라는 구조에 대해 `+` 연산자를 정의 합니다. 구조체는 피트와 인치로 측정 된 높이를 사용 합니다. 1 *인치* 는 2.54 센티미터이 고 1 *피트* 는 12 인치입니다. 정규화 된 값 (인치 < 12.0)을 보장 하기 위해 생성자는 *모듈로* 12 산술 연산을 수행 합니다. `+` 연산자는 생성자를 사용 하 여 정규화 된 값을 생성 합니다.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 다음 코드를 사용 하 여 `height` 구조를 테스트할 수 있습니다.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>참고자료

- [연산자 프로시저](./operator-procedures.md)
- [방법: 변환 연산자 정의](./how-to-define-a-conversion-operator.md)
- [방법: 연산자 프로시저 호출](./how-to-call-an-operator-procedure.md)
- [방법: 연산자를 정의하는 클래스 사용](./how-to-use-a-class-that-defines-operators.md)
- [Operator 문](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [방법: 구조체 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)
