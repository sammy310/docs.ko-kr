---
title: '방법: 프로시저 (Visual Basic) 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 56099d334a03e85b816cf48983cbbead0784ef5b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320394"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>방법: 프로시저 (Visual Basic) 만들기
선언문의 시작 사이 프로시저를 묶습니다 (`Sub` 나 `Function`) 및 선언문의 끝 (`End Sub` 또는 `End Function`). 프로시저의 모든 코드가 이러한 문 사이 존재 합니다.  
  
 프로시저를 다른 프로시저 밖에 서 해당 시작 및 끝 문 이어야 하므로 다른 프로시저를 사용할 수 없습니다.  
  
 여러 위치에서 동일한 작업을 수행 하는 코드를 사용 하는 경우에 절차로 한 번 작업을 작성 수 있으며 다음 코드의 다른 위치에서 호출할 수 있습니다.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>값을 반환 하지 않는 프로시저를 만들려면  
  
1. 다른 프로시저 밖에 서 사용 하 여는 `Sub` 문 뒤에 `End Sub` 문입니다.  
  
2. 에 `Sub` 문을 따릅니다는 `Sub` 프로시저 이름이 매개 변수 목록 괄호를 사용 하 여 키워드.  
  
3. 간의 프로시저의 코드 문을 배치 합니다 `Sub` 및 `End Sub` 문입니다.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면  
  
1. 다른 프로시저 밖에 서 사용 하 여는 `Function` 문 뒤에 `End Function` 문입니다.  
  
2. 에 `Function` 문을 수행를 `Function` 키워드와 매개 변수 목록 괄호 안의 프로시저의 이름 차례로 `As` 반환 값의 데이터 형식을 지정 하는 절.  
  
3. 간의 프로시저의 코드 문을 배치 합니다 `Function` 및 `End Function` 문입니다.  
  
4. 사용 된 `Return` 호출 코드에 값을 반환 하는 문입니다.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>오래 되 고 반복적인 코드 블록을 사용 하 여 새 프로시저를 연결 하려면  
  
1. 이전 코드에 액세스할 수 있는 위치에 새 프로시저를 정의 해야 합니다.  
  
2. 이전 반복 코드 블록을 호출 하는 단일 문 사용 하 여 반복적인 작업을 수행 하는 문을 바꿉니다 합니다 `Sub` 또는 `Function` 프로시저입니다.  
  
3. 프로시저가 `Function` 값을 반환 하는 호출 문에서 반환된 된 값을 변수에 저장 하는 등을 사용 하 여 작업을 수행 합니다. 그러지 않으면 값이 손실 됩니다을 확인 합니다.  
  
## <a name="example"></a>예제  
 다음 `Function` 프로시저 제일 긴 쪽 또는 다른 두 가지 측면에 대 한 값이 지정 된 오른쪽 삼각형의 빗변을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [함수 프로시저](./function-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [재귀 프로시저](./recursive-procedures.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [개체 지향 프로그래밍 (Visual Basic)](../../concepts/object-oriented-programming.md)
