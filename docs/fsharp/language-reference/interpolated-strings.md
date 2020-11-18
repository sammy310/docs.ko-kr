---
title: 보간된 문자열
description: 'F # 식을 직접 포함할 수 있는 특수 한 형식의 문자열에 대해 알아봅니다.'
ms.date: 11/12/2020
ms.openlocfilehash: 8c552b44cea7d6c51ec333b6bdd4d407c6f10da7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829689"
---
# <a name="interpolated-strings"></a><span data-ttu-id="47b50-103">보간된 문자열</span><span class="sxs-lookup"><span data-stu-id="47b50-103">Interpolated strings</span></span>

<span data-ttu-id="47b50-104">보간된 문자열은 F # 식을 포함 하는 데 사용할 수 있는 [문자열](strings.md) 입니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="47b50-105">값 또는 식의 결과에 따라 문자열 값이 변경 될 수 있는 다양 한 시나리오에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="47b50-106">구문</span><span class="sxs-lookup"><span data-stu-id="47b50-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="47b50-107">설명</span><span class="sxs-lookup"><span data-stu-id="47b50-107">Remarks</span></span>

<span data-ttu-id="47b50-108">보간된 문자열을 사용 하면 문자열 리터럴 내에서 "구멍"으로 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="47b50-109">기본 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="47b50-110">각 중괄호 쌍 사이에 있는 내용은 `{}` 임의의 F # 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="47b50-111">중괄호 쌍을 이스케이프 하려면 `{}` 다음과 같이 두 가지를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="47b50-112">형식화 된 보간된 문자열</span><span class="sxs-lookup"><span data-stu-id="47b50-112">Typed interpolated strings</span></span>

<span data-ttu-id="47b50-113">보간된 문자열에는 형식 안전성을 적용 하기 위해 F # 형식 지정자도 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-113">Interpolated strings can also have F# format specifiers to enforce type safety.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="47b50-114">앞의 예제에서 코드는가 이어야 하는 값을 잘못 전달 `age` `name` 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="47b50-115">보간된 문자열은 형식 지정자를 사용 하기 때문에이는 미묘한 런타임 버그 대신 컴파일 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="47b50-116">[일반 텍스트 서식](plaintext-formatting.md) 에서 적용 되는 모든 형식 지정자는 보간된 문자열 내에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="47b50-117">축 자 보간된 문자열</span><span class="sxs-lookup"><span data-stu-id="47b50-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="47b50-118">F #은 문자열 리터럴을 포함할 수 있도록 삼중 따옴표를 사용 하 여 축 자 보간된 문자열을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="47b50-119">보간된 문자열에서 식 맞춤</span><span class="sxs-lookup"><span data-stu-id="47b50-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="47b50-120">를 사용 하 여 보간된 문자열 내에 식을 왼쪽으로 맞추거나 오른쪽에 맞추고, 공백 수를 지정할 수 있습니다 `|` .</span><span class="sxs-lookup"><span data-stu-id="47b50-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="47b50-121">다음 보간된 문자열은 왼쪽 및 오른쪽 식을 각각 일곱 개의 공백으로 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by seven spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="47b50-122">보간된 문자열 및 `FormattableString` 서식 지정</span><span class="sxs-lookup"><span data-stu-id="47b50-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="47b50-123">다음에 대 한 규칙을 준수 하는 서식도 적용할 수 있습니다 <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="47b50-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="47b50-124">또한 보간된 문자열은 형식 주석을 통해로 확인할 수도 있습니다 <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="47b50-124">Additionally, an interpolated string can also be type checked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="47b50-125">형식 주석은 보간된 문자열 식 자체에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47b50-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="47b50-126">F #은 보간된 문자열을으로 암시적으로 변환 하지 않습니다 <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="47b50-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="47b50-127">참조</span><span class="sxs-lookup"><span data-stu-id="47b50-127">See also</span></span>

* [<span data-ttu-id="47b50-128">문자열</span><span class="sxs-lookup"><span data-stu-id="47b50-128">Strings</span></span>](strings.md)
