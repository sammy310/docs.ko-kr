---
description: '자세한 정보: 방법: 모호한 시간 확인'
title: '방법: 모호한 시간 확인'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], ambiguous time
- ambiguous time [.NET]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
ms.openlocfilehash: 743aff3303669efcf20e233b1f5b2d520475d5f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702524"
---
# <a name="how-to-resolve-ambiguous-times"></a><span data-ttu-id="94f38-103">방법: 모호한 시간 확인</span><span class="sxs-lookup"><span data-stu-id="94f38-103">How to: Resolve ambiguous times</span></span>

<span data-ttu-id="94f38-104">모호한 시간은 하나 이상의 UTC(협정 세계시)를 매핑하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-104">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="94f38-105">표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-105">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="94f38-106">모호한 시간을 처리하는 경우 다음 중 하나를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-106">When handling an ambiguous time, you can do one of the following:</span></span>

- <span data-ttu-id="94f38-107">시간을 UTC로 매핑하는 방법에 대해 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-107">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="94f38-108">예를 들어 있는 모호한 시간을 항상 표준 시간대의 표준 시간으로 표시한다고 가정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-108">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

- <span data-ttu-id="94f38-109">모호한 시간이 사용자로부터 입력된 데이터 항목인 경우 사용자가 모호성을 해결하도록 맡기면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-109">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

<span data-ttu-id="94f38-110">이 항목에서는 모호한 시간을 표준 시간대의 표준 시간을 나타내는 것으로 가정 하 여 해결 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-110">This topic shows how to resolve an ambiguous time by assuming that it represents the time zone's standard time.</span></span>

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a><span data-ttu-id="94f38-111">모호한 시간을 표준 시간대의 표준 시간으로 매핑하려면</span><span class="sxs-lookup"><span data-stu-id="94f38-111">To map an ambiguous time to a time zone's standard time</span></span>

1. <span data-ttu-id="94f38-112"><xref:System.TimeZoneInfo.IsAmbiguousTime%2A>시간이 모호한 지 여부를 확인 하려면 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-112">Call the <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> method to determine whether the time is ambiguous.</span></span>

2. <span data-ttu-id="94f38-113">시간이 모호한 경우 표준 <xref:System.TimeSpan> 시간대의 속성에 의해 반환 된 개체에서 시간을 뺍니다 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .</span><span class="sxs-lookup"><span data-stu-id="94f38-113">If the time is ambiguous, subtract the time from the <xref:System.TimeSpan> object returned by the time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property.</span></span>

3. <span data-ttu-id="94f38-114">`static`( `Shared` Visual Basic .net) 메서드를 호출 <xref:System.DateTime.SpecifyKind%2A> 하 여 UTC 날짜 및 시간 값의 속성을 <xref:System.DateTime.Kind%2A> 로 설정 합니다 <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="94f38-114">Call the `static` (`Shared` in Visual Basic .NET) <xref:System.DateTime.SpecifyKind%2A> method to set the UTC date and time value's <xref:System.DateTime.Kind%2A> property to <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="94f38-115">예제</span><span class="sxs-lookup"><span data-stu-id="94f38-115">Example</span></span>

<span data-ttu-id="94f38-116">다음 예제에서는 모호한 시간을 UTC로 변환 하는 방법을 보여 줍니다 .이는 현지 표준 시간대의 표준 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-116">The following example illustrates how to convert an ambiguous time to UTC by assuming that it represents the local time zone's standard time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

<span data-ttu-id="94f38-117">예제는 `ResolveAmbiguousTime` 전달 된 값이 모호한 지 여부를 결정 하는 라는 메서드로 구성 됩니다 <xref:System.DateTime> .</span><span class="sxs-lookup"><span data-stu-id="94f38-117">The example consists of a method named `ResolveAmbiguousTime` that determines whether the <xref:System.DateTime> value passed to it is ambiguous.</span></span> <span data-ttu-id="94f38-118">값이 모호한 경우 메서드는 <xref:System.DateTime> 해당 UTC 시간을 나타내는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-118">If the value is ambiguous, the method returns a <xref:System.DateTime> value that represents the corresponding UTC time.</span></span> <span data-ttu-id="94f38-119">메서드는 현지 시간에서 현지 표준 시간대의 속성 값을 빼서이 변환을 처리 합니다 <xref:System.TimeZoneInfo.BaseUtcOffset%2A> .</span><span class="sxs-lookup"><span data-stu-id="94f38-119">The method handles this conversion by subtracting the value of the local time zone's <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property from the local time.</span></span>

<span data-ttu-id="94f38-120">일반적으로 모호한 시간의 <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> <xref:System.TimeSpan> 가능한 UTC 오프셋을 포함 하는 개체의 배열을 검색 하기 위해 메서드를 호출 하 여 모호한 시간을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-120">Ordinarily, an ambiguous time is handled by calling the <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> method to retrieve an array of <xref:System.TimeSpan> objects that contain the ambiguous time's possible UTC offsets.</span></span> <span data-ttu-id="94f38-121">그러나 이 예제에서는 모호한 시간이 표준 시간대의 표준 시간으로 항상 매핑되어야 한다고 임의로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-121">However, this example makes the arbitrary assumption that an ambiguous time should always be mapped to the time zone's standard time.</span></span> <span data-ttu-id="94f38-122"><xref:System.TimeZoneInfo.BaseUtcOffset%2A>속성은 UTC와 표준 시간대의 표준 시간 사이의 오프셋을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-122">The <xref:System.TimeZoneInfo.BaseUtcOffset%2A> property returns the offset between UTC and a time zone's standard time.</span></span>

<span data-ttu-id="94f38-123">이 예제에서는 로컬 표준 시간대에 대 한 모든 참조가 속성을 통해 수행 됩니다. <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 로컬 표준 시간대는 개체 변수에 할당 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-123">In this example, all references to the local time zone are made through the <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="94f38-124">이 방법은 메서드를 호출 하 여 <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> 현지 표준 시간대가 할당 된 모든 개체를 무효화 하기 때문에 권장 되는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-124">This is a recommended practice because a call to the <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType> method invalidates any objects that the local time zone is assigned to.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="94f38-125">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="94f38-125">Compiling the code</span></span>

<span data-ttu-id="94f38-126">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="94f38-126">This example requires:</span></span>

- <span data-ttu-id="94f38-127"><xref:System>문을 사용 하 여 네임 스페이스를 가져옵니다 `using` (c # 코드에 필요).</span><span class="sxs-lookup"><span data-stu-id="94f38-127">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="94f38-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94f38-128">See also</span></span>

- [<span data-ttu-id="94f38-129">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="94f38-129">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="94f38-130">방법: 사용자에게 모호한 시간 확인 작업 허용</span><span class="sxs-lookup"><span data-stu-id="94f38-130">How to: Let users resolve ambiguous times</span></span>](let-users-resolve-ambiguous-times.md)
