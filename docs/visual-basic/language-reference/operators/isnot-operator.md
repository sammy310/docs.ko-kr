---
title: IsNot 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966930"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 연산자(Visual Basic)
두 개체 참조 변수를 비교 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. `Boolean` 값입니다.  
  
 `object1`  
 필수 요소. `Object` 변수 또는 식입니다.  
  
 `object2`  
 필수 요소. `Object` 변수 또는 식입니다.  
  
## <a name="remarks"></a>설명  
 연산자 `IsNot` 는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다. 그러나 값 비교를 수행 하지는 않습니다. `False` `result` 와 `object1` `object2` 가정확히동일한개체인스턴스를참조`True`하면이 고, 그렇지 않으면입니다. `result`  
  
 `IsNot``Is` 연산자와 반대입니다. 의 `IsNot` 장점은 읽기가 어려울 수 있는 및로 인 `Not` 한 `Is`구문을 방지할 수 있다는 것입니다.  
  
 `Is` 및`IsNot` 연산자를 사용 하 여 초기 바인딩된 개체와 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.  
  
> [!NOTE]
> 연산자를 사용 하 여 `TypeOf` 연산자에서 반환 된 식을 비교할 수 없습니다. `IsNot` 대신 `Not` 및`Is` 연산자를 사용 해야 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Is` 연산자 `IsNot` 와 연산자를 모두 사용 하 여 동일한 비교를 수행 합니다.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>참고자료

- [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [방법: 두 개체가 같은지 여부를 테스트 합니다.](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
