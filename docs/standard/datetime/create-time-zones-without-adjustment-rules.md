---
description: '자세히 알아보기: 방법: 조정 규칙을 사용 하지 않고 표준 시간대 만들기'
title: '방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기'
ms.date: 04/10/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET], adjustment rule
- time zones [.NET], creating
- adjustment rule [.NET]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
ms.openlocfilehash: c2d1f2d2ea21c53c6a3b41603be4f31ec5442a30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99702732"
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a><span data-ttu-id="76986-103">방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="76986-103">How to: Create time zones without adjustment rules</span></span>

<span data-ttu-id="76986-104">응용 프로그램에 필요한 정확한 표준 시간대 정보는 다음과 같은 여러 가지 이유로 특정 시스템에 표시 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-104">The precise time zone information that is required by an application may not be present on a particular system for several reasons:</span></span>

- <span data-ttu-id="76986-105">현지 시스템의 레지스트리에서 표준 시간대가 정의 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-105">The time zone has never been defined in the local system's registry.</span></span>

- <span data-ttu-id="76986-106">표준 시간대에 대 한 데이터가 레지스트리에서 수정 되었거나 제거 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-106">Data about the time zone has been modified or removed from the registry.</span></span>

- <span data-ttu-id="76986-107">표준 시간대가 있지만 특정 기록 기간의 표준 시간대 조정에 대 한 정확한 정보가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-107">The time zone exists but does not have accurate information about time zone adjustments for a particular historic period.</span></span>

