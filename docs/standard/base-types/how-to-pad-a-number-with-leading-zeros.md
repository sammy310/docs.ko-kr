---
title: '방법: 숫자 앞에 0으로 채우기'
ms.date: 02/25/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
ms.openlocfilehash: bc3c4b75c484274c214141d8fbfcf8ac592b0b99
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131983"
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a><span data-ttu-id="c8dcf-102">방법: 숫자 앞에 0으로 채우기</span><span class="sxs-lookup"><span data-stu-id="c8dcf-102">How to: Pad a Number with Leading Zeros</span></span>

<span data-ttu-id="c8dcf-103">"D" [표준 숫자 서식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md)과 함께 전체 자릿수 지정자를 사용하여 앞에 오는 0을 정수에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-103">You can add leading zeros to an integer by using the "D" [standard numeric format string](../../../docs/standard/base-types/standard-numeric-format-strings.md) with a precision specifier.</span></span> <span data-ttu-id="c8dcf-104">[사용자 지정 숫자 서식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)을 사용하여 정수와 부동 소수점 숫자 둘 다에 앞에 오는 0을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-104">You can add leading zeros to both integer and floating-point numbers by using a [custom numeric format string](../../../docs/standard/base-types/custom-numeric-format-strings.md).</span></span> <span data-ttu-id="c8dcf-105">이 문서에서는 두 개의 메서드를 사용하여 앞에 오는 0으로 숫자를 채우는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-105">This article shows how to use both methods to pad a number with leading zeros.</span></span>

## <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="c8dcf-106">앞에 오는 0으로 특정 길이까지 정수를 채우려면</span><span class="sxs-lookup"><span data-stu-id="c8dcf-106">To pad an integer with leading zeros to a specific length</span></span>

1. <span data-ttu-id="c8dcf-107">표시할 정수 값의 최소 자릿수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-107">Determine the minimum number of digits you want the integer value to display.</span></span> <span data-ttu-id="c8dcf-108">이 숫자에 원하는 선행 자릿수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-108">Include any leading digits in this number.</span></span>

1. <span data-ttu-id="c8dcf-109">정수를 10진수 값으로 표시할지 아니면 16진수 값으로 표시할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-109">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="c8dcf-110">정수를 10진수 값으로 표시하려면 해당 `ToString(String)` 메서드를 호출하고 문자열 "D*n*"을 `format` 매개 변수의 값으로 전달합니다. 여기서 *n*은 문자열의 최소 길이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-110">To display the integer as a decimal value, call its `ToString(String)` method, and pass the string "D*n*" as the value of the `format` parameter, where *n* represents the minimum length of the string.</span></span>

    - <span data-ttu-id="c8dcf-111">정수를 16진수 값으로 표시하려면 해당 `ToString(String)` 메서드를 호출하고 문자열 "X*n*"을 서식 매개 변수의 값으로 전달합니다. 여기서 *n*은 문자열의 최소 길이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-111">To display the integer as a hexadecimal value, call its `ToString(String)` method and pass the string "X*n*" as the value of the format parameter, where *n* represents the minimum length of the string.</span></span>

