---
title: 리터럴
description: 'F # 프로그래밍 언어의 리터럴 형식에 대해 알아봅니다.'
ms.date: 06/28/2019
ms.openlocfilehash: 98d609a1cf0beb00c0dd4d45ea343aaa2280b62e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855025"
---
# <a name="literals"></a><span data-ttu-id="3122d-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="3122d-103">Literals</span></span>

<span data-ttu-id="3122d-104">이 문서에서는 F #에서 리터럴의 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-104">This article provides a table that shows how to specify the type of a literal in F#.</span></span>

> [!NOTE]
> <span data-ttu-id="3122d-105">F #에 대 한 docs.microsoft.com API 참조가 완전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-105">The docs.microsoft.com API reference for F# is not complete.</span></span> <span data-ttu-id="3122d-106">끊어진 링크가 있는 경우 대신 [F # 핵심 라이브러리 설명서](https://fsharp.github.io/fsharp-core-docs/) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3122d-106">If you encounter any broken links, reference [F# Core Library Documentation](https://fsharp.github.io/fsharp-core-docs/) instead.</span></span>

## <a name="literal-types"></a><span data-ttu-id="3122d-107">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="3122d-107">Literal types</span></span>

<span data-ttu-id="3122d-108">다음 표에서는 F #의 리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-108">The following table shows the literal types in F#.</span></span> <span data-ttu-id="3122d-109">16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자를 구분 하지 않습니다. 형식을 식별 하는 문자는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-109">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="3122d-110">Type</span><span class="sxs-lookup"><span data-stu-id="3122d-110">Type</span></span>|<span data-ttu-id="3122d-111">설명</span><span class="sxs-lookup"><span data-stu-id="3122d-111">Description</span></span>|<span data-ttu-id="3122d-112">접미사 또는 접두사</span><span class="sxs-lookup"><span data-stu-id="3122d-112">Suffix or prefix</span></span>|<span data-ttu-id="3122d-113">예</span><span class="sxs-lookup"><span data-stu-id="3122d-113">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="3122d-114">sbyte</span><span class="sxs-lookup"><span data-stu-id="3122d-114">sbyte</span></span>|<span data-ttu-id="3122d-115">부호 있는 8 비트 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-115">signed 8-bit integer</span></span>|<span data-ttu-id="3122d-116">y</span><span class="sxs-lookup"><span data-stu-id="3122d-116">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="3122d-117">byte</span><span class="sxs-lookup"><span data-stu-id="3122d-117">byte</span></span>|<span data-ttu-id="3122d-118">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="3122d-118">unsigned 8-bit natural number</span></span>|<span data-ttu-id="3122d-119">uy</span><span class="sxs-lookup"><span data-stu-id="3122d-119">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="3122d-120">int16</span><span class="sxs-lookup"><span data-stu-id="3122d-120">int16</span></span>|<span data-ttu-id="3122d-121">부호 있는 16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-121">signed 16-bit integer</span></span>|<span data-ttu-id="3122d-122">s</span><span class="sxs-lookup"><span data-stu-id="3122d-122">s</span></span>|`86s`|
|<span data-ttu-id="3122d-123">uint16</span><span class="sxs-lookup"><span data-stu-id="3122d-123">uint16</span></span>|<span data-ttu-id="3122d-124">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="3122d-124">unsigned 16-bit natural number</span></span>|<span data-ttu-id="3122d-125">us</span><span class="sxs-lookup"><span data-stu-id="3122d-125">us</span></span>|`86us`|
|<span data-ttu-id="3122d-126">Int</span><span class="sxs-lookup"><span data-stu-id="3122d-126">int</span></span><br /><br /><span data-ttu-id="3122d-127">int32</span><span class="sxs-lookup"><span data-stu-id="3122d-127">int32</span></span>|<span data-ttu-id="3122d-128">부호 있는 32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-128">signed 32-bit integer</span></span>|<span data-ttu-id="3122d-129">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="3122d-129">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="3122d-130">uint</span><span class="sxs-lookup"><span data-stu-id="3122d-130">uint</span></span><br /><br /><span data-ttu-id="3122d-131">uint32</span><span class="sxs-lookup"><span data-stu-id="3122d-131">uint32</span></span>|<span data-ttu-id="3122d-132">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="3122d-132">unsigned 32-bit natural number</span></span>|<span data-ttu-id="3122d-133">u 또는 ul</span><span class="sxs-lookup"><span data-stu-id="3122d-133">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="3122d-134">nativeint</span><span class="sxs-lookup"><span data-stu-id="3122d-134">nativeint</span></span>|<span data-ttu-id="3122d-135">부호 있는 자연 숫자에 대 한 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-135">native pointer to a signed natural number</span></span>|<span data-ttu-id="3122d-136">n</span><span class="sxs-lookup"><span data-stu-id="3122d-136">n</span></span>|`123n`|
|<span data-ttu-id="3122d-137">unativeint</span><span class="sxs-lookup"><span data-stu-id="3122d-137">unativeint</span></span>|<span data-ttu-id="3122d-138">부호 없는 자연 숫자로 된 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="3122d-138">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="3122d-139">되지</span><span class="sxs-lookup"><span data-stu-id="3122d-139">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="3122d-140">int64</span><span class="sxs-lookup"><span data-stu-id="3122d-140">int64</span></span>|<span data-ttu-id="3122d-141">부호 있는 64 비트 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-141">signed 64-bit integer</span></span>|<span data-ttu-id="3122d-142">L</span><span class="sxs-lookup"><span data-stu-id="3122d-142">L</span></span>|`86L`|
|<span data-ttu-id="3122d-143">uint64</span><span class="sxs-lookup"><span data-stu-id="3122d-143">uint64</span></span>|<span data-ttu-id="3122d-144">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="3122d-144">unsigned 64-bit natural number</span></span>|<span data-ttu-id="3122d-145">UL</span><span class="sxs-lookup"><span data-stu-id="3122d-145">UL</span></span>|`86UL`|
|<span data-ttu-id="3122d-146">single, float32</span><span class="sxs-lookup"><span data-stu-id="3122d-146">single, float32</span></span>|<span data-ttu-id="3122d-147">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="3122d-147">32-bit floating point number</span></span>|<span data-ttu-id="3122d-148">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="3122d-148">F or f</span></span>|<span data-ttu-id="3122d-149">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="3122d-149">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="3122d-150">lf</span><span class="sxs-lookup"><span data-stu-id="3122d-150">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="3122d-151">f 차례로</span><span class="sxs-lookup"><span data-stu-id="3122d-151">float; double</span></span>|<span data-ttu-id="3122d-152">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="3122d-152">64-bit floating point number</span></span>|<span data-ttu-id="3122d-153">none</span><span class="sxs-lookup"><span data-stu-id="3122d-153">none</span></span>|<span data-ttu-id="3122d-154">`4.14` 또는 `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="3122d-154">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="3122d-155">LF</span><span class="sxs-lookup"><span data-stu-id="3122d-155">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="3122d-156">bigint</span><span class="sxs-lookup"><span data-stu-id="3122d-156">bigint</span></span>|<span data-ttu-id="3122d-157">64 비트 표현으로 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-157">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="3122d-158">I</span><span class="sxs-lookup"><span data-stu-id="3122d-158">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="3122d-159">decimal</span><span class="sxs-lookup"><span data-stu-id="3122d-159">decimal</span></span>|<span data-ttu-id="3122d-160">고정 소수점 또는 유리수로 표현 되는 소수 자릿수입니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-160">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="3122d-161">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="3122d-161">M or m</span></span>|<span data-ttu-id="3122d-162">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="3122d-162">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="3122d-163">Char</span><span class="sxs-lookup"><span data-stu-id="3122d-163">Char</span></span>|<span data-ttu-id="3122d-164">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="3122d-164">Unicode character</span></span>|<span data-ttu-id="3122d-165">none</span><span class="sxs-lookup"><span data-stu-id="3122d-165">none</span></span>|<span data-ttu-id="3122d-166">`'a'` 또는 `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="3122d-166">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="3122d-167">String</span><span class="sxs-lookup"><span data-stu-id="3122d-167">String</span></span>|<span data-ttu-id="3122d-168">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="3122d-168">Unicode string</span></span>|<span data-ttu-id="3122d-169">none</span><span class="sxs-lookup"><span data-stu-id="3122d-169">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="3122d-170">또는</span><span class="sxs-lookup"><span data-stu-id="3122d-170">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="3122d-171">또는</span><span class="sxs-lookup"><span data-stu-id="3122d-171">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="3122d-172">또는</span><span class="sxs-lookup"><span data-stu-id="3122d-172">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="3122d-173">[문자열](Strings.md)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3122d-173">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="3122d-174">byte</span><span class="sxs-lookup"><span data-stu-id="3122d-174">byte</span></span>|<span data-ttu-id="3122d-175">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="3122d-175">ASCII character</span></span>|<span data-ttu-id="3122d-176">b</span><span class="sxs-lookup"><span data-stu-id="3122d-176">B</span></span>|`'a'B`|
|<span data-ttu-id="3122d-177">byte[]</span><span class="sxs-lookup"><span data-stu-id="3122d-177">byte[]</span></span>|<span data-ttu-id="3122d-178">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="3122d-178">ASCII string</span></span>|<span data-ttu-id="3122d-179">b</span><span class="sxs-lookup"><span data-stu-id="3122d-179">B</span></span>|`"text"B`|
|<span data-ttu-id="3122d-180">String 또는 byte []</span><span class="sxs-lookup"><span data-stu-id="3122d-180">String or byte[]</span></span>|<span data-ttu-id="3122d-181">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="3122d-181">verbatim string</span></span>|<span data-ttu-id="3122d-182">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="3122d-182">@ prefix</span></span>|<span data-ttu-id="3122d-183">`@"\\server\share"`유니코드</span><span class="sxs-lookup"><span data-stu-id="3122d-183">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="3122d-184">`@"\\server\share"B`부호</span><span class="sxs-lookup"><span data-stu-id="3122d-184">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="3122d-185">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="3122d-185">Named literals</span></span>

