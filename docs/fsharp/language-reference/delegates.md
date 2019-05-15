---
title: 대리자
description: 대리자를 사용 하는 방법에 알아봅니다 F#입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 0596b67530b0399df41dffdf855a07bce2bf4761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641981"
---
# <a name="delegates"></a>대리자

대리자 개체를 함수 호출을 나타냅니다. F#, 일반적으로 첫 번째 클래스 값;으로 기능을 나타내는 데 함수 값을 사용 해야 그러나 대리자.NET Framework에서 사용 되 고 예상 하는 Api를 사용 하 여 상호 운용 하는 경우 필요 하므로. 이러한도 사용할 수 있습니다 다른.NET Framework 언어에서 사용 하기 위한 라이브러리를 작성할 때.

## <a name="syntax"></a>구문

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a>설명

이전 구문에서 `type1` 은 인수 형식 또는 형식 및 `type2` 반환 형식을 나타냅니다. 으로 표현 되는 인수 형식을 `type1` 자동 변환 됩니다. 튜플 형식을 사용 하 여 대상 함수의 인수 변환 되는 경우이 형식 및 튜플 형식에 이미 있는 인수에 대 한 괄호로 묶인 튜플을 원인 중 하나입니다. 자동 (currying) 괄호 대상 메서드를 일치 하는 튜플 인수 집합을 제거 합니다. 각각의 경우에서 사용 해야 하는 구문에 대 한 코드 예제를 참조 하십시오.

대리자에 연결할 수 있습니다 F# 함수 값 및 정적 또는 인스턴스 메서드. F#함수 값 대리자 생성자에 인수로 직접 전달할 수 있습니다. 정적 메서드에 대 한 클래스 및 메서드 이름을 사용 하 여 대리자를 생성 합니다. 인스턴스 메서드의 인수로 메서드와 개체 인스턴스를 제공합니다. 두 경우 모두, 멤버 액세스 연산자 (`.`) 사용 됩니다.

`Invoke` 대리자 형식의 메서드로 캡슐화 된 함수를 호출 합니다. 또한 대리자는 괄호 없이 Invoke 메서드 이름을 참조 하 여 함수 값으로 전달할 수 있습니다.

다음 코드에서는 클래스에서 다양 한 메서드를 나타내는 대리자를 만드는 구문을 보여 줍니다. 메서드는 정적 메서드 또는 인스턴스 메서드, 인지 및 튜플 형식에서 커리 된 형식 인수가 있는지에 따라 선언 하 고 대리자를 할당 하는 구문은 약간 다릅니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

다음 코드는 일부 대리자를 사용 하 여 작업할 수는 여러 가지 방법을 보여 줍니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

이전 코드 예제의 출력은 다음과 같습니다.

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [매개 변수 및 인수](parameters-and-arguments.md)
- [이벤트](members/events.md)
