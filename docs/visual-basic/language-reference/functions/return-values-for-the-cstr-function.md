---
title: CStr 함수의 반환 값(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819517"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="aa110-102">CStr 함수의 반환 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="aa110-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="aa110-103">다음 표에서 반환 값에 대 한 설명 `CStr` 의 다른 데이터 형식에 대 한 `expression`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="aa110-104">경우 `expression` 형식은</span><span class="sxs-lookup"><span data-stu-id="aa110-104">If `expression` type is</span></span>|<span data-ttu-id="aa110-105">`CStr` return</span><span class="sxs-lookup"><span data-stu-id="aa110-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="aa110-106">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aa110-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="aa110-107">"True"를 포함 하는 문자열 또는 "False"입니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="aa110-108">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aa110-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="aa110-109">포함 된 문자열을 `Date` 시스템의 간단한 날짜 형식의 값 (날짜 및 시간).</span><span class="sxs-lookup"><span data-stu-id="aa110-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="aa110-110">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aa110-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="aa110-111">수를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="aa110-112">CStr 및 날짜</span><span class="sxs-lookup"><span data-stu-id="aa110-112">CStr and Date</span></span>  
 <span data-ttu-id="aa110-113">`Date` 형식을 항상 날짜 및 시간 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="aa110-114">형식 변환 목적으로, Visual Basic은 간주 1/1/0001 (1 년 1 월 1 일) 수를 *중립 값* 시간에 대 한 중립 값으로 날짜 및 00시: 00 (자정)에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="aa110-115">`CStr` 중립 값의 결과 문자열에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="aa110-116">예를 들어, 변환 하는 경우 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00"은 날짜 정보를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="aa110-117">그러나 날짜 정보는 여전히 원래 `Date` 값과 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa110-118">`CStr` 함수가 응용 프로그램에 대 한 현재 문화권 설정에 따라 해당 변환을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="aa110-119">숫자의 문자열 표현을 특정 문화권에서을 사용 수의 `ToString(IFormatProvider)` 메서드.</span><span class="sxs-lookup"><span data-stu-id="aa110-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="aa110-120">사용 예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때는 `Double` 에 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="aa110-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa110-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="aa110-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="aa110-122">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="aa110-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="aa110-123">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aa110-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="aa110-124">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="aa110-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
