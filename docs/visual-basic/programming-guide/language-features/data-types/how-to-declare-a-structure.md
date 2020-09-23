---
title: '방법: 구조 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bffdc5974eff6b71e0abc4780a61aa300769eed6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058549"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>방법: 구조체 선언(Visual Basic)

Structure [문을](../../../language-reference/statements/structure-statement.md)사용 하 여 구조체 선언을 시작 하 고 `End Structure` 문으로 종료 합니다. 이러한 두 문 사이에는 하나 이상의 *요소*를 선언 해야 합니다. 요소는 모든 데이터 형식이 될 수 있지만 하나 이상 비공유 변수 이거나 비공유 noncustom 이벤트 여야 합니다.  
  
 구조체 선언에서 구조체 요소를 초기화할 수 없습니다. 구조체 형식으로 변수를 선언 하는 경우 변수를 통해 값에 액세스 하 여 요소에 값을 할당 합니다.  
  
 구조와 클래스 간의 차이점에 대 한 설명은 [구조체 및 클래스](structures-and-classes.md)를 참조 하세요.  
  
 데모용으로 직원의 이름, 전화 내선 및 급여를 추적 하려는 상황을 고려해 보세요. 구조체를 사용 하면 단일 변수에서이 작업을 수행할 수 있습니다.  
  
### <a name="to-declare-a-structure"></a>구조체를 선언 하려면  
  
1. 구조체에 대 한 시작 및 종료 문을 만듭니다.  
  
     [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)또는 [Private](../../../language-reference/modifiers/private.md) 키워드를 사용 하 여 구조체의 액세스 수준을 지정 하거나를 기본값으로 지정할 수 있습니다 `Public` .  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. 구조 본문에 요소를 추가 합니다.  
  
     구조체에는 요소가 하나 이상 있어야 합니다. 모든 요소를 선언 하 고 해당 요소에 대 한 액세스 수준을 지정 해야 합니다. 키워드 없이 [Dim 문을](../../../language-reference/statements/dim-statement.md) 사용 하는 경우 액세스 가능성은 기본적으로로 설정 `Public` 됩니다.  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     `salary`앞의 예제에서 필드는 `Private` 를 포함 하는 클래스 에서도 구조체 외부에서 액세스할 수 없음을 의미 하는입니다. 그러나 프로시저는 이므로 `giveRaise` `Public` 구조 외부에서 호출할 수 있습니다. 마찬가지로 구조 외부에서 이벤트를 발생 시킬 수 있습니다 `salaryReviewTime` .  
  
     변수, `Sub` 프로시저 및 이벤트 외에도 구조에서 상수, 프로시저 및 속성을 정의할 수 있습니다 `Function` . 하나 이상의 인수를 사용 하는 경우 *기본 속성*으로 최대 하나의 속성을 지정할 수 있습니다. [공유](../../../language-reference/modifiers/shared.md) 프로시저를 사용 하 여 이벤트를 처리할 수 있습니다 `Sub` . 자세한 내용은 [방법: Visual Basic에서 기본 속성 선언 및 호출](../procedures/how-to-declare-and-call-a-default-property.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [데이터 형식](index.md)
- [기본 데이터 형식](elementary-data-types.md)
- [복합 데이터 형식](composite-data-types.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [구조체](structures.md)
- [데이터 형식 문제 해결](troubleshooting-data-types.md)
- [구조체 변수](structure-variables.md)
- [구조체 및 기타 프로그래밍 요소](structures-and-other-programming-elements.md)
- [구조체와 클래스](structures-and-classes.md)
- [사용자 정의 데이터 형식](../../../language-reference/data-types/user-defined-data-type.md)
