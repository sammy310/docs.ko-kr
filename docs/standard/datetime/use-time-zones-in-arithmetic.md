---
title: '방법: 날짜 및 시간 산술 연산의 표준 시간대 사용'
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
ms.openlocfilehash: 1acd53fad6b0ab173f855850353339190ebdd893
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132537"
---
# <a name="how-to-use-time-zones-in-date-and-time-arithmetic"></a><span data-ttu-id="56990-102">방법: 날짜 및 시간 산술 연산의 표준 시간대 사용</span><span class="sxs-lookup"><span data-stu-id="56990-102">How to: Use time zones in date and time arithmetic</span></span>

<span data-ttu-id="56990-103">일반적으로 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 값을 사용 하 여 날짜 및 시간 산술 연산을 수행 하는 경우 결과는 표준 시간대 조정 규칙을 반영 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56990-103">Ordinarily, when you perform date and time arithmetic using <xref:System.DateTime> or <xref:System.DateTimeOffset> values, the result does not reflect any time zone adjustment rules.</span></span> <span data-ttu-id="56990-104">이는 날짜 및 시간 값의 표준 시간대를 명확 하 게 식별할 수 있는 경우에도 마찬가지입니다. 예를 들어 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Local>로 설정 된 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="56990-104">This is true even when the time zone of the date and time value is clearly identifiable (for example, when the <xref:System.DateTime.Kind%2A> property is set to <xref:System.DateTimeKind.Local>).</span></span> <span data-ttu-id="56990-105">이 항목에서는 특정 표준 시간대에 속하는 날짜 및 시간 값에 대 한 산술 연산을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56990-105">This topic shows how to perform arithmetic operations on date and time values that belong to a particular time zone.</span></span> <span data-ttu-id="56990-106">산술 연산 작업의 결과는 표준 시간대의 조정 규칙을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-106">The results of the arithmetic operations will reflect the time zone's adjustment rules.</span></span>

### <a name="to-apply-adjustment-rules-to-date-and-time-arithmetic"></a><span data-ttu-id="56990-107">날짜 및 시간 산술 연산에 조정 규칙을 적용하려면</span><span class="sxs-lookup"><span data-stu-id="56990-107">To apply adjustment rules to date and time arithmetic</span></span>

