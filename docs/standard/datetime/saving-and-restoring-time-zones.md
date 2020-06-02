---
title: 표준 시간대 저장 및 복원
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- restoring time zones
- deserialization [.NET Framework], time zones
- serialization [.NET Framework], time zones
- time zone objects [.NET Framework], restoring
- saving time zones
- time zone objects [.NET Framework], deserializing
- time zones [.NET Framework], saving
- time zones [.NET Framework], restoring
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 4028b310-e7ce-49d4-a646-1e83bfaf6f9d
ms.openlocfilehash: 8da26988d2e141ac704f0d3756cd8a50602cb3fd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84281052"
---
# <a name="saving-and-restoring-time-zones"></a><span data-ttu-id="9248b-102">표준 시간대 저장 및 복원</span><span class="sxs-lookup"><span data-stu-id="9248b-102">Saving and restoring time zones</span></span>

<span data-ttu-id="9248b-103">클래스는 레지스트리를 사용 <xref:System.TimeZoneInfo> 하 여 미리 정의 된 표준 시간대 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-103">The <xref:System.TimeZoneInfo> class relies on the registry to retrieve predefined time zone data.</span></span> <span data-ttu-id="9248b-104">그러나 레지스트리는 동적 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-104">However, the registry is a dynamic structure.</span></span> <span data-ttu-id="9248b-105">또한 레지스트리가 포함 하는 표준 시간대 정보는 운영 체제에서 주로 현재 연도의 시간 조정 및 변환을 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-105">Additionally, the time zone information that the registry contains is used by the operating system primarily to handle time adjustments and conversions for the current year.</span></span> <span data-ttu-id="9248b-106">이는 정확한 표준 시간대 데이터를 사용 하는 응용 프로그램에 대 한 두 가지 주요 영향을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-106">This has two major implications for applications that rely on accurate time zone data:</span></span>

- <span data-ttu-id="9248b-107">응용 프로그램에 필요한 표준 시간대가 레지스트리에 정의 되어 있지 않거나 레지스트리에서 제거 되었거나 이름이 바뀌었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-107">A time zone that is required by an application may not be defined in the registry, or it may have been renamed or removed from the registry.</span></span>

- <span data-ttu-id="9248b-108">레지스트리에 정의 된 표준 시간대에는 기록 표준 시간대 변환에 필요한 특정 조정 규칙에 대 한 정보가 부족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-108">A time zone that is defined in the registry may lack information about the particular adjustment rules that are necessary for historical time zone conversions.</span></span>

<span data-ttu-id="9248b-109"><xref:System.TimeZoneInfo>클래스는 표준 시간대 데이터의 serialization (저장) 및 deserialization (복원)을 지원 하 여 이러한 제한 사항을 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-109">The <xref:System.TimeZoneInfo> class addresses these limitations through its support for serialization (saving) and deserialization (restoring) of time zone data.</span></span>

## <a name="time-zone-serialization-and-deserialization"></a><span data-ttu-id="9248b-110">표준 시간대 직렬화 및 deserialization</span><span class="sxs-lookup"><span data-stu-id="9248b-110">Time zone serialization and deserialization</span></span>

<span data-ttu-id="9248b-111">표준 시간대 데이터를 serialize 및 deserialize 하 여 표준 시간대를 저장 하 고 복원 하는 작업에는 두 개의 메서드 호출만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-111">Saving and restoring a time zone by serializing and deserializing time zone data involves just two method calls:</span></span>

- <span data-ttu-id="9248b-112">개체 <xref:System.TimeZoneInfo> 의 메서드를 호출 하 여 개체를 serialize 할 수 있습니다 <xref:System.TimeZoneInfo.ToSerializedString%2A> .</span><span class="sxs-lookup"><span data-stu-id="9248b-112">You can serialize a <xref:System.TimeZoneInfo> object by calling that object's <xref:System.TimeZoneInfo.ToSerializedString%2A> method.</span></span> <span data-ttu-id="9248b-113">메서드는 매개 변수를 사용 하지 않고 표준 시간대 정보를 포함 하는 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-113">The method takes no parameters and returns a string that contains time zone information.</span></span>

- <span data-ttu-id="9248b-114"><xref:System.TimeZoneInfo>해당 문자열을 `static` ( `Shared` Visual Basic) 메서드에 전달 하 여 serialize 된 문자열에서 개체를 deserialize 할 수 있습니다 <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9248b-114">You can deserialize a <xref:System.TimeZoneInfo> object from a serialized string by passing that string to the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.FromSerializedString%2A?displayProperty=nameWithType> method.</span></span>

## <a name="serialization-and-deserialization-scenarios"></a><span data-ttu-id="9248b-115">Serialization 및 deserialization 시나리오</span><span class="sxs-lookup"><span data-stu-id="9248b-115">Serialization and deserialization scenarios</span></span>

