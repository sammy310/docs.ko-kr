---
description: '자세한 정보: Is 연산자 (Visual Basic)'
title: Is 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0912ebd9bc9c33149568c6cea0197ef24c305ff2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665687"
---
# <a name="is-operator-visual-basic"></a>Is 연산자 (Visual Basic)

두 개체 참조 변수를 비교 합니다.

## <a name="syntax"></a>Syntax

```vb
result = object1 Is object2
```

## <a name="parts"></a>부분

 `result`  
 필수 사항입니다. 모든 `Boolean` 값입니다.  
  
 `object1`  
 필수 사항입니다. 모든 `Object` 이름입니다.  
  
 `object2`  
 필수 사항입니다. 모든 `Object` 이름입니다.  
  
## <a name="remarks"></a>설명

`Is`연산자는 두 개체 참조가 동일한 개체를 참조 하는지 여부를 확인 합니다. 그러나 값 비교를 수행 하지는 않습니다. `object1`와 `object2` 가 정확히 동일한 개체 인스턴스를 참조 하면이 고, 그렇지 않으면입니다 `result` `True` `result` `False` .

> [!NOTE]
> `Is`키워드는 Select ...에도 사용 됩니다. [ Case 문](../statements/select-case-statement.md).
  
## <a name="example"></a>예제

다음 예제에서는 연산자를 사용 하 여 `Is` 개체 참조 쌍을 비교 합니다. `Boolean`두 개체가 동일한 지 여부를 나타내는 값에 결과가 할당 됩니다.

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

앞의 예제에서 보여 주는 것 처럼 연산자를 사용 `Is` 하 여 초기 바인딩과 런타임에 바인딩된 개체를 모두 테스트할 수 있습니다.

## <a name="use-typeof-operator-with-is-operator"></a>Is 연산자에 TypeOf 연산자 사용

`Is` 연산자는 키워드와 함께 사용 `TypeOf` 하 여 `TypeOf` `Is` 개체 변수가 데이터 형식과 호환 되는지 여부를 테스트 하는 ... 식을 만들 수도 있습니다. 예를 들면 다음과 같습니다.

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a>참고 항목

- [TypeOf 연산자](typeof-operator.md)
- [IsNot 연산자](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [연산자 및 식](../../programming-guide/language-features/operators-and-expressions/index.md)
