---
title: '방법: 조정 규칙을 사용하여 표준 시간대 만들기'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], creating
- time zones [.NET Framework], and adjustment rules
- adjustment rule [.NET Framework]
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: face995dbd5ba4b0b12e80bcef10a90b46c093ff
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586419"
---
# <a name="how-to-create-time-zones-with-adjustment-rules"></a><span data-ttu-id="08d35-102">방법: 조정 규칙을 사용하여 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="08d35-102">How to: Create time zones with adjustment rules</span></span>

<span data-ttu-id="08d35-103">응용 프로그램에 필요한 정확한 표준 시간대 정보를 여러 가지 이유로 특정 시스템에 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-103">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

* <span data-ttu-id="08d35-104">로컬 시스템 레지스트리에서 표준 시간대를 정의 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-104">The time zone has never been defined in the local system's registry.</span></span>

* <span data-ttu-id="08d35-105">표준 시간대에 대 한 데이터 수정 되었거나 레지스트리에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-105">Data about the time zone has been modified or removed from the registry.</span></span>

* <span data-ttu-id="08d35-106">표준 시간대는 중요 한 특정 기간에 대 한 표준 시간대 조정에 대 한 정확한 정보는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-106">The time zone does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="08d35-107">이러한 경우에 호출할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 응용 프로그램에 필요한 표준 시간대를 정의 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-107">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="08d35-108">표준 시간대를 사용 하 여 만들거나 조정 규칙 없이이 메서드의 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-108">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="08d35-109">표준 시간대 일광 절약 시간을 지 원하는 경우에 고정 또는 부동 조정 규칙 중 하나를 사용 하 여 조정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-109">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="08d35-110">(이러한 용어의 정의 "표준 시간대 용어" 섹션을 참조 하세요 [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md).)</span><span class="sxs-lookup"><span data-stu-id="08d35-110">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](../../../docs/standard/datetime/time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08d35-111">호출 하 여 만든 사용자 지정 표준 시간대를 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-111">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="08d35-112">대신 반환한 개체 참조를 통해서만 액세스할 수 있습니다는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-112">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="08d35-113">이 항목에서는 조정 규칙을 사용 하 여 시간대를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-113">This topic shows how to create a time zone with adjustment rules.</span></span> <span data-ttu-id="08d35-114">일광 절약 시간 조정 규칙을 지원 하지 않는 시간대를 만들려면 참조 [방법: 표준 시간대 조정 규칙 없이 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-114">To create a time zone that does not support daylight saving time adjustment rules, see [How to: Create Time Zones Without Adjustment Rules](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-with-floating-adjustment-rules"></a><span data-ttu-id="08d35-115">부동 조정 규칙을 표준 시간대를 만들려면</span><span class="sxs-lookup"><span data-stu-id="08d35-115">To create a time zone with floating adjustment rules</span></span>

1. <span data-ttu-id="08d35-116">(즉, 각 전환에서 및 특정 시간 간격에 대해 표준 시간으로 다시) 각 조정에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-116">For each adjustment (that is, for each transition away from and back to standard time over a particular time interval), do the following:</span></span>

    1. <span data-ttu-id="08d35-117">표준 시간대 조정에 대 한 시작 전환 시간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-117">Define the starting transition time for the time zone adjustment.</span></span>

       <span data-ttu-id="08d35-118">호출 해야 합니다 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 메서드 전달를 <xref:System.DateTime> 전환, 전환의 월을 정의 하는 정수 값, 전환 일 주를 정의 하는 정수 값의 시간을 정의 하는 값 및 <xref:System.DayOfWeek> 전환이 발생 하는 요일을 정의 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-118">You must call the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method and pass it a <xref:System.DateTime> value that defines the time of the transition, an integer value that defines the month of the transition, an integer value that defines the week on which the transition occurs, and a <xref:System.DayOfWeek> value that defines the day of the week on which the transition occurs.</span></span> <span data-ttu-id="08d35-119">이 메서드 호출은 인스턴스화하는 <xref:System.TimeZoneInfo.TransitionTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-119">This method call instantiates a <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    2. <span data-ttu-id="08d35-120">표준 시간대 조정에 대 한 끝 전환 시간을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-120">Define the ending transition time for the time zone adjustment.</span></span> <span data-ttu-id="08d35-121">이렇게 하려면 다른 호출에는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="08d35-121">This requires another call to the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="08d35-122">이 메서드 호출은 인스턴스화하는 두 번째 <xref:System.TimeZoneInfo.TransitionTime> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-122">This method call instantiates a second <xref:System.TimeZoneInfo.TransitionTime> object.</span></span>

    3. <span data-ttu-id="08d35-123">호출을 <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> 메서드 유효한 시작 및 종료 날짜를 조정의 전달 및는 <xref:System.TimeSpan> 전환 및 두 기간을 정의 하는 개체 <xref:System.TimeZoneInfo.TransitionTime> 시기를 정의 하는 개체와 일광에서 전환을 시간에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-123">Call the <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> method and pass it the effective start and end dates of the adjustment, a <xref:System.TimeSpan> object that defines the amount of time in the transition, and the two <xref:System.TimeZoneInfo.TransitionTime> objects that define when the transitions to and from daylight saving time occur.</span></span> <span data-ttu-id="08d35-124">이 메서드 호출은 인스턴스화하는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-124">This method call instantiates a <xref:System.TimeZoneInfo.AdjustmentRule> object.</span></span>

    4. <span data-ttu-id="08d35-125">할당 된 <xref:System.TimeZoneInfo.AdjustmentRule> 개체의 배열을 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-125">Assign the <xref:System.TimeZoneInfo.AdjustmentRule> object to an array of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span>

2. <span data-ttu-id="08d35-126">표준 시간대의 표시 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-126">Define the time zone's display name.</span></span> <span data-ttu-id="08d35-127">표시 이름을 시간대의 오프셋이 utc (협정 세계시) 괄호로 묶인 및 시간대 또는 표준 시간대 또는 하나에 있는 도시를 더 이상의 cou를 식별 하는 문자열 뒤에 대개 표준 형식을 따릅니다. ntries 또는 지역 표준 시간대에서입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-127">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

3. <span data-ttu-id="08d35-128">표준 시간대의 표준 시간 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-128">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="08d35-129">일반적으로이 문자열은 또한 해당 표준 시간대의 식별자로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-129">Typically, this string is also used as the time zone's identifier.</span></span>

4. <span data-ttu-id="08d35-130">표준 시간대의 일광 절약 시간제의 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-130">Define the name of the time zone's daylight time.</span></span>

5. <span data-ttu-id="08d35-131">표준 시간대의 표준 이름 보다 다른 식별자를 사용 하려는 경우 표준 시간대 식별자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-131">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

6. <span data-ttu-id="08d35-132">인스턴스화하는 <xref:System.TimeSpan> UTC 표준 시간대 오프셋을 정의 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-132">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="08d35-133">UTC 보다 늦은 시간을 사용 하 여 표준 시간대 오프셋은 양수입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-133">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="08d35-134">UTC 보다 이전 시간을 사용 하 여 표준 시간대 오프셋은 음수 경우</span><span class="sxs-lookup"><span data-stu-id="08d35-134">Time zones with times that are earlier than UTC have a negative offset.</span></span>

7. <span data-ttu-id="08d35-135">호출 된 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 새 표준 시간대를 인스턴스화하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-135">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="08d35-136">예제</span><span class="sxs-lookup"><span data-stu-id="08d35-136">Example</span></span>

<span data-ttu-id="08d35-137">다음 예에서는 현재 1918에서 시간 간격의 여러 조정 규칙을 포함 하는 미국 중앙 표준 시간대를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-137">The following example defines a Central Standard Time zone for the United States that includes adjustment rules for a variety of time intervals from 1918 to the present.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
[!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]

<span data-ttu-id="08d35-138">이 예제에서 만든 표준 시간대에 여러 조정 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-138">The time zone created in this example has multiple adjustment rules.</span></span> <span data-ttu-id="08d35-139">유효한 시작 및 종료 날짜 조정 규칙의 다른 조정 규칙의 날짜와 겹치지 않는 되도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-139">Care must be taken to ensure that the effective start and end dates of any adjustment rule do not overlap with the dates of another adjustment rule.</span></span> <span data-ttu-id="08d35-140">겹치는 경우는 <xref:System.InvalidTimeZoneException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-140">If there is an overlap, an <xref:System.InvalidTimeZoneException> is thrown.</span></span>

<span data-ttu-id="08d35-141">조정 규칙이 부동 소수점 값 5로 전달 됩니다는 `week` 의 매개 변수는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드는 특정 월의 마지막 주에 전환을 발생 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-141">For floating adjustment rules, the value 5 is passed to the `week` parameter of the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method to indicate that the transition occurs on the last week of a particular month.</span></span>

<span data-ttu-id="08d35-142">배열을 만드는 <xref:System.TimeZoneInfo.AdjustmentRule> 개체에서 사용 하는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> 메서드 호출 코드에는 표준 시간대에 대해 생성 될 조정 수가 필요한 크기를 해당 배열을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-142">In creating the array of <xref:System.TimeZoneInfo.AdjustmentRule> objects to use in the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=nameWithType> method call, the code could initialize the array to the size required by the number of adjustments to be created for the time zone.</span></span> <span data-ttu-id="08d35-143">이 코드 예제에서는 호출 하는 대신 합니다 <xref:System.Collections.Generic.List%601.Add%2A> 제네릭에 각 조정 규칙을 추가 하는 방법 <xref:System.Collections.Generic.List%601> 컬렉션 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-143">Instead, this code example calls the <xref:System.Collections.Generic.List%601.Add%2A> method to add each adjustment rule to a generic <xref:System.Collections.Generic.List%601> collection of <xref:System.TimeZoneInfo.AdjustmentRule> objects.</span></span> <span data-ttu-id="08d35-144">호출 된 <xref:System.Collections.Generic.List%601.CopyTo%2A> 이 컬렉션의 멤버를 배열에 복사 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-144">The code then calls the <xref:System.Collections.Generic.List%601.CopyTo%2A> method to copy the members of this collection to the array.</span></span>

<span data-ttu-id="08d35-145">또한이 예제에서는 <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> 조정 고정 날짜를 정의 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-145">The example also uses the <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> method to define fixed-date adjustments.</span></span> <span data-ttu-id="08d35-146">호출 비슷합니다는 <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> 메서드, 시간, 월 및 일의 전환 매개 변수를 필요 하다는 점을 제외 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-146">This is similar to calling the <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> method, except that it requires only the time, month, and day of the transition parameters.</span></span>

<span data-ttu-id="08d35-147">이 예제에서는 다음과 같은 코드를 사용 하 여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-147">The example can be tested using code such as the following:</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
[!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]

## <a name="compiling-the-code"></a><span data-ttu-id="08d35-148">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="08d35-148">Compiling the code</span></span>

<span data-ttu-id="08d35-149">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-149">This example requires:</span></span>

* <span data-ttu-id="08d35-150">다음 네임 스페이스를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08d35-150">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="08d35-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="08d35-151">See also</span></span>

- [<span data-ttu-id="08d35-152">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="08d35-152">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="08d35-153">표준 시간대 개요</span><span class="sxs-lookup"><span data-stu-id="08d35-153">Time zone overview</span></span>](../../../docs/standard/datetime/time-zone-overview.md)
- [<span data-ttu-id="08d35-154">방법: 표준 시간대 조정 규칙 없이 만들기</span><span class="sxs-lookup"><span data-stu-id="08d35-154">How to: Create time zones without adjustment rules</span></span>](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)
