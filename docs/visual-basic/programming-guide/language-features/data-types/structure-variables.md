---
title: 구조체 변수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663390"
---
# <a name="structure-variables-visual-basic"></a>구조체 변수(Visual Basic)
구조를 만든 후에 해당 형식으로 프로시저 수준 및 모듈 수준 변수를 선언할 수 있습니다. 예를 들어, 컴퓨터 시스템에 대 한 정보를 기록 하는 구조를 만들 수 있습니다. 다음은 이에 대한 예입니다.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 이제 형식의 변수를 선언할 수 있습니다. 다음 선언은이 설명 합니다.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  클래스와 모듈에서 선언 된 구조체를 사용 하 여 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 기본적으로 공용 액세스 합니다. 비공개 구조를 하려는 경우 사용 하 여 선언 하 고 있는지 확인 합니다 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드입니다.  
  
## <a name="access-to-structure-values"></a>구조 값에 대 한 액세스  
 지정 하 고 요소의 구조 변수에서 값을 검색을 설정 하 고 개체의 속성 가져오기를 사용 하 여 동일한 구문을 사용 합니다. 멤버 액세스 연산자를 배치 (`.`) 구조 변수 이름 사이의 요소 이름입니다. 다음 예제에서는 액세스 형식으로 이전에 선언 된 변수에 요소의 `systemInfo`합니다.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>구조체 변수를 할당합니다.  
 둘 다 동일한 구조체 형식의 경우 다른 하나의 변수를 할당할 수도 있습니다. 이 다른의 해당 요소에 한 구조체의 모든 요소를 복사합니다. 다음 선언은이 설명 합니다.  
  
```  
yourSystem = mySystem  
```  
  
 구조 요소 인지 참조 형식 등을 `String`, `Object`, 또는 데이터에 대 한 포인터 배열에 복사 됩니다. 이전 예제의 경우 `systemInfo` 앞의 예제에서 포인터 복사 개체 변수를 포함 했습니다 `mySystem` 에 `yourSystem`, 한 구조체를 통해 개체의 데이터에 대 한 변경에 액세스할 때 적용 되는 및 다른 구조입니다.  
  
## <a name="see-also"></a>참고자료

- [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [복합 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [구조체](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [방법: 구조 선언](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [구조체 및 기타 프로그래밍 요소](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [구조체와 클래스](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure 문](../../../../visual-basic/language-reference/statements/structure-statement.md)
