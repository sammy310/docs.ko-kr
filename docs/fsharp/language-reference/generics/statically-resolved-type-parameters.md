---
title: 정적으로 확인된 형식 매개 변수
description: 사용 하는 방법을 알아봅니다는 F# 런타임 대신 컴파일 시간에 실제 형식으로 대체 되는 정적으로 확인 된 형식 매개 변수입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 337d4f40418ee76cb18397add27acba75f756091
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645252"
---
# <a name="statically-resolved-type-parameters"></a>정적으로 확인된 형식 매개 변수

A *정적으로 확인 된 형식 매개 변수* 은 런타임 대신 컴파일 시간에 실제 형식으로 대체 되는 형식 매개 변수입니다. 캐럿 (^) 기호가 앞에 있습니다.

## <a name="syntax"></a>구문

```
ˆtype-parameter
```

## <a name="remarks"></a>설명

에 F# 언어를 가지 다음 두 가지 종류의 형식 매개 변수입니다. 첫 번째 종류에는 표준 제네릭 형식 매개 변수입니다. 이러한 에서처럼 아포스트로피 (')로 표시 됩니다 `'T` 고 `'U`입니다. 제네릭 형식 매개 변수에 다른.NET Framework 언어에서 동일 합니다. 다른 종류 정적으로 해결 되 고 에서처럼 캐럿 기호 나타난 `^T` 고 `^U`입니다.

정적으로 확인 된 형식 매개 변수는 형식 인수 있어야 특정 멤버를 사용할 수 있도록 지정할 수 있도록 하는 제약 조건 멤버 제약 조건과 함께에서 주로 유용 합니다. 일반 제네릭 형식 매개 변수를 사용 하 여이 유형의 제약 조건 만드는 방법이 없습니다.

다음 표에서 유사성과 두 종류의 형식 매개 변수 간의 차이점을 요약합니다.

|기능|제네릭|정적으로 확인 된|
|-------|-------|-------------------|
|구문|`'T`, `'U`|`^T`, `^U`|
|해결 시간|런타임|컴파일 시간|
|멤버 제약 조건|멤버 제약 조건과 함께 사용할 수 없습니다.|멤버 제약 조건과 함께 사용할 수 있습니다.|
|코드 생성|표준 제네릭 형식 매개 변수를 사용 하 여 형식 (또는 메서드)는 단일 제네릭 형식 또는 메서드의 생성 됩니다.|여러 인스턴스화 형식 및 메서드 생성 됩니다, 그리고 하나는 각 형식에 대 한 필요 합니다.|
|형식 사용|형식에 사용할 수 있습니다.|형식에 사용할 수 없습니다.|
|인라인 함수와 함께 사용|아니요. 인라인 함수는 표준 제네릭 형식 매개 변수를 사용 하 여 매개 변수화 할 수 없습니다.|예. 함수 또는 메서드에서 인라인이 아닌 정적으로 확인 된 형식 매개 변수를 사용할 수 없습니다.|

많은 F# 코어 라이브러리 함수, 특히 연산자는 형식 매개 변수를 정적으로 확인 된 합니다. 이러한 함수 및 연산자에는 인라인 및 숫자 계산을 위한 효율적인 코드 생성 합니다.

인라인 메서드 및 연산자를 사용 하거나 형식 매개 변수를 정적으로 해결 하는 다른 함수를 사용 하는 함수에는 자체 정적으로 확인 된 형식 매개 변수를 사용할 수도 있습니다. 종종 형식 유추와 같은 인라인 함수가 정적으로 확인 된 형식 매개 변수를 유추 합니다. 다음 예제에서는 정적으로 확인 된 형식 매개 변수가으로 유추 되는 연산자 정을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

확인 된 형식 `(+@)` 사용을 기반으로 `(+)` 및 `(*)`두 멤버 제약 조건을 정적으로 확인 된 형식 매개 변수에서 유추 하는 형식 유추를 발생 하는 중입니다. 에 표시 된 것 처럼 확인된 된 형식에는 F# 인터프리터는 다음과 같습니다.

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

출력은 다음과 같습니다.

```
2
1.500000
```

부터 F# 4.1 정적으로 확인 된 형식 매개 변수 서명에서 구체적인 형식 이름을 지정할 수도 있습니다.  언어의 이전 버전에서는 형식 이름을 컴파일러에서 유추할 수 실제로 하지만 실제로 지정할 수 없습니다 시그니처에서.  F# 4.1 정적으로 확인 된 형식 매개 변수 서명에서 구체적인 형식 이름을 지정할 수도 있습니다. 예를 들면 다음과 같습니다.

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a>참고자료

- [제네릭](index.md)
- [형식 유추](../type-inference.md)
- [자동 일반화](automatic-generalization.md)
- [제약 조건](constraints.md)
- [인라인 함수](../functions/inline-functions.md)
