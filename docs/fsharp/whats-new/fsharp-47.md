---
title: 'F # 4.7의 새로운 내용 - F # 가이드'
description: F# 4.7에서 사용할 수 있는 새로운 기능에 대한 개요를 확인하세요.
ms.date: 11/27/2019
ms.openlocfilehash: 7a6e744a398719bcb55d168dd700459e0b122dd6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185873"
---
# <a name="whats-new-in-f-47"></a>F # 4.7의 새로운 내용

F # 4.7은 F # 언어에 여러 가지 개선 기능을 추가합니다.

## <a name="get-started"></a>시작하기

F# 4.7은 모든 .NET 코어 배포판 및 Visual Studio 툴링에서 사용할 수 있습니다. [F#로 시작하여](../get-started/index.md) 자세히 알아보십시오.

## <a name="language-version"></a>언어 버전

F # 4.7 컴파일러는 프로젝트 파일의 속성을 통해 효과적인 언어 버전을 설정하는 기능을 소개합니다.

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

값 `4.6`, `4.7`및 `latest` `preview`로 설정할 수 있습니다. 기본값은 `latest`입니다.

을 로 `preview`설정하면 컴파일러에서 구현된 모든 F# 미리 보기 기능이 활성화됩니다.

## <a name="implicit-yields"></a>암시적 수율

더 이상 형식을 유추할 수 있는 배열, 목록, 시퀀스 또는 계산 식에 `yield` 키워드를 적용할 필요가 없습니다. 다음 예제에서는 두 식 모두 `yield` F# 4.7 이전에 각 항목에 대한 명령문이 필요했습니다.

```fsharp
let s = seq { 1; 2; 3; 4; 5 }

let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]
```

단일 `yield` 키워드를 소개하는 경우 다른 모든 `yield` 항목도 해당 키워드에 적용해야 합니다.

암시적 수율은 시퀀스를 평평하게 하는 `yield!` 데 사용하는 식에서 사용할 때 활성화되지 않습니다. 이러한 경우 오늘도 계속 사용해야 `yield` 합니다.

## <a name="wildcard-identifiers"></a>와일드카드 식별자

클래스와 관련된 F# 코드에서 자체 식별자는 항상 멤버 선언에서 명시적이어야 합니다. 그러나 자체 식별자가 사용되지 않는 경우 전통적으로 이름 없는 자체 식별자를 나타내기 위해 이중 밑줄을 사용하는 것이 규칙이었습니다. 이제 단일 밑줄을 사용할 수 있습니다.

```fsharp
type C() =
    member _.M() = ()
```

루프에도 `for` 적용됩니다.

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a>들여쓰기 이완

F# 4.7 이전에는 기본 생성자 및 정적 멤버 인수에 대한 들여쓰기 요구 사항에 과도한 들여쓰기가 필요했습니다. 이제 단일 들여쓰기 범위만 필요합니다.

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
