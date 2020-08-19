---
title: Fixed 키워드
description: "F # ' fixed ' 키워드를 사용 하 여 컬렉션을 방지 하기 위해 스택에 로컬를 ' 고정 ' 하는 방법에 대해 알아봅니다."
ms.date: 08/15/2020
ms.openlocfilehash: 786ffd706c243fc83f8fb3afc2201d2a34536372
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559182"
---
# <a name="the-fixed-keyword"></a>Fixed 키워드

`fixed`키워드를 사용 하면 스택에 로컬를 "고정" 하 여 가비지 수집 중에 수집 되거나 이동 되지 않도록 할 수 있습니다.  하위 수준 프로그래밍 시나리오에 사용 됩니다.

## <a name="syntax"></a>구문

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>설명

이렇게 하면 식의 구문을 확장 하 여 포인터를 추출 하 고 가비지 수집 중에 수집 되거나 이동 되지 않도록 하는 이름에 바인딩합니다.  

식에서의 포인터는 키워드를 `fixed` 통해 식별자에 바인딩되고 키워드를 통해 고정 됩니다 `use` .  이의 의미 체계는 키워드를 통한 리소스 관리와 유사 합니다 `use` .  포인터는 범위 내에 있는 동안 고정 되 고 범위를 벗어난 후에는 더 이상 고정 되지 않습니다.  `fixed` 는 바인딩의 컨텍스트 외부에서 사용할 수 없습니다 `use` .  를 사용 하 여 이름에 포인터를 바인딩해야 합니다 `use` .

의 사용은 `fixed` 함수 또는 메서드의 식 내에서 발생 해야 합니다.  스크립트 수준 또는 모듈 수준 범위에서 사용할 수 없습니다.

모든 포인터 코드와 마찬가지로이 기능은 안전 하지 않으며 사용 될 때 경고를 내보냅니다.

## <a name="example"></a>예제

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a>참고 항목

- [NativePtr 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
