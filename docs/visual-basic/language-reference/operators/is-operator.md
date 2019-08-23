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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917212"
---
# <a name="is-operator-visual-basic"></a>Is 연산자(Visual Basic)
두 개체 참조 변수를 비교 합니다.  
  
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
 연산자 `Is` 는 두 개체 참조가 동일한 개체를 참조 하는지 여부를 확인 합니다. 그러나 값 비교를 수행 하지는 않습니다. `True` `result` 와 `object1` `object2` 가정확히동일한개체인스턴스를참조`False`하면이 고, 그렇지 않으면입니다. `result`  
  
 `Is``TypeOf` 키워드와 함께 사용 하 `TypeOf`여 ... `Is` 식-개체 변수가 데이터 형식과 호환 되는지 여부를 테스트 합니다.  
  
> [!NOTE]
> `Is` 키워드는 [Select ...에도 사용 됩니다. Case 문](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Is` 연산자를 사용 하 여 개체 참조 쌍을 비교 합니다. 두 개체가 동일한 지 여부를 `Boolean` 나타내는 값에 결과가 할당 됩니다.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 앞의 예제에서 보여 주는 것 처럼 `Is` 연산자를 사용 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
