---
title: 일반 텍스트 서식 지정
description: 'F # 응용 프로그램 및 스크립트에서 printf 및 기타 일반 텍스트 서식 지정을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 07/22/2020
ms.openlocfilehash: 6b14633e074961757d0f0cd258d1b1667f5fd8ee
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854921"
---
# <a name="plain-text-formatting"></a><span data-ttu-id="efdd7-103">일반 텍스트 서식 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-103">Plain text formatting</span></span>

<span data-ttu-id="efdd7-104">F # `printf` 에서는,, 및 관련 함수를 사용 하 여 일반 텍스트의 형식 선택 형식을 지원 `printfn` `sprintf` 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-104">F# supports type-checked formatting of plain text using `printf`, `printfn`, `sprintf`, and related functions.</span></span>
<span data-ttu-id="efdd7-105">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-105">For example,</span></span>

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

<span data-ttu-id="efdd7-106">출력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-106">gives the output</span></span>

```fsharp
Hello world, 2 + 2 is 4
```

<span data-ttu-id="efdd7-107">또한 F #에서는 구조적 값을 일반 텍스트로 서식 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-107">F# also allows structured values to be formatted as plain text.</span></span>
<span data-ttu-id="efdd7-108">예를 들어 다음 예제에서는 출력을 매트릭스와 유사한 튜플 표시로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-108">For example, consider the following example that formats the output as a matrix-like display of tuples.</span></span>

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

<span data-ttu-id="efdd7-109">`%A`서식 문자열에 형식을 사용 하는 경우 구조적 일반 텍스트 형식이 활성화 됩니다 `printf` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-109">Structured plain text formatting is activated when you use the `%A` format in `printf` formatting strings.</span></span>
<span data-ttu-id="efdd7-110">또한 F # interactive에서 값 출력의 서식을 지정할 때 활성화 됩니다. 여기에서 출력에는 추가 정보가 포함 되 고 추가로 사용자 지정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-110">It's also activated when formatting the output of values in F# interactive, where the output includes extra information and is additionally customizable.</span></span>
<span data-ttu-id="efdd7-111">일반 텍스트 서식 지정은 `x.ToString()` 디버깅, 로깅 및 기타 도구에서 암시적으로 발생 하는 값을 포함 하 여 F # 공용 구조체 및 레코드 값에 대 한 모든 호출을 통해 관찰할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-111">Plain text formatting is also observable through any calls to `x.ToString()` on F# union and record values, including those that occur implicitly in debugging, logging, and other tooling.</span></span>

## <a name="checking-of-printf-format-strings"></a><span data-ttu-id="efdd7-112">형식 문자열을 확인 하는 중 `printf`</span><span class="sxs-lookup"><span data-stu-id="efdd7-112">Checking of `printf`-format strings</span></span>

<span data-ttu-id="efdd7-113">`printf`형식 문자열의 printf 형식 지정자와 일치 하지 않는 인수와 함께 서식 함수를 사용 하는 경우 컴파일 시간 오류가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-113">A compile-time error will be reported if a `printf` formatting function is used with an argument that doesn't match the printf format specifiers in the format string.</span></span>  <span data-ttu-id="efdd7-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-114">For example,</span></span>

```fsharp
sprintf "Hello %s" (2+2)
```

<span data-ttu-id="efdd7-115">출력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-115">gives the output</span></span>

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

<span data-ttu-id="efdd7-116">기술적으로 말하면 `printf` 및 기타 관련 된 함수를 사용 하는 경우 F # 컴파일러의 특별 한 규칙은 형식 문자열로 전달 된 문자열 리터럴을 검사 하 여, 적용 되는 후속 인수가 사용 되는 형식 지정자와 일치 하는지 확인 하는 올바른 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-116">Technically speaking, when using `printf` and other related functions, a special rule in the F# compiler checks the string literal passed as the format string, ensuring the subsequent arguments applied are of the correct type to match the format specifiers used.</span></span>

