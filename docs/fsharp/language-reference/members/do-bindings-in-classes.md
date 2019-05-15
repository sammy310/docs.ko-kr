---
title: 클래스의 do 바인딩
description: 사용 하는 방법을 알아봅니다는 F# 개체가 생성 될 때나 형식을 처음 사용할 때 작업을 수행 하는 클래스 정의 바인딩 ' do'.
ms.date: 05/16/2016
ms.openlocfilehash: c924c882974989436d8ea404ebee0a7ef3c54fd3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641793"
---
# <a name="do-bindings-in-classes"></a>클래스의 do 바인딩

A `do` 클래스 정의에서 바인딩 작업을 수행 개체가 생성 될 때 정적 `do` 바인딩는 유형을 처음 사용할 때.

## <a name="syntax"></a>구문

```fsharp
[static] do expression
```

## <a name="remarks"></a>설명

A `do` 바인딩 표시와 함께 또는 후 `let` 바인딩 클래스 정의의 멤버 정의 하기 전에 합니다. 하지만 합니다 `do` 키워드는 선택 사항입니다 `do` 바인딩을 대 한 선택적 있지 모듈 수준에서 `do` 클래스 정의에 바인딩.

지정 된 형식에 static이 아니고의 모든 개체를 생성할 `do` 바인딩 및 비정적 `let` 바인딩 클래스 정의에 나타나는 순서 대로 실행 됩니다. 여러 `do` 바인딩 형식에서 발생할 수 있습니다. 비정적 `let` 바인딩 및 비정적 `do` 바인딩 기본 생성자의 본문이 됩니다. 정적이 지 않은 코드 `do` 기본 생성자 매개 변수를 임의의 값 또는 함수에 정의 된 바인딩 섹션 참조할 수는 `let` 바인딩 섹션입니다.

비정적 `do` 클래스에서 정의한 자체 식별자가으로 바인딩 클래스의 멤버를 액세스할 수는 `as` 제목과으로 해당 멤버의 모든 사용은 클래스에 대 한 자체 식별자로 정규화 된 클래스에는 키워드입니다.

때문에 `let` 멤버는 예상 대로 작동 하도록 하는 데 필요한 경우가 되는 클래스를 개인 필드를 초기화 하는 바인딩을 `do` 바인딩 후 일반적으로 배치 됩니다 `let` 바인딩이 있으므로 해당 코드는 `do` 바인딩 수 완전히 초기화 된 개체를 사용 하 여 실행 합니다. 코드를 초기화가 완료 되기 전에 구성원을 사용 하려고 InvalidOperationException이 발생 합니다.

정적 `do` 바인딩 정적 멤버를 참조할 수 또는 필드 바깥쪽의 클래스 하지만 하지 인스턴스 멤버 또는 필드입니다. 정적 `do` 바인딩 클래스를 처음 사용 하기 전에 실행 되는 클래스의 정적 이니셜라이저의 일부가 됩니다.

에 대 한 특성은 무시 됩니다 `do` 바인딩 형식에서입니다. 특성에서 실행 되는 코드에 대 한 필수 인지를 `do` 바인딩을 적용 해야 기본 생성자입니다.

다음 코드를 클래스에 정적 `do` 바인딩 및 static이 아니고 `do` 바인딩. 두 매개 변수가 있는 생성자를 포함 하는 개체 `a` 하 고 `b`, 및 두 개의 private 필드에 정의 됩니다는 `let` 클래스에 대 한 바인딩을 합니다. 두 가지 속성이 정의 됩니다. 비정적의 범위 내에 이러한 모든 기능은 `do` 바인딩 섹션에는 해당 값을 모든 출력 줄에서 볼 수 있듯이 합니다.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

출력은 다음과 같습니다.

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a>참고자료

- [멤버](index.md)
- [클래스](../classes.md)
- [생성자](constructors.md)
- [클래스의 `let` 바인딩](let-bindings-in-classes.md)
- [`do` Bindings](../functions/do-Bindings.md)
