---
title: Visual Basic의 범위
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823547"
---
# <a name="scope-in-visual-basic"></a>Visual Basic의 범위
합니다 *범위* 선언 된 요소의 이름을 한정 하거나 통하지 않고를 참조할 수 있는 모든 코드의 집합입니다는 [Imports 문 (.NET Namespace 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)합니다. 요소는 다음 수준 중 하나에서 범위를 포함할 수 있습니다.  
  
|수준|설명|  
|-----------|-----------------|  
|블록 범위|선언 된 블록 코드 에서만 사용할 수 있습니다.|  
|프로시저 범위|이전에 선언 된 프로시저 내에서 모든 코드에 사용할 수 있습니다.|  
|모듈 범위|모듈, 클래스 또는 구조체 선언 되는 모든 코드에 사용할 수 있습니다.|  
|Namespace 범위|이전에 선언 된 네임 스페이스의 모든 코드에 사용할 수 있습니다.|  
  
 이러한 수준의 넓은 범위 (네임 스페이스), 가장 좁은 (블록)에서 범위 진행률 위치 *가장 좁은 범위* 한정자 없이 요소를 참조할 수 있는 코드의 최소 집합을 의미 합니다. 자세한 내용은이 페이지에서 "범위 수준"을 참조 하세요.  
  
## <a name="specifying-scope-and-defining-variables"></a>범위를 지정 하 고 변수를 정의 합니다.  
 선언할 때 요소의 범위를 지정 합니다. 범위는 다음 요인에 따라 달라질 수 있습니다.  
  
-   요소를 선언한 지역 (블록, 절차, 모듈, 클래스 또는 구조체)  
  
-   요소 선언을 포함 하는 네임 스페이스  
  
-   요소에 대 한 선언 하는 액세스 수준  
  
 이렇게 하기 때문에 이름은 같지만 다른 범위를 사용 하 여 변수를 정의 하는 경우 주의 예기치 않은 결과가 발생할 수 있습니다. 자세한 내용은 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하세요.  
  
## <a name="levels-of-scope"></a>범위 수준  
 프로그래밍 요소를 선언 하는 지역에서 사용할 수 있습니다. 동일한 지역에 모든 코드 요소에 해당 이름을 한정 하지 않고 참조할 수 있습니다.  
  
### <a name="block-scope"></a>블록 범위  
 블록의 시작 및 종료 같은 선언문에 묶인 문 집합 같습니다.  
  
-   `Do` 및 `Loop`  
  
-   `For` [`Each`] 및 `Next`  
  
-   `If` 및 `End If`  
  
-   `Select` 및 `End Select`  
  
-   `SyncLock` 및 `End SyncLock`  
  
-   `Try` 및 `End Try`  
  
-   `While` 및 `End While`  
  
-   `With` 및 `End With`  
  
 블록 내에서 변수를 선언 하는 경우 해당 블록 내 에서만 사용할 수 있습니다. 다음 예제에서는 정수 변수의 범위에에서 `cube` 간에 블록입니다 `If` 하 고 `End If`를 더 이상 참조할 수 없습니다 및 `cube` 실행 블록 밖으로 전달 하는 경우.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  변수의 범위는 블록으로 제한 된 경우에 해당 수명은 전체 절차의 합니다. 블록 절차 중 한 번 입력 하는 경우 각 블록 변수는 이전 값을 유지 합니다. 이 경우 예기치 않은 결과 방지 하려면 블록의 시작 부분에서 블록 변수를 초기화 하는 것이 좋습니다.  
  
### <a name="procedure-scope"></a>프로시저 범위  
 프로시저 내에서 선언 된 요소에는 프로시저 밖에 서 사용할 수 없는 경우 선언을 포함 하는 프로시저에만 사용할 수 있습니다. 이 수준에서 변수가 라고도 *지역 변수*합니다. 사용 하 여 선언 합니다 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)과 함께 또는 없이 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 키워드입니다.  
  
 프로시저 및 블록 범위 밀접 한 관련이 있습니다. 프로시저 내의 하지만 해당 절차 내에서 모든 블록 외부 변수를 선언 하면 변수의 블록 범위를 블록 전체 프로시저 인 것으로 생각할 수 있습니다.  
  
> [!NOTE]
>  경우에 모든 로컬 요소를 `Static` 변수는 표시 되는 프로시저 전용입니다. 사용 하는 모든 요소를 선언할 수 없습니다는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 프로시저 내에서 키워드입니다.  
  
