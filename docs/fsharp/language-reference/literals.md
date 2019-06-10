---
title: 리터럴
description: 리터럴 형식에 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 06/08/2019
ms.openlocfilehash: 93329cd868ff7a2daaffa1b87ba838bbbc98015c
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816237"
---
# <a name="literals"></a><span data-ttu-id="0e67e-103">리터럴</span><span class="sxs-lookup"><span data-stu-id="0e67e-103">Literals</span></span>

> [!NOTE]
> <span data-ttu-id="0e67e-104">이 문서의 API 참조 링크 하면 MSDN (당분간).</span><span class="sxs-lookup"><span data-stu-id="0e67e-104">The API reference links in this article will take you to MSDN (for now).</span></span>

<span data-ttu-id="0e67e-105">이 항목에서는 테이블의 리터럴 형식을 지정 하는 방법을 보여 주는 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-105">This topic provides a table that shows how to specify the type of a literal in F#.</span></span>

## <a name="literal-types"></a><span data-ttu-id="0e67e-106">리터럴 형식</span><span class="sxs-lookup"><span data-stu-id="0e67e-106">Literal Types</span></span>

<span data-ttu-id="0e67e-107">다음 표에서 리터럴 형식에서 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-107">The following table shows the literal types in F#.</span></span> <span data-ttu-id="0e67e-108">16 진수 표기법으로 숫자를 나타내는 문자; 대/소문자 구분 하지 않습니다. 문자 형식을 식별 하는 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-108">Characters that represent digits in hexadecimal notation are not case-sensitive; characters that identify the type are case-sensitive.</span></span>