## <a name="format-specifiers-for-printf"></a><span data-ttu-id="efdd7-117">형식 지정자`printf`</span><span class="sxs-lookup"><span data-stu-id="efdd7-117">Format specifiers for `printf`</span></span>

<span data-ttu-id="efdd7-118">형식에 대 한 형식 지정 `printf` 은 `%` 형식을 나타내는 표식을 사용 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-118">Format specifications for `printf` formats are strings with `%` markers that indicate format.</span></span> <span data-ttu-id="efdd7-119">형식 자리 표시자는 `%[flags][width][.precision][type]` 형식이 다음과 같이 해석 되는 위치로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-119">Format placeholders consist of `%[flags][width][.precision][type]` where the type is interpreted as follows:</span></span>

| <span data-ttu-id="efdd7-120">형식 지정자</span><span class="sxs-lookup"><span data-stu-id="efdd7-120">Format specifier</span></span>   | <span data-ttu-id="efdd7-121">유형</span><span class="sxs-lookup"><span data-stu-id="efdd7-121">Type(s)</span></span>        | <span data-ttu-id="efdd7-122">설명</span><span class="sxs-lookup"><span data-stu-id="efdd7-122">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | <span data-ttu-id="efdd7-123">부울</span><span class="sxs-lookup"><span data-stu-id="efdd7-123">bool</span></span>      | <span data-ttu-id="efdd7-124">또는로 형식이 지정 됨 `true``false`</span><span class="sxs-lookup"><span data-stu-id="efdd7-124">Formatted as `true` or `false`</span></span>                |
| `%s`               | <span data-ttu-id="efdd7-125">string</span><span class="sxs-lookup"><span data-stu-id="efdd7-125">string</span></span>    | <span data-ttu-id="efdd7-126">이스케이프 되지 않은 콘텐츠로 서식 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-126">Formatted as its unescaped contents</span></span>         |
| `%c`               | <span data-ttu-id="efdd7-127">char</span><span class="sxs-lookup"><span data-stu-id="efdd7-127">char</span></span>      | <span data-ttu-id="efdd7-128">문자 리터럴로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-128">Formatted as the character literal</span></span>  |
| <span data-ttu-id="efdd7-129">`%d`, `%i`</span><span class="sxs-lookup"><span data-stu-id="efdd7-129">`%d`, `%i`</span></span>         | <span data-ttu-id="efdd7-130">기본 정수 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-130">a basic integer type</span></span> | <span data-ttu-id="efdd7-131">기본 정수 형식이 서명 된 경우 부호 있는 10 진수 정수로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-131">Formatted as a decimal integer, signed if the basic integer type is signed</span></span> |
| `%u`               | <span data-ttu-id="efdd7-132">기본 정수 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-132">a basic integer type</span></span> | <span data-ttu-id="efdd7-133">부호 없는 10 진수 정수로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-133">Formatted as an unsigned decimal integer</span></span>   |
| <span data-ttu-id="efdd7-134">`%x`, `%X`</span><span class="sxs-lookup"><span data-stu-id="efdd7-134">`%x`, `%X`</span></span>         | <span data-ttu-id="efdd7-135">기본 정수 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-135">a basic integer type</span></span> | <span data-ttu-id="efdd7-136">부호 없는 16 진수 (각각 16 진수에 대 한 a-f 또는 A-f) 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-136">Formatted as an unsigned hexadecimal number (a-f or A-F for hex digits respectively)</span></span>  |
|  `%o`              | <span data-ttu-id="efdd7-137">기본 정수 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-137">a basic integer type</span></span> | <span data-ttu-id="efdd7-138">부호 없는 8 진수 숫자로 서식 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-138">Formatted as an unsigned octal number</span></span> |
| <span data-ttu-id="efdd7-139">`%e`, `%E`</span><span class="sxs-lookup"><span data-stu-id="efdd7-139">`%e`, `%E`</span></span>         | <span data-ttu-id="efdd7-140">기본 부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-140">a basic floating point type</span></span> | <span data-ttu-id="efdd7-141">형식에 부호 있는 값으로 서식이 지정 `[-]d.dddde[sign]ddd` 됩니다. 여기서 d는 단일 10 진수이 고, dddd는 하나 이상의 10 진수이 고, ddd는 정확히 3 자리 10 진수이 고, 부호는 또는입니다. `+``-`</span><span class="sxs-lookup"><span data-stu-id="efdd7-141">Formatted as a signed value having the form `[-]d.dddde[sign]ddd` where d is a single decimal digit, dddd is one or more decimal digits, ddd is exactly three decimal digits, and sign is `+` or `-`</span></span> |
| `%f`               | <span data-ttu-id="efdd7-142">기본 부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-142">a basic floating point type</span></span> | <span data-ttu-id="efdd7-143">형식을 가진 부호 있는 값으로 형식이 지정 `[-]dddd.dddd` `dddd` 됩니다. 여기서은 하나 이상의 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-143">Formatted as a signed value having the form `[-]dddd.dddd`, where `dddd` is one or more decimal digits.</span></span> <span data-ttu-id="efdd7-144">소수점 앞의 자릿수는 수의 크기에 따라 다르며, 소수점 뒤의 자릿수는 요청된 정밀도에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-144">The number of digits before the decimal point depends on the magnitude of the number, and the number of digits after the decimal point depends on the requested precision.</span></span> |
| <span data-ttu-id="efdd7-145">`%g`, `%G`</span><span class="sxs-lookup"><span data-stu-id="efdd7-145">`%g`, `%G`</span></span> | <span data-ttu-id="efdd7-146">기본 부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="efdd7-146">a basic floating point type</span></span> |  <span data-ttu-id="efdd7-147">또는 형식으로 인쇄 된 부호 있는 값으로를 사용 하 여 서식이 지정 된 `%f` `%e` 값 및 전체 자릿수에 대해 더 간결한 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-147">Formatted using as a signed value printed in `%f` or `%e` format, whichever is more compact for the given value and precision.</span></span> |
| `%M` | <span data-ttu-id="efdd7-148">`System.Decimal`값</span><span class="sxs-lookup"><span data-stu-id="efdd7-148">a `System.Decimal` value</span></span>  |    <span data-ttu-id="efdd7-149">형식 지정자를 사용 하 여 형식이 지정 됩니다. `"G"``System.Decimal.ToString(format)`</span><span class="sxs-lookup"><span data-stu-id="efdd7-149">Formatted using the `"G"` format specifier for `System.Decimal.ToString(format)`</span></span> |
| `%O` | <span data-ttu-id="efdd7-150">모든 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-150">any value</span></span>  |   <span data-ttu-id="efdd7-151">개체를 boxing 하 고 메서드를 호출 하 여 형식이 지정 됩니다. `System.Object.ToString()`</span><span class="sxs-lookup"><span data-stu-id="efdd7-151">Formatted by boxing the object and calling its `System.Object.ToString()` method</span></span> |
| `%A` | <span data-ttu-id="efdd7-152">모든 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-152">any value</span></span>  |   <span data-ttu-id="efdd7-153">기본 레이아웃 설정을 사용 하 여 [구조적 일반 텍스트 서식 지정](plaintext-formatting.md) 을 사용 하 여 서식 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-153">Formatted using [structured plain text formatting](plaintext-formatting.md) with the default layout settings</span></span> |
| `%a` | <span data-ttu-id="efdd7-154">모든 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-154">any value</span></span>  |   <span data-ttu-id="efdd7-155">두 개의 인수가 필요 합니다. 형식 지정 함수는 컨텍스트 매개 변수 및 값을 허용 하 고 특정 값은 인쇄 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-155">Requires two arguments: a formatting function accepting a context parameter and the value, and the particular value to print</span></span> |
| `%t` | <span data-ttu-id="efdd7-156">모든 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-156">any value</span></span>  |   <span data-ttu-id="efdd7-157">하나의 인수가 필요 합니다. 형식 지정 함수는 적절 한 텍스트를 출력 하거나 반환 하는 컨텍스트 매개 변수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-157">Requires one argument: a formatting function accepting a context parameter that either outputs or returns the appropriate text</span></span> |

