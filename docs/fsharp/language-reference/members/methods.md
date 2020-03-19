---
title: 메서드
description: F# 메서드가 개체 및 형식의 기능 및 동작을 노출하고 구현하는 데 사용되는 형식과 연결된 함수인 방법을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401066"
---
# <a name="methods"></a>메서드

*메서드는* 형식과 연결된 함수입니다. 개체 지향 프로그래밍에서는 메서드를 사용하여 개체 및 형식의 기능 및 동작을 노출하고 구현합니다.

## <a name="syntax"></a>구문

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a>설명

이전 구문에서 다양한 형태의 메서드 선언 및 정의를 볼 수 있습니다. 더 긴 메서드 바디에서 줄 바이탈은 등가부(=)를 따르고 전체 메서드 본문이 들여쓰기됩니다.

특성은 모든 메서드 선언에 적용할 수 있습니다. 메서드 정의에 대 한 구문 앞에 표시 되며 일반적으로 별도 줄에 나열 됩니다. 자세한 내용은 [특성](../attributes.md)을 참조하세요.

메서드를 표시할 `inline`수 있습니다. `inline`에 대한 내용은 [인라인 함수](../functions/inline-functions.md)를 참조하세요.

비인라인 메서드는 형식 내에서 재귀적으로 사용할 수 있습니다. `rec` 키워드를 명시적으로 사용할 필요가 없습니다.

## <a name="instance-methods"></a>인스턴스 방법

인스턴스 메서드는 `member` 키워드와 자체 *식별자로*선언되고 마침표(.) 및 메서드 이름 및 매개 변수가 표시됩니다. 바인딩의 경우와 마찬가지로 *매개 변수 목록은* 패턴일 수 있습니다. `let` 일반적으로 메서드 매개 변수를 튜플 형식으로 괄호안에 포함하면 메서드가 다른 .NET Framework 언어로 만들 때 F#에 표시되는 방식입니다. 그러나 커리 형식(공백으로 구분된 매개 변수)도 일반적이며 다른 패턴도 지원됩니다.

다음 예제에서는 비추상 인스턴스 메서드의 정의 및 사용을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

인스턴스 메서드 내에서 let 바인딩을 사용 하 여 정의 된 필드에 액세스 하는 자체 식별자를 사용 하지 마십시오. 다른 멤버 및 속성에 액세스할 때 자체 식별자를 사용합니다.

## <a name="static-methods"></a>정적 메서드

키워드는 `static` 메서드가 인스턴스 없이 호출될 수 있고 개체 인스턴스와 연결되지 않도록 지정하는 데 사용됩니다. 그렇지 않으면 메서드는 인스턴스 메서드입니다.

다음 섹션의 예제에서는 `let` 키워드로 선언된 필드, `member` 키워드로 선언된 속성 멤버 및 `static` 키워드로 선언된 정적 메서드를 보여 주십습니다.

다음 예제에서는 정적 메서드의 정의 및 사용을 보여 줍니다. 이러한 메서드 정의가 이전 `SomeType` 섹션의 클래스에 있다고 가정합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>추상 메서드 및 가상 메서드

키워드는 `abstract` 메서드에 가상 디스패치 슬롯이 있으며 클래스에 정의가 없을 수 있음을 나타냅니다. *가상 디스패치 슬롯은* 런타임에 개체 지향 형식의 가상 함수 호출을 조회하는 데 사용되는 내부적으로 유지 관리되는 함수 테이블의 항목입니다. 가상 디스패치 메커니즘은 개체 지향 프로그래밍의 중요한 기능인 *다형성을*구현하는 메커니즘입니다. 정의없이 하나 이상의 추상 메서드가있는 클래스는 *추상 클래스이며,* 이는 해당 클래스의 인스턴스를 만들 수 없음을 의미합니다. 추상 클래스에 대한 자세한 내용은 [추상 클래스를](../abstract-classes.md)참조하십시오.

