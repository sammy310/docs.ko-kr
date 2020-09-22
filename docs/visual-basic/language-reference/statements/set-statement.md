---
title: Set 문
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: b3524769567a56a87184bf916a3e5ccb1fd4fa1c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871751"
---
# <a name="set-statement-visual-basic"></a>Set 문(Visual Basic)

`Set`속성에 값을 할당 하는 데 사용 되는 속성 프로시저를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>부분  

 `attributelist`  
 선택 사항입니다. [특성 목록](attribute-list.md)을 참조 하십시오.  
  
 `accessmodifier`  
 `Get`이 속성의 및 문 중 최대 하나에 대해 선택적입니다 `Set` . 다음 중 하나일 수 있습니다.  
  
- [보호](../modifiers/protected.md)  
  
- [Friend](../modifiers/friend.md)  
  
- [개인](../modifiers/private.md)  
  
- `Protected Friend`  
  
 [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.  
  
 `value`  
 필수 사항입니다. 속성의 새 값을 포함 하는 매개 변수입니다.  
  
 `datatype`  
 필요한 경우 `Option Strict` 는 `On`합니다. 매개 변수의 데이터 형식 `value` 입니다. 지정 된 데이터 형식은이 문이 선언 된 속성의 데이터 형식과 동일 해야 합니다 `Set` .  
  
 `statements`  
 선택 사항입니다. 속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다 `Set` .  
  
 `End Set`  
 필수 사항입니다. 속성 프로시저의 정의를 종료 `Set` 합니다.  
  
## <a name="remarks"></a>설명  

 `Set`속성이로 표시 되지 않은 경우 모든 속성에 속성 프로시저가 있어야 합니다 `ReadOnly` . `Set`프로시저는 속성의 값을 설정 하는 데 사용 됩니다.  
  
 `Set`대입문은 속성에 저장 되는 값을 제공 하는 경우 속성의 프로시저를 자동으로 호출 Visual Basic 합니다.  
  
 Visual Basic는 속성을 할당 하는 동안 매개 변수를 프로시저에 전달 `Set` 합니다. 에 대 한 매개 변수를 제공 하지 않으면 `Set` IDE (통합 개발 환경)에서 라는 암시적 매개 변수를 사용 합니다 `value` . 매개 변수는 속성에 할당 되는 값을 포함 합니다. 일반적으로이 값을 private 지역 변수에 저장 하 고 프로시저가 호출 될 때마다 반환 `Get` 합니다.  
  
 속성 선언의 본문은 속성 `Get` `Set` [문과](property-statement.md) 문 사이에 속성의 및 프로시저만 포함할 수 있습니다 `End Property` . 이러한 프로시저 이외의 항목은 저장할 수 없습니다. 특히 속성의 현재 값을 저장할 수 없습니다. 속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다. 일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../modifiers/private.md) 변수에 값을 저장 하는 것입니다. `Set`속성이 적용 되는 속성 내에 프로시저를 정의 해야 합니다.  
  
 `Set`문에서를 사용 하지 않는 경우 프로시저는 포함 하는 속성의 액세스 수준으로 설정 `accessmodifier` `Set` 됩니다.  
  
## <a name="rules"></a>규칙  
  
- **혼합 액세스 수준.** 읽기/쓰기 속성을 정의 하는 경우 필요에 따라 또는 프로시저 중 하나에 다른 액세스 수준을 지정할 수 있습니다 `Get` `Set` . 이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다. 예를 들어 속성이 선언 된 경우 `Friend` 프로시저를 선언할 수 있지만는 선언할 수 `Set` `Private` 없습니다 `Public` .  
  
     속성을 정의 하는 경우 `WriteOnly` 프로시저는 `Set` 전체 속성을 나타냅니다. `Set`속성에 대해 두 개의 액세스 수준을 설정 하므로에 대해 다른 액세스 수준을 선언할 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
- **속성 프로시저에서 반환** `Set`프로시저가 호출 코드로 반환 될 때 저장 되는 값을 제공 하는 문 다음에 실행이 계속 됩니다.  
  
     `Set` 속성 프로시저는 [Return 문](return-statement.md) 또는 [Exit 문](exit-statement.md)중 하나를 사용 하 여를 반환할 수 있습니다.  
  
     `Exit Property`및 `Return` 문을 실행 하면 속성 프로시저에서 즉시 종료 됩니다. 프로시저의 모든 위치에는 개수와 `Exit Property` `Return` 문이 모두 표시 될 수 있으며 `Exit Property` 문과 문을 혼합할 수 있습니다 `Return` .  
  
## <a name="example"></a>예제  

 다음 예에서는 문을 사용 하 여 `Set` 속성의 값을 설정 합니다.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>참조

- [Get 문](get-statement.md)
- [Property Statement](property-statement.md)
- [Sub 문](sub-statement.md)
- [속성 프로시저](../../programming-guide/language-features/procedures/property-procedures.md)
