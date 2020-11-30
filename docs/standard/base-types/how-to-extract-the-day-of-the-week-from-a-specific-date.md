---
title: '방법: 특정 날짜의 요일 추출'
description: .NET에서 특정 날짜가 일주일 중 몇 번째 날인지 확인하는 방법을 알아봅니다. 특정 날짜에 대해 지역화된 요일 이름을 표시하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET], dates
- DateTime.DayOfWeek property
- DateTime.ToString method
- dates [.NET], retrieving week information
- DateTimeOffset.DayOfWeek property
- dates [.NET], day of week
- Weekday function
- day of week [.NET]
- extracting day of week
- weekday names
- WeekdayName function
- numbers [.NET], day of week
- formatting [.NET], time
- DateTimeOffset.ToString method
- full weekday names
ms.assetid: 1c9bef76-5634-46cf-b91c-9b9eb72091d7
ms.openlocfilehash: 9db11146ee9428ce22b08accacf7660137d539c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726992"
---
# <a name="how-to-extract-the-day-of-the-week-from-a-specific-date"></a><span data-ttu-id="5db43-104">방법: 특정 날짜의 요일 추출</span><span class="sxs-lookup"><span data-stu-id="5db43-104">How to: Extract the Day of the Week from a Specific Date</span></span>

<span data-ttu-id="5db43-105">.NET을 사용하면 쉽게 특정 날짜가 일주일 중 몇 번째 날인지 확인하고, 특정 날짜의 지역화된 요일 이름을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-105">.NET makes it easy to determine the ordinal day of the week for a particular date, and to display the localized weekday name for a particular date.</span></span> <span data-ttu-id="5db43-106">특정 날짜에 해당하는 요일을 나타내는 열거형 값은 <xref:System.DateTime.DayOfWeek%2A> 또는 <xref:System.DateTimeOffset.DayOfWeek%2A> 속성에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-106">An enumerated value that indicates the day of the week corresponding to a particular date is available from the <xref:System.DateTime.DayOfWeek%2A> or <xref:System.DateTimeOffset.DayOfWeek%2A> property.</span></span> <span data-ttu-id="5db43-107">이와 대조적으로 요일 이름을 검색하는 것은 날짜 및 시간 값의 `ToString` 메서드 또는 <xref:System.String.Format%2A?displayProperty=nameWithType> 메서드와 같은 서식 지정 메서드를 호출하여 수행할 수 있는 서식 지정 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-107">In contrast, retrieving the weekday name is a formatting operation that can be performed by calling a formatting method, such as a date and time value's `ToString` method or the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5db43-108">이 항목에서는 이러한 서식 지정 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-108">This topic shows how to perform these formatting operations.</span></span>  
  
## <a name="extract-a-number-indicating-the-day-of-the-week"></a><span data-ttu-id="5db43-109">요일을 나타내는 숫자 추출</span><span class="sxs-lookup"><span data-stu-id="5db43-109">Extract a number indicating the day of the week</span></span>
  
1. <span data-ttu-id="5db43-110">날짜의 문자열 표현에 대한 작업을 하는 경우에는 정적 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 메서드를 사용하여 해당 표현을 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-110">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="5db43-111"><xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> 속성을 사용하여 요일을 나타내는 <xref:System.DayOfWeek> 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-111">Use the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve a <xref:System.DayOfWeek> value that indicates the day of the week.</span></span>  
  
