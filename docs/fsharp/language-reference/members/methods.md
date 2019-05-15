---
title: 메서드
description: 에 대해 알아봅니다 어떻게는 F# 메서드는 노출 기능 및 개체 및 유형의 동작을 구현 하는 데 사용 되는 형식과 연결 된 함수입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 9b661a3ff7fa9a7704f5a31570acb62deaac2fcf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641757"
---
# <a name="methods"></a>메서드

A *메서드* 함수 형식과 연결 된입니다. 개체 지향 프로그래밍에서 노출 하 고 기능 및 개체 및 유형의 동작을 구현 하는 메서드가 사용 됩니다.

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

이전 구문에서 다양 한 형태의 메서드 선언 및 정의 볼 수 있습니다. 긴 메서드 본문에서 줄 바꿈을 등호 (=)를 따르며 전체 메서드 본문을 들여쓰 합니다.

메서드 선언에 특성을 적용할 수 있습니다. 메서드 정의 구문은 앞에 야 하며 일반적으로 별도 줄에 나열 됩니다. 자세한 내용은 [특성](../attributes.md)을 참조하세요.

메서드를 표시할 수 있습니다 `inline`합니다. `inline`에 대한 내용은 [인라인 함수](../functions/inline-functions.md)를 참조하세요.

비-인라인 메서드 형식 내에서 재귀적으로 사용된 될 수 있습니다. 명시적으로 사용 하지 않아도 됩니다는 `rec` 키워드입니다.

## <a name="instance-methods"></a>인스턴스 메서드

인스턴스 메서드를 사용 하 여 선언 된 `member` 키워드 및 *자체 식별자*고 뒤에 마침표 (.) 및 메서드 이름과 매개 변수. 대/소문자를 있는 그대로 `let` 바인딩 합니다 *매개 변수 목록을* 패턴 일 수 있습니다. 표시 된 방식으로 메서드는 튜플 형식에 대 한 괄호 안에 매개 변수의 메서드를 포함 하는 일반적으로 F# 다른.NET Framework 언어로 만들어질 때. 그러나 일반적인 이기도 커리 된 형식 (공백으로 구분 하 여 매개 변수) 및 다른 패턴도 지원 됩니다.

다음 예제에서는 추상이 아닌 인스턴스 메서드를 사용 하 고 정의 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

인스턴스 메서드 내에서 let 바인딩을 사용 하 여 정의 된 액세스 필드 자체 식별자를 사용 하지 마십시오. 다른 멤버 및 속성에 액세스 하는 경우 자체 식별자를 사용 합니다.

## <a name="static-methods"></a>정적 메서드

키워드 `static` 메서드 인스턴스 없이 호출할 수 있는지를 지정 하는 및 개체 인스턴스와 연결 되어 있지 않습니다. 그렇지 않으면 메서드는 인스턴스 메서드입니다.

다음 섹션의 예제에서는 사용 하 여 선언 된 필드를 `let` 키워드를 사용 하 여 선언 된 속성 멤버를 `member` 키워드 및 사용 하 여 선언 된 정적 메서드는 `static` 키워드입니다.

다음 예제에 정 및 정적 메서드를 사용 합니다. 이 메서드 정의에 있다고 가정 합니다 `SomeType` 이전 섹션에는 클래스입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a>추상 메서드 및 가상 메서드

키워드 `abstract` 메서드 가상 디스패치와 슬롯 있고 클래스의 정의 없을 수 있음을 의미 합니다. A *가상 디스패치와 슬롯* 은 개체 지향 형식에서 호출 하는 데 사용 되는 런타임 시 가상 함수를 조회 함수 내부적으로 유지 되는 테이블의 항목입니다. 가상 디스패치와 메커니즘은 구현 하는 메커니즘 *다형성*, 개체 지향 프로그래밍의 중요 한 기능입니다. 정의 하지 않고 하나 이상의 추상 메서드가 포함 된 클래스는 *추상 클래스*, 즉, 해당 클래스의 인스턴스를 만들 수 있습니다. 추상 클래스에 대 한 자세한 내용은 참조 하세요. [추상 클래스](../abstract-classes.md)합니다.