추상 메서드 선언에는 메서드 본문이 포함되지 않습니다. 대신 메서드 의 이름 뒤에 콜론(:)이 표시됩니다. 및 메서드에 대한 형식 시그니처입니다. 메서드의 형식 시그니처는 매개 변수 이름이 없는 경우를 제외하고 Visual Studio 코드 편집기의 메서드 이름 위에 마우스 포인터를 일시 중지할 때 IntelliSense에서 표시한 것과 동일합니다. 대화식으로 작업할 때 인터프리터 fsi.exe에서도 형식 서명이 표시됩니다. 메서드의 형식 시그니처는 매개 변수의 형식을 나열하고 적절한 구분 기호를 사용하여 반환 형식을 나열하여 형성됩니다. 커리 매개변수는 로 `->` 구분되고 튜플 매개변수는 `*`에 의해 구분됩니다. 반환 값은 항상 `->` 기호로 인수와 분리됩니다. 괄호는 함수 형식이 매개 변수인 경우와 같은 복잡한 매개 변수를 그룹화하거나 튜플이 두 매개 변수가 아닌 단일 매개변수로 처리되는 시기를 나타내는 데 사용할 수 있습니다.

이 항목의 구문 블록에 표시된 대로 클래스에 정의를 `default` 추가하고 키워드를 사용하여 추상 메서드 기본 정의를 제공할 수도 있습니다. 동일한 클래스에 정의가 있는 추상 메서드는 다른 .NET Framework 언어의 가상 메서드와 동일합니다. 정의가 있는지 여부에 관계없이 `abstract` 키워드는 클래스의 가상 함수 테이블에 새 디스패치 슬롯을 만듭니다.

기본 클래스가 추상 메서드를 구현하는지 여부에 관계없이 파생 클래스는 추상 메서드의 구현을 제공할 수 있습니다. 파생 클래스에서 추상 메서드를 구현하려면 또는 `override` `default` 키워드를 사용하지 말고 파생 클래스에 동일한 이름과 서명을 가지는 메서드를 정의하고 메서드 본문을 제공합니다. 키워드와 `override` `default` 정확히 같은 것을 의미한다. 새 `override` 메서드가 기본 클래스 구현을 재정의하는 경우 사용합니다. 원래 `default` 추상 선언과 동일한 클래스에서 구현을 만들 때 사용합니다. 기본 클래스에서 `abstract` 추상으로 선언된 메서드를 구현하는 메서드에서 키워드를 사용하지 마십시오.

다음 예제에서는 .NET `Rotate` Framework 가상 메서드와 동일한 기본 구현이 있는 추상 메서드를 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

다음 예제에서는 기본 클래스 메서드를 재정의하는 파생 클래스를 보여 줍니다. 이 경우 재정의는 메서드가 아무 것도 수행하지 않도록 동작을 변경합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>오버로드된 메서드

오버로드된 메서드는 지정된 형식에 이름이 동일하지만 인수가 다른 메서드입니다. F#에서 선택적 인수는 일반적으로 오버로드된 메서드 대신 사용됩니다. 그러나 인수가 커리 형식이 아닌 튜플 형식인 경우 오버로드된 메서드는 언어에서 허용됩니다.

## <a name="optional-arguments"></a>선택적 인수

F # 4.1로 시작하여 메서드에서 기본 매개 변수 값이있는 선택적 인수를 가질 수도 있습니다.  이는 C# 코드와의 상호 운용을 용이하게 하기 위한 것입니다.  다음 예제에서는 구문을 보여 줍니다.

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

에 `DefaultParameterValue` 전달 된 값은 입력 형식과 일치해야 합니다.  위의 샘플에서, 그것은 `int`이다.  정수가 아닌 값을 `DefaultParameterValue` 전달하려고 하면 컴파일 오류가 발생합니다.

## <a name="example-properties-and-methods"></a>예: 속성 및 메서드

다음 예제에는 필드, 개인 함수, 속성 및 정적 메서드의 예가 있는 형식이 포함되어 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>참고 항목

- [멤버](index.md)