3. <span data-ttu-id="5db43-112">필요한 경우 <xref:System.DayOfWeek> 값을 정수로 캐스팅(C#의 경우) 또는 변환(Visual Basic의 경우)합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-112">If necessary, cast (in C#) or convert (in Visual Basic) the <xref:System.DayOfWeek> value to an integer.</span></span>  
  
 <span data-ttu-id="5db43-113">다음 예제에서는 특정 날짜의 요일을 나타내는 정수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-113">The following example displays an integer that represents the day of the week of a specific date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/weekdaynumber7.cs#7)]
 [!code-vb[Formatting.Howto.WeekdayName#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/weekdaynumber7.vb#7)]  
  
## <a name="extract-the-abbreviated-weekday-name"></a><span data-ttu-id="5db43-114">축약된 요일 이름 추출</span><span class="sxs-lookup"><span data-stu-id="5db43-114">Extract the abbreviated weekday name</span></span>
  
1. <span data-ttu-id="5db43-115">날짜의 문자열 표현에 대한 작업을 하는 경우에는 정적 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 메서드를 사용하여 해당 표현을 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-115">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="5db43-116">현재 문화권 또는 특정 문화권의 간략화된 요일 이름을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-116">You can extract the abbreviated weekday name of the current culture or of a specific culture:</span></span>  
  
    1. <span data-ttu-id="5db43-117">현재 문화권의 간략화된 요일 이름을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> 인스턴스 메서드를 호출하고 문자열 "ddd"를 `format` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-117">To extract the abbreviated weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="5db43-118">다음 예제에서는 <xref:System.DateTime.ToString%28System.String%29> 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-118">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname1.cs#1)]
         [!code-vb[Formatting.Howto.WeekdayName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname1.vb#1)]  
  
    2. <span data-ttu-id="5db43-119">특정 문화권의 간략화된 요일 이름을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-119">To extract the abbreviated weekday name for a specific culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="5db43-120">문자열 "ddd"를 `format` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-120">Pass the string "ddd" as the `format` parameter.</span></span> <span data-ttu-id="5db43-121"><xref:System.Globalization.CultureInfo> 또는 요일 이름을 <xref:System.Globalization.DateTimeFormatInfo> 매개 변수로 검색하려는 문화권을 나타내는 `provider` 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-121">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="5db43-122">다음 코드에서는 fr-FR 문화권을 나타내는 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> 개체를 사용하여 <xref:System.Globalization.CultureInfo> 메서드에 대한 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-122">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the fr-FR culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/abbrname2.cs#2)]
         [!code-vb[Formatting.Howto.WeekdayName#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/abbrname2.vb#2)]  
  
## <a name="extract-the-full-weekday-name"></a><span data-ttu-id="5db43-123">전체 요일 이름 추출</span><span class="sxs-lookup"><span data-stu-id="5db43-123">Extract the full weekday name</span></span>
  
1. <span data-ttu-id="5db43-124">날짜의 문자열 표현에 대한 작업을 하는 경우에는 정적 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 메서드를 사용하여 해당 표현을 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-124">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType> method.</span></span>  
  
2. <span data-ttu-id="5db43-125">현재 문화권 또는 특정 문화권의 전체 요일 이름을 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-125">You can extract the full weekday name of the current culture or of a specific culture:</span></span>  
  
    1. <span data-ttu-id="5db43-126">현재 문화권의 요일 이름을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> 인스턴스 메서드를 호출하고 문자열 “dddd”를 `format` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-126">To extract the weekday name for the current culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> instance method, and pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="5db43-127">다음 예제에서는 <xref:System.DateTime.ToString%28System.String%29> 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-127">The following example illustrates the call to the <xref:System.DateTime.ToString%28System.String%29> method.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname4.cs#4)]
         [!code-vb[Formatting.Howto.WeekdayName#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname4.vb#4)]  
  
    2. <span data-ttu-id="5db43-128">특정 문화권의 요일 이름을 추출하려면 날짜 및 시간 값의 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 인스턴스 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-128">To extract the weekday name for a specific culture, call the date and time value's <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="5db43-129">문자열 "dddd"를 `format` 매개 변수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-129">Pass the string "dddd" as the `format` parameter.</span></span> <span data-ttu-id="5db43-130"><xref:System.Globalization.CultureInfo> 또는 요일 이름을 <xref:System.Globalization.DateTimeFormatInfo> 매개 변수로 검색하려는 문화권을 나타내는 `provider` 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-130">Pass either a <xref:System.Globalization.CultureInfo> or a <xref:System.Globalization.DateTimeFormatInfo> object that represents the culture whose weekday name you want to retrieve as the `provider` parameter.</span></span> <span data-ttu-id="5db43-131">다음 코드에서는 es-ES 문화권을 나타내는 <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> 개체를 사용하여 <xref:System.Globalization.CultureInfo> 메서드에 대한 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-131">The following code illustrates a call to the <xref:System.DateTime.ToString%28System.String%2CSystem.IFormatProvider%29> method using a <xref:System.Globalization.CultureInfo> object that represents the es-ES culture.</span></span>  
  
         [!code-csharp[Formatting.Howto.WeekdayName#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/fullname5.cs#5)]
         [!code-vb[Formatting.Howto.WeekdayName#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/fullname5.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="5db43-132">예제</span><span class="sxs-lookup"><span data-stu-id="5db43-132">Example</span></span>  

 <span data-ttu-id="5db43-133">이 예제에서는 특정 날짜의 요일, 간략화된 요일 이름 및 전체 요일 이름을 나타내는 숫자를 검색하기 위해 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 및 <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> 속성과 <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> 및 <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> 메서드에 대한 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-133">The example illustrates calls to the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.DayOfWeek%2A?displayProperty=nameWithType> properties and the <xref:System.DateTime.ToString%2A?displayProperty=nameWithType> and <xref:System.DateTimeOffset.ToString%2A?displayProperty=nameWithType> methods to retrieve the number that represents the day of the week, the abbreviated weekday name, and the full weekday name for a particular date.</span></span>  
  
 [!code-csharp[Formatting.Howto.WeekdayName#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/example6.cs#6)]
 [!code-vb[Formatting.Howto.WeekdayName#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example6.vb#6)]  
  
 <span data-ttu-id="5db43-134">개별 언어는 .NET에서 제공하는 기능과 중복되거나 이러한 기능을 보완하는 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-134">Individual languages may provide functionality that duplicates or supplements the functionality provided by .NET.</span></span> <span data-ttu-id="5db43-135">예를 들어, Visual Basic에는 다음과 같은 두 가지 함수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-135">For example, Visual Basic includes two such functions:</span></span>  
  
- <span data-ttu-id="5db43-136">`Weekday`: 특정 날짜의 요일을 나타내는 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-136">`Weekday`, which returns a number that indicates the day of the week of a particular date.</span></span> <span data-ttu-id="5db43-137">이 함수는 요일의 첫날 서수 값을 1로 간주하는 반면, <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 속성은 이를 0으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-137">It considers the ordinal value of the first day of the week to be one, whereas the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property considers it to be zero.</span></span>  
  
- <span data-ttu-id="5db43-138">`WeekdayName`: 현재 문화권에서 특정 요일 숫자에 해당하는 요일 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-138">`WeekdayName`, which returns the name of the week in the current culture that corresponds to a particular weekday number.</span></span>  
  
 <span data-ttu-id="5db43-139">다음 예제에서는 Visual Basic `Weekday` 및 `WeekdayName` 함수의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-139">The following example illustrates the use of the Visual Basic `Weekday` and `WeekdayName` functions.</span></span>  
  
 [!code-vb[Formatting.HowTo.WeekdayName#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/example9.vb#9)]  
  
 <span data-ttu-id="5db43-140">또한 <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> 속성에서 반환하는 값을 사용하여 특정 날짜의 요일 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-140">You can also use the value returned by the <xref:System.DateTime.DayOfWeek%2A?displayProperty=nameWithType> property to retrieve the weekday name of a particular date.</span></span> <span data-ttu-id="5db43-141">이렇게 하려면 속성에서 반환하는 <xref:System.Enum.ToString%2A> 값에 대해 <xref:System.DayOfWeek> 메서드를 호출하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-141">This requires only a call to the <xref:System.Enum.ToString%2A> method on the <xref:System.DayOfWeek> value returned by the property.</span></span> <span data-ttu-id="5db43-142">그러나 이 방법은 다음 예제에 나와 있는 것처럼 현재 문화권의 지역화된 요일 이름을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5db43-142">However, this technique does not produce a localized weekday name for the current culture, as the following example illustrates.</span></span>  
  
 [!code-csharp[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/cs/Howto1.cs#8)]
 [!code-vb[Formatting.HowTo.WeekdayName#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.WeekdayName/vb/Howto1.vb#8)]

## <a name="see-also"></a><span data-ttu-id="5db43-143">참조</span><span class="sxs-lookup"><span data-stu-id="5db43-143">See also</span></span>

- [<span data-ttu-id="5db43-144">표준 날짜 및 시간 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="5db43-144">Standard Date and Time Format Strings</span></span>](standard-date-and-time-format-strings.md)
- [<span data-ttu-id="5db43-145">사용자 지정 날짜 및 시간 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="5db43-145">Custom Date and Time Format Strings</span></span>](custom-date-and-time-format-strings.md)
