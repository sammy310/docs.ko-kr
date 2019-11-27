---
title: IsNot 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336071"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 연산자(Visual Basic)

두 개체 참조 변수를 비교 합니다.

## <a name="syntax"></a>구문

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>요소
 `result` 필수입니다. `Boolean` 값입니다.

 `object1` 필수입니다. 모든 `Object` 변수 또는 식입니다.

 `object2` 필수입니다. 모든 `Object` 변수 또는 식입니다.

## <a name="remarks"></a>주의
 `IsNot` 연산자는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다. 그러나 값 비교를 수행 하지는 않습니다. `object1`와 `object2` 모두 정확히 동일한 개체 인스턴스를 참조 하는 경우 `result` `False`됩니다. 그렇지 않으면 `result` `True`됩니다.

 `IsNot`은 `Is` 연산자와 반대입니다. `IsNot`의 장점은 읽기가 어려울 수 있는 `Not` 및 `Is`를 사용 하 여 구문이 좋지 않게 방지할 수 있다는 것입니다.

 `Is` 및 `IsNot` 연산자를 사용 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.

## <a name="example"></a>예제
 다음 코드 예제에서는 `Is` 연산자와 `IsNot` 연산자를 모두 사용 하 여 동일한 비교를 수행 합니다.

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a>참고 항목

- [Is 연산자](is-operator.md)
- [TypeOf 연산자](typeof-operator.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [방법: 두 개체가 동일한지 테스트](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
