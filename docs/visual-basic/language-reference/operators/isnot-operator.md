---
description: '자세한 정보: IsNot 연산자 (Visual Basic)'
title: IsNot 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ac3e127676dfa57d14e07838152022de62fc336b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665668"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 연산자(Visual Basic)

두 개체 참조 변수를 비교 합니다.

## <a name="syntax"></a>Syntax

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>부분

- `result`

  필수 사항입니다. `Boolean` 값입니다.

- `object1`

  필수 사항입니다. `Object`변수 또는 식입니다.

- `object2`

  필수 사항입니다. `Object`변수 또는 식입니다.

## <a name="remarks"></a>설명

`IsNot`연산자는 두 개체 참조가 서로 다른 개체를 참조 하는지 여부를 확인 합니다. 그러나 값 비교를 수행 하지 않습니다. `object1`와 `object2` 가 정확히 동일한 개체 인스턴스를 참조 하면이 고, 그렇지 않으면입니다 `result` `False` `result` `True` .

`IsNot` 연산자와 반대입니다 `Is` . 의 장점은 `IsNot` `Not` 읽기가 어려울 수 있는 및로 인 한 구문을 방지할 수 있다는 것입니다 `Is` .

 및 연산자를 사용 `Is` `IsNot` 하 여 초기 바인딩된 개체와 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.

## <a name="example"></a>예제

다음 코드 예제에서는 연산자와 연산자를 모두 사용 하 여 `Is` `IsNot` 동일한 비교를 수행 합니다.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>IsNot 연산자에 TypeOf 연산자 사용

Visual Basic 14부터 연산자를 `TypeOf` 연산자와 함께 사용 하 여 `IsNot` 개체가 데이터 형식과 호환 *되지* 않는지 여부를 테스트할 수 있습니다. 예를 들면 다음과 같습니다.

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>참고 항목

- [Is 연산자](is-operator.md)
- [TypeOf 연산자](typeof-operator.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [방법: 두 개체가 동일한지 테스트](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
