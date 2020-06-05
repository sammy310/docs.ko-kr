---
title: 반복기
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: bb19289c69f4c523363e88e91a58f37d232b07df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396235"
---
# <a name="iterator-visual-basic"></a>반복기(Visual Basic)
함수 또는 `Get` 접근자가 반복기 임을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 *반복기* 는 컬렉션에 대해 사용자 지정 반복을 수행 합니다. 반복기는 [Yield](../statements/yield-statement.md) 문을 사용 하 여 컬렉션의 각 요소를 한 번에 하나씩 반환 합니다. `Yield`문에 도달 하면 코드의 현재 위치가 유지 됩니다. 다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 반복기는 함수 또는 `Get` 속성 정의의 접근자로 구현할 수 있습니다. `Iterator`한정자는 반복기 함수 또는 접근자의 선언에 나타납니다 `Get` .  
  
 For Each ...를 사용 하 여 클라이언트 코드에서 반복기를 호출 합니다. [ 다음 문](../statements/for-each-next-statement.md).  
  
 반복기 함수 또는 접근자의 반환 형식은 `Get` ,, 또는 일 수 있습니다 <xref:System.Collections.IEnumerable> <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Collections.IEnumerator> <xref:System.Collections.Generic.IEnumerator%601> .  
  
 반복기에는 `ByRef` 매개 변수를 사용할 수 없습니다.  
  
 반복기는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.  
  
 반복기는 익명 함수 일 수 있습니다. 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.  
  
## <a name="usage"></a>사용량  
 `Iterator` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
- [Function 문](../statements/function-statement.md)  
  
- [Property Statement](../statements/property-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 반복기 함수를 보여 줍니다. 반복기 함수에 `Yield` [에 대 한 문이 있습니다. Next](../statements/for-next-statement.md) 루프. 의 각 문 본문 [에 대 한](../statements/for-each-next-statement.md) 각 반복은 `Main` 반복기 함수에 대 한 호출을 만듭니다 `Power` . 반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>예제  
 다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다. `Iterator`한정자는 속성 선언에 있습니다.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 추가 예제는 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [반복기](../../programming-guide/concepts/iterators.md)
- [Yield 문](../statements/yield-statement.md)
