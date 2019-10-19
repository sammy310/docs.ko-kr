---
title: Yield 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: 57b36bb32e1a575a645f7a15045bf0898dd10dfd
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582210"
---
# <a name="yield-statement-visual-basic"></a>Yield 문(Visual Basic)
컬렉션의 다음 요소를 `For Each...Next` 문으로 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>매개 변수  
  
|용어|정의|  
|---|---|  
|`expression`|필수 요소. @No__t_1 문을 포함 하는 반복기 함수 또는 `Get` 접근자의 형식으로 암시적으로 변환할 수 있는 식입니다.|  
  
## <a name="remarks"></a>주의  
 @No__t_0 문은 한 번에 한 컬렉션의 요소를 반환 합니다. @No__t_0 문은 컬렉션에 대해 사용자 지정 반복을 수행 하는 반복기 함수 또는 `Get` 접근자에 포함 되어 있습니다.  
  
 For Each ...를 사용 하 여 반복기 함수를 사용 합니다. [ 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 또는 LINQ 쿼리입니다. @No__t_0 루프의 각 반복은 반복기 함수를 호출 합니다. 반복기 함수에서 `Yield` 문에 도달 하면 `expression` 반환 되 고 코드에서 현재 위치가 유지 됩니다. 다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.  
  
 @No__t_1 문의 `expression` 형식에서 반복기의 반환 형식으로의 암시적 변환이 있어야 합니다.  
  
 @No__t_0 또는 `Return` 문을 사용 하 여 반복을 종료할 수 있습니다.  
  
 "Yield"는 예약 된 단어가 아니므로 `Iterator` 함수 또는 `Get` 접근자에서 사용 되는 경우에만 특별 한 의미가 있습니다.  
  
 반복기 함수 및 `Get` 접근자에 대 한 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.  
  
## <a name="iterator-functions-and-get-accessors"></a>반복기 함수 및 Get 접근자  
 반복기 함수 또는 `Get` 접근자의 선언은 다음 요구 사항을 충족 해야 합니다.  
  
- [반복기](../../../visual-basic/language-reference/modifiers/iterator.md) 한정자를 포함 해야 합니다.  
  
- 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, 또는 <xref:System.Collections.Generic.IEnumerator%601>여야 합니다.  
  
- @No__t_0 매개 변수를 가질 수 없습니다.  
  
 반복기 함수는 이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 소멸자에서 발생할 수 없습니다.  
  
 반복기 함수는 익명 함수 일 수 있습니다. 자세한 내용은 [반복기](../../programming-guide/concepts/iterators.md)를 참조하세요.  
  
## <a name="exception-handling"></a>예외 처리  
 @No__t_0 문은 Try ...의 `Try` 블록 안에 있을 수 있습니다. [ Catch ... Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). @No__t_1 문을 포함 하는 `Try` 블록은 `Catch` 블록을 포함할 수 있으며 `Finally` 블록을 포함할 수 있습니다.  
  
 @No__t_0 문은 `Catch` 블록 또는 `Finally` 블록 안에 있을 수 없습니다.  
  
 @No__t_0 본문 (반복기 함수 외부)에서 예외를 throw 하는 경우 반복기 함수의 `Catch` 블록이 실행 되지 않지만 반복기 함수의 `Finally` 블록이 실행 됩니다. 반복기 함수 내의 `Catch` 블록은 반복기 함수 내에서 발생 하는 예외만 catch 합니다.  
  
## <a name="technical-implementation"></a>기술 구현  
 다음 코드는 반복기 함수에서 `IEnumerable (Of String)`를 반환한 다음 `IEnumerable (Of String)`의 요소를 반복 합니다.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 @No__t_0에 대 한 호출은 함수 본문을 실행 하지 않습니다. 대신에 `IEnumerable(Of String)` 변수에 `elements`을 반환합니다.  
  
 `For Each` 루프 반복에서 <xref:System.Collections.IEnumerator.MoveNext%2A>에 대한 `elements` 메서드가 호출됩니다. 이 호출은 다음 `MyIteratorFunction` 문에 도달할 때까지 `Yield` 본문을 실행합니다. @No__t_0 문은 루프 본문에서 사용 하는 `element` 변수 값 뿐만 아니라 요소의 <xref:System.Collections.Generic.IEnumerator%601.Current%2A> 속성 (`IEnumerable (Of String)`)을 결정 하는 식을 반환 합니다.  
  
 이후에 `For Each` 루프가 반복될 때마다 중지되었던 위치에서 반복기 본문 실행이 계속되고 `Yield` 문에 도달하면 다시 중지됩니다. @No__t_0 루프는 반복기 함수 또는 `Return` 또는 `Exit Function` 문의 끝에 도달 하면 완료 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 [에 대 한 `Yield` 문이 있습니다. Next](../../../visual-basic/language-reference/statements/for-next-statement.md) 루프. @No__t_1의 각 문 본문 [에 대 한](../../../visual-basic/language-reference/statements/for-each-next-statement.md) 각 반복은 `Power` 반복기 함수에 대 한 호출을 만듭니다. 반복기 함수를 호출할 때마다 다음에 `Yield` 루프를 반복하는 도중에 `For…Next` 문이 실행됩니다.  
  
 반복기 메서드의 반환 형식은 <xref:System.Collections.Generic.IEnumerable%601> 반복기 인터페이스 형식입니다. 반복기 메서드가 호출되면 숫자의 거듭제곱이 들어 있는 열거형 개체를 반환합니다.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>예제  
 다음 예제는 반복기인 `Get` 접근자에 대해 설명합니다. 속성 선언에 `Iterator` 한정자가 포함 되어 있습니다.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 추가 예제는 [반복기](../../programming-guide/concepts/iterators.md)를 참조 하세요.  
  
## <a name="see-also"></a>참조

- [문](../../../visual-basic/language-reference/statements/index.md)
