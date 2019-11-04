---
title: 액세스 제어
description: F# 프로그래밍 언어에서 형식, 메서드, 함수 등의 프로그래밍 요소에 대 한 액세스를 제어 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: fe204a883a440794fdd033c54d6d8d4fb68e0ce2
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425105"
---
# <a name="access-control"></a>액세스 제어

*액세스 제어* 는 형식, 메서드 및 함수와 같은 특정 프로그램 요소를 사용할 수 있는 클라이언트를 선언 하는 것을 말합니다.

## <a name="basics-of-access-control"></a>Access Control의 기본 사항

에서 F#액세스 제어 지정자 `public`, `internal`및 `private`를 모듈, 형식, 메서드, 값 정의, 함수, 속성 및 명시적 필드에 적용할 수 있습니다.

- `public`은 모든 호출자가 엔터티에 액세스할 수 있음을 나타냅니다.

- `internal`는 동일한 어셈블리 에서만 엔터티를 액세스할 수 있음을 나타냅니다.

- `private`는 바깥쪽 형식 또는 모듈 에서만 엔터티에 액세스할 수 있음을 나타냅니다.

> [!NOTE]
> 액세스 지정자 `protected`는에서 사용 되지 않지만 F#`protected` 액세스를 지 원하는 언어로 작성 된 형식을 사용 하는 경우에는 허용 됩니다. 따라서 protected 메서드를 재정의 하는 경우 메서드는 클래스 및 해당 하위 클래스 내 에서만 액세스할 수 있습니다.

일반적으로 지정자는 `mutable` 또는 `inline` 지정 자가 사용 되는 경우를 제외 하 고는 엔터티 이름 앞에 배치 됩니다 .이는 액세스 제어 지정자 뒤에 표시 됩니다.

액세스 지정자를 사용 하지 않는 경우에는 항상 형식에 `private` 되는 형식의 `let` 바인딩을 제외 하 고 기본값은 `public`입니다.

의 F# 시그니처는 프로그램 요소에 대 한 액세스 F# 를 제어 하는 또 다른 메커니즘을 제공 합니다. 액세스 제어에는 서명이 필요 하지 않습니다. 자세한 내용은 [시그니처](signature-files.md)를 참조하세요.

## <a name="rules-for-access-control"></a>Access Control에 대 한 규칙

액세스 제어에는 다음 규칙이 적용 됩니다.

- 상속 선언 (즉, 클래스의 기본 클래스를 지정 하는 `inherit` 사용), 인터페이스 선언 (즉, 클래스에서 인터페이스를 구현 하도록 지정) 및 추상 멤버는 항상 바깥쪽 형식과 동일한 접근성을 갖습니다. 따라서 이러한 구문에서는 액세스 제어 지정자를 사용할 수 없습니다.

- 구분 된 공용 구조체의 개별 사례에 대 한 접근성은 구별 된 공용 구조체 자체의 접근성에 의해 결정 됩니다. 즉, 특정 공용 구조체 케이스는 union 자체 보다 액세스 하기 어렵습니다.

- 레코드 형식의 개별 필드에 대 한 액세스 가능성은 레코드 자체의 접근성에 의해 결정 됩니다. 즉, 특정 레코드 레이블은 레코드 자체 보다 액세스 하기 어렵습니다.

## <a name="example"></a>예제

다음 코드에서는 액세스 제어 지정자를 사용 하는 방법을 보여 줍니다. 프로젝트에는 두 개의 파일, `Module1.fs` 및 `Module2.fs`있습니다. 각 파일은 암시적으로 모듈입니다. 따라서 `Module1`와 `Module2`의 두 모듈이 있습니다. 전용 형식 및 내부 형식은 `Module1`에서 정의 됩니다. `Module2`에서 전용 형식에 액세스할 수 없지만 내부 형식은 사용할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet1.fs)]

다음 코드는 `Module1.fs`에서 만든 형식의 액세스 가능성을 테스트 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a>참조

- [F# 언어 참조](index.md)
- [시그니처](signature-files.md)
