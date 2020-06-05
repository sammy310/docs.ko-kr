---
title: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6b155de0bb62f667ca76ec9454dec1466976a9b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400411"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.

하나 이상의 인수를 사용 하는 프로그래밍 요소는 LINQ 쿼리에 포함 됩니다. 컴파일러가 해당 프로그래밍 요소에서 범위 변수를 유추할 수 없습니다.

**오류 ID:** BC36599

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

다음 코드와 같이 프로그래밍 요소에 대 한 명시적 변수 이름을 제공 합니다.

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>참고 항목

- [Visual Basic의 LINQ 소개](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Select 절](../queries/select-clause.md)
