---
title: 문자열
description: F# '문자열' 형식이 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타내는 방법을 알아봅니다.
ms.date: 07/05/2019
ms.openlocfilehash: 242a2cefa1cce8995090dddd1d1fd7181e0f5e0c
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739562"
---
# <a name="strings"></a><span data-ttu-id="ba3dd-103">문자열</span><span class="sxs-lookup"><span data-stu-id="ba3dd-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="ba3dd-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="ba3dd-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="ba3dd-106">형식은 `string` 유니코드 문자시퀀스로 변경할 수 없는 텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="ba3dd-107">`string`은 .NET Framework에서 `System.String`의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba3dd-108">설명</span><span class="sxs-lookup"><span data-stu-id="ba3dd-108">Remarks</span></span>

<span data-ttu-id="ba3dd-109">문자열 리터럴은 따옴표(") 문자로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="ba3dd-110">백슬래시 문자 \\ ()는 특정 특수 문자를 인코딩하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="ba3dd-111">백슬래시와 다음 문자를 함께 *이스케이프 시퀀스라고*합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="ba3dd-112">F# 문자열 리터럴에서 지원되는 이스케이프 시퀀스는 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="ba3dd-113">문자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-113">Character</span></span>|<span data-ttu-id="ba3dd-114">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="ba3dd-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="ba3dd-115">경고</span><span class="sxs-lookup"><span data-stu-id="ba3dd-115">Alert</span></span>|`\a`|
|<span data-ttu-id="ba3dd-116">백스페이스</span><span class="sxs-lookup"><span data-stu-id="ba3dd-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="ba3dd-117">용지 공급</span><span class="sxs-lookup"><span data-stu-id="ba3dd-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="ba3dd-118">줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="ba3dd-118">Newline</span></span>|`\n`|
|<span data-ttu-id="ba3dd-119">캐리지 리턴</span><span class="sxs-lookup"><span data-stu-id="ba3dd-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="ba3dd-120">탭</span><span class="sxs-lookup"><span data-stu-id="ba3dd-120">Tab</span></span>|`\t`|
|<span data-ttu-id="ba3dd-121">세로 탭</span><span class="sxs-lookup"><span data-stu-id="ba3dd-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="ba3dd-122">백슬래시</span><span class="sxs-lookup"><span data-stu-id="ba3dd-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="ba3dd-123">물음표</span><span class="sxs-lookup"><span data-stu-id="ba3dd-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="ba3dd-124">아포스트로피</span><span class="sxs-lookup"><span data-stu-id="ba3dd-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="ba3dd-125">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-125">Unicode character</span></span>|<span data-ttu-id="ba3dd-126">`\DDD`(여기서 `D` 소수 자릿수, 범위는 000 - 255; 예를 `\231` 들어 = "ç")</span><span class="sxs-lookup"><span data-stu-id="ba3dd-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="ba3dd-127">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-127">Unicode character</span></span>|<span data-ttu-id="ba3dd-128">`\xHH`(여기서 `H` 헥사데피상 자릿수; 00 - FF; 예를 `\xE7` 들어 = "ç")</span><span class="sxs-lookup"><span data-stu-id="ba3dd-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="ba3dd-129">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-129">Unicode character</span></span>|<span data-ttu-id="ba3dd-130">`\uHHHH`(UTF-16) (여기서 `H` 헥사데피숫자; 0000의 범위 - FFFF;  예를 들어 `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="ba3dd-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="ba3dd-131">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-131">Unicode character</span></span>|<span data-ttu-id="ba3dd-132">`\U00HHHHHH`(UTF-32) (여기서 `H` 헥사데피수 자릿수; 000000- 10FFFFFF의 범위;  예를 들어 `\U0001F47D` =👽" ")</span><span class="sxs-lookup"><span data-stu-id="ba3dd-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="ba3dd-133">이스케이프 시퀀스는 `\DDD` 대부분의 다른 언어와 마찬가지로 십자수 표기형이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="ba3dd-134">따라서 `8` 숫자와 `9` 유효하며 공백(U+0020)을 `\032` 나타내는 시퀀스가 있는 반면, 팔각형 표기법의 동일한 코드 포인트는 . `\040`</span><span class="sxs-lookup"><span data-stu-id="ba3dd-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="ba3dd-135">0 - 255(0xFF) 범위로 제한되는 `\DDD` `\x` 이스케이프 시퀀스는 처음 256개의 유니코드 코드 포인트와 일치하기 때문에 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 문자 집합이 효과적으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="ba3dd-136">축어 문자열</span><span class="sxs-lookup"><span data-stu-id="ba3dd-136">Verbatim Strings</span></span>

<span data-ttu-id="ba3dd-137">@ 기호 앞에 오는 경우 리터럴은 축어 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="ba3dd-138">즉, 두 개의 따옴표 문자가 하나의 따옴표 문자로 해석된다는 점을 제외하면 이스케이프 시퀀스는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="ba3dd-139">트리플 인용 문자열</span><span class="sxs-lookup"><span data-stu-id="ba3dd-139">Triple Quoted Strings</span></span>

<span data-ttu-id="ba3dd-140">또한 문자열은 삼중 따옴표로 묶일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="ba3dd-141">이 경우 이중 따옴표 문자를 포함하여 모든 이스케이프 시퀀스는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="ba3dd-142">포함된 quoted 문자열이 포함된 문자열을 지정하려면 축어 문자열 또는 삼중 인용 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="ba3dd-143">축어 문자열을 사용하는 경우 두 개의 따옴표 문자를 지정하여 단일 따옴표 문자를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="ba3dd-144">삼중 따옴표 문자열을 사용하는 경우 문자열의 끝으로 구문 분석되지 않고 단일 따옴표 기호 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="ba3dd-145">이 기술은 XML 또는 포함된 따옴표를 포함하는 다른 구조로 작업할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="ba3dd-146">코드에서 줄 바꿈이 있는 문자열은 허용되고 줄 바꿈은 백슬래시 문자가 줄 바꿈 전마지막 문자가 아니면 말 그대로 줄 바꿈으로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="ba3dd-147">백슬래시 문자를 사용할 때 다음 줄의 선도 공백은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="ba3dd-148">다음 코드는 값이 `str1` 있는 문자열과 `"abc\ndef"` 값이 `str2` `"abcdef"`있는 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="ba3dd-149">문자열 인덱싱 및 슬라이싱</span><span class="sxs-lookup"><span data-stu-id="ba3dd-149">String Indexing and Slicing</span></span>

<span data-ttu-id="ba3dd-150">배열과 같은 구문을 사용하여 문자열의 개별 문자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="ba3dd-151">출력은 `b`입니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-151">The output is `b`.</span></span>

<span data-ttu-id="ba3dd-152">또는 다음 코드와 같이 배열 조각 구문을 사용하여 하위 문자열을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="ba3dd-153">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="ba3dd-154">부호없는 바이트의 배열로 ASCII 문자열을 나타낼 `byte[]`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="ba3dd-155">문자열 리터럴에 `B` 접미사를 추가하여 ASCII 문자열임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="ba3dd-156">바이트 배열에 사용되는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외하고 유니코드 문자열과 동일한 이스케이프 시퀀스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="ba3dd-157">문자열 연산자</span><span class="sxs-lookup"><span data-stu-id="ba3dd-157">String Operators</span></span>

<span data-ttu-id="ba3dd-158">연산자는 `+` .NET Framework 문자열 처리 기능과의 호환성을 유지하면서 문자열을 통합하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-158">The `+` operator can be used to concatenate strings, maintaining compatibility with the .NET Framework string handling features.</span></span> <span data-ttu-id="ba3dd-159">다음 예제에서는 문자열 연결에 대해 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-159">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="ba3dd-160">문자열 클래스</span><span class="sxs-lookup"><span data-stu-id="ba3dd-160">String Class</span></span>

<span data-ttu-id="ba3dd-161">F#의 문자열 형식은 실제로 .NET `System.String` Framework 형식이므로 모든 멤버를 `System.String` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-161">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="ba3dd-162">여기에는 `+` 문자열, `Length` 속성 및 문자열을 유니코드 문자의 배열로 반환하는 `Chars` 속성을 통합하는 데 사용되는 연산자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-162">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="ba3dd-163">문자열에 대한 자세한 내용은 `System.String`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-163">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="ba3dd-164">`System.String`의 `Chars` 속성을 사용하여 다음 코드와 같이 인덱스를 지정하여 문자열의 개별 문자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-164">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="ba3dd-165">문자열 모듈</span><span class="sxs-lookup"><span data-stu-id="ba3dd-165">String Module</span></span>

<span data-ttu-id="ba3dd-166">문자열 처리를 위한 추가 기능은 `String` `FSharp.Core` 네임스페이스의 모듈에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-166">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="ba3dd-167">자세한 내용은 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ba3dd-167">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="ba3dd-168">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba3dd-168">See also</span></span>

- [<span data-ttu-id="ba3dd-169">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ba3dd-169">F# Language Reference</span></span>](index.md)