<span data-ttu-id="3122d-186">상수로 사용할 값은 [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-186">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="3122d-187">이 특성은 값이 상수로 컴파일되는 효과를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-187">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="3122d-188">패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 리터럴이 아니라 바인딩할 변수로 취급 되므로 리터럴을 정의할 때 일반적으로 초기 대문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-188">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="3122d-189">설명</span><span class="sxs-lookup"><span data-stu-id="3122d-189">Remarks</span></span>

<span data-ttu-id="3122d-190">유니코드 문자열에는를 사용 하 여 지정할 수 있는 명시적 인코딩 ( `\u` 0000-FFFF) 또는 `\U` 유니코드 코드 포인트 (0010FFFF)를 나타내는 32 비트 16 진수 코드를 사용 하 여 지정할 수 있는 u t f-32 인코딩이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-190">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="3122d-191">이외의 다른 비트 연산자를 사용할 `|||` 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3122d-191">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="3122d-192">다른 기본의 정수</span><span class="sxs-lookup"><span data-stu-id="3122d-192">Integers in other bases</span></span>

<span data-ttu-id="3122d-193">`0x`, 또는 접두사를 사용 하 여 부호 있는 32 비트 정수를 16 진수, 8 진수 또는 이진으로 지정할 수도 있습니다 `0o` `0b` .</span><span class="sxs-lookup"><span data-stu-id="3122d-193">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="3122d-194">숫자 리터럴의 밑줄</span><span class="sxs-lookup"><span data-stu-id="3122d-194">Underscores in numeric literals</span></span>

<span data-ttu-id="3122d-195">숫자를 밑줄 문자 ()로 구분할 수 있습니다 `_` .</span><span class="sxs-lookup"><span data-stu-id="3122d-195">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="3122d-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3122d-196">See also</span></span>

- [<span data-ttu-id="3122d-197">LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="3122d-197">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
