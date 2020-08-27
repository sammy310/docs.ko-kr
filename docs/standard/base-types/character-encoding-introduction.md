---
title: .NET의 문자 인코딩 소개
description: .NET의 문자 인코딩/디코딩에 대해 알아봅니다.
ms.date: 03/09/2020
no-loc:
- Rune
- char
- string
dev_langs:
- csharp
helpviewer_keywords:
- encoding, understanding
ms.openlocfilehash: a5d838176bf4437a295ebe6c2cea8b1fe0eeeb61
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656295"
---
# <a name="character-encoding-in-net"></a><span data-ttu-id="6df2b-103">.NET의 문자 인코딩</span><span class="sxs-lookup"><span data-stu-id="6df2b-103">Character encoding in .NET</span></span>

<span data-ttu-id="6df2b-104">이 문서에서는 .NET에서 사용되는 문자 인코딩 시스템을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-104">This article provides an introduction to character encoding systems that are used by .NET.</span></span> <span data-ttu-id="6df2b-105">이 문서에서는 <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune> 및 <xref:System.Globalization.StringInfo> 형식이 유니코드, UTF-16 및 UTF-8에서 작동하는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-105">The article explains how the <xref:System.String>, <xref:System.Char>, <xref:System.Text.Rune>, and <xref:System.Globalization.StringInfo> types work with Unicode, UTF-16, and UTF-8.</span></span>

