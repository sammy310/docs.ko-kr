---
title: $ - 문자열 보간 - C# 참조
ms.custom: seodec18
description: 문자열 보간을 이용한 구문으로 기존의 문자열 합성보다 읽기 쉽고 편리하게 문자열 출력의 서식을 지정할 수 있습니다.
ms.date: 04/29/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: bc27eedcf1957a109a9bcb80cf9a49e9606921fd
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/28/2019
ms.locfileid: "66250995"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="1967d-103">$ - 문자열 보간(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1967d-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="1967d-104">`$`특수 문자는 문자열 리터럴을 *보간된 문자열*로 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="1967d-105">보간된 문자열은 *보간 식*이 포함될 수 있는 문자열 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-105">An interpolated string is a string literal that might contain *interpolation expressions*.</span></span> <span data-ttu-id="1967d-106">보간된 문자열이 결과 문자열로 해석되면 보간 식이 있는 항목이 식 결과의 문자열 표현으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-106">When an interpolated string is resolved to a result string, items with interpolation expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="1967d-107">이 기능은 컴퓨터 언어 C# 6 이상 버전에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="1967d-108">문자열 보간은 [문자열 합성 서식 지정](../../../standard/base-types/composite-formatting.md) 기능보다 읽기 쉽고 편리하게 서식이 지정된 문자열을 만들 수 있는 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="1967d-109">다음 예제에서는 두 기능을 사용하여 동일한 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="1967d-110">보간된 문자열의 구조</span><span class="sxs-lookup"><span data-stu-id="1967d-110">Structure of an interpolated string</span></span>

<span data-ttu-id="1967d-111">문자열 리터럴을 보간된 문자열로 식별하려면 `$` 기호를 사용하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="1967d-112">문자열 리터럴을 시작하는 `$` 및 `"` 사이에 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="1967d-113">이렇게 하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="1967d-114">보간 식이 있는 항목의 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-114">The structure of an item with an interpolation expression is as follows:</span></span>

```
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="1967d-115">대괄호 안의 요소는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="1967d-116">다음 표에서는 각 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-116">The following table describes each element:</span></span>

|<span data-ttu-id="1967d-117">요소</span><span class="sxs-lookup"><span data-stu-id="1967d-117">Element</span></span>|<span data-ttu-id="1967d-118">설명</span><span class="sxs-lookup"><span data-stu-id="1967d-118">Description</span></span>|
|-------------|-----------------|
|`interpolationExpression`|<span data-ttu-id="1967d-119">서식을 지정할 결과를 생성하는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="1967d-120">`null` 결과의 문자열 표현은 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="1967d-121">보간 식의 결과에 대한 문자열 표현의 최소 문자 수를 정의하는 값을 갖는 상수 식입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolation expression.</span></span> <span data-ttu-id="1967d-122">양수이면 문자열 표현이 오른쪽에 맞춰지며, 음수이면 왼쪽에 맞춰집니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="1967d-123">자세한 내용은 [맞춤 구성 요소](../../../standard/base-types/composite-formatting.md#alignment-component)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="1967d-124">식 결과의 형식을 기준으로 지원되는 서식 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="1967d-125">자세한 내용은 [서식 문자열 구성 요소](../../../standard/base-types/composite-formatting.md#format-string-component)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="1967d-126">다음 예제에서는 위에 설명된 선택적 서식 지정 구성 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="1967d-127">특수 문자</span><span class="sxs-lookup"><span data-stu-id="1967d-127">Special characters</span></span>

<span data-ttu-id="1967d-128">보간된 문자열로 생성된 문자에 중괄호("{" 또는 "}")를 포함하려면 두 개의 중괄호("{{" 또는 "}}")를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="1967d-129">자세한 내용은 [중괄호 이스케이프](../../../standard/base-types/composite-formatting.md#escaping-braces)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="1967d-130">콜론(":")은 보간 식 항목에서 특별한 의미가 있으므로, 보간 식에서 [조건부 연산자](../operators/conditional-operator.md)를 사용하려면 해당 식을 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-130">As the colon (":") has special meaning in an interpolation expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolation expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="1967d-131">다음 예제에서는 중괄호를 결과 문자열에 포함하는 방법과 보간 식에서 조건부 연산자를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolation expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="1967d-132">약어 보간된 문자열은 `@` 문자가 뒤에 오는 `$` 문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="1967d-133">약어 문자열에 대한 자세한 내용은 [문자열](../keywords/string.md) 및 [약어 식별자](verbatim.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="1967d-134">`$` 토큰은 약어 보간된 문자열에서 `@` 토큰 앞에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="1967d-135">암시적 변환 및 `IFormatProvider` 구현 지정</span><span class="sxs-lookup"><span data-stu-id="1967d-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="1967d-136">보간된 문자열에서 다음과 같은 세 가지 암시적 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="1967d-137">보간된 문자열을 <xref:System.String> 인스턴스로 변환. 보간 식 항목을 사용하여 보간된 문자열을 확인한 결과를 올바르게 서식이 지정된 문자열 표현으로 바꾼 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolation expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="1967d-138">이 변환은 현재 문화권을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="1967d-139">보간된 문자열을 서식을 지정할 식 결과와 함께 복합 서식 문자열을 나타내는 <xref:System.FormattableString> 인스턴스로 변환.</span><span class="sxs-lookup"><span data-stu-id="1967d-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="1967d-140">이 변수를 사용하면 단일 <xref:System.FormattableString> 인스턴스에서 문화권별 콘텐츠가 포함된 여러 결과 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="1967d-141">이렇게 하려면 다음 메서드 중 하나를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="1967d-142"><xref:System.Globalization.CultureInfo.CurrentCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString> 오버로드.</span><span class="sxs-lookup"><span data-stu-id="1967d-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="1967d-143"><xref:System.Globalization.CultureInfo.InvariantCulture>에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.Invariant%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1967d-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="1967d-144">지정된 문화에 대한 결과 문자열을 생성하는 <xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드.</span><span class="sxs-lookup"><span data-stu-id="1967d-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="1967d-145"><xref:System.FormattableString.ToString(System.IFormatProvider)> 메서드를 사용하여 사용자 지정 형식을 지원하는 <xref:System.IFormatProvider> 인터페이스의 사용자 정의 구현을 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="1967d-146">자세한 내용은 [ICustomFormatter를 사용한 사용자 지정 형식 지정](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="1967d-147">보간된 문자열을 <xref:System.IFormattable> 인스턴스로 변환. 또한 이 인스턴스를 사용하면 단일 <xref:System.IFormattable> 인스턴스의 문화권별 콘텐츠로 여러 결과 문자열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="1967d-148">다음 예제에서는 <xref:System.FormattableString>에 대한 암시적 변환을 사용하여 문화권별 결과 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="1967d-149">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1967d-149">Additional resources</span></span>

<span data-ttu-id="1967d-150">문자열 보간을 처음 접하는 경우 [C#의 문자열 보간](../../tutorials/exploration/interpolated-strings.yml) 대화형 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="1967d-151">보간된 문자열을 사용하여 서식화된 문자열을 생성하는 방법을 보여 주는 다른 [C#의 문자열 보간](../../tutorials/string-interpolation.md) 자습서도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-151">You also can check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="1967d-152">보간된 문자열의 컴파일</span><span class="sxs-lookup"><span data-stu-id="1967d-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="1967d-153">보간된 문자열이 `string` 형식이면 일반적으로 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="1967d-154">컴파일러는 분석된 동작이 연결에 해당하는 경우 <xref:System.String.Format%2A?displayProperty=nameWithType>을 <xref:System.String.Concat%2A?displayProperty=nameWithType>으로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="1967d-155">보간된 문자열 형식이 <xref:System.IFormattable> 또는 <xref:System.FormattableString>이면 컴파일러가 <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> 메서드에 대한 호출을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1967d-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1967d-156">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1967d-156">C# language specification</span></span>

<span data-ttu-id="1967d-157">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [보간된 문자열](~/_csharplang/spec/expressions.md#interpolated-strings) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1967d-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1967d-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1967d-158">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="1967d-159">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="1967d-159">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="1967d-160">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="1967d-160">Formatting numeric results table</span></span>](../keywords/formatting-numeric-results-table.md)
- [<span data-ttu-id="1967d-161">문자열</span><span class="sxs-lookup"><span data-stu-id="1967d-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="1967d-162">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1967d-162">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1967d-163">C# 특수 문자</span><span class="sxs-lookup"><span data-stu-id="1967d-163">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="1967d-164">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1967d-164">C# Reference</span></span>](../index.md)