<span data-ttu-id="c8dcf-112">[C#](../../csharp/language-reference/tokens/interpolated.md) 및 [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) 모두의 보간된 문자열에서 형식 문자열을 사용할 수도 있습니다. 또는 [복합 서식 지정](../../../docs/standard/base-types/composite-formatting.md)을 사용하는 <xref:System.String.Format%2A?displayProperty=nameWithType> 또는 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>과 같은 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-112">You can also use the format string in an interpolated string in both [C#](../../csharp/language-reference/tokens/interpolated.md) and [Visual Basic](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md), or you can call a method, such as <xref:System.String.Format%2A?displayProperty=nameWithType> or <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, that uses [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>

<span data-ttu-id="c8dcf-113">다음 예제에서는 서식이 지정된 숫자의 전체 길이가 8자 이상이 되도록 앞에 오는 0으로 여러 정수 값의 서식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-113">The following example formats several integer values with leading zeros so that the total length of the formatted number is at least eight characters.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
[!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]

## <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="c8dcf-114">특정 수의 앞에 오는 0으로 정수를 채우려면</span><span class="sxs-lookup"><span data-stu-id="c8dcf-114">To pad an integer with a specific number of leading zeros</span></span>

1. <span data-ttu-id="c8dcf-115">정수 값을 표시하는 데 사용할 앞에 오는 0의 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-115">Determine how many leading zeros you want the integer value to display.</span></span>

1. <span data-ttu-id="c8dcf-116">정수를 10진수 값으로 표시할지 아니면 16진수 값으로 표시할지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-116">Determine whether you want to display the integer as a decimal value or a hexadecimal value.</span></span>

    - <span data-ttu-id="c8dcf-117">10진수 값으로 서식을 지정하려면 "D" 표준 서식 지정자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-117">Formatting it as a decimal value requires that you use the "D" standard format specifier.</span></span>

    - <span data-ttu-id="c8dcf-118">16진수 값으로 서식을 지정하려면 "X" 표준 서식 지정자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-118">Formatting it as a hexadecimal value requires that you use the "X" standard format specifier.</span></span>

1. <span data-ttu-id="c8dcf-119">정수 값의 `ToString("D").Length` 또는 `ToString("X").Length` 메서드를 호출하여 채워지지 않은 숫자 문자열의 길이를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-119">Determine the length of the unpadded numeric string by calling the integer value's `ToString("D").Length` or `ToString("X").Length` method.</span></span>

1. <span data-ttu-id="c8dcf-120">서식이 지정된 문자열에 포함할 앞에 오는 0의 수를 채워지지 않은 숫자 문자열의 길이에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-120">Add the number of leading zeros that you want to include in the formatted string to the length of the unpadded numeric string.</span></span> <span data-ttu-id="c8dcf-121">앞에 오는 0의 개수를 추가하면 채워진 문자열의 전체 길이를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-121">Adding the number of leading zeros defines the total length of the padded string.</span></span>

1. <span data-ttu-id="c8dcf-122">정수 값의 `ToString(String)` 메서드를 호출하고, 10진수 문자열의 경우 문자열 "D*n*"을 전달하고 16진수 문자열의 경우 "X*n*"을 전달합니다. 여기서 *n*은 채워진 문자열의 전체 길이를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-122">Call the integer value's `ToString(String)` method, and pass the string "D*n*" for decimal strings and "X*n*" for hexadecimal strings, where *n* represents the total length of the padded string.</span></span> <span data-ttu-id="c8dcf-123">또한 합성 서식 지정을 지원하는 메서드에 "D*n*" 또는 "X*n*" 서식 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-123">You can also use the "D*n*" or "X*n*" format string in a method that supports composite formatting.</span></span>

<span data-ttu-id="c8dcf-124">다음 예제에서는 5개의 앞에 오는 0으로 정수 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-124">The following example pads an integer value with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
[!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]

## <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a><span data-ttu-id="c8dcf-125">앞에 오는 0으로 특정 길이까지 숫자 값을 채우려면</span><span class="sxs-lookup"><span data-stu-id="c8dcf-125">To pad a numeric value with leading zeros to a specific length</span></span>

1. <span data-ttu-id="c8dcf-126">숫자의 문자열 표현에서 정수 부분을 표시하는 데 사용할 자릿수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-126">Determine how many digits to the left of the decimal you want the string representation of the number to have.</span></span> <span data-ttu-id="c8dcf-127">이 숫자의 전체 자릿수에 원하는 수의 앞에 오는 0을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-127">Include any leading zeros in this total number of digits.</span></span>

1. <span data-ttu-id="c8dcf-128">0 자리 표시자("0")를 사용하여 0의 최소 개수를 나타내는 사용자 지정 숫자 서식 문자열을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-128">Define a custom numeric format string that uses the zero placeholder "0" to represent the minimum number of zeros.</span></span>

1. <span data-ttu-id="c8dcf-129">숫자의 `ToString(String)` 메서드를 호출하여 사용자 지정 서식 문자열에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-129">Call the number's `ToString(String)` method and pass it the custom format string.</span></span> <span data-ttu-id="c8dcf-130">합성 서식 지정을 지원하는 문자열 보간 또는 메서드에서 사용자 지정 서식 문자열을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-130">You can also use the custom format string with string interpolation or with a method that supports composite formatting.</span></span>

<span data-ttu-id="c8dcf-131">다음 예제에서는 앞에 오는 0으로 여러 숫자 값의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-131">The following example formats several numeric values with leading zeros.</span></span> <span data-ttu-id="c8dcf-132">결과적으로 서식이 지정된 숫자의 전체 길이는 10진수의 왼쪽으로 최소한 8자리입니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-132">As a result, the total length of the formatted number is at least eight digits to the left of the decimal.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
[!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]

## <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a><span data-ttu-id="c8dcf-133">특정 수의 앞에 오는 0으로 숫자 값을 채우려면</span><span class="sxs-lookup"><span data-stu-id="c8dcf-133">To pad a numeric value with a specific number of leading zeros</span></span>

1. <span data-ttu-id="c8dcf-134">숫자 값을 표시하는 데 사용할 앞에 오는 0의 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-134">Determine how many leading zeros you want the numeric value to have.</span></span>

1. <span data-ttu-id="c8dcf-135">채워지지 않은 숫자 문자열에서 정수 부분의 자릿수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-135">Determine the number of digits to the left of the decimal in the unpadded numeric string:</span></span>

    1. <span data-ttu-id="c8dcf-136">숫자의 문자열 표현에 소수점 기호가 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-136">Determine whether the string representation of a number includes a decimal point symbol.</span></span>

    1. <span data-ttu-id="c8dcf-137">소수점 기호가 포함되어 있으면 정수 부분에 있는 문자 수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-137">If it does include a decimal point symbol, determine the number of characters to the left of the decimal point.</span></span>

         <span data-ttu-id="c8dcf-138">또는</span><span class="sxs-lookup"><span data-stu-id="c8dcf-138">-or-</span></span>

         <span data-ttu-id="c8dcf-139">소수점 기호가 포함되어 있지 않으면 문자열의 길이를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-139">If it doesn't include a decimal point symbol, determine the string's length.</span></span>

1. <span data-ttu-id="c8dcf-140">다음을 사용하는 사용자 지정 형식 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-140">Create a custom format string that uses:</span></span>

    - <span data-ttu-id="c8dcf-141">문자열에 표시할 앞에 오는 0 각각에 대한 0 자리 표시자("0").</span><span class="sxs-lookup"><span data-stu-id="c8dcf-141">The zero placeholder "0" for each of the leading zeros to appear in the string.</span></span>

    - <span data-ttu-id="c8dcf-142">기본 문자열의 각 숫자를 나타내는 0 자리 표시자 또는 10진수 자리 표시자("#").</span><span class="sxs-lookup"><span data-stu-id="c8dcf-142">Either the zero placeholder or the digit placeholder "#" to represent each digit in the default string.</span></span>

1. <span data-ttu-id="c8dcf-143">사용자 지정 서식 문자열을 숫자의 `ToString(String)` 메서드에 대한 매개 변수 또는 합성 서식 지정을 지원하는 메서드에 대한 매개 변수로 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-143">Supply the custom format string as a parameter either to the number's `ToString(String)` method or to a method that supports composite formatting.</span></span>

<span data-ttu-id="c8dcf-144">다음 예제에서는 5개의 앞에 오는 0으로 두 개의 <xref:System.Double> 값을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="c8dcf-144">The following example pads two <xref:System.Double> values with five leading zeros.</span></span>

[!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
[!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="c8dcf-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8dcf-145">See also</span></span>

- [<span data-ttu-id="c8dcf-146">Custom Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="c8dcf-146">Custom Numeric Format Strings</span></span>](../../../docs/standard/base-types/custom-numeric-format-strings.md)
- [<span data-ttu-id="c8dcf-147">Standard Numeric Format Strings</span><span class="sxs-lookup"><span data-stu-id="c8dcf-147">Standard Numeric Format Strings</span></span>](../../../docs/standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="c8dcf-148">복합 형식 지정</span><span class="sxs-lookup"><span data-stu-id="c8dcf-148">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)
