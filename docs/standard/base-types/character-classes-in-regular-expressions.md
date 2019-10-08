---
title: .NET 정규식의 문자 클래스
description: 문자 클래스를 사용하여 .NET 정규식에서 문자 집합을 나타내는 방법을 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- character classes
- regular expressions, character classes
- characters, matching syntax
- .NET Framework regular expressions, character classes
ms.assetid: 0f8bffab-ee0d-4e0e-9a96-2b4a252bb7e4
author: rpetrusha
ms.author: ronpet
ms.custom: seodec18
ms.openlocfilehash: f6d96d14a4d05178a8f90c15edecb1318e8c5a36
ms.sourcegitcommit: 7bfe1682d9368cf88d43e895d1e80ba2d88c3a99
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71957195"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="aac68-103">정규식의 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="aac68-103">Character classes in regular expressions</span></span>

<span data-ttu-id="aac68-104">문자 클래스는 문자 집합을 정의하며, 이 중 하나가 입력 문자열에서 발생하면 일치하는 것으로 판정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-104">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="aac68-105">.NET의 정규식 언어는 다음과 같은 문자 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-105">The regular expression language in .NET supports the following character classes:</span></span>  
  
- <span data-ttu-id="aac68-106">긍정 문자 그룹.</span><span class="sxs-lookup"><span data-stu-id="aac68-106">Positive character groups.</span></span> <span data-ttu-id="aac68-107">입력 문자열의 문자는 지정된 문자 집합 중 하나와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-107">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="aac68-108">자세한 내용은 [긍정 문자 그룹](#PositiveGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-108">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
- <span data-ttu-id="aac68-109">부정 문자 그룹.</span><span class="sxs-lookup"><span data-stu-id="aac68-109">Negative character groups.</span></span> <span data-ttu-id="aac68-110">입력 문자열의 문자는 지정된 문자 집합 중 하나와 일치하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-110">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="aac68-111">자세한 내용은 [부정 문자 그룹](#NegativeGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-111">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
- <span data-ttu-id="aac68-112">임의의 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-112">Any character.</span></span> <span data-ttu-id="aac68-113">정규식의 `.`(점 또는 마침표) 문자는 `\n`을 제외한 모든 문자와 일치하는 와일드카드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-113">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="aac68-114">자세한 내용은 [임의의 문자](#AnyCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-114">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
- <span data-ttu-id="aac68-115">일반 유니코드 범주 또는 명명된 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-115">A general Unicode category or named block.</span></span> <span data-ttu-id="aac68-116">입력 문자열의 문자는 일치하는 것으로 판정하려면 특정 유니코드 범주의 멤버이거나 유니코드 문자의 연속된 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-116">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="aac68-117">자세한 내용은 [유니코드 범주 또는 유니코드 블록](#CategoryOrBlock)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-117">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
- <span data-ttu-id="aac68-118">부정 일반 유니코드 범주 또는 명명된 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-118">A negative general Unicode category or named block.</span></span> <span data-ttu-id="aac68-119">입력 문자열의 문자는 일치하는 것으로 판정하려면 특정 유니코드 범주의 멤버가 아니거나 유니코드 문자의 연속된 범위 내에 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-119">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="aac68-120">자세한 내용은 [부정 유니코드 범주 또는 유니코드 블록](#NegativeCategoryOrBlock)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-120">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
- <span data-ttu-id="aac68-121">단어 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-121">A word character.</span></span> <span data-ttu-id="aac68-122">입력 문자열의 문자는 단어에 있는 문자에 적합한 유니코드 범주에 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-122">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="aac68-123">자세한 내용은 [단어 문자](#WordCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-123">For more information, see [Word Character](#WordCharacter).</span></span>  
  
- <span data-ttu-id="aac68-124">비단어 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-124">A non-word character.</span></span> <span data-ttu-id="aac68-125">입력 문자열의 문자는 단어 문자가 아닌 유니코드 범주에 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-125">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="aac68-126">자세한 내용은 [단어가 아닌 문자](#NonWordCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-126">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
- <span data-ttu-id="aac68-127">공백 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-127">A white-space character.</span></span> <span data-ttu-id="aac68-128">입력 문자열의 문자는 유니코드 구분 문자뿐만 아니라 많은 제어 문자 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-128">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="aac68-129">자세한 내용은 [공백 문자](#WhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-129">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="aac68-130">공백이 아닌 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-130">A non-white-space character.</span></span> <span data-ttu-id="aac68-131">입력 문자열의 문자는 공백 문자가 아닌 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-131">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="aac68-132">자세한 내용은 [공백이 아닌 문자](#NonWhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-132">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="aac68-133">10진수입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-133">A decimal digit.</span></span> <span data-ttu-id="aac68-134">입력 문자열의 문자는 유니코드 10진 자릿수로 분류된 모든 문자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-134">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="aac68-135">자세한 내용은 [10진수 숫자 문자](#DigitCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-135">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
- <span data-ttu-id="aac68-136">10진수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-136">A non-decimal digit.</span></span> <span data-ttu-id="aac68-137">입력 문자열의 문자는 유니코드 10진수 이외의 문자는 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-137">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="aac68-138">자세한 내용은 [10진수 숫자 문자](#NonDigitCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-138">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="aac68-139">.NET에서는 한 문자 클래스에서 다른 문자 클래스를 제외한 결과로 문자 집합을 정의하는 데 사용할 수 있는 문자 클래스 빼기 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-139">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="aac68-140">자세한 내용은 [문자 클래스 빼기](#CharacterClassSubtraction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-140">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aac68-141">일치하는 단어 문자를 검색하는 [\w](#WordCharacter) 또는 일치하는 유니코드 범주를 검색하는 [\p{}](#CategoryOrBlock)와 같이 범주별로 일치하는 문자를 검색하는 문자 클래스는 <xref:System.Globalization.CharUnicodeInfo> 클래스를 활용하여 문자 범주에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-141">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="aac68-142">.NET Framework 4.6.2부터, 문자 범주는 [유니코드 표준, 버전 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-142">Starting with the .NET Framework 4.6.2, character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="aac68-143">.NET Framework 4에서 .NET Framework 4.6.1까지는 [유니코드 표준, 버전 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-143">In the .NET Framework 4 through the .NET Framework 4.6.1, they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="aac68-144">긍정 문자 그룹: [ ]</span><span class="sxs-lookup"><span data-stu-id="aac68-144">Positive character group: [ ]</span></span>  
 <span data-ttu-id="aac68-145">긍정 문자 그룹은 일치 항목으로 간주되려면 입력 문자열에 나타날 수 있는 문자 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-145">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="aac68-146">이 문자 목록은 개별적으로, 범위로 또는 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-146">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="aac68-147">개별 문자 목록을 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-147">The syntax for specifying a list of individual characters is as follows:</span></span>  

`[*character_group*]`

 <span data-ttu-id="aac68-148">여기서 *character_group*은 일치가 성공하기 위해 입력 문자열에 나타날 수 있는 개별 문자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-148">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="aac68-149">*character_group*은 하나 이상의 리터럴 문자, [이스케이프 문자](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) 또는 문자 클래스로 이루어진 조합으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-149">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="aac68-150">문자의 범위를 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-150">The syntax for specifying a range of characters is as follows:</span></span>  
  
`[firstCharacter-lastCharacter]`  
  
 <span data-ttu-id="aac68-151">여기서 *firstCharacter*는 범위를 시작하는 문자이고 *lastCharacter*는 범위를 끝내는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-151">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="aac68-152">문자 범위는 일련의 문자로서, 문자 범위를 정의하려면 연속된 문자 중 첫 번째 문자와 마지막 문자를 하이픈(-)으로 연결하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-152">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="aac68-153">두 문자의 유니코드 코드 포인트가 연속되면 이 두 문자는 연속된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-153">Two characters are contiguous if they have adjacent Unicode code points.</span></span> <span data-ttu-id="aac68-154">*firstCharacter*는 낮은 코드 포인트를 가진 문자여야 하며 *lastCharacter*는 높은 코드 포인트를 가진 문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-154">*firstCharacter* must be the character with the lower code point, and *lastCharacter* must be the character with the higher code point.</span></span>

> [!NOTE]
> <span data-ttu-id="aac68-155">양수 문자 그룹에는 문자 세트와 문자 범위가 모두 포함될 수 있기 때문에, 하이픈 문자(`-`)는 그룹의 첫 번째 또는 마지막 문자가 아닌 한 항상 범위 구분 기호로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-155">Because a positive character group can include both a set of characters and a character range, a hyphen character (`-`) is always interpreted as the range separator unless it is the first or last character of the group.</span></span>

<span data-ttu-id="aac68-156">긍정 문자 클래스가 포함된 몇 가지 일반적인 정규식 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-156">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="aac68-157">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-157">Pattern</span></span>|<span data-ttu-id="aac68-158">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-158">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="aac68-159">모든 모음을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-159">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="aac68-160">모든 문장 부호 및 10진수 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-160">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="aac68-161">모든 공백 및 문장 부호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-161">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="aac68-162">다음 예제에서는 입력 문자열이 문자 "grey" 또는 "gray"에 이어 일치할 다른 일치 단어를 포함하도록 단어 "a"와 "e"가 포함된 긍정 문자 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-162">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="aac68-163">`gr[ae]y\s\S+?[\s|\p{P}]` 정규식은 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-163">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="aac68-164">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-164">Pattern</span></span>|<span data-ttu-id="aac68-165">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-165">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="aac68-166">리터럴 문자 "gr"을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-166">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="aac68-167">"a" 또는 "e"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-167">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="aac68-168">리터럴 문자 y 다음에 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-168">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="aac68-169">하나 이상의 공백이 아닌 문자이지만 가능한 적은 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-169">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="aac68-170">공백 문자 또는 문장 부호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-170">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="aac68-171">다음 예제에서는 모든 대문자로 시작하는 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-171">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="aac68-172">A-Z의 대문자로 범위를 나타내기 위해 `[A-Z]` 하위 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-172">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="aac68-173">`\b[A-Z]\w*\b` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-173">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-174">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-174">Pattern</span></span>|<span data-ttu-id="aac68-175">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-175">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="aac68-176">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-176">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="aac68-177">A-Z의 대문자를 모두 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-177">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="aac68-178">0개 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-178">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="aac68-179">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-179">Match a word boundary.</span></span>|  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="aac68-180">부정 문자 그룹: [^]</span><span class="sxs-lookup"><span data-stu-id="aac68-180">Negative character group: [^]</span></span>  
 <span data-ttu-id="aac68-181">부정 문자 그룹은 일치 항목으로 간주되려면 입력 문자열에 나타나서는 안 되는 문자 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-181">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="aac68-182">문자 목록은 개별적으로, 범위로 또는 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-182">The list of characters may be specified individually, as a range, or both.</span></span>  
  
<span data-ttu-id="aac68-183">개별 문자 목록을 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-183">The syntax for specifying a list of individual characters is as follows:</span></span>  

`[*^character_group*]`

 <span data-ttu-id="aac68-184">여기서 *character_group*은 일치가 성공하기 위해 입력 문자열에 나타날 수 없는 개별 문자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-184">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="aac68-185">*character_group*은 하나 이상의 리터럴 문자, [이스케이프 문자](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) 또는 문자 클래스로 이루어진 조합으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-185">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="aac68-186">문자의 범위를 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-186">The syntax for specifying a range of characters is as follows:</span></span>  

`[^*firstCharacter*-*lastCharacter*]`

<span data-ttu-id="aac68-187">여기서 *firstCharacter*는 범위를 시작하는 문자이고 *lastCharacter*는 범위를 끝내는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-187">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="aac68-188">문자 범위는 일련의 문자로서, 문자 범위를 정의하려면 연속된 문자 중 첫 번째 문자와 마지막 문자를 하이픈(-)으로 연결하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-188">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="aac68-189">두 문자의 유니코드 코드 포인트가 연속되면 이 두 문자는 연속된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-189">Two characters are contiguous if they have adjacent Unicode code points.</span></span> <span data-ttu-id="aac68-190">*firstCharacter*는 낮은 코드 포인트를 가진 문자여야 하며 *lastCharacter*는 높은 코드 포인트를 가진 문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-190">*firstCharacter* must be the character with the lower code point, and *lastCharacter* must be the character with the higher code point.</span></span>

> [!NOTE]
> <span data-ttu-id="aac68-191">음수 문자 그룹에는 문자 세트와 문자 범위가 모두 포함될 수 있기 때문에, 하이픈 문자(`-`)는 그룹의 첫 번째 또는 마지막 문자가 아닌 한 항상 범위 구분 기호로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-191">Because a negative character group can include both a set of characters and a character range, a hyphen character (`-`) is always interpreted as the range separator unless it is the first or last character of the group.</span></span>
  
 <span data-ttu-id="aac68-192">두 개 이상의 문자 범위를 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-192">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="aac68-193">예를 들어, "0"부터 "9"까지의 10진수 범위, "a"부터 "f"까지의 소문자 범위 및 "A"부터 "F"까지의 대문자 범위를 지정하려면 `[0-9a-fA-F]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-193">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="aac68-194">부정 문자 그룹에서 맨 앞의 캐럿 문자(`^`)는 필수 문자로서, 해당 문자 그룹이 긍정 문자 그룹이 아니라 부정 문자 그룹임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-194">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="aac68-195">큰 정규식 패턴에서 부정 문자 그룹은 너비가 0인 어설션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-195">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="aac68-196">즉, 부정 문자 그룹을 평가한 후 정규식 엔진은 입력 문자열에서 한 문자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-196">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="aac68-197">부정 문자 그룹이 포함된 몇 가지 일반적인 정규식 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-197">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="aac68-198">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-198">Pattern</span></span>|<span data-ttu-id="aac68-199">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-199">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="aac68-200">모음을 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-200">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="aac68-201">문장 부호 및 10진수 문자를 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-201">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="aac68-202">다음 예제에서는 "th" 문자로 시작하고 이어서 "o"가 나오지 않는 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-202">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="aac68-203">`\bth[^o]\w+\b` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-203">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-204">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-204">Pattern</span></span>|<span data-ttu-id="aac68-205">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-205">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="aac68-206">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-206">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="aac68-207">리터럴 문자 "th"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-207">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="aac68-208">"o"가 아닌 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-208">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="aac68-209">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-209">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="aac68-210">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-210">End at a word boundary.</span></span>|  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="aac68-211">임의의 문자: .</span><span class="sxs-lookup"><span data-stu-id="aac68-211">Any character: .</span></span>  
 <span data-ttu-id="aac68-212">마침표 문자(.)는 `\n`(줄바꿈 문자, \u000A)를 제외하고 다음 두 한정자가 있는 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-212">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
- <span data-ttu-id="aac68-213">정규식 패턴이 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 옵션에 의해 수정되거나 `.` 문자 클래스를 포함하는 패턴의 일부가 `s` 옵션에 의해 수정되는 경우 `.`가 문자를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-213">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="aac68-214">자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-214">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="aac68-215">다음 예제에서는 기본 및 `.` 옵션으로 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 문자 클래스의 다른 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-215">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="aac68-216">정규식 `^.+`는 문자열의 시작 부분에서 시작하여 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-216">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="aac68-217">기본적으로 일치는 첫 번째 줄의 끝 부분에서 끝납니다. 정규식 패턴은 캐리지 리턴 문자, `\r` 또는 \u000D와 일치하지만 `\n`과는 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-217">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="aac68-218"><xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 옵션은 전체 입력 문자열을 한 줄로 해석하기 때문에 `\n`을 포함하여 입력 문자열의 모든 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-218">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
> <span data-ttu-id="aac68-219">`\n`을 제외한 모든 문자와 일치하기 때문에 `.` 문자 클래스가 `\r`(캐리지 리턴 문자, \u000D)과도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-219">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
- <span data-ttu-id="aac68-220">긍정 또는 부정 문자 그룹의 마침표는 문자 클래스가 아니라 리터럴 마침표 문자로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-220">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="aac68-221">자세한 내용은 이 항목 앞부분의 [긍정 문자 그룹](#PositiveGroup) 및 [부정 문자 그룹](#NegativeGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-221">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="aac68-222">다음 예제는 문자 클래스와 긍정 문자 그룹으로 마침표 문자(`.`)를 포함하는 정규식을 정의하는 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-222">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="aac68-223">`\b.*[.?!;:](\s|\z)` 정규식은 단어 경계에서 시작하여 마침표를 포함하여 다섯 가지 문장 부호 중 하나와 만날 때까지 임의의 문자를 찾은 다음 공백 문자 또는 문자열 끝을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-223">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="aac68-224">모든 문자와 일치하기 때문에 `.` 언어 요소는 정규식 패턴이 여러 번 임의의 문자와 일치하도록 시도할 경우 종종 lazy 수량자와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-224">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="aac68-225">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-225">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="aac68-226">유니코드 범주 또는 유니코드 블록: \p{}</span><span class="sxs-lookup"><span data-stu-id="aac68-226">Unicode category or Unicode block: \p{}</span></span>  
 <span data-ttu-id="aac68-227">유니코드 표준에서는 각 문자를 일반 범주에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-227">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="aac68-228">예를 들어, 특정 문자는 대문자(`Lu` 범주로 표현), 10진수(`Nd` 범주), 수학 기호(`Sm` 범주) 또는 단락 구분 기호(`Zl` 범주)가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-228">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="aac68-229">유니코드 표준의 특정 문자 집합이 특정 범위 또는 연속된 코드 포인트의 블록도 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-229">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="aac68-230">예를 들어, 기본 라틴 문자 집합은 \u0000부터 \u007F까지에서 발견되고, 아랍어 문자 집합이 \u0600부터 \u06FF까지에서 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-230">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="aac68-231">정규식 만들기</span><span class="sxs-lookup"><span data-stu-id="aac68-231">The regular expression construct</span></span>  
  
 <span data-ttu-id="aac68-232">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="aac68-232">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="aac68-233">유니코드 일반 범주 또는 명명된 블록에 속하는 모든 문자를 찾습니다. 여기서 *name*은 범주 약어 또는 명명된 블록 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-233">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="aac68-234">범주 약어 목록은 이 항목의 뒷부분에 있는 [지원되는 유니코드 일반 범주](#SupportedUnicodeGeneralCategories) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-234">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="aac68-235">명명된 블록 목록은 이 항목의 뒷부분에 있는 [지원되는 명명된 블록](#SupportedNamedBlocks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-235">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="aac68-236">다음 예제에서는 `\p{`*name*`}` 구문을 사용하여 유니코드 일반 범주(이 경우 `Pd` 또는 문장 부호, 대시 범주) 및 명명된 블록(명명된 블록 `IsGreek` 및 `IsBasicLatin`)을 모두 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-236">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="aac68-237">`\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-237">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-238">무늬</span><span class="sxs-lookup"><span data-stu-id="aac68-238">Pattern</span></span>|<span data-ttu-id="aac68-239">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-239">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="aac68-240">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-240">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="aac68-241">둘 이상의 그리스어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-241">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="aac68-242">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-242">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="aac68-243">하나 이상의 그리스 문자 다음에 0개 또는 1개의 공백 문자가 한 번 이상 나타나는 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-243">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="aac68-244">문장 부호, 대시 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-244">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="aac68-245">공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-245">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="aac68-246">하나 이상의 기본 라틴 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-246">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="aac68-247">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-247">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="aac68-248">하나 이상의 기본 라틴 문자 다음에 0개 또는 1개의 공백 문자가 한 번 이상 나타나는 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-248">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="aac68-249">부정 유니코드 범주 또는 유니코드 블록: \P{}</span><span class="sxs-lookup"><span data-stu-id="aac68-249">Negative Unicode category or Unicode block: \P{}</span></span>  
 <span data-ttu-id="aac68-250">유니코드 표준에서는 각 문자를 일반 범주에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-250">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="aac68-251">예를 들어, 특정 문자는 대문자(`Lu` 범주로 표현), 10진수(`Nd` 범주), 수학 기호(`Sm` 범주) 또는 단락 구분 기호(`Zl` 범주)가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-251">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="aac68-252">유니코드 표준의 특정 문자 집합이 특정 범위 또는 연속된 코드 포인트의 블록도 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-252">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="aac68-253">예를 들어, 기본 라틴 문자 집합은 \u0000부터 \u007F까지에서 발견되고, 아랍어 문자 집합이 \u0600부터 \u06FF까지에서 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-253">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="aac68-254">정규식 만들기</span><span class="sxs-lookup"><span data-stu-id="aac68-254">The regular expression construct</span></span>  
  
 <span data-ttu-id="aac68-255">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="aac68-255">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="aac68-256">유니코드 일반 범주 또는 명명된 블록에 속하지 않는 모든 문자를 찾습니다. 여기서 *name*은 범주 약어 또는 명명된 블록 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-256">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="aac68-257">범주 약어 목록은 이 항목의 뒷부분에 있는 [지원되는 유니코드 일반 범주](#SupportedUnicodeGeneralCategories) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-257">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="aac68-258">명명된 블록 목록은 이 항목의 뒷부분에 있는 [지원되는 명명된 블록](#SupportedNamedBlocks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-258">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="aac68-259">다음 예제에서는 `\P{`*name*`}` 구문을 사용하여 숫자 문자열에서 모든 통화 기호(이 경우, `Sc` 또는 기호, 통화 범주)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-259">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="aac68-260">정규식 패턴 `(\P{Sc})+`는 통화 기호가 아닌 하나 이상의 문자를 찾습니다. 결과 문자열에서 모든 통화 기호를 효과적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-260">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="aac68-261">단어 문자: \w</span><span class="sxs-lookup"><span data-stu-id="aac68-261">Word character: \w</span></span>  
 <span data-ttu-id="aac68-262">`\w`는 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-262">`\w` matches any word character.</span></span> <span data-ttu-id="aac68-263">단어 문자는 다음 표에 나열된 유니코드 범주의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-263">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="aac68-264">범주</span><span class="sxs-lookup"><span data-stu-id="aac68-264">Category</span></span>|<span data-ttu-id="aac68-265">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-265">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="aac68-266">Ll</span><span class="sxs-lookup"><span data-stu-id="aac68-266">Ll</span></span>|<span data-ttu-id="aac68-267">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="aac68-267">Letter, Lowercase</span></span>|  
|<span data-ttu-id="aac68-268">Lu</span><span class="sxs-lookup"><span data-stu-id="aac68-268">Lu</span></span>|<span data-ttu-id="aac68-269">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="aac68-269">Letter, Uppercase</span></span>|  
|<span data-ttu-id="aac68-270">Lt</span><span class="sxs-lookup"><span data-stu-id="aac68-270">Lt</span></span>|<span data-ttu-id="aac68-271">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="aac68-271">Letter, Titlecase</span></span>|  
|<span data-ttu-id="aac68-272">Lo</span><span class="sxs-lookup"><span data-stu-id="aac68-272">Lo</span></span>|<span data-ttu-id="aac68-273">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-273">Letter, Other</span></span>|  
|<span data-ttu-id="aac68-274">Lm</span><span class="sxs-lookup"><span data-stu-id="aac68-274">Lm</span></span>|<span data-ttu-id="aac68-275">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="aac68-275">Letter, Modifier</span></span>|  
|<span data-ttu-id="aac68-276">Mn</span><span class="sxs-lookup"><span data-stu-id="aac68-276">Mn</span></span>|<span data-ttu-id="aac68-277">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="aac68-277">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="aac68-278">Nd</span><span class="sxs-lookup"><span data-stu-id="aac68-278">Nd</span></span>|<span data-ttu-id="aac68-279">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="aac68-279">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="aac68-280">Pc</span><span class="sxs-lookup"><span data-stu-id="aac68-280">Pc</span></span>|<span data-ttu-id="aac68-281">문장 부호, 연결자.</span><span class="sxs-lookup"><span data-stu-id="aac68-281">Punctuation, Connector.</span></span> <span data-ttu-id="aac68-282">이 범주는 가장 일반적으로 사용되는 LOWLINE 문자 (_), U + 005F인 10개의 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-282">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="aac68-283">ECMAScript와 호환되는 동작을 지정한 경우 `\w`는 `[a-zA-Z_0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-283">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="aac68-284">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-284">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aac68-285">모든 단어 문자와 일치하기 때문에 `\w` 언어 요소는 정규식 패턴이 특정 단어 문자가 따라오는 임의의 단어 문자를 여러 번 찾으려 하는 경우 lazy 수량자와 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-285">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="aac68-286">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-286">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="aac68-287">다음 예제에서는 `\w` 언어 요소를 사용하여 단어의 중복 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-287">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="aac68-288">예제는 다음과 같이 해석될 수 있는 정규식 패턴 `(\w)\1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-288">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="aac68-289">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-289">Element</span></span>|<span data-ttu-id="aac68-290">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-290">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aac68-291">(\w)</span><span class="sxs-lookup"><span data-stu-id="aac68-291">(\w)</span></span>|<span data-ttu-id="aac68-292">단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-292">Match a word character.</span></span> <span data-ttu-id="aac68-293">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-293">This is the first capturing group.</span></span>|  
|<span data-ttu-id="aac68-294">\1</span><span class="sxs-lookup"><span data-stu-id="aac68-294">\1</span></span>|<span data-ttu-id="aac68-295">첫 번째 캡처의 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-295">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="aac68-296">단어가 아닌 문자: \W</span><span class="sxs-lookup"><span data-stu-id="aac68-296">Non-word character: \W</span></span>  
 <span data-ttu-id="aac68-297">`\W`는 비단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-297">`\W` matches any non-word character.</span></span> <span data-ttu-id="aac68-298">\W 언어 요소는 다음 문자 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-298">The \W language element is equivalent to the following character class:</span></span>  
  
`[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]`  
  
 <span data-ttu-id="aac68-299">즉, 다음 표에 나열된 유니코드 범주의 문자를 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-299">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="aac68-300">범주</span><span class="sxs-lookup"><span data-stu-id="aac68-300">Category</span></span>|<span data-ttu-id="aac68-301">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-301">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="aac68-302">Ll</span><span class="sxs-lookup"><span data-stu-id="aac68-302">Ll</span></span>|<span data-ttu-id="aac68-303">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="aac68-303">Letter, Lowercase</span></span>|  
|<span data-ttu-id="aac68-304">Lu</span><span class="sxs-lookup"><span data-stu-id="aac68-304">Lu</span></span>|<span data-ttu-id="aac68-305">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="aac68-305">Letter, Uppercase</span></span>|  
|<span data-ttu-id="aac68-306">Lt</span><span class="sxs-lookup"><span data-stu-id="aac68-306">Lt</span></span>|<span data-ttu-id="aac68-307">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="aac68-307">Letter, Titlecase</span></span>|  
|<span data-ttu-id="aac68-308">Lo</span><span class="sxs-lookup"><span data-stu-id="aac68-308">Lo</span></span>|<span data-ttu-id="aac68-309">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-309">Letter, Other</span></span>|  
|<span data-ttu-id="aac68-310">Lm</span><span class="sxs-lookup"><span data-stu-id="aac68-310">Lm</span></span>|<span data-ttu-id="aac68-311">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="aac68-311">Letter, Modifier</span></span>|  
|<span data-ttu-id="aac68-312">Mn</span><span class="sxs-lookup"><span data-stu-id="aac68-312">Mn</span></span>|<span data-ttu-id="aac68-313">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="aac68-313">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="aac68-314">Nd</span><span class="sxs-lookup"><span data-stu-id="aac68-314">Nd</span></span>|<span data-ttu-id="aac68-315">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="aac68-315">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="aac68-316">Pc</span><span class="sxs-lookup"><span data-stu-id="aac68-316">Pc</span></span>|<span data-ttu-id="aac68-317">문장 부호, 연결자.</span><span class="sxs-lookup"><span data-stu-id="aac68-317">Punctuation, Connector.</span></span> <span data-ttu-id="aac68-318">이 범주는 가장 일반적으로 사용되는 LOWLINE 문자 (_), U + 005F인 10개의 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-318">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="aac68-319">ECMAScript와 호환되는 동작을 지정한 경우 `\W`는 `[^a-zA-Z_0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-319">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="aac68-320">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-320">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aac68-321">모든 비단어 문자와 일치하기 때문에 `\W` 언어 요소는 정규식 패턴이 특정 비단어 문자가 따라오는 임의의 비단어 문자를 여러 번 찾으려 하는 경우 lazy 수량자와 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-321">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="aac68-322">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-322">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="aac68-323">다음 예제에서는 `\W` 문자 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-323">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="aac68-324">공백 또는 문장 부호와 같은 한두 개의 비단어 문자가 따라오는 단어와 일치하는 정규식 패턴 `\b(\w+)(\W){1,2}`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-324">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="aac68-325">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-325">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-326">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-326">Element</span></span>|<span data-ttu-id="aac68-327">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-327">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aac68-328">\b</span><span class="sxs-lookup"><span data-stu-id="aac68-328">\b</span></span>|<span data-ttu-id="aac68-329">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-329">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="aac68-330">(\w+)</span><span class="sxs-lookup"><span data-stu-id="aac68-330">(\w+)</span></span>|<span data-ttu-id="aac68-331">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-331">Match one or more word characters.</span></span> <span data-ttu-id="aac68-332">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-332">This is the first capturing group.</span></span>|  
|<span data-ttu-id="aac68-333">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="aac68-333">(\W){1,2}</span></span>|<span data-ttu-id="aac68-334">단어가 아닌 문자를 한 개 또는 두 개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-334">Match a non-word character either one or two times.</span></span> <span data-ttu-id="aac68-335">이 그룹은 두 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-335">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="aac68-336">두 번째 캡처링 그룹의 <xref:System.Text.RegularExpressions.Group> 개체가 단일 캡처된 비단어 문자만 포함하기 때문에 예제에서는 <xref:System.Text.RegularExpressions.CaptureCollection> 속성에 의해 반환되는 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 개체에서 모든 캡처된 비단어 문자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-336">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
<a name="WhitespaceCharacter"></a>   
## <a name="whitespace-character-s"></a><span data-ttu-id="aac68-337">공백 문자: \s</span><span class="sxs-lookup"><span data-stu-id="aac68-337">Whitespace character: \s</span></span>  
 <span data-ttu-id="aac68-338">`\s`는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-338">`\s` matches any whitespace character.</span></span> <span data-ttu-id="aac68-339">다음 표에 나열된 이스케이프 시퀀스 및 유니코드 범주와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-339">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="aac68-340">범주</span><span class="sxs-lookup"><span data-stu-id="aac68-340">Category</span></span>|<span data-ttu-id="aac68-341">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-341">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="aac68-342">용지 공급 문자, \u000C.</span><span class="sxs-lookup"><span data-stu-id="aac68-342">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="aac68-343">줄 바꿈 문자, \u000A.</span><span class="sxs-lookup"><span data-stu-id="aac68-343">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="aac68-344">캐리지 리턴 문자 \u000D입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-344">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="aac68-345">탭 문자, \u0009.</span><span class="sxs-lookup"><span data-stu-id="aac68-345">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="aac68-346">세로 탭 문자, \u000B.</span><span class="sxs-lookup"><span data-stu-id="aac68-346">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="aac68-347">줄임표 또는 NEXT LINE (NEL) 문자 (…), \u0085.</span><span class="sxs-lookup"><span data-stu-id="aac68-347">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="aac68-348">임의의 구분 기호 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-348">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="aac68-349">ECMAScript와 호환되는 동작을 지정한 경우 `\s`는 `[ \f\n\r\t\v]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-349">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="aac68-350">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-350">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="aac68-351">다음 예제에서는 `\s` 문자 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-351">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="aac68-352">"s" 또는 "es"로 끝나고 그 뒤에 공백 문자나 입력 문자열의 끝이 있는 단어와 일치하는 정규식 패턴 `\b\w+(e)?s(\s|$)`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-352">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="aac68-353">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-353">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-354">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-354">Element</span></span>|<span data-ttu-id="aac68-355">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-355">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aac68-356">\b</span><span class="sxs-lookup"><span data-stu-id="aac68-356">\b</span></span>|<span data-ttu-id="aac68-357">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-357">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="aac68-358">\w+</span><span class="sxs-lookup"><span data-stu-id="aac68-358">\w+</span></span>|<span data-ttu-id="aac68-359">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-359">Match one or more word characters.</span></span>|  
|<span data-ttu-id="aac68-360">(e)?</span><span class="sxs-lookup"><span data-stu-id="aac68-360">(e)?</span></span>|<span data-ttu-id="aac68-361">"e"를 0개 또는 한 개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-361">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="aac68-362">초</span><span class="sxs-lookup"><span data-stu-id="aac68-362">s</span></span>|<span data-ttu-id="aac68-363">"s"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-363">Match an "s".</span></span>|  
|<span data-ttu-id="aac68-364">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="aac68-364">(\s&#124;$)</span></span>|<span data-ttu-id="aac68-365">공백 문자 또는 입력 문자열의 끝을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-365">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-whitespace-character-s"></a><span data-ttu-id="aac68-366">공백이 아닌 문자: \S</span><span class="sxs-lookup"><span data-stu-id="aac68-366">Non-whitespace character: \S</span></span>  
 <span data-ttu-id="aac68-367">`\S`는 공백 문자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-367">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="aac68-368">`[^\f\n\r\t\v\x85\p{Z}]` 정규식 패턴과 동일하거나, 공백 문자와 일치하는 `\s`과 동일한 정규식 패턴의 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-368">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="aac68-369">자세한 내용은 [공백 문자: \s](#WhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-369">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="aac68-370">ECMAScript와 호환되는 동작을 지정한 경우 `\S`는 `[^ \f\n\r\t\v]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-370">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="aac68-371">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-371">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="aac68-372">다음 예제에서는 `\S` 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-372">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="aac68-373">정규식 패턴 `\b(\S+)\s?`는 공백 문자로 구분된 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-373">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="aac68-374">일치 <xref:System.Text.RegularExpressions.GroupCollection> 개체의 두 번째 요소는 일치하는 문자열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-374">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="aac68-375">정규식은 다음 표에 나와 있는 것처럼 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-375">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-376">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-376">Element</span></span>|<span data-ttu-id="aac68-377">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-377">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="aac68-378">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-378">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="aac68-379">공백이 아닌 문자를 하나 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-379">Match one or more non-white-space characters.</span></span> <span data-ttu-id="aac68-380">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-380">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="aac68-381">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-381">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="aac68-382">10진수 문자: \d</span><span class="sxs-lookup"><span data-stu-id="aac68-382">Decimal digit character: \d</span></span>  
 <span data-ttu-id="aac68-383">`\d`는 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-383">`\d` matches any decimal digit.</span></span> <span data-ttu-id="aac68-384">많은 다른 문자 집합의 10진수뿐만 아니라 표준 10진수 0-9를 포함하는 `\p{Nd}` 정규식 패턴과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-384">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="aac68-385">ECMAScript와 호환되는 동작을 지정한 경우 `\d`는 `[0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-385">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="aac68-386">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-386">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="aac68-387">다음 예제에서는 `\d` 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-387">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="aac68-388">입력 문자열이 미국 및 캐나다의 올바른 전화 번호를 나타내는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-388">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="aac68-389">정규식 패턴 `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` 는 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-389">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-390">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-390">Element</span></span>|<span data-ttu-id="aac68-391">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-391">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="aac68-392">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-392">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="aac68-393">0개 또는 한 개의 리터럴 "(" 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-393">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="aac68-394">세 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-394">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="aac68-395">0개 또는 한 개의 리터럴 ")" 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-395">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="aac68-396">하이픈 또는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-396">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="aac68-397">옵션 여는 괄호에 이어 세 개의 10진수, 옵션 닫는 괄호 및 공백 문자나 하이픈 0개 또는 1개를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-397">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="aac68-398">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-398">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="aac68-399">세 개의 10진수, 하이픈, 네 개 이상의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-399">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="aac68-400">입력 문자열의 끝 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-400">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="aac68-401">숫자가 아닌 문자: \D</span><span class="sxs-lookup"><span data-stu-id="aac68-401">Non-digit character: \D</span></span>  
 <span data-ttu-id="aac68-402">`\D`는 숫자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-402">`\D` matches any non-digit character.</span></span> <span data-ttu-id="aac68-403">`\P{Nd}` 정규식 패턴과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-403">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="aac68-404">ECMAScript와 호환되는 동작을 지정한 경우 `\D`는 `[^0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-404">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="aac68-405">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-405">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="aac68-406">다음 예제에서는 \D 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-406">The following example illustrates the \D language element.</span></span> <span data-ttu-id="aac68-407">부품 번호 같은 문자열이 10진수 문자 및 10진수가 아닌 문자의 적절한 조합으로 구성되어 있는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-407">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="aac68-408">정규식 패턴 `^\D\d{1,5}\D*$` 는 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-408">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-409">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-409">Element</span></span>|<span data-ttu-id="aac68-410">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-410">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="aac68-411">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-411">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="aac68-412">숫자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-412">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="aac68-413">1~5의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-413">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="aac68-414">0개 또는 하나 이상의 10진수가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-414">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="aac68-415">입력 문자열의 끝 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-415">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="aac68-416">지원되는 유니코드 일반 범주</span><span class="sxs-lookup"><span data-stu-id="aac68-416">Supported Unicode general categories</span></span>  
 <span data-ttu-id="aac68-417">유니코드는 다음 표에 나와 있는 일반 범주를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-417">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="aac68-418">자세한 내용은 [유니코드 문자 데이터베이스](https://www.unicode.org/reports/tr44/)의 하위 항목인 "UCD 파일 형식"과 "일반 범주 값"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-418">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="aac68-419">범주</span><span class="sxs-lookup"><span data-stu-id="aac68-419">Category</span></span>|<span data-ttu-id="aac68-420">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-420">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="aac68-421">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="aac68-421">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="aac68-422">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="aac68-422">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="aac68-423">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="aac68-423">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="aac68-424">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="aac68-424">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="aac68-425">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-425">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="aac68-426">모든 문자</span><span class="sxs-lookup"><span data-stu-id="aac68-426">All letter characters.</span></span> <span data-ttu-id="aac68-427">여기에는 `Lu`, `Ll`, `Lt`, `Lm` 및 `Lo` 문자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-427">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="aac68-428">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="aac68-428">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="aac68-429">표시, 공백 조합</span><span class="sxs-lookup"><span data-stu-id="aac68-429">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="aac68-430">표시, 묶기</span><span class="sxs-lookup"><span data-stu-id="aac68-430">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="aac68-431">모든 분음 기호</span><span class="sxs-lookup"><span data-stu-id="aac68-431">All diacritic marks.</span></span> <span data-ttu-id="aac68-432">여기에는 `Mn`, `Mc` 및 `Me` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-432">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="aac68-433">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="aac68-433">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="aac68-434">숫자, 문자</span><span class="sxs-lookup"><span data-stu-id="aac68-434">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="aac68-435">숫자, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-435">Number, Other</span></span>|  
|`N`|<span data-ttu-id="aac68-436">모든 숫자.</span><span class="sxs-lookup"><span data-stu-id="aac68-436">All numbers.</span></span> <span data-ttu-id="aac68-437">여기에는 `Nd`, `Nl` 및 `No` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-437">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="aac68-438">문장 부호, 연결자</span><span class="sxs-lookup"><span data-stu-id="aac68-438">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="aac68-439">문장 부호, 대시</span><span class="sxs-lookup"><span data-stu-id="aac68-439">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="aac68-440">문장 부호, 열기</span><span class="sxs-lookup"><span data-stu-id="aac68-440">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="aac68-441">문장 부호, 닫기</span><span class="sxs-lookup"><span data-stu-id="aac68-441">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="aac68-442">문장 부호, 처음 따옴표(사용 방식에 따라 Ps 또는 Pe와 같이 동작)</span><span class="sxs-lookup"><span data-stu-id="aac68-442">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="aac68-443">문장 부호, 마지막 따옴표(사용 방식에 따라 Ps 또는 Pe와 같이 동작)</span><span class="sxs-lookup"><span data-stu-id="aac68-443">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="aac68-444">문장 부호, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-444">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="aac68-445">모든 구두점 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-445">All punctuation characters.</span></span> <span data-ttu-id="aac68-446">여기에는 `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf` 및 `Po` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-446">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="aac68-447">기호, 수학</span><span class="sxs-lookup"><span data-stu-id="aac68-447">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="aac68-448">기호, 통화</span><span class="sxs-lookup"><span data-stu-id="aac68-448">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="aac68-449">기호, 한정자</span><span class="sxs-lookup"><span data-stu-id="aac68-449">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="aac68-450">기호, 기타</span><span class="sxs-lookup"><span data-stu-id="aac68-450">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="aac68-451">모든 기호.</span><span class="sxs-lookup"><span data-stu-id="aac68-451">All symbols.</span></span> <span data-ttu-id="aac68-452">여기에는 `Sm`, `Sc`, `Sk` 및 `So` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-452">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="aac68-453">구분 기호, 공백</span><span class="sxs-lookup"><span data-stu-id="aac68-453">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="aac68-454">구분 기호, 줄</span><span class="sxs-lookup"><span data-stu-id="aac68-454">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="aac68-455">구분 기호, 단락</span><span class="sxs-lookup"><span data-stu-id="aac68-455">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="aac68-456">모든 구분 기호 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-456">All separator characters.</span></span> <span data-ttu-id="aac68-457">여기에는 `Zs`, `Zl` 및 `Zp` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-457">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="aac68-458">기타, 제어</span><span class="sxs-lookup"><span data-stu-id="aac68-458">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="aac68-459">기타, 서식</span><span class="sxs-lookup"><span data-stu-id="aac68-459">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="aac68-460">기타, 서로게이트</span><span class="sxs-lookup"><span data-stu-id="aac68-460">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="aac68-461">기타, 전용 항목</span><span class="sxs-lookup"><span data-stu-id="aac68-461">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="aac68-462">기타, 지정되지 않음(이 속성을 가진 문자가 없음)</span><span class="sxs-lookup"><span data-stu-id="aac68-462">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="aac68-463">모든 제어 문자.</span><span class="sxs-lookup"><span data-stu-id="aac68-463">All control characters.</span></span> <span data-ttu-id="aac68-464">여기에는 `Cc`, `Cf`, `Cs`, `Co` 및 `Cn` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-464">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="aac68-465">해당 문자를 <xref:System.Char.GetUnicodeCategory%2A> 메서드로 전달하여 특정 문자의 유니코드 범주를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-465">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="aac68-466">다음 예제에서는 <xref:System.Char.GetUnicodeCategory%2A> 메서드를 사용하여 선택한 라틴 문자를 포함하는 배열에서 각 요소의 범주를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-466">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="aac68-467">지원되는 명명된 블록</span><span class="sxs-lookup"><span data-stu-id="aac68-467">Supported named blocks</span></span>

<span data-ttu-id="aac68-468">.NET에서는 다음 표에 나와 있는 명명된 블록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-468">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="aac68-469">지원되는 명명된 블록 집합은 유니코드 4.0 및 Perl 5.6을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-469">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span> <span data-ttu-id="aac68-470">명명된 블록을 사용하는 정규식에 대해서는 [유니코드 범주 또는 유니코드 블록: \\p{}](#unicode-category-or-unicode-block-p) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-470">For a regular expression that uses named blocks, see the [Unicode category or Unicode block: \\p{}](#unicode-category-or-unicode-block-p) section.</span></span>  
  
|<span data-ttu-id="aac68-471">코드 포인트 범위</span><span class="sxs-lookup"><span data-stu-id="aac68-471">Code point range</span></span>|<span data-ttu-id="aac68-472">블록 이름</span><span class="sxs-lookup"><span data-stu-id="aac68-472">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="aac68-473">0000 - 007F</span><span class="sxs-lookup"><span data-stu-id="aac68-473">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="aac68-474">0080 - 00FF</span><span class="sxs-lookup"><span data-stu-id="aac68-474">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="aac68-475">0100 - 017F</span><span class="sxs-lookup"><span data-stu-id="aac68-475">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="aac68-476">0180 - 024F</span><span class="sxs-lookup"><span data-stu-id="aac68-476">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="aac68-477">0250 - 02AF</span><span class="sxs-lookup"><span data-stu-id="aac68-477">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="aac68-478">02B0 - 02FF</span><span class="sxs-lookup"><span data-stu-id="aac68-478">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="aac68-479">0300 - 036F</span><span class="sxs-lookup"><span data-stu-id="aac68-479">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="aac68-480">0370 - 03FF</span><span class="sxs-lookup"><span data-stu-id="aac68-480">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="aac68-481">또는</span><span class="sxs-lookup"><span data-stu-id="aac68-481">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="aac68-482">0400 - 04FF</span><span class="sxs-lookup"><span data-stu-id="aac68-482">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="aac68-483">0500 - 052F</span><span class="sxs-lookup"><span data-stu-id="aac68-483">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="aac68-484">0530 - 058F</span><span class="sxs-lookup"><span data-stu-id="aac68-484">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="aac68-485">0590 - 05FF</span><span class="sxs-lookup"><span data-stu-id="aac68-485">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="aac68-486">0600 - 06FF</span><span class="sxs-lookup"><span data-stu-id="aac68-486">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="aac68-487">0700 - 074F</span><span class="sxs-lookup"><span data-stu-id="aac68-487">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="aac68-488">0780 - 07BF</span><span class="sxs-lookup"><span data-stu-id="aac68-488">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="aac68-489">0900 - 097F</span><span class="sxs-lookup"><span data-stu-id="aac68-489">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="aac68-490">0980 - 09FF</span><span class="sxs-lookup"><span data-stu-id="aac68-490">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="aac68-491">0A00 - 0A7F</span><span class="sxs-lookup"><span data-stu-id="aac68-491">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="aac68-492">0A80 - 0AFF</span><span class="sxs-lookup"><span data-stu-id="aac68-492">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="aac68-493">0B00 - 0B7F</span><span class="sxs-lookup"><span data-stu-id="aac68-493">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="aac68-494">0B80 - 0BFF</span><span class="sxs-lookup"><span data-stu-id="aac68-494">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="aac68-495">0C00 - 0C7F</span><span class="sxs-lookup"><span data-stu-id="aac68-495">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="aac68-496">0C80 - 0CFF</span><span class="sxs-lookup"><span data-stu-id="aac68-496">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="aac68-497">0D00 - 0D7F</span><span class="sxs-lookup"><span data-stu-id="aac68-497">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="aac68-498">0D80 - 0DFF</span><span class="sxs-lookup"><span data-stu-id="aac68-498">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="aac68-499">0E00 - 0E7F</span><span class="sxs-lookup"><span data-stu-id="aac68-499">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="aac68-500">0E80 - 0EFF</span><span class="sxs-lookup"><span data-stu-id="aac68-500">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="aac68-501">0F00 - 0FFF</span><span class="sxs-lookup"><span data-stu-id="aac68-501">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="aac68-502">1000 - 109F</span><span class="sxs-lookup"><span data-stu-id="aac68-502">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="aac68-503">10A0 - 10FF</span><span class="sxs-lookup"><span data-stu-id="aac68-503">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="aac68-504">1100 - 11FF</span><span class="sxs-lookup"><span data-stu-id="aac68-504">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="aac68-505">1200 - 137F</span><span class="sxs-lookup"><span data-stu-id="aac68-505">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="aac68-506">13A0 - 13FF</span><span class="sxs-lookup"><span data-stu-id="aac68-506">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="aac68-507">1400 - 167F</span><span class="sxs-lookup"><span data-stu-id="aac68-507">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="aac68-508">1680 - 169F</span><span class="sxs-lookup"><span data-stu-id="aac68-508">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="aac68-509">16A0 - 16FF</span><span class="sxs-lookup"><span data-stu-id="aac68-509">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="aac68-510">1700 - 171F</span><span class="sxs-lookup"><span data-stu-id="aac68-510">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="aac68-511">1720 - 173F</span><span class="sxs-lookup"><span data-stu-id="aac68-511">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="aac68-512">1740 - 175F</span><span class="sxs-lookup"><span data-stu-id="aac68-512">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="aac68-513">1760 - 177F</span><span class="sxs-lookup"><span data-stu-id="aac68-513">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="aac68-514">1780 - 17FF</span><span class="sxs-lookup"><span data-stu-id="aac68-514">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="aac68-515">1800 - 18AF</span><span class="sxs-lookup"><span data-stu-id="aac68-515">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="aac68-516">1900 - 194F</span><span class="sxs-lookup"><span data-stu-id="aac68-516">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="aac68-517">1950 - 197F</span><span class="sxs-lookup"><span data-stu-id="aac68-517">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="aac68-518">19E0 - 19FF</span><span class="sxs-lookup"><span data-stu-id="aac68-518">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="aac68-519">1D00 - 1D7F</span><span class="sxs-lookup"><span data-stu-id="aac68-519">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="aac68-520">1E00 - 1EFF</span><span class="sxs-lookup"><span data-stu-id="aac68-520">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="aac68-521">1F00 - 1FFF</span><span class="sxs-lookup"><span data-stu-id="aac68-521">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="aac68-522">2000 - 206F</span><span class="sxs-lookup"><span data-stu-id="aac68-522">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="aac68-523">2070 - 209F</span><span class="sxs-lookup"><span data-stu-id="aac68-523">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="aac68-524">20A0 - 20CF</span><span class="sxs-lookup"><span data-stu-id="aac68-524">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="aac68-525">20D0 - 20FF</span><span class="sxs-lookup"><span data-stu-id="aac68-525">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="aac68-526">또는</span><span class="sxs-lookup"><span data-stu-id="aac68-526">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="aac68-527">2100 - 214F</span><span class="sxs-lookup"><span data-stu-id="aac68-527">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="aac68-528">2150 - 218F</span><span class="sxs-lookup"><span data-stu-id="aac68-528">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="aac68-529">2190 - 21FF</span><span class="sxs-lookup"><span data-stu-id="aac68-529">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="aac68-530">2200 - 22FF</span><span class="sxs-lookup"><span data-stu-id="aac68-530">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="aac68-531">2300 - 23FF</span><span class="sxs-lookup"><span data-stu-id="aac68-531">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="aac68-532">2400 - 243F</span><span class="sxs-lookup"><span data-stu-id="aac68-532">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="aac68-533">2440 - 245F</span><span class="sxs-lookup"><span data-stu-id="aac68-533">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="aac68-534">2460 - 24FF</span><span class="sxs-lookup"><span data-stu-id="aac68-534">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="aac68-535">2500 - 257F</span><span class="sxs-lookup"><span data-stu-id="aac68-535">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="aac68-536">2580 - 259F</span><span class="sxs-lookup"><span data-stu-id="aac68-536">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="aac68-537">25A0 - 25FF</span><span class="sxs-lookup"><span data-stu-id="aac68-537">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="aac68-538">2600 - 26FF</span><span class="sxs-lookup"><span data-stu-id="aac68-538">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="aac68-539">2700 - 27BF</span><span class="sxs-lookup"><span data-stu-id="aac68-539">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="aac68-540">27C0 - 27EF</span><span class="sxs-lookup"><span data-stu-id="aac68-540">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="aac68-541">27F0 - 27FF</span><span class="sxs-lookup"><span data-stu-id="aac68-541">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="aac68-542">2800 - 28FF</span><span class="sxs-lookup"><span data-stu-id="aac68-542">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="aac68-543">2900 - 297F</span><span class="sxs-lookup"><span data-stu-id="aac68-543">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="aac68-544">2980 - 29FF</span><span class="sxs-lookup"><span data-stu-id="aac68-544">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="aac68-545">2A00 - 2AFF</span><span class="sxs-lookup"><span data-stu-id="aac68-545">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="aac68-546">2B00 - 2BFF</span><span class="sxs-lookup"><span data-stu-id="aac68-546">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="aac68-547">2E80 - 2EFF</span><span class="sxs-lookup"><span data-stu-id="aac68-547">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="aac68-548">2F00 - 2FDF</span><span class="sxs-lookup"><span data-stu-id="aac68-548">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="aac68-549">2FF0 - 2FFF</span><span class="sxs-lookup"><span data-stu-id="aac68-549">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="aac68-550">3000 - 303F</span><span class="sxs-lookup"><span data-stu-id="aac68-550">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="aac68-551">3040 - 309F</span><span class="sxs-lookup"><span data-stu-id="aac68-551">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="aac68-552">30A0 - 30FF</span><span class="sxs-lookup"><span data-stu-id="aac68-552">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="aac68-553">3100 - 312F</span><span class="sxs-lookup"><span data-stu-id="aac68-553">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="aac68-554">3130 - 318F</span><span class="sxs-lookup"><span data-stu-id="aac68-554">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="aac68-555">3190 - 319F</span><span class="sxs-lookup"><span data-stu-id="aac68-555">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="aac68-556">31A0 - 31BF</span><span class="sxs-lookup"><span data-stu-id="aac68-556">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="aac68-557">31F0 - 31FF</span><span class="sxs-lookup"><span data-stu-id="aac68-557">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="aac68-558">3200 - 32FF</span><span class="sxs-lookup"><span data-stu-id="aac68-558">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="aac68-559">3300 - 33FF</span><span class="sxs-lookup"><span data-stu-id="aac68-559">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="aac68-560">3400 - 4DBF</span><span class="sxs-lookup"><span data-stu-id="aac68-560">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="aac68-561">4DC0 - 4DFF</span><span class="sxs-lookup"><span data-stu-id="aac68-561">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="aac68-562">4E00 - 9FFF</span><span class="sxs-lookup"><span data-stu-id="aac68-562">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="aac68-563">A000 - A48F</span><span class="sxs-lookup"><span data-stu-id="aac68-563">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="aac68-564">A490 - A4CF</span><span class="sxs-lookup"><span data-stu-id="aac68-564">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="aac68-565">AC00 - D7AF</span><span class="sxs-lookup"><span data-stu-id="aac68-565">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="aac68-566">D800 - DB7F</span><span class="sxs-lookup"><span data-stu-id="aac68-566">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="aac68-567">DB80 - DBFF</span><span class="sxs-lookup"><span data-stu-id="aac68-567">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="aac68-568">DC00 - DFFF</span><span class="sxs-lookup"><span data-stu-id="aac68-568">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="aac68-569">E000 - F8FF</span><span class="sxs-lookup"><span data-stu-id="aac68-569">E000 - F8FF</span></span>|<span data-ttu-id="aac68-570">`IsPrivateUse` 또는 `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="aac68-570">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="aac68-571">F900 - FAFF</span><span class="sxs-lookup"><span data-stu-id="aac68-571">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="aac68-572">FB00 - FB4F</span><span class="sxs-lookup"><span data-stu-id="aac68-572">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="aac68-573">FB50 - FDFF</span><span class="sxs-lookup"><span data-stu-id="aac68-573">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="aac68-574">FE00 - FE0F</span><span class="sxs-lookup"><span data-stu-id="aac68-574">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="aac68-575">FE20 - FE2F</span><span class="sxs-lookup"><span data-stu-id="aac68-575">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="aac68-576">FE30 - FE4F</span><span class="sxs-lookup"><span data-stu-id="aac68-576">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="aac68-577">FE50 - FE6F</span><span class="sxs-lookup"><span data-stu-id="aac68-577">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="aac68-578">FE70 - FEFF</span><span class="sxs-lookup"><span data-stu-id="aac68-578">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="aac68-579">FF00 - FFEF</span><span class="sxs-lookup"><span data-stu-id="aac68-579">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="aac68-580">FFF0 - FFFF</span><span class="sxs-lookup"><span data-stu-id="aac68-580">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-base_group---excluded_group"></a><span data-ttu-id="aac68-581">문자 클래스 빼기: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="aac68-581">Character class subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="aac68-582">문자 클래스는 문자 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-582">A character class defines a set of characters.</span></span> <span data-ttu-id="aac68-583">문자 클래스 빼기는 한 문자 클래스에서 다른 문자 클래스의 문자를 제외한 결과로 문자 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-583">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="aac68-584">문자 클래스 빼기 식의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-584">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="aac68-585">`[` *base_group* `-[` *excluded_group* `]]`</span><span class="sxs-lookup"><span data-stu-id="aac68-585">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="aac68-586">대괄호(`[]`)와 하이픈(`-`)은 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-586">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="aac68-587">*base_group*은 [긍정 문자 그룹](#PositiveGroup) 또는 [부정 문자 그룹](#NegativeGroup)입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-587">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="aac68-588">*excluded_group* 구성 요소는 다른 긍정 또는 부정 문자 그룹이거나 다른 문자 클래스 빼기 식입니다. 즉, 문자 클래스 빼기 식을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-588">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="aac68-589">예를 들어, "a"부터 "z"까지의 문자 범위로 구성된 기본 그룹이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-589">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="aac68-590">문자 "m"을 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[m]]`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-590">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="aac68-591">문자 "d", "j" 및 "p"를 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[djp]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-591">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="aac68-592">"m"부터 "p"까지의 문자 범위를 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[m-p]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-592">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="aac68-593">중첩된 문자 클래스 빼기 식인 `[a-z-[d-w-[m-o]]]`를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-593">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="aac68-594">가장 안쪽 문자 범위에서 바깥쪽으로 식이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-594">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="aac68-595">먼저 'd'부터 'w'까지의 문자 범위에서 "m"부터 "o"까지의 문자 범위를 뺍니다. 그러면 "d"부터 "l"까지와 "p"부터 "w"까지의 문자로 구성된 문자 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-595">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="aac68-596">그런 다음 "a"부터 "z"까지의 문자 범위에서 이 집합을 뺍니다. 그러면 문자 집합 `[abcmnoxyz]`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-596">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="aac68-597">모든 문자 클래스에 문자 클래스 빼기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-597">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="aac68-598">\u0000부터 \uFFFF까지의 문자에서 공백 문자(`\s`), 문장 부호 일반 범주의 문자(`\p{P}`), 명명된 블록 `IsGreek`의 문자(`\p{IsGreek}`) 및 유니코드 NEXT LINE 제어 문자(\x85)를 제외한 모든 유니코드 문자로 구성된 문자 집합을 정의하려면 `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-598">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="aac68-599">문자 클래스 빼기 식에 사용할 문자 클래스를 선택할 때는 유용한 결과를 생성할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-599">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="aac68-600">어떤 문자도 나타낼 수 없는 빈 문자 집합을 생성하는 식이나 원래 기본 그룹에 해당하는 식은 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-600">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="aac68-601">예를 들어, `IsBasicLatin` 일반 범주에서 `IsBasicLatin` 문자 범위의 모든 문자를 빼는 `[\p{IsBasicLatin}-[\x00-\x7F]]` 식을 사용하면 빈 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-601">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="aac68-602">마찬가지로 `[a-z-[0-9]]` 식을 사용하면 원래 기본 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-602">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="aac68-603">"a"부터 "z"까지의 문자 범위를 나타내는 기본 그룹에는 제외할 그룹의 문자, 즉 "0"부터 "9"까지의 10진수 문자 범위가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-603">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="aac68-604">다음 예제에서는 입력 문자열에서 0과 홀수를 찾는 정규식 `^[0-9-[2468]]+$`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-604">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="aac68-605">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-605">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="aac68-606">요소</span><span class="sxs-lookup"><span data-stu-id="aac68-606">Element</span></span>|<span data-ttu-id="aac68-607">설명</span><span class="sxs-lookup"><span data-stu-id="aac68-607">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="aac68-608">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-608">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="aac68-609">모든 문자 0에서 9까지 2, 4, 6 및 8을 제외한 하나 이상의 항목을 일치하세요.</span><span class="sxs-lookup"><span data-stu-id="aac68-609">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="aac68-610">즉, 한 번 이상 나오는 0 또는 홀수와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-610">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="aac68-611">입력 문자열의 끝 부분에서 검색을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="aac68-611">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="aac68-612">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aac68-612">See also</span></span>

- <xref:System.Char.GetUnicodeCategory%2A>
- [<span data-ttu-id="aac68-613">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="aac68-613">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [<span data-ttu-id="aac68-614">정규식 옵션</span><span class="sxs-lookup"><span data-stu-id="aac68-614">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
