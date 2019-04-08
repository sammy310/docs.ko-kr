---
title: 하위 식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5b26a091dc8eb7415702c3c2853a569324def7d5
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824613"
---
# <a name="sub-expression-visual-basic"></a>하위 식(Visual Basic)
매개 변수 및 서브루틴 람다 식을 정의 하는 코드를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`parameterlist`|선택 사항입니다. 프로시저의 매개 변수를 나타내는 로컬 변수 이름의 목록입니다. 괄호는 목록이 비어 있는 경우에 있어야 합니다. 자세한 내용은 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)을 참조하세요.|  
|`statement`|필수 요소. 단일 문입니다.|  
|`statements`|필수 요소. 문 목록입니다.|  
  
## <a name="remarks"></a>설명  
 A *람다 식* 이름을 없는 서브루틴 이며 하나 이상의 문을 실행 합니다. 어디서 나 람다 식을 사용할 수 있습니다는 사용할 수는 대리자 형식을 제외 하 고 인수로 `RemoveHandler`합니다. 대리자 및 람다 식 대리자를 사용 하 여 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [대리자 문](../../../visual-basic/language-reference/statements/delegate-statement.md) 하 고 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)합니다.  
  
## <a name="lambda-expression-syntax"></a>람다 식 구문  
 람다 식의 구문은 유사 표준 서브루틴의 합니다. 차이점은 다음과 같습니다.  
  
-   람다 식에 이름이 없습니다.  
  
-   람다 식을와 같은 한정자를 사용할 수 없습니다 `Overloads` 또는 `Overrides`합니다.  
  
-   한 줄 람다 식의 본문에는 식이 아닌 문 이어야 합니다. Sub 프로시저를 호출 하지만 function 프로시저를 호출 하지 본문 구성할 수 있습니다.  
  
-   람다 식에서 모든 매개 변수에 지정 된 데이터 형식 또는 모든 매개 변수를 유추할 수 있어야 합니다.  
  
-   선택 사항 및 `ParamArray` 매개 변수는 람다 식에서 허용 되지 않습니다.  
  
-   제네릭 매개 변수 람다 식에서 허용 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음은 콘솔에 값을 기록 하는 람다 식의 예입니다. 두 줄 및 여러 줄 람다 식 구문은 서브루틴을 보여 줍니다. 더 많은 예제를 참조 하세요 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)합니다.  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>참고자료

- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
- [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
