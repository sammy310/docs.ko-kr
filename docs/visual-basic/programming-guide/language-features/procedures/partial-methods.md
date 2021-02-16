---
description: '자세한 정보: 부분 메서드 (Visual Basic)'
title: 부분 메서드
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: d9be2d318ca0da9e1197949c88db5332832bdb3b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466720"
---
# <a name="partial-methods-visual-basic"></a>부분 메서드(Visual Basic)

개발자는 부분 메서드를 사용 하 여 사용자 지정 논리를 코드에 삽입할 수 있습니다. 일반적으로 코드는 디자이너에서 생성 된 클래스의 일부입니다. 부분 메서드 (partial method)는 코드 생성기에 의해 생성 되는 partial 클래스에서 정의 되며, 일반적으로 항목이 변경 되었음을 알리는 데 사용 됩니다. 개발자는 변경에 대 한 응답으로 사용자 지정 동작을 지정할 수 있습니다.  
  
 코드 생성기의 디자이너는 메서드 시그니처와 메서드에 대 한 호출을 하나 이상 정의 합니다. 그러면 개발자는 생성 된 코드의 동작을 사용자 지정 하려는 경우 메서드에 대 한 구현을 제공할 수 있습니다. 구현을 제공 하지 않으면 컴파일러에서 메서드에 대 한 호출을 제거 하 여 추가 성능 오버 헤드를 초래 하지 않습니다.  
  
## <a name="declaration"></a>선언  

 생성 된 코드는 `Partial` 시그니처 줄의 시작 부분에 키워드를 배치 하 여 부분 메서드 정의를 표시 합니다.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 정의는 다음 조건을 충족 해야 합니다.  
  
- 메서드는 `Sub` 이 아닌 여야 합니다 `Function` .  
  
- 메서드의 본문은 비워 두어야 합니다.  
  
- 액세스 한정자는 이어야 합니다 `Private` .  
  
## <a name="implementation"></a>구현  

 구현은 주로 부분 메서드 본문의 입력으로 구성 됩니다. 구현은 일반적으로 정의와 별도의 partial 클래스에 있으며 생성 된 코드를 확장 하려는 개발자가 작성 합니다.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 이전 예제에서는 선언의 시그니처를 정확 하 게 복제 하지만 변형이 가능 합니다. 특히 또는와 같은 다른 한정자를 추가할 수 있습니다 `Overloads` `Overrides` . `Overrides`한정자는 하나만 허용 됩니다. 메서드 한정자에 대 한 자세한 내용은 [Sub 문](../../../language-reference/statements/sub-statement.md)을 참조 하세요.  
  
## <a name="use"></a>기능  

 다른 프로시저를 호출 하는 것 처럼 부분 메서드를 호출 `Sub` 합니다. 메서드가 구현 된 경우 인수가 평가 되 고 메서드의 본문이 실행 됩니다. 그러나 부분 메서드를 구현 하는 것은 선택 사항입니다. 메서드가 구현 되지 않은 경우에는 호출에 영향을 주지 않으며 메서드에 인수로 전달 된 식은 계산 되지 않습니다.  
  
## <a name="example"></a>예  

 이름이 node.js 인 파일에서 속성이 있는 클래스를 정의 합니다. `Product` `Quantity`  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 이름이 제품별 인 파일에서에 대 한 구현을 제공 `QuantityChanged` 합니다.  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 마지막으로 프로젝트의 Main 메서드에서 인스턴스를 선언 `Product` 하 고 해당 속성에 대 한 초기 값을 제공 `Quantity` 합니다.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 다음 메시지가 표시 되는 메시지 상자가 나타납니다.  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>추가 정보

- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [하위 프로시저](./sub-procedures.md)
- [선택적 매개 변수](./optional-parameters.md)
- [부분](../../../language-reference/modifiers/partial.md)
- [LINQ to SQL에서 코드 생성](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Partial 메서드를 사용하여 비즈니스 논리 추가](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
