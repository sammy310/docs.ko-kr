---
title: 네임스페이스
description: 에 대해 알아봅니다 어떻게는 F# 네임 스페이스를 사용 하면 프로그램 요소의 그룹에 이름을 연결 하 여 관련 기능 영역으로 코드를 구성할 수 있습니다.
ms.date: 12/08/2018
ms.openlocfilehash: b315d654dad0d36e3584564ad027c68fb3c94cce
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645266"
---
# <a name="namespaces"></a>네임스페이스

네임 스페이스 이름을 그룹에 연결할 수 있도록 하 여 관련 기능 영역으로 코드를 구성할 수 있습니다 F# 요소를 프로그래밍 합니다. 네임 스페이스에서 일반적으로 최상위 요소는 F# 파일입니다.

## <a name="syntax"></a>구문

```fsharp
namespace [rec] [parent-namespaces.]identifier
```

## <a name="remarks"></a>설명

네임 스페이스에 코드를 배치 하려는 경우 파일의 첫 번째 선언은 네임 스페이스를 선언 해야 합니다. 그런 다음 전체 파일의 내용을 네임 스페이스의 일부가, 다른 네임 스페이스 선언이 없는 존재 제공 파일에 추가 합니다. 하는 경우 다음 네임 스페이스 선언까지 모든 코드는 첫 번째 네임 스페이스에 있는 것으로 간주 됩니다.

네임 스페이스 값 및 함수에 직접 포함할 수 없습니다. 대신 값 및 함수 모듈에 포함 되어야 하며 모듈이 네임 스페이스에 포함 됩니다. 네임 스페이스에는 모듈 형식을 포함할 수 있습니다.

XML 문서 주석 위에 네임 스페이스를 선언할 수 있습니다 있지만 무시 됩니다. 컴파일러 지시문은 네임 스페이스 위에 선언할 수 있습니다.

네임 스페이스 선언할 수 있습니다 명시적으로 네임 스페이스 키워드를 사용 하거나 암시적으로 모듈을 선언 하는 경우. 네임 스페이스를 명시적으로 선언 하려면 네임 스페이스 이름 뒤에 네임 스페이스 키워드를 사용 합니다. 다음 예제에서는 네임 스페이스를 선언 하는 코드 파일 `Widgets` 형식과 해당 네임 스페이스에 포함 된 모듈을 사용 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6406.fs)]

파일의 전체 내용을 하나의 모듈에 있는 경우 선언할 수도 있습니다 네임 스페이스 암시적으로 사용 하 여는 `module` 키워드 및 정규화 된 모듈 이름에 새 네임 스페이스 이름을 제공 합니다. 다음 예제에서는 네임 스페이스를 선언 하는 코드 파일을 보여 줍니다 `Widgets` 및 모듈 `WidgetsModule`, 함수를 포함 하는 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6401.fs)]

다음 코드는 이전 코드와 동일 하지만 모듈은 로컬 모듈 선언 합니다. 이 경우 네임 스페이스 자체 줄에 나타나야 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/namespaces/snippet6402.fs)]

둘 이상의 모듈에 하나 이상의 네임 스페이스에 있는 동일한 파일에서 필요한 경우 로컬 모듈 선언 사용 해야 합니다. 로컬 모듈 선언에 사용 하는 경우에 모듈 선언에 정규화 된 네임 스페이스를 사용할 수 없습니다. 다음 코드는 네임 스페이스 선언 및 두 개의 로컬 모듈 선언 된 파일을 보여 줍니다. 모듈의 네임 스페이스에 직접 포함 된이 예제의 경우 파일 이름이 동일한 암시적으로 만든된 모듈이 없는 경우 와 같은 파일에서 코드 다른를 `do` 되므로 모듈 멤버를 한정할 필요가 내부 모듈을 제외한 네임 스페이스에는 바인딩 `widgetFunction` 모듈 이름을 사용 하 여 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6403.fs)]

이 예제의 출력은 아래와 같습니다.