|<span data-ttu-id="0e67e-109">형식</span><span class="sxs-lookup"><span data-stu-id="0e67e-109">Type</span></span>|<span data-ttu-id="0e67e-110">설명</span><span class="sxs-lookup"><span data-stu-id="0e67e-110">Description</span></span>|<span data-ttu-id="0e67e-111">접미사 또는 접두사</span><span class="sxs-lookup"><span data-stu-id="0e67e-111">Suffix or prefix</span></span>|<span data-ttu-id="0e67e-112">예제</span><span class="sxs-lookup"><span data-stu-id="0e67e-112">Examples</span></span>|
|----|-----------|----------------|--------|
|<span data-ttu-id="0e67e-113">sbyte</span><span class="sxs-lookup"><span data-stu-id="0e67e-113">sbyte</span></span>|<span data-ttu-id="0e67e-114">부호 있는 8 비트 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-114">signed 8-bit integer</span></span>|<span data-ttu-id="0e67e-115">y</span><span class="sxs-lookup"><span data-stu-id="0e67e-115">y</span></span>|`86y`<br /><br />`0b00000101y`|
|<span data-ttu-id="0e67e-116">byte</span><span class="sxs-lookup"><span data-stu-id="0e67e-116">byte</span></span>|<span data-ttu-id="0e67e-117">부호 없는 8 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="0e67e-117">unsigned 8-bit natural number</span></span>|<span data-ttu-id="0e67e-118">uy</span><span class="sxs-lookup"><span data-stu-id="0e67e-118">uy</span></span>|`86uy`<br /><br />`0b00000101uy`|
|<span data-ttu-id="0e67e-119">int16</span><span class="sxs-lookup"><span data-stu-id="0e67e-119">int16</span></span>|<span data-ttu-id="0e67e-120">부호 있는 16 비트 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-120">signed 16-bit integer</span></span>|<span data-ttu-id="0e67e-121">초</span><span class="sxs-lookup"><span data-stu-id="0e67e-121">s</span></span>|`86s`|
|<span data-ttu-id="0e67e-122">uint16</span><span class="sxs-lookup"><span data-stu-id="0e67e-122">uint16</span></span>|<span data-ttu-id="0e67e-123">부호 없는 16 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="0e67e-123">unsigned 16-bit natural number</span></span>|<span data-ttu-id="0e67e-124">us</span><span class="sxs-lookup"><span data-stu-id="0e67e-124">us</span></span>|`86us`|
|<span data-ttu-id="0e67e-125">int</span><span class="sxs-lookup"><span data-stu-id="0e67e-125">int</span></span><br /><br /><span data-ttu-id="0e67e-126">int32</span><span class="sxs-lookup"><span data-stu-id="0e67e-126">int32</span></span>|<span data-ttu-id="0e67e-127">부호 있는 32 비트 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-127">signed 32-bit integer</span></span>|<span data-ttu-id="0e67e-128">l 또는 없음</span><span class="sxs-lookup"><span data-stu-id="0e67e-128">l or none</span></span>|`86`<br /><br />`86l`|
|<span data-ttu-id="0e67e-129">uint</span><span class="sxs-lookup"><span data-stu-id="0e67e-129">uint</span></span><br /><br /><span data-ttu-id="0e67e-130">uint32</span><span class="sxs-lookup"><span data-stu-id="0e67e-130">uint32</span></span>|<span data-ttu-id="0e67e-131">부호 없는 32 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="0e67e-131">unsigned 32-bit natural number</span></span>|<span data-ttu-id="0e67e-132">u 또는 ul</span><span class="sxs-lookup"><span data-stu-id="0e67e-132">u or ul</span></span>|`86u`<br /><br />`86ul`|
|<span data-ttu-id="0e67e-133">nativeint</span><span class="sxs-lookup"><span data-stu-id="0e67e-133">nativeint</span></span>|<span data-ttu-id="0e67e-134">서명 된 자연 수에 대 한 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="0e67e-134">native pointer to a signed natural number</span></span>|<span data-ttu-id="0e67e-135">n</span><span class="sxs-lookup"><span data-stu-id="0e67e-135">n</span></span>|`123n`|
|<span data-ttu-id="0e67e-136">unativeint</span><span class="sxs-lookup"><span data-stu-id="0e67e-136">unativeint</span></span>|<span data-ttu-id="0e67e-137">부호 없는 자연 수는 네이티브 포인터</span><span class="sxs-lookup"><span data-stu-id="0e67e-137">native pointer as an unsigned natural number</span></span>|<span data-ttu-id="0e67e-138">취소</span><span class="sxs-lookup"><span data-stu-id="0e67e-138">un</span></span>|`0x00002D3Fun`|
|<span data-ttu-id="0e67e-139">int64</span><span class="sxs-lookup"><span data-stu-id="0e67e-139">int64</span></span>|<span data-ttu-id="0e67e-140">부호 있는 64 비트 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-140">signed 64-bit integer</span></span>|<span data-ttu-id="0e67e-141">L</span><span class="sxs-lookup"><span data-stu-id="0e67e-141">L</span></span>|`86L`|
|<span data-ttu-id="0e67e-142">uint64</span><span class="sxs-lookup"><span data-stu-id="0e67e-142">uint64</span></span>|<span data-ttu-id="0e67e-143">부호 없는 64 비트 자연 수</span><span class="sxs-lookup"><span data-stu-id="0e67e-143">unsigned 64-bit natural number</span></span>|<span data-ttu-id="0e67e-144">UL</span><span class="sxs-lookup"><span data-stu-id="0e67e-144">UL</span></span>|`86UL`|
|<span data-ttu-id="0e67e-145">단일 float32</span><span class="sxs-lookup"><span data-stu-id="0e67e-145">single, float32</span></span>|<span data-ttu-id="0e67e-146">32 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="0e67e-146">32-bit floating point number</span></span>|<span data-ttu-id="0e67e-147">F 또는 f</span><span class="sxs-lookup"><span data-stu-id="0e67e-147">F or f</span></span>|<span data-ttu-id="0e67e-148">`4.14F` 또는 `4.14f`</span><span class="sxs-lookup"><span data-stu-id="0e67e-148">`4.14F` or `4.14f`</span></span>|
|||<span data-ttu-id="0e67e-149">lf</span><span class="sxs-lookup"><span data-stu-id="0e67e-149">lf</span></span>|`0x00000000lf`|
|<span data-ttu-id="0e67e-150">float; double</span><span class="sxs-lookup"><span data-stu-id="0e67e-150">float; double</span></span>|<span data-ttu-id="0e67e-151">64 비트 부동 소수점 숫자</span><span class="sxs-lookup"><span data-stu-id="0e67e-151">64-bit floating point number</span></span>|<span data-ttu-id="0e67e-152">없음</span><span class="sxs-lookup"><span data-stu-id="0e67e-152">none</span></span>|<span data-ttu-id="0e67e-153">`4.14` 또는 `2.3E+32` 또는 `2.3e+32`</span><span class="sxs-lookup"><span data-stu-id="0e67e-153">`4.14` or `2.3E+32` or `2.3e+32`</span></span>|
|||<span data-ttu-id="0e67e-154">LF</span><span class="sxs-lookup"><span data-stu-id="0e67e-154">LF</span></span>|`0x0000000000000000LF`|
|<span data-ttu-id="0e67e-155">bigint</span><span class="sxs-lookup"><span data-stu-id="0e67e-155">bigint</span></span>|<span data-ttu-id="0e67e-156">64 비트 표현으로 제한 되지 않는 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-156">integer not limited to 64-bit representation</span></span>|<span data-ttu-id="0e67e-157">I</span><span class="sxs-lookup"><span data-stu-id="0e67e-157">I</span></span>|`9999999999999999999999999999I`|
|<span data-ttu-id="0e67e-158">decimal</span><span class="sxs-lookup"><span data-stu-id="0e67e-158">decimal</span></span>|<span data-ttu-id="0e67e-159">고정된 소수점 또는 유리수로 표현 되는 소수</span><span class="sxs-lookup"><span data-stu-id="0e67e-159">fractional number represented as a fixed point or rational number</span></span>|<span data-ttu-id="0e67e-160">M 또는 m</span><span class="sxs-lookup"><span data-stu-id="0e67e-160">M or m</span></span>|<span data-ttu-id="0e67e-161">`0.7833M` 또는 `0.7833m`</span><span class="sxs-lookup"><span data-stu-id="0e67e-161">`0.7833M` or `0.7833m`</span></span>|
|<span data-ttu-id="0e67e-162">Char</span><span class="sxs-lookup"><span data-stu-id="0e67e-162">Char</span></span>|<span data-ttu-id="0e67e-163">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="0e67e-163">Unicode character</span></span>|<span data-ttu-id="0e67e-164">없음</span><span class="sxs-lookup"><span data-stu-id="0e67e-164">none</span></span>|`'a'`|
|<span data-ttu-id="0e67e-165">문자열</span><span class="sxs-lookup"><span data-stu-id="0e67e-165">String</span></span>|<span data-ttu-id="0e67e-166">유니코드 문자열</span><span class="sxs-lookup"><span data-stu-id="0e67e-166">Unicode string</span></span>|<span data-ttu-id="0e67e-167">없음</span><span class="sxs-lookup"><span data-stu-id="0e67e-167">none</span></span>|`"text\n"`<br /><br /><span data-ttu-id="0e67e-168">또는</span><span class="sxs-lookup"><span data-stu-id="0e67e-168">or</span></span><br /><br />`@"c:\filename"`<br /><br /><span data-ttu-id="0e67e-169">또는</span><span class="sxs-lookup"><span data-stu-id="0e67e-169">or</span></span><br /><br />`"""<book title="Paradise Lost">"""`<br /><br /><span data-ttu-id="0e67e-170">또는</span><span class="sxs-lookup"><span data-stu-id="0e67e-170">or</span></span><br /><br />`"string1" + "string2"`<br /><br /><span data-ttu-id="0e67e-171">참고 항목 [문자열](Strings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-171">See also [Strings](Strings.md).</span></span>|
|<span data-ttu-id="0e67e-172">byte</span><span class="sxs-lookup"><span data-stu-id="0e67e-172">byte</span></span>|<span data-ttu-id="0e67e-173">ASCII 문자</span><span class="sxs-lookup"><span data-stu-id="0e67e-173">ASCII character</span></span>|<span data-ttu-id="0e67e-174">B</span><span class="sxs-lookup"><span data-stu-id="0e67e-174">B</span></span>|`'a'B`|
|<span data-ttu-id="0e67e-175">byte[]</span><span class="sxs-lookup"><span data-stu-id="0e67e-175">byte[]</span></span>|<span data-ttu-id="0e67e-176">ASCII 문자열</span><span class="sxs-lookup"><span data-stu-id="0e67e-176">ASCII string</span></span>|<span data-ttu-id="0e67e-177">B</span><span class="sxs-lookup"><span data-stu-id="0e67e-177">B</span></span>|`"text"B`|
|<span data-ttu-id="0e67e-178">String 또는 byte]</span><span class="sxs-lookup"><span data-stu-id="0e67e-178">String or byte[]</span></span>|<span data-ttu-id="0e67e-179">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="0e67e-179">verbatim string</span></span>|<span data-ttu-id="0e67e-180">@ prefix</span><span class="sxs-lookup"><span data-stu-id="0e67e-180">@ prefix</span></span>|<span data-ttu-id="0e67e-181">`@"\\server\share"` (유니코드)</span><span class="sxs-lookup"><span data-stu-id="0e67e-181">`@"\\server\share"` (Unicode)</span></span><br /><br /><span data-ttu-id="0e67e-182">`@"\\server\share"B` (ASCII)</span><span class="sxs-lookup"><span data-stu-id="0e67e-182">`@"\\server\share"B` (ASCII)</span></span>|

