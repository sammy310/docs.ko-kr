---
title: ByVal(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433810"
---
# <a name="byval-visual-basic"></a>ByVal(Visual Basic)
호출 된 프로시저 또는 속성이 호출 코드에서 인수를 기반으로 하는 변수의 값을 변경할 수 없도록 인수를 [값으로](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)전달 하도록 지정 합니다. 한정자를 지정 하지 않으면 기본적으로 ByVal이 지정 됩니다.
  
## <a name="remarks"></a>설명  
 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 참조 형식 인수를 사용 `ByVal` 하 여 매개 변수 전달 메커니즘을 사용 하는 방법을 보여 줍니다. 예제에서 인수 `c1`는 클래스 `Class1`의 인스턴스입니다. `ByVal`프로시저의 코드가 참조 인수 `c1`의 기본 값을 변경 하는 것을 방지 하지만의 `c1`액세스 가능 필드와 속성은 보호 하지 않습니다.  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>참고자료

- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [값 또는 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
