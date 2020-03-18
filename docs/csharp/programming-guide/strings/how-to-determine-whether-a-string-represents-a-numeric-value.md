---
title: 문자열이 숫자 값을 나타내는지 확인하는 방법 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- numeric strings [C#]
- validating numeric input [C#]
- strings [C#], numeric
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
ms.openlocfilehash: 15a21a6298f8f0a57e0189554246202b220dd259
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79157067"
---
# <a name="how-to-determine-whether-a-string-represents-a-numeric-value-c-programming-guide"></a><span data-ttu-id="5eeb2-102">문자열이 숫자 값을 나타내는지 확인하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5eeb2-102">How to determine whether a string represents a numeric value (C# Programming Guide)</span></span>
<span data-ttu-id="5eeb2-103">문자열이 지정된 숫자 형식의 유효한 표현인지 확인하려면 모든 기본 숫자 형식 및 `TryParse`, <xref:System.DateTime> 등의 형식에 의해서도 구현되는 정적 <xref:System.Net.IPAddress> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-103">To determine whether a string is a valid representation of a specified numeric type, use the static `TryParse` method that is implemented by all primitive numeric types and also by types such as <xref:System.DateTime> and <xref:System.Net.IPAddress>.</span></span> <span data-ttu-id="5eeb2-104">다음 예제에서는 "108"이 유효한 [int](../../language-reference/builtin-types/integral-numeric-types.md)인지 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-104">The following example shows how to determine whether "108" is a valid [int](../../language-reference/builtin-types/integral-numeric-types.md).</span></span>  
  
```csharp  
int i = 0;
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 <span data-ttu-id="5eeb2-105">문자열이 숫자가 아닌 문자를 포함하거나, 숫자 값이 지정한 특정 형식에 비해 너무 크거나 너무 작은 경우 `TryParse`는 false를 반환하고 out 매개 변수를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-105">If the string contains nonnumeric characters or the numeric value is too large or too small for the particular type you have specified, `TryParse` returns false and sets the out parameter to zero.</span></span> <span data-ttu-id="5eeb2-106">그렇지 않으면 true를 반환하고 out 매개 변수를 문자열의 숫자 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-106">Otherwise, it returns true and sets the out parameter to the numeric value of the string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5eeb2-107">문자열이 숫자만 포함해도 사용하는 `TryParse` 메서드의 형식에 유효하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-107">A string may contain only numeric characters and still not be valid for the type whose `TryParse` method that you use.</span></span> <span data-ttu-id="5eeb2-108">예를 들어 "256"은 `byte`에 유효한 값이 아니지만 `int`에는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-108">For example, "256" is not a valid value for `byte` but it is valid for `int`.</span></span> <span data-ttu-id="5eeb2-109">"98.6"은 `int`에 유효한 값이 아니지만 유효한 `decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-109">"98.6" is not a valid value for `int` but it is a valid `decimal`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eeb2-110">예제</span><span class="sxs-lookup"><span data-stu-id="5eeb2-110">Example</span></span>  
 <span data-ttu-id="5eeb2-111">다음 예제에서는`TryParse`, `long` 및 `byte` 값의 문자열 표현과 함께 `decimal`를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-111">The following examples show how to use `TryParse` with string representations of `long`, `byte`, and `decimal` values.</span></span>  
  
 [!code-csharp[csProgGuideStrings#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStrings/CS/Strings.cs#14)]  
  
## <a name="robust-programming"></a><span data-ttu-id="5eeb2-112">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5eeb2-112">Robust Programming</span></span>  
 <span data-ttu-id="5eeb2-113">또한 기본 숫자 형식은 문자열이 유효한 숫자가 아닌 경우 예외를 throw하는 `Parse` 정적 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-113">Primitive numeric types also implement the `Parse` static method, which throws an exception if the string is not a valid number.</span></span> <span data-ttu-id="5eeb2-114">일반적으로 숫자가 유효하지 않은 경우 단순히 false를 반환하는 `TryParse`가 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-114">`TryParse` is generally more efficient because it just returns false if the number is not valid.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5eeb2-115">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="5eeb2-115">.NET Framework Security</span></span>  
 <span data-ttu-id="5eeb2-116">항상 `TryParse` 또는 `Parse` 메서드를 사용하여 텍스트 상자, 콤보 상자 등의 컨트롤에서 들어오는 사용자 입력의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="5eeb2-116">Always use the `TryParse` or `Parse` methods to validate user input from controls such as text boxes and combo boxes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eeb2-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5eeb2-117">See also</span></span>

- [<span data-ttu-id="5eeb2-118">바이트 배열을 int로 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="5eeb2-118">How to convert a byte array to an int</span></span>](../types/how-to-convert-a-byte-array-to-an-int.md)
- [<span data-ttu-id="5eeb2-119">문자열을 숫자로 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="5eeb2-119">How to convert a string to a number</span></span>](../types/how-to-convert-a-string-to-a-number.md)
- [<span data-ttu-id="5eeb2-120">16진수 문자열과 숫자 형식 간에 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="5eeb2-120">How to convert between hexadecimal strings and numeric types</span></span>](../types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)
- [<span data-ttu-id="5eeb2-121">숫자 문자열 구문 분석</span><span class="sxs-lookup"><span data-stu-id="5eeb2-121">Parsing Numeric Strings</span></span>](../../../standard/base-types/parsing-numeric.md)
- [<span data-ttu-id="5eeb2-122">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="5eeb2-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
