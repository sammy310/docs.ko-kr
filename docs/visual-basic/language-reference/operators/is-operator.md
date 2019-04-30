---
title: Is 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054966"
---
# <a name="is-operator-visual-basic"></a>Is 연산자(Visual Basic)
두 개체 참조 변수를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 값입니다.  
  
 `object1`  
 필수 요소. 모든 `Object` 이름입니다.  
  
 `object2`  
 필수 요소. 모든 `Object` 이름입니다.  
  
## <a name="remarks"></a>설명  
 `Is` 연산자 두 개체 참조가 동일한 개체를 참조 하는지 여부를 결정 합니다. 그러나 값 비교를 수행 하지 않습니다. 경우 `object1` 하 고 `object2` 모두 정확히 같은 개체 인스턴스를 참조 `result` 됩니다 `True`가지고 있지 않은 경우 `result` 는 `False`합니다.  
  
 `Is` 사용 하 여 사용할 수도 있습니다는 `TypeOf` 있도록 키워드는 `TypeOf`... `Is` 개체 변수 데이터 형식과 호환 되는지 테스트 하는 식입니다.  
  
> [!NOTE]
>  합니다 `Is` 키워드에도 사용 되는 [선택... Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Is` 개체 참조의 쌍을 비교 연산자입니다. 결과에 할당 되는 `Boolean` 두 개체가 동일한 지 여부를 나타내는 값입니다.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 위 예제에 사용할 수 있습니다는 `Is` 연산자 둘 다를 테스트 하려면 초기 바인딩 및 런타임에 바인딩된 개체입니다.  
  
## <a name="see-also"></a>참고자료

- [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
