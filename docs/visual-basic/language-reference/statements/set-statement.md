---
title: Set 문(Visual Basic)
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
ms.openlocfilehash: cb0dc76d110f3e6a3ea3e74cc0bfb5a669b35396
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583229"
---
# <a name="set-statement-visual-basic"></a>Set 문(Visual Basic)
속성에 값을 할당 하는 데 사용 되는 `Set` 속성 프로시저를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 (선택 사항) [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.  
  
 `accessmodifier`  
 이 속성의 `Get` 및 `Set` 문 중 최대 하나에 대해 선택적입니다. 다음 중 하나일 수 있습니다.  
  
- [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.  
  
 `value`  
 필수 요소. 속성의 새 값을 포함 하는 매개 변수입니다.  
  
 `datatype`  
 @No__t_0 `On` 경우 필수입니다. @No__t_0 매개 변수의 데이터 형식입니다. 지정 된 데이터 형식은이 `Set` 문이 선언 된 속성의 데이터 형식과 동일 해야 합니다.  
  
 `statements`  
 (선택 사항) @No__t_0 속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다.  
  
 `End Set`  
 필수 요소. @No__t_0 속성 프로시저의 정의를 종료 합니다.  
  
## <a name="remarks"></a>주의  
 속성이 `ReadOnly`로 표시 되지 않은 경우 모든 속성에는 `Set` 속성 프로시저가 있어야 합니다. @No__t_0 프로시저는 속성의 값을 설정 하는 데 사용 됩니다.  
  
 Visual Basic는 대입문이 속성에 저장 될 값을 제공 하는 경우 속성의 `Set` 프로시저를 자동으로 호출 합니다.  
  
 Visual Basic는 속성을 할당 하는 동안 매개 변수를 `Set` 프로시저에 전달 합니다. @No__t_0에 대 한 매개 변수를 제공 하지 않으면 IDE (통합 개발 환경)에서 `value` 라는 암시적 매개 변수를 사용 합니다. 매개 변수는 속성에 할당 되는 값을 포함 합니다. 일반적으로이 값을 개인 지역 변수에 저장 하 고 `Get` 프로시저가 호출 될 때마다 반환 합니다.  
  
 속성 선언의 본문은 속성의 `Get` 및 [속성 문과](../../../visual-basic/language-reference/statements/property-statement.md) `End Property` 문 간의 `Set` 프로시저만 포함할 수 있습니다. 이러한 프로시저 이외의 항목은 저장할 수 없습니다. 특히 속성의 현재 값을 저장할 수 없습니다. 속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다. 일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장 하는 것입니다. 속성이 적용 되는 속성 내에 `Set` 프로시저를 정의 해야 합니다.  
  
 @No__t_0 프로시저는 `Set` 문에서 `accessmodifier`를 사용 하지 않는 경우 포함 하는 속성의 액세스 수준으로 설정 됩니다.  
  
## <a name="rules"></a>규칙  
  
- **혼합 액세스 수준.** 읽기/쓰기 속성을 정의 하는 경우 필요에 따라 `Get` 또는 `Set` 프로시저에 대해 다른 액세스 수준을 지정할 수 있습니다. 이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다. 예를 들어 속성을 `Friend` 선언 하는 경우 `Set` 프로시저 `Private` 선언할 수 있지만 `Public`는 선언할 수 없습니다.  
  
     @No__t_0 속성을 정의 하는 경우 `Set` 프로시저는 전체 속성을 나타냅니다. 속성에 대해 두 개의 액세스 수준을 설정 하므로 `Set`에 대해 다른 액세스 수준을 선언할 수 없습니다.  
  
## <a name="behavior"></a>동작  
  
- **속성 프로시저에서 반환** @No__t_0 프로시저가 호출 코드로 반환 되 면 저장 될 값을 제공한 문 다음에 실행이 계속 됩니다.  
  
     `Set` 속성 프로시저는 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md) 또는 [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)중 하나를 사용 하 여를 반환할 수 있습니다.  
  
     @No__t_0 및 `Return` 문은 속성 프로시저에서 즉시 종료를 발생 시킵니다. 프로시저의 어디에 든 많은 `Exit Property` 및 `Return` 문이 표시 될 수 있으며 `Exit Property` 문과 `Return` 문을 혼합할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Set` 문을 사용 하 여 속성의 값을 설정 합니다.  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a>참조

- [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)
- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
