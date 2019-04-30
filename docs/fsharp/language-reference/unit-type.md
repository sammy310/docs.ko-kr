---
title: 단위 형식
description: 에 대해 알아봅니다 하는 방법을 F# 'unit' 유형은 자리를 값이 필요한 언어 구문을 사용 하 여 필요한 되었거나 필요한 값이 없는 경우에 자주 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: f1866ff12f36f4f8d3eaa1275551c42fc4ade216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982529"
---
# <a name="unit-type"></a>단위 형식

합니다 `unit` 의 특정 값이 없음을 나타내는 형식인 형식은 `unit` 형식은 다른 값이 없으므로 있거나 필요한 경우 자리 표시자로 역할을 하는 단일 값만 합니다.

## <a name="syntax"></a>구문

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>설명

모든 F# 식은 값으로 계산 되어야 합니다. 형식의 값을 원하는 값을 생성 하지 않습니다 하는 식에 대 한 `unit` 사용 됩니다. `unit` 형식와 유사 합니다 `void` 와 같은 언어에서 입력 C# 및 C++.

합니다 `unit` 형식은 단일 값 및 해당 값은 토큰에 나타난 `()`합니다.

값을 `unit` 형식에 주로 사용 됩니다 F# 하지만 값은 필요한 또는 원하는 언어 구문을 사용 하 여 값이 필요한 경우 위치를 저장 하는 프로그래밍 합니다. 반환 값을 예로 들 수 있습니다는 `printf` 함수입니다. 있으므로의 중요 한 작업을 `printf` 작업 함수에서 발생이 함수는 실제 값을 반환할 필요가 없습니다. 형식의 반환 값은 따라서 `unit`합니다.

일부 구문은 예상을 `unit` 값입니다. 예를 들어, 한 `do` 바인딩 또는 코드 모듈의 최상위 수준에서 평가 되어야 하는 `unit` 값입니다. 컴파일러 경고를 보고 경우는 `do` 바인딩 또는 코드 모듈의 최상위 수준에서 결과 이외의 `unit` 다음 예와에서 같이 사용 되지 않는 값입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

이 경고는 함수형 프로그래밍;의 특징 다른.NET 프로그래밍 언어에에서는 표시 되지 않습니다. 함수 없는 부작용을 순수 함수형 프로그램에서 최종 반환 값은 함수 호출의 유일한 결과입니다. 따라서 결과 무시 하는 경우 가능한 프로그래밍 오류입니다. 하지만 F# 순수 하 게 제대로 작동 하지 않는 프로그래밍 언어, 것이 좋습니다 가능한 함수형 프로그래밍 스타일을 따릅니다.

## <a name="see-also"></a>참고자료

- [기본](primitive-types.md)
- [F# 언어 참조](index.md)