추상 메서드 선언에서 메서드 본문을 포함 하지 않습니다. 대신, 메서드 이름 뒤에 콜론 (:) 및 메서드에 대 한 형식 서명은 합니다. 메서드 서명의 형식 마우스 포인터가 위에 놓으면 Visual Studio 코드 편집기에서 메서드 이름을 제외 하 고 매개 변수 이름이 지정 되지 않은 IntelliSense에서 표시 된 것 같습니다. 대화형으로 작업 하는 경우에 형식 시그니처는 인터프리터 fsi.exe에 의해 표시 됩니다. 메서드 서명의 형식 뒤에 적절 한 구분 기호를 사용 하 여 반환 형식, 매개 변수의 형식을 나열 하 여 형성 됩니다. 커리 된 매개 변수는 구분 `->` 개 튜플 매개 변수 구분 하 여 `*`입니다. 반환 값으로 인수에서 항상 구분 되는 `->` 기호입니다. 함수 형식 매개 변수를 경우 처럼 복잡 한 매개 변수 그룹 또는 두 개의 매개 변수가 아닌 단일 매개 변수로 튜플을 처리 하는 경우 괄호를 사용할 수 있습니다.

제공할 수도 있습니다 추상 메서드 default 정의가 클래스 정의 추가 하 고 사용 하 여는 `default` 키워드를이 항목의 구문 블록에 표시 된 대로 합니다. 동일한 클래스의 정의가 있는 추상 메서드는 다른.NET Framework 언어의 가상 메서드와 동일 합니다. 정의가 존재 여부는 `abstract` 키워드는 클래스에 대 한 가상 함수 테이블에 새 디스패치 슬롯을 만듭니다.

기본 클래스에서 추상 메서드를 구현 하는지 여부에 관계 없이 파생된 클래스는 추상 메서드의 구현을 제공할 수 있습니다. 파생된 클래스에서 추상 메서드를 구현 하려면 동일한 이름 및 서명을 사용 하 여 제외 하 고 파생된 클래스에 있는 메서드를 정의 합니다 `override` 또는 `default` 키워드, 메서드 본문을 제공 합니다. 키워드 `override` 고 `default` 정확히 동일 합니다. 사용 하 여 `override` 사용 하 여 새 메서드는 기본 클래스 구현을 재정의 하는 경우 `default` 원래 추상 선언으로 동일한 클래스의 구현을 만들 때. 사용 하지 마십시오는 `abstract` 추상 기본 클래스에서 선언 된 메서드를 구현 하는 방법에 대 한 키워드입니다.

다음 예제에서는 추상 메서드를 보여 줍니다. `Rotate` .NET Framework 가상 메서드의 해당 하는 기본 구현이 포함 됩니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

다음 예제에서는 기본 클래스 메서드를 재정의 하는 파생된 클래스를 보여 줍니다. 이 경우 메서드는 아무 작업도 수행 하지 않도록 재정의 동작을 변경 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a>오버로드된 메서드

오버 로드 된 메서드는 지정된 된 형식에서 동일한 이름을 갖지만 다른 인수를 포함 하는 메서드입니다. F#, 선택적 인수는 일반적으로 오버 로드 된 메서드 대신 사용 됩니다. 그러나 오버 로드 된 메서드는 인수는 튜플 형식으로 변환된 하지 형식은 언어에서 허용 됩니다.

## <a name="optional-arguments"></a>선택적 인수

부터 F# 4.1 메서드에서 기본 매개 변수 값을 사용 하 여 선택적 인수를 할 수도 있습니다.  이 C# 코드와의 상호 운용성을 용이 하 게 하는 데 도움이 됩니다.  다음 예에서는 구문을 보여 줍니다.

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

에 대 한 값을 전달 하는 참고 `DefaultParameterValue` 입력된 형식과 일치 해야 합니다.  에서는 위 예제에서는 `int`합니다.  에 정수가 아닌 값을 전달 하 려 `DefaultParameterValue` 컴파일 오류를 초래 합니다.

## <a name="example-properties-and-methods"></a>예제: 속성 및 메서드

다음 예제에서는 형식에 필드, 전용 함수, 속성 및 정적 메서드는 예가 포함 되어 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a>참고자료

- [멤버](index.md)
