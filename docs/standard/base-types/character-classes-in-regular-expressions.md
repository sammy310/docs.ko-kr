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
ms.openlocfilehash: 54d190bfa3f13ccfc78dd2501018442afb281d37
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64634704"
---
# <a name="character-classes-in-regular-expressions"></a><span data-ttu-id="3d2a7-103">정규식의 문자 클래스</span><span class="sxs-lookup"><span data-stu-id="3d2a7-103">Character Classes in Regular Expressions</span></span>
<a name="Top"></a> <span data-ttu-id="3d2a7-104">문자 클래스는 문자 집합을 정의하며, 이 중 하나가 입력 문자열에서 발생하면 일치하는 것으로 판정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-104">A character class defines a set of characters, any one of which can occur in an input string for a match to succeed.</span></span> <span data-ttu-id="3d2a7-105">.NET의 정규식 언어는 다음과 같은 문자 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-105">The regular expression language in .NET supports the following character classes:</span></span>  
  
- <span data-ttu-id="3d2a7-106">긍정 문자 그룹.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-106">Positive character groups.</span></span> <span data-ttu-id="3d2a7-107">입력 문자열의 문자는 지정된 문자 집합 중 하나와 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-107">A character in the input string must match one of a specified set of characters.</span></span> <span data-ttu-id="3d2a7-108">자세한 내용은 [긍정 문자 그룹](#PositiveGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-108">For more information, see [Positive Character Group](#PositiveGroup).</span></span>  
  
- <span data-ttu-id="3d2a7-109">부정 문자 그룹.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-109">Negative character groups.</span></span> <span data-ttu-id="3d2a7-110">입력 문자열의 문자는 지정된 문자 집합 중 하나와 일치하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-110">A character in the input string must not match one of a specified set of characters.</span></span> <span data-ttu-id="3d2a7-111">자세한 내용은 [부정 문자 그룹](#NegativeGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-111">For more information, see [Negative Character Group](#NegativeGroup).</span></span>  
  
- <span data-ttu-id="3d2a7-112">임의의 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-112">Any character.</span></span> <span data-ttu-id="3d2a7-113">정규식의 `.`(점 또는 마침표) 문자는 `\n`을 제외한 모든 문자와 일치하는 와일드카드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-113">The `.` (dot or period) character in a regular expression is a wildcard character that matches any character except `\n`.</span></span> <span data-ttu-id="3d2a7-114">자세한 내용은 [임의의 문자](#AnyCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-114">For more information, see [Any Character](#AnyCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-115">일반 유니코드 범주 또는 명명된 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-115">A general Unicode category or named block.</span></span> <span data-ttu-id="3d2a7-116">입력 문자열의 문자는 일치하는 것으로 판정하려면 특정 유니코드 범주의 멤버이거나 유니코드 문자의 연속된 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-116">A character in the input string must be a member of a particular Unicode category or must fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="3d2a7-117">자세한 내용은 [유니코드 범주 또는 유니코드 블록](#CategoryOrBlock)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-117">For more information, see [Unicode Category or Unicode Block](#CategoryOrBlock).</span></span>  
  
- <span data-ttu-id="3d2a7-118">부정 일반 유니코드 범주 또는 명명된 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-118">A negative general Unicode category or named block.</span></span> <span data-ttu-id="3d2a7-119">입력 문자열의 문자는 일치하는 것으로 판정하려면 특정 유니코드 범주의 멤버가 아니거나 유니코드 문자의 연속된 범위 내에 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-119">A character in the input string must not be a member of a particular Unicode category or must not fall within a contiguous range of Unicode characters for a match to succeed.</span></span> <span data-ttu-id="3d2a7-120">자세한 내용은 [부정 유니코드 범주 또는 유니코드 블록](#NegativeCategoryOrBlock)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-120">For more information, see [Negative Unicode Category or Unicode Block](#NegativeCategoryOrBlock).</span></span>  
  
- <span data-ttu-id="3d2a7-121">단어 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-121">A word character.</span></span> <span data-ttu-id="3d2a7-122">입력 문자열의 문자는 단어에 있는 문자에 적합한 유니코드 범주에 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-122">A character in the input string can belong to any of the Unicode categories that are appropriate for characters in words.</span></span> <span data-ttu-id="3d2a7-123">자세한 내용은 [단어 문자](#WordCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-123">For more information, see [Word Character](#WordCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-124">비단어 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-124">A non-word character.</span></span> <span data-ttu-id="3d2a7-125">입력 문자열의 문자는 단어 문자가 아닌 유니코드 범주에 속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-125">A character in the input string can belong to any Unicode category that is not a word character.</span></span> <span data-ttu-id="3d2a7-126">자세한 내용은 [단어가 아닌 문자](#NonWordCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-126">For more information, see [Non-Word Character](#NonWordCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-127">공백 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-127">A white-space character.</span></span> <span data-ttu-id="3d2a7-128">입력 문자열의 문자는 유니코드 구분 문자뿐만 아니라 많은 제어 문자 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-128">A character in the input string can be any Unicode separator character, as well as any one of a number of control characters.</span></span> <span data-ttu-id="3d2a7-129">자세한 내용은 [공백 문자](#WhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-129">For more information, see [White-Space Character](#WhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-130">공백이 아닌 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-130">A non-white-space character.</span></span> <span data-ttu-id="3d2a7-131">입력 문자열의 문자는 공백 문자가 아닌 문자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-131">A character in the input string can be any character that is not a white-space character.</span></span> <span data-ttu-id="3d2a7-132">자세한 내용은 [공백이 아닌 문자](#NonWhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-132">For more information, see [Non-White-Space Character](#NonWhitespaceCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-133">10진수입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-133">A decimal digit.</span></span> <span data-ttu-id="3d2a7-134">입력 문자열의 문자는 유니코드 10진 자릿수로 분류된 모든 문자가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-134">A character in the input string can be any of a number of characters classified as Unicode decimal digits.</span></span> <span data-ttu-id="3d2a7-135">자세한 내용은 [10진수 숫자 문자](#DigitCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-135">For more information, see [Decimal Digit Character](#DigitCharacter).</span></span>  
  
- <span data-ttu-id="3d2a7-136">10진수가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-136">A non-decimal digit.</span></span> <span data-ttu-id="3d2a7-137">입력 문자열의 문자는 유니코드 10진수 이외의 문자는 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-137">A character in the input string can be anything other than a Unicode decimal digit.</span></span> <span data-ttu-id="3d2a7-138">자세한 내용은 [10진수 숫자 문자](#NonDigitCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-138">For more information, see [Decimal Digit Character](#NonDigitCharacter).</span></span>  
  
 <span data-ttu-id="3d2a7-139">.NET에서는 한 문자 클래스에서 다른 문자 클래스를 제외한 결과로 문자 집합을 정의하는 데 사용할 수 있는 문자 클래스 빼기 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-139">.NET supports character class subtraction expressions, which enables you to define a set of characters as the result of excluding one character class from another character class.</span></span> <span data-ttu-id="3d2a7-140">자세한 내용은 [문자 클래스 빼기](#CharacterClassSubtraction)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-140">For more information, see [Character Class Subtraction](#CharacterClassSubtraction).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d2a7-141">일치하는 단어 문자를 검색하는 [\w](#WordCharacter) 또는 일치하는 유니코드 범주를 검색하는 [\p{}](#CategoryOrBlock)와 같이 범주별로 일치하는 문자를 검색하는 문자 클래스는 <xref:System.Globalization.CharUnicodeInfo> 클래스를 활용하여 문자 범주에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-141">Character classes that match characters by category, such as [\w](#WordCharacter) to match word characters or [\p{}](#CategoryOrBlock) to match a Unicode category, rely on the <xref:System.Globalization.CharUnicodeInfo> class to provide information about character categories.</span></span>  <span data-ttu-id="3d2a7-142">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]부터, 문자 범주는 [유니코드 표준, 버전 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/)을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-142">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], character categories are based on [The Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/).</span></span> <span data-ttu-id="3d2a7-143">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] ~ [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서는 [유니코드 표준, 버전 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/)를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-143">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] through the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], they are based on [The Unicode Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).</span></span>  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a><span data-ttu-id="3d2a7-144">긍정 문자 그룹: [ ]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-144">Positive Character Group: [ ]</span></span>  
 <span data-ttu-id="3d2a7-145">긍정 문자 그룹은 일치 항목으로 간주되려면 입력 문자열에 나타날 수 있는 문자 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-145">A positive character group specifies a list of characters, any one of which may appear in an input string for a match to occur.</span></span> <span data-ttu-id="3d2a7-146">이 문자 목록은 개별적으로, 범위로 또는 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-146">This list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="3d2a7-147">개별 문자 목록을 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-147">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="3d2a7-148">[*character_group*]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-148">[*character_group*]</span></span>  
  
 <span data-ttu-id="3d2a7-149">여기서 *character_group*은 일치가 성공하기 위해 입력 문자열에 나타날 수 있는 개별 문자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-149">where *character_group* is a list of the individual characters that can appear in the input string for a match to succeed.</span></span> <span data-ttu-id="3d2a7-150">*character_group*은 하나 이상의 리터럴 문자, [이스케이프 문자](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) 또는 문자 클래스로 이루어진 조합으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-150">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="3d2a7-151">문자의 범위를 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-151">The syntax for specifying a range of characters is as follows:</span></span>  
  
```  
[firstCharacter-lastCharacter]  
```  
  
 <span data-ttu-id="3d2a7-152">여기서 *firstCharacter*는 범위를 시작하는 문자이고 *lastCharacter*는 범위를 끝내는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-152">where *firstCharacter* is the character that begins the range and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="3d2a7-153">문자 범위는 일련의 문자로서, 문자 범위를 정의하려면 연속된 문자 중 첫 번째 문자와 마지막 문자를 하이픈(-)으로 연결하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-153">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="3d2a7-154">두 문자의 유니코드 코드 포인트가 연속되면 이 두 문자는 연속된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-154">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="3d2a7-155">긍정 문자 클래스가 포함된 몇 가지 일반적인 정규식 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-155">Some common regular expression patterns that contain positive character classes are listed in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-156">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-156">Pattern</span></span>|<span data-ttu-id="3d2a7-157">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-157">Description</span></span>|  
|-------------|-----------------|  
|`[aeiou]`|<span data-ttu-id="3d2a7-158">모든 모음을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-158">Match all vowels.</span></span>|  
|`[\p{P}\d]`|<span data-ttu-id="3d2a7-159">모든 문장 부호 및 10진수 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-159">Match all punctuation and decimal digit characters.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="3d2a7-160">모든 공백 및 문장 부호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-160">Match all white space and punctuation.</span></span>|  
  
 <span data-ttu-id="3d2a7-161">다음 예제에서는 입력 문자열이 문자 "grey" 또는 "gray"에 이어 일치할 다른 일치 단어를 포함하도록 단어 "a"와 "e"가 포함된 긍정 문자 그룹을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-161">The following example defines a positive character group that contains the characters "a" and "e" so that the input string must contain the words "grey" or "gray" followed by another word for a match to occur.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 <span data-ttu-id="3d2a7-162">`gr[ae]y\s\S+?[\s|\p{P}]` 정규식은 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-162">The regular expression `gr[ae]y\s\S+?[\s|\p{P}]` is defined as follows:</span></span>  
  
|<span data-ttu-id="3d2a7-163">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-163">Pattern</span></span>|<span data-ttu-id="3d2a7-164">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-164">Description</span></span>|  
|-------------|-----------------|  
|`gr`|<span data-ttu-id="3d2a7-165">리터럴 문자 "gr"을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-165">Match the literal characters "gr".</span></span>|  
|`[ae]`|<span data-ttu-id="3d2a7-166">"a" 또는 "e"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-166">Match either an "a" or an "e".</span></span>|  
|`y\s`|<span data-ttu-id="3d2a7-167">리터럴 문자 y 다음에 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-167">Match the literal character "y" followed by a white-space character.</span></span>|  
|`\S+?`|<span data-ttu-id="3d2a7-168">하나 이상의 공백이 아닌 문자이지만 가능한 적은 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-168">Match one or more non-white-space characters, but as few as possible.</span></span>|  
|`[\s\p{P}]`|<span data-ttu-id="3d2a7-169">공백 문자 또는 문장 부호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-169">Match either a white-space character or a punctuation mark.</span></span>|  
  
 <span data-ttu-id="3d2a7-170">다음 예제에서는 모든 대문자로 시작하는 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-170">The following example matches words that begin with any capital letter.</span></span> <span data-ttu-id="3d2a7-171">A-Z의 대문자로 범위를 나타내기 위해 `[A-Z]` 하위 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-171">It uses the subexpression `[A-Z]` to represent the range of capital letters from A to Z.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 <span data-ttu-id="3d2a7-172">`\b[A-Z]\w*\b` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-172">The regular expression `\b[A-Z]\w*\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-173">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-173">Pattern</span></span>|<span data-ttu-id="3d2a7-174">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-174">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="3d2a7-175">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-175">Start at a word boundary.</span></span>|  
|`[A-Z]`|<span data-ttu-id="3d2a7-176">A-Z의 대문자를 모두 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-176">Match any uppercase character from A to Z.</span></span>|  
|`\w*`|<span data-ttu-id="3d2a7-177">0개 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-177">Match zero or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="3d2a7-178">단어 경계를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-178">Match a word boundary.</span></span>|  
  
 [<span data-ttu-id="3d2a7-179">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-179">Back to Top</span></span>](#Top)  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a><span data-ttu-id="3d2a7-180">부정 문자 그룹: [^]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-180">Negative Character Group: [^]</span></span>  
 <span data-ttu-id="3d2a7-181">부정 문자 그룹은 일치 항목으로 간주되려면 입력 문자열에 나타나서는 안 되는 문자 목록을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-181">A negative character group specifies a list of characters that must not appear in an input string for a match to occur.</span></span> <span data-ttu-id="3d2a7-182">문자 목록은 개별적으로, 범위로 또는 둘 다 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-182">The list of characters may be specified individually, as a range, or both.</span></span>  
  
 <span data-ttu-id="3d2a7-183">개별 문자 목록을 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-183">The syntax for specifying a list of individual characters is as follows:</span></span>  
  
 <span data-ttu-id="3d2a7-184">[*^character_group*]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-184">[*^character_group*]</span></span>  
  
 <span data-ttu-id="3d2a7-185">여기서 *character_group*은 일치가 성공하기 위해 입력 문자열에 나타날 수 없는 개별 문자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-185">where *character_group* is a list of the individual characters that cannot appear in the input string for a match to succeed.</span></span> <span data-ttu-id="3d2a7-186">*character_group*은 하나 이상의 리터럴 문자, [이스케이프 문자](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) 또는 문자 클래스로 이루어진 조합으로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-186">*character_group* can consist of any combination of one or more literal characters, [escape characters](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md), or character classes.</span></span>  
  
 <span data-ttu-id="3d2a7-187">문자의 범위를 지정하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-187">The syntax for specifying a range of characters is as follows:</span></span>  
  
 <span data-ttu-id="3d2a7-188">[^*firstCharacter*-*lastCharacter*]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-188">[^*firstCharacter*-*lastCharacter*]</span></span>  
  
 <span data-ttu-id="3d2a7-189">여기서 *firstCharacter*는 범위를 시작하는 문자이고 *lastCharacter*는 범위를 끝내는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-189">where *firstCharacter* is the character that begins the range, and *lastCharacter* is the character that ends the range.</span></span> <span data-ttu-id="3d2a7-190">문자 범위는 일련의 문자로서, 문자 범위를 정의하려면 연속된 문자 중 첫 번째 문자와 마지막 문자를 하이픈(-)으로 연결하여 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-190">A character range is a contiguous series of characters defined by specifying the first character in the series, a hyphen (-), and then the last character in the series.</span></span> <span data-ttu-id="3d2a7-191">두 문자의 유니코드 코드 포인트가 연속되면 이 두 문자는 연속된 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-191">Two characters are contiguous if they have adjacent Unicode code points.</span></span>  
  
 <span data-ttu-id="3d2a7-192">두 개 이상의 문자 범위를 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-192">Two or more character ranges can be concatenated.</span></span> <span data-ttu-id="3d2a7-193">예를 들어, "0"부터 "9"까지의 10진수 범위, "a"부터 "f"까지의 소문자 범위 및 "A"부터 "F"까지의 대문자 범위를 지정하려면 `[0-9a-fA-F]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-193">For example, to specify the range of decimal digits from "0" through "9", the range of lowercase letters from "a" through "f", and the range of uppercase letters from "A" through "F", use `[0-9a-fA-F]`.</span></span>  
  
 <span data-ttu-id="3d2a7-194">부정 문자 그룹에서 맨 앞의 캐럿 문자(`^`)는 필수 문자로서, 해당 문자 그룹이 긍정 문자 그룹이 아니라 부정 문자 그룹임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-194">The leading carat character (`^`) in a negative character group is mandatory and indicates the character group is a negative character group instead of a positive character group.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3d2a7-195">큰 정규식 패턴에서 부정 문자 그룹은 너비가 0인 어설션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-195">A negative character group in a larger regular expression pattern is not a zero-width assertion.</span></span> <span data-ttu-id="3d2a7-196">즉, 부정 문자 그룹을 평가한 후 정규식 엔진은 입력 문자열에서 한 문자를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-196">That is, after evaluating the negative character group, the regular expression engine advances one character in the input string.</span></span>  
  
 <span data-ttu-id="3d2a7-197">부정 문자 그룹이 포함된 몇 가지 일반적인 정규식 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-197">Some common regular expression patterns that contain negative character groups are listed in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-198">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-198">Pattern</span></span>|<span data-ttu-id="3d2a7-199">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-199">Description</span></span>|  
|-------------|-----------------|  
|`[^aeiou]`|<span data-ttu-id="3d2a7-200">모음을 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-200">Match all characters except vowels.</span></span>|  
|`[^\p{P}\d]`|<span data-ttu-id="3d2a7-201">문장 부호 및 10진수 문자를 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-201">Match all characters except punctuation and decimal digit characters.</span></span>|  
  
 <span data-ttu-id="3d2a7-202">다음 예제에서는 "th" 문자로 시작하고 이어서 "o"가 나오지 않는 단어를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-202">The following example matches any word that begins with the characters "th" and is not followed by an "o".</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 <span data-ttu-id="3d2a7-203">`\bth[^o]\w+\b` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-203">The regular expression `\bth[^o]\w+\b` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-204">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-204">Pattern</span></span>|<span data-ttu-id="3d2a7-205">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-205">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="3d2a7-206">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-206">Start at a word boundary.</span></span>|  
|`th`|<span data-ttu-id="3d2a7-207">리터럴 문자 "th"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-207">Match the literal characters "th".</span></span>|  
|`[^o]`|<span data-ttu-id="3d2a7-208">"o"가 아닌 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-208">Match any character that is not an "o".</span></span>|  
|`\w+`|<span data-ttu-id="3d2a7-209">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-209">Match one or more word characters.</span></span>|  
|`\b`|<span data-ttu-id="3d2a7-210">단어 경계를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-210">End at a word boundary.</span></span>|  
  
 [<span data-ttu-id="3d2a7-211">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-211">Back to Top</span></span>](#Top)  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a><span data-ttu-id="3d2a7-212">임의의 문자: .</span><span class="sxs-lookup"><span data-stu-id="3d2a7-212">Any Character: .</span></span>  
 <span data-ttu-id="3d2a7-213">마침표 문자(.)는 `\n`(줄바꿈 문자, \u000A)를 제외하고 다음 두 한정자가 있는 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-213">The period character (.) matches any character except `\n` (the newline character, \u000A), with the following two qualifications:</span></span>  
  
- <span data-ttu-id="3d2a7-214">정규식 패턴이 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 옵션에 의해 수정되거나 `.` 문자 클래스를 포함하는 패턴의 일부가 `s` 옵션에 의해 수정되는 경우 `.`가 문자를 일치시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-214">If a regular expression pattern is modified by the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option, or if the portion of the pattern that contains the `.` character class is modified by the `s` option, `.` matches any character.</span></span> <span data-ttu-id="3d2a7-215">자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-215">For more information, see [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
     <span data-ttu-id="3d2a7-216">다음 예제에서는 기본 및 `.` 옵션으로 <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 문자 클래스의 다른 동작을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-216">The following example illustrates the different behavior of the `.` character class by default and with the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option.</span></span> <span data-ttu-id="3d2a7-217">정규식 `^.+`는 문자열의 시작 부분에서 시작하여 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-217">The regular expression `^.+` starts at the beginning of the string and matches every character.</span></span> <span data-ttu-id="3d2a7-218">기본적으로 일치는 첫 번째 줄의 끝 부분에서 끝납니다. 정규식 패턴은 캐리지 리턴 문자, `\r` 또는 \u000D와 일치하지만 `\n`과는 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-218">By default, the match ends at the end of the first line; the regular expression pattern matches the carriage return character, `\r` or \u000D, but it does not match `\n`.</span></span> <span data-ttu-id="3d2a7-219"><xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> 옵션은 전체 입력 문자열을 한 줄로 해석하기 때문에 `\n`을 포함하여 입력 문자열의 모든 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-219">Because the <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType> option interprets the entire input string as a single line, it matches every character in the input string, including `\n`.</span></span>  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
>  <span data-ttu-id="3d2a7-220">`\n`을 제외한 모든 문자와 일치하기 때문에 `.` 문자 클래스가 `\r`(캐리지 리턴 문자, \u000D)과도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-220">Because it matches any character except `\n`, the `.` character class also matches `\r` (the carriage return character, \u000D).</span></span>  
  
- <span data-ttu-id="3d2a7-221">긍정 또는 부정 문자 그룹의 마침표는 문자 클래스가 아니라 리터럴 마침표 문자로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-221">In a positive or negative character group, a period is treated as a literal period character, and not as a character class.</span></span> <span data-ttu-id="3d2a7-222">자세한 내용은 이 항목 앞부분의 [긍정 문자 그룹](#PositiveGroup) 및 [부정 문자 그룹](#NegativeGroup)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-222">For more information, see [Positive Character Group](#PositiveGroup) and [Negative Character Group](#NegativeGroup) earlier in this topic.</span></span> <span data-ttu-id="3d2a7-223">다음 예제는 문자 클래스와 긍정 문자 그룹으로 마침표 문자(`.`)를 포함하는 정규식을 정의하는 그림을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-223">The following example provides an illustration by defining a regular expression that includes the period character (`.`) both as a character class and as a member of a positive character group.</span></span> <span data-ttu-id="3d2a7-224">`\b.*[.?!;:](\s|\z)` 정규식은 단어 경계에서 시작하여 마침표를 포함하여 다섯 가지 문장 부호 중 하나와 만날 때까지 임의의 문자를 찾은 다음 공백 문자 또는 문자열 끝을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-224">The regular expression `\b.*[.?!;:](\s|\z)` begins at a word boundary, matches any character until it encounters one of five punctuation marks, including a period, and then matches either a white-space character or the end of the string.</span></span>  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="3d2a7-225">모든 문자와 일치하기 때문에 `.` 언어 요소는 정규식 패턴이 여러 번 임의의 문자와 일치하도록 시도할 경우 종종 lazy 수량자와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-225">Because it matches any character, the `.` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any character multiple times.</span></span> <span data-ttu-id="3d2a7-226">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-226">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 [<span data-ttu-id="3d2a7-227">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-227">Back to Top</span></span>](#Top)  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a><span data-ttu-id="3d2a7-228">유니코드 범주 또는 유니코드 블록: \p{}</span><span class="sxs-lookup"><span data-stu-id="3d2a7-228">Unicode Category or Unicode Block: \p{}</span></span>  
 <span data-ttu-id="3d2a7-229">유니코드 표준에서는 각 문자를 일반 범주에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-229">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="3d2a7-230">예를 들어, 특정 문자는 대문자(`Lu` 범주로 표현), 10진수(`Nd` 범주), 수학 기호(`Sm` 범주) 또는 단락 구분 기호(`Zl` 범주)가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-230">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="3d2a7-231">유니코드 표준의 특정 문자 집합이 특정 범위 또는 연속된 코드 포인트의 블록도 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-231">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="3d2a7-232">예를 들어, 기본 라틴 문자 집합은 \u0000부터 \u007F까지에서 발견되고, 아랍어 문자 집합이 \u0600부터 \u06FF까지에서 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-232">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="3d2a7-233">정규식 만들기</span><span class="sxs-lookup"><span data-stu-id="3d2a7-233">The regular expression construct</span></span>  
  
 <span data-ttu-id="3d2a7-234">`\p{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="3d2a7-234">`\p{` *name* `}`</span></span>  
  
 <span data-ttu-id="3d2a7-235">유니코드 일반 범주 또는 명명된 블록에 속하는 모든 문자를 찾습니다. 여기서 *name*은 범주 약어 또는 명명된 블록 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-235">matches any character that belongs to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="3d2a7-236">범주 약어 목록은 이 항목의 뒷부분에 있는 [지원되는 유니코드 일반 범주](#SupportedUnicodeGeneralCategories) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-236">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="3d2a7-237">명명된 블록 목록은 이 항목의 뒷부분에 있는 [지원되는 명명된 블록](#SupportedNamedBlocks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-237">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="3d2a7-238">다음 예제에서는 `\p{`*name*`}` 구문을 사용하여 유니코드 일반 범주(이 경우 `Pd` 또는 문장 부호, 대시 범주) 및 명명된 블록(명명된 블록 `IsGreek` 및 `IsBasicLatin`)을 모두 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-238">The following example uses the `\p{`*name*`}` construct to match both a Unicode general category (in this case, the `Pd`, or Punctuation, Dash category) and a named block (the `IsGreek` and `IsBasicLatin` named blocks).</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 <span data-ttu-id="3d2a7-239">`\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` 정규식은 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-239">The regular expression `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-240">무늬</span><span class="sxs-lookup"><span data-stu-id="3d2a7-240">Pattern</span></span>|<span data-ttu-id="3d2a7-241">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-241">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="3d2a7-242">단어 경계를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-242">Start at a word boundary.</span></span>|  
|`\p{IsGreek}+`|<span data-ttu-id="3d2a7-243">둘 이상의 그리스어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-243">Match one or more Greek characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="3d2a7-244">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-244">Match zero or one white-space character.</span></span>|  
|`(\p{IsGreek}+(\s)?)+`|<span data-ttu-id="3d2a7-245">하나 이상의 그리스 문자 다음에 0개 또는 1개의 공백 문자가 한 번 이상 나타나는 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-245">Match the pattern of one or more Greek characters followed by zero or one white-space characters one or more times.</span></span>|  
|`\p{Pd}`|<span data-ttu-id="3d2a7-246">문장 부호, 대시 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-246">Match a Punctuation, Dash character.</span></span>|  
|`\s`|<span data-ttu-id="3d2a7-247">공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-247">Match a white-space character.</span></span>|  
|`\p{IsBasicLatin}+`|<span data-ttu-id="3d2a7-248">하나 이상의 기본 라틴 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-248">Match one or more basic Latin characters.</span></span>|  
|`(\s)?`|<span data-ttu-id="3d2a7-249">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-249">Match zero or one white-space character.</span></span>|  
|`(\p{IsBasicLatin}+(\s)?)+`|<span data-ttu-id="3d2a7-250">하나 이상의 기본 라틴 문자 다음에 0개 또는 1개의 공백 문자가 한 번 이상 나타나는 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-250">Match the pattern of one or more basic Latin characters followed by zero or one white-space characters one or more times.</span></span>|  
  
 [<span data-ttu-id="3d2a7-251">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-251">Back to Top</span></span>](#Top)  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a><span data-ttu-id="3d2a7-252">부정 유니코드 범주 또는 유니코드 블록: \P{}</span><span class="sxs-lookup"><span data-stu-id="3d2a7-252">Negative Unicode Category or Unicode Block: \P{}</span></span>  
 <span data-ttu-id="3d2a7-253">유니코드 표준에서는 각 문자를 일반 범주에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-253">The Unicode standard assigns each character a general category.</span></span> <span data-ttu-id="3d2a7-254">예를 들어, 특정 문자는 대문자(`Lu` 범주로 표현), 10진수(`Nd` 범주), 수학 기호(`Sm` 범주) 또는 단락 구분 기호(`Zl` 범주)가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-254">For example, a particular character can be an uppercase letter (represented by the `Lu` category), a decimal digit (the `Nd` category), a math symbol (the `Sm` category), or a paragraph separator (the `Zl` category).</span></span> <span data-ttu-id="3d2a7-255">유니코드 표준의 특정 문자 집합이 특정 범위 또는 연속된 코드 포인트의 블록도 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-255">Specific character sets in the Unicode standard also occupy a specific range or block of consecutive code points.</span></span> <span data-ttu-id="3d2a7-256">예를 들어, 기본 라틴 문자 집합은 \u0000부터 \u007F까지에서 발견되고, 아랍어 문자 집합이 \u0600부터 \u06FF까지에서 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-256">For example, the basic Latin character set is found from \u0000 through \u007F, while the Arabic character set is found from \u0600 through \u06FF.</span></span>  
  
 <span data-ttu-id="3d2a7-257">정규식 만들기</span><span class="sxs-lookup"><span data-stu-id="3d2a7-257">The regular expression construct</span></span>  
  
 <span data-ttu-id="3d2a7-258">`\P{` *name* `}`</span><span class="sxs-lookup"><span data-stu-id="3d2a7-258">`\P{` *name* `}`</span></span>  
  
 <span data-ttu-id="3d2a7-259">유니코드 일반 범주 또는 명명된 블록에 속하지 않는 모든 문자를 찾습니다. 여기서 *name*은 범주 약어 또는 명명된 블록 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-259">matches any character that does not belong to a Unicode general category or named block, where *name* is the category abbreviation or named block name.</span></span> <span data-ttu-id="3d2a7-260">범주 약어 목록은 이 항목의 뒷부분에 있는 [지원되는 유니코드 일반 범주](#SupportedUnicodeGeneralCategories) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-260">For a list of category abbreviations, see the [Supported Unicode General Categories](#SupportedUnicodeGeneralCategories) section later in this topic.</span></span> <span data-ttu-id="3d2a7-261">명명된 블록 목록은 이 항목의 뒷부분에 있는 [지원되는 명명된 블록](#SupportedNamedBlocks) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-261">For a list of named blocks, see the [Supported Named Blocks](#SupportedNamedBlocks) section later in this topic.</span></span>  
  
 <span data-ttu-id="3d2a7-262">다음 예제에서는 `\P{`*name*`}` 구문을 사용하여 숫자 문자열에서 모든 통화 기호(이 경우, `Sc` 또는 기호, 통화 범주)를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-262">The following example uses the `\P{`*name*`}` construct to remove any currency symbols (in this case, the `Sc`, or Symbol, Currency category) from numeric strings.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 <span data-ttu-id="3d2a7-263">정규식 패턴 `(\P{Sc})+`는 통화 기호가 아닌 하나 이상의 문자를 찾습니다. 결과 문자열에서 모든 통화 기호를 효과적으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-263">The regular expression pattern `(\P{Sc})+` matches one or more characters that are not currency symbols; it effectively strips any currency symbol from the result string.</span></span>  
  
 [<span data-ttu-id="3d2a7-264">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-264">Back to Top</span></span>](#Top)  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a><span data-ttu-id="3d2a7-265">단어 문자: \w</span><span class="sxs-lookup"><span data-stu-id="3d2a7-265">Word Character: \w</span></span>  
 <span data-ttu-id="3d2a7-266">`\w`는 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-266">`\w` matches any word character.</span></span> <span data-ttu-id="3d2a7-267">단어 문자는 다음 표에 나열된 유니코드 범주의 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-267">A word character is a member of any of the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-268">범주</span><span class="sxs-lookup"><span data-stu-id="3d2a7-268">Category</span></span>|<span data-ttu-id="3d2a7-269">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-269">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="3d2a7-270">Ll</span><span class="sxs-lookup"><span data-stu-id="3d2a7-270">Ll</span></span>|<span data-ttu-id="3d2a7-271">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-271">Letter, Lowercase</span></span>|  
|<span data-ttu-id="3d2a7-272">Lu</span><span class="sxs-lookup"><span data-stu-id="3d2a7-272">Lu</span></span>|<span data-ttu-id="3d2a7-273">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-273">Letter, Uppercase</span></span>|  
|<span data-ttu-id="3d2a7-274">Lt</span><span class="sxs-lookup"><span data-stu-id="3d2a7-274">Lt</span></span>|<span data-ttu-id="3d2a7-275">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="3d2a7-275">Letter, Titlecase</span></span>|  
|<span data-ttu-id="3d2a7-276">Lo</span><span class="sxs-lookup"><span data-stu-id="3d2a7-276">Lo</span></span>|<span data-ttu-id="3d2a7-277">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-277">Letter, Other</span></span>|  
|<span data-ttu-id="3d2a7-278">Lm</span><span class="sxs-lookup"><span data-stu-id="3d2a7-278">Lm</span></span>|<span data-ttu-id="3d2a7-279">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-279">Letter, Modifier</span></span>|  
|<span data-ttu-id="3d2a7-280">Mn</span><span class="sxs-lookup"><span data-stu-id="3d2a7-280">Mn</span></span>|<span data-ttu-id="3d2a7-281">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="3d2a7-281">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="3d2a7-282">Nd</span><span class="sxs-lookup"><span data-stu-id="3d2a7-282">Nd</span></span>|<span data-ttu-id="3d2a7-283">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="3d2a7-283">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="3d2a7-284">Pc</span><span class="sxs-lookup"><span data-stu-id="3d2a7-284">Pc</span></span>|<span data-ttu-id="3d2a7-285">문장 부호, 연결자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-285">Punctuation, Connector.</span></span> <span data-ttu-id="3d2a7-286">이 범주는 가장 일반적으로 사용되는 LOWLINE 문자 (_), U + 005F인 10개의 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-286">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="3d2a7-287">ECMAScript와 호환되는 동작을 지정한 경우 `\w`는 `[a-zA-Z_0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-287">If ECMAScript-compliant behavior is specified, `\w` is equivalent to `[a-zA-Z_0-9]`.</span></span> <span data-ttu-id="3d2a7-288">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-288">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d2a7-289">모든 단어 문자와 일치하기 때문에 `\w` 언어 요소는 정규식 패턴이 특정 단어 문자가 따라오는 임의의 단어 문자를 여러 번 찾으려 하는 경우 lazy 수량자와 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-289">Because it matches any word character, the `\w` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any word character multiple times, followed by a specific word character.</span></span> <span data-ttu-id="3d2a7-290">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-290">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="3d2a7-291">다음 예제에서는 `\w` 언어 요소를 사용하여 단어의 중복 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-291">The following example uses the `\w` language element to match duplicate characters in a word.</span></span> <span data-ttu-id="3d2a7-292">예제는 다음과 같이 해석될 수 있는 정규식 패턴 `(\w)\1`을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-292">The example defines a regular expression pattern, `(\w)\1`, which can be interpreted as follows.</span></span>  
  
|<span data-ttu-id="3d2a7-293">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-293">Element</span></span>|<span data-ttu-id="3d2a7-294">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-294">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d2a7-295">(\w)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-295">(\w)</span></span>|<span data-ttu-id="3d2a7-296">단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-296">Match a word character.</span></span> <span data-ttu-id="3d2a7-297">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-297">This is the first capturing group.</span></span>|  
|<span data-ttu-id="3d2a7-298">\1</span><span class="sxs-lookup"><span data-stu-id="3d2a7-298">\1</span></span>|<span data-ttu-id="3d2a7-299">첫 번째 캡처의 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-299">Match the value of the first capture.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
 [<span data-ttu-id="3d2a7-300">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-300">Back to Top</span></span>](#Top)  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a><span data-ttu-id="3d2a7-301">비단어 문자: \W</span><span class="sxs-lookup"><span data-stu-id="3d2a7-301">Non-Word Character: \W</span></span>  
 <span data-ttu-id="3d2a7-302">`\W`는 비단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-302">`\W` matches any non-word character.</span></span> <span data-ttu-id="3d2a7-303">\W 언어 요소는 다음 문자 클래스에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-303">The \W language element is equivalent to the following character class:</span></span>  
  
```  
[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]  
```  
  
 <span data-ttu-id="3d2a7-304">즉, 다음 표에 나열된 유니코드 범주의 문자를 제외한 모든 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-304">In other words, it matches any character except for those in the Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-305">범주</span><span class="sxs-lookup"><span data-stu-id="3d2a7-305">Category</span></span>|<span data-ttu-id="3d2a7-306">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-306">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="3d2a7-307">Ll</span><span class="sxs-lookup"><span data-stu-id="3d2a7-307">Ll</span></span>|<span data-ttu-id="3d2a7-308">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-308">Letter, Lowercase</span></span>|  
|<span data-ttu-id="3d2a7-309">Lu</span><span class="sxs-lookup"><span data-stu-id="3d2a7-309">Lu</span></span>|<span data-ttu-id="3d2a7-310">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-310">Letter, Uppercase</span></span>|  
|<span data-ttu-id="3d2a7-311">Lt</span><span class="sxs-lookup"><span data-stu-id="3d2a7-311">Lt</span></span>|<span data-ttu-id="3d2a7-312">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="3d2a7-312">Letter, Titlecase</span></span>|  
|<span data-ttu-id="3d2a7-313">Lo</span><span class="sxs-lookup"><span data-stu-id="3d2a7-313">Lo</span></span>|<span data-ttu-id="3d2a7-314">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-314">Letter, Other</span></span>|  
|<span data-ttu-id="3d2a7-315">Lm</span><span class="sxs-lookup"><span data-stu-id="3d2a7-315">Lm</span></span>|<span data-ttu-id="3d2a7-316">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-316">Letter, Modifier</span></span>|  
|<span data-ttu-id="3d2a7-317">Mn</span><span class="sxs-lookup"><span data-stu-id="3d2a7-317">Mn</span></span>|<span data-ttu-id="3d2a7-318">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="3d2a7-318">Mark, Nonspacing</span></span>|  
|<span data-ttu-id="3d2a7-319">Nd</span><span class="sxs-lookup"><span data-stu-id="3d2a7-319">Nd</span></span>|<span data-ttu-id="3d2a7-320">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="3d2a7-320">Number, Decimal Digit</span></span>|  
|<span data-ttu-id="3d2a7-321">Pc</span><span class="sxs-lookup"><span data-stu-id="3d2a7-321">Pc</span></span>|<span data-ttu-id="3d2a7-322">문장 부호, 연결자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-322">Punctuation, Connector.</span></span> <span data-ttu-id="3d2a7-323">이 범주는 가장 일반적으로 사용되는 LOWLINE 문자 (_), U + 005F인 10개의 문자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-323">This category includes ten characters, the most commonly used of which is the LOWLINE character (_), u+005F.</span></span>|  
  
 <span data-ttu-id="3d2a7-324">ECMAScript와 호환되는 동작을 지정한 경우 `\W`는 `[^a-zA-Z_0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-324">If ECMAScript-compliant behavior is specified, `\W` is equivalent to `[^a-zA-Z_0-9]`.</span></span> <span data-ttu-id="3d2a7-325">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-325">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d2a7-326">모든 비단어 문자와 일치하기 때문에 `\W` 언어 요소는 정규식 패턴이 특정 비단어 문자가 따라오는 임의의 비단어 문자를 여러 번 찾으려 하는 경우 lazy 수량자와 함께 사용되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-326">Because it matches any non-word character, the `\W` language element is often used with a lazy quantifier if a regular expression pattern attempts to match any non-word character multiple times followed by a specific non-word character.</span></span> <span data-ttu-id="3d2a7-327">자세한 내용은 [수량자](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-327">For more information, see [Quantifiers](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="3d2a7-328">다음 예제에서는 `\W` 문자 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-328">The following example illustrates the `\W` character class.</span></span>  <span data-ttu-id="3d2a7-329">공백 또는 문장 부호와 같은 한두 개의 비단어 문자가 따라오는 단어와 일치하는 정규식 패턴 `\b(\w+)(\W){1,2}`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-329">It defines a regular expression pattern, `\b(\w+)(\W){1,2}`, that matches a word followed by one or two non-word characters, such as white space or punctuation.</span></span> <span data-ttu-id="3d2a7-330">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-330">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-331">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-331">Element</span></span>|<span data-ttu-id="3d2a7-332">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-332">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d2a7-333">\b</span><span class="sxs-lookup"><span data-stu-id="3d2a7-333">\b</span></span>|<span data-ttu-id="3d2a7-334">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-334">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="3d2a7-335">(\w+)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-335">(\w+)</span></span>|<span data-ttu-id="3d2a7-336">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-336">Match one or more word characters.</span></span> <span data-ttu-id="3d2a7-337">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-337">This is the first capturing group.</span></span>|  
|<span data-ttu-id="3d2a7-338">(\W){1,2}</span><span class="sxs-lookup"><span data-stu-id="3d2a7-338">(\W){1,2}</span></span>|<span data-ttu-id="3d2a7-339">단어가 아닌 문자를 한 개 또는 두 개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-339">Match a non-word character either one or two times.</span></span> <span data-ttu-id="3d2a7-340">이 그룹은 두 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-340">This is the second capturing group.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 <span data-ttu-id="3d2a7-341">두 번째 캡처링 그룹의 <xref:System.Text.RegularExpressions.Group> 개체가 단일 캡처된 비단어 문자만 포함하기 때문에 예제에서는 <xref:System.Text.RegularExpressions.CaptureCollection> 속성에 의해 반환되는 <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> 개체에서 모든 캡처된 비단어 문자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-341">Because the <xref:System.Text.RegularExpressions.Group> object for the second capturing group contains only a single captured non-word character, the example retrieves all captured non-word characters from the <xref:System.Text.RegularExpressions.CaptureCollection> object that is returned by the <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType> property.</span></span>  
  
 [<span data-ttu-id="3d2a7-342">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-342">Back to Top</span></span>](#Top)  
  
<a name="WhitespaceCharacter"></a>   
## <a name="white-space-character-s"></a><span data-ttu-id="3d2a7-343">공백 문자: \s</span><span class="sxs-lookup"><span data-stu-id="3d2a7-343">White-Space Character: \s</span></span>  
 <span data-ttu-id="3d2a7-344">`\s`는 임의의 공백 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-344">`\s` matches any white-space character.</span></span> <span data-ttu-id="3d2a7-345">다음 표에 나열된 이스케이프 시퀀스 및 유니코드 범주와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-345">It is equivalent to the escape sequences and Unicode categories listed in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-346">범주</span><span class="sxs-lookup"><span data-stu-id="3d2a7-346">Category</span></span>|<span data-ttu-id="3d2a7-347">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-347">Description</span></span>|  
|--------------|-----------------|  
|`\f`|<span data-ttu-id="3d2a7-348">용지 공급 문자, \u000C.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-348">The form feed character, \u000C.</span></span>|  
|`\n`|<span data-ttu-id="3d2a7-349">줄 바꿈 문자, \u000A.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-349">The newline character, \u000A.</span></span>|  
|`\r`|<span data-ttu-id="3d2a7-350">캐리지 리턴 문자 \u000D입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-350">The carriage return character, \u000D.</span></span>|  
|`\t`|<span data-ttu-id="3d2a7-351">탭 문자, \u0009.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-351">The tab character, \u0009.</span></span>|  
|`\v`|<span data-ttu-id="3d2a7-352">세로 탭 문자, \u000B.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-352">The vertical tab character, \u000B.</span></span>|  
|`\x85`|<span data-ttu-id="3d2a7-353">줄임표 또는 NEXT LINE (NEL) 문자 (…), \u0085.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-353">The ellipsis or NEXT LINE (NEL) character (…), \u0085.</span></span>|  
|`\p{Z}`|<span data-ttu-id="3d2a7-354">임의의 구분 기호 문자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-354">Matches any separator character.</span></span>|  
  
 <span data-ttu-id="3d2a7-355">ECMAScript와 호환되는 동작을 지정한 경우 `\s`는 `[ \f\n\r\t\v]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-355">If ECMAScript-compliant behavior is specified, `\s` is equivalent to `[ \f\n\r\t\v]`.</span></span> <span data-ttu-id="3d2a7-356">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-356">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="3d2a7-357">다음 예제에서는 `\s` 문자 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-357">The following example illustrates the `\s` character class.</span></span> <span data-ttu-id="3d2a7-358">"s" 또는 "es"로 끝나고 그 뒤에 공백 문자나 입력 문자열의 끝이 있는 단어와 일치하는 정규식 패턴 `\b\w+(e)?s(\s|$)`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-358">It defines a regular expression pattern, `\b\w+(e)?s(\s|$)`, that matches a word ending in either "s" or "es" followed by either a white-space character or the end of the input string.</span></span> <span data-ttu-id="3d2a7-359">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-359">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-360">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-360">Element</span></span>|<span data-ttu-id="3d2a7-361">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-361">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d2a7-362">\b</span><span class="sxs-lookup"><span data-stu-id="3d2a7-362">\b</span></span>|<span data-ttu-id="3d2a7-363">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-363">Begin the match at a word boundary.</span></span>|  
|<span data-ttu-id="3d2a7-364">\w+</span><span class="sxs-lookup"><span data-stu-id="3d2a7-364">\w+</span></span>|<span data-ttu-id="3d2a7-365">하나 이상의 단어 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-365">Match one or more word characters.</span></span>|  
|<span data-ttu-id="3d2a7-366">(e)?</span><span class="sxs-lookup"><span data-stu-id="3d2a7-366">(e)?</span></span>|<span data-ttu-id="3d2a7-367">"e"를 0개 또는 한 개 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-367">Match an "e" either zero or one time.</span></span>|  
|<span data-ttu-id="3d2a7-368">초</span><span class="sxs-lookup"><span data-stu-id="3d2a7-368">s</span></span>|<span data-ttu-id="3d2a7-369">"s"를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-369">Match an "s".</span></span>|  
|<span data-ttu-id="3d2a7-370">(\s&#124;$)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-370">(\s&#124;$)</span></span>|<span data-ttu-id="3d2a7-371">공백 문자 또는 입력 문자열의 끝을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-371">Match either a white-space character or the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
 [<span data-ttu-id="3d2a7-372">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-372">Back to Top</span></span>](#Top)  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-white-space-character-s"></a><span data-ttu-id="3d2a7-373">공백이 아닌 모든 문자: \S</span><span class="sxs-lookup"><span data-stu-id="3d2a7-373">Non-White-Space Character: \S</span></span>  
 <span data-ttu-id="3d2a7-374">`\S`는 공백 문자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-374">`\S` matches any non-white-space character.</span></span> <span data-ttu-id="3d2a7-375">`[^\f\n\r\t\v\x85\p{Z}]` 정규식 패턴과 동일하거나, 공백 문자와 일치하는 `\s`과 동일한 정규식 패턴의 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-375">It is equivalent to the `[^\f\n\r\t\v\x85\p{Z}]` regular expression pattern, or the opposite of the regular expression pattern that is equivalent to `\s`, which matches white-space characters.</span></span> <span data-ttu-id="3d2a7-376">자세한 내용은 [공백 문자: \s](#WhitespaceCharacter)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-376">For more information, see [White-Space Character: \s](#WhitespaceCharacter).</span></span>  
  
 <span data-ttu-id="3d2a7-377">ECMAScript와 호환되는 동작을 지정한 경우 `\S`는 `[^ \f\n\r\t\v]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-377">If ECMAScript-compliant behavior is specified, `\S` is equivalent to  `[^ \f\n\r\t\v]`.</span></span> <span data-ttu-id="3d2a7-378">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-378">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="3d2a7-379">다음 예제에서는 `\S` 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-379">The following example illustrates the `\S` language element.</span></span> <span data-ttu-id="3d2a7-380">정규식 패턴 `\b(\S+)\s?`는 공백 문자로 구분된 문자열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-380">The regular expression pattern `\b(\S+)\s?` matches strings that are delimited by white-space characters.</span></span> <span data-ttu-id="3d2a7-381">일치 <xref:System.Text.RegularExpressions.GroupCollection> 개체의 두 번째 요소는 일치하는 문자열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-381">The second element in the match's <xref:System.Text.RegularExpressions.GroupCollection> object contains the matched string.</span></span> <span data-ttu-id="3d2a7-382">정규식은 다음 표에 나와 있는 것처럼 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-382">The regular expression can be interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-383">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-383">Element</span></span>|<span data-ttu-id="3d2a7-384">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-384">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="3d2a7-385">단어 경계에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-385">Begin the match at a word boundary.</span></span>|  
|`(\S+)`|<span data-ttu-id="3d2a7-386">공백이 아닌 문자를 하나 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-386">Match one or more non-white-space characters.</span></span> <span data-ttu-id="3d2a7-387">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-387">This is the first capturing group.</span></span>|  
|`\s?`|<span data-ttu-id="3d2a7-388">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-388">Match zero or one white-space character.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
 [<span data-ttu-id="3d2a7-389">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-389">Back to Top</span></span>](#Top)  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a><span data-ttu-id="3d2a7-390">10진수 숫자 문자: \d</span><span class="sxs-lookup"><span data-stu-id="3d2a7-390">Decimal Digit Character: \d</span></span>  
 <span data-ttu-id="3d2a7-391">`\d`는 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-391">`\d` matches any decimal digit.</span></span> <span data-ttu-id="3d2a7-392">많은 다른 문자 집합의 10진수뿐만 아니라 표준 10진수 0-9를 포함하는 `\p{Nd}` 정규식 패턴과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-392">It is equivalent to the `\p{Nd}` regular expression pattern, which includes the standard decimal digits 0-9 as well as the decimal digits of a number of other character sets.</span></span>  
  
 <span data-ttu-id="3d2a7-393">ECMAScript와 호환되는 동작을 지정한 경우 `\d`는 `[0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-393">If ECMAScript-compliant behavior is specified, `\d` is equivalent to  `[0-9]`.</span></span> <span data-ttu-id="3d2a7-394">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-394">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="3d2a7-395">다음 예제에서는 `\d` 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-395">The following example illustrates the `\d` language element.</span></span> <span data-ttu-id="3d2a7-396">입력 문자열이 미국 및 캐나다의 올바른 전화 번호를 나타내는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-396">It tests whether an input string represents a valid telephone number in the United States and Canada.</span></span> <span data-ttu-id="3d2a7-397">정규식 패턴 `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` 는 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-397">The regular expression pattern `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-398">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-398">Element</span></span>|<span data-ttu-id="3d2a7-399">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-399">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="3d2a7-400">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-400">Begin the match at the beginning of the input string.</span></span>|  
|`\(?`|<span data-ttu-id="3d2a7-401">0개 또는 한 개의 리터럴 "(" 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-401">Match zero or one literal "(" character.</span></span>|  
|`\d{3}`|<span data-ttu-id="3d2a7-402">세 개의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-402">Match three decimal digits.</span></span>|  
|`\)?`|<span data-ttu-id="3d2a7-403">0개 또는 한 개의 리터럴 ")" 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-403">Match zero or one literal ")" character.</span></span>|  
|`[\s-]`|<span data-ttu-id="3d2a7-404">하이픈 또는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-404">Match a hyphen or a white-space character.</span></span>|  
|`(\(?\d{3}\)?[\s-])?`|<span data-ttu-id="3d2a7-405">옵션 여는 괄호에 이어 세 개의 10진수, 옵션 닫는 괄호 및 공백 문자나 하이픈 0개 또는 1개를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-405">Match an optional opening parenthesis followed by three decimal digits, an optional closing parenthesis, and either a white-space character or a hyphen zero or one time.</span></span> <span data-ttu-id="3d2a7-406">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-406">This is the first capturing group.</span></span>|  
|`\d{3}-\d{4}`|<span data-ttu-id="3d2a7-407">세 개의 10진수, 하이픈, 네 개 이상의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-407">Match three decimal digits followed by a hyphen and four more decimal digits.</span></span>|  
|`$`|<span data-ttu-id="3d2a7-408">입력 문자열의 끝 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-408">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
 [<span data-ttu-id="3d2a7-409">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-409">Back to Top</span></span>](#Top)  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a><span data-ttu-id="3d2a7-410">숫자가 아닌 문자: \D</span><span class="sxs-lookup"><span data-stu-id="3d2a7-410">Non-Digit Character: \D</span></span>  
 <span data-ttu-id="3d2a7-411">`\D`는 숫자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-411">`\D` matches any non-digit character.</span></span> <span data-ttu-id="3d2a7-412">`\P{Nd}` 정규식 패턴과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-412">It is equivalent to the `\P{Nd}` regular expression pattern.</span></span>  
  
 <span data-ttu-id="3d2a7-413">ECMAScript와 호환되는 동작을 지정한 경우 `\D`는 `[^0-9]`와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-413">If ECMAScript-compliant behavior is specified, `\D` is equivalent to  `[^0-9]`.</span></span> <span data-ttu-id="3d2a7-414">ECMAScript 정규식에 대한 자세한 내용은 [정규식 옵션](../../../docs/standard/base-types/regular-expression-options.md)에서 "ECMAScript 일치 동작" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-414">For information on ECMAScript regular expressions, see the "ECMAScript Matching Behavior" section in [Regular Expression Options](../../../docs/standard/base-types/regular-expression-options.md).</span></span>  
  
 <span data-ttu-id="3d2a7-415">다음 예제에서는 \D 언어 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-415">The following example illustrates the \D language element.</span></span> <span data-ttu-id="3d2a7-416">부품 번호 같은 문자열이 10진수 문자 및 10진수가 아닌 문자의 적절한 조합으로 구성되어 있는지 여부를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-416">It tests whether a string such as a part number consists of the appropriate combination of decimal and non-decimal characters.</span></span> <span data-ttu-id="3d2a7-417">정규식 패턴 `^\D\d{1,5}\D*$` 는 다음 테이블과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-417">The regular expression pattern `^\D\d{1,5}\D*$` is defined as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-418">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-418">Element</span></span>|<span data-ttu-id="3d2a7-419">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-419">Description</span></span>|  
|-------------|-----------------|  
|`^`|<span data-ttu-id="3d2a7-420">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-420">Begin the match at the beginning of the input string.</span></span>|  
|`\D`|<span data-ttu-id="3d2a7-421">숫자가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-421">Match a non-digit character.</span></span>|  
|`\d{1,5}`|<span data-ttu-id="3d2a7-422">1~5의 10진수를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-422">Match from one to five decimal digits.</span></span>|  
|`\D*`|<span data-ttu-id="3d2a7-423">0개 또는 하나 이상의 10진수가 아닌 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-423">Match zero, one, or more non-decimal characters.</span></span>|  
|`$`|<span data-ttu-id="3d2a7-424">입력 문자열의 끝 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-424">Match the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
 [<span data-ttu-id="3d2a7-425">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-425">Back to Top</span></span>](#Top)  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a><span data-ttu-id="3d2a7-426">지원되는 유니코드 일반 범주</span><span class="sxs-lookup"><span data-stu-id="3d2a7-426">Supported Unicode General Categories</span></span>  
 <span data-ttu-id="3d2a7-427">유니코드는 다음 표에 나와 있는 일반 범주를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-427">Unicode defines the general categories listed in the following table.</span></span> <span data-ttu-id="3d2a7-428">자세한 내용은 [유니코드 문자 데이터베이스](https://www.unicode.org/reports/tr44/)의 하위 항목인 "UCD 파일 형식"과 "일반 범주 값"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-428">For more information, see the "UCD File Format" and "General Category Values" subtopics at the [Unicode Character Database](https://www.unicode.org/reports/tr44/).</span></span>  
  
|<span data-ttu-id="3d2a7-429">범주</span><span class="sxs-lookup"><span data-stu-id="3d2a7-429">Category</span></span>|<span data-ttu-id="3d2a7-430">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-430">Description</span></span>|  
|--------------|-----------------|  
|`Lu`|<span data-ttu-id="3d2a7-431">문자, 대문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-431">Letter, Uppercase</span></span>|  
|`Ll`|<span data-ttu-id="3d2a7-432">문자, 소문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-432">Letter, Lowercase</span></span>|  
|`Lt`|<span data-ttu-id="3d2a7-433">문자, 제목 스타일</span><span class="sxs-lookup"><span data-stu-id="3d2a7-433">Letter, Titlecase</span></span>|  
|`Lm`|<span data-ttu-id="3d2a7-434">문자, 한정자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-434">Letter, Modifier</span></span>|  
|`Lo`|<span data-ttu-id="3d2a7-435">문자, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-435">Letter, Other</span></span>|  
|`L`|<span data-ttu-id="3d2a7-436">모든 문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-436">All letter characters.</span></span> <span data-ttu-id="3d2a7-437">여기에는 `Lu`, `Ll`, `Lt`, `Lm` 및 `Lo` 문자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-437">This includes the `Lu`, `Ll`, `Lt`, `Lm`, and `Lo` characters.</span></span>|  
|`Mn`|<span data-ttu-id="3d2a7-438">표시, 공백 없음</span><span class="sxs-lookup"><span data-stu-id="3d2a7-438">Mark, Nonspacing</span></span>|  
|`Mc`|<span data-ttu-id="3d2a7-439">표시, 공백 조합</span><span class="sxs-lookup"><span data-stu-id="3d2a7-439">Mark, Spacing Combining</span></span>|  
|`Me`|<span data-ttu-id="3d2a7-440">표시, 묶기</span><span class="sxs-lookup"><span data-stu-id="3d2a7-440">Mark, Enclosing</span></span>|  
|`M`|<span data-ttu-id="3d2a7-441">모든 분음 기호</span><span class="sxs-lookup"><span data-stu-id="3d2a7-441">All diacritic marks.</span></span> <span data-ttu-id="3d2a7-442">여기에는 `Mn`, `Mc` 및 `Me` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-442">This includes the `Mn`, `Mc`, and `Me` categories.</span></span>|  
|`Nd`|<span data-ttu-id="3d2a7-443">숫자, 10진수</span><span class="sxs-lookup"><span data-stu-id="3d2a7-443">Number, Decimal Digit</span></span>|  
|`Nl`|<span data-ttu-id="3d2a7-444">숫자, 문자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-444">Number, Letter</span></span>|  
|`No`|<span data-ttu-id="3d2a7-445">숫자, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-445">Number, Other</span></span>|  
|`N`|<span data-ttu-id="3d2a7-446">모든 숫자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-446">All numbers.</span></span> <span data-ttu-id="3d2a7-447">여기에는 `Nd`, `Nl` 및 `No` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-447">This includes the `Nd`, `Nl`, and `No` categories.</span></span>|  
|`Pc`|<span data-ttu-id="3d2a7-448">문장 부호, 연결자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-448">Punctuation, Connector</span></span>|  
|`Pd`|<span data-ttu-id="3d2a7-449">문장 부호, 대시</span><span class="sxs-lookup"><span data-stu-id="3d2a7-449">Punctuation, Dash</span></span>|  
|`Ps`|<span data-ttu-id="3d2a7-450">문장 부호, 열기</span><span class="sxs-lookup"><span data-stu-id="3d2a7-450">Punctuation, Open</span></span>|  
|`Pe`|<span data-ttu-id="3d2a7-451">문장 부호, 닫기</span><span class="sxs-lookup"><span data-stu-id="3d2a7-451">Punctuation, Close</span></span>|  
|`Pi`|<span data-ttu-id="3d2a7-452">문장 부호, 처음 따옴표(사용 방식에 따라 Ps 또는 Pe와 같이 동작)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-452">Punctuation, Initial quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Pf`|<span data-ttu-id="3d2a7-453">문장 부호, 마지막 따옴표(사용 방식에 따라 Ps 또는 Pe와 같이 동작)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-453">Punctuation, Final quote (may behave like Ps or Pe depending on usage)</span></span>|  
|`Po`|<span data-ttu-id="3d2a7-454">문장 부호, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-454">Punctuation, Other</span></span>|  
|`P`|<span data-ttu-id="3d2a7-455">모든 구두점 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-455">All punctuation characters.</span></span> <span data-ttu-id="3d2a7-456">여기에는 `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf` 및 `Po` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-456">This includes the `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf`, and `Po` categories.</span></span>|  
|`Sm`|<span data-ttu-id="3d2a7-457">기호, 수학</span><span class="sxs-lookup"><span data-stu-id="3d2a7-457">Symbol, Math</span></span>|  
|`Sc`|<span data-ttu-id="3d2a7-458">기호, 통화</span><span class="sxs-lookup"><span data-stu-id="3d2a7-458">Symbol, Currency</span></span>|  
|`Sk`|<span data-ttu-id="3d2a7-459">기호, 한정자</span><span class="sxs-lookup"><span data-stu-id="3d2a7-459">Symbol, Modifier</span></span>|  
|`So`|<span data-ttu-id="3d2a7-460">기호, 기타</span><span class="sxs-lookup"><span data-stu-id="3d2a7-460">Symbol, Other</span></span>|  
|`S`|<span data-ttu-id="3d2a7-461">모든 기호.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-461">All symbols.</span></span> <span data-ttu-id="3d2a7-462">여기에는 `Sm`, `Sc`, `Sk` 및 `So` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-462">This includes the `Sm`, `Sc`, `Sk`, and `So` categories.</span></span>|  
|`Zs`|<span data-ttu-id="3d2a7-463">구분 기호, 공백</span><span class="sxs-lookup"><span data-stu-id="3d2a7-463">Separator, Space</span></span>|  
|`Zl`|<span data-ttu-id="3d2a7-464">구분 기호, 줄</span><span class="sxs-lookup"><span data-stu-id="3d2a7-464">Separator, Line</span></span>|  
|`Zp`|<span data-ttu-id="3d2a7-465">구분 기호, 단락</span><span class="sxs-lookup"><span data-stu-id="3d2a7-465">Separator, Paragraph</span></span>|  
|`Z`|<span data-ttu-id="3d2a7-466">모든 구분 기호 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-466">All separator characters.</span></span> <span data-ttu-id="3d2a7-467">여기에는 `Zs`, `Zl` 및 `Zp` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-467">This includes the `Zs`, `Zl`, and `Zp` categories.</span></span>|  
|`Cc`|<span data-ttu-id="3d2a7-468">기타, 제어</span><span class="sxs-lookup"><span data-stu-id="3d2a7-468">Other, Control</span></span>|  
|`Cf`|<span data-ttu-id="3d2a7-469">기타, 서식</span><span class="sxs-lookup"><span data-stu-id="3d2a7-469">Other, Format</span></span>|  
|`Cs`|<span data-ttu-id="3d2a7-470">기타, 서로게이트</span><span class="sxs-lookup"><span data-stu-id="3d2a7-470">Other, Surrogate</span></span>|  
|`Co`|<span data-ttu-id="3d2a7-471">기타, 전용 항목</span><span class="sxs-lookup"><span data-stu-id="3d2a7-471">Other, Private Use</span></span>|  
|`Cn`|<span data-ttu-id="3d2a7-472">기타, 지정되지 않음(이 속성을 가진 문자가 없음)</span><span class="sxs-lookup"><span data-stu-id="3d2a7-472">Other, Not Assigned (no characters have this property)</span></span>|  
|`C`|<span data-ttu-id="3d2a7-473">모든 제어 문자.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-473">All control characters.</span></span> <span data-ttu-id="3d2a7-474">여기에는 `Cc`, `Cf`, `Cs`, `Co` 및 `Cn` 범주가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-474">This includes the `Cc`, `Cf`, `Cs`, `Co`, and `Cn` categories.</span></span>|  
  
 <span data-ttu-id="3d2a7-475">해당 문자를 <xref:System.Char.GetUnicodeCategory%2A> 메서드로 전달하여 특정 문자의 유니코드 범주를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-475">You can determine the Unicode category of any particular character by passing that character to the <xref:System.Char.GetUnicodeCategory%2A> method.</span></span> <span data-ttu-id="3d2a7-476">다음 예제에서는 <xref:System.Char.GetUnicodeCategory%2A> 메서드를 사용하여 선택한 라틴 문자를 포함하는 배열에서 각 요소의 범주를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-476">The following example uses the <xref:System.Char.GetUnicodeCategory%2A> method to determine the category of each element in an array that contains selected Latin characters.</span></span>  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
 [<span data-ttu-id="3d2a7-477">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-477">Back to Top</span></span>](#Top)  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a><span data-ttu-id="3d2a7-478">지원되는 명명된 블록</span><span class="sxs-lookup"><span data-stu-id="3d2a7-478">Supported Named Blocks</span></span>  
 <span data-ttu-id="3d2a7-479">.NET에서는 다음 표에 나와 있는 명명된 블록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-479">.NET provides the named blocks listed in the following table.</span></span> <span data-ttu-id="3d2a7-480">지원되는 명명된 블록 집합은 유니코드 4.0 및 Perl 5.6을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-480">The set of supported named blocks is based on Unicode 4.0 and Perl 5.6.</span></span>  
  
|<span data-ttu-id="3d2a7-481">코드 포인트 범위</span><span class="sxs-lookup"><span data-stu-id="3d2a7-481">Code point range</span></span>|<span data-ttu-id="3d2a7-482">블록 이름</span><span class="sxs-lookup"><span data-stu-id="3d2a7-482">Block name</span></span>|  
|----------------------|----------------|  
|<span data-ttu-id="3d2a7-483">0000 - 007F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-483">0000 - 007F</span></span>|`IsBasicLatin`|  
|<span data-ttu-id="3d2a7-484">0080 - 00FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-484">0080 - 00FF</span></span>|`IsLatin-1Supplement`|  
|<span data-ttu-id="3d2a7-485">0100 - 017F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-485">0100 - 017F</span></span>|`IsLatinExtended-A`|  
|<span data-ttu-id="3d2a7-486">0180 - 024F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-486">0180 - 024F</span></span>|`IsLatinExtended-B`|  
|<span data-ttu-id="3d2a7-487">0250 - 02AF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-487">0250 - 02AF</span></span>|`IsIPAExtensions`|  
|<span data-ttu-id="3d2a7-488">02B0 - 02FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-488">02B0 - 02FF</span></span>|`IsSpacingModifierLetters`|  
|<span data-ttu-id="3d2a7-489">0300 - 036F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-489">0300 - 036F</span></span>|`IsCombiningDiacriticalMarks`|  
|<span data-ttu-id="3d2a7-490">0370 - 03FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-490">0370 - 03FF</span></span>|`IsGreek`<br /><br /> <span data-ttu-id="3d2a7-491">또는</span><span class="sxs-lookup"><span data-stu-id="3d2a7-491">-or-</span></span><br /><br /> `IsGreekandCoptic`|  
|<span data-ttu-id="3d2a7-492">0400 - 04FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-492">0400 - 04FF</span></span>|`IsCyrillic`|  
|<span data-ttu-id="3d2a7-493">0500 - 052F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-493">0500 - 052F</span></span>|`IsCyrillicSupplement`|  
|<span data-ttu-id="3d2a7-494">0530 - 058F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-494">0530 - 058F</span></span>|`IsArmenian`|  
|<span data-ttu-id="3d2a7-495">0590 - 05FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-495">0590 - 05FF</span></span>|`IsHebrew`|  
|<span data-ttu-id="3d2a7-496">0600 - 06FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-496">0600 - 06FF</span></span>|`IsArabic`|  
|<span data-ttu-id="3d2a7-497">0700 - 074F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-497">0700 - 074F</span></span>|`IsSyriac`|  
|<span data-ttu-id="3d2a7-498">0780 - 07BF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-498">0780 - 07BF</span></span>|`IsThaana`|  
|<span data-ttu-id="3d2a7-499">0900 - 097F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-499">0900 - 097F</span></span>|`IsDevanagari`|  
|<span data-ttu-id="3d2a7-500">0980 - 09FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-500">0980 - 09FF</span></span>|`IsBengali`|  
|<span data-ttu-id="3d2a7-501">0A00 - 0A7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-501">0A00 - 0A7F</span></span>|`IsGurmukhi`|  
|<span data-ttu-id="3d2a7-502">0A80 - 0AFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-502">0A80 - 0AFF</span></span>|`IsGujarati`|  
|<span data-ttu-id="3d2a7-503">0B00 - 0B7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-503">0B00 - 0B7F</span></span>|`IsOriya`|  
|<span data-ttu-id="3d2a7-504">0B80 - 0BFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-504">0B80 - 0BFF</span></span>|`IsTamil`|  
|<span data-ttu-id="3d2a7-505">0C00 - 0C7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-505">0C00 - 0C7F</span></span>|`IsTelugu`|  
|<span data-ttu-id="3d2a7-506">0C80 - 0CFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-506">0C80 - 0CFF</span></span>|`IsKannada`|  
|<span data-ttu-id="3d2a7-507">0D00 - 0D7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-507">0D00 - 0D7F</span></span>|`IsMalayalam`|  
|<span data-ttu-id="3d2a7-508">0D80 - 0DFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-508">0D80 - 0DFF</span></span>|`IsSinhala`|  
|<span data-ttu-id="3d2a7-509">0E00 - 0E7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-509">0E00 - 0E7F</span></span>|`IsThai`|  
|<span data-ttu-id="3d2a7-510">0E80 - 0EFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-510">0E80 - 0EFF</span></span>|`IsLao`|  
|<span data-ttu-id="3d2a7-511">0F00 - 0FFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-511">0F00 - 0FFF</span></span>|`IsTibetan`|  
|<span data-ttu-id="3d2a7-512">1000 - 109F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-512">1000 - 109F</span></span>|`IsMyanmar`|  
|<span data-ttu-id="3d2a7-513">10A0 - 10FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-513">10A0 - 10FF</span></span>|`IsGeorgian`|  
|<span data-ttu-id="3d2a7-514">1100 - 11FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-514">1100 - 11FF</span></span>|`IsHangulJamo`|  
|<span data-ttu-id="3d2a7-515">1200 - 137F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-515">1200 - 137F</span></span>|`IsEthiopic`|  
|<span data-ttu-id="3d2a7-516">13A0 - 13FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-516">13A0 - 13FF</span></span>|`IsCherokee`|  
|<span data-ttu-id="3d2a7-517">1400 - 167F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-517">1400 - 167F</span></span>|`IsUnifiedCanadianAboriginalSyllabics`|  
|<span data-ttu-id="3d2a7-518">1680 - 169F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-518">1680 - 169F</span></span>|`IsOgham`|  
|<span data-ttu-id="3d2a7-519">16A0 - 16FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-519">16A0 - 16FF</span></span>|`IsRunic`|  
|<span data-ttu-id="3d2a7-520">1700 - 171F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-520">1700 - 171F</span></span>|`IsTagalog`|  
|<span data-ttu-id="3d2a7-521">1720 - 173F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-521">1720 - 173F</span></span>|`IsHanunoo`|  
|<span data-ttu-id="3d2a7-522">1740 - 175F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-522">1740 - 175F</span></span>|`IsBuhid`|  
|<span data-ttu-id="3d2a7-523">1760 - 177F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-523">1760 - 177F</span></span>|`IsTagbanwa`|  
|<span data-ttu-id="3d2a7-524">1780 - 17FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-524">1780 - 17FF</span></span>|`IsKhmer`|  
|<span data-ttu-id="3d2a7-525">1800 - 18AF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-525">1800 - 18AF</span></span>|`IsMongolian`|  
|<span data-ttu-id="3d2a7-526">1900 - 194F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-526">1900 - 194F</span></span>|`IsLimbu`|  
|<span data-ttu-id="3d2a7-527">1950 - 197F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-527">1950 - 197F</span></span>|`IsTaiLe`|  
|<span data-ttu-id="3d2a7-528">19E0 - 19FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-528">19E0 - 19FF</span></span>|`IsKhmerSymbols`|  
|<span data-ttu-id="3d2a7-529">1D00 - 1D7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-529">1D00 - 1D7F</span></span>|`IsPhoneticExtensions`|  
|<span data-ttu-id="3d2a7-530">1E00 - 1EFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-530">1E00 - 1EFF</span></span>|`IsLatinExtendedAdditional`|  
|<span data-ttu-id="3d2a7-531">1F00 - 1FFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-531">1F00 - 1FFF</span></span>|`IsGreekExtended`|  
|<span data-ttu-id="3d2a7-532">2000 - 206F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-532">2000 - 206F</span></span>|`IsGeneralPunctuation`|  
|<span data-ttu-id="3d2a7-533">2070 - 209F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-533">2070 - 209F</span></span>|`IsSuperscriptsandSubscripts`|  
|<span data-ttu-id="3d2a7-534">20A0 - 20CF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-534">20A0 - 20CF</span></span>|`IsCurrencySymbols`|  
|<span data-ttu-id="3d2a7-535">20D0 - 20FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-535">20D0 - 20FF</span></span>|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> <span data-ttu-id="3d2a7-536">또는</span><span class="sxs-lookup"><span data-stu-id="3d2a7-536">-or-</span></span><br /><br /> `IsCombiningMarksforSymbols`|  
|<span data-ttu-id="3d2a7-537">2100 - 214F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-537">2100 - 214F</span></span>|`IsLetterlikeSymbols`|  
|<span data-ttu-id="3d2a7-538">2150 - 218F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-538">2150 - 218F</span></span>|`IsNumberForms`|  
|<span data-ttu-id="3d2a7-539">2190 - 21FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-539">2190 - 21FF</span></span>|`IsArrows`|  
|<span data-ttu-id="3d2a7-540">2200 - 22FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-540">2200 - 22FF</span></span>|`IsMathematicalOperators`|  
|<span data-ttu-id="3d2a7-541">2300 - 23FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-541">2300 - 23FF</span></span>|`IsMiscellaneousTechnical`|  
|<span data-ttu-id="3d2a7-542">2400 - 243F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-542">2400 - 243F</span></span>|`IsControlPictures`|  
|<span data-ttu-id="3d2a7-543">2440 - 245F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-543">2440 - 245F</span></span>|`IsOpticalCharacterRecognition`|  
|<span data-ttu-id="3d2a7-544">2460 - 24FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-544">2460 - 24FF</span></span>|`IsEnclosedAlphanumerics`|  
|<span data-ttu-id="3d2a7-545">2500 - 257F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-545">2500 - 257F</span></span>|`IsBoxDrawing`|  
|<span data-ttu-id="3d2a7-546">2580 - 259F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-546">2580 - 259F</span></span>|`IsBlockElements`|  
|<span data-ttu-id="3d2a7-547">25A0 - 25FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-547">25A0 - 25FF</span></span>|`IsGeometricShapes`|  
|<span data-ttu-id="3d2a7-548">2600 - 26FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-548">2600 - 26FF</span></span>|`IsMiscellaneousSymbols`|  
|<span data-ttu-id="3d2a7-549">2700 - 27BF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-549">2700 - 27BF</span></span>|`IsDingbats`|  
|<span data-ttu-id="3d2a7-550">27C0 - 27EF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-550">27C0 - 27EF</span></span>|`IsMiscellaneousMathematicalSymbols-A`|  
|<span data-ttu-id="3d2a7-551">27F0 - 27FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-551">27F0 - 27FF</span></span>|`IsSupplementalArrows-A`|  
|<span data-ttu-id="3d2a7-552">2800 - 28FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-552">2800 - 28FF</span></span>|`IsBraillePatterns`|  
|<span data-ttu-id="3d2a7-553">2900 - 297F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-553">2900 - 297F</span></span>|`IsSupplementalArrows-B`|  
|<span data-ttu-id="3d2a7-554">2980 - 29FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-554">2980 - 29FF</span></span>|`IsMiscellaneousMathematicalSymbols-B`|  
|<span data-ttu-id="3d2a7-555">2A00 - 2AFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-555">2A00 - 2AFF</span></span>|`IsSupplementalMathematicalOperators`|  
|<span data-ttu-id="3d2a7-556">2B00 - 2BFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-556">2B00 - 2BFF</span></span>|`IsMiscellaneousSymbolsandArrows`|  
|<span data-ttu-id="3d2a7-557">2E80 - 2EFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-557">2E80 - 2EFF</span></span>|`IsCJKRadicalsSupplement`|  
|<span data-ttu-id="3d2a7-558">2F00 - 2FDF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-558">2F00 - 2FDF</span></span>|`IsKangxiRadicals`|  
|<span data-ttu-id="3d2a7-559">2FF0 - 2FFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-559">2FF0 - 2FFF</span></span>|`IsIdeographicDescriptionCharacters`|  
|<span data-ttu-id="3d2a7-560">3000 - 303F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-560">3000 - 303F</span></span>|`IsCJKSymbolsandPunctuation`|  
|<span data-ttu-id="3d2a7-561">3040 - 309F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-561">3040 - 309F</span></span>|`IsHiragana`|  
|<span data-ttu-id="3d2a7-562">30A0 - 30FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-562">30A0 - 30FF</span></span>|`IsKatakana`|  
|<span data-ttu-id="3d2a7-563">3100 - 312F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-563">3100 - 312F</span></span>|`IsBopomofo`|  
|<span data-ttu-id="3d2a7-564">3130 - 318F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-564">3130 - 318F</span></span>|`IsHangulCompatibilityJamo`|  
|<span data-ttu-id="3d2a7-565">3190 - 319F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-565">3190 - 319F</span></span>|`IsKanbun`|  
|<span data-ttu-id="3d2a7-566">31A0 - 31BF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-566">31A0 - 31BF</span></span>|`IsBopomofoExtended`|  
|<span data-ttu-id="3d2a7-567">31F0 - 31FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-567">31F0 - 31FF</span></span>|`IsKatakanaPhoneticExtensions`|  
|<span data-ttu-id="3d2a7-568">3200 - 32FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-568">3200 - 32FF</span></span>|`IsEnclosedCJKLettersandMonths`|  
|<span data-ttu-id="3d2a7-569">3300 - 33FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-569">3300 - 33FF</span></span>|`IsCJKCompatibility`|  
|<span data-ttu-id="3d2a7-570">3400 - 4DBF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-570">3400 - 4DBF</span></span>|`IsCJKUnifiedIdeographsExtensionA`|  
|<span data-ttu-id="3d2a7-571">4DC0 - 4DFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-571">4DC0 - 4DFF</span></span>|`IsYijingHexagramSymbols`|  
|<span data-ttu-id="3d2a7-572">4E00 - 9FFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-572">4E00 - 9FFF</span></span>|`IsCJKUnifiedIdeographs`|  
|<span data-ttu-id="3d2a7-573">A000 - A48F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-573">A000 - A48F</span></span>|`IsYiSyllables`|  
|<span data-ttu-id="3d2a7-574">A490 - A4CF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-574">A490 - A4CF</span></span>|`IsYiRadicals`|  
|<span data-ttu-id="3d2a7-575">AC00 - D7AF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-575">AC00 - D7AF</span></span>|`IsHangulSyllables`|  
|<span data-ttu-id="3d2a7-576">D800 - DB7F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-576">D800 - DB7F</span></span>|`IsHighSurrogates`|  
|<span data-ttu-id="3d2a7-577">DB80 - DBFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-577">DB80 - DBFF</span></span>|`IsHighPrivateUseSurrogates`|  
|<span data-ttu-id="3d2a7-578">DC00 - DFFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-578">DC00 - DFFF</span></span>|`IsLowSurrogates`|  
|<span data-ttu-id="3d2a7-579">E000 - F8FF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-579">E000 - F8FF</span></span>|<span data-ttu-id="3d2a7-580">`IsPrivateUse` 또는 `IsPrivateUseArea`</span><span class="sxs-lookup"><span data-stu-id="3d2a7-580">`IsPrivateUse` or `IsPrivateUseArea`</span></span>|  
|<span data-ttu-id="3d2a7-581">F900 - FAFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-581">F900 - FAFF</span></span>|`IsCJKCompatibilityIdeographs`|  
|<span data-ttu-id="3d2a7-582">FB00 - FB4F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-582">FB00 - FB4F</span></span>|`IsAlphabeticPresentationForms`|  
|<span data-ttu-id="3d2a7-583">FB50 - FDFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-583">FB50 - FDFF</span></span>|`IsArabicPresentationForms-A`|  
|<span data-ttu-id="3d2a7-584">FE00 - FE0F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-584">FE00 - FE0F</span></span>|`IsVariationSelectors`|  
|<span data-ttu-id="3d2a7-585">FE20 - FE2F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-585">FE20 - FE2F</span></span>|`IsCombiningHalfMarks`|  
|<span data-ttu-id="3d2a7-586">FE30 - FE4F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-586">FE30 - FE4F</span></span>|`IsCJKCompatibilityForms`|  
|<span data-ttu-id="3d2a7-587">FE50 - FE6F</span><span class="sxs-lookup"><span data-stu-id="3d2a7-587">FE50 - FE6F</span></span>|`IsSmallFormVariants`|  
|<span data-ttu-id="3d2a7-588">FE70 - FEFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-588">FE70 - FEFF</span></span>|`IsArabicPresentationForms-B`|  
|<span data-ttu-id="3d2a7-589">FF00 - FFEF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-589">FF00 - FFEF</span></span>|`IsHalfwidthandFullwidthForms`|  
|<span data-ttu-id="3d2a7-590">FFF0 - FFFF</span><span class="sxs-lookup"><span data-stu-id="3d2a7-590">FFF0 - FFFF</span></span>|`IsSpecials`|  
  
 [<span data-ttu-id="3d2a7-591">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="3d2a7-591">Back to Top</span></span>](#Top)  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-basegroup---excludedgroup"></a><span data-ttu-id="3d2a7-592">문자 클래스 빼기: [base_group - [excluded_group]]</span><span class="sxs-lookup"><span data-stu-id="3d2a7-592">Character Class Subtraction: [base_group - [excluded_group]]</span></span>  
 <span data-ttu-id="3d2a7-593">문자 클래스는 문자 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-593">A character class defines a set of characters.</span></span> <span data-ttu-id="3d2a7-594">문자 클래스 빼기는 한 문자 클래스에서 다른 문자 클래스의 문자를 제외한 결과로 문자 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-594">Character class subtraction yields a set of characters that is the result of excluding the characters in one character class from another character class.</span></span>  
  
 <span data-ttu-id="3d2a7-595">문자 클래스 빼기 식의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-595">A character class subtraction expression has the following form:</span></span>  
  
 <span data-ttu-id="3d2a7-596">`[` *base_group* `-[` *excluded_group* `]]`</span><span class="sxs-lookup"><span data-stu-id="3d2a7-596">`[` *base_group* `-[` *excluded_group* `]]`</span></span>  
  
 <span data-ttu-id="3d2a7-597">대괄호(`[]`)와 하이픈(`-`)은 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-597">The square brackets (`[]`) and hyphen (`-`) are mandatory.</span></span> <span data-ttu-id="3d2a7-598">*base_group*은 [긍정 문자 그룹](#PositiveGroup) 또는 [부정 문자 그룹](#NegativeGroup)입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-598">The *base_group* is a [positive character group](#PositiveGroup) or a [negative character group](#NegativeGroup).</span></span> <span data-ttu-id="3d2a7-599">*excluded_group* 구성 요소는 다른 긍정 또는 부정 문자 그룹이거나 다른 문자 클래스 빼기 식입니다. 즉, 문자 클래스 빼기 식을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-599">The *excluded_group* component is another positive or negative character group, or another character class subtraction expression (that is, you can nest character class subtraction expressions).</span></span>  
  
 <span data-ttu-id="3d2a7-600">예를 들어, "a"부터 "z"까지의 문자 범위로 구성된 기본 그룹이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-600">For example, suppose you have a base group that consists of the character range from "a" through "z".</span></span> <span data-ttu-id="3d2a7-601">문자 "m"을 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[m]]`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-601">To define the set of characters that consists of the base group except for the character "m", use `[a-z-[m]]`.</span></span> <span data-ttu-id="3d2a7-602">문자 "d", "j" 및 "p"를 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[djp]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-602">To define the set of characters that consists of the base group except for the set of characters "d", "j", and "p", use `[a-z-[djp]]`.</span></span> <span data-ttu-id="3d2a7-603">"m"부터 "p"까지의 문자 범위를 제외한 기본 그룹으로 구성된 문자 집합을 정의하려면 `[a-z-[m-p]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-603">To define the set of characters that consists of the base group except for the character range from "m" through "p", use `[a-z-[m-p]]`.</span></span>  
  
 <span data-ttu-id="3d2a7-604">중첩된 문자 클래스 빼기 식인 `[a-z-[d-w-[m-o]]]`를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-604">Consider the nested character class subtraction expression, `[a-z-[d-w-[m-o]]]`.</span></span> <span data-ttu-id="3d2a7-605">가장 안쪽 문자 범위에서 바깥쪽으로 식이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-605">The expression is evaluated from the innermost character range outward.</span></span> <span data-ttu-id="3d2a7-606">먼저 'd'부터 'w'까지의 문자 범위에서 "m"부터 "o"까지의 문자 범위를 뺍니다. 그러면 "d"부터 "l"까지와 "p"부터 "w"까지의 문자로 구성된 문자 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-606">First, the character range from "m" through "o" is subtracted from the character range "d" through "w", which yields the set of characters from "d" through "l" and "p" through "w".</span></span> <span data-ttu-id="3d2a7-607">그런 다음 "a"부터 "z"까지의 문자 범위에서 이 집합을 뺍니다. 그러면 문자 집합 `[abcmnoxyz]`가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-607">That set is then subtracted from the character range from "a" through "z", which yields the set of characters `[abcmnoxyz]`.</span></span>  
  
 <span data-ttu-id="3d2a7-608">모든 문자 클래스에 문자 클래스 빼기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-608">You can use any character class with character class subtraction.</span></span> <span data-ttu-id="3d2a7-609">\u0000부터 \uFFFF까지의 문자에서 공백 문자(`\s`), 문장 부호 일반 범주의 문자(`\p{P}`), 명명된 블록 `IsGreek`의 문자(`\p{IsGreek}`) 및 유니코드 NEXT LINE 제어 문자(\x85)를 제외한 모든 유니코드 문자로 구성된 문자 집합을 정의하려면 `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-609">To define the set of characters that consists of all Unicode characters from \u0000 through \uFFFF except white-space characters (`\s`), the characters in the punctuation general category (`\p{P}`), the characters in the `IsGreek` named block (`\p{IsGreek}`), and the Unicode NEXT LINE control character (\x85), use `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.</span></span>  
  
 <span data-ttu-id="3d2a7-610">문자 클래스 빼기 식에 사용할 문자 클래스를 선택할 때는 유용한 결과를 생성할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-610">Choose character classes for a character class subtraction expression that will yield useful results.</span></span> <span data-ttu-id="3d2a7-611">어떤 문자도 나타낼 수 없는 빈 문자 집합을 생성하는 식이나 원래 기본 그룹에 해당하는 식은 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-611">Avoid an expression that yields an empty set of characters, which cannot match anything, or an expression that is equivalent to the original base group.</span></span> <span data-ttu-id="3d2a7-612">예를 들어, `IsBasicLatin` 일반 범주에서 `IsBasicLatin` 문자 범위의 모든 문자를 빼는 `[\p{IsBasicLatin}-[\x00-\x7F]]` 식을 사용하면 빈 집합이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-612">For example, the empty set is the result of the expression `[\p{IsBasicLatin}-[\x00-\x7F]]`, which subtracts all characters in the `IsBasicLatin` character range from the `IsBasicLatin` general category.</span></span> <span data-ttu-id="3d2a7-613">마찬가지로 `[a-z-[0-9]]` 식을 사용하면 원래 기본 그룹이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-613">Similarly, the original base group is the result of the expression `[a-z-[0-9]]`.</span></span>  <span data-ttu-id="3d2a7-614">"a"부터 "z"까지의 문자 범위를 나타내는 기본 그룹에는 제외할 그룹의 문자, 즉 "0"부터 "9"까지의 10진수 문자 범위가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-614">This is because the base group, which is the character range of letters from "a" through "z", does not contain any characters in the excluded group, which is the character range of decimal digits from "0" through "9".</span></span>  
  
 <span data-ttu-id="3d2a7-615">다음 예제에서는 입력 문자열에서 0과 홀수를 찾는 정규식 `^[0-9-[2468]]+$`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-615">The following example defines a regular expression, `^[0-9-[2468]]+$`, that matches zero and odd digits in an input string.</span></span>  <span data-ttu-id="3d2a7-616">정규식은 다음 표와 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-616">The regular expression is interpreted as shown in the following table.</span></span>  
  
|<span data-ttu-id="3d2a7-617">요소</span><span class="sxs-lookup"><span data-stu-id="3d2a7-617">Element</span></span>|<span data-ttu-id="3d2a7-618">설명</span><span class="sxs-lookup"><span data-stu-id="3d2a7-618">Description</span></span>|  
|-------------|-----------------|  
|^|<span data-ttu-id="3d2a7-619">입력 문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-619">Begin the match at the start of the input string.</span></span>|  
|`[0-9-[2468]]+`|<span data-ttu-id="3d2a7-620">모든 문자 0에서 9까지 2, 4, 6 및 8을 제외한 하나 이상의 항목을 일치하세요.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-620">Match one or more occurrences of any character from 0 to 9 except for 2, 4, 6, and 8.</span></span> <span data-ttu-id="3d2a7-621">즉, 한 번 이상 나오는 0 또는 홀수와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-621">In other words, match one or more occurrences of zero or an odd digit.</span></span>|  
|$|<span data-ttu-id="3d2a7-622">입력 문자열의 끝 부분에서 검색을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3d2a7-622">End the match at the end of the input string.</span></span>|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="3d2a7-623">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d2a7-623">See also</span></span>

- <xref:System.Char.GetUnicodeCategory%2A>
- [<span data-ttu-id="3d2a7-624">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="3d2a7-624">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [<span data-ttu-id="3d2a7-625">정규식 옵션</span><span class="sxs-lookup"><span data-stu-id="3d2a7-625">Regular Expression Options</span></span>](../../../docs/standard/base-types/regular-expression-options.md)
