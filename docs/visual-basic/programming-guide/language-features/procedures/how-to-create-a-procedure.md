---
description: '자세히 알아보기: 방법: 프로시저 만들기 (Visual Basic)'
title: '방법: 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: bca5ad24e845600642429273f6053787dd290b88
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472542"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>방법: 프로시저 만들기(Visual Basic)

시작 선언 문 ( `Sub` 또는 `Function` )과 끝 선언 문 ( `End Sub` 또는) 사이에 프로시저를 묶습니다 `End Function` . 프로시저의 모든 코드는 이러한 문 사이에 있습니다.

 프로시저는 다른 프로시저를 포함할 수 없으므로 시작 문과 종료 문은 다른 프로시저 외부에 있어야 합니다.

 다른 위치에서 동일한 작업을 수행 하는 코드가 있는 경우 작업을 한 번에 한 번 작성 한 다음 코드의 다른 위치에서 호출할 수 있습니다.

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>값을 반환 하지 않는 프로시저를 만들려면

1. 다른 프로시저 외부에서는 문을 사용 하 고 `Sub` `End Sub` 문을 사용 합니다.

2. `Sub`문에서 `Sub` 키워드를 프로시저 이름으로 따르고 매개 변수 목록을 괄호로 묶습니다.

3. 프로시저의 코드 문을 문과 문 사이에 `Sub` 놓습니다 `End Sub` .

### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면

1. 다른 프로시저 외부에서는 문을 사용 하 고 `Function` `End Function` 문을 사용 합니다.

2. `Function`문에서 `Function` 키워드를 프로시저 이름으로 따르고 매개 변수 목록을 괄호로 묶은 다음 `As` 반환 값의 데이터 형식을 지정 하는 절을 사용 합니다.

3. 프로시저의 코드 문을 문과 문 사이에 `Function` 놓습니다 `End Function` .

4. 문을 사용 `Return` 하 여 호출 코드에 값을 반환 합니다.

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>새 프로시저를 반복적인 코드 블록에 연결 하려면

1. 이전 코드에서 액세스할 수 있는 위치에 새 프로시저를 정의 해야 합니다.

2. 이전 반복적인 코드 블록에서 반복 작업을 수행 하는 문을 또는 프로시저를 호출 하는 단일 문으로 바꿉니다 `Sub` `Function` .

3. 프로시저에서 `Function` 값을 반환 하는 인 경우 호출 문이 반환 된 값을 사용 하 여 작업을 변수에 저장 하는 등의 작업을 수행 해야 합니다. 그렇지 않으면 값이 손실 됩니다.

## <a name="example"></a>예

 다음 `Function` 프로시저는 다른 두 변의 값을 지정 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>추가 정보

- [절차](index.md)
- [하위 프로시저](sub-procedures.md)
- [함수 프로시저](function-procedures.md)
- [속성 프로시저](property-procedures.md)
- [연산자 프로시저](operator-procedures.md)
- [프로시저 매개 변수 및 인수](procedure-parameters-and-arguments.md)
- [재귀 프로시저](recursive-procedures.md)
- [프로시저 오버로딩](procedure-overloading.md)
- [개체 및 클래스](../objects-and-classes/index.md)
- [개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)
