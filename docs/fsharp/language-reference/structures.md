---
title: 구조체
description: 에 대 한 자세한는 F# 구조체, 종종 간단한 개체 형식으로 적은 양의 데이터 적고 동작이 단순한 형식에 대해 클래스 보다 더 효율적입니다.
ms.date: 05/16/2016
ms.openlocfilehash: dc302b975604bebcd145a385fb59b21417547c5e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645340"
---
# <a name="structures"></a>구조체

A *구조* 적은 양의 데이터 적고 동작이 단순한 형식에 대 한 클래스 보다 효율적일 수 있는 간단한 개체 형식인 합니다.

## <a name="syntax"></a>구문

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    struct
        type-definition-elements-and-members
    end
// or
[ attributes ]
[<StructAttribute>]
type [accessibility-modifier] type-name =
    type-definition-elements-and-members
```

## <a name="remarks"></a>설명

구조체가 *값 형식*, 즉, 스택에 직접 또는으로 사용 되는 저장 된 필드 또는 배열 요소를 부모에 대 한 인라인 입력 합니다. 클래스나 레코드와 달리 구조체는 pass-by-value 의미 체계를 포함합니다. 따라서 기본적으로 자주 액세스 및 복사하는 소규모 데이터 집계에 유용합니다.

위 구문에는 두 개의 폼이 표시되어 있습니다. 첫 번째는 간단한 구문은 아니지만 자주 사용됩니다. `struct` 및 `end` 키워드를 사용하는 경우 두 번째 구문에 나와 있는 `StructAttribute` 특성을 생략할 수 있기 때문입니다. 즉, `StructAttribute`를 `Struct`로 간략하게 작성할 수 있습니다.

합니다 *형식-정의-요소-및-멤버* 이전 구문에서 멤버 선언 및 정의 나타냅니다. 구조체는 생성자 및 변경 가능/불가능한 필드를 포함할 수 있으며 멤버 및 인터페이스 구현을 선언할 수 있습니다. 자세한 내용은 [멤버](members/index.md)합니다.

구조체는 상속에 참가할 수 없고, `let` 또는 `do` 바인딩을 포함할 수 없으며, 자신의 형식으로 된 필드를 재귀적으로 포함할 수 없습니다. 그러나 자신의 형식을 참조하는 참조 셀은 포함할 수 있습니다.

구조체는 `let` 바인딩을 허용하지 않으므로 구조체에서는 `val` 키워드를 사용하여 필드를 선언해야 합니다. `val` 키워드는 필드와 해당 형식을 정의하지만 초기화는 허용하지 않습니다. 대신 `val` 선언이 null 또는 0으로 초기화됩니다. 따라서 암시적 생성자(선언에서 구조체 이름 바로 뒤에 지정되는 매개 변수)를 포함하는 구조체에서는 `val` 선언을 `DefaultValue` 특성으로 주석 처리해야 합니다. 정의된 생성자가 있는 구조체도 0으로의 초기화를 지원합니다. 그러므로 `DefaultValue` 특성은 이러한 0 값이 필드에 유효함을 나타내는 선언입니다. 구조체의 암시적 생성자는 아무런 작업도 수행하지 않습니다. 해당 형식에 대해서는 `let` 및 `do` 바인딩이 허용되지 않지만 전달되는 암시적 생성자 매개 변수 값은 개인 필드로 사용할 수 있기 때문입니다.

명시적 생성자에서는 필드 값이 초기화될 수 있습니다. 명시적 생성자를 포함하는 구조체는 0으로의 초기화도 지원합니다. 그러나 `DefaultValue` 선언에서 `val` 특성을 사용하는 경우 명시적 생성자와 충돌하므로 해당 특성은 사용하지 않아야 합니다. 에 대 한 자세한 내용은 `val` 선언을 참조 [명시적 필드: 합니다 `val` 키워드](members/explicit-fields-the-val-keyword.md)합니다.

특성 및 액세스 가능성 한정자는 구조체에서 허용되며 다른 형식과 동일한 규칙을 따릅니다. 자세한 내용은 [특성](attributes.md) 하 고 [Access Control](access-control.md)합니다.

다음 코드 예제에서는 구조체 정의를 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2501.fs)]

## <a name="byreflike-structs"></a>ByRefLike 구조체

수를 준수 하는 사용자 고유의 구조체를 정의할 수 있습니다 `byref`-같은 의미 체계: 참조 [Byref](byrefs.md) 자세한 내용은 합니다. 사용 하 여 <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> 특성:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` 의미 하지는 않습니다 `Struct`합니다. 두 형식에 있어야 합니다.

"`byref`-같은" 구조체에서 F# 스택 바인딩된 값 형식입니다. 관리 되는 힙에 할당 되지 됩니다. `byref`-같은 구조체 유용 고성능 프로그래밍에 대 한 일련의 수명 및 비캡처 하는 방법에 대 한 강력한 검사를 사용 하 여 적용 됩니다. 규칙은 다음과 같습니다.

* 사용할 수 있습니다 함수 매개 변수, 메서드 매개 변수, 지역 변수, 메서드를 반환 합니다.
* 정적 이어야 하거나 멤버 클래스 또는 일반 구조체의 인스턴스 수는 없습니다.
* 모든 클로저 생성으로 캡처할 수 없습니다 (`async` 메서드 또는 람다 식).
* 제네릭 매개 변수로 사용할 수 없습니다.

이러한 규칙은 매우 강력 하 게 사용을 제한, 있지만 그렇게 안전한 방식으로 고성능 컴퓨팅의 약속을 충족 하 합니다.

## <a name="readonly-structs"></a>읽기 전용 구조체

구조체를 사용 하 여 주석을 추가할 수는 <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> 특성입니다. 예를 들어:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsReadOnly` 의미 하지는 않습니다 `Struct`합니다. 모두 추가 해야는 `IsReadOnly` 구조체입니다.

이 특성을 사용 하는 메타 데이터 수 있도록 내보냅니다 F# 및 C# 로 처리할 알고 `inref<'T>` 하 고 `in ref`각각.

읽기 전용 구조체 내에서 변경할 수 있는 값을 정의 했는데 오류가 발생 합니다.

## <a name="struct-records-and-discriminated-unions"></a>구조체 레코드 및 구분 된 공용 구조체

나타낼 수 있습니다 [레코드](records.md) 하 고 [구별 된 공용 구조체](discriminated-unions.md) 사용 하 여 구조체로 `[<Struct>]` 특성입니다.  자세한 내용은 각 문서를 참조 하세요.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [클래스](classes.md)
- [레코드](records.md)
- [멤버](members/index.md)
