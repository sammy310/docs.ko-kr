---
title: 문자열을 부분 문자열로 분리
description: String.Split, 정규식, String.Substring 등 문자열의 일부를 추출하는 다양한 방법에 대해 알아봅니다.
ms.date: 10/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], breaking up
ms.openlocfilehash: 88947c4576b0496e4b4e45042d665e3ca5857c53
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93403483"
---
# <a name="extract-substrings-from-a-string"></a><span data-ttu-id="f18f6-103">문자열에서 부분 문자열 추출</span><span class="sxs-lookup"><span data-stu-id="f18f6-103">Extract substrings from a string</span></span>

<span data-ttu-id="f18f6-104">이 문서에서는 문자열의 일부를 추출하는 몇 가지 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-104">This article covers some different techniques for extracting parts of a string.</span></span>

- <span data-ttu-id="f18f6-105">원하는 부분 문자열이 알려진 구분 문자(또는 문자)로 구분된 경우 [Split 메서드](#stringsplit-method)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-105">Use the [Split method](#stringsplit-method) when the substrings you want are separated by a known delimiting character (or characters).</span></span>
- <span data-ttu-id="f18f6-106">[정규식](#regular-expressions)은 문자열이 고정 패턴을 준수하는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-106">[Regular expressions](#regular-expressions) are useful when the string conforms to a fixed pattern.</span></span>
- <span data-ttu-id="f18f6-107">문자열의 모든 부분 문자열을 추출하려는 것이 아니라면 [IndexOf 메서드와 Substring 메서드](#stringindexof-and-stringsubstring-methods)를 함께 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="f18f6-107">Use the [IndexOf and Substring methods](#stringindexof-and-stringsubstring-methods) in conjunction when you don't want to extract *all* of the substrings in a string.</span></span>

## <a name="stringsplit-method"></a><span data-ttu-id="f18f6-108">String.Split 메서드</span><span class="sxs-lookup"><span data-stu-id="f18f6-108">String.Split method</span></span>

<span data-ttu-id="f18f6-109"><xref:System.String.Split%2A?displayProperty=nameWithType>은 지정하는 하나 이상의 구분 문자에 따라 문자열을 부분 문자열 그룹으로 분할하는 데 도움이 되는 몇 가지 오버로드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-109"><xref:System.String.Split%2A?displayProperty=nameWithType> provides a handful of overloads to help you break up a string into a group of substrings based on one or more delimiting characters that you specify.</span></span> <span data-ttu-id="f18f6-110">최종 결과에서 전체 부분 문자열 수를 제한하거나, 부분 문자열에서 공백 문자를 자르거나, 빈 부분 문자열을 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-110">You can choose to limit the total number of substrings in the final result, trim white-space characters from substrings, or exclude empty substrings.</span></span>

<span data-ttu-id="f18f6-111">다음 예제는 `String.Split()`의 세 가지 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-111">The following examples show three different overloads of `String.Split()`.</span></span> <span data-ttu-id="f18f6-112">첫 번째 예제는 구분 문자를 전달하지 않고 <xref:System.String.Split(System.Char[])> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-112">The first example calls the <xref:System.String.Split(System.Char[])> overload without passing any separator characters.</span></span> <span data-ttu-id="f18f6-113">구분 문자를 지정하지 않으면 `String.Split()`은 공백 문자인 기본 구분 기호를 사용하여 문자열을 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-113">When you don't specify any delimiting characters, `String.Split()` uses default delimiters, which are white-space characters, to split up the string.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#1)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="1":::

<span data-ttu-id="f18f6-114">여기에서 볼 수 있듯이 마침표 문자(`.`)가 두 부분 문자열에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-114">As you can see, the period characters (`.`) are included in two of the substrings.</span></span> <span data-ttu-id="f18f6-115">마침표 문자를 제외하려는 경우 마침표 문자를 추가 구분 문자로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-115">If you want to exclude the period characters, you can add the period character as an additional delimiting character.</span></span> <span data-ttu-id="f18f6-116">다음 예제는 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-116">The next example shows how to do this.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#2)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="2":::

<span data-ttu-id="f18f6-117">부분 문자열에서 마침표가 사라졌지만 이제는 두 개의 빈 부분 문자열이 추가로 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-117">The periods are gone from the substrings, but now two extra empty substrings have been included.</span></span> <span data-ttu-id="f18f6-118">이러한 빈 부분 문자열은 단어와 그 뒤에 오는 마침표 사이의 부분 문자열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-118">These empty substring represent the substring between the word and the period that follows it.</span></span> <span data-ttu-id="f18f6-119">결과 배열에서 빈 부분 문자열을 생략하려면 <xref:System.String.Split(System.Char[],System.StringSplitOptions)> 오버로드를 호출하고 `options` 매개 변수의 <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType>을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-119">To omit empty substrings from the resulting array, you can call the <xref:System.String.Split(System.Char[],System.StringSplitOptions)> overload and specify <xref:System.StringSplitOptions.RemoveEmptyEntries?displayProperty=nameWithType> for the `options` parameter.</span></span>

[!code-csharp-interactive[Intro#1](snippets/parse-strings/csharp/intro.cs#3)]
:::code language="vb" source="snippets/parse-strings/vb/intro.vb" id="3":::

## <a name="regular-expressions"></a><span data-ttu-id="f18f6-120">정규식</span><span class="sxs-lookup"><span data-stu-id="f18f6-120">Regular expressions</span></span>

<span data-ttu-id="f18f6-121">문자열이 고정 패턴을 따르는 경우 정규식을 사용하여 해당 요소를 추출하고 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-121">If your string conforms to a fixed pattern, you can use a regular expression to extract and handle its elements.</span></span> <span data-ttu-id="f18f6-122">예를 들어 문자열이 "  숫자 피연산자 숫자" 형식을 사용하는 경우 [정규식](regular-expressions.md)을 사용하여 문자열의 요소를 추출하고 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-122">For example, if strings take the form " *number* *operand* *number* ", you can use a [regular expression](regular-expressions.md) to extract and handle the string's elements.</span></span> <span data-ttu-id="f18f6-123">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-123">Here's an example:</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="1":::

<span data-ttu-id="f18f6-124">정규식 패턴 `(\d+)\s+([-+*/])\s+(\d+)`는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-124">The regular expression pattern `(\d+)\s+([-+*/])\s+(\d+)` is defined like this:</span></span>

|<span data-ttu-id="f18f6-125">무늬</span><span class="sxs-lookup"><span data-stu-id="f18f6-125">Pattern</span></span>|<span data-ttu-id="f18f6-126">Description</span><span class="sxs-lookup"><span data-stu-id="f18f6-126">Description</span></span>|
|-------------|-----------------|
|`(\d+)`|<span data-ttu-id="f18f6-127">하나 이상의 10진수 숫자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-127">Match one or more decimal digits.</span></span> <span data-ttu-id="f18f6-128">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-128">This is the first capturing group.</span></span>|
|`\s+`|<span data-ttu-id="f18f6-129">하나 이상의 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-129">Match one or more white-space characters.</span></span>|
|`([-+*/])`|<span data-ttu-id="f18f6-130">산술 연산자 기호(+, -, \*, /)를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-130">Match an arithmetic operator sign (+, -, \*, or /).</span></span> <span data-ttu-id="f18f6-131">이 그룹은 두 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-131">This is the second capturing group.</span></span>|
|`\s+`|<span data-ttu-id="f18f6-132">하나 이상의 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-132">Match one or more white-space characters.</span></span>|
|`(\d+)`|<span data-ttu-id="f18f6-133">하나 이상의 10진수 숫자가 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-133">Match one or more decimal digits.</span></span> <span data-ttu-id="f18f6-134">이 그룹은 세 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-134">This is the third capturing group.</span></span>|

<span data-ttu-id="f18f6-135">정규식을 사용하여 고정 문자 집합이 아닌 패턴을 기반으로 문자열에서 부분 문자열을 추출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-135">You can also use a regular expression to extract substrings from a string based on a pattern rather than a fixed set of characters.</span></span> <span data-ttu-id="f18f6-136">다음은 이러한 조건 중 하나가 발생하는 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-136">This is a common scenario when either of these conditions occurs:</span></span>

- <span data-ttu-id="f18f6-137">하나 이상의 구분 문자가 <xref:System.String> 인스턴스에서 항상 구분 기호로 사용되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-137">One or more of the delimiter characters does not *always* serve as a delimiter in the <xref:System.String> instance.</span></span>

- <span data-ttu-id="f18f6-138">구분 문자의 시퀀스와 수는 변수이거나 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-138">The sequence and number of delimiter characters is variable or unknown.</span></span>

<span data-ttu-id="f18f6-139">예를 들어 <xref:System.String.Split%2A> 메서드는 다음 문자열을 분할하는 데 사용할 수 없습니다. `\n`(줄 바꿈) 문자 수가 변수이고 이 문자가 항상 구분 기호로 사용되지는 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-139">For example, the <xref:System.String.Split%2A> method cannot be used to split the following string, because the number of `\n` (newline) characters is variable, and they don't always serve as delimiters.</span></span>

```text
[This is captured\ntext.]\n\n[\n[This is more captured text.]\n]
\n[Some more captured text:\n   Option1\n   Option2][Terse text.]
```

<span data-ttu-id="f18f6-140">정규식은 다음 예제에서 볼 수 있듯이 이 문자열을 쉽게 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-140">A regular expression can split this string easily, as the following example shows.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="2" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="2":::

<span data-ttu-id="f18f6-141">정규식 패턴 `\[([^\[\]]+)\]`는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-141">The regular expression pattern `\[([^\[\]]+)\]` is defined like this:</span></span>

|<span data-ttu-id="f18f6-142">무늬</span><span class="sxs-lookup"><span data-stu-id="f18f6-142">Pattern</span></span>|<span data-ttu-id="f18f6-143">Description</span><span class="sxs-lookup"><span data-stu-id="f18f6-143">Description</span></span>|
|-------------|-----------------|
|`\[`|<span data-ttu-id="f18f6-144">여는 대괄호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-144">Match an opening bracket.</span></span>|
|`([^\[\]]+)`|<span data-ttu-id="f18f6-145">여는 대괄호나 닫는 대괄호가 아닌 문자를 한 번 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-145">Match any character that is not an opening or a closing bracket one or more times.</span></span> <span data-ttu-id="f18f6-146">이 그룹은 첫 번째 캡처링 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-146">This is the first capturing group.</span></span>|
|`\]`|<span data-ttu-id="f18f6-147">닫는 대괄호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-147">Match a closing bracket.</span></span>|

<span data-ttu-id="f18f6-148"><xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드는 고정 문자 집합 대신 정규식 패턴을 기반으로 문자열을 분할한다는 점을 제외하면 <xref:System.String.Split%2A?displayProperty=nameWithType>과 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-148">The <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method is almost identical to <xref:System.String.Split%2A?displayProperty=nameWithType>, except that it splits a string based on a regular expression pattern instead of a fixed character set.</span></span> <span data-ttu-id="f18f6-149">예를 들어 다음 예제에서는 <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> 메서드를 사용하여 하이픈과 기타 문자의 다양한 조합으로 구분된 부분 문자열이 포함된 문자열을 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-149">For example, the following example uses the <xref:System.Text.RegularExpressions.Regex.Split%2A?displayProperty=nameWithType> method to split a string that contains substrings delimited by various combinations of hyphens and other characters.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/regex.cs" id="3" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/regex.vb" id="3":::

<span data-ttu-id="f18f6-150">정규식 패턴 `\s-\s?[+*]?\s?-\s`는 다음과 같이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-150">The regular expression pattern `\s-\s?[+*]?\s?-\s` is defined like this:</span></span>

|<span data-ttu-id="f18f6-151">무늬</span><span class="sxs-lookup"><span data-stu-id="f18f6-151">Pattern</span></span>|<span data-ttu-id="f18f6-152">Description</span><span class="sxs-lookup"><span data-stu-id="f18f6-152">Description</span></span>|
|-------------|-----------------|
|`\s-`|<span data-ttu-id="f18f6-153">뒤에 하이픈이 오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-153">Match a white-space character followed by a hyphen.</span></span>|
|`\s?`|<span data-ttu-id="f18f6-154">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-154">Match zero or one white-space character.</span></span>|
|`[+*]?`|<span data-ttu-id="f18f6-155">0번 또는 한 번 나오는 + 또는 \* 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-155">Match zero or one occurrence of either the + or \* character.</span></span>|
|`\s?`|<span data-ttu-id="f18f6-156">0번 이상 나오는 공백 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-156">Match zero or one white-space character.</span></span>|
|`-\s`|<span data-ttu-id="f18f6-157">뒤에 공백 문자가 오는 하이픈을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-157">Match a hyphen followed by a white-space character.</span></span>|

## <a name="stringindexof-and-stringsubstring-methods"></a><span data-ttu-id="f18f6-158">String.IndexOf 및 String.Substring 메서드</span><span class="sxs-lookup"><span data-stu-id="f18f6-158">String.IndexOf and String.Substring methods</span></span>

<span data-ttu-id="f18f6-159">문자열의 모든 부분 문자열에 관심이 있는 것이 아니라면 일치가 시작되는 인덱스를 반환하는 문자열 비교 메서드 중 하나를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-159">If you aren't interested in all of the substrings in a string, you might prefer to work with one of the string comparison methods that returns the index at which the match begins.</span></span> <span data-ttu-id="f18f6-160">그런 다음 <xref:System.String.Substring%2A> 메서드를 호출하여 원하는 부분 문자열을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-160">You can then call the <xref:System.String.Substring%2A> method to extract the substring that you want.</span></span> <span data-ttu-id="f18f6-161">문자열 비교 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-161">The string comparison methods include:</span></span>

- <span data-ttu-id="f18f6-162">문자열 인스턴스에서 처음 나오는 문자 또는 문자열의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.IndexOf%2A></span><span class="sxs-lookup"><span data-stu-id="f18f6-162"><xref:System.String.IndexOf%2A>, which returns the zero-based index of the first occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="f18f6-163">문자 배열에서 문자가 처음 나오는 현재 문자열 인스턴스의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.IndexOfAny%2A></span><span class="sxs-lookup"><span data-stu-id="f18f6-163"><xref:System.String.IndexOfAny%2A>, which returns the zero-based index in the current string instance of the first occurrence of any character in a character array.</span></span>

- <span data-ttu-id="f18f6-164">문자열 인스턴스에서 마지막으로 나오는 문자 또는 문자열의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.LastIndexOf%2A></span><span class="sxs-lookup"><span data-stu-id="f18f6-164"><xref:System.String.LastIndexOf%2A>, which returns the zero-based index of the last occurrence of a character or string in a string instance.</span></span>

- <span data-ttu-id="f18f6-165">문자 배열에서 문자가 마지막으로 나오는 현재 문자열 인스턴스의 0부터 시작하는 인덱스를 반환하는 <xref:System.String.LastIndexOfAny%2A></span><span class="sxs-lookup"><span data-stu-id="f18f6-165"><xref:System.String.LastIndexOfAny%2A>, which returns a zero-based index in the current string instance of the last occurrence of any character in a character array.</span></span>

<span data-ttu-id="f18f6-166">다음 예제는 <xref:System.String.IndexOf%2A> 메서드를 사용하여 문자열의 마침표를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-166">The following example uses the <xref:System.String.IndexOf%2A> method to find the periods in a string.</span></span> <span data-ttu-id="f18f6-167">그런 다음 <xref:System.String.Substring%2A> 메서드를 사용하여 전체 문장을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f18f6-167">It then uses the <xref:System.String.Substring%2A> method to return full sentences.</span></span>

:::code language="csharp" source="snippets/parse-strings/csharp/indexof.cs" id="1" interactive="try-dotnet":::
:::code language="vb" source="snippets/parse-strings/vb/indexof.vb" id="1":::

## <a name="see-also"></a><span data-ttu-id="f18f6-168">참조</span><span class="sxs-lookup"><span data-stu-id="f18f6-168">See also</span></span>

- [<span data-ttu-id="f18f6-169">.NET의 기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="f18f6-169">Basic string operations in .NET</span></span>](basic-string-operations.md)
- [<span data-ttu-id="f18f6-170">.NET 정규식</span><span class="sxs-lookup"><span data-stu-id="f18f6-170">.NET regular expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="f18f6-171">C#에서 String.Split을 사용하여 문자열을 구문 분석하는 방법</span><span class="sxs-lookup"><span data-stu-id="f18f6-171">How to parse strings using String.Split in C#</span></span>](../../csharp/how-to/parse-strings-using-split.md)
