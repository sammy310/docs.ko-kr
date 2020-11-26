---
title: 문자열을 숫자로 변환하는 방법 - C# 프로그래밍 가이드
description: C#에서 Parse, TryParse 또는 Convert 클래스 메서드를 호출하여 문자열을 숫자로 변환하는 방법을 알아봅니다.
ms.date: 11/20/2020
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 0a9585d05a817d09308e06558352f78a5347a8f1
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099174"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a><span data-ttu-id="f0845-103">문자열을 숫자로 변환하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f0845-103">How to convert a string to a number (C# Programming Guide)</span></span>

<span data-ttu-id="f0845-104">다양한 숫자 형식(`int`, `long`, `double` 등)에 있는 `Parse` 또는 `TryParse` 메서드를 호출하거나 <xref:System.Convert?displayProperty=nameWithType> 클래스의 메서드를 사용하여 [문자열](../../language-reference/builtin-types/reference-types.md)을 숫자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-104">You can convert a [string](../../language-reference/builtin-types/reference-types.md) to a number by calling the `Parse` or `TryParse` method found on the various numeric types (`int`, `long`, `double`, and so on), or by using methods in the <xref:System.Convert?displayProperty=nameWithType> class.</span></span>  
  
 <span data-ttu-id="f0845-105">`TryParse` 메서드(예: [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) 또는 `Parse` 메서드(예: [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A))를 호출하면 약간 더 효율적이고 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-105">It's slightly more efficient and straightforward to call a `TryParse` method (for example, [`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) or `Parse` method (for example, [`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)).</span></span>  <span data-ttu-id="f0845-106"><xref:System.Convert> 메서드 사용은 <xref:System.IConvertible>을 구현하는 일반 개체에 더 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-106">Using a <xref:System.Convert> method is more useful for general objects that implement <xref:System.IConvertible>.</span></span>  
  
 <span data-ttu-id="f0845-107">`Parse` 또는 `TryParse` 메서드는 <xref:System.Int32?displayProperty=nameWithType> 형식과 같이 문자열에 포함되는 숫자 형식에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-107">You use `Parse` or `TryParse` methods on the numeric type you expect the string contains, such as the <xref:System.Int32?displayProperty=nameWithType> type.</span></span>  <span data-ttu-id="f0845-108"><xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> 메서드는 <xref:System.Int32.Parse%2A>를 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-108">The <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> method uses <xref:System.Int32.Parse%2A> internally.</span></span>  <span data-ttu-id="f0845-109">`Parse` 메서드는 변환된 숫자를 반환합니다. `TryParse` 메서드는 변환에 성공했는지 여부를 나타내는 <xref:System.Boolean> 값을 반환하고 변환된 숫자를 [`out` 매개 변수](../../language-reference/keywords/out.md)로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-109">The `Parse` method returns the converted number; the `TryParse` method returns a <xref:System.Boolean> value that indicates whether the conversion succeeded, and returns the converted number in an [`out` parameter](../../language-reference/keywords/out.md).</span></span> <span data-ttu-id="f0845-110">문자열이 유효한 형식이 아닌 경우 `Parse`는 예외를 throw하지만 `TryParse`는 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-110">If the string isn't in a valid format, `Parse` throws an exception, but `TryParse` returns `false`.</span></span> <span data-ttu-id="f0845-111">`Parse` 메서드를 호출할 때는 항상 예외 처리를 사용하여 구문 분석 작업이 실패하는 이벤트에서 <xref:System.FormatException>을 catch해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-111">When calling a `Parse` method, you should always use exception handling to catch a <xref:System.FormatException> in the event that the parse operation fails.</span></span>  
  
## <a name="calling-the-parse-and-tryparse-methods"></a><span data-ttu-id="f0845-112">Parse 및 TryParse 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="f0845-112">Calling the Parse and TryParse methods</span></span>

<span data-ttu-id="f0845-113">`Parse` 및 `TryParse` 메서드는 문자열의 시작과 끝에 있는 공백을 무시하지만 다른 모든 문자는 적절한 숫자 형식(`int`, `long`, `ulong`, `float`, `decimal` 등)을 구성하는 문자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-113">The `Parse` and `TryParse` methods ignore white space at the beginning and at the end of the string, but all other characters must be characters that form the appropriate numeric type (`int`, `long`, `ulong`, `float`, `decimal`, and so on).</span></span>  <span data-ttu-id="f0845-114">숫자를 구성하는 문자열 내에 공백이 있으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-114">Any white space within the string that forms the number causes an error.</span></span>  <span data-ttu-id="f0845-115">예를 들어 `decimal.TryParse`를 사용하여 “10”, “10.3” 또는 “  10  ”은 구문 분석할 수 있지만 이 메서드를 사용하여 “10X”, “1 0”(공백 포함), “10 .3”(공백 포함), “10e1”(`float.TryParse` 사용) 등에서 10을 구문 분석할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-115">For example, you can use `decimal.TryParse` to parse "10", "10.3", or "  10  ", but you can't use this method to parse 10 from "10X", "1 0" (note the embedded space), "10 .3" (note the embedded space), "10e1" (`float.TryParse` works here), and so on.</span></span> <span data-ttu-id="f0845-116">값이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>인 문자열은 구문 분석되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-116">A string whose value is `null` or <xref:System.String.Empty?displayProperty=nameWithType> fails to parse successfully.</span></span> <span data-ttu-id="f0845-117"><xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> 메서드를 호출하여 구문 분석하기 전에 Null 또는 빈 문자열을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-117">You can check for a null or empty string before attempting to parse it by calling the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f0845-118">다음 예제에서는 `Parse` 및 `TryParse` 호출이 성공하는 경우와 실패하는 경우를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-118">The following example demonstrates both successful and unsuccessful calls to `Parse` and `TryParse`.</span></span>  
  
[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]  

<span data-ttu-id="f0845-119">다음 예제에서는 선행 숫자(16진수 문자 포함) 및 숫자가 아닌 후행 문자를 포함해야 하는 문자열을 구문 분석하는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-119">The following example illustrates one approach to parsing a string expected to include leading numeric characters (including hexadecimal characters) and trailing non-numeric characters.</span></span> <span data-ttu-id="f0845-120"><xref:System.Int32.TryParse%2A> 메서드를 호출하기 전에 문자열 시작 부분의 유효한 문자를 새 문자열에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-120">It assigns valid characters from the beginning of a string to a new string before calling the <xref:System.Int32.TryParse%2A> method.</span></span> <span data-ttu-id="f0845-121">구문 분석할 문자열에 포함된 문자 수가 적으므로 예제에서는 <xref:System.String.Concat%2A?displayProperty=nameWithType> 메서드를 호출하여 새 문자열에 유효한 문자를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-121">Because the strings to be parsed contain a small number of characters, the example calls the <xref:System.String.Concat%2A?displayProperty=nameWithType> method to assign valid characters to a new string.</span></span> <span data-ttu-id="f0845-122">더 큰 문자열의 경우 <xref:System.Text.StringBuilder> 클래스를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-122">For a larger string, the <xref:System.Text.StringBuilder> class can be used instead.</span></span>
  
[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]  

## <a name="calling-the-convert-methods"></a><span data-ttu-id="f0845-123">변환 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="f0845-123">Calling the Convert methods</span></span>

<span data-ttu-id="f0845-124">다음 표에는 문자열을 숫자로 변환하는 데 사용할 수 있는 <xref:System.Convert> 클래스의 일부 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-124">The following table lists some of the methods from the <xref:System.Convert> class that you can use to convert a string to a number.</span></span>  
  
|<span data-ttu-id="f0845-125">숫자 형식</span><span class="sxs-lookup"><span data-stu-id="f0845-125">Numeric Type</span></span>|<span data-ttu-id="f0845-126">메서드</span><span class="sxs-lookup"><span data-stu-id="f0845-126">Method</span></span>|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 <span data-ttu-id="f0845-127">다음 예제에서는 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> 메서드를 호출하여 입력 문자열을 [int](../../language-reference/builtin-types/integral-numeric-types.md)로 변환합니다. 예제에서는 이 메서드에서 throw할 수 있는 두 가지 가장 일반적인 예외인 <xref:System.FormatException>과 <xref:System.OverflowException>을 catch합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-127">The following example calls the <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> method to convert an input string to an [int](../../language-reference/builtin-types/integral-numeric-types.md). The example catches the two most common exceptions that can be thrown by this method, <xref:System.FormatException> and <xref:System.OverflowException>.</span></span> <span data-ttu-id="f0845-128"><xref:System.Int32.MaxValue?displayProperty=nameWithType>을 초과하지 않고 결과 숫자를 증분할 수 있는 경우 예제에서는 결과에 1을 더하고 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f0845-128">If the resulting number can be incremented without exceeding <xref:System.Int32.MaxValue?displayProperty=nameWithType>, the example adds 1 to the result and displays the output.</span></span>  
  
[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f0845-129">참조</span><span class="sxs-lookup"><span data-stu-id="f0845-129">See also</span></span>

- [<span data-ttu-id="f0845-130">형식</span><span class="sxs-lookup"><span data-stu-id="f0845-130">Types</span></span>](./index.md)
- [<span data-ttu-id="f0845-131">문자열이 숫자 값을 나타내는지 확인 방법</span><span class="sxs-lookup"><span data-stu-id="f0845-131">How to determine whether a string represents a numeric value</span></span>](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [<span data-ttu-id="f0845-132">샘플: .NET Core WinForms 서식 유틸리티(C#)</span><span class="sxs-lookup"><span data-stu-id="f0845-132">Sample: .NET Core WinForms Formatting Utility (C#)</span></span>](/samples/dotnet/samples/windowsforms-formatting-utility-cs)