<span data-ttu-id="efdd7-158">기본 정수 형식은 `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), (), (), (), (), (), (), () `int16` `System.Int16` `uint16` `System.UInt16` `int32` `System.Int32` `uint32` `System.UInt32` `int64` `System.Int64` `uint64` `System.UInt64` `nativeint` `System.IntPtr` 및 () `unativeint` `System.UIntPtr` 입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-158">Basic integer types are `byte` (`System.Byte`), `sbyte` (`System.SByte`), `int16` (`System.Int16`), `uint16` (`System.UInt16`), `int32` (`System.Int32`), `uint32` (`System.UInt32`), `int64` (`System.Int64`), `uint64` (`System.UInt64`), `nativeint`  (`System.IntPtr`), and `unativeint`  (`System.UIntPtr`).</span></span>
<span data-ttu-id="efdd7-159">기본 부동 소수점 형식은 `float` ( `System.Double` ) 및 `float32` ( `System.Single` )입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-159">Basic floating point types are `float` (`System.Double`) and `float32` (`System.Single`).</span></span>

<span data-ttu-id="efdd7-160">선택적 너비는 결과의 최소 너비를 나타내는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-160">The optional width is an integer indicating the minimal width of the result.</span></span> <span data-ttu-id="efdd7-161">예를 들어는 `%6d` 정수를 인쇄 하 여 6 자 이상으로 채울 수 있는 공백을 접두사로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-161">For instance, `%6d` prints an integer, prefixing it with spaces to fill at least six characters.</span></span> <span data-ttu-id="efdd7-162">Width가 이면 `*` 추가 정수 인수를 사용 하 여 해당 너비를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-162">If width is `*`, then an extra integer  argument is taken to specify the corresponding width.</span></span>

<span data-ttu-id="efdd7-163">유효한 플래그는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-163">Valid flags are:</span></span>

| <span data-ttu-id="efdd7-164">플래그</span><span class="sxs-lookup"><span data-stu-id="efdd7-164">Flag</span></span>   | <span data-ttu-id="efdd7-165">효과</span><span class="sxs-lookup"><span data-stu-id="efdd7-165">Effect</span></span>        | <span data-ttu-id="efdd7-166">설명</span><span class="sxs-lookup"><span data-stu-id="efdd7-166">Remarks</span></span>                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | <span data-ttu-id="efdd7-167">필요한 너비를 구성 하려면 공백 대신 0을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-167">Add zeros instead of spaces to make up the required width</span></span> |    |
| `-` |  <span data-ttu-id="efdd7-168">지정 된 너비 내에서 결과를 왼쪽에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-168">Left justify the result within the specified width</span></span> |   |
| `+`  | <span data-ttu-id="efdd7-169">`+`숫자가 양수 이면 문자를 추가 합니다 (부정 부호와 일치 하는 경우 `-` ).</span><span class="sxs-lookup"><span data-stu-id="efdd7-169">Add a `+` character if the number is positive (to match a `-` sign for negatives)</span></span> |   |
| <span data-ttu-id="efdd7-170">공백 문자</span><span class="sxs-lookup"><span data-stu-id="efdd7-170">space character</span></span> | <span data-ttu-id="efdd7-171">숫자가 양수 이면 추가 공백을 추가 합니다 (부정의 '-' 부호와 일치).</span><span class="sxs-lookup"><span data-stu-id="efdd7-171">Add an extra space if the number is positive (to match a '-' sign for negatives)</span></span> |

<span data-ttu-id="efdd7-172">Printf `#` 플래그가 잘못 되었으며 사용 되는 경우 컴파일 타임 오류가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-172">The printf `#` flag is invalid and a compile-time error will be reported if it is used.</span></span>