1. <span data-ttu-id="56990-108">날짜 및 시간 값을 속해 있는 표준 시간대와 밀접하게 연결하는 몇 가지 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-108">Implement some method of closely coupling a date and time value with the time zone to which it belongs.</span></span> <span data-ttu-id="56990-109">예를 들어, 날짜 및 시간 값 및 해당 표준 시간대를 모두 포함하는 구조체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-109">For example, declare a structure that includes both the date and time value and its time zone.</span></span> <span data-ttu-id="56990-110">다음 예제에서는이 방법을 사용 하 여 <xref:System.DateTime> 값을 표준 시간대와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-110">The following example uses this approach to link a <xref:System.DateTime> value with its time zone.</span></span>

   [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
   [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]

2. <span data-ttu-id="56990-111"><xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> 메서드나 <xref:System.TimeZoneInfo.ConvertTime%2A> 메서드를 호출 하 여 시간을 UTC (협정 세계시)로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-111">Convert a time to Coordinated Universal Time (UTC) by calling either the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> method or the <xref:System.TimeZoneInfo.ConvertTime%2A> method.</span></span>

3. <span data-ttu-id="56990-112">UTC 시간에 대한 산술 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-112">Perform the arithmetic operation on the UTC time.</span></span>

4. <span data-ttu-id="56990-113"><xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 메서드를 호출 하 여 시간을 UTC에서 원래 시간의 연결 된 표준 시간대로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-113">Convert the time from UTC to the original time's associated time zone by calling the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span>

## <a name="example"></a><span data-ttu-id="56990-114">예제</span><span class="sxs-lookup"><span data-stu-id="56990-114">Example</span></span>

<span data-ttu-id="56990-115">다음 예제에서는 중부 표준시 2008년 3월 9일 오전 1시 30분에 2시간 30분을</span><span class="sxs-lookup"><span data-stu-id="56990-115">The following example adds two hours and thirty minutes to March 9, 2008, at 1:30 A.M.</span></span> <span data-ttu-id="56990-116">추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-116">Central Standard Time.</span></span> <span data-ttu-id="56990-117">30분 뒤인 2008년 3월 9일 오전 2시에 표준 시간대가 일광 절약 시간으로</span><span class="sxs-lookup"><span data-stu-id="56990-117">The time zone's transition to daylight saving time occurs thirty minutes later, at 2:00 A.M.</span></span> <span data-ttu-id="56990-118">이전 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-118">on March 9, 2008.</span></span> <span data-ttu-id="56990-119">이 예제에서는 이전 섹션의 네 단계를 수행하므로 결과 시간이 2008년 3월 9일 오전 5시로 올바르게</span><span class="sxs-lookup"><span data-stu-id="56990-119">Because the example follows the four steps listed in the previous section, it correctly reports the resulting time as 5:00 A.M.</span></span> <span data-ttu-id="56990-120">이전 코드와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-120">on March 9, 2008.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
[!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]

<span data-ttu-id="56990-121"><xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값은 모두 속할 수 있는 표준 시간대에서 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56990-121">Both <xref:System.DateTime> and <xref:System.DateTimeOffset> values are disassociated from any time zone to which they might belong.</span></span> <span data-ttu-id="56990-122">자동으로 표준 시간대의 조정 규칙을 적용하는 방식으로 날짜 및 시간 산술 연산을 수행하려면 모든 날짜 및 시간 값이 속해 있는 표준 시간대를 즉시 식별할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-122">To perform date and time arithmetic in a way that automatically applies a time zone's adjustment rules, the time zone to which any date and time value belongs must be immediately identifiable.</span></span> <span data-ttu-id="56990-123">즉, 날짜 및 시간과 관련된 표준 시간대는 밀접하게 결합되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-123">This means that a date and time and its associated time zone must be tightly coupled.</span></span> <span data-ttu-id="56990-124">여러 가지 방법을 통해 다음을 포함하는 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56990-124">There are several ways to do this, which include the following:</span></span>

- <span data-ttu-id="56990-125">애플리케이션에서 사용되는 모든 시간이 특정 표준 시간대에 속한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-125">Assume that all times used in an application belong to a particular time zone.</span></span> <span data-ttu-id="56990-126">일부 경우에는 적합하지만 이 방식은 제한된 유연성과 이식성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-126">Although appropriate in some cases, this approach offers limited flexibility and possibly limited portability.</span></span>

- <span data-ttu-id="56990-127">모두 형식의 필드로 포함하여 관련된 표준 시간대와 날짜 및 시간을 밀접하게 결합하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-127">Define a type that tightly couples a date and time with its associated time zone by including both as fields of the type.</span></span> <span data-ttu-id="56990-128">이 방법은 코드 예제에 사용되며 여기서 두 개의 구성원 필드에 있는 날짜 및 시간과 표준 시간대를 저장하는 구조체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-128">This approach is used in the code example, which defines a structure to store the date and time and the time zone in two member fields.</span></span>

<span data-ttu-id="56990-129">이 예제에서는 표준 시간대 조정 규칙이 결과에 적용 되도록 <xref:System.DateTime> 값에 산술 연산을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56990-129">The example illustrates how to perform arithmetic operations on <xref:System.DateTime> values so that time zone adjustment rules are applied to the result.</span></span> <span data-ttu-id="56990-130">그러나 <xref:System.DateTimeOffset> 값을 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56990-130">However, <xref:System.DateTimeOffset> values can be used just as easily.</span></span> <span data-ttu-id="56990-131">다음 예제에서는 원래 예제의 코드가 <xref:System.DateTime> 값 대신 <xref:System.DateTimeOffset>를 사용 하도록 조정 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56990-131">The following example illustrates how the code in the original example might be adapted to use <xref:System.DateTimeOffset> instead of <xref:System.DateTime> values.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
[!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]

<span data-ttu-id="56990-132">이 더하기를 먼저 UTC로 변환 하지 않고 <xref:System.DateTimeOffset> 값에 대해 수행 하는 경우 결과는 올바른 시점을 반영 하지만 해당 오프셋은 해당 시간에 지정 된 표준 시간대의 오프셋을 반영 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56990-132">Note that if this addition is simply performed on the <xref:System.DateTimeOffset> value without first converting it to UTC, the result reflects the correct point in time but its offset does not reflect that of the designated time zone for that time.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="56990-133">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="56990-133">Compiling the code</span></span>

<span data-ttu-id="56990-134">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="56990-134">This example requires:</span></span>

- <span data-ttu-id="56990-135"><xref:System> 네임 스페이스는 `using` 문을 사용 하 여 가져옵니다 (코드에 C# 필요).</span><span class="sxs-lookup"><span data-stu-id="56990-135">That the <xref:System> namespace be imported with the `using` statement (required in C# code).</span></span>

## <a name="see-also"></a><span data-ttu-id="56990-136">참조</span><span class="sxs-lookup"><span data-stu-id="56990-136">See also</span></span>

- [<span data-ttu-id="56990-137">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="56990-137">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="56990-138">날짜 및 시간에 대한 산술 연산 수행</span><span class="sxs-lookup"><span data-stu-id="56990-138">Performing arithmetic operations with dates and times</span></span>](../../../docs/standard/datetime/performing-arithmetic-operations.md)
