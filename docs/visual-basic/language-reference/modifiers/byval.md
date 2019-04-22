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
ms.openlocfilehash: 5e534eac2300327d4c54c5ce93d8b2c6c538e794
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832499"
---
# <a name="byval-visual-basic"></a>ByVal(Visual Basic)
이러한 방식으로 호출된 된 프로시저 또는 속성을 인수의 기반이 되는 호출 코드에서 변수 값을 변경할 수는 인수로 전달 되도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 된 `ByVal` 전달 메커니즘은 참조 형식 인수를 사용 하 여 매개 변수입니다. 예에서는 인수가 `c1`, 클래스의 인스턴스 `Class1`합니다. `ByVal` 절차의 코드 참조의 기본 값을 변경 하는 것을 금지 `c1`에 액세스할 수 있는 필드와 속성을 보호 되지 않습니다 하지만 `c1`합니다.  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a>참고자료

- [C++ 키워드](../../../visual-basic/language-reference/keywords/index.md)
- [값 또는 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
