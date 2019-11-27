---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351590"
---
# <a name="byval-visual-basic"></a>ByVal(Visual Basic)
호출 된 프로시저 또는 속성이 호출 코드에서 인수를 기반으로 하는 변수의 값을 변경할 수 없도록 인수를 [값으로](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)전달 하도록 지정 합니다. 한정자를 지정 하지 않으면 기본적으로 ByVal이 지정 됩니다.

> [!NOTE]
> 기본값 이기 때문에 메서드 시그니처에서 `ByVal` 키워드를 명시적으로 지정 하지 않아도 됩니다. 잡음이 있는 코드를 생성 하는 경향이 있으며 기본값이 아닌 `ByRef` 키워드가 간과 되는 경우가 많습니다.

## <a name="remarks"></a>주의
 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)

 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a>예제
 다음 예제에서는 참조 형식 인수를 사용 하 여 `ByVal` 매개 변수 전달 메커니즘을 사용 하는 방법을 보여 줍니다. 예제에서 인수는 `c1``Class1`클래스의 인스턴스입니다. `ByVal` 프로시저의 코드에서 참조 인수의 기본 값을 변경 하는 것을 방지 `c1`하 고 `c1`의 액세스 가능 필드와 속성은 보호 하지 않습니다.

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>참고 항목

- [키워드](../../../visual-basic/language-reference/keywords/index.md)
- [값 또는 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
