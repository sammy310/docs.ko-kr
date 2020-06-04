---
title: 중첩된 함수에 '<delegatename>' 대리자와 호환되는 시그니처가 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 28d07f01c0fd467cb68d73749988273eee95edf4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409428"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>중첩된 함수에 '\<delegatename>' 대리자와 호환되는 시그니처가 없습니다.

호환 되지 않는 시그니처가 있는 대리자에 람다 식이 할당 되었습니다. 예를 들어 다음 코드에서 대리자에는 `Del` 두 개의 정수 매개 변수가 있습니다.

```vb
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer
```

하나의 인수를 포함 하는 람다 식이 형식으로 선언 된 경우 오류가 발생 합니다 `Del` .

```vb
' Neither of these is valid.
' Dim lambda1 As Del = Function(n As Integer) n + 1
' Dim lambda2 As Del = Function(n) n + 1
```

**오류 ID:** BC36532

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

시그니처가 호환 되도록 대리자 정의 또는 할당 된 람다 식 중 하나를 조정 합니다.

## <a name="see-also"></a>참고 항목

- [완화된 대리자 변환](../../programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [람다 식](../../programming-guide/language-features/procedures/lambda-expressions.md)
