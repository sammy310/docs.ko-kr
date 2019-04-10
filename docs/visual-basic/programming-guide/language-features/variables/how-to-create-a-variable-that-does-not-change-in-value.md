---
title: '방법: (Visual Basic) 값이 변경 되지 않는 변수 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: 7180e5141572d219ed02c57103e9d4b80cde536e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342936"
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>방법: (Visual Basic) 값이 변경 되지 않는 변수 만들기
해당 값을 변경 하지 않는 변수의 개념 모순 되 게 나타날 수 있습니다. 상수 불가능 한 경우에 있고 변수를 fixed 값을 가진 것이 유용 합니다. 이러한 경우에 사용 하 여 멤버 변수를 정의할 수 있습니다 합니다 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.  
  
 사용할 수 없습니다는 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 다음과 같은 경우에서 상수 값을 할당 합니다.  
  
-   `Const` 문에서 사용 하려는 데이터 형식을 허용 하지 않는  
  
-   컴파일 타임에 값을 모르는  
  
-   컴파일 시간에 상수 값을 계산할 수 없습니다  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>값이 변경 되지 않는 변수를 만들려면  
  
1. 모듈 수준에서 멤버 변수를 선언 합니다 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md), 포함 합니다 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     지정할 수 있습니다 `ReadOnly` 멤버 변수 에서만. 즉, 기존 프로시저 외부의 모듈 수준 변수를 정의 해야 합니다.  
  
2. 컴파일 시간에 단일 문에서 값을 계산할 수, 하는 경우에 초기화 절을 사용 합니다 `Dim` 문입니다. 수행 합니다 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 등호를 사용 하 여 절 (`=`) 식 뒤에. 컴파일러는 상수 값이이 식을 평가할 수 있어야 합니다.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     값을 할당할 수 있습니다는 `ReadOnly` 변수 한 번만 합니다. 이렇게 하면 코드가 없습니다. 해당 값을 변경 수 있습니다.  
  
     컴파일 타임에 값을 알지 못하는 하거나 단일 문에서 컴파일 시간에 계산할 수 없습니다. 생성자에서 런타임 시 계속 할당할 수 있습니다. 이 작업을 수행 하려면 선언 해야 합니다 `ReadOnly` 클래스 또는 구조 수준에서 변수입니다. 해당 클래스 또는 구조체에 대 한 생성자에서 변수의 고정된 값을 계산 하 고 생성자에서 반환 하기 전에를 변수에 할당 합니다.  
  
## <a name="see-also"></a>참고자료

- [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)
- [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)