<span data-ttu-id="76986-108">이러한 경우 메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 하 여 응용 프로그램에 필요한 표준 시간대를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-108">In these cases, you can call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method to define the time zone required by your application.</span></span> <span data-ttu-id="76986-109">이 메서드의 오버 로드를 사용 하 여 조정 규칙을 사용 하거나 사용 하지 않고 표준 시간대를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-109">You can use the overloads of this method to create a time zone with or without adjustment rules.</span></span> <span data-ttu-id="76986-110">표준 시간대가 일광 절약 시간을 지 원하는 경우 고정 또는 부동 조정 규칙을 사용 하 여 조정을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-110">If the time zone supports daylight saving time, you can define adjustments with either fixed or floating adjustment rules.</span></span> <span data-ttu-id="76986-111">이러한 용어에 대 한 정의는 [표준 시간대 개요](time-zone-overview.md)의 "표준 시간대 용어" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76986-111">(For definitions of these terms, see the "Time Zone Terminology" section in [Time zone overview](time-zone-overview.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="76986-112">메서드를 호출 하 여 만든 사용자 지정 표준 시간대 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 는 레지스트리에 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-112">Custom time zones created by calling the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method are not added to the registry.</span></span> <span data-ttu-id="76986-113">대신 메서드 호출에서 반환 되는 개체 참조를 통해서만 액세스할 수 있습니다 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> .</span><span class="sxs-lookup"><span data-stu-id="76986-113">Instead, they can be accessed only through the object reference returned by the <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> method call.</span></span>

<span data-ttu-id="76986-114">이 항목에서는 조정 규칙을 사용 하지 않고 표준 시간대를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="76986-114">This topic shows how to create a time zone without adjustment rules.</span></span> <span data-ttu-id="76986-115">일광 절약 시간 조정 규칙을 지 원하는 표준 시간대를 만들려면 [방법: 조정 규칙을 사용 하 여 표준 시간대 만들기](create-time-zones-with-adjustment-rules.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="76986-115">To create a time zone that supports daylight saving time adjustment rules, see [How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md).</span></span>

### <a name="to-create-a-time-zone-without-adjustment-rules"></a><span data-ttu-id="76986-116">조정 규칙을 사용 하지 않고 표준 시간대를 만들려면</span><span class="sxs-lookup"><span data-stu-id="76986-116">To create a time zone without adjustment rules</span></span>

1. <span data-ttu-id="76986-117">표준 시간대의 표시 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-117">Define the time zone's display name.</span></span>

   <span data-ttu-id="76986-118">표시 이름은 표준 시간대의 오프셋 (UTC)을 괄호로 묶고 표준 시간대를 나타내는 문자열, 표준 시간대에서 하나 이상의 도시 또는 표준 시간대의 국가 또는 지역 중 하나 이상에 해당 하는 문자열 뒤에 오는 매우 일반적인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76986-118">The display name follows a fairly standard format in which the time zone's offset from Coordinated Universal Time (UTC) is enclosed in parentheses and is followed by a string that identifies the time zone, one or more of the cities in the time zone, or one or more of the countries or regions in the time zone.</span></span>

2. <span data-ttu-id="76986-119">표준 시간대의 표준 시간 이름을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-119">Define the name of the time zone's standard time.</span></span> <span data-ttu-id="76986-120">일반적으로이 문자열은 표준 시간대의 식별자로도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76986-120">Typically, this string is also used as the time zone's identifier.</span></span>

3. <span data-ttu-id="76986-121">표준 시간대의 표준 이름과 다른 식별자를 사용 하려면 표준 시간대 식별자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-121">If you want to use a different identifier than the time zone's standard name, define the time zone identifier.</span></span>

4. <span data-ttu-id="76986-122"><xref:System.TimeSpan>UTC에서 표준 시간대의 오프셋을 정의 하는 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-122">Instantiate a <xref:System.TimeSpan> object that defines the time zone's offset from UTC.</span></span> <span data-ttu-id="76986-123">시간이 UTC 보다 늦은 표준 시간대에는 양의 오프셋이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-123">Time zones with times that are later than UTC have a positive offset.</span></span> <span data-ttu-id="76986-124">시간이 UTC 보다 이전인 표준 시간대에는 음의 오프셋이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76986-124">Time zones with times that are earlier than UTC have a negative offset.</span></span>

5. <span data-ttu-id="76986-125">메서드를 호출 <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> 하 여 새 표준 시간대를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-125">Call the <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType> method to instantiate the new time zone.</span></span>

## <a name="example"></a><span data-ttu-id="76986-126">예제</span><span class="sxs-lookup"><span data-stu-id="76986-126">Example</span></span>

<span data-ttu-id="76986-127">다음 예제에서는 조정 규칙이 없는 모슨에 대 한 사용자 지정 표준 시간대를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-127">The following example defines a custom time zone for Mawson, Antarctica, which has no adjustment rules.</span></span>

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

<span data-ttu-id="76986-128">속성에 할당 된 문자열은 표준 시간대의 <xref:System.TimeZoneInfo.DisplayName%2A> 오프셋 뒤에 표준 시간대에 대 한 설명이 표시 되는 표준 형식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="76986-128">The string assigned to the <xref:System.TimeZoneInfo.DisplayName%2A> property follows a standard format in which the time zone's offset from UTC is followed by a friendly description of the time zone.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="76986-129">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="76986-129">Compiling the code</span></span>

<span data-ttu-id="76986-130">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="76986-130">This example requires:</span></span>

- <span data-ttu-id="76986-131">다음 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76986-131">That the following namespaces be imported:</span></span>

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a><span data-ttu-id="76986-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76986-132">See also</span></span>

- [<span data-ttu-id="76986-133">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="76986-133">Dates, times, and time zones</span></span>](index.md)
- [<span data-ttu-id="76986-134">표준 시간대 개요</span><span class="sxs-lookup"><span data-stu-id="76986-134">Time zone overview</span></span>](time-zone-overview.md)
- [<span data-ttu-id="76986-135">방법: 조정 규칙을 사용하여 표준 시간대 만들기</span><span class="sxs-lookup"><span data-stu-id="76986-135">How to: Create time zones with adjustment rules</span></span>](create-time-zones-with-adjustment-rules.md)
