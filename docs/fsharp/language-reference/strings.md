---
title: 문자열
description: 설명 하는 방법을 F# 'string' 형식은 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타냅니다.
ms.date: 07/05/2019
ms.openlocfilehash: ec895723cc6d21a701a27b5d70d053bb681ce2b3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660606"
---
# <a name="strings"></a><span data-ttu-id="08c4f-103">문자열</span><span class="sxs-lookup"><span data-stu-id="08c4f-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="08c4f-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="08c4f-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="08c4f-106">`string` 형식은 유니코드 문자 시퀀스로 변경할 수 없는 텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="08c4f-107">`string`은 .NET Framework에서 `System.String`의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="08c4f-108">설명</span><span class="sxs-lookup"><span data-stu-id="08c4f-108">Remarks</span></span>

<span data-ttu-id="08c4f-109">문자열 리터럴은 따옴표 (") 문자로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="08c4f-110">백슬래시 문자 ( \\ ) 특정 특수 문자를 인코딩하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="08c4f-111">백슬래시와 함께 다음 문자는 라고는 *이스케이프 시퀀스*합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="08c4f-112">이스케이프 시퀀스에서 지원 되는 F# 문자열 리터럴은 다음 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="08c4f-113">문자</span><span class="sxs-lookup"><span data-stu-id="08c4f-113">Character</span></span>|<span data-ttu-id="08c4f-114">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="08c4f-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="08c4f-115">경고</span><span class="sxs-lookup"><span data-stu-id="08c4f-115">Alert</span></span>|`\a`|
|<span data-ttu-id="08c4f-116">백스페이스</span><span class="sxs-lookup"><span data-stu-id="08c4f-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="08c4f-117">폼 피드</span><span class="sxs-lookup"><span data-stu-id="08c4f-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="08c4f-118">줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="08c4f-118">Newline</span></span>|`\n`|
|<span data-ttu-id="08c4f-119">캐리지 리턴</span><span class="sxs-lookup"><span data-stu-id="08c4f-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="08c4f-120">탭</span><span class="sxs-lookup"><span data-stu-id="08c4f-120">Tab</span></span>|`\t`|
|<span data-ttu-id="08c4f-121">세로 탭</span><span class="sxs-lookup"><span data-stu-id="08c4f-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="08c4f-122">백슬래시</span><span class="sxs-lookup"><span data-stu-id="08c4f-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="08c4f-123">따옴표</span><span class="sxs-lookup"><span data-stu-id="08c4f-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="08c4f-124">아포스트로피</span><span class="sxs-lookup"><span data-stu-id="08c4f-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="08c4f-125">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="08c4f-125">Unicode character</span></span>|<span data-ttu-id="08c4f-126">`\DDD` (여기서 `D` 10 진수를 나타냅니다 자리; 000-범위의 255; 예를 들어 `\231` "ç" =)</span><span class="sxs-lookup"><span data-stu-id="08c4f-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="08c4f-127">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="08c4f-127">Unicode character</span></span>|<span data-ttu-id="08c4f-128">`\xHH` (여기서 `H` 16 진수; 00-FF;의 범위를 나타내는 예를 들어 `\xE7` "ç" =)</span><span class="sxs-lookup"><span data-stu-id="08c4f-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="08c4f-129">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="08c4f-129">Unicode character</span></span>|<span data-ttu-id="08c4f-130">`\uHHHH` (U T F-16) (여기서 `H` 16 진수; 0000-FFFF;의 범위를 나타냅니다  예를 들어 `\u00E7` "ç" =)</span><span class="sxs-lookup"><span data-stu-id="08c4f-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="08c4f-131">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="08c4f-131">Unicode character</span></span>|<span data-ttu-id="08c4f-132">`\U00HHHHHH` (UTF-32) (여기서 `H` 16 진수; 000000-10ffff 까지의;의 범위를 나타냅니다  예를 들어 `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="08c4f-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="08c4f-133">`\DDD` 이스케이프 시퀀스는 소수 표기법, 대부분의 다른 언어에서 같은 하지 8 진수 표기법입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="08c4f-134">따라서 자리 `8` 및 `9` 은 유효 및 시퀀스 `\032` 공백을 나타냅니다 (u+0020), 8 진수 표기법으로 동일한 코드 포인트를 수 있지만 `\040`합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="08c4f-135">범위는 0으로 제한 되-255 (0xff 인 경우)를 `\DDD` 및 `\x` 이스케이프 시퀀스는 효과적으로 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 하므로 처음 256 개의 유니코드 코드 포인트를 일치 하는 문자 집합을 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

<span data-ttu-id="08c4f-136">앞의 리터럴은 축 자 문자열 @ 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-136">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="08c4f-137">즉, 모든 이스케이프 시퀀스가 무시 되는 제외 하 고 두 개의 따옴표 문자 하나 따옴표 문자로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-137">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

<span data-ttu-id="08c4f-138">또한 문자열 삼중 따옴표로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-138">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="08c4f-139">이 예제의 경우 이스케이프 시퀀스가 모두 무시 됩니다 큰따옴표 문자를 포함 하 여.</span><span class="sxs-lookup"><span data-stu-id="08c4f-139">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="08c4f-140">포함 된 따옴표 문자열이 포함 된 문자열을 지정 하려면 축 자 문자열 또는 삼중 따옴표가 붙은 문자열을 하거나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-140">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="08c4f-141">축 자 문자열을 사용 하면 단일 큰따옴표 문자를 나타내기 위해 두 개의 따옴표 문자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-141">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="08c4f-142">삼중 따옴표가 붙은 문자열을 사용 하는 경우 문자열의 끝으로 구문 분석 중인 없으면 작은따옴표 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-142">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="08c4f-143">이 기술은 XML 또는 포함 된 따옴표를 포함 하는 다른 구조를 사용 하 여 작업할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-143">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="08c4f-144">코드에서 줄 바꿈이 있는 문자열이 허용 되는 줄 바꿈이 그대로 해석 됩니다 줄 바꿈, 백슬래시 문자 줄 바꿈 앞 마지막 문자가 아닌을</span><span class="sxs-lookup"><span data-stu-id="08c4f-144">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="08c4f-145">백슬래시 문자를 사용할 때 다음 줄에서 선행 공백 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-145">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="08c4f-146">다음 코드는 문자열을 생성 `str1` 에 값을 갖는 `"abc\ndef"` 문자열과 `str2` 에 값을 갖는 `"abcdef"`합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-146">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

<span data-ttu-id="08c4f-147">다음과 같이 배열 유사 구문을 사용 하 여 문자열의 개별 문자를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-147">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="08c4f-148">출력은 `b`입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-148">The output is `b`.</span></span>

<span data-ttu-id="08c4f-149">또는 다음 코드 에서처럼 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-149">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="08c4f-150">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-150">The output is as follows.</span></span>

```
abc
def
```

<span data-ttu-id="08c4f-151">형식이 부호 없는 바이트 배열에서 ASCII 문자열을 나타낼 수 있습니다 `byte[]`합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-151">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="08c4f-152">접미사를 추가한 `B` 문자열 리터럴로 ASCII 문자열 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-152">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="08c4f-153">바이트 배열을 사용 하는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외 하 고 유니코드 문자열로 동일한 이스케이프 시퀀스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-153">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="08c4f-154">문자열 연산자</span><span class="sxs-lookup"><span data-stu-id="08c4f-154">String Operators</span></span>

<span data-ttu-id="08c4f-155">문자열을 연결 하는 방법은 두 가지:를 사용 하 여 합니다 `+` 연산자 또는 사용 하 여는 `^` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-155">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="08c4f-156">`+` 연산자 기능을 처리 하는.NET Framework 문자열과 호환성이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-156">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="08c4f-157">다음 예제에서는 문자열 연결을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-157">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="08c4f-158">String 클래스</span><span class="sxs-lookup"><span data-stu-id="08c4f-158">String Class</span></span>

<span data-ttu-id="08c4f-159">문자열 형식에서 F# 는 실제로.NET 프레임 워크 `System.String` all을 입력 합니다 `System.String` 멤버를 사용할 수.</span><span class="sxs-lookup"><span data-stu-id="08c4f-159">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="08c4f-160">여기에 `+` 연산자에 사용 되는 문자열을 연결 하는 `Length` 속성 및 `Chars` 유니코드 문자의 배열 문자열을 반환 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-160">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="08c4f-161">문자열에 대 한 자세한 내용은 참조 하세요. `System.String`합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-161">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="08c4f-162">사용 하 여 합니다 `Chars` 속성의 `System.String`, 다음 코드에 표시 된 대로 인덱스를 지정 하 여 문자열의 개별 문자를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-162">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="08c4f-163">문자열 모듈</span><span class="sxs-lookup"><span data-stu-id="08c4f-163">String Module</span></span>

<span data-ttu-id="08c4f-164">문자열 처리에 대 한 추가 기능이 포함 된 `String` 모듈에는 `FSharp.Core` 네임 스페이스.</span><span class="sxs-lookup"><span data-stu-id="08c4f-164">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="08c4f-165">자세한 내용은 [Core.String 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="08c4f-165">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="08c4f-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="08c4f-166">See also</span></span>

- [<span data-ttu-id="08c4f-167">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="08c4f-167">F# Language Reference</span></span>](index.md)
