---
title: 날짜, 시간 및 표준 시간대
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zone objects [.NET Framework]
- date and time data [.NET Framework]
- time zones [.NET Framework]
- times [.NET Framework], time zones
- time [.NET Framework], time zones
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
ms.openlocfilehash: 86602cd6e662b1b1057832247babc558ef67b79f
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84276935"
---
# <a name="dates-times-and-time-zones"></a><span data-ttu-id="12ad4-102">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="12ad4-102">Dates, times, and time zones</span></span>

<span data-ttu-id="12ad4-103">.NET에서는 기본 <xref:System.DateTime> 구조 외에도 다음과 같이 표준 시간대를 사용할 수 있는 클래스를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-103">In addition to the basic <xref:System.DateTime> structure, .NET provides the following classes that support working with time zones:</span></span>

* <xref:System.TimeZone>

  <span data-ttu-id="12ad4-104">이 클래스를 사용하여 시스템의 현지 표준 시간대와 UTC(협정 세계시) 영역을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-104">Use this class to work with the system's local time zone and the Coordinated Universal Time (UTC) zone.</span></span> <span data-ttu-id="12ad4-105">클래스의 기능은 <xref:System.TimeZone> 주로 클래스로 대체 됩니다 <xref:System.TimeZoneInfo> .</span><span class="sxs-lookup"><span data-stu-id="12ad4-105">The functionality of the <xref:System.TimeZone> class is largely superseded by the <xref:System.TimeZoneInfo> class.</span></span>

* <xref:System.TimeZoneInfo>

  <span data-ttu-id="12ad4-106">이 클래스를 사용하여 시스템에 미리 정의된 표준 시간대를 사용하고, 새 표준 시간대를 만들고, 한 표준 시간대에서 다른 표준 시간대로 날짜 및 시간을 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-106">Use this class to work with any time zone that is predefined on a system, to create new time zones, and to easily convert dates and times from one time zone to another.</span></span> <span data-ttu-id="12ad4-107">새로운 개발에는 <xref:System.TimeZone> 클래스 대신 <xref:System.TimeZoneInfo> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-107">For new development, use the <xref:System.TimeZoneInfo> class instead of the <xref:System.TimeZone> class.</span></span>

* <xref:System.DateTimeOffset>

  <span data-ttu-id="12ad4-108">이 구조를 사용하여 UTC의 해당 오프셋(또는 차이)가 알려진 날짜 및 시간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-108">Use this structure to work with dates and times whose offset (or difference) from UTC is known.</span></span> <span data-ttu-id="12ad4-109"><xref:System.DateTimeOffset> 구조체는 날짜 및 시간 값을 UTC의 해당 시간 오프셋과 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-109">The <xref:System.DateTimeOffset> structure combines a date and time value with that time's offset from UTC.</span></span> <span data-ttu-id="12ad4-110">UTC와의 관련성으로 인해 개별 날짜 및 시간 값은 단일 지점을 명확하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-110">Because of its relationship to UTC, an individual date and time value unambiguously identifies a single point in time.</span></span> <span data-ttu-id="12ad4-111">이렇게 하면 <xref:System.DateTime> 값보다는 <xref:System.DateTimeOffset> 값을 한 컴퓨터에서 다른 컴퓨터로 더욱 이식하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-111">This makes a <xref:System.DateTimeOffset> value more portable from one computer to another than a <xref:System.DateTime> value.</span></span>

<span data-ttu-id="12ad4-112">설명서의 이 섹션에서는 표준 시간대로 작업하고 날짜 및 시간 한 시간 표준 시간대에서 다른 표준 시간대로 변환할 수 있는 표준 시간대 인식 애플리케이션을 만들기 위해 필요한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-112">This section of the documentation provides the information that you need to work with time zones and to create time zone-aware applications that can convert dates and times from one time zone to another.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="12ad4-113">단원 내용</span><span class="sxs-lookup"><span data-stu-id="12ad4-113">In this section</span></span>