<span data-ttu-id="6df2b-106">여기서 ‘문자’라는 용어는 ‘판독기가 단일 표시 요소로 인식’한다는 일반적인 의미로 사용합니다. </span><span class="sxs-lookup"><span data-stu-id="6df2b-106">The term *character* is used here in the general sense of *what a reader perceives as a single display element*.</span></span> <span data-ttu-id="6df2b-107">일반적인 예는 문자 "a", 기호 "@" 및 이모지 "🐂"입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-107">Common examples are the letter "a", the symbol "@", and the emoji "🐂".</span></span> <span data-ttu-id="6df2b-108">[문자소 클러스터](#grapheme-clusters) 섹션에 설명된 것처럼 한 문자처럼 보이는 것이 실제로는 독립적인 여러 표시 요소로 구성된 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-108">Sometimes what looks like one character is actually composed of multiple independent display elements, as the section on [grapheme clusters](#grapheme-clusters) explains.</span></span>

## <a name="the-no-locstring-and-no-locchar-types"></a><span data-ttu-id="6df2b-109">string 및 char 형식</span><span class="sxs-lookup"><span data-stu-id="6df2b-109">The string and char types</span></span>

<span data-ttu-id="6df2b-110">[string](xref:System.String) 클래스의 인스턴스는 일부 텍스트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-110">An instance of the [string](xref:System.String) class represents some text.</span></span> <span data-ttu-id="6df2b-111">`string`은 논리적으로 16비트 값의 시퀀스이며, 각각은 [char](xref:System.Char) 구조체의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-111">A `string` is logically a sequence of 16-bit values, each of which is an instance of the [char](xref:System.Char) struct.</span></span> <span data-ttu-id="6df2b-112">[string.Length](xref:System.String.Length) 속성은 `string` 인스턴스의 `char` 인스턴스 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-112">The [string.Length](xref:System.String.Length) property returns the number of `char` instances in the `string` instance.</span></span>

<span data-ttu-id="6df2b-113">다음 샘플 함수는 `string`에 있는 모든 `char` 인스턴스의 값을 16진수 표기법으로 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-113">The following sample function prints out the values in hexadecimal notation of all the `char` instances in a `string`:</span></span>

<span data-ttu-id="6df2b-114">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-114">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/PrintStringChars.cs" id="SnippetPrintChars":::</span></span>

<span data-ttu-id="6df2b-115">이 함수에 string “Hello”를 전달하면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-115">Pass the string "Hello" to this function, and you get the following output:</span></span>

```csharp
PrintChars("Hello");
```

```output
"Hello".Length = 5
s[0] = 'H' ('\u0048')
s[1] = 'e' ('\u0065')
s[2] = 'l' ('\u006c')
s[3] = 'l' ('\u006c')
s[4] = 'o' ('\u006f')
```

<span data-ttu-id="6df2b-116">각 문자는 단일 `char` 값으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-116">Each character is represented by a single `char` value.</span></span> <span data-ttu-id="6df2b-117">이 패턴은 대부분의 세계 언어에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-117">That pattern holds true for most of the world's languages.</span></span> <span data-ttu-id="6df2b-118">예를 들어 다음은 *nǐ hǎo*로 발음되고 *Hello*를 의미하는 중국어 문자 2자의 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-118">For example, here's the output for two Chinese characters that sound like *nǐ hǎo* and mean *Hello*:</span></span>

```csharp
PrintChars("你好");
```

```output
"你好".Length = 2
s[0] = '你' ('\u4f60')
s[1] = '好' ('\u597d')
```

<span data-ttu-id="6df2b-119">그러나 일부 언어와 일부 기호 및 이모지에서는 `char` 인스턴스 2개를 사용하여 단일 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-119">However, for some languages and for some symbols and emoji, it takes two `char` instances to represent a single character.</span></span> <span data-ttu-id="6df2b-120">예를 들어 오세이지족 언어에서 *Osage*를 의미하는 단어의 문자와 `char` 인스턴스를 비교해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-120">For example, compare the characters and `char` instances in the word that means *Osage* in the Osage language:</span></span>

```csharp
PrintChars("𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟");
```

```output
"𐓏𐓘𐓻𐓘𐓻𐓟 𐒻𐓟".Length = 17
s[0] = '�' ('\ud801')
s[1] = '�' ('\udccf')
s[2] = '�' ('\ud801')
s[3] = '�' ('\udcd8')
s[4] = '�' ('\ud801')
s[5] = '�' ('\udcfb')
s[6] = '�' ('\ud801')
s[7] = '�' ('\udcd8')
s[8] = '�' ('\ud801')
s[9] = '�' ('\udcfb')
s[10] = '�' ('\ud801')
s[11] = '�' ('\udcdf')
s[12] = ' ' ('\u0020')
s[13] = '�' ('\ud801')
s[14] = '�' ('\udcbb')
s[15] = '�' ('\ud801')
s[16] = '�' ('\udcdf')
```

<span data-ttu-id="6df2b-121">위의 예제에서 공백을 제외한 각 문자는 `char` 인스턴스 2개로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-121">In the preceding example, each character except the space is represented by two `char` instances.</span></span>

<span data-ttu-id="6df2b-122">ox 이모지를 보여 주는 다음 예제에 표시된 것처럼 단일 유니코드 이모지도 두 개의 `char`로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-122">A single Unicode emoji is also represented by two `char`s, as seen in the following example showing an ox emoji:</span></span>

```
"🐂".Length = 2
s[0] = '�' ('\ud83d')
s[1] = '�' ('\udc02')
```

<span data-ttu-id="6df2b-123">예제를 통해 `char` 인스턴스 수를 나타내는 `string.Length` 값과 표시되는 문자 수가 반드시 같은 것은 아님을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-123">These examples show that the value of `string.Length`, which indicates the number of `char` instances, doesn't necessarily indicate the number of displayed characters.</span></span> <span data-ttu-id="6df2b-124">단일 `char` 인스턴스만으로 한 문자를 나타낼 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-124">A single `char` instance by itself doesn't necessarily represent a character.</span></span>

<span data-ttu-id="6df2b-125">단일 문자에 매핑되는 `char` 쌍을 ‘서로게이트 쌍’이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-125">The `char` pairs that map to a single character are called *surrogate pairs*.</span></span> <span data-ttu-id="6df2b-126">그 작동 방식을 이해하려면 유니코드 및 UTF-16 인코딩을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-126">To understand how they work, you need to understand Unicode and UTF-16 encoding.</span></span>

## <a name="unicode-code-points"></a><span data-ttu-id="6df2b-127">유니코드 코드 포인트</span><span class="sxs-lookup"><span data-stu-id="6df2b-127">Unicode code points</span></span>

<span data-ttu-id="6df2b-128">유니코드는 다양한 언어 및 스크립트를 사용하여 다양한 플랫폼에서 사용하기 위한 국제 인코딩 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-128">Unicode is an international encoding standard for use on various platforms and with various languages and scripts.</span></span>

<span data-ttu-id="6df2b-129">유니코드 표준은 110만 개 이상의 [코드 포인트](https://www.unicode.org/glossary/#code_point)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-129">The Unicode Standard defines over 1.1 million [code points](https://www.unicode.org/glossary/#code_point).</span></span> <span data-ttu-id="6df2b-130">코드 포인트는 0과 `U+10FFFF`(10진수 1,114,111) 사이의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-130">A code point is an integer value that can range from 0 to `U+10FFFF` (decimal 1,114,111).</span></span> <span data-ttu-id="6df2b-131">일부 코드 포인트는 문자, 기호 또는 이모지에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-131">Some code points are assigned to letters, symbols, or emoji.</span></span> <span data-ttu-id="6df2b-132">다른 코드 포인트는 텍스트 또는 문자가 표시되는 방식을 제어하는 작업(예: 새 줄로 이동)에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-132">Others are assigned to actions that control how text or characters are displayed, such as advance to a new line.</span></span> <span data-ttu-id="6df2b-133">많은 코드 포인트가 아직 할당되지 않은 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-133">Many code points are not yet assigned.</span></span>

<span data-ttu-id="6df2b-134">다음은 코드 포인트 할당의 몇 가지 예제와 해당 유니코드 차트의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-134">Here are some examples of code point assignments, with links to Unicode charts in which they appear:</span></span>

|<span data-ttu-id="6df2b-135">Decimal</span><span class="sxs-lookup"><span data-stu-id="6df2b-135">Decimal</span></span>|<span data-ttu-id="6df2b-136">Hex</span><span class="sxs-lookup"><span data-stu-id="6df2b-136">Hex</span></span>       |<span data-ttu-id="6df2b-137">예제</span><span class="sxs-lookup"><span data-stu-id="6df2b-137">Example</span></span>|<span data-ttu-id="6df2b-138">설명</span><span class="sxs-lookup"><span data-stu-id="6df2b-138">Description</span></span>|
|------:|----------|-------|-----------|
|<span data-ttu-id="6df2b-139">10</span><span class="sxs-lookup"><span data-stu-id="6df2b-139">10</span></span>     | `U+000A` |<span data-ttu-id="6df2b-140">N/A</span><span class="sxs-lookup"><span data-stu-id="6df2b-140">N/A</span></span>| <span data-ttu-id="6df2b-141">[줄 바꿈](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="6df2b-141">[LINE FEED](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="6df2b-142">65</span><span class="sxs-lookup"><span data-stu-id="6df2b-142">65</span></span>     | `U+0061` | <span data-ttu-id="6df2b-143">a</span><span class="sxs-lookup"><span data-stu-id="6df2b-143">a</span></span> | <span data-ttu-id="6df2b-144">[라틴 소문자 A](https://www.unicode.org/charts/PDF/U0000.pdf)</span><span class="sxs-lookup"><span data-stu-id="6df2b-144">[LATIN SMALL LETTER A](https://www.unicode.org/charts/PDF/U0000.pdf)</span></span> |
|<span data-ttu-id="6df2b-145">562</span><span class="sxs-lookup"><span data-stu-id="6df2b-145">562</span></span>    | `U+0232` | <span data-ttu-id="6df2b-146">Ȳ</span><span class="sxs-lookup"><span data-stu-id="6df2b-146">Ȳ</span></span> | <span data-ttu-id="6df2b-147">[장음 기호를 사용하는 라틴어 대문자 Y](https://www.unicode.org/charts/PDF/U0180.pdf)</span><span class="sxs-lookup"><span data-stu-id="6df2b-147">[LATIN CAPITAL LETTER Y WITH MACRON](https://www.unicode.org/charts/PDF/U0180.pdf)</span></span> |
|<span data-ttu-id="6df2b-148">68,675</span><span class="sxs-lookup"><span data-stu-id="6df2b-148">68,675</span></span> | `U+10C43`| <span data-ttu-id="6df2b-149">𐱃</span><span class="sxs-lookup"><span data-stu-id="6df2b-149">𐱃</span></span> | <span data-ttu-id="6df2b-150">[고대 튀르크 문자 ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf)</span><span class="sxs-lookup"><span data-stu-id="6df2b-150">[OLD TURKIC LETTER ORKHON AT](https://www.unicode.org/charts/PDF/U10C00.pdf)</span></span> |
|<span data-ttu-id="6df2b-151">127,801</span><span class="sxs-lookup"><span data-stu-id="6df2b-151">127,801</span></span>| `U+1F339`| <span data-ttu-id="6df2b-152">🌹</span><span class="sxs-lookup"><span data-stu-id="6df2b-152">🌹</span></span> | <span data-ttu-id="6df2b-153">[장미 이모지](https://www.unicode.org/charts/PDF/U1F300.pdf)</span><span class="sxs-lookup"><span data-stu-id="6df2b-153">[ROSE emoji](https://www.unicode.org/charts/PDF/U1F300.pdf)</span></span> |

<span data-ttu-id="6df2b-154">코드 포인트는 관례적으로 `U+xxxx` 구문을 사용하여 지칭됩니다. 여기서 `xxxx`는 16진수로 인코딩된 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-154">Code points are customarily referred to by using the syntax `U+xxxx`, where `xxxx` is the hex-encoded integer value.</span></span>

<span data-ttu-id="6df2b-155">코드 포인트의 전체 범위 내에 두 가지 하위 범위가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-155">Within the full range of code points there are two subranges:</span></span>

* <span data-ttu-id="6df2b-156">**BMP(기본 다국어 평면)** 는 `U+0000..U+FFFF` 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-156">The **Basic Multilingual Plane (BMP)** in the range `U+0000..U+FFFF`.</span></span> <span data-ttu-id="6df2b-157">이 16비트 범위는 전 세계 쓰기 시스템을 대부분 포괄하는 데 충분한 65,536개 코드 포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-157">This 16-bit range provides 65,536 code points, enough to cover the majority of the world's writing systems.</span></span>
* <span data-ttu-id="6df2b-158">**보조 코드 포인트**는 `U+10000..U+10FFFF` 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-158">**Supplementary code points** in the range `U+10000..U+10FFFF`.</span></span> <span data-ttu-id="6df2b-159">이 21비트 범위는 덜 알려진 언어와 이모지 같은 다른 용도로 사용할 수 있는 백만 개 이상의 추가 코드 포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-159">This 21-bit range provides more than a million additional code points that can be used for less well-known languages and other purposes such as emojis.</span></span>

<span data-ttu-id="6df2b-160">다음 다이어그램에서는 BMP와 보조 코드 포인트의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-160">The following diagram illustrates the relationship between the BMP and the supplementary code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-supplementary.svg" alt-text="BMP 및 보조 코드 포인트":::

## <a name="utf-16-code-units"></a><span data-ttu-id="6df2b-162">UTF-16 코드 단위</span><span class="sxs-lookup"><span data-stu-id="6df2b-162">UTF-16 code units</span></span>

<span data-ttu-id="6df2b-163">16비트 유니코드 변환 형식([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16))은 16비트 ‘코드 단위’를 사용하여 유니코드 코드 포인트를 나타내는 문자 인코딩 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-163">16-bit Unicode Transformation Format ([UTF-16](https://www.unicode.org/faq/utf_bom.html#UTF16)) is a character encoding system that uses 16-bit *code units* to represent Unicode code points.</span></span> <span data-ttu-id="6df2b-164">.NET에서는 UTF-16을 사용하여 `string`의 텍스트를 인코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-164">.NET uses UTF-16 to encode the text in a `string`.</span></span> <span data-ttu-id="6df2b-165">`char` 인스턴스는 16비트 코드 단위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-165">A `char` instance represents a 16-bit code unit.</span></span>

<span data-ttu-id="6df2b-166">단일 16비트 코드 단위는 기본 다국어 평면 16비트 범위의 코드 포인트를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-166">A single 16-bit code unit can represent any code point in the 16-bit range of the Basic Multilingual Plane.</span></span> <span data-ttu-id="6df2b-167">하지만 보조 범위의 코드 포인트의 경우 두 개의 `char` 인스턴스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-167">But for a code point in the supplementary range, two `char` instances are needed.</span></span>

## <a name="surrogate-pairs"></a><span data-ttu-id="6df2b-168">서로게이트 쌍</span><span class="sxs-lookup"><span data-stu-id="6df2b-168">Surrogate pairs</span></span>

<span data-ttu-id="6df2b-169">두 개의 16비트 값을 단일 21비트 값으로 변환하는 과정은 `U+D800`부터 `U+DFFF`까지(10진수 55.296부터 57,343까지)의 특수 범위인 *서로게이트 코드 포인트*를 통해 간단해집니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-169">The translation of two 16-bit values to a single 21-bit value is facilitated by a special range called the *surrogate code points*, from `U+D800` to `U+DFFF` (decimal 55,296 to 57,343), inclusive.</span></span>

<span data-ttu-id="6df2b-170">다음 다이어그램에서는 BMP와 서로게이트 코드 포인트의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-170">The following diagram illustrates the relationship between the BMP and the surrogate code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/bmp-and-surrogate.svg" alt-text="BMP 및 서로게이트 코드 포인트":::

<span data-ttu-id="6df2b-172">*상위 서로게이트* 코드 포인트(`U+D800..U+DBFF`) 바로 다음에 *하위 서로게이트* 코드 포인트(`U+DC00..U+DFFF`)가 오는 경우 이 쌍은 다음 수식을 사용하여 보조 코드 포인트로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-172">When a *high surrogate* code point (`U+D800..U+DBFF`) is immediately followed by a *low surrogate* code point (`U+DC00..U+DFFF`), the pair is interpreted as a supplementary code point by using the following formula:</span></span>

```
code point = 0x10000 +
  ((high surrogate code point - 0xD800) * 0x0400) +
  (low surrogate code point - 0xDC00)
```

<span data-ttu-id="6df2b-173">다음은 10진수 표기법을 사용하는 동일한 수식입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-173">Here's the same formula using decimal notation:</span></span>

```
code point = 65,536 +
  ((high surrogate code point - 55,296) * 1,024) +
  (low surrogate code point - 56,320)
```

<span data-ttu-id="6df2b-174">*상위* 서로게이트 코드 포인트가 *하위* 서로게이트 코드 포인트보다 높은 값을 갖는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-174">A *high* surrogate code point doesn't have a higher number value than a *low* surrogate code point.</span></span> <span data-ttu-id="6df2b-175">상위 서로게이트 코드 포인트는 전체 21비트 코드 포인트 범위의 상위 차수 11비트를 계산하는 데 사용되기 때문에 "상위"라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-175">The high surrogate code point is called "high" because it's used to calculate the higher-order 11 bits of the full 21-bit code point range.</span></span> <span data-ttu-id="6df2b-176">하위 서로게이트 코드 포인트는 하위 차수 10비트를 계산하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-176">The low surrogate code point is used to calculate the lower-order 10 bits.</span></span>

<span data-ttu-id="6df2b-177">예를 들어 서로게이트 쌍 `0xD83C` 및 `0xDF39`에 해당하는 실제 코드 포인트는 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-177">For example, the actual code point that corresponds to the surrogate pair `0xD83C` and `0xDF39`  is computed as follows:</span></span>

```
actual = 0x10000 + ((0xD83C - 0xD800) * 0x0400) + (0xDF39 - 0xDC00)
       = 0x10000 + (          0x003C  * 0x0400) +           0x0339
       = 0x10000 +                      0xF000  +           0x0339
       = 0x1F339
```

<span data-ttu-id="6df2b-178">다음은 10진수 표기법을 사용한 동일한 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-178">Here's the same calculation using decimal notation:</span></span>

```
actual =  65,536 + ((55,356 - 55,296) * 1,024) + (57,145 - 56320)
       =  65,536 + (              60  * 1,024) +             825
       =  65,536 +                     61,440  +             825
       = 127,801
```

<span data-ttu-id="6df2b-179">앞의 예제에서는 `"\ud83c\udf39"`가 앞서 언급한 `U+1F339 ROSE ('🌹')` 코드 포인트의 UTF-16 인코딩입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-179">The preceding example demonstrates that `"\ud83c\udf39"` is the UTF-16 encoding of the `U+1F339 ROSE ('🌹')` code point mentioned earlier.</span></span>

## <a name="unicode-scalar-values"></a><span data-ttu-id="6df2b-180">유니코드 스칼라 값</span><span class="sxs-lookup"><span data-stu-id="6df2b-180">Unicode scalar values</span></span>

<span data-ttu-id="6df2b-181">용어 [유니코드 스칼라 값](https://www.unicode.org/glossary/#unicode_scalar_value)은 서로게이트 코드 포인트가 아닌 모든 코드 포인트를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-181">The term [Unicode scalar value](https://www.unicode.org/glossary/#unicode_scalar_value) refers to all code points other than the surrogate code points.</span></span> <span data-ttu-id="6df2b-182">즉, 스칼라 값은 문자가 할당되었거나 나중에 문자가 할당될 수 있는 모든 코드 포인트입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-182">In other words, a scalar value is any code point that is assigned a character or can be assigned a character in the future.</span></span> <span data-ttu-id="6df2b-183">여기서 “문자”는 텍스트 또는 문자가 표시되는 방식을 제어하는 작업 등을 포함하여 코드 포인트에 할당될 수 있는 모든 것을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-183">"Character" here refers to anything that can be assigned to a code point, which includes such things as actions that control how text or characters are displayed.</span></span>

<span data-ttu-id="6df2b-184">다음 다이어그램에서는 스칼라 값 코드 포인트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-184">The following diagram illustrates the scalar value code points.</span></span>

:::image type="content" source="media/character-encoding-introduction/scalar-values.svg" alt-text="스칼라 값":::

### <a name="the-no-locrune-type-as-a-scalar-value"></a><span data-ttu-id="6df2b-186">스칼라 값의 Rune 형식</span><span class="sxs-lookup"><span data-stu-id="6df2b-186">The Rune type as a scalar value</span></span>

<span data-ttu-id="6df2b-187">.NET Core 3.0부터 <xref:System.Text.Rune?displayProperty=fullName> 형식은 유니코드 스칼라 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-187">Beginning with .NET Core 3.0, the <xref:System.Text.Rune?displayProperty=fullName> type represents a Unicode scalar value.</span></span> <span data-ttu-id="6df2b-188">**`Rune`는 .NET Core 2.x 또는 .NET Framework 4.x에서 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="6df2b-188">**`Rune` is not available in .NET Core 2.x or .NET Framework 4.x.**</span></span>

<span data-ttu-id="6df2b-189">`Rune` 생성자는 결과 인스턴스가 유효한 유니코드 스칼라 값인지 확인합니다. 유효하지 않은 경우에는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-189">The `Rune` constructors validate that the resulting instance is a valid Unicode scalar value, otherwise they throw an exception.</span></span> <span data-ttu-id="6df2b-190">다음 예제에서는 입력이 유효한 스칼라 값을 나타내므로 `Rune` 인스턴스를 성공적으로 인스턴스화하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-190">The following example shows code that successfully instantiates `Rune` instances because the input represents valid scalar values:</span></span>

<span data-ttu-id="6df2b-191">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-191">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetValid":::</span></span>

<span data-ttu-id="6df2b-192">다음 예제에서는 코드 포인트가 서로게이트 범위에 있고 서로게이트 쌍에 속하지 않기 때문에 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-192">The following example throws an exception because the code point is in the surrogate range and isn't part of a surrogate pair:</span></span>

<span data-ttu-id="6df2b-193">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-193">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidSurrogate":::</span></span>

<span data-ttu-id="6df2b-194">다음 예제에서는 코드 포인트가 보조 범위를 초과하기 때문에 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-194">The following example throws an exception because the code point is beyond the supplementary range:</span></span>

<span data-ttu-id="6df2b-195">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-195">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InstantiateRunes.cs" id="SnippetInvalidHigh":::</span></span>

### <a name="no-locrune-usage-example-changing-letter-case"></a><span data-ttu-id="6df2b-196">Rune 사용 예제: 문자 대/소문자 변경</span><span class="sxs-lookup"><span data-stu-id="6df2b-196">Rune usage example: changing letter case</span></span>

<span data-ttu-id="6df2b-197">`char`를 사용하고 스칼라 값 코드 포인트에서 작동하는 것으로 가정하는 API는 `char`가 서로게이트 쌍의 일부인 경우 올바르게 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-197">An API that takes a `char` and assumes it is working with a code point that is a scalar value doesn't work correctly if the `char` is from a surrogate pair.</span></span> <span data-ttu-id="6df2b-198">예를 들어 string의 각 char에서 <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출하는 다음 메서드를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-198">For example, consider the following method that calls <xref:System.Char.ToUpperInvariant%2A?displayProperty=nameWithType> on each char in a string:</span></span>

<span data-ttu-id="6df2b-199">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-199">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="6df2b-200">`input` string에 소문자 데저렛 문자 `er`(`𐑉`)이 포함되는 경우 이 코드는 대문자(`𐐡`)로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-200">If the `input` string contains the lowercase Deseret letter `er` (`𐑉`), this code won't convert it to uppercase (`𐐡`).</span></span> <span data-ttu-id="6df2b-201">이 코드는 각 서로게이트 코드 포인트 `U+D801` 및 `U+DC49`에서 별도로 `char.ToUpperInvariant`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-201">The code calls `char.ToUpperInvariant` separately on each surrogate code point, `U+D801` and `U+DC49`.</span></span> <span data-ttu-id="6df2b-202">그러나 `U+D801` 자체에는 해당 정보를 소문자로 식별하는 데 충분한 정보가 없으므로 `char.ToUpperInvariant`는 이를 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-202">But `U+D801` doesn't have enough information by itself to identify it as a lowercase letter, so `char.ToUpperInvariant` leaves it alone.</span></span> <span data-ttu-id="6df2b-203">그리고 `U+DC49`도 동일한 방식으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-203">And it handles `U+DC49` the same way.</span></span> <span data-ttu-id="6df2b-204">그 결과 `input` string의 소문자 '𐑉'가 대문자 '𐑉'로 변환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-204">The result is that lowercase '𐑉' in the `input` string doesn't get converted to uppercase '𐐡'.</span></span>

<span data-ttu-id="6df2b-205">string를 올바르게 대문자로 변환하는 두 가지 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-205">Here are two options for correctly converting a string to uppercase:</span></span>

* <span data-ttu-id="6df2b-206">`char` 및 `char`를 반복하는 대신 입력 string에서 <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-206">Call <xref:System.String.ToUpperInvariant%2A?displayProperty=nameWithType> on the input string rather than iterating `char`-by-`char`.</span></span> <span data-ttu-id="6df2b-207">`string.ToUpperInvariant` 메서드는 각 서로게이트 쌍의 두 부분에 모두 액세스할 수 있으므로 모든 유니코드 코드 포인트를 올바르게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-207">The `string.ToUpperInvariant` method has access to both parts of each surrogate pair, so it can handle all Unicode code points correctly.</span></span>
* <span data-ttu-id="6df2b-208">다음 예제와 같이 `char` 인스턴스 대신 `Rune` 인스턴스로 유니코드 스칼라 값을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-208">Iterate through the Unicode scalar values as `Rune` instances instead of `char` instances, as shown in the following example.</span></span> <span data-ttu-id="6df2b-209">`Rune` 인스턴스는 유효한 유니코드 스칼라 값이므로 스칼라 값에 대해 작동할 것으로 간주되는 API에 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-209">Since a `Rune` instance is a valid Unicode scalar value, it can be passed to APIs that expect to operate on a scalar value.</span></span> <span data-ttu-id="6df2b-210">예를 들어 다음 예제와 같이 <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType>를 호출하면 올바른 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-210">For example, calling <xref:System.Text.Rune.ToUpperInvariant%2A?displayProperty=nameWithType> as shown in the following example gives correct results:</span></span>

  <span data-ttu-id="6df2b-211">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-211">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/ConvertToUpper.cs" id="SnippetGoodExample":::</span></span>

### <a name="other-no-locrune-apis"></a><span data-ttu-id="6df2b-212">기타 Rune API</span><span class="sxs-lookup"><span data-stu-id="6df2b-212">Other Rune APIs</span></span>

<span data-ttu-id="6df2b-213">`Rune` 형식은 다수의 `char` API의 아날로그를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-213">The `Rune` type exposes analogs of many of the `char` APIs.</span></span> <span data-ttu-id="6df2b-214">예를 들어 다음 메서드는 `char` 형식에 대한 정적 API를 미러링합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-214">For example, the following methods mirror static APIs on the `char` type:</span></span>

* <xref:System.Text.Rune.IsLetter%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsWhiteSpace%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.IsLetterOrDigit%2A?displayProperty=nameWithType>
* <xref:System.Text.Rune.GetUnicodeCategory%2A?displayProperty=nameWithType>

<span data-ttu-id="6df2b-215">`Rune` 인스턴스에서 원시 스칼라 값을 가져오려면 <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-215">To get the raw scalar value from a `Rune` instance, use the <xref:System.Text.Rune.Value%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="6df2b-216">`Rune` 인스턴스를 `char`의 시퀀스로 다시 변환하려면 <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> 또는 <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-216">To convert a `Rune` instance back to a sequence of `char`s, use <xref:System.Text.Rune.ToString%2A?displayProperty=nameWithType> or the <xref:System.Text.Rune.EncodeToUtf16%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6df2b-217">모든 유니코드 스칼라 값은 단일 `char` 또는 서로게이트 쌍으로 표현할 수 있으므로 `Rune` 인스턴스는 최대 2개의 `char` 인스턴스로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-217">Since any Unicode scalar value is representable by a single `char` or by a surrogate pair, any `Rune` instance can be represented by at most 2 `char` instances.</span></span> <span data-ttu-id="6df2b-218"><xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType>를 사용하여 `Rune` 인스턴스를 표현하는 데 필요한 `char` 인스턴스 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-218">Use <xref:System.Text.Rune.Utf16SequenceLength%2A?displayProperty=nameWithType> to see how many `char` instances are required to represent a `Rune` instance.</span></span>

<span data-ttu-id="6df2b-219">.NET `Rune` 형식에 대한 자세한 내용은 [`Rune` API 참조](xref:System.Text.Rune)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6df2b-219">For more information about the .NET `Rune` type, see the [`Rune` API reference](xref:System.Text.Rune).</span></span>

## <a name="grapheme-clusters"></a><span data-ttu-id="6df2b-220">문자소 클러스터</span><span class="sxs-lookup"><span data-stu-id="6df2b-220">Grapheme clusters</span></span>

<span data-ttu-id="6df2b-221">한 문자처럼 보이는 것이 여러 코드 포인트가 조합된 결과일 수 있으므로 “문자” 대신 자주 사용되는 보다 서술적인 용어가 [문자소 클러스터](https://www.unicode.org/glossary/#grapheme_cluster)입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-221">What looks like one character might result from a combination of multiple code points, so a more descriptive term that is often used in place of "character" is [grapheme cluster](https://www.unicode.org/glossary/#grapheme_cluster).</span></span> <span data-ttu-id="6df2b-222">.NET에서 해당 용어는 [텍스트 요소](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A)입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-222">The equivalent term in .NET is [text element](xref:System.Globalization.StringInfo.GetTextElementEnumerator%2A).</span></span>

<span data-ttu-id="6df2b-223">`string` 인스턴스 “a”, “á”, “á”, “`👩🏽‍🚒`” 등을 살펴보겠습니다,</span><span class="sxs-lookup"><span data-stu-id="6df2b-223">Consider the `string` instances "a", "á", "á", and "`👩🏽‍🚒`".</span></span> <span data-ttu-id="6df2b-224">운영 체제가 유니코드 표준에 지정된 대로 이들 항목을 처리하는 경우 각 `string` 인스턴스는 단일 텍스트 요소나 문자소 클러스터로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-224">If your operating system handles them as specified by the Unicode standard, each of these `string` instances appears as a single text element or grapheme cluster.</span></span> <span data-ttu-id="6df2b-225">하지만 마지막 두 개는 둘 이상의 스칼라 값 코드 포인트로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-225">But the last two are represented by more than one scalar value code point.</span></span>

* <span data-ttu-id="6df2b-226">string "a"는 하나의 스칼라 값으로 표현되고 하나의 `char` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-226">The string "a" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+0061 LATIN SMALL LETTER A`

* <span data-ttu-id="6df2b-227">string "á"는 하나의 스칼라 값으로 표현되고 하나의 `char` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-227">The string "á" is represented by one scalar value and contains one `char` instance.</span></span>

  * `U+00E1 LATIN SMALL LETTER A WITH ACUTE`

* <span data-ttu-id="6df2b-228">string "á"는 "Á"와 같아 보이지만 두 개의 스칼라 값으로 표현되고 두 개의 `char` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-228">The string "á" looks the same as "á" but is represented by two scalar values and contains two `char` instances.</span></span>

  * `U+0061 LATIN SMALL LETTER A`
  * `U+0301 COMBINING ACUTE ACCENT`

* <span data-ttu-id="6df2b-229">마지막으로 string "`👩🏽‍🚒`"은 4개의 스칼라 값으로 표현되고 7개의 `char` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-229">Finally, the string "`👩🏽‍🚒`" is represented by four scalar values and contains seven `char` instances.</span></span>

  * <span data-ttu-id="6df2b-230">`U+1F469 WOMAN`(보조 범위, 서로게이트 쌍 필요)</span><span class="sxs-lookup"><span data-stu-id="6df2b-230">`U+1F469 WOMAN` (supplementary range, requires a surrogate pair)</span></span>
  * <span data-ttu-id="6df2b-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4`(보조 범위, 서로게이트 쌍 필요)</span><span class="sxs-lookup"><span data-stu-id="6df2b-231">`U+1F3FD EMOJI MODIFIER FITZPATRICK TYPE-4` (supplementary range, requires a surrogate pair)</span></span>
  * `U+200D ZERO WIDTH JOINER`
  * <span data-ttu-id="6df2b-232">`U+1F692 FIRE ENGINE`(보조 범위, 서로게이트 쌍 필요)</span><span class="sxs-lookup"><span data-stu-id="6df2b-232">`U+1F692 FIRE ENGINE` (supplementary range, requires a surrogate pair)</span></span>

<span data-ttu-id="6df2b-233">위의 예제 중 일부(예: 결합 악센트 한정자 또는 스킨 톤 한정자)에서는 코드 포인트가 화면에 독립 실행형 요소로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-233">In some of the preceding examples - such as the combining accent modifier or the skin tone modifier - the code point does not display as a standalone element on the screen.</span></span> <span data-ttu-id="6df2b-234">대신, 텍스트 요소의 모양을 수정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-234">Rather, it serves to modify the appearance of a text element that came before it.</span></span> <span data-ttu-id="6df2b-235">예제를 통해 단일 “문자” 또는 “문자소 클러스터”로 간주되는 것을 구성하기 위해 여러 스칼라 값이 필요할 수 있음을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-235">These examples show that it might take multiple scalar values to make up what we think of as a single "character," or "grapheme cluster."</span></span>

<span data-ttu-id="6df2b-236">`string`의 문자소 클러스터를 열거하려면 다음 예제와 같이 <xref:System.Globalization.StringInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-236">To enumerate the grapheme clusters of a `string`, use the <xref:System.Globalization.StringInfo> class as shown in the following example.</span></span> <span data-ttu-id="6df2b-237">Swift에 대해 잘 알고 있는 경우 .NET `StringInfo` 형식은 개념적으로 [Swift의 `character` 형식](https://developer.apple.com/documentation/swift/character)과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-237">If you're familiar with Swift, the .NET `StringInfo` type is conceptually similar to [Swift's `character` type](https://developer.apple.com/documentation/swift/character).</span></span>

### <a name="example-count-no-locchar-no-locrune-and-text-element-instances"></a><span data-ttu-id="6df2b-238">예: count char, Rune 및 텍스트 요소 인스턴스</span><span class="sxs-lookup"><span data-stu-id="6df2b-238">Example: count char, Rune, and text element instances</span></span>

<span data-ttu-id="6df2b-239">.NET API에서는 문자소 클러스터를 *텍스트 요소*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-239">In .NET APIs, a grapheme cluster is called a *text element*.</span></span> <span data-ttu-id="6df2b-240">다음 메서드는 `string`에서 `char`, `Rune` 및 텍스트 요소 인스턴스 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-240">The following method demonstrates the differences between `char`, `Rune`, and text element instances in a `string`:</span></span>

<span data-ttu-id="6df2b-241">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-241">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCountMethod":::</span></span>

<span data-ttu-id="6df2b-242">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-242">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/CountTextElements.cs" id="SnippetCallCountMethod":::</span></span>

<span data-ttu-id="6df2b-243">.NET Framework 또는 .NET Core 3.1 이전 버전에서 이 코드를 실행하는 경우 이모지의 텍스트 요소 수에 `4`가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-243">If you run this code in .NET Framework or .NET Core 3.1 or earlier, the text element count for the emoji shows `4`.</span></span> <span data-ttu-id="6df2b-244">이는 .NET 5에서 수정된 `StringInfo` 클래스의 버그로 인한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-244">That is due to a bug in the `StringInfo` class that is fixed in .NET 5.</span></span>

### <a name="example-splitting-no-locstring-instances"></a><span data-ttu-id="6df2b-245">예: string 인스턴스 분할</span><span class="sxs-lookup"><span data-stu-id="6df2b-245">Example: splitting string instances</span></span>

<span data-ttu-id="6df2b-246">`string` 인스턴스를 분할하는 경우 서로게이트 쌍 및 문자소 클러스터를 분할하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6df2b-246">When splitting `string` instances, avoid splitting surrogate pairs and grapheme clusters.</span></span> <span data-ttu-id="6df2b-247">다음은 string에 10자마다 줄 바꿈을 삽입하려는 코드의 잘못된 예입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-247">Consider the following example of incorrect code, which intends to insert line breaks every 10 characters in a string:</span></span>

<span data-ttu-id="6df2b-248">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-248">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetBadExample":::</span></span>

<span data-ttu-id="6df2b-249">이 코드는 `char` 인스턴스를 열거하기 때문에 10개 `char`의 경계에 걸쳐 있는 서로게이트 쌍이 분할되고 그 사이에 줄 바꿈이 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-249">Because this code enumerates `char` instances, a surrogate pair that happens to straddle a 10-`char` boundary will be split and a newline injected between them.</span></span> <span data-ttu-id="6df2b-250">서로게이트 코드 포인트는 쌍으로만 의미가 있으므로 이 삽입은 데이터를 손상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-250">This insertion introduces data corruption, because surrogate code points are meaningful only as pairs.</span></span>

<span data-ttu-id="6df2b-251">`char` 인스턴스 대신 `Rune` 인스턴스(스칼라 값)를 열거하는 경우 데이터 손상 가능성이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-251">The potential for data corruption isn't eliminated if you enumerate `Rune` instances (scalar values) instead of `char` instances.</span></span> <span data-ttu-id="6df2b-252">한 `Rune` 인스턴스 집합이 10개 `char`의 경계에 걸쳐 있는 문자소 클러스터를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-252">A set of `Rune` instances might make up a grapheme cluster that straddles a 10-`char` boundary.</span></span> <span data-ttu-id="6df2b-253">문자소 클러스터 집합이 분할된 경우 올바르게 해석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-253">If the grapheme cluster set is split up, it can't be interpreted correctly.</span></span>

<span data-ttu-id="6df2b-254">다음 예제와 같이 문자소 클러스터(또는 텍스트 요소)를 계산하여 string을 줄 바꿈하는 것이 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-254">A better approach is to break the string by counting grapheme clusters, or text elements, as in the following example:</span></span>

<span data-ttu-id="6df2b-255">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span><span class="sxs-lookup"><span data-stu-id="6df2b-255">:::code language="csharp" source="snippets/character-encoding-introduction/csharp/InsertNewlines.cs" id="SnippetGoodExample":::</span></span>

<span data-ttu-id="6df2b-256">그러나 앞에서 설명한 것처럼 .NET 5 이외의 .NET 구현에서는 `StringInfo` 클래스가 일부 문자소 클러스터를 잘못 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-256">As noted earlier, however, in implementations of .NET other than .NET 5, the `StringInfo` class might handle some grapheme clusters incorrectly.</span></span>

## <a name="utf-8-and-utf-32"></a><span data-ttu-id="6df2b-257">UTF-8 및 UTF-32</span><span class="sxs-lookup"><span data-stu-id="6df2b-257">UTF-8 and UTF-32</span></span>

<span data-ttu-id="6df2b-258">이전 섹션에서는 UTF-16에 초점을 두었습니다. .NET이 `string` 인스턴스를 인코딩하는 데 사용하기 때문이었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-258">The preceding sections focused on UTF-16 because that's what .NET uses to encode `string` instances.</span></span> <span data-ttu-id="6df2b-259">다른 유니코드용 인코딩 시스템 [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) 및 [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32)도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-259">There are other encoding systems for Unicode - [UTF-8](https://www.unicode.org/faq/utf_bom.html#UTF8) and [UTF-32](https://www.unicode.org/faq/utf_bom.html#UTF32).</span></span> <span data-ttu-id="6df2b-260">이러한 인코딩은 각각 8비트 코드 단위 및 32비트 코드 단위를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-260">These encodings use 8-bit code units and 32-bit code units, respectively.</span></span>

<span data-ttu-id="6df2b-261">UTF-16과 마찬가지로 UTF-8은 일부 유니코드 스칼라 값을 나타내기 위해 여러 코드 단위가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-261">Like UTF-16, UTF-8 requires multiple code units to represent some Unicode scalar values.</span></span> <span data-ttu-id="6df2b-262">UTF-32는 단일 32비트 코드 단위로 모든 스칼라 값을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-262">UTF-32 can represent any scalar value in a single 32-bit code unit.</span></span>

<span data-ttu-id="6df2b-263">다음은 이러한 세 가지 유니코드 인코딩 시스템에서 동일한 유니코드 코드 포인트를 표현하는 방법을 보여 주는 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-263">Here are some examples showing how the same Unicode code point is represented in each of these three Unicode encoding systems:</span></span>

```
Scalar: U+0061 LATIN SMALL LETTER A ('a')
UTF-8 : [ 61 ]           (1x  8-bit code unit  = 8 bits total)
UTF-16: [ 0061 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000061 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+0429 CYRILLIC CAPITAL LETTER SHCHA ('Щ')
UTF-8 : [ D0 A9 ]        (2x  8-bit code units = 16 bits total)
UTF-16: [ 0429 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 00000429 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+A992 JAVANESE LETTER GA ('ꦒ')
UTF-8 : [ EA A6 92 ]     (3x  8-bit code units = 24 bits total)
UTF-16: [ A992 ]         (1x 16-bit code unit  = 16 bits total)
UTF-32: [ 0000A992 ]     (1x 32-bit code unit  = 32 bits total)

Scalar: U+104CC OSAGE CAPITAL LETTER TSHA ('𐓌')
UTF-8 : [ F0 90 93 8C ]  (4x  8-bit code units = 32 bits total)
UTF-16: [ D801 DCCC ]    (2x 16-bit code units = 32 bits total)
UTF-32: [ 000104CC ]     (1x 32-bit code unit  = 32 bits total)
```

<span data-ttu-id="6df2b-264">앞서 설명한 것처럼 [서로게이트 쌍](#surrogate-pairs)의 단일 UTF-16 코드 단위는 그 자체로는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-264">As noted earlier, a single UTF-16 code unit from a [surrogate pair](#surrogate-pairs) is meaningless by itself.</span></span> <span data-ttu-id="6df2b-265">동일한 방식으로 단일 UTF-8 코드 단위가 스칼라 값을 계산하기 위해 2, 3 또는 4개의 시퀀스로 사용되는 경우에는 자체로는 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-265">In the same way, a single UTF-8 code unit is meaningless by itself if it's in a sequence of two, three, or four used to calculate a scalar value.</span></span>

### <a name="endianness"></a><span data-ttu-id="6df2b-266">endian</span><span class="sxs-lookup"><span data-stu-id="6df2b-266">Endianness</span></span>

<span data-ttu-id="6df2b-267">.NET에서 string의 UTF-16 코드 단위는 연속 메모리에 16비트 정수(`char` 인스턴스)의 시퀀스로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-267">In .NET, the UTF-16 code units of a string are stored in contiguous memory as a sequence of 16-bit integers (`char` instances).</span></span> <span data-ttu-id="6df2b-268">개별 코드 단위의 비트는 현재 아키텍처의 [endian](https://en.wikipedia.org/wiki/Endianness)에 따라 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-268">The bits of individual code units are laid out according to the [endianness](https://en.wikipedia.org/wiki/Endianness) of the current architecture.</span></span>

<span data-ttu-id="6df2b-269">Little-Endian 아키텍처에서는 UTF-16 코드 포인트 `[ D801 DCCC ]`로 구성된 string이 바이트 `[ 0x01, 0xD8, 0xCC, 0xDC ]`로 메모리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-269">On a little-endian architecture, the string consisting of the UTF-16 code points `[ D801 DCCC ]` would be laid out in memory as the bytes `[ 0x01, 0xD8, 0xCC, 0xDC ]`.</span></span> <span data-ttu-id="6df2b-270">Big-Endian 아키텍처에서는 동일한 string이 바이트 `[ 0xD8, 0x01, 0xDC, 0xCC ]`로 메모리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-270">On a big-endian architecture that same string would be laid out in memory as the bytes `[ 0xD8, 0x01, 0xDC, 0xCC ]`.</span></span>

<span data-ttu-id="6df2b-271">서로 통신하는 컴퓨터 시스템은 네트워크를 통과하는 데이터의 표현에 동의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-271">Computer systems that communicate with each other must agree on the representation of data crossing the wire.</span></span> <span data-ttu-id="6df2b-272">대부분의 네트워크 프로토콜은 텍스트를 전송할 때 UTF-8을 표준으로 사용하여 Little-Endian 컴퓨터와 통신하는 Big-Endian 컴퓨터에서 발생하는 문제를 부분적으로 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-272">Most network protocols use UTF-8 as a standard when transmitting text, partly to avoid issues that might result from a big-endian machine communicating with a little-endian machine.</span></span> <span data-ttu-id="6df2b-273">UTF-8 코드 포인트 `[ F0 90 93 8C ]`로 구성되는 string은 endian에 관계없이 항상 바이트 `[ 0xF0, 0x90, 0x93, 0x8C ]`로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-273">The string consisting of the UTF-8 code points `[ F0 90 93 8C ]` will always be represented as the bytes `[ 0xF0, 0x90, 0x93, 0x8C ]` regardless of endianness.</span></span>

<span data-ttu-id="6df2b-274">텍스트를 전송하는 데 UTF-8을 사용하기 위해 .NET 애플리케이션은 종종 다음 예제와 같은 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-274">To use UTF-8 for transmitting text, .NET applications often use code like the following example:</span></span>

```csharp
string stringToWrite = GetString();
byte[] stringAsUtf8Bytes = Encoding.UTF8.GetBytes(stringToWrite);
await outputStream.WriteAsync(stringAsUtf8Bytes, 0, stringAsUtf8Bytes.Length);
```

<span data-ttu-id="6df2b-275">앞의 예제에서 [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) 메서드는 UTF-16 `string`을 일련의 유니코드 스칼라 값으로 다시 디코딩한 다음 해당 스칼라 값을 UTF-8로 인코드하여 결과 시퀀스를 `byte` 배열에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-275">In the preceding example, the method [Encoding.UTF8.GetBytes](xref:System.Text.UTF8Encoding.GetBytes%2A) decodes the UTF-16 `string` back into a series of Unicode scalar values, then it re-encodes those scalar values into UTF-8 and places the resulting sequence into a `byte` array.</span></span> <span data-ttu-id="6df2b-276">[Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) 메서드는 반대 방향으로 변환을 수행하여 UTF-8 `byte` 배열을 UTF-16 `string`로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-276">The method [Encoding.UTF8.GetString](xref:System.Text.UTF8Encoding.GetString%2A) performs the opposite transformation, converting a UTF-8 `byte` array to a UTF-16 `string`.</span></span>

> [!WARNING]
> <span data-ttu-id="6df2b-277">UTF-8은 인터넷에서 일반적이므로 네트워크에서 원시 바이트를 읽고 데이터를 UTF-8인 것처럼 처리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-277">Since UTF-8 is commonplace on the internet, it may be tempting to read raw bytes from the wire and to treat the data as if it were UTF-8.</span></span> <span data-ttu-id="6df2b-278">그러나 잘 구성된 인코딩인지 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-278">However, you should validate that it is indeed well-formed.</span></span> <span data-ttu-id="6df2b-279">악의적인 클라이언트가 잘못 구성된 UTF-8을 서비스에 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-279">A malicious client might submit ill-formed UTF-8 to your service.</span></span> <span data-ttu-id="6df2b-280">이러한 데이터를 잘 구성된 것처럼 작업하는 경우 애플리케이션에서 오류 또는 보안 허점이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-280">If you operate on that data as if it were well-formed, it could cause errors or security holes in your application.</span></span> <span data-ttu-id="6df2b-281">UTF-8 데이터의 유효성을 검사하려면 들어오는 데이터를 `string`으로 변환하는 동안 유효성 검사를 수행하는 `Encoding.UTF8.GetString`와 같은 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-281">To validate UTF-8 data, you can use a method like `Encoding.UTF8.GetString`, which will perform validation while converting the incoming data to a `string`.</span></span>

### <a name="well-formed-encoding"></a><span data-ttu-id="6df2b-282">잘 구성된 인코딩</span><span class="sxs-lookup"><span data-stu-id="6df2b-282">Well-formed encoding</span></span>

<span data-ttu-id="6df2b-283">잘 구성된 유니코드 인코딩은 오류 없이 명확하게 디코딩할 수 있는 유니코드 스칼라 값의 시퀀스로 디코딩할 수 있는 코드 단위의 string입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-283">A well-formed Unicode encoding is a string of code units that can be decoded unambiguously and without error into a sequence of Unicode scalar values.</span></span> <span data-ttu-id="6df2b-284">잘 구성된 데이터는 UTF-8, UTF-16 및 UTF-32 사이에서 자유롭게 트랜스코딩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-284">Well-formed data can be transcoded freely back and forth between UTF-8, UTF-16, and UTF-32.</span></span>

<span data-ttu-id="6df2b-285">인코딩 시퀀스가 잘 구성되었는지 여부는 컴퓨터 아키텍처의 endian과 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-285">The question of whether an encoding sequence is well-formed or not is unrelated to the endianness of a machine's architecture.</span></span> <span data-ttu-id="6df2b-286">잘못 구성된 UTF-8 시퀀스는 Big-Endian 및 Little-Endian 컴퓨터 모두에서 동일한 방식으로 잘못 구성된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-286">An ill-formed UTF-8 sequence is ill-formed in the same way on both big-endian and little-endian machines.</span></span>

<span data-ttu-id="6df2b-287">다음은 잘못 구성된 인코딩의 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-287">Here are some examples of ill-formed encodings:</span></span>

* <span data-ttu-id="6df2b-288">UTF-8에서 시퀀스 `[ 6C C2 61 ]`은 잘못 구성된 것입니다. `C2` 뒤에 `61`이 올 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-288">In UTF-8, the sequence `[ 6C C2 61 ]` is ill-formed because `C2` cannot be followed by `61`.</span></span>

* <span data-ttu-id="6df2b-289">UTF-16에서 시퀀스 `[ DC00 DD00 ]`(또는 C#의 string `"\udc00\udd00"`)는 잘못 구성된 것입니다. 하위 서로게이트 `DC00` 뒤에 다른 하위 서로게이트 `DD00`가 올 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-289">In UTF-16, the sequence `[ DC00 DD00 ]` (or, in C#, the string `"\udc00\udd00"`) is ill-formed because the low surrogate `DC00` cannot be followed by another low surrogate `DD00`.</span></span>

* <span data-ttu-id="6df2b-290">UTF-32에서 시퀀스 `[ 0011ABCD ]`는 잘못 구성된 것입니다. `0011ABCD`가 유니코드 스칼라 값 범위를 벗어나기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-290">In UTF-32, the sequence `[ 0011ABCD ]` is ill-formed because `0011ABCD` is outside the range of Unicode scalar values.</span></span>

<span data-ttu-id="6df2b-291">.NET에서 `string` 인스턴스는 거의 항상 잘 구성된 UTF-16 데이터를 포함하지만 이것이 보장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-291">In .NET, `string` instances almost always contain well-formed UTF-16 data, but that isn't guaranteed.</span></span> <span data-ttu-id="6df2b-292">다음 예제에서는 `string` 인스턴스에 잘못 구성된 UTF-16 데이터를 만드는 유효한 C# 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-292">The following examples show valid C# code that creates ill-formed UTF-16 data in `string` instances.</span></span>

* <span data-ttu-id="6df2b-293">잘못 구성된 리터럴:</span><span class="sxs-lookup"><span data-stu-id="6df2b-293">An ill-formed literal:</span></span>

  ```csharp
  const string s = "\ud800";
  ```

* <span data-ttu-id="6df2b-294">서로게이트 쌍을 분할하는 substring:</span><span class="sxs-lookup"><span data-stu-id="6df2b-294">A substring that splits up a surrogate pair:</span></span>

  ```csharp
  string x = "\ud83e\udd70"; // "🥰"
  string y = x.Substring(1, 1); // "\udd70" standalone low surrogate
  ```

<span data-ttu-id="6df2b-295">[`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A)과 같은 API는 잘못 구성된 `string` 인스턴스를 반환하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-295">APIs like [`Encoding.UTF8.GetString`](xref:System.Text.UTF8Encoding.GetString%2A) never return ill-formed `string` instances.</span></span> <span data-ttu-id="6df2b-296">`Encoding.GetString` 및 `Encoding.GetBytes` 메서드는 입력에서 잘못 구성된 시퀀스를 검색하고 출력을 생성할 때 문자 대체를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-296">`Encoding.GetString` and `Encoding.GetBytes` methods detect ill-formed sequences in the input and perform character substitution when generating the output.</span></span> <span data-ttu-id="6df2b-297">예를 들어 [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A)이 입력에서 ASCII가 아닌 바이트(U+0000..U+007F 범위를 벗어남)를 발견할 경우 반환된 `string` 인스턴스에 '?'를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-297">For example, if [`Encoding.ASCII.GetString(byte[])`](xref:System.Text.ASCIIEncoding.GetString%2A) sees a non-ASCII byte in the input (outside the range U+0000..U+007F), it inserts a '?' into the returned `string` instance.</span></span> <span data-ttu-id="6df2b-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A)은 반환된 `string` 인스턴스에서 잘못 구성된 UTF-8 시퀀스를 `U+FFFD REPLACEMENT CHARACTER ('�')`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-298">[`Encoding.UTF8.GetString(byte[])`](xref:System.Text.UTF8Encoding.GetString%2A) replaces ill-formed UTF-8 sequences with `U+FFFD REPLACEMENT CHARACTER ('�')` in the returned `string` instance.</span></span> <span data-ttu-id="6df2b-299">자세한 내용은 [유니코드 표준](https://www.unicode.org/versions/latest/) 섹션 5.22 및 3.9를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6df2b-299">For more information, see [the Unicode Standard](https://www.unicode.org/versions/latest/), Sections 5.22 and 3.9.</span></span>

<span data-ttu-id="6df2b-300">잘못 구성된 시퀀스가 발견될 때 문자 대체를 수행하는 대신 예외를 throw하도록 기본 제공 `Encoding` 클래스를 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-300">The built-in `Encoding` classes can also be configured to throw an exception rather than perform character substitution when ill-formed sequences are seen.</span></span> <span data-ttu-id="6df2b-301">이 방법은 문자 대체가 허용되지 않을 수 있는 보안 관련 애플리케이션에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df2b-301">This approach is often used in security-sensitive applications where character substitution might not be acceptable.</span></span>

```csharp
byte[] utf8Bytes = ReadFromNetwork();
UTF8Encoding encoding = new UTF8Encoding(encoderShouldEmitUTF8Identifier: false, throwOnInvalidBytes: true);
string asString = encoding.GetString(utf8Bytes); // will throw if 'utf8Bytes' is ill-formed
```

<span data-ttu-id="6df2b-302">기본 제공 `Encoding` 클래스를 사용하는 방법에 대한 자세한 내용은 [.NET에서 문자 인코딩 클래스를 사용하는 방법](character-encoding.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6df2b-302">For information about how to use the built-in `Encoding` classes, see [How to use character encoding classes in .NET](character-encoding.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6df2b-303">참조</span><span class="sxs-lookup"><span data-stu-id="6df2b-303">See also</span></span>

- <xref:System.String>
- <xref:System.Char>
- <xref:System.Text.Rune>
- [<span data-ttu-id="6df2b-304">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="6df2b-304">Globalization and Localization</span></span>](../globalization-localization/index.md)
