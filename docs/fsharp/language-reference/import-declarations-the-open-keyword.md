---
title: '선언 가져오기: open 키워드'
description: 'F # 가져오기 선언과 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 포함 하는 모듈 또는 네임 스페이스를 지정 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: ab208c53809e120bc216c8f8b4d04a322d67cf2f
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557183"
---
# <a name="import-declarations-the-open-keyword"></a>가져오기 선언: `open` 키워드

*가져오기 선언은* 정규화 된 이름을 사용 하지 않고 참조할 수 있는 요소를 포함 하는 모듈 또는 네임 스페이스를 지정 합니다.

## <a name="syntax"></a>구문

```fsharp
open module-or-namespace-name
open type type-name
```

## <a name="remarks"></a>설명

항상 정규화 된 네임 스페이스 또는 모듈 경로를 사용 하 여 코드를 참조 하면 쓰기, 읽기 및 유지 관리가 어려운 코드를 만들 수 있습니다. 대신, `open` 자주 사용 되는 모듈 및 네임 스페이스에 대 한 키워드를 사용 하 여 해당 모듈 또는 네임 스페이스의 멤버를 참조할 때 정규화 된 이름 대신 짧은 형식의 이름을 사용할 수 있습니다. 이 키워드는 `using` c #의 키워드, `using namespace` Visual C++ 및 Visual Basic와 비슷합니다 `Imports` .

제공 된 모듈이 나 네임 스페이스는 동일한 프로젝트 또는 참조 된 프로젝트 또는 어셈블리에 있어야 합니다. 그렇지 않은 경우 프로젝트에 대 한 참조를 추가 하거나 `-reference` 명령줄 옵션 또는 해당 약어를 사용할 수 있습니다 `-r` . 자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.

가져오기 선언은 선언 뒤에 오는 코드에서 바깥쪽 네임 스페이스, 모듈 또는 파일의 끝까지 이름을 사용할 수 있도록 합니다.

여러 가져오기 선언을 사용 하는 경우 별도의 줄에 표시 되어야 합니다.

다음 코드에서는 키워드를 사용 하 여 `open` 코드를 간소화 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

두 개 이상의 open 모듈이 나 네임 스페이스에서 같은 이름이 발생할 때 모호성이 발생 하면 F # 컴파일러에서 오류 또는 경고를 내보내지 않습니다. 모호성 발생 시 F #은 가장 최근에 열린 모듈 또는 네임 스페이스에 대 한 기본 설정을 제공 합니다. 예를 들어, 다음 코드에서 `empty` `Seq.empty` `empty` 는가 및 모듈에 모두 있는 경우에도를 의미 `List` `Seq` 합니다.

```fsharp
open List
open Seq
printfn "%A" empty
```

따라서 같은 이름을 가진 멤버를 포함 하는 또는 같은 모듈 또는 네임 스페이스를 열 때는 주의 해야 `List` `Seq` 합니다. 대신 정규화 된 이름을 사용 하는 것이 좋습니다. 코드가 가져오기 선언의 순서에 따라 달라 지는 상황을 피해 야 합니다.

## <a name="open-type-declarations"></a>개방형 형식 선언

F # `open` 은 다음과 같은 형식에서를 지원 합니다.

```fsharp
open type System.Math
PI
```

그러면 해당 형식에 대 한 액세스 가능한 모든 정적 필드와 멤버가 노출 됩니다.

`open`F #으로 정의 된 [레코드](records.md) 및 구분 된 [공용 구조체](discriminated-unions.md) 형식을 정적 멤버를 노출 시킬 수도 있습니다. 구별 된 공용 구조체의 경우 공용 구조체 케이스를 노출할 수도 있습니다. 이렇게 하면 다음과 같이 열지 않을 수 있는 모듈 내에서 선언 된 형식의 공용 구조체 케이스에 액세스할 때 유용 합니다.

```fsharp
module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

## <a name="namespaces-that-are-open-by-default"></a>기본적으로 열리는 네임 스페이스

일부 네임 스페이스는 명시적 가져오기 선언이 없어도 암시적으로 열리는 F # 코드에서 자주 사용 됩니다. 다음 표에서는 기본적으로 열리는 네임 스페이스를 보여 줍니다.

|네임스페이스|Description|
|---------|-----------|
|`FSharp.Core`|및와 같은 기본 제공 형식에 대 한 기본 F # 형식 정의를 포함 `int` `float` 합니다.|
|`FSharp.Core.Operators`|및와 같은 기본 산술 연산을 `+` 포함 `*` 합니다.|
|`FSharp.Collections`|및와 같은 변경할 수 없는 컬렉션 클래스 `List` 를 포함 `Array` 합니다.|
|`FSharp.Control`|지연 계산, 비동기 워크플로 등의 제어 구문에 대 한 형식을 포함 합니다.|
|`FSharp.Text`|함수와 같은 형식이 지정 된 IO에 대 한 함수를 포함 `printf` 합니다.|

## <a name="autoopen-attribute"></a>AutoOpen 특성

`AutoOpen`어셈블리를 참조할 때 네임 스페이스나 모듈을 자동으로 열려면 어셈블리에 특성을 적용 하면 됩니다. `AutoOpen`부모 모듈이 나 네임 스페이스를 열 때 모듈에 특성을 적용 하 여 해당 모듈을 자동으로 열 수도 있습니다. 자세한 내용은 [Autoopenattribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html)를 참조 하세요.

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess 특성

일부 모듈, 레코드 또는 공용 구조체 형식에서 특성을 지정할 수 있습니다 `RequireQualifiedAccess` . 이러한 모듈, 레코드 또는 공용 구조체의 요소를 참조할 때는 가져오기 선언을 포함 하는지 여부에 관계 없이 정규화 된 이름을 사용 해야 합니다. 일반적으로 사용 되는 이름을 정의 하는 형식에 대해이 특성을 사용 하는 경우 이름 충돌을 방지 하 고 라이브러리의 변경에 대 한 코드의 복원 력을 높일 수 있습니다. 자세한 내용은 [RequireQualifiedAccessAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [네임스페이스](namespaces.md)
- [모듈](modules.md)