<span data-ttu-id="12ad4-114">[표준 시간대 개요](time-zone-overview.md) 표준 시간대 인식 애플리케이션을 만드는 데 관련된 용어, 개념 및 문제에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-114">[Time zone overview](time-zone-overview.md) Discusses the terminology, concepts, and issues involved in creating time zone-aware applications.</span></span>

<span data-ttu-id="12ad4-115">[DateTime, DateTimeOffset, TimeSpan 및 TimeZoneInfo 중에서 선택](choosing-between-datetime.md) <xref:System.DateTime> <xref:System.DateTimeOffset> <xref:System.TimeZoneInfo> 날짜 및 시간 데이터로 작업할 때, 및 형식을 사용 하는 경우에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-115">[Choosing between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo](choosing-between-datetime.md) Discusses when to use the <xref:System.DateTime>, <xref:System.DateTimeOffset>, and <xref:System.TimeZoneInfo> types when working with date and time data.</span></span>

<span data-ttu-id="12ad4-116">[로컬 시스템에 정의된 표준 시간대 찾기](finding-the-time-zones-on-local-system.md) 로컬 시스템에서 발견된 표준 시간대를 열거하는 방법에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-116">[Finding the time zones defined on a local system](finding-the-time-zones-on-local-system.md) Describes how to enumerate the time zones found on a local system.</span></span>

<span data-ttu-id="12ad4-117">[방법: 컴퓨터에 있는 표준 시간대 열거](enumerate-time-zones.md) 컴퓨터의 레지스트리에 정의된 표준 시간대를 열거하고 사용자가 목록에서 미리 정의된 표준 시간대를 선택할 수 있는 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-117">[How to: Enumerate time zones present on a computer](enumerate-time-zones.md) Provides examples that enumerate the time zones defined in a computer's registry and that let users select a predefined time zone from a list.</span></span>

<span data-ttu-id="12ad4-118">[방법: 미리 정의된 UTC 및 현지 표준 시간대 개체에 액세스](access-utc-and-local.md) 협정 세계시 및 현지 표준 시간대에 액세스하는 방법에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-118">[How to: Access the predefined UTC and local time zone objects](access-utc-and-local.md) Describes how to access Coordinated Universal Time and the local time zone.</span></span>

<span data-ttu-id="12ad4-119">[방법: TimeZoneInfo 개체 인스턴스화](instantiate-time-zone-info.md) 로컬 시스템 레지스트리에서 <xref:System.TimeZoneInfo> 개체를 인스턴스화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-119">[How to: Instantiate a TimeZoneInfo object](instantiate-time-zone-info.md) Describes how to instantiate a <xref:System.TimeZoneInfo> object from the local system registry.</span></span>

<span data-ttu-id="12ad4-120">[DateTimeOffset 개체 인스턴스화](instantiating-a-datetimeoffset-object.md)<xref:System.DateTimeOffset> 개체를 인스턴스화할 수 있는 방법 및 <xref:System.DateTime> 값을 <xref:System.DateTimeOffset> 값으로 변환할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-120">[Instantiating a DateTimeOffset object](instantiating-a-datetimeoffset-object.md) Discusses the ways in which a <xref:System.DateTimeOffset> object can be instantiated, and the ways in which a <xref:System.DateTime> value can be converted to a <xref:System.DateTimeOffset> value.</span></span>

<span data-ttu-id="12ad4-121">[방법: 조정 규칙을 사용하지 않고 표준 시간대 만들기](create-time-zones-without-adjustment-rules.md) 일광 절약 시간제와의 전환을 지원하지 않는 사용자 지정 표준 시간대를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-121">[How to: Create time zones without adjustment rules](create-time-zones-without-adjustment-rules.md) Describes how to create a custom time zone that does not support the transition to and from daylight saving time.</span></span>

<span data-ttu-id="12ad4-122">[방법: 조정 규칙을 사용하여 표준 시간대 만들기](create-time-zones-with-adjustment-rules.md) 일광 절약 시간제와의 전환을 하나 이상 지원하는 사용자 지정 표준 시간대를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-122">[How to: Create time zones with adjustment rules](create-time-zones-with-adjustment-rules.md) Describes how to create a custom time zone that supports one or more transitions to and from daylight saving time.</span></span>

