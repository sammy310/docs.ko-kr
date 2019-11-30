---
title: 4\.6의 F# 새로운 기능- F# 가이드
description: 4\.6에서 F# 사용할 수 있는 새 기능에 대 한 개요를 확인 하세요.
ms.date: 11/27/2019
ms.openlocfilehash: 81d3e988d044cb16f8ec079118fd0ede2dabc587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74644135"
---
# <a name="whats-new-in-f-46"></a>4\.6의 F# 새로운 기능

F#4.6는 언어에 대 한 F# 여러 가지 향상 된 기능을 추가 합니다.

## <a name="get-started"></a>시작

F#4.6는 모든 .NET Core 배포 및 Visual Studio 도구에서 사용할 수 있습니다. 를 [시작 F# ](../get-started/index.md) 하 여 자세히 알아보세요.

## <a name="anonymous-records"></a>익명 레코드

[익명 레코드](../language-reference/anonymous-records.md) 는 4.6에 F# 도입 된 F# 새로운 종류의 유형입니다. 사용 하기 전에 선언 하지 않아도 되는 명명 된 값의 단순 집계입니다. 구조체 또는 참조 형식 중 하나로 선언할 수 있습니다. 기본적으로 참조 형식입니다.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

값 형식을 그룹화 하 고 성능이 중요 한 시나리오에서 작동 하는 경우에 대 한 구조체로 선언할 수도 있습니다.

```fsharp
open System

let getCircleStats radius =
    let d = radius * 2.0
    let a = Math.PI * (radius ** 2.0)
    let c = 2.0 * Math.PI * radius

    struct {| Diameter = d; Area = a; Circumference = c |}

let r = 2.0
let stats = getCircleStats r
printfn "Circle with radius: %f has diameter %f, area %f, and circumference %f"
    r stats.Diameter stats.Area stats.Circumference
```

매우 강력 하 고 다양 한 시나리오에서 사용할 수 있습니다. [익명 레코드](../language-reference/anonymous-records.md)에서 자세히 알아보세요.

## <a name="valueoption-functions"></a>ValueOption 함수

4\.5에 F# 추가 된 valueoption 형식에는 이제 옵션 유형을 사용 하는 "모듈 바인딩된 함수 패리티"가 있습니다. 가장 일반적으로 사용 되는 예제는 다음과 같습니다.

```fsharp
// Multiply a value option by 2 if it has  value
let xOpt = ValueSome 99
let result = xOpt |> ValueOption.map (fun v -> v * 2)

// Reverse a string if it exists
let strOpt = ValueSome "Mirror image"
let reverse (str: string) =
    match str with
    | null
    | "" -> None
    | s ->
        str.ToCharArray()
        |> Array.rev
        |> string
        |> Some

let reversedString = strOpt |> Option.bind reverse
```

이렇게 하면 값 형식이 성능을 향상 시키는 시나리오에서 옵션과 마찬가지로 ValueOption을 사용할 수 있습니다.
