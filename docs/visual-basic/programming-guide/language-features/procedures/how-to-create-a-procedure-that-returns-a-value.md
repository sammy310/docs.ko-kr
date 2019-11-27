---
title: '방법: 값을 반환하는 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349717"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>방법: 값을 반환하는 프로시저 만들기(Visual Basic)
`Function` 프로시저를 사용 하 여 호출 코드에 값을 반환 합니다.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면  
  
1. 다른 프로시저 외부에서 `Function` 문을 사용 하 고 그 뒤에 `End Function` 문을 사용 합니다.  
  
2. `Function` 문에서 `Function` 키워드를 프로시저 이름과 함께 사용 하 고 매개 변수 목록을 괄호 안에 추가 합니다.  
  
3. `As` 절을 사용 하 여 괄호를 따라 반환 된 값의 데이터 형식을 지정 합니다.  
  
4. 프로시저의 코드 문을 `Function` 문과 `End Function` 문 사이에 놓습니다.  
  
5. `Return` 문을 사용 하 여 호출 코드에 값을 반환 합니다.  
  
     다음 `Function` 프로시저는 다른 두 변의 값을 고려 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     다음 예제에서는 `hypotenuse`에 대 한 일반적인 호출을 보여 줍니다.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [Sub 프로시저](./sub-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)
- [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