<span data-ttu-id="12ad4-123">[표준 시간대 저장 및 복원](saving-and-restoring-time-zones.md) 표준 시간대 데이터의 serialization 및 deserialization에 대한 <xref:System.TimeZoneInfo> 지원에 관해 설명하고 이러한 기능을 사용할 수 있는 일부 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-123">[Saving and restoring time zones](saving-and-restoring-time-zones.md) Describes <xref:System.TimeZoneInfo> support for serialization and deserialization of time zone data and illustrates some of the scenarios in which these features can be used.</span></span>

<span data-ttu-id="12ad4-124">[방법: 포함 리소스에 표준 시간대 저장](save-time-zones-to-an-embedded-resource.md) 사용자 지정 표준 시간대를 만들고 리소스 파일에 해당 정보를 저장하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-124">[How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md) Describes how to create a custom time zone and save its information in a resource file.</span></span>

<span data-ttu-id="12ad4-125">[방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md) 포함된 리소스 파일에 저장된 사용자 지정 표준 시간대를 인스턴스화하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-125">[How to: Restore time zones from an embedded resource](restore-time-zones-from-an-embedded-resource.md) Describes how to instantiate custom time zones that have been saved to an embedded resource file.</span></span>

<span data-ttu-id="12ad4-126">[날짜 및 시간에 대한 산술 연산 수행](performing-arithmetic-operations.md)<xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값의 더하기, 빼기 및 비교와 관련된 문제에 관해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-126">[Performing arithmetic operations with dates and times](performing-arithmetic-operations.md) Discusses the issues involved in adding, subtracting, and comparing <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="12ad4-127">[방법: 날짜 및 시간 산술 연산의 표준 시간대 사용](use-time-zones-in-arithmetic.md) 표준 시간대의 조정 규칙을 반영하는 날짜 및 시간 산술 연산을 수행하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-127">[How to: Use time zones in date and time arithmetic](use-time-zones-in-arithmetic.md) Discusses how to perform date and time arithmetic that reflects a time zone's adjustment rules.</span></span>

<span data-ttu-id="12ad4-128">[DateTime과 DateTimeOffset 간 변환](converting-between-datetime-and-offset.md)<xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값 간에 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-128">[Converting between DateTime and DateTimeOffset](converting-between-datetime-and-offset.md) Describes how to convert between <xref:System.DateTime> and <xref:System.DateTimeOffset> values.</span></span>

<span data-ttu-id="12ad4-129">[표준 시간대 간에 시간 변환](converting-between-time-zones.md) 한 표준 시간대를 다른 표준 시간대로 변환하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-129">[Converting times between time zones](converting-between-time-zones.md) Describes how to convert times from one time zone to another.</span></span>

<span data-ttu-id="12ad4-130">[방법: 모호한 시간 확인](resolve-ambiguous-times.md) 모호한 시간을 표준 시간대의 표준 시간에 매핑하여 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-130">[How to: Resolve ambiguous times](resolve-ambiguous-times.md) Describes how to resolve an ambiguous time by mapping it to the time zone's standard time.</span></span>

<span data-ttu-id="12ad4-131">[방법: 사용자의 모호한 시간 확인 작업 허용](let-users-resolve-ambiguous-times.md) 사용자가 모호한 현지 시간과 협정 세계시 간의 매핑을 확인하도록 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12ad4-131">[How to: Let users resolve ambiguous times](let-users-resolve-ambiguous-times.md) Describes how to let a user determine the mapping between an ambiguous local time and Coordinated Universal Time.</span></span>

## <a name="reference"></a><span data-ttu-id="12ad4-132">참고</span><span class="sxs-lookup"><span data-stu-id="12ad4-132">Reference</span></span>

<xref:System.TimeZoneInfo?displayProperty=nameWithType>
