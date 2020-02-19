---
title: 문자열
description: "' String ' F# 형식에서 변경할 수 없는 텍스트를 유니코드 문자 시퀀스로 나타내는 방법에 대해 알아봅니다."
ms.date: 07/05/2019
ms.openlocfilehash: 002de464d09a49b6161608db6e46c619369f5ceb
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452820"
---
# <a name="strings"></a><span data-ttu-id="f0ad8-103">문자열</span><span class="sxs-lookup"><span data-stu-id="f0ad8-103">Strings</span></span>

> [!NOTE]
> <span data-ttu-id="f0ad8-104">이 문서의 API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-104">The API reference links in this article will take you to MSDN.</span></span>  <span data-ttu-id="f0ad8-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="f0ad8-106">`string` 형식은 변경할 수 없는 텍스트를 유니코드 문자 시퀀스로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-106">The `string` type represents immutable text as a sequence of Unicode characters.</span></span> <span data-ttu-id="f0ad8-107">`string`은 .NET Framework에서 `System.String`의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-107">`string` is an alias for `System.String` in the .NET Framework.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0ad8-108">설명</span><span class="sxs-lookup"><span data-stu-id="f0ad8-108">Remarks</span></span>

<span data-ttu-id="f0ad8-109">문자열 리터럴은 따옴표 (") 문자로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-109">String literals are delimited by the quotation mark (") character.</span></span> <span data-ttu-id="f0ad8-110">백슬래시 문자 (\\)는 특정 특수 문자를 인코딩하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-110">The backslash character ( \\ ) is used to encode certain special characters.</span></span> <span data-ttu-id="f0ad8-111">백슬래시와 다음 문자를 함께 *이스케이프 시퀀스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-111">The backslash and the next character together are known as an *escape sequence*.</span></span> <span data-ttu-id="f0ad8-112">다음 표에서는 F# 문자열 리터럴에서 지원 되는 이스케이프 시퀀스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-112">Escape sequences supported in F# string literals are shown in the following table.</span></span>

|<span data-ttu-id="f0ad8-113">문자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-113">Character</span></span>|<span data-ttu-id="f0ad8-114">이스케이프 시퀀스</span><span class="sxs-lookup"><span data-stu-id="f0ad8-114">Escape sequence</span></span>|
|---------|---------------|
|<span data-ttu-id="f0ad8-115">경고</span><span class="sxs-lookup"><span data-stu-id="f0ad8-115">Alert</span></span>|`\a`|
|<span data-ttu-id="f0ad8-116">백스페이스</span><span class="sxs-lookup"><span data-stu-id="f0ad8-116">Backspace</span></span>|`\b`|
|<span data-ttu-id="f0ad8-117">용지 공급</span><span class="sxs-lookup"><span data-stu-id="f0ad8-117">Form feed</span></span>|`\f`|
|<span data-ttu-id="f0ad8-118">줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="f0ad8-118">Newline</span></span>|`\n`|
|<span data-ttu-id="f0ad8-119">캐리지 리턴</span><span class="sxs-lookup"><span data-stu-id="f0ad8-119">Carriage return</span></span>|`\r`|
|<span data-ttu-id="f0ad8-120">탭</span><span class="sxs-lookup"><span data-stu-id="f0ad8-120">Tab</span></span>|`\t`|
|<span data-ttu-id="f0ad8-121">세로 탭</span><span class="sxs-lookup"><span data-stu-id="f0ad8-121">Vertical tab</span></span>|`\v`|
|<span data-ttu-id="f0ad8-122">백슬래시</span><span class="sxs-lookup"><span data-stu-id="f0ad8-122">Backslash</span></span>|`\\`|
|<span data-ttu-id="f0ad8-123">물음표</span><span class="sxs-lookup"><span data-stu-id="f0ad8-123">Quotation mark</span></span>|`\"`|
|<span data-ttu-id="f0ad8-124">아포스트로피가</span><span class="sxs-lookup"><span data-stu-id="f0ad8-124">Apostrophe</span></span>|`\'`|
|<span data-ttu-id="f0ad8-125">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-125">Unicode character</span></span>|<span data-ttu-id="f0ad8-126">`\DDD` (여기서 `D`는 10 진수를 나타냅니다. 범위는 000-255 (예: `\231` = "ç")입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-126">`\DDD` (where `D` indicates a decimal digit; range of 000 - 255; for example, `\231` = "ç")</span></span>|
|<span data-ttu-id="f0ad8-127">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-127">Unicode character</span></span>|<span data-ttu-id="f0ad8-128">`\xHH` (여기서 `H`는 16 진수를 나타냅니다. 00-FF의 범위 (예: `\xE7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="f0ad8-128">`\xHH` (where `H` indicates a hexadecimal digit; range of 00 - FF; for example, `\xE7` = "ç")</span></span>|
|<span data-ttu-id="f0ad8-129">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-129">Unicode character</span></span>|<span data-ttu-id="f0ad8-130">`\uHHHH` (UTF-16) (여기서 `H`는 16 진수를 나타냅니다. 0000-FFFF의 범위입니다.  예: `\u00E7` = "ç")</span><span class="sxs-lookup"><span data-stu-id="f0ad8-130">`\uHHHH` (UTF-16) (where `H` indicates a hexadecimal digit; range of 0000 - FFFF;  for example, `\u00E7` = "ç")</span></span>|
|<span data-ttu-id="f0ad8-131">유니코드 문자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-131">Unicode character</span></span>|<span data-ttu-id="f0ad8-132">`\U00HHHHHH` (UTF-32) (여기서 `H`는 16 진수를 나타냅니다. 000000-10FFFF; 범위  예: `\U0001F47D` = "👽")</span><span class="sxs-lookup"><span data-stu-id="f0ad8-132">`\U00HHHHHH` (UTF-32) (where `H` indicates a hexadecimal digit; range of 000000 - 10FFFF;  for example, `\U0001F47D` = "👽")</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="f0ad8-133">`\DDD` 이스케이프 시퀀스는 다른 언어와 같은 8 진수 표기법이 아닌 소수 표기법입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-133">The `\DDD` escape sequence is decimal notation, not octal notation like in most other languages.</span></span> <span data-ttu-id="f0ad8-134">따라서 숫자 `8` 및 `9`는 유효 하 고 `\032` 시퀀스는 공백 (U + 0020)을 나타내지만 8 진수 표기법의 동일한 코드 포인트는 `\040`됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-134">Therefore, digits `8` and `9` are valid, and a sequence of `\032` represents a space (U+0020), whereas that same code point in octal notation would be `\040`.</span></span>

> [!NOTE]
> <span data-ttu-id="f0ad8-135">범위가 0-255 (0xFF)로 제한 되는 경우 `\DDD` 및 `\x` 이스케이프 시퀀스는 효과적으로 [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) 문자 집합입니다 .이는 첫 번째 256 유니코드 코드 지점과 일치 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-135">Being constrained to a range of 0 - 255 (0xFF), the `\DDD` and `\x` escape sequences are effectively the [ISO-8859-1](https://en.wikipedia.org/wiki/ISO/IEC_8859-1#Code_page_layout) character set, since that matches the first 256 Unicode code points.</span></span>

## <a name="verbatim-strings"></a><span data-ttu-id="f0ad8-136">축 자 문자열</span><span class="sxs-lookup"><span data-stu-id="f0ad8-136">Verbatim Strings</span></span>

<span data-ttu-id="f0ad8-137">@ 기호가 앞에 오면 리터럴은 축 자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-137">If preceded by the @ symbol, the literal is a verbatim string.</span></span> <span data-ttu-id="f0ad8-138">즉, 두 개의 따옴표 문자가 하나의 인용 부호 문자로 해석 된다는 점을 제외 하 고 모든 이스케이프 시퀀스는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-138">This means that any escape sequences are ignored, except that two quotation mark characters are interpreted as one quotation mark character.</span></span>

## <a name="triple-quoted-strings"></a><span data-ttu-id="f0ad8-139">따옴표 붙은 문자열</span><span class="sxs-lookup"><span data-stu-id="f0ad8-139">Triple Quoted Strings</span></span>

<span data-ttu-id="f0ad8-140">또한 문자열을 삼중 따옴표로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-140">Additionally, a string may be enclosed by triple quotes.</span></span> <span data-ttu-id="f0ad8-141">이 경우 큰따옴표 문자를 포함 하 여 모든 이스케이프 시퀀스가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-141">In this case, all escape sequences are ignored, including double quotation mark characters.</span></span> <span data-ttu-id="f0ad8-142">포함 된 따옴표 붙은 문자열을 포함 하는 문자열을 지정 하려면 축 자 문자열 또는 세 개의 따옴표 붙은 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-142">To specify a string that contains an embedded quoted string, you can either use a verbatim string or a triple-quoted string.</span></span> <span data-ttu-id="f0ad8-143">축 자 문자열을 사용 하는 경우 작은따옴표 문자를 나타내는 두 개의 따옴표 문자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-143">If you use a verbatim string, you  must specify two quotation mark characters to indicate a single quotation mark character.</span></span> <span data-ttu-id="f0ad8-144">세 번째 따옴표 붙은 문자열을 사용 하는 경우 문자열의 끝으로 구문 분석 되지 않고 작은따옴표 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-144">If you use a triple-quoted string, you can use the single quotation mark characters without them being parsed as the end of the string.</span></span> <span data-ttu-id="f0ad8-145">이 기법은 XML 또는 포함 된 따옴표를 포함 하는 다른 구조체로 작업 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-145">This technique can be useful when you work with XML or other structures that include embedded quotation marks.</span></span>

```fsharp
// Using a verbatim string
let xmlFragment1 = @"<book author=""Milton, John"" title=""Paradise Lost"">"

// Using a triple-quoted string
let xmlFragment2 = """<book author="Milton, John" title="Paradise Lost">"""
```

<span data-ttu-id="f0ad8-146">코드에서 줄 바꿈이 있는 문자열이 허용 되 고 줄 바꿈이 줄 바꿈 앞의 마지막 문자인 경우를 제외 하 고는 줄바꿈로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-146">In code, strings that have line breaks are accepted and the line breaks are interpreted literally as newlines, unless a backslash character is the last character before the line break.</span></span> <span data-ttu-id="f0ad8-147">백슬래시 문자를 사용 하는 경우 다음 줄의 선행 공백은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-147">Leading white space on the next line is ignored when the backslash character is used.</span></span> <span data-ttu-id="f0ad8-148">다음 코드는 값이 `"abc\ndef"` 인 문자열 `str1`를 생성 하 고 값 `"abcdef"`를 포함 하는 문자열 `str2`를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-148">The following code produces a string `str1` that has value `"abc\ndef"` and a string `str2` that has value `"abcdef"`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1001.fs)]

## <a name="string-indexing-and-slicing"></a><span data-ttu-id="f0ad8-149">문자열 인덱싱 및 조각화</span><span class="sxs-lookup"><span data-stu-id="f0ad8-149">String Indexing and Slicing</span></span>

<span data-ttu-id="f0ad8-150">다음과 같이 배열 형식 구문을 사용 하 여 문자열의 개별 문자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-150">You can access individual characters in a string by using array-like syntax, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1002.fs)]

<span data-ttu-id="f0ad8-151">출력은 `b`입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-151">The output is `b`.</span></span>

<span data-ttu-id="f0ad8-152">또는 다음 코드와 같이 배열 조각 구문을 사용 하 여 부분 문자열을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-152">Or you can extract substrings by using array slice syntax, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1003.fs)]

<span data-ttu-id="f0ad8-153">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-153">The output is as follows.</span></span>

```console
abc
def
```

<span data-ttu-id="f0ad8-154">부호 없는 바이트 배열, `byte[]`형식으로 ASCII 문자열을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-154">You can represent ASCII strings by arrays of unsigned bytes, type `byte[]`.</span></span> <span data-ttu-id="f0ad8-155">문자열 리터럴에 `B` 접미사를 추가 하 여 ASCII 문자열 임을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-155">You add the suffix `B` to a string literal to indicate that it is an ASCII string.</span></span> <span data-ttu-id="f0ad8-156">바이트 배열과 함께 사용 되는 ASCII 문자열 리터럴은 유니코드 이스케이프 시퀀스를 제외 하 고 유니코드 문자열과 동일한 이스케이프 시퀀스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-156">ASCII string literals used with byte arrays support the same escape sequences as Unicode strings, except for the Unicode escape sequences.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1004.fs)]

## <a name="string-operators"></a><span data-ttu-id="f0ad8-157">문자열 연산자</span><span class="sxs-lookup"><span data-stu-id="f0ad8-157">String Operators</span></span>

<span data-ttu-id="f0ad8-158">문자열을 연결 하는 방법에는 두 가지가 있습니다. `+` 연산자를 사용 하거나 `^` 연산자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-158">There are two ways to concatenate strings: by using the `+` operator or by using the `^` operator.</span></span> <span data-ttu-id="f0ad8-159">`+` 연산자는 .NET Framework 문자열 처리 기능과의 호환성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-159">The `+` operator maintains compatibility with the .NET Framework string handling features.</span></span>

<span data-ttu-id="f0ad8-160">다음 예제에서는 문자열 연결을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-160">The following example illustrates string concatenation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1006.fs)]

## <a name="string-class"></a><span data-ttu-id="f0ad8-161">String 클래스</span><span class="sxs-lookup"><span data-stu-id="f0ad8-161">String Class</span></span>

<span data-ttu-id="f0ad8-162">의 F# 문자열 형식은 실제로 .NET Framework `System.String` 형식 이므로 모든 `System.String` 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-162">Because the string type in F# is actually a .NET Framework `System.String` type, all the `System.String` members are available.</span></span> <span data-ttu-id="f0ad8-163">여기에는 문자열을 연결 하는 데 사용 되는 `+` 연산자, `Length` 속성 및 문자열을 유니코드 문자 배열로 반환 하는 `Chars` 속성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-163">This includes the `+` operator, which is used to concatenate strings, the `Length` property, and the `Chars` property, which returns the string as an array of Unicode characters.</span></span> <span data-ttu-id="f0ad8-164">문자열에 대 한 자세한 내용은 `System.String`를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-164">For more information about strings, see `System.String`.</span></span>

<span data-ttu-id="f0ad8-165">`System.String`의 `Chars` 속성을 사용 하 여 다음 코드와 같이 인덱스를 지정 하 여 문자열의 개별 문자에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-165">By using the `Chars` property of `System.String`, you can access the individual characters in a string by specifying an index, as is shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1005.fs)]

## <a name="string-module"></a><span data-ttu-id="f0ad8-166">문자열 모듈</span><span class="sxs-lookup"><span data-stu-id="f0ad8-166">String Module</span></span>

<span data-ttu-id="f0ad8-167">문자열 처리를 위한 추가 기능은 `FSharp.Core` 네임 스페이스의 `String` 모듈에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-167">Additional functionality for string handling is included in the `String` module in the `FSharp.Core` namespace.</span></span> <span data-ttu-id="f0ad8-168">자세한 내용은 [Core. 문자열 모듈](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f0ad8-168">For more information, see [Core.String Module](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.string-module-%5bfsharp%5d).</span></span>

## <a name="see-also"></a><span data-ttu-id="f0ad8-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0ad8-169">See also</span></span>

- [<span data-ttu-id="f0ad8-170">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f0ad8-170">F# Language Reference</span></span>](index.md)
