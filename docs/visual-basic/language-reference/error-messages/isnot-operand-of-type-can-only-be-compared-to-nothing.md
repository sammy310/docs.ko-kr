---
title: "'typename'이(가) nullable 형식이므로 'typename' 형식의 'IsNot' 피연산자는 'Nothing'과(와)만 비교할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 1660971e2a1a11d7a2d14f222cd149edf4aa4c7b
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249515"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>'typename'이(가) nullable 형식이므로 'typename' 형식의 'IsNot' 피연산자는 'Nothing'과(와)만 비교할 수 있습니다.

nullable 값 유형으로 선언된 변수는 연산자 `Nothing` 사용 `IsNot` 이외의 식과 비교되었습니다.

**오류 ID:** BC32128

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

`Nothing` 연산자를 사용하여 nullable 형식을 `IsNot` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>참조

- [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
