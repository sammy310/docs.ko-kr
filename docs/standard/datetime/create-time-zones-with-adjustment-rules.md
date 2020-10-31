---
title: '방법: 조정 규칙을 사용하여 표준 시간대 만들기'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], creating
- time zones [.NET], and adjustment rules
- adjustment rule [.NET]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
ms.openlocfilehash: 28ab7c8ceabcfd64a6797cf5a85869c469963983
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063822"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="d8cb9-102">방법: 조정 규칙을 사용하여 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="d8cb9-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="d8cb9-103">응용 프로그램에 필요한 정확한 표준 시간대 정보는 다음과 같은 여러 가지 이유로 특정 시스템에 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="d8cb9-104">현지 시스템의 레지스트리에서 표준 시간대가 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-104">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="d8cb9-105">표준 시간대에 대 한 데이터가 레지스트리에서 수정 되었거나 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-105">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="d8cb9-106">표준 시간대에 특정 기록 기간의 표준 시간대 조정에 대 한 정확한 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="d8cb9-107">이러한 경우 메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 하 여 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="d8cb9-108">이 메서드의 오버 로드를 사용 하 여 조정 규칙을 사용 하거나 사용 하지 않고 표준 시간대를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="d8cb9-109">표준 시간대가 일광 절약 시간을 지 원하는 경우 고정 또는 부동 조정 규칙을 사용 하 여 조정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="d8cb9-110">이러한 용어에 대 한 정의는 [표준 시간대 개요](time-zone-overview.md)의 "표준 시간대 용어" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8cb9-111">메서드를 호출 하 여 만든 사용자 지정 표준 시간대 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 는 레지스트리에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="d8cb9-112">대신 메서드 호출에서 반환 되는 개체 참조를 통해서만 액세스할 수 있습니다 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> .</span><span class="sxs-lookup"><span data-stu-id="d8cb9-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="d8cb9-113">이 항목에서는 조정 규칙을 사용 하 여 표준 시간대를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="d8cb9-114">일광 절약 시간 조정 규칙을 지원 하지 않는 표준 시간대를 만들려면 [방법: 조정 규칙을 사용 하지 않고 표준 시간대 만들기](create-time-zones-without-adjustment-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="d8cb9-115">부동 조정 규칙을 사용 하 여 표준 시간대를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d8cb9-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="d8cb9-116">각 조정에 대해 (즉, 특정 시간 간격 동안 다시 표준 시간으로 전환 하는 경우) 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="d8cb9-117">표준 시간대 조정에 대 한 시작 전환 시간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="d8cb9-118">메서드를 호출 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 하 고 전환 <xref:System.DateTime> 시간을 정의 하는 값, 전환 월을 정의 하는 정수 값, 전환이 발생 하는 주를 정의 하는 정수 값 및 전환이 발생 하는 요일을 정의 하는 값을 전달 해야 합니다 <xref:System.DayOfWeek> .</span><span class="sxs-lookup"><span data-stu-id="d8cb9-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="d8cb9-119">이 메서드 호출은 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.TransitionTime> .</span><span class="sxs-lookup"><span data-stu-id="d8cb9-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="d8cb9-120">표준 시간대 조정의 종료 전환 시간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="d8cb9-121">이렇게 하려면 메서드를 다른 호출 해야 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d8cb9-122">이 메서드 호출은 두 번째 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.TransitionTime> .</span><span class="sxs-lookup"><span data-stu-id="d8cb9-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="d8cb9-123">메서드를 호출 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 하 고 조정의 유효한 시작 및 종료 날짜, <xref:System.TimeSpan> 전환 시간을 정의 하는 개체 및 <xref:System.TimeZoneInfo.TransitionTime> 일광 절약 시간으로 전환 하는 경우를 정의 하는 두 개의 개체를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="d8cb9-124">이 메서드 호출은 개체를 인스턴스화합니다 <xref:System.TimeZoneInfo.AdjustmentRule> .</span><span class="sxs-lookup"><span data-stu-id="d8cb9-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="d8cb9-125">개체를 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열에 할당 <xref:System.TimeZoneInfo.AdjustmentRule> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="d8cb9-126">표준 시간대의 표시 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-126">Define the time zone's display name.</span></span> <span data-ttu-id="d8cb9-127">표시 이름은 표준 시간대의 오프셋 (UTC)을 괄호로 묶고 표준 시간대를 나타내는 문자열, 표준 시간대에서 하나 이상의 도시 또는 표준 시간대의 국가 또는 지역 중 하나 이상에 해당 하는 문자열 뒤에 오는 매우 일반적인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="d8cb9-128">표준 시간대의 표준 시간 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="d8cb9-129">일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="d8cb9-130">표준 시간대의 일광 절약 시간 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="d8cb9-131">표준 시간대의 표준 이름과 다른 식별자를 사용 하려면 표준 시간대 식별자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="d8cb9-132"><xref:System.TimeSpan>UTC에서 표준 시간대의 오프셋을 정의 하는 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="d8cb9-133">시간이 UTC 보다 늦은 표준 시간대에는 양의 오프셋이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="d8cb9-134">시간이 UTC 보다 이전인 표준 시간대에는 음의 오프셋이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="d8cb9-135">메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 하 여 새 표준 시간대를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="d8cb9-136">예제</span><span class="sxs-lookup"><span data-stu-id="d8cb9-136">Example</span></span>

<span data-ttu-id="d8cb9-137">다음 예제에서는 1918부터 현재 까지의 다양 한 시간 간격에 대 한 조정 규칙을 포함 하는 미국에 대 한 중부 표준 시간대를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="d8cb9-138">이 예제에서 만든 표준 시간대에는 여러 조정 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="d8cb9-139">조정 규칙의 유효 시작 및 종료 날짜가 다른 조정 규칙의 날짜와 겹치지 않도록 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="d8cb9-140">겹치는 부분이 있으면 <xref:System.InvalidTimeZoneException> 이 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="d8cb9-141">부동 조정 규칙의 경우 값 5는 `week` 메서드의 매개 변수에 전달 되어 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 특정 월의 마지막 주에 전환이 발생 함을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="d8cb9-142"><xref:System.TimeZoneInfo.AdjustmentRule>메서드 호출에서 사용할 개체의 배열을 만들 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 때 코드는 표준 시간대에 대 한 조정 수에 필요한 크기에 맞게 배열을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="d8cb9-143">대신,이 코드 예제에서는 메서드를 호출 <xref:System.Collections.Generic.List%601.Add%2A> 하 여 각 조정 규칙을 <xref:System.Collections.Generic.List%601> 개체의 제네릭 컬렉션에 추가 <xref:System.TimeZoneInfo.AdjustmentRule> 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="d8cb9-144">그런 다음 코드는 메서드를 호출 <xref:System.Collections.Generic.List%601.CopyTo%2A> 하 여이 컬렉션의 멤버를 배열에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="d8cb9-145">또한이 예제에서는 메서드를 사용 하 여 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 고정 날짜 조정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="d8cb9-146">이는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 전환 매개 변수의 시간, 월 및 일만 필요 하다는 점을 제외 하 고 메서드를 호출 하는 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="d8cb9-147">예제는 다음과 같은 코드를 사용 하 여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="d8cb9-148">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="d8cb9-148">Compiling the code</span></span>

<span data-ttu-id="d8cb9-149">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-149">This example requires:</span></span>

- <span data-ttu-id="d8cb9-150">다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d8cb9-150">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="d8cb9-151">추가 정보</span><span class="sxs-lookup"><span data-stu-id="d8cb9-151">See also</span></span>

- [<span data-ttu-id="d8cb9-152">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="d8cb9-152">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="d8cb9-153">표준 시간대 개요</span><span class="sxs-lookup"><span data-stu-id="d8cb9-153">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="d8cb9-154">방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="d8cb9-154">How to: Create time zones without adjustment rules</span></span>](create-time-zones-without-adjustment-rules.md)
