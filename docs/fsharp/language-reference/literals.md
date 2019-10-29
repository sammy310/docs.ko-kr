---
title: 리터럴
description: F# 프로그래밍 언어의 리터럴 형식에 대해 알아봅니다.
ms.date: 06/28/2019
ms.openlocfilehash: 9792a24ac28eb402e35e78574cd6a2bf9526734d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73041042"
---
# <a name="literals"></a><span data-ttu-id="49bce-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="49bce-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="49bce-104">이 문서의 API 참조 링크를 통해 MSDN (현재)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="49bce-105">이 항목에서는에서 F#리터럴의 형식을 지정 하는 방법을 보여 주는 표를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="49bce-106">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="49bce-106">Literal Types</span></span>

<span data-ttu-id="49bce-107">다음 표에서는의 F#리터럴 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="49bce-108">16 진수 표기법으로 숫자를 나타내는 문자는 대/소문자를 구분 하지 않습니다. 형식을 식별 하는 문자는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="49bce-109">Type</span><span class="sxs-lookup"><span data-stu-id="49bce-109">Type</span></span>|<span data-ttu-id="49bce-110">설명</span><span class="sxs-lookup"><span data-stu-id="49bce-110">Description</span></span>|<span data-ttu-id="49bce-111">접미사 또는 접두사</span><span class="sxs-lookup"><span data-stu-id="49bce-111">Suffix or prefix</span></span>|<span data-ttu-id="49bce-112">예제</span><span class="sxs-lookup"><span data-stu-id="49bce-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="49bce-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="49bce-113">sbyte</span></span>|<span data-ttu-id="49bce-114">부호 있는 8 비트 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-114">signed 8-bit integer</span></span>|<span data-ttu-id="49bce-115">y</span><span class="sxs-lookup"><span data-stu-id="49bce-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="49bce-116">byte</span><span class="sxs-lookup"><span data-stu-id="49bce-116">byte</span></span>|<span data-ttu-id="49bce-117">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="49bce-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="49bce-118">uy</span><span class="sxs-lookup"><span data-stu-id="49bce-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="49bce-119">int16</span><span class="sxs-lookup"><span data-stu-id="49bce-119">int16</span></span>|<span data-ttu-id="49bce-120">부호 있는 16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-120">signed 16-bit integer</span></span>|<span data-ttu-id="49bce-121">초</span><span class="sxs-lookup"><span data-stu-id="49bce-121">s</span></span>|`86s`|
|<span data-ttu-id="49bce-122">uint16</span><span class="sxs-lookup"><span data-stu-id="49bce-122">uint16</span></span>|<span data-ttu-id="49bce-123">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="49bce-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="49bce-124">us</span><span class="sxs-lookup"><span data-stu-id="49bce-124">us</span></span>|`86us`|
|<span data-ttu-id="49bce-125">정수</span><span class="sxs-lookup"><span data-stu-id="49bce-125">int</span></span><br /><br /><span data-ttu-id="49bce-126">int32</span><span class="sxs-lookup"><span data-stu-id="49bce-126">int32</span></span>|<span data-ttu-id="49bce-127">부호 있는 32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-127">signed 32-bit integer</span></span>|<span data-ttu-id="49bce-128">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="49bce-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="49bce-129">uint</span><span class="sxs-lookup"><span data-stu-id="49bce-129">uint</span></span><br /><br /><span data-ttu-id="49bce-130">uint32</span><span class="sxs-lookup"><span data-stu-id="49bce-130">uint32</span></span>|<span data-ttu-id="49bce-131">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="49bce-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="49bce-132">u 또는 ul</span><span class="sxs-lookup"><span data-stu-id="49bce-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="49bce-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="49bce-133">nativeint</span></span>|<span data-ttu-id="49bce-134">부호 있는 자연 숫자에 대 한 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="49bce-135">n</span><span class="sxs-lookup"><span data-stu-id="49bce-135">n</span></span>|`123n`|
|<span data-ttu-id="49bce-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="49bce-136">unativeint</span></span>|<span data-ttu-id="49bce-137">부호 없는 자연 숫자로 된 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="49bce-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="49bce-138">되지</span><span class="sxs-lookup"><span data-stu-id="49bce-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="49bce-139">int64</span><span class="sxs-lookup"><span data-stu-id="49bce-139">int64</span></span>|<span data-ttu-id="49bce-140">부호 있는 64 비트 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-140">signed 64-bit integer</span></span>|<span data-ttu-id="49bce-141">L</span><span class="sxs-lookup"><span data-stu-id="49bce-141">L</span></span>|`86L`|
|<span data-ttu-id="49bce-142">uint64</span><span class="sxs-lookup"><span data-stu-id="49bce-142">uint64</span></span>|<span data-ttu-id="49bce-143">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="49bce-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="49bce-144">UL</span><span class="sxs-lookup"><span data-stu-id="49bce-144">UL</span></span>|`86UL`|
|<span data-ttu-id="49bce-145">single, float32</span><span class="sxs-lookup"><span data-stu-id="49bce-145">single, float32</span></span>|<span data-ttu-id="49bce-146">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="49bce-146">32-bit floating point number</span></span>|<span data-ttu-id="49bce-147">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="49bce-147">F or f</span></span>|<span data-ttu-id="49bce-148">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="49bce-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="49bce-149">lf</span><span class="sxs-lookup"><span data-stu-id="49bce-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="49bce-150">f 차례로</span><span class="sxs-lookup"><span data-stu-id="49bce-150">float; double</span></span>|<span data-ttu-id="49bce-151">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="49bce-151">64-bit floating point number</span></span>|<span data-ttu-id="49bce-152">없음</span><span class="sxs-lookup"><span data-stu-id="49bce-152">none</span></span>|<span data-ttu-id="49bce-153">`4.14`, `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="49bce-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="49bce-154">LF</span><span class="sxs-lookup"><span data-stu-id="49bce-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="49bce-155">bigint</span><span class="sxs-lookup"><span data-stu-id="49bce-155">bigint</span></span>|<span data-ttu-id="49bce-156">64 비트 표현으로 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="49bce-157">I</span><span class="sxs-lookup"><span data-stu-id="49bce-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="49bce-158">decimal</span><span class="sxs-lookup"><span data-stu-id="49bce-158">decimal</span></span>|<span data-ttu-id="49bce-159">고정 소수점 또는 유리수로 표현 되는 소수 자릿수입니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="49bce-160">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="49bce-160">M or m</span></span>|<span data-ttu-id="49bce-161">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="49bce-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="49bce-162">Char</span><span class="sxs-lookup"><span data-stu-id="49bce-162">Char</span></span>|<span data-ttu-id="49bce-163">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="49bce-163">Unicode character</span></span>|<span data-ttu-id="49bce-164">없음</span><span class="sxs-lookup"><span data-stu-id="49bce-164">none</span></span>|<span data-ttu-id="49bce-165">`'a'` 또는 `'\u0061'`</span><span class="sxs-lookup"><span data-stu-id="49bce-165">`'a'` or `'\u0061'`</span></span>|
|<span data-ttu-id="49bce-166">String</span><span class="sxs-lookup"><span data-stu-id="49bce-166">String</span></span>|<span data-ttu-id="49bce-167">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="49bce-167">Unicode string</span></span>|<span data-ttu-id="49bce-168">없음</span><span class="sxs-lookup"><span data-stu-id="49bce-168">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="49bce-169">or</span><span class="sxs-lookup"><span data-stu-id="49bce-169">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="49bce-170">or</span><span class="sxs-lookup"><span data-stu-id="49bce-170">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="49bce-171">or</span><span class="sxs-lookup"><span data-stu-id="49bce-171">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="49bce-172">[문자열](Strings.md)도 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="49bce-172">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="49bce-173">byte</span><span class="sxs-lookup"><span data-stu-id="49bce-173">byte</span></span>|<span data-ttu-id="49bce-174">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="49bce-174">ASCII character</span></span>|<span data-ttu-id="49bce-175">B</span><span class="sxs-lookup"><span data-stu-id="49bce-175">B</span></span>|`'a'B`|
|<span data-ttu-id="49bce-176">byte[]</span><span class="sxs-lookup"><span data-stu-id="49bce-176">byte[]</span></span>|<span data-ttu-id="49bce-177">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="49bce-177">ASCII string</span></span>|<span data-ttu-id="49bce-178">B</span><span class="sxs-lookup"><span data-stu-id="49bce-178">B</span></span>|`"text"B`|
|<span data-ttu-id="49bce-179">String 또는 byte []</span><span class="sxs-lookup"><span data-stu-id="49bce-179">String or byte[]</span></span>|<span data-ttu-id="49bce-180">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="49bce-180">verbatim string</span></span>|<span data-ttu-id="49bce-181">@ 접두사</span><span class="sxs-lookup"><span data-stu-id="49bce-181">@ prefix</span></span>|<span data-ttu-id="49bce-182">`@"\\server\share"` (유니코드)</span><span class="sxs-lookup"><span data-stu-id="49bce-182">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="49bce-183">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="49bce-183">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="49bce-184">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="49bce-184">Named literals</span></span>

<span data-ttu-id="49bce-185">상수로 사용할 값은 [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-185">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="49bce-186">이 특성은 값이 상수로 컴파일되는 효과를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-186">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="49bce-187">패턴 일치 식에서 소문자로 시작 하는 식별자는 항상 리터럴이 아니라 바인딩할 변수로 취급 되므로 리터럴을 정의할 때 일반적으로 초기 대문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-187">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="49bce-188">주의</span><span class="sxs-lookup"><span data-stu-id="49bce-188">Remarks</span></span>

<span data-ttu-id="49bce-189">유니코드 문자열에는 `\u`를 사용 하 여 지정할 수 있는 명시적 인코딩, 16 비트 16 진수 코드 (0000-FFFF) 또는 유니코드를 나타내는 32 비트 16 진수 코드를 `\U` 사용 하 여 지정할 수 있는 u t f-32 인코딩이 포함 될 수 있습니다. 코드 포인트 (00000000-0010FFFF).</span><span class="sxs-lookup"><span data-stu-id="49bce-189">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code (0000 - FFFF), or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents any Unicode code point (00000000 - 0010FFFF).</span></span>

<span data-ttu-id="49bce-190">`|||` 이외의 다른 비트 연산자를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-190">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="49bce-191">다른 기본의 정수</span><span class="sxs-lookup"><span data-stu-id="49bce-191">Integers in other bases</span></span>

<span data-ttu-id="49bce-192">부호 있는 32 비트 정수는 `0x`, `0o` 또는 `0b` 접두사를 사용 하 여 16 진수, 8 진수 또는 이진으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-192">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="49bce-193">숫자 리터럴의 밑줄</span><span class="sxs-lookup"><span data-stu-id="49bce-193">Underscores in numeric literals</span></span>

<span data-ttu-id="49bce-194">밑줄 문자 (`_`)를 사용 하 여 숫자를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49bce-194">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="49bce-195">참조</span><span class="sxs-lookup"><span data-stu-id="49bce-195">See also</span></span>

- [<span data-ttu-id="49bce-196">LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="49bce-196">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