## <a name="named-literals"></a><span data-ttu-id="0e67e-183">명명 된 리터럴</span><span class="sxs-lookup"><span data-stu-id="0e67e-183">Named literals</span></span>

<span data-ttu-id="0e67e-184">값은 상수를 사용 하 여 표시할 수 있습니다 합니다 [리터럴](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-184">Values that are intended to be constants can be marked with the [Literal](https://msdn.microsoft.com/library/465f36ce-d146-41c0-b425-679c509cd285) attribute.</span></span> <span data-ttu-id="0e67e-185">이 특성에 적용 하면 값을 상수로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-185">This attribute has the effect of causing a value to be compiled as a constant.</span></span>

<span data-ttu-id="0e67e-186">패턴 일치 식에서에서 소문자로 시작 하는 식별자는 항상 바인딩을 위한 변수로 처리 됩니다 것이 아니라 리터럴로 하므로 일반적으로 사용 해야 문자가 대문자 리터럴을 정의할 때.</span><span class="sxs-lookup"><span data-stu-id="0e67e-186">In pattern matching expressions, identifiers that begin with lowercase characters are always treated as variables to be bound, rather than as literals, so you should generally use initial capitals when you define literals.</span></span>

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

## <a name="remarks"></a><span data-ttu-id="0e67e-187">설명</span><span class="sxs-lookup"><span data-stu-id="0e67e-187">Remarks</span></span>

<span data-ttu-id="0e67e-188">유니코드 문자열에는 명시적 인코딩을 사용 하 여 지정할 수 있는 포함 될 수 있습니다 `\u` 뒤에 16 비트 16 진수 코드 또는 UTF-32 인코딩을 사용 하 여 지정할 수 있는 `\U` 뒤에 유니코드를 나타내는 32 비트 16 진수 코드 서로게이트 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-188">Unicode strings can contain explicit encodings that you can specify by using `\u` followed by a 16-bit hexadecimal code or UTF-32 encodings that you can specify by using `\U` followed by a 32-bit hexadecimal code that represents a Unicode surrogate pair.</span></span>

<span data-ttu-id="0e67e-189">이외의 다른 비트 연산자를 사용 하 여 `|||` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-189">The use of other bitwise operators other than `|||` isn't allowed.</span></span>

## <a name="integers-in-other-bases"></a><span data-ttu-id="0e67e-190">다른 밑에 있는 정수</span><span class="sxs-lookup"><span data-stu-id="0e67e-190">Integers in other bases</span></span>

<span data-ttu-id="0e67e-191">부호 있는 32 비트 정수의 16 진수, 8 진수 또는 이진 사용 하 여 지정할 수도 있습니다는 `0x`, `0o` 또는 `0b` 각각 접두사입니다.</span><span class="sxs-lookup"><span data-stu-id="0e67e-191">Signed 32-bit integers can also be specified in hexadecimal, octal, or binary using a `0x`, `0o` or `0b` prefix respectively.</span></span>

```fsharp
let numbers = (0x9F, 0o77, 0b1010)
// Result: numbers : int * int * int = (159, 63, 10)
```

## <a name="underscores-in-numeric-literals"></a><span data-ttu-id="0e67e-192">숫자 리터럴의 밑줄</span><span class="sxs-lookup"><span data-stu-id="0e67e-192">Underscores in numeric literals</span></span>

<span data-ttu-id="0e67e-193">밑줄 문자를 사용 하 여 숫자를 구분할 수 있습니다 (`_`).</span><span class="sxs-lookup"><span data-stu-id="0e67e-193">You can separate digits with the underscore character (`_`).</span></span>

```fsharp
let value = 0xDEAD_BEEF

let valueAsBits = 0b1101_1110_1010_1101_1011_1110_1110_1111

let exampleSSN = 123_456_7890
```

## <a name="see-also"></a><span data-ttu-id="0e67e-194">참고자료</span><span class="sxs-lookup"><span data-stu-id="0e67e-194">See also</span></span>

- [<span data-ttu-id="0e67e-195">Core.LiteralAttribute 클래스</span><span class="sxs-lookup"><span data-stu-id="0e67e-195">Core.LiteralAttribute Class</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.literalattribute-class-%5bfsharp%5d)
