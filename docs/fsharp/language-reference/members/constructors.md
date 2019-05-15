---
title: 생성자
description: 정의에서 생성자를 사용 하는 방법을 알아봅니다 F# 를 만들고 클래스 및 구조체 개체를 초기화 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 47fb6e77ce369d7aa4fce3aa2c97ecf7df280c03
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645224"
---
# <a name="constructors"></a>생성자

이 항목 정의 만들고 클래스 및 구조체 개체를 초기화 하려면 생성자를 사용 하는 방법을 설명 합니다.

## <a name="construction-of-class-objects"></a>클래스 개체 생성

클래스 형식의 개체 생성자가 있는 경우. 생성자의 두 종류가 있습니다. 하나는 매개 변수를 가진 형식 이름 바로 뒤 괄호 안에 표시 하는 기본 생성자입니다. 선택적으로 다른 추가 생성자를 사용 하 여 지정 된 `new` 키워드. 이러한 추가 생성자는 기본 생성자를 호출 해야 합니다.

기본 생성자를 포함 `let` 고 `do` 클래스 정의의 시작 부분에 표시 되는 바인딩. A `let` 바인딩 선언 private 필드 및 클래스의 메서드를 `do` 바인딩 코드를 실행 합니다. 에 대 한 자세한 내용은 `let` 클래스 생성자에서 바인딩을 참조 [ `let` 클래스에 바인딩](let-bindings-in-classes.md)합니다. 에 대 한 자세한 내용은 `do` 생성자에 대 한 바인딩 참조 [ `do` 클래스에 바인딩](do-bindings-in-classes.md)합니다.

여부에 관계 없이 생성자를 호출 하려는 기본 생성자 또는 추가 생성자를 사용 하 여 개체를 만들 수는 `new` 식을 없이 선택적 `new` 키워드입니다. 쉼표로 구분 하 여 및 괄호 안에 명명 된 인수 및 값을 사용 하 여 또는 괄호로 묶인 인수를 순서 대로 나열 하는 생성자 인수를 함께 개체를 초기화 합니다. 또한 및 설정할 수 있습니다 속성 개체에 개체를 생성 하는 동안 속성 이름을 사용 하 여 명명 된 생성자 인수를 사용 하는 것 처럼 값을 할당 합니다.

다음 코드는 생성자 및 개체를 만드는 다양 한 방법을 포함 하는 클래스를 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

출력은 다음과 같습니다.

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a>구조 생성

구조는 클래스의 모든 규칙을 따릅니다. 따라서 기본 생성자를 포함할 수 있으며 다른 생성자를 사용 하 여 제공할 수 있습니다 `new`합니다. 그러나 구조체와 클래스 간의 중요 한 차이점 중 하나는: 없는 기본 생성자가 정의 하는 경우에 구조 (즉, 하나는 인수 없이) 기본 생성자를 가질 수 있습니다. 기본 생성자는 해당 형식, 일반적으로 0 또는 해당 기본 값으로 모든 필드를 초기화합니다. 구조에 대해 정의한 모든 생성자는 기본 생성자를 사용 하 여 충돌 하지 않도록 인수가 하나 이상 있어야 합니다.

또한 구조 필드를 사용 하 여 만든를 자주 할는 `val` 키워드; 클래스는 이러한 필드를 수도 있습니다. 구조체와 클래스를 사용 하 여 정의 된 필드를 있는 `val` 키워드 수 초기화할 수도 추가 생성자의 레코드 식을 사용 하 여 다음 코드와 같이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

자세한 내용은 참조 하세요. [명시적 필드: 합니다 `val` 키워드](explicit-fields-the-val-keyword.md)합니다.

## <a name="executing-side-effects-in-constructors"></a>생성자의 파생 작업 실행

클래스에서 기본 생성자의 코드를 실행할 수는 `do` 바인딩. 그러나 경우에 어떻게 해야 하지 않고 추가 생성자의 코드를 실행 하는 `do` 바인딩? 이 작업을 수행 하려면 사용 된 `then` 키워드입니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

기본 생성자의 파생 작업이 계속 실행합니다. 따라서 출력은 다음과 같습니다.

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a>생성자의 자체 식별자

다른 멤버의 각 멤버의 정의에 있는 현재 개체의 이름을 제공합니다. 사용 하 여 클래스 정의의 첫 번째 줄에서 자체 식별자를 추가할 수도 있습니다는 `as` 키워드 바로 뒤에 생성자 매개 변수입니다. 다음 예제에서는이 구문을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

추가 생성자를 정의할 수도 있습니다 자체 식별자를 넣어는 `as` 생성자 매개 변수 바로 뒤에 절. 다음 예제에서는이 구문을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

완전히 정의 하기 전에 개체를 사용 하려고 할 때 문제가 발생할 수 있습니다. 따라서 자체 식별자의 사용 하 여 경고를 생성 하 고 개체 초기화 되기 전에 개체의 멤버에 액세스 하지 않도록 하는 추가 검사를 삽입 하도록 컴파일러에 발생할 수 있습니다. 자체 식별자만 사용 해야 합니다 `do` 바인딩 후 또는 기본 생성자의는 `then` 추가 생성자의 키워드입니다.

자체 식별자의 이름을 사용할 필요가 없습니다 `this`합니다. 유효한 식별자 수 있습니다.

## <a name="assigning-values-to-properties-at-initialization"></a>초기화 시 속성에 값 할당

형식의 할당 목록을 추가 하 여 초기화 코드에서 클래스 개체의 속성 값을 할당할 수 있습니다 `property = value` 생성자의 인수 목록입니다. 다음 코드 예제에서 이를 확인할 수 있습니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

이전 코드의 다음 버전에서는 일반 인수, 선택적 인수 및 생성자 호출에서 속성 설정의 조합을 보여 줍니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a>상속 된 클래스의 생성자

생성자가 있는 기본 클래스에서 상속 하는 경우에 상속 절에서 인수를 지정 해야 합니다. 자세한 내용은 [생성자 및 상속](../inheritance.md#constructors-and-inheritance)합니다.

## <a name="static-constructors-or-type-constructors"></a>정적 생성자 또는 형식 생성자

정적 개체를 만들기 위한 코드를 지정 하는 것 외에도 `let` 고 `do` 바인딩 형식 수준에서 초기화를 수행 하는 형식을 처음으로 사용 하기 전에 실행 되는 클래스 형식에서 작성할 수 있습니다. 자세한 내용은 참조 하세요. [ `let` 클래스의 바인딩](let-bindings-in-classes.md) 및 [ `do` 클래스에 바인딩](do-bindings-in-classes.md)합니다.

## <a name="see-also"></a>참고자료

- [멤버](index.md)