<span data-ttu-id="efdd7-173">값은 고정 문화권을 사용 하 여 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-173">Values are formatted using invariant culture.</span></span> <span data-ttu-id="efdd7-174">문화권 설정은 `printf` 및 형식 지정의 결과에 영향을 주는 경우를 제외 하 고는 서식 지정 `%O` 과 관련이 `%A` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-174">Culture settings are irrelevant to `printf` formatting except when they affect the results of `%O` and `%A` formatting.</span></span> <span data-ttu-id="efdd7-175">자세한 내용은 [구조적 일반 텍스트 서식 지정](plaintext-formatting.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efdd7-175">For more information, see [structured plain text formatting](plaintext-formatting.md).</span></span>

## <a name="a-formatting"></a><span data-ttu-id="efdd7-176">`%A`서식 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-176">`%A` formatting</span></span>

<span data-ttu-id="efdd7-177">`%A`형식 지정자는 사람이 읽을 수 있는 방식으로 값의 형식을 지정 하는 데 사용 되며 진단 정보를 보고 하는 데에도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-177">The `%A` format specifier is used to format values in a human-readable way, and can also be useful for reporting diagnostic information.</span></span>

### <a name="primitive-values"></a><span data-ttu-id="efdd7-178">기본 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-178">Primitive values</span></span>

<span data-ttu-id="efdd7-179">지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` F # 숫자 값은 접미사와 고정 문화권으로 서식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-179">When formatting plain text using the `%A` specifier, F# numeric values are formatted with their suffix and invariant culture.</span></span> <span data-ttu-id="efdd7-180">부동 소수점 값은 부동 소수점 전체 자릿수 10 개를 사용 하 여 서식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-180">Floating point values are formatted using 10 places of floating point precision.</span></span> <span data-ttu-id="efdd7-181">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-181">For example,</span></span>

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

<span data-ttu-id="efdd7-182">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-182">produces</span></span>

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

<span data-ttu-id="efdd7-183">지정자를 사용 하는 경우 `%A` 따옴표를 사용 하 여 문자열의 서식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-183">When using the `%A` specifier, strings are formatted using quotes.</span></span> <span data-ttu-id="efdd7-184">이스케이프 코드는 추가 되지 않고 대신 원시 문자를 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-184">Escape codes are not added and instead the raw characters are printed.</span></span> <span data-ttu-id="efdd7-185">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-185">For example,</span></span>

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

<span data-ttu-id="efdd7-186">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-186">produces</span></span>

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a><span data-ttu-id="efdd7-187">.NET 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-187">.NET values</span></span>

<span data-ttu-id="efdd7-188">지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` `x.ToString()` 및에서 제공 하는 .net의 기본 설정을 사용 하 여 비 F # .net 개체의 형식을 지정 합니다 `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-188">When formatting plain text using the `%A` specifier, non-F# .NET objects are formatted by using `x.ToString()` using the default settings of .NET given by `System.Globalization.CultureInfo.CurrentCulture` and `System.Globalization.CultureInfo.CurrentUICulture`.</span></span>  <span data-ttu-id="efdd7-189">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-189">For example,</span></span>

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

<span data-ttu-id="efdd7-190">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-190">produces</span></span>

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a><span data-ttu-id="efdd7-191">구조적 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-191">Structured values</span></span>

<span data-ttu-id="efdd7-192">지정자를 사용 하 여 일반 텍스트의 서식을 지정 하는 경우 `%A` F # 목록 및 튜플에 대해 블록 들여쓰기가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-192">When formatting plain text using the `%A` specifier, block indentation is used for F# lists and tuples.</span></span> <span data-ttu-id="efdd7-193">이전 예제에 표시 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-193">This shown in the previous example.</span></span>
<span data-ttu-id="efdd7-194">다차원 배열을 비롯 한 배열의 구조도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-194">The structure of arrays is also used, including multi-dimensional arrays.</span></span>  <span data-ttu-id="efdd7-195">1 차원 배열에는 구문이 표시 됩니다 `[| ... |]` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-195">Single-dimensional arrays are shown with `[| ... |]` syntax.</span></span> <span data-ttu-id="efdd7-196">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-196">For example,</span></span>

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

<span data-ttu-id="efdd7-197">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-197">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

<span data-ttu-id="efdd7-198">기본 인쇄 너비는 80입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-198">The default print width is 80.</span></span>  <span data-ttu-id="efdd7-199">이 너비는 서식 지정자에서 인쇄 너비를 사용 하 여 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-199">This width can be customized by using a print width in the format specifier.</span></span> <span data-ttu-id="efdd7-200">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-200">For example,</span></span>

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

<span data-ttu-id="efdd7-201">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-201">produces</span></span>

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

<span data-ttu-id="efdd7-202">인쇄 너비를 0으로 지정 하면 인쇄 너비가 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-202">Specifying a print width of 0 results in no print width being used.</span></span> <span data-ttu-id="efdd7-203">출력의 포함 된 문자열이 줄 바꿈을 포함 하는 경우를 제외 하 고 한 줄의 텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-203">A single line of text will result, except where embedded strings in the output contain line breaks.</span></span>  <span data-ttu-id="efdd7-204">예</span><span class="sxs-lookup"><span data-stu-id="efdd7-204">For example</span></span>

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

<span data-ttu-id="efdd7-205">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-205">produces</span></span>

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

<span data-ttu-id="efdd7-206">4의 깊이 한도가로 표시 되는 sequence ( `IEnumerable` ) 값에 사용 됩니다 `seq { ...}` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-206">A depth limit of 4 is used for sequence (`IEnumerable`) values, which are shown as `seq { ...}`.</span></span> <span data-ttu-id="efdd7-207">목록 및 배열 값에는 100의 깊이 제한이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-207">A depth limit of 100 is used for list and array values.</span></span>
<span data-ttu-id="efdd7-208">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-208">For example,</span></span>

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

<span data-ttu-id="efdd7-209">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-209">produces</span></span>

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

<span data-ttu-id="efdd7-210">블록 들여쓰기는 공용 레코드 및 공용 구조체 값의 구조에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-210">Block indentation is also used for the structure of public record and union values.</span></span> <span data-ttu-id="efdd7-211">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-211">For example,</span></span>

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="efdd7-212">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-212">produces</span></span>

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

<span data-ttu-id="efdd7-213">를 사용 하는 경우에는 `%+A` 리플렉션을 사용 하 여 레코드와 공용 구조체의 전용 구조도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-213">If `%+A` is used, then the private structure of records and unions is also revealed by using reflection.</span></span> <span data-ttu-id="efdd7-214">예</span><span class="sxs-lookup"><span data-stu-id="efdd7-214">For example</span></span>

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

<span data-ttu-id="efdd7-215">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-215">produces</span></span>

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a><span data-ttu-id="efdd7-216">큼, 순환 또는 깊게 중첩 된 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-216">Large, cyclic, or deeply nested values</span></span>

<span data-ttu-id="efdd7-217">큰 구조화 된 값은 최대 1만의 전체 개체 노드 수로 형식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-217">Large structured values are formatted to a maximum overall object node count of 10000.</span></span>
<span data-ttu-id="efdd7-218">깊이 중첩 된 값의 형식은 100입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-218">Deeply nested values are formatted to a depth of 100.</span></span>  <span data-ttu-id="efdd7-219">두 경우 모두를 `...` 사용 하 여 일부 출력을 elide 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-219">In both cases `...` is used to elide some of the output.</span></span>  <span data-ttu-id="efdd7-220">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-220">For example,</span></span>

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

<span data-ttu-id="efdd7-221">생략 일부를 사용 하 여 많은 출력을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-221">produces a large output with some parts elided:</span></span>

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

<span data-ttu-id="efdd7-222">주기는 개체 그래프에서 감지 되 고 `...` 사이클이 검색 된 위치에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-222">Cycles are detected in the object graphs and `...` is used at places where cycles are detected.</span></span> <span data-ttu-id="efdd7-223">예</span><span class="sxs-lookup"><span data-stu-id="efdd7-223">For example</span></span>

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

<span data-ttu-id="efdd7-224">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-224">produces</span></span>

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a><span data-ttu-id="efdd7-225">Lazy, null 및 함수 값</span><span class="sxs-lookup"><span data-stu-id="efdd7-225">Lazy, null, and function values</span></span>

<span data-ttu-id="efdd7-226">`Value is not created`값이 아직 계산 되지 않은 경우 지연 값은 또는 동등한 텍스트로 인쇄 됩니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-226">Lazy values are printed as `Value is not created` or equivalent text when the value has not yet been evaluated.</span></span>

<span data-ttu-id="efdd7-227">Null 값은 `null` 값의 정적 형식이 공용 구조체 형식으로 결정 되는 경우를 제외 하 고는로 출력 됩니다 `null` . 여기서가 허용 되는 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-227">Null values are printed as `null` unless the static type of the value is determined to be a union type where `null` is a permitted representation.</span></span>

<span data-ttu-id="efdd7-228">F # 함수 값은 내부적으로 생성 된 클로저 이름으로 인쇄 됩니다 (예:) `<fun:it@43-7>` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-228">F# function values are printed as their internally generated closure name, for example, `<fun:it@43-7>`.</span></span>

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a><span data-ttu-id="efdd7-229">일반 텍스트 서식 지정 사용자 지정`StructuredFormatDisplay`</span><span class="sxs-lookup"><span data-stu-id="efdd7-229">Customize plain text formatting with `StructuredFormatDisplay`</span></span>

<span data-ttu-id="efdd7-230">지정자를 사용 하는 경우 `%A` `StructuredFormatDisplay` 형식 선언에 특성이 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-230">When using the `%A` specifier, the presence of the `StructuredFormatDisplay` attribute on type declarations is respected.</span></span>  <span data-ttu-id="efdd7-231">서로게이트 텍스트와 속성을 지정 하 여 값을 표시 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-231">This can be used to specify surrogate text and property to display a value.</span></span> <span data-ttu-id="efdd7-232">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="efdd7-232">For example:</span></span>

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

<span data-ttu-id="efdd7-233">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-233">produces</span></span>

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a><span data-ttu-id="efdd7-234">재정의 하 여 일반 텍스트 서식 지정`ToString`</span><span class="sxs-lookup"><span data-stu-id="efdd7-234">Customize plain text formatting by overriding `ToString`</span></span>

<span data-ttu-id="efdd7-235">의 기본 구현은 `ToString` F # 프로그래밍에서 관찰 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-235">The default implementation of `ToString` is observable in F# programming.</span></span> <span data-ttu-id="efdd7-236">기본 결과는 프로그래머 지향 정보 표시 또는 사용자 출력에 사용 하기에 적합 하지 않은 경우가 많으므로 기본 구현을 재정의 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-236">Often, the default results aren't suitable for use in either programmer-facing information display or user output, and as a result it is common to override the default implementation.</span></span>  

<span data-ttu-id="efdd7-237">기본적으로 F # 레코드 및 공용 구조체 형식은를 `ToString` 사용 하는 구현을 사용 하 여의 구현을 재정의 합니다 `sprintf "%+A"` .</span><span class="sxs-lookup"><span data-stu-id="efdd7-237">By default, F# record and union types override the implementation of `ToString` with an implementation that uses `sprintf "%+A"`.</span></span>  <span data-ttu-id="efdd7-238">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-238">For example,</span></span>

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

<span data-ttu-id="efdd7-239">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-239">produces</span></span>

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

<span data-ttu-id="efdd7-240">클래스 형식의 경우의 기본 구현을 제공 하지 `ToString` 않으며 .net 기본값을 사용 하 여 형식의 이름을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-240">For class types, no default implementation of `ToString` is provided and the .NET default is used, which reports the name of the type.</span></span> <span data-ttu-id="efdd7-241">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-241">For example,</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="efdd7-242">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-242">produces</span></span>

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

<span data-ttu-id="efdd7-243">에 대 한 재정의를 추가 `ToString` 하면 서식 지정이 더 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-243">Adding an override for `ToString` can give better formatting.</span></span>

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

<span data-ttu-id="efdd7-244">예제의</span><span class="sxs-lookup"><span data-stu-id="efdd7-244">produces</span></span>

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="efdd7-245">F# 대화형 구조적 인쇄</span><span class="sxs-lookup"><span data-stu-id="efdd7-245">F# Interactive structured printing</span></span>

<span data-ttu-id="efdd7-246">F# 대화형 ( `dotnet fsi` )는 확장 된 버전의 구조적 일반 텍스트 서식을 사용 하 여 값을 보고 하 고 추가 사용자 지정 가능성를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-246">F# Interactive (`dotnet fsi`) uses an extended version of structured plain text formatting to report values and allows additional customizability.</span></span> <span data-ttu-id="efdd7-247">자세한 내용은 [F# 대화형](fsharp-interactive-options.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="efdd7-247">For more information, see [F# Interactive](fsharp-interactive-options.md).</span></span>

## <a name="customize-debug-displays"></a><span data-ttu-id="efdd7-248">디버그 표시 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="efdd7-248">Customize debug displays</span></span>

<span data-ttu-id="efdd7-249">.NET 용 디버거는 및와 같은 특성을 사용 `DebuggerDisplay` `DebuggerTypeProxy` 하며, 이러한 특성은 디버거 검사 창에서 개체의 구조적 표시에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-249">Debuggers for .NET respect the use of attributes such as `DebuggerDisplay` and `DebuggerTypeProxy`, and these affect the structured display of objects in debugger inspection windows.</span></span>
<span data-ttu-id="efdd7-250">F # 컴파일러는 구별 된 공용 구조체 및 레코드 형식에 대해 이러한 특성을 자동으로 생성 하지만 클래스, 인터페이스 또는 구조체 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-250">The F# compiler automatically generated these attributes for discriminated union and record types, but not class, interface, or struct types.</span></span>

<span data-ttu-id="efdd7-251">이러한 특성은 F # 일반 텍스트 서식에서 무시 되지만 F # 형식을 디버그할 때 표시를 향상 시키기 위해 이러한 메서드를 구현 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efdd7-251">These attributes are ignored in F# plain text formatting, but it can be useful to implement these methods to improve displays when debugging F# types.</span></span>

## <a name="see-also"></a><span data-ttu-id="efdd7-252">참조</span><span class="sxs-lookup"><span data-stu-id="efdd7-252">See also</span></span>

- [<span data-ttu-id="efdd7-253">문자열</span><span class="sxs-lookup"><span data-stu-id="efdd7-253">Strings</span></span>](strings.md)
- [<span data-ttu-id="efdd7-254">레코드</span><span class="sxs-lookup"><span data-stu-id="efdd7-254">Records</span></span>](records.md)
- [<span data-ttu-id="efdd7-255">구별된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="efdd7-255">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="efdd7-256">F# 대화형</span><span class="sxs-lookup"><span data-stu-id="efdd7-256">F# Interactive</span></span>](fsharp-interactive-options.md)
