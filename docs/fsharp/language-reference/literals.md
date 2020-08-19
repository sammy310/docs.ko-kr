---
title: 리터럴
description: 'F # 프로그래밍 언어의 리터럴 형식에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 15f73db3c36f7c60ab1eeba96c63a28ebc6d7f01
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559156"
---
# <a name="literals"></a><span data-ttu-id="4d67f-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="4d67f-103">Literals</span></span>

<span data-ttu-id="4d67f-104">이 문서에서는 F #에서 리터럴의 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="4d67f-105">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="4d67f-105">Literal types</span></span>

<span data-ttu-id="4d67f-106">다음 표에서는 F #의 리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-106">The following table shows the literal types in F#.</span></span> <span data-ttu-id="4d67f-107">16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자를 구분 하지 않습니다. 형식을 식별 하는 문자는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-107">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="4d67f-108">Type</span><span class="sxs-lookup"><span data-stu-id="4d67f-108">Type</span></span>|<span data-ttu-id="4d67f-109">Description</span><span class="sxs-lookup"><span data-stu-id="4d67f-109">Description</span></span>|<span data-ttu-id="4d67f-110">접미사 또는 접두사</span><span class="sxs-lookup"><span data-stu-id="4d67f-110">Suffix or prefix</span></span>|<span data-ttu-id="4d67f-111">예제</span><span class="sxs-lookup"><span data-stu-id="4d67f-111">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="4d67f-112">sbyte</span><span class="sxs-lookup"><span data-stu-id="4d67f-112">sbyte</span></span>|<span data-ttu-id="4d67f-113">부호 있는 8 비트 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-113">signed 8-bit integer</span></span>|<span data-ttu-id="4d67f-114">y</span><span class="sxs-lookup"><span data-stu-id="4d67f-114">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="4d67f-115">byte</span><span class="sxs-lookup"><span data-stu-id="4d67f-115">byte</span></span>|<span data-ttu-id="4d67f-116">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="4d67f-116">unsigned 8-bit natural number</span></span>|<span data-ttu-id="4d67f-117">uy</span><span class="sxs-lookup"><span data-stu-id="4d67f-117">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="4d67f-118">int16</span><span class="sxs-lookup"><span data-stu-id="4d67f-118">int16</span></span>|<span data-ttu-id="4d67f-119">부호 있는 16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-119">signed 16-bit integer</span></span>|<span data-ttu-id="4d67f-120">s</span><span class="sxs-lookup"><span data-stu-id="4d67f-120">s</span></span>|`86s`|
|<span data-ttu-id="4d67f-121">uint16</span><span class="sxs-lookup"><span data-stu-id="4d67f-121">uint16</span></span>|<span data-ttu-id="4d67f-122">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="4d67f-122">unsigned 16-bit natural number</span></span>|<span data-ttu-id="4d67f-123">us</span><span class="sxs-lookup"><span data-stu-id="4d67f-123">us</span></span>|`86us`|
|<span data-ttu-id="4d67f-124">int</span><span class="sxs-lookup"><span data-stu-id="4d67f-124">int</span></span><br /><br /><span data-ttu-id="4d67f-125">int32</span><span class="sxs-lookup"><span data-stu-id="4d67f-125">int32</span></span>|<span data-ttu-id="4d67f-126">부호 있는 32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-126">signed 32-bit integer</span></span>|<span data-ttu-id="4d67f-127">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="4d67f-127">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="4d67f-128">uint</span><span class="sxs-lookup"><span data-stu-id="4d67f-128">uint</span></span><br /><br /><span data-ttu-id="4d67f-129">uint32</span><span class="sxs-lookup"><span data-stu-id="4d67f-129">uint32</span></span>|<span data-ttu-id="4d67f-130">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="4d67f-130">unsigned 32-bit natural number</span></span>|<span data-ttu-id="4d67f-131">u 또는 ul</span><span class="sxs-lookup"><span data-stu-id="4d67f-131">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="4d67f-132">nativeint</span><span class="sxs-lookup"><span data-stu-id="4d67f-132">nativeint</span></span>|<span data-ttu-id="4d67f-133">부호 있는 자연 숫자에 대 한 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-133">native pointer to a signed natural number</span></span>|<span data-ttu-id="4d67f-134">n</span><span class="sxs-lookup"><span data-stu-id="4d67f-134">n</span></span>|`123n`|
|<span data-ttu-id="4d67f-135">unativeint</span><span class="sxs-lookup"><span data-stu-id="4d67f-135">unativeint</span></span>|<span data-ttu-id="4d67f-136">부호 없는 자연 숫자로 된 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="4d67f-136">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="4d67f-137">되지</span><span class="sxs-lookup"><span data-stu-id="4d67f-137">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="4d67f-138">int64</span><span class="sxs-lookup"><span data-stu-id="4d67f-138">int64</span></span>|<span data-ttu-id="4d67f-139">부호 있는 64 비트 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-139">signed 64-bit integer</span></span>|<span data-ttu-id="4d67f-140">L</span><span class="sxs-lookup"><span data-stu-id="4d67f-140">L</span></span>|`86L`|
|<span data-ttu-id="4d67f-141">uint64</span><span class="sxs-lookup"><span data-stu-id="4d67f-141">uint64</span></span>|<span data-ttu-id="4d67f-142">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="4d67f-142">unsigned 64-bit natural number</span></span>|<span data-ttu-id="4d67f-143">UL</span><span class="sxs-lookup"><span data-stu-id="4d67f-143">UL</span></span>|`86UL`|
|<span data-ttu-id="4d67f-144">single, float32</span><span class="sxs-lookup"><span data-stu-id="4d67f-144">single, float32</span></span>|<span data-ttu-id="4d67f-145">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="4d67f-145">32-bit floating point number</span></span>|<span data-ttu-id="4d67f-146">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="4d67f-146">F or f</span></span>|<span data-ttu-id="4d67f-147">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="4d67f-147">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="4d67f-148">lf</span><span class="sxs-lookup"><span data-stu-id="4d67f-148">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="4d67f-149">f 차례로</span><span class="sxs-lookup"><span data-stu-id="4d67f-149">float; double</span></span>|<span data-ttu-id="4d67f-150">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="4d67f-150">64-bit floating point number</span></span>|<span data-ttu-id="4d67f-151">없음</span><span class="sxs-lookup"><span data-stu-id="4d67f-151">none</span></span>|<span data-ttu-id="4d67f-152">`4.14` 또는 `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="4d67f-152">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="4d67f-153">LF</span><span class="sxs-lookup"><span data-stu-id="4d67f-153">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="4d67f-154">bigint</span><span class="sxs-lookup"><span data-stu-id="4d67f-154">bigint</span></span>|<span data-ttu-id="4d67f-155">64 비트 표현으로 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-155">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="4d67f-156">I</span><span class="sxs-lookup"><span data-stu-id="4d67f-156">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="4d67f-157">decimal</span><span class="sxs-lookup"><span data-stu-id="4d67f-157">decimal</span></span>|<span data-ttu-id="4d67f-158">고정 소수점 또는 유리수로 표현 되는 소수 자릿수입니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-158">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="4d67f-159">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="4d67f-159">M or m</span></span>|<span data-ttu-id="4d67f-160">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="4d67f-160">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="4d67f-161">Char</span><span class="sxs-lookup"><span data-stu-id="4d67f-161">Char</span></span>|<span data-ttu-id="4d67f-162">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="4d67f-162">Unicode character</span></span>|<span data-ttu-id="4d67f-163">없음</span><span class="sxs-lookup"><span data-stu-id="4d67f-163">none</span></span>|<span data-ttu-id="4d67f-164">`'a'` 또는 `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="4d67f-164">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="4d67f-165">String</span><span class="sxs-lookup"><span data-stu-id="4d67f-165">String</span></span>|<span data-ttu-id="4d67f-166">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="4d67f-166">Unicode string</span></span>|<span data-ttu-id="4d67f-167">없음</span><span class="sxs-lookup"><span data-stu-id="4d67f-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="4d67f-168">또는</span><span class="sxs-lookup"><span data-stu-id="4d67f-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="4d67f-169">또는</span><span class="sxs-lookup"><span data-stu-id="4d67f-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="4d67f-170">또는</span><span class="sxs-lookup"><span data-stu-id="4d67f-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="4d67f-171">[문자열](Strings.md)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4d67f-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="4d67f-172">byte</span><span class="sxs-lookup"><span data-stu-id="4d67f-172">byte</span></span>|<span data-ttu-id="4d67f-173">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="4d67f-173">ASCII character</span></span>|<span data-ttu-id="4d67f-174">b</span><span class="sxs-lookup"><span data-stu-id="4d67f-174">B</span></span>|`'a'B`|
|<span data-ttu-id="4d67f-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="4d67f-175">byte[]</span></span>|<span data-ttu-id="4d67f-176">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="4d67f-176">ASCII string</span></span>|<span data-ttu-id="4d67f-177">b</span><span class="sxs-lookup"><span data-stu-id="4d67f-177">B</span></span>|`"text"B`|
|<span data-ttu-id="4d67f-178">String 또는 byte []</span><span class="sxs-lookup"><span data-stu-id="4d67f-178">String or byte[]</span></span>|<span data-ttu-id="4d67f-179">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="4d67f-179">verbatim string</span></span>|<span data-ttu-id="4d67f-180">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="4d67f-180">@ prefix</span></span>|<span data-ttu-id="4d67f-181">`@"\\server\share"` 유니코드</span><span class="sxs-lookup"><span data-stu-id="4d67f-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="4d67f-182">`@"\\server\share"B` 부호</span><span class="sxs-lookup"><span data-stu-id="4d67f-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="4d67f-183">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="4d67f-183">Named literals</span></span>

