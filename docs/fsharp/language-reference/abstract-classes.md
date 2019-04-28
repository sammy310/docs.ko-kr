---
title: 추상 클래스
description: 에 대해 알아봅니다 F# 추상 클래스 구현 되지 않은 일부 또는 모든 멤버를 유지 하는 및 개체 유형의 다양 한 집합의 공통 기능을 나타냅니다.
ms.date: 05/16/2016
ms.openlocfilehash: fecd3b2d550c6b8f59fa614f5d00c5f730a4896a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772777"
---
# <a name="abstract-classes"></a>추상 클래스

*추상 클래스* 는 파생된 클래스에서 구현할 수 있도록 일부 또는 모든 멤버를 구현 되지 않은 채로 두는 클래스입니다.

## <a name="syntax"></a>구문

```fsharp
// Abstract class syntax.
[<AbstractClass>]
type [ accessibility-modifier ] abstract-class-name =
[ inherit base-class-or-interface-name ]
[ abstract-member-declarations-and-member-definitions ]

// Abstract member syntax.
abstract member member-name : type-signature
```

## <a name="remarks"></a>설명

개체 지향 프로그래밍에서 추상 클래스 계층의 기본 클래스로 사용 되 고 다양 한 개체 유형 집합의 공통 기능을 나타냅니다. "Abstract" 이름에서 알 수 있듯이 추상 클래스 종종 맞지 않는 문제 도메인의 구체적 엔터티를 직접. 그러나 여러 다른 콘크리트 엔터티의 공통점 나타냅니다지 않습니다.

추상 클래스에 있어야 합니다 `AbstractClass` 특성입니다. 구현 되 고 멤버를 구현 되지 않았으며 있을 수 있습니다. 하지만 이라는 용어를 사용 *추상* 적용할 때 클래스는 다른.NET 언어와 동일 이라는 용어를 사용 *추상* 메서드 (및 속성)에 적용 하는 경우에 약간 다릅니다은 F# 다른.NET 언어에서 사용 하 여 합니다. F#메서드를 사용 하 여 표시할지 하는 경우를 `abstract` 키워드를이 의미 멤버인 이라고 하는 항목을는 *가상 디스패치와 슬롯*, 가상 함수는 형식에 대 한 내부 테이블에 합니다. 즉, 메서드는 가상 있지만 합니다 `virtual` 키워드에 사용 되지 않습니다는 F# 언어입니다. 키워드 `abstract` 메서드를 구현 하는 여부에 관계 없이 가상 메서드에 사용 됩니다. 가상 디스패치와 슬롯의 선언은 해당 디스패치 슬롯에 대 한 메서드의 정의에서 별도입니다. 따라서는 F# 가상 메서드 선언은 다른.NET 언어에서 정의 해당 하는 추상 메서드 선언 및 사용 하 여 별도 정의 모두의 조합 합니다 `default` 키워드와 `override` 키워드입니다. 자세한 내용 및 예제를 참조 하세요 [메서드](members/methods.md)합니다.

클래스는 추상 선언 되지만 정의 되지 않은 추상 메서드가 필요한 경우에 간주 됩니다. 따라서 추상 메서드가 있는 클래스는 반드시 추상 클래스가 없습니다. 클래스의 추상 메서드를 정의 되지 않은 경우가 아니면 사용 하지 않는 합니다 **AbstractClass** 특성입니다.

이전 구문에서 *접근성 한정자* 될 수 있습니다 `public`를 `private` 또는 `internal`합니다. 자세한 내용은 [액세스 제어](access-control.md)를 참조하세요.

다른 형식과 마찬가지로 추상 클래스는 기본 클래스와 하나 이상의 기본 인터페이스를 가질 수 있습니다. 각 기본 클래스 또는 인터페이스와 함께 별도 줄에 표시 되는 `inherit` 키워드입니다.

추상 클래스의 형식 정의는 완벽 하 게 정의 된 멤버를 포함할 수 있습니다 하지만 추상 멤버를 포함할 수도 있습니다. 추상 멤버를 포함 하는 구문은 이전 구문에서 별도로 표시 됩니다. 이 구문에서은 *형식 시그니처* 멤버의 목록을 포함 하는 순서는 반환 형식에는 매개 변수 형식으로 구분 됩니다 `->` 토큰 및/또는 `*` 변환에 대 한 적절 하 게 토큰 및 튜플 되었을 수 있는 매개 변수입니다. 추상 멤버 형식 서명에 대 한 구문을 서명 파일에서 사용 하 고 Visual Studio 코드 편집기에서 IntelliSense에서 표시와 같습니다.

다음 코드에는 추상 클래스를 두 비추상 파생된 클래스, 사각형, 원에 있는 셰이프를 보여 줍니다. 추상 클래스, 메서드 및 속성을 사용 하는 방법을 보여 줍니다. 예제에서는 추상 클래스 모양 구체적 엔터티 원과 사각형의 공통 요소를 나타냅니다. 셰이프 (2 차원 좌표 시스템)의 일반적인 기능 셰이프 클래스로 추상화 됩니다: 면적 및 둘레 속성 표, 회전 각도에 위치 합니다. 이 재정의할 수 있습니다 위치를 변경할 수 없습니다 개별 셰이프는 동작을 제외 하 고 있습니다.

대칭성 회전 고정이 Circle 클래스에서와 같이 회전 메서드를 재정의할 수 있습니다. 따라서 Circle 클래스에서 회전 메서드는 아무 작업도 수행 하지 하는 메서드에서 대체 됩니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2901.fs)]

**출력:**

```
Perimeter of square with side length 10.000000 is 40.000000
Circumference of circle with radius 5.000000 is 31.415927
Area of Square: 100.000000
Area of Circle: 78.539816
```

## <a name="see-also"></a>참고자료

- [클래스](classes.md)
- [멤버](members/index.md)
- [메서드](members/methods.md)
- [속성](members/Properties.md)