<span data-ttu-id="9248b-116">개체를 문자열에 저장 하거나 serialize 하 <xref:System.TimeZoneInfo> 고 나중에 사용 하기 위해 복원 (또는 deserialize) 하는 기능을 사용 하면 유틸리티와 클래스의 유연성이 모두 향상 <xref:System.TimeZoneInfo> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-116">The ability to save (or serialize) a <xref:System.TimeZoneInfo> object to a string and to restore (or deserialize) it for later use increases both the utility and the flexibility of the <xref:System.TimeZoneInfo> class.</span></span> <span data-ttu-id="9248b-117">이 섹션에서는 serialization 및 deserialization이 가장 유용한 상황 중 일부를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-117">This section examines some of the situations in which serialization and deserialization are most useful.</span></span>

### <a name="serializing-and-deserializing-time-zone-data-in-an-application"></a><span data-ttu-id="9248b-118">응용 프로그램에서 표준 시간대 데이터 serialize 및 deserialize</span><span class="sxs-lookup"><span data-stu-id="9248b-118">Serializing and deserializing time zone data in an application</span></span>

<span data-ttu-id="9248b-119">필요한 경우 문자열에서 serialize 된 표준 시간대를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-119">A serialized time zone can be restored from a string when it is needed.</span></span> <span data-ttu-id="9248b-120">레지스트리에서 검색 한 표준 시간대가 특정 날짜 범위 내에서 날짜 및 시간을 올바르게 변환할 수 없는 경우 응용 프로그램에서이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-120">An application might do this if the time zone retrieved from the registry is unable to correctly convert a date and time within a particular date range.</span></span> <span data-ttu-id="9248b-121">예를 들어 Windows XP 레지스트리에서 표준 시간대 데이터는 단일 조정 규칙을 지원 하 고 Windows Vista 레지스트리에 정의 된 표준 시간대는 일반적으로 두 가지 조정 규칙에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-121">For example, time zone data in the Windows XP registry supports a single adjustment rule, while time zones defined in the Windows Vista registry typically provide information about two adjustment rules.</span></span> <span data-ttu-id="9248b-122">즉, 기록 시간 변환이 정확 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-122">This means that historical time conversions may be inaccurate.</span></span> <span data-ttu-id="9248b-123">표준 시간대 데이터의 Serialization 및 deserialization은 이러한 제한을 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-123">Serialization and deserialization of time zone data can handle this limitation.</span></span>

<span data-ttu-id="9248b-124">다음 예제에서는 미국의 일광 절약 시간을 도입하기 전에 1883년에서 1917년 사이의 미국 동부 표준시를 나타내는 사용자 지정 <xref:System.TimeZoneInfo> 클래스를 조정 규칙 없이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-124">In the following example, a custom <xref:System.TimeZoneInfo> class that has no adjustment rules is defined to represent the U.S. Eastern Standard Time zone from 1883 to 1917, before the introduction of daylight saving time in the United States.</span></span> <span data-ttu-id="9248b-125">사용자 지정 표준 시간대는 전역 범위를 갖는 변수에 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-125">The custom time zone is serialized in a variable that has global scope.</span></span> <span data-ttu-id="9248b-126">표준 시간대 변환 메서드인는 `ConvertUtcTime` 변환할 utc (협정 세계시) 시간에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-126">The time zone conversion method, `ConvertUtcTime`, is passed Coordinated Universal Time (UTC) times to convert.</span></span> <span data-ttu-id="9248b-127">1917 또는 이전 버전에서 날짜 및 시간이 발생 하는 경우 사용자 지정 동부 표준 표준 시간대는 직렬화 된 문자열에서 복원 되 고 레지스트리에서 검색 된 표준 시간대를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-127">If the date and time occurs in 1917 or earlier, the custom Eastern Standard Time zone is restored from a serialized string and replaces the time zone retrieved from the registry.</span></span>