<span data-ttu-id="4d67f-184">상수로 사용할 값은 [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) 특성으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-184">Values that are intended to be constants can be marked with the [Literal](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-literalattribute.html) attribute.</span></span> <span data-ttu-id="4d67f-185">이 특성은 값이 상수로 컴파일되는 효과를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="4d67f-186">패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 리터럴이 아니라 바인딩할 변수로 취급 되므로 리터럴을 정의할 때 일반적으로 초기 대문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

```fsharp
[<Literal>]
let SomeJson = """{"numbers":[1,2,3,4,5]}"""

[<Literal>]
let Literal1 = "a" + "b"

[<Literal>]
let FileLocation =   __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let Literal2 = 1 ||| 64

[<Literal>]
let Literal3 = System.IO.FileAccess.Read ||| System.IO.FileAccess.Write
```

## <a name="remarks"></a><span data-ttu-id="4d67f-187">설명</span><span class="sxs-lookup"><span data-stu-id="4d67f-187">Remarks</span></span>

<span data-ttu-id="4d67f-188">유니코드 문자열에는를 사용 하 여 지정할 수 있는 명시적 인코딩 ( `\u` 0000-FFFF) 또는 `\U` 유니코드 코드 포인트 (0010FFFF)를 나타내는 32 비트 16 진수 코드를 사용 하 여 지정할 수 있는 u t f-32 인코딩이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="4d67f-189">이외의 다른 비트 연산자를 사용할 `|||` 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d67f-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="4d67f-190">다른 기본의 정수</span><span class="sxs-lookup"><span data-stu-id="4d67f-190">Integers in other bases</span></span>

<span data-ttu-id="4d67f-191">`0x`, 또는 접두사를 사용 하 여 부호 있는 32 비트 정수를 16 진수, 8 진수 또는 이진으로 지정할 수도 있습니다 `0o` `0b` .</span><span class="sxs-lookup"><span data-stu-id="4d67f-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="4d67f-192">숫자 리터럴의 밑줄</span><span class="sxs-lookup"><span data-stu-id="4d67f-192">Underscores in numeric literals</span></span>

<span data-ttu-id="4d67f-193">숫자를 밑줄 문자 ()로 구분할 수 있습니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="4d67f-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```
