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
ms.openlocfilehash: 8daf6600f59cea343e0d02b99632b92ce4bf3183
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875480"
---
# <a name="byval-visual-basic"></a>ByVal(Visual Basic)

호출 된 프로시저 또는 속성이 호출 코드에서 인수를 기반으로 하는 변수의 값을 변경할 수 없도록 인수를 [값으로](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)전달 하도록 지정 합니다. 한정자를 지정 하지 않으면 기본적으로 ByVal이 지정 됩니다.

> [!NOTE]
> 기본값 이기 때문에 메서드 시그니처에서 키워드를 명시적으로 지정 하지 않아도 `ByVal` 됩니다. 이 경우 잡음이 있는 코드를 생성 하 고 기본값이 아닌 `ByRef` 키워드가 간과 되는 경우가 많습니다.

## <a name="remarks"></a>설명

 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.

 [Declare 문](../statements/declare-statement.md)

 [Function 문](../statements/function-statement.md)
  
 [Operator Statement](../statements/operator-statement.md)
  
 [Property Statement](../statements/property-statement.md)
  
 [Sub 문](../statements/sub-statement.md)

## <a name="example"></a>예제

 다음 예제에서는 `ByVal` 참조 형식 인수를 사용 하 여 매개 변수 전달 메커니즘을 사용 하는 방법을 보여 줍니다. 예제에서 인수는 `c1` 클래스의 인스턴스입니다 `Class1` . `ByVal` 프로시저의 코드가 참조 인수의 기본 값을 변경 하는 것을 방지 `c1` 하지만의 액세스 가능 필드와 속성은 보호 하지 않습니다 `c1` .

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a>참조

- [키워드](../keywords/index.md)
- [값 또는 참조로 인수 전달](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