### <a name="module-scope"></a>모듈 범위  
 편의상 라는 단일 용어로 *모듈 수준* 모듈, 클래스 및 구조에도 똑같이 적용 됩니다. 모든 프로시저 또는 블록 외부에서 하지만 모듈, 클래스 또는 구조체 내의 선언문을 배치 하 여이 수준의 요소를 선언할 수 있습니다.  
  
 모듈 수준에서 선언, 하는 경우 원하는 액세스 수준을 범위를 결정 합니다. 모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 범위를도 영향을 줍니다.  
  
 선언 하는 요소 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 액세스 수준은 해당 모듈의 모든 절차 아니라 다른 모듈의에서 코드에서는 사용할 수 있습니다. 합니다 `Dim` 문은 모듈 수준에서 기본값은 `Private` 액세스 수준 키워드를 사용 하지 않는 경우. 그러나 가능 범위 및 액세스 수준 보다 명확 하 게 사용 하 여 합니다 `Private` 키워드는 `Dim` 문입니다.  
  
 다음 예제에서는 모듈에 정의 된 모든 프로시저 문자열 변수를 참조할 수 있습니다 `strMsg`합니다. 두 번째 프로시저를 호출 하는 경우 문자열 변수의 내용을 표시 `strMsg` 대화 상자에서.  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a>Namespace 범위  
 모듈 수준 사용 하 여 요소를 선언 하는 경우는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 요소가 선언 된 네임 스페이스 모든 프로시저에 사용할 키워드입니다. 위의 예제에서는 문자열 변수를 다음과 같이 변경 하면 `strMsg` 선언의 네임 스페이스에 있는 모든 코드에서 참조할 수 있습니다.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 Namespace 범위는 중첩 된 네임 스페이스를 포함합니다. 네임 스페이스 내에서 사용할 수 있는 요소는 네임 스페이스 내에 중첩 된 모든 네임 스페이스 내에서 사용할 수 이기도 합니다.  
  
 프로젝트에 없는 경우 모든 [Namespace 문](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, 프로젝트의 모든 항목은 동일한 네임 스페이스입니다. 이 예에서 네임 스페이스 범위는 프로젝트 범위로 생각할 수 있습니다. `Public` 모듈, 클래스 또는 구조 요소에서 해당 프로젝트를 참조 하는 모든 프로젝트에 사용할 수 있습니다.  
  
## <a name="choice-of-scope"></a>범위 선택  
 변수를 선언할 때 유지 해야 염두에서 다음 사항을 범위를 선택 합니다.  
  
### <a name="advantages-of-local-variables"></a>지역 변수의 장점  
 지역 변수는 다음과 같은 이유로 적합 한 모든 종류의 임시 계산은:  
  
-   **이름 충돌 방지 합니다.** 지역 변수 이름 충돌을 쉽게 받지 않습니다. 예를 들어 라는 변수를 포함 하는 몇 가지 다른 프로시저를 만들 수 있습니다 `intTemp`합니다. 각 `intTemp` 지역 변수로 선언 된 각 프로시저 자체 버전에만 인식의 `intTemp`합니다. 하나의 프로시저는 로컬 값을 변경할 수 있습니다 `intTemp` 영향을 주지 않고 `intTemp` 다른 프로시저에서 변수입니다.  
  
-   **메모리 사용량** 지역 변수는 해당 프로시저가 실행 되는 동안에 메모리를 사용 합니다. 프로시저가 호출 코드에 반환 되는 메모리 해제 됩니다. 이와 반대로 [공유](../../../../visual-basic/language-reference/modifiers/shared.md) 하 고 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 변수 응용 프로그램 실행이 중지 될 때까지 메모리 리소스를 소비, 따라서 필요한 경우에 사용 합니다. *인스턴스 변수* 는 로컬 변수를 보다 효율적이 지 않지만 보다 효율적 해당 인스턴스는 계속 존재 하는 동안 메모리 소비 `Shared` 또는 `Static` 변수입니다.  
  
### <a name="minimizing-scope"></a>범위를 최소화합니다.  
 일반적으로 변수 또는 상수를 선언할 때 최대한으로 좁은 범위를 확인 하려면이 좋은 프로그래밍 방법 (블록 범위는 좁음). 이 메모리를 절약 하는 데 도움이 됩니다 하 고 변수를 잘못 참조 코드의 가능성을 최소화 합니다. 변수를 선언 해야 마찬가지로 [정적](../../../../visual-basic/language-reference/modifiers/static.md) 경우에 프로시저 호출 하는 동안 값을 유지 해야 합니다.  
  
## <a name="see-also"></a>참고자료

- [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [방법: 변수의 범위 제어](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
