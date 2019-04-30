---
title: '방법: 날짜 및 시간 산술 연산에서 표준 시간대 사용'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], arithmetic operations
- arithmetic operations [.NET Framework], dates and times
- dates [.NET Framework], adding and subtracting
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 053ca2d10deadf58d5bb8b4628fb5dee815d82c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026499"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="ef144-102">방법: 날짜 및 시간 산술 연산에서 표준 시간대 사용</span><span class="sxs-lookup"><span data-stu-id="ef144-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="ef144-103">일반적으로 날짜를 수행 하 고 사용 하 여 산술 시간 있습니다 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 결과 값은 모든 표준 시간대 조정 규칙을 반영 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="ef144-104">이것이 true가 날짜 및 시간 값의 표준 시간대 명확 하 게 식별할 수 있는 경우에 (경우에 예를 들어 합니다 <xref:System.DateTime.Kind%2A> 속성 <xref:System.DateTimeKind.Local>).</span><span class="sxs-lookup"><span data-stu-id="ef144-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="ef144-105">이 항목에서는 특정 표준 시간대에 속하는 날짜 및 시간 값에 산술 연산을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="ef144-106">산술 연산 작업의 결과는 표준 시간대의 조정 규칙을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="ef144-107">날짜 및 시간 산술 연산에 조정 규칙을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="ef144-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="ef144-108">날짜 및 시간 값을 속해 있는 표준 시간대와 밀접하게 연결하는 몇 가지 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="ef144-109">예를 들어, 날짜 및 시간 값 및 해당 표준 시간대를 모두 포함하는 구조체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="ef144-110">다음 예제에서는이 방법을 사용 하 여 연결을 <xref:System.DateTime> 해당 표준 시간대를 사용 하 여 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="ef144-111">호출 하 여 시간을 utc (협정 세계시)로 변환 합니다 <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 메서드 또는 <xref:System.TimeZoneInfo.ConvertTime%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ef144-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="ef144-112">UTC 시간에 대한 산술 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="ef144-113">호출 하 여 원래 시간과 관련 된 표준 시간대를 UTC에서 시간을 변환 합니다 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ef144-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="ef144-114">예제</span><span class="sxs-lookup"><span data-stu-id="ef144-114">Example</span></span>

<span data-ttu-id="ef144-115">다음 예제에서는 중부 표준시 2008년 3월 9일 오전 1시 30분에 2시간 30분을</span><span class="sxs-lookup"><span data-stu-id="ef144-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="ef144-116">추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-116">Central Standard Time.</span></span> <span data-ttu-id="ef144-117">30분 뒤인 2008년 3월 9일 오전 2시에 표준 시간대가 일광 절약 시간으로</span><span class="sxs-lookup"><span data-stu-id="ef144-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="ef144-118">전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-118">on March 9, 2008.</span></span> <span data-ttu-id="ef144-119">이 예제에서는 이전 섹션의 네 단계를 수행하므로 결과 시간이 2008년 3월 9일 오전 5시로 올바르게</span><span class="sxs-lookup"><span data-stu-id="ef144-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="ef144-120">이전 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="ef144-121">둘 다 <xref:System.DateTime> 고 <xref:System.DateTimeOffset> 값 속할 수 있는 표준 시간대에서 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="ef144-122">자동으로 표준 시간대의 조정 규칙을 적용하는 방식으로 날짜 및 시간 산술 연산을 수행하려면 모든 날짜 및 시간 값이 속해 있는 표준 시간대를 즉시 식별할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="ef144-123">즉, 날짜 및 시간과 관련된 표준 시간대는 밀접하게 결합되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="ef144-124">여러 가지 방법을 통해 다음을 포함하는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-124">There are several ways to do this, which include the following:</span></span>

* <span data-ttu-id="ef144-125">애플리케이션에서 사용되는 모든 시간이 특정 표준 시간대에 속한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="ef144-126">일부 경우에는 적합하지만 이 방식은 제한된 유연성과 이식성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

* <span data-ttu-id="ef144-127">모두 형식의 필드로 포함하여 관련된 표준 시간대와 날짜 및 시간을 밀접하게 결합하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="ef144-128">이 방법은 코드 예제에 사용되며 여기서 두 개의 구성원 필드에 있는 날짜 및 시간과 표준 시간대를 저장하는 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="ef144-129">예제에 산술 연산을 수행 하는 방법에 <xref:System.DateTime> 값 시간대 조정 규칙 결과에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="ef144-130">그러나 <xref:System.DateTimeOffset> 값을 간단 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="ef144-131">다음 예제에서는 원래 예제에서 코드를 사용 하 여 적용할 수 있습니다 하는 방법을 보여 줍니다 <xref:System.DateTimeOffset> 대신 <xref:System.DateTime> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="ef144-132">이 추가에 대해 간단히 수행 하는 경우는 <xref:System.DateTimeOffset> 첫째 UTC로 변환한 결과 올바른 시점이 반영 하지만 해당 오프셋 반영 되지 않습니다 지정 된 표준 시간대의 해당 시간에 대 한 없는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="ef144-133">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ef144-133">Compiling the code</span></span>

<span data-ttu-id="ef144-134">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-134">This example requires:</span></span>

* <span data-ttu-id="ef144-135">System.Core.dll에 대 한 참조를 프로젝트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef144-135">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="ef144-136">합니다 <xref:System> 네임 스페이스를 사용 하 여 가져와야 합니다 `using` 문 (C# 코드에 필요).</span><span class="sxs-lookup"><span data-stu-id="ef144-136">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="ef144-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="ef144-137">See also</span></span>

- [<span data-ttu-id="ef144-138">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="ef144-138">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="ef144-139">날짜 및 시간에 대한 산술 연산 수행</span><span class="sxs-lookup"><span data-stu-id="ef144-139">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)
