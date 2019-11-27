---
title: Get 문
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 9560faf90d531c32f104dbd053a7c1f5584cfb1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351180"
---
# <a name="get-statement"></a>Get 문
속성의 값을 검색 하는 데 사용 되는 `Get` 속성 프로시저를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attributelist`|(선택 사항) [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조 하십시오.|  
|`accessmodifier`|이 속성의 `Get` 및 `Set` 문 중 최대 하나에 대해 선택적입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [보호](../../../visual-basic/language-reference/modifiers/protected.md) 됨<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하세요.|  
|`statements`|(선택 사항) `Get` 속성 프로시저가 호출 될 때 실행 되는 하나 이상의 문입니다.|  
|`End Get`|필수입니다. `Get` 속성 프로시저의 정의를 종료 합니다.|  
  
## <a name="remarks"></a>주의  
 속성이 `WriteOnly`로 표시 되지 않은 경우 모든 속성에는 `Get` 속성 프로시저가 있어야 합니다. `Get` 프로시저는 속성의 현재 값을 반환 하는 데 사용 됩니다.  
  
 Visual Basic은 식에서 속성의 값을 요청할 때 속성의 `Get` 프로시저를 자동으로 호출 합니다.  
  
 속성 선언의 본문은 속성의 `Get` 및 [속성 문과](../../../visual-basic/language-reference/statements/property-statement.md) `End Property` 문 간의 `Set` 프로시저만 포함할 수 있습니다. 이러한 프로시저 이외의 항목은 저장할 수 없습니다. 특히 속성의 현재 값을 저장할 수 없습니다. 속성 프로시저 중 하나에 저장 하는 경우 다른 속성 프로시저에서 액세스할 수 없기 때문에이 값을 속성 외부에 저장 해야 합니다. 일반적인 방법은 속성과 같은 수준에서 선언 된 [전용](../../../visual-basic/language-reference/modifiers/private.md) 변수에 값을 저장 하는 것입니다. 속성이 적용 되는 속성 내에 `Get` 프로시저를 정의 해야 합니다.  
  
 `Get` 프로시저는 `Get` 문에서 `accessmodifier`를 사용 하지 않는 경우 포함 하는 속성의 액세스 수준으로 설정 됩니다.  
  
## <a name="rules"></a>규칙  
  
- **혼합 액세스 수준.** 읽기/쓰기 속성을 정의 하는 경우 필요에 따라 `Get` 또는 `Set` 프로시저에 대해 다른 액세스 수준을 지정할 수 있습니다. 이 작업을 수행 하는 경우 프로시저 액세스 수준이 속성의 액세스 수준 보다 더 제한적 이어야 합니다. 예를 들어 속성을 `Friend`선언 하는 경우 `Get` 프로시저 `Private`선언할 수 있지만 `Public`는 선언할 수 없습니다.  
  
     `ReadOnly` 속성을 정의 하는 경우 `Get` 프로시저는 전체 속성을 나타냅니다. 속성에 대해 두 개의 액세스 수준을 설정 하므로 `Get`에 대해 다른 액세스 수준을 선언할 수 없습니다.  
  
- **반환 형식입니다.** [Property 문은](../../../visual-basic/language-reference/statements/property-statement.md) 반환 하는 값의 데이터 형식을 선언할 수 있습니다. `Get` 프로시저는 해당 데이터 형식을 자동으로 반환 합니다. 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.  
  
     `Property` 문에서 `returntype`를 지정 하지 않는 경우 프로시저는 `Object`반환 합니다.  
  
## <a name="behavior"></a>동작  
  
- **프로시저에서 반환** `Get` 프로시저가 호출 코드로 반환 되 면 속성 값을 요청한 문 내에서 실행이 계속 됩니다.  
  
     `Get` 속성 프로시저는 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md) 중 하나를 사용 하거나 반환 값을 속성 이름에 할당 하 여 값을 반환할 수 있습니다. 자세한 내용은 [함수 문의](../../../visual-basic/language-reference/statements/function-statement.md)"반환 값"을 참조 하세요.  
  
     `Exit Property` 및 `Return` 문은 속성 프로시저에서 즉시 종료를 발생 시킵니다. 프로시저의 어디에 든 많은 `Exit Property` 및 `Return` 문이 표시 될 수 있으며 `Exit Property` 문과 `Return` 문을 혼합할 수 있습니다.  
  
- **반환 값입니다.** `Get` 프로시저에서 값을 반환 하려면 속성 이름에 값을 할당 하거나 [Return 문에](../../../visual-basic/language-reference/statements/return-statement.md)값을 포함 하면 됩니다. `Return` 문은 `Get` 프로시저 반환 값을 동시에 할당 하 고 프로시저를 종료 합니다.  
  
     속성 이름에 값을 할당 하지 않고 `Exit Property`를 사용 하는 경우 `Get` 프로시저는 속성의 데이터 형식에 대 한 기본값을 반환 합니다. 자세한 내용은 [함수 문의](../../../visual-basic/language-reference/statements/function-statement.md)"반환 값"을 참조 하세요.  
  
     다음 예제에서는 읽기 전용 속성 `quoteForTheDay` `quoteValue`개인 변수에 저장 된 값을 반환할 수 있는 두 가지 방법을 보여 줍니다.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>예제  
 다음 예에서는 `Get` 문을 사용 하 여 속성의 값을 반환 합니다.  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>참고 항목

- [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)
- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [연습: 클래스 정의](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
