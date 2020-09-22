---
title: CStr 함수의 반환 값
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
ms.openlocfilehash: cc5e5cc437175e9aebfba559488ca74283faa9ad
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870151"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="ab9ac-102">CStr 함수의 반환 값(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab9ac-102">Return Values for the CStr Function (Visual Basic)</span></span>

<span data-ttu-id="ab9ac-103">다음 표에서는 `CStr` 의 여러 데이터 형식에 대 한 반환 값을 설명 합니다 `expression` .</span><span class="sxs-lookup"><span data-stu-id="ab9ac-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="ab9ac-104">`expression`형식이 인 경우</span><span class="sxs-lookup"><span data-stu-id="ab9ac-104">If `expression` type is</span></span>|<span data-ttu-id="ab9ac-105">`CStr` return</span><span class="sxs-lookup"><span data-stu-id="ab9ac-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="ab9ac-106">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab9ac-106">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="ab9ac-107">"True" 또는 "False"를 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="ab9ac-108">날짜 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab9ac-108">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="ab9ac-109">`Date`시스템의 간단한 날짜 형식 값 (날짜 및 시간)을 포함 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="ab9ac-110">숫자 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab9ac-110">Numeric Data Types</span></span>](../../programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="ab9ac-111">숫자를 나타내는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="ab9ac-112">CStr 및 Date</span><span class="sxs-lookup"><span data-stu-id="ab9ac-112">CStr and Date</span></span>  

 <span data-ttu-id="ab9ac-113">형식에는 `Date` 항상 날짜 및 시간 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="ab9ac-114">형식 변환의 목적을 위해 Visual Basic은 1/1/0001 (1 년 1 월 1 일)을 날짜의 *중립 값* 으로 간주 하 고 00:00:00 (자정)을 시간에 대 한 중립 값으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="ab9ac-115">`CStr` 결과 문자열에 중립 값을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="ab9ac-116">예를 들어 문자열로 변환 하는 경우 `#January 1, 0001 9:30:00#` 결과는 "9:30:00 AM"이 고 날짜 정보는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="ab9ac-117">그러나 날짜 정보는 여전히 원래 값에 존재 하며와 `Date` 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="ab9ac-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ab9ac-118">`CStr`함수는 응용 프로그램의 현재 문화권 설정에 따라 변환을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="ab9ac-119">특정 문화권의 숫자에 대 한 문자열 표현을 가져오려면 숫자의 메서드를 사용 `ToString(IFormatProvider)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="ab9ac-120">예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을로 변환할 때를 사용 `Double` `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab9ac-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab9ac-121">참조</span><span class="sxs-lookup"><span data-stu-id="ab9ac-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="ab9ac-122">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="ab9ac-122">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="ab9ac-123">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab9ac-123">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="ab9ac-124">날짜 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ab9ac-124">Date Data Type</span></span>](../data-types/date-data-type.md)