```fsharp
Module1 10 20
Module2 5 6
```

자세한 내용은 [모듈](modules.md)합니다.

## <a name="nested-namespaces"></a>중첩 된 네임 스페이스

중첩된 된 네임 스페이스를 만들 때 완전히 서 한 정해야 합니다. 그렇지 않으면 새 최상위 네임 스페이스를 만들 있습니다. 들여쓰기는 네임 스페이스 선언에서 무시 됩니다.

다음 예제에서는 중첩된 된 네임 스페이스를 선언 하는 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6404.fs)]

## <a name="namespaces-in-files-and-assemblies"></a>파일 및 어셈블리의 네임 스페이스

네임 스페이스는 단일 프로젝트 또는 컴파일에서 여러 파일을 확장할 수 있습니다. 용어 *네임 스페이스 조각* 하나의 파일에 포함 된 네임 스페이스의 일부를 설명 합니다. 네임 스페이스에는 여러 어셈블리 걸쳐 있을 수도 있습니다. 예를 들어를 `System` 네임 스페이스에 걸쳐 여러 어셈블리를 여러 개의 중첩 된 네임 스페이스를 포함 합니다. 전체.NET Framework를 포함 합니다.

## <a name="global-namespace"></a>전역 Namespace

미리 정의 된 네임 스페이스를 사용 하면 `global` .NET 최상위 네임 스페이스의 이름을 삽입할 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6407.fs)]

사용할 수도 있습니다 전역 예를 들어 최상위.NET 네임 스페이스 참조를 다른 네임 스페이스와 이름 충돌을 해결할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6408.fs)]

## <a name="recursive-namespaces"></a>재귀 네임 스페이스

상호 재귀를 모두 포함 된 코드에 대 한 허용 하도록 자동으로 네임 스페이스를 선언할 수도 있습니다.  이 통해 이루어집니다 `namespace rec`합니다. 사용 `namespace rec` 의 종류와 모듈 간의 상호 참조 코드를 쓸 수 없는 몇 가지 문제를 완화할 수 있습니다. 다음은이 예제입니다.

```fsharp
namespace rec MutualReferences

type Orientation = Up | Down
type PeelState = Peeled | Unpeeled

// This exception depends on the type below.
exception DontSqueezeTheBananaException of Banana

type BananaPeel() = class end

type Banana(orientation : Orientation) =
    member val IsPeeled = false with get, set
    member val Orientation = orientation with get, set
    member val Sides: PeelState list = [ Unpeeled; Unpeeled; Unpeeled; Unpeeled] with get, set

    member self.Peel() = BananaHelpers.peel self // Note the dependency on the BananaHelpers module.
    member self.SqueezeJuiceOut() = raise (DontSqueezeTheBananaException self) // This member depends on the exception above.

module BananaHelpers =
    let peel (b: Banana) =
        let flip (banana: Banana) =
            match banana.Orientation with
            | Up -> 
                banana.Orientation <- Down
                banana
            | Down -> banana

        let peelSides (banana: Banana) =
            banana.Sides
            |> List.map (function
                         | Unpeeled -> Peeled
                         | Peeled -> Peeled)

        match b.Orientation with
        | Up ->   b |> flip |> peelSides
        | Down -> b |> peelSides
```

예외 `DontSqueezeTheBananaException` 및 클래스 `Banana` 모두 서로를 참조 합니다.  또한 모듈 `BananaHelpers` 및 클래스 `Banana` 서로 참조할 수도 있습니다. 에 표시할 수 없을 것임이 F# 를 제거한 경우 합니다 `rec` 키워드를는 `MutualReferences` 네임 스페이스입니다.

이 기능은 또한에 사용할 수 있는 최상위 [모듈](modules.md)합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [모듈](modules.md)
- [F#RFC FS-1009-파일 내에서 더 큰 범위를 통한 상호 참조 형식 및 모듈 허용](https://github.com/fsharp/fslang-design/blob/master/FSharp-4.1/FS-1009-mutually-referential-types-and-modules-single-scope.md)
