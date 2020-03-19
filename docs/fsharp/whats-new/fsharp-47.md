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
# <a name="whats-new-in-f-47"></a><span data-ttu-id="744e0-103">F # 4.7의 새로운 내용</span><span class="sxs-lookup"><span data-stu-id="744e0-103">What's new in F# 4.7</span></span>

<span data-ttu-id="744e0-104">F # 4.7은 F # 언어에 여러 가지 개선 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-104">F# 4.7 adds multiple improvements to the F# language.</span></span>

## <a name="get-started"></a><span data-ttu-id="744e0-105">시작하기</span><span class="sxs-lookup"><span data-stu-id="744e0-105">Get started</span></span>

<span data-ttu-id="744e0-106">F# 4.7은 모든 .NET 코어 배포판 및 Visual Studio 툴링에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-106">F# 4.7 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="744e0-107">[F#로 시작하여](../get-started/index.md) 자세히 알아보십시오.</span><span class="sxs-lookup"><span data-stu-id="744e0-107">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="language-version"></a><span data-ttu-id="744e0-108">언어 버전</span><span class="sxs-lookup"><span data-stu-id="744e0-108">Language version</span></span>

<span data-ttu-id="744e0-109">F # 4.7 컴파일러는 프로젝트 파일의 속성을 통해 효과적인 언어 버전을 설정하는 기능을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-109">The F# 4.7 compiler introduces the ability to set your effective language version via a property in your project file:</span></span>

```xml
<PropertyGroup>
    <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="744e0-110">값 `4.6`, `4.7`및 `latest` `preview`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-110">You can set it to the values `4.6`, `4.7`, `latest`, and `preview`.</span></span> <span data-ttu-id="744e0-111">기본값은 `latest`입니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-111">The default is `latest`.</span></span>

<span data-ttu-id="744e0-112">을 로 `preview`설정하면 컴파일러에서 구현된 모든 F# 미리 보기 기능이 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-112">If you set it to `preview`, your compiler will activate all F# preview features that are implemented in your compiler.</span></span>

## <a name="implicit-yields"></a><span data-ttu-id="744e0-113">암시적 수율</span><span class="sxs-lookup"><span data-stu-id="744e0-113">Implicit yields</span></span>

<span data-ttu-id="744e0-114">더 이상 형식을 유추할 수 있는 배열, 목록, 시퀀스 또는 계산 식에 `yield` 키워드를 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-114">You no longer need to apply the `yield` keyword in arrays, lists, sequences, or computation expressions where the type can be inferred.</span></span> <span data-ttu-id="744e0-115">다음 예제에서는 두 식 모두 `yield` F# 4.7 이전에 각 항목에 대한 명령문이 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-115">In the following example, both expressions required the `yield` statement for each entry prior to F# 4.7:</span></span>

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

<span data-ttu-id="744e0-116">단일 `yield` 키워드를 소개하는 경우 다른 모든 `yield` 항목도 해당 키워드에 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-116">If you introduce a single `yield` keyword, every other item must also have `yield` applied to it.</span></span>

<span data-ttu-id="744e0-117">암시적 수율은 시퀀스를 평평하게 하는 `yield!` 데 사용하는 식에서 사용할 때 활성화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-117">Implicit yields are not activated when used in an expression that also uses `yield!` to do something like flatten a sequence.</span></span> <span data-ttu-id="744e0-118">이러한 경우 오늘도 계속 사용해야 `yield` 합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-118">You must continue to use `yield` today in these cases.</span></span>

## <a name="wildcard-identifiers"></a><span data-ttu-id="744e0-119">와일드카드 식별자</span><span class="sxs-lookup"><span data-stu-id="744e0-119">Wildcard identifiers</span></span>

<span data-ttu-id="744e0-120">클래스와 관련된 F# 코드에서 자체 식별자는 항상 멤버 선언에서 명시적이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-120">In F# code involving classes, the self-identifier needs to always be explicit in member declarations.</span></span> <span data-ttu-id="744e0-121">그러나 자체 식별자가 사용되지 않는 경우 전통적으로 이름 없는 자체 식별자를 나타내기 위해 이중 밑줄을 사용하는 것이 규칙이었습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-121">But in cases where the self-identifier is never used, it has traditionally been convention to use a double-underscore to indicate a nameless self-identifiers.</span></span> <span data-ttu-id="744e0-122">이제 단일 밑줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-122">You can now use a single underscore:</span></span>

```fsharp
type C() =
    member _.M() = ()
```

<span data-ttu-id="744e0-123">루프에도 `for` 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-123">This also applies for `for` loops:</span></span>

```fsharp
for _ in 1..10 do printfn "Hello!"
```

## <a name="indentation-relaxations"></a><span data-ttu-id="744e0-124">들여쓰기 이완</span><span class="sxs-lookup"><span data-stu-id="744e0-124">Indentation relaxations</span></span>

<span data-ttu-id="744e0-125">F# 4.7 이전에는 기본 생성자 및 정적 멤버 인수에 대한 들여쓰기 요구 사항에 과도한 들여쓰기가 필요했습니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-125">Prior to F# 4.7, the indentation requirements for primary constructor and static member arguments required excessive indentation.</span></span> <span data-ttu-id="744e0-126">이제 단일 들여쓰기 범위만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="744e0-126">They now only require a single indentation scope:</span></span>

```fsharp
type OffsideCheck(a:int,
    b:int, c:int,
    d:int) = class end

type C() =
    static member M(a:int,
        b:int, c:int,
        d:int) = 1
```