[!code-csharp[System.TimeZone2.Serialization.1#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/cs/Serialization.cs#1)]
[!code-vb[System.TimeZone2.Serialization.1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.1/vb/Serialization.vb#1)]

### <a name="handling-time-zone-exceptions"></a><span data-ttu-id="9248b-128">표준 시간대 예외 처리</span><span class="sxs-lookup"><span data-stu-id="9248b-128">Handling time zone exceptions</span></span>

<span data-ttu-id="9248b-129">레지스트리는 동적 구조 이므로 해당 콘텐츠는 실수나 의도적인 수정이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-129">Because the registry is a dynamic structure, its contents are subject to accidental or deliberate modification.</span></span> <span data-ttu-id="9248b-130">즉, 레지스트리에 정의 되어야 하며 응용 프로그램을 성공적으로 실행 하는 데 필요한 표준 시간대가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-130">This means that a time zone that should be defined in the registry and that is required for an application to execute successfully may be absent.</span></span> <span data-ttu-id="9248b-131">표준 시간대 serialization 및 deserialization을 지원 하지 않으면 응용 프로그램을 종료 하 여 결과를 처리 하는 것이 거의 선택 되지 않습니다 <xref:System.TimeZoneNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="9248b-131">Without support for time zone serialization and deserialization, you have little choice but to handle the resulting <xref:System.TimeZoneNotFoundException> by ending the application.</span></span> <span data-ttu-id="9248b-132">그러나 표준 시간대 serialization 및 deserialization을 사용 하면 <xref:System.TimeZoneNotFoundException> serialize 된 문자열에서 필요한 표준 시간대를 복원 하 여 예기치 않은을 처리할 수 있으며 응용 프로그램은 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-132">However, by using time zone serialization and deserialization, you can handle an unexpected <xref:System.TimeZoneNotFoundException> by restoring the required time zone from a serialized string, and the application will continue to run.</span></span>

<span data-ttu-id="9248b-133">다음 예제에서는 사용자 지정 중부 표준 시간대를 만들고 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-133">The following example creates and serializes a custom Central Standard Time zone.</span></span> <span data-ttu-id="9248b-134">그런 다음 레지스트리에서 중앙 표준 시간대 검색을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-134">It then tries to retrieve the Central Standard Time zone from the registry.</span></span> <span data-ttu-id="9248b-135">검색 작업에서 또는를 throw 하는 경우 <xref:System.TimeZoneNotFoundException> <xref:System.InvalidTimeZoneException> 예외 처리기가 표준 시간대를 deserialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-135">If the retrieval operation throws either a <xref:System.TimeZoneNotFoundException> or an <xref:System.InvalidTimeZoneException>, the exception handler deserializes the time zone.</span></span>

[!code-csharp[System.TimeZone2.Serialization.2#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/cs/Serialization2.cs#1)]
[!code-vb[System.TimeZone2.Serialization.2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Serialization.2/vb/Serialization2.vb#1)]

### <a name="storing-a-serialized-string-and-restoring-it-when-needed"></a><span data-ttu-id="9248b-136">Serialize 된 문자열 저장 및 필요할 때 복원</span><span class="sxs-lookup"><span data-stu-id="9248b-136">Storing a serialized string and restoring it when needed</span></span>

<span data-ttu-id="9248b-137">이전 예에서는 표준 시간대 정보를 문자열 변수에 저장 하 고 필요할 때 복원 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-137">The previous examples have stored time zone information to a string variable and restored it when needed.</span></span> <span data-ttu-id="9248b-138">그러나 serialize 된 표준 시간대 정보를 포함 하는 문자열은 외부 파일, 응용 프로그램에 포함 된 리소스 파일 또는 레지스트리와 같은 일부 저장 미디어에 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-138">However, the string that contains serialized time zone information can itself be stored in some storage medium, such as an external file, a resource file embedded in the application, or the registry.</span></span> <span data-ttu-id="9248b-139">사용자 지정 표준 시간대에 대 한 정보는 레지스트리의 시스템 표준 시간대 키와 별도로 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-139">(Note that information about custom time zones should be stored apart from the system's time zone keys in the registry.)</span></span>

<span data-ttu-id="9248b-140">이러한 방식으로 serialize 된 표준 시간대 문자열을 저장 하면 표준 시간대 생성 루틴이 응용 프로그램 자체와 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-140">Storing a serialized time zone string in this manner also separates the time zone creation routine from the application itself.</span></span> <span data-ttu-id="9248b-141">예를 들어 표준 시간대 만들기 루틴은 응용 프로그램에서 사용할 수 있는 기록 표준 시간대 정보가 포함 된 데이터 파일을 실행 하 고 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-141">For example, a time zone creation routine can execute and create a data file that contains historical time zone information that an application can use.</span></span> <span data-ttu-id="9248b-142">그런 다음 응용 프로그램에 데이터 파일을 설치 하 고, 응용 프로그램에서 필요할 때 해당 표준 시간대를 하나 이상 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9248b-142">The data file can be then be installed with the application, and it can be opened and one or more of its time zones can be deserialized when the application requires them.</span></span>

<span data-ttu-id="9248b-143">포함 된 리소스를 사용 하 여 serialize 된 표준 시간대 데이터를 저장 하는 예제는 [방법: 포함 리소스에 표준 시간대 저장](save-time-zones-to-an-embedded-resource.md) 및 [방법: 포함 리소스에서 표준 시간대 복원](restore-time-zones-from-an-embedded-resource.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9248b-143">For an example that uses an embedded resource to store serialized time zone data, see [How to: Save time zones to an embedded resource](save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](restore-time-zones-from-an-embedded-resource.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9248b-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9248b-144">See also</span></span>

- [<span data-ttu-id="9248b-145">날짜, 시간 및 표준 시간대</span><span class="sxs-lookup"><span data-stu-id="9248b-145">Dates, times, and time zones</span></span>](index.md)
