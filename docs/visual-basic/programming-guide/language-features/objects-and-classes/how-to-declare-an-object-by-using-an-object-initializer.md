---
title: '방법: 개체 이니셜라이저를 사용하여 개체 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347130"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>방법: 개체 이니셜라이저를 사용하여 개체 선언(Visual Basic)
개체 이니셜라이저를 사용 하면 단일 문에서 클래스의 인스턴스를 선언 하 고 인스턴스화할 수 있습니다. 또한 매개 변수가 있는 생성자를 호출 하지 않고 인스턴스의 멤버를 한 번에 하나 이상 초기화할 수 있습니다.  
  
 개체 이니셜라이저를 사용 하 여 명명 된 형식의 인스턴스를 만드는 경우 클래스에 대 한 매개 변수가 없는 생성자가 호출 된 다음 지정 된 순서로 지정 된 멤버를 초기화 합니다.  
  
 다음 절차에서는 세 가지 방법으로 `Student` 클래스의 인스턴스를 만드는 방법을 보여 줍니다. 클래스에는 이름, 성 및 클래스 year 속성이 있습니다. 세 선언 각각은 속성 `First` "Michael"로 설정 되 고, 속성 `Last` "Tucker"로 설정 되 고, 다른 모든 멤버가 기본값으로 설정 된 `Student`의 새 인스턴스를 만듭니다. 프로시저의 각 선언 결과는 개체 이니셜라이저를 사용 하지 않는 다음 예제와 동일 합니다.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 `Student` 클래스의 구현에 대 한 자세한 내용은 [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)를 참조 하세요. 해당 항목에서 코드를 복사 하 여 클래스를 설정 하 고 작업할 `Student` 개체 목록을 만들 수 있습니다.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>개체 이니셜라이저를 사용 하 여 명명 된 클래스의 개체를 만들려면  
  
1. 생성자를 사용 하기 위해 계획 한 것 처럼 선언을 시작 합니다.  
  
     `Dim student1 As New Student`  
  
2. `With`키워드를 입력 한 다음 중괄호에 초기화 목록을 입력 합니다.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. 초기화 목록에서 초기화 하려는 각 속성을 포함 하 고 초기 값을 할당 합니다. 속성 이름 앞에는 마침표가와 야 합니다.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     클래스의 멤버를 하나 이상 초기화할 수 있습니다.  
  
4. 또는 클래스의 새 인스턴스를 선언 하 고 여기에 값을 할당할 수 있습니다. 먼저 `Student`의 인스턴스를 선언 합니다.  
  
     `Dim student2 As Student`  
  
5. 일반적인 방법으로 `Student` 인스턴스 만들기를 시작 합니다.  
  
     `Dim student2 As Student = New Student`  
  
6. `With`를 입력 한 다음 개체 이니셜라이저를 입력 하 여 새 인스턴스의 멤버를 하나 이상 초기화 합니다.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. `As Student`를 생략 하 여 이전 단계에서 정의를 단순화할 수 있습니다. 이 작업을 수행 하는 경우 컴파일러는 `student3` 로컬 형식 유추를 사용 하 여 `Student` 인스턴스인지를 확인 합니다.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [방법: 항목 목록 만들기](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [개체 이니셜라이저: 명명된 형식과 익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
