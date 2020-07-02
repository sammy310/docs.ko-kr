---
title: 문자열 검색 방법(C# 가이드)
ms.date: 02/21/2018
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with String methods
- strings [C#], searching with regular expressions
ms.assetid: fb1d9a6d-598d-4a35-bd5f-b86012edcb2b
ms.openlocfilehash: 34f9f2df11f9b7c51fcec2f8475a50ccf4c5e220
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324131"
---
# <a name="how-to-search-strings"></a><span data-ttu-id="6e500-102">문자열 검색 방법</span><span class="sxs-lookup"><span data-stu-id="6e500-102">How to search strings</span></span>

<span data-ttu-id="6e500-103">문자열에서 텍스트를 검색하는 두 가지 기본 전략을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-103">You can use two main strategies to search for text in strings.</span></span> <span data-ttu-id="6e500-104"><xref:System.String> 클래스의 메서드는 특정 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-104">Methods of the <xref:System.String> class search for specific text.</span></span> <span data-ttu-id="6e500-105">정규식은 텍스트에서 패턴을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-105">Regular expressions search for patterns in text.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="6e500-106"><xref:System.String?displayProperty=nameWithType> 클래스의 별칭인 [string](../language-reference/builtin-types/reference-types.md#the-string-type) 형식은 문자열 내용을 검색하기 위한 여러 가지 유용한 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-106">The [string](../language-reference/builtin-types/reference-types.md#the-string-type) type, which is an alias for the <xref:System.String?displayProperty=nameWithType> class, provides a number of useful methods for searching the contents of a string.</span></span> <span data-ttu-id="6e500-107">그중에 <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A>, <xref:System.String.EndsWith%2A>, <xref:System.String.IndexOf%2A>, <xref:System.String.LastIndexOf%2A>입니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-107">Among them are <xref:System.String.Contains%2A>, <xref:System.String.StartsWith%2A>, <xref:System.String.EndsWith%2A>, <xref:System.String.IndexOf%2A>, <xref:System.String.LastIndexOf%2A>.</span></span> <span data-ttu-id="6e500-108"><xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 클래스는 텍스트에서 패턴을 검색하는 풍부한 어휘를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-108">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class provides a rich vocabulary to search for patterns in text.</span></span> <span data-ttu-id="6e500-109">이 문서에서는 이러한 기술 및 요구 사항에 대해 최상의 메서드를 선택하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-109">In this article, you learn these techniques and how to choose the best method for your needs.</span></span>

## <a name="does-a-string-contain-text"></a><span data-ttu-id="6e500-110">문자열에 텍스트가 포함되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="6e500-110">Does a string contain text?</span></span>

<span data-ttu-id="6e500-111"><xref:System.String.Contains%2A?displayProperty=nameWithType>, <xref:System.String.StartsWith%2A?displayProperty=nameWithType> 및 <xref:System.String.EndsWith%2A?displayProperty=nameWithType> 메서드는 문자열에서 특정 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-111">The <xref:System.String.Contains%2A?displayProperty=nameWithType>, <xref:System.String.StartsWith%2A?displayProperty=nameWithType>, and <xref:System.String.EndsWith%2A?displayProperty=nameWithType> methods search a string for specific text.</span></span> <span data-ttu-id="6e500-112">다음 예에서는 이러한 메서드 각각 및 대/소문자 구분 검색을 사용하는 변형을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-112">The following example shows each of these methods and a variation that uses a case-insensitive search:</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet1":::

<span data-ttu-id="6e500-113">앞의 예제에서는 이러한 메서드를 사용하는 경우 중요한 사항을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-113">The preceding example demonstrates an important point for using these methods.</span></span> <span data-ttu-id="6e500-114">검색은 기본적으로 **대/소문자를 구분**합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-114">Searches are **case-sensitive** by default.</span></span> <span data-ttu-id="6e500-115"><xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> 열거형 값을 사용하여 대/소문자 구분 검색을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-115">You use the <xref:System.StringComparison.CurrentCultureIgnoreCase?displayProperty=nameWithType> enumeration value to specify a case-insensitive search.</span></span>

## <a name="where-does-the-sought-text-occur-in-a-string"></a><span data-ttu-id="6e500-116">검색된 텍스트가 있는 문자열의 위치는 어디인가요?</span><span class="sxs-lookup"><span data-stu-id="6e500-116">Where does the sought text occur in a string?</span></span>

<span data-ttu-id="6e500-117"><xref:System.String.IndexOf%2A> 및 <xref:System.String.LastIndexOf%2A> 메서드도 문자열에서 텍스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-117">The <xref:System.String.IndexOf%2A> and <xref:System.String.LastIndexOf%2A> methods also search for text in strings.</span></span> <span data-ttu-id="6e500-118">이러한 메서드는 검색되는 텍스트의 위치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-118">These methods return the location of the text being sought.</span></span> <span data-ttu-id="6e500-119">텍스트를 찾을 수 없으면 `-1`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-119">If the text isn't found, they return `-1`.</span></span> <span data-ttu-id="6e500-120">다음 예제에서는 "메서드"라는 단어의 첫 번째 및 마지막 항목에 대한 검색을 보여주고, 그 사이에 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-120">The following example shows a search for the first and last occurrence of the word "methods" and displays the text in between.</span></span>

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet2":::

## <a name="finding-specific-text-using-regular-expressions"></a><span data-ttu-id="6e500-121">정규식을 사용하여 특정 텍스트 찾기</span><span class="sxs-lookup"><span data-stu-id="6e500-121">Finding specific text using regular expressions</span></span>

<span data-ttu-id="6e500-122"><xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> 클래스를 사용하여 문자열을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-122">The <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> class can be used to search strings.</span></span> <span data-ttu-id="6e500-123">이 검색은 단순한 텍스트 패턴에서 복잡한 텍스트 패턴까지 복잡성의 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-123">These searches can range in complexity from simple to complicated text patterns.</span></span>

<span data-ttu-id="6e500-124">다음 코드 예제에서는 문장에서 "the" 또는 "their"라는 문자를 검색하고 대/소문자를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-124">The following code example searches for the word "the" or "their" in a sentence, ignoring case.</span></span> <span data-ttu-id="6e500-125">고정 메서드 <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>은 검색을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-125">The static method <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> performs the search.</span></span> <span data-ttu-id="6e500-126">검색할 문자열 및 검색 패턴을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-126">You give it the string to search and a search pattern.</span></span> <span data-ttu-id="6e500-127">이 경우에 세 번째 인수는 대/소문자 구분 검색을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-127">In this case, a third argument specifies case-insensitive search.</span></span> <span data-ttu-id="6e500-128">자세한 내용은 <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e500-128">For more information, see <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="6e500-129">검색 패턴은 검색할 텍스트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-129">The search pattern describes the text you search for.</span></span> <span data-ttu-id="6e500-130">다음 표에서는 검색 패턴의 각 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-130">The following table describes each element of the search pattern.</span></span> <span data-ttu-id="6e500-131">(아래 표에서는 C# 문자열에서 `\\`로 이스케이프되어야 하는 단일 `\`를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="6e500-131">(The table below uses the single `\`, which must be escaped as `\\` in a C# string).</span></span>

| <span data-ttu-id="6e500-132">무늬</span><span class="sxs-lookup"><span data-stu-id="6e500-132">Pattern</span></span>  | <span data-ttu-id="6e500-133">의미</span><span class="sxs-lookup"><span data-stu-id="6e500-133">Meaning</span></span>                          |
|----------|----------------------------------|
| `the`    | <span data-ttu-id="6e500-134">텍스트 "the" 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-134">match the text "the"</span></span>             |
| `(eir)?` | <span data-ttu-id="6e500-135">“eir”과 0 또는 1개 항목 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-135">match 0 or 1 occurrence of "eir"</span></span> |
| `\s`     | <span data-ttu-id="6e500-136">공백 문자 찾기</span><span class="sxs-lookup"><span data-stu-id="6e500-136">match a white-space character</span></span>    |

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet3":::

> [!TIP]
> <span data-ttu-id="6e500-137">정확한 문자열을 검색하는 경우 일반적으로 `string` 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-137">The `string` methods are usually better choices when you are searching for an exact string.</span></span> <span data-ttu-id="6e500-138">원본 문자열에서 몇 가지 패턴을 검색하는 경우 정규식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-138">Regular expressions are better when you are searching for some pattern in a source string.</span></span>

## <a name="does-a-string-follow-a-pattern"></a><span data-ttu-id="6e500-139">문자열은 패턴을 따르나요?</span><span class="sxs-lookup"><span data-stu-id="6e500-139">Does a string follow a pattern?</span></span>

<span data-ttu-id="6e500-140">다음 코드는 정규식을 사용하여 배열에서 각 문자열 형식의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-140">The following code uses regular expressions to validate the format of each string in an array.</span></span> <span data-ttu-id="6e500-141">유효성 검사에서는 각 문자열이 전화 번호의 형식을 사용해야 합니다. 이 경우 3개의 숫자 그룹이 대시로 구분되고, 처음 두 그룹에는 세 자리 숫자가 포함되며, 세 번째 그룹에는 네 자리 숫자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-141">The validation requires that each string have the form of a telephone number in which three groups of digits are separated by dashes, the first two groups contain three digits, and the third group contains four digits.</span></span> <span data-ttu-id="6e500-142">검색 패턴은 정규식 `^\\d{3}-\\d{3}-\\d{4}$`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-142">The search pattern uses the regular expression `^\\d{3}-\\d{3}-\\d{4}$`.</span></span> <span data-ttu-id="6e500-143">자세한 내용은 [정규식 언어 - 빠른 참조](../../standard/base-types/regular-expression-language-quick-reference.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e500-143">For more information, see [Regular Expression Language - Quick Reference](../../standard/base-types/regular-expression-language-quick-reference.md).</span></span>

| <span data-ttu-id="6e500-144">무늬</span><span class="sxs-lookup"><span data-stu-id="6e500-144">Pattern</span></span> | <span data-ttu-id="6e500-145">의미</span><span class="sxs-lookup"><span data-stu-id="6e500-145">Meaning</span></span>                             |
|---------|-------------------------------------|
| `^`     | <span data-ttu-id="6e500-146">문자열의 시작 부분 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-146">matches the beginning of the string</span></span> |
| `\d{3}` | <span data-ttu-id="6e500-147">정확히 3자리 문자 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-147">matches exactly 3 digit characters</span></span>  |
| `-`     | <span data-ttu-id="6e500-148">'-' 문자 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-148">matches the '-' character</span></span>           |
| `\d{3}` | <span data-ttu-id="6e500-149">정확히 3자리 문자 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-149">matches exactly 3 digit characters</span></span>  |
| `-`     | <span data-ttu-id="6e500-150">'-' 문자 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-150">matches the '-' character</span></span>           |
| `\d{4}` | <span data-ttu-id="6e500-151">정확히 4자리 문자 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-151">matches exactly 4 digit characters</span></span>  |
| `$`     | <span data-ttu-id="6e500-152">문자열의 끝 일치</span><span class="sxs-lookup"><span data-stu-id="6e500-152">matches the end of the string</span></span>       |

:::code language="csharp" interactive="try-dotnet-method" source="../../../samples/snippets/csharp/how-to/strings/SearchStrings.cs" id="Snippet4":::

<span data-ttu-id="6e500-153">이 단일 검색 패턴은 많은 유효한 문자열과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-153">This single search pattern matches many valid strings.</span></span> <span data-ttu-id="6e500-154">단일 텍스트 문자열이 아닌 패턴을 검색하거나 유효성을 확인하기 위해 정규식을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e500-154">Regular expressions are better to search for or validate against a pattern, rather than a single text string.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e500-155">참조</span><span class="sxs-lookup"><span data-stu-id="6e500-155">See also</span></span>

- [<span data-ttu-id="6e500-156">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="6e500-156">C# programming guide</span></span>](../programming-guide/index.md)
- [<span data-ttu-id="6e500-157">문자열</span><span class="sxs-lookup"><span data-stu-id="6e500-157">Strings</span></span>](../programming-guide/strings/index.md)
- [<span data-ttu-id="6e500-158">LINQ 및 문자열</span><span class="sxs-lookup"><span data-stu-id="6e500-158">LINQ and strings</span></span>](../programming-guide/concepts/linq/linq-and-strings.md)
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>
- [<span data-ttu-id="6e500-159">.NET Framework 정규식</span><span class="sxs-lookup"><span data-stu-id="6e500-159">.NET Framework regular expressions</span></span>](../../standard/base-types/regular-expressions.md)
- [<span data-ttu-id="6e500-160">정규식 언어 - 빠른 참조</span><span class="sxs-lookup"><span data-stu-id="6e500-160">Regular expression language - quick reference</span></span>](../../standard/base-types/regular-expression-language-quick-reference.md)
- [<span data-ttu-id="6e500-161">.NET에서 문자열 사용에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="6e500-161">Best practices for using strings in .NET</span></span>](../../standard/base-types/best-practices-strings.md)
