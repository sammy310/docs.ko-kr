---
title: <EnableAmPmParseAdjustment> 요소
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222512"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="ffeee-102">\<EnableAmPmParseAdjustment > 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="ffeee-103">날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 조정 된 규칙 집합을 사용할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="ffeee-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ffeee-104">\<configuration></span></span>  
 <span data-ttu-id="ffeee-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ffeee-105">\<runtime></span></span>  
<span data-ttu-id="ffeee-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="ffeee-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffeee-107">구문</span><span class="sxs-lookup"><span data-stu-id="ffeee-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffeee-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ffeee-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffeee-110">특성</span><span class="sxs-lookup"><span data-stu-id="ffeee-110">Attributes</span></span>  
  
|<span data-ttu-id="ffeee-111">특성</span><span class="sxs-lookup"><span data-stu-id="ffeee-111">Attribute</span></span>|<span data-ttu-id="ffeee-112">설명</span><span class="sxs-lookup"><span data-stu-id="ffeee-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ffeee-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ffeee-114">날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 조정 된 규칙 집합을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="ffeee-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="ffeee-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ffeee-116">값</span><span class="sxs-lookup"><span data-stu-id="ffeee-116">Value</span></span>|<span data-ttu-id="ffeee-117">설명</span><span class="sxs-lookup"><span data-stu-id="ffeee-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ffeee-118">0</span><span class="sxs-lookup"><span data-stu-id="ffeee-118">0</span></span>|<span data-ttu-id="ffeee-119">날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정된 규칙을 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ffeee-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="ffeee-120">1</span><span class="sxs-lookup"><span data-stu-id="ffeee-120">1</span></span>|<span data-ttu-id="ffeee-121">날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정 된 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffeee-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-122">Child Elements</span></span>  
 <span data-ttu-id="ffeee-123">없음</span><span class="sxs-lookup"><span data-stu-id="ffeee-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffeee-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ffeee-125">요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-125">Element</span></span>|<span data-ttu-id="ffeee-126">설명</span><span class="sxs-lookup"><span data-stu-id="ffeee-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ffeee-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ffeee-128">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffeee-129">설명</span><span class="sxs-lookup"><span data-stu-id="ffeee-129">Remarks</span></span>  
 <span data-ttu-id="ffeee-130">`<EnableAmPmParseAdjustment>` 요소는 다음 방법 숫자 일 및 월을 시간 하 고 (예: "4 월 10 6 AM")는 AM/PM 지정자 뒤에 있는 날짜 문자열의 구문을 분석 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="ffeee-131">다른 패턴이 없습니다 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="ffeee-132">합니다 `<EnableAmPmParseAdjustment>` 요소가 영향을 주지 않습니다 합니다 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, 및 <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ffeee-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ffeee-133">.NET Core 및.NET 네이티브에서는 조정 된 AM/PM 구문 분석 규칙은 기본적으로 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="ffeee-134">구문 분석 조정 규칙을 사용 하지 않는 문자열의 첫 번째 숫자는 12 시간제 시계 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="ffeee-135">날짜 및 시간 구문 분석 메서드에서 반환 된 현재 날짜 및 날짜 문자열에서 추출 된 날의 시간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="ffeee-136">구문 분석 조정 규칙을 사용 하는 경우 메서드를 구문 분석 일 및 월 현재 연도에 속하는 것으로 해석 하 고 12 시간제 시계 시간으로 시간을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="ffeee-137">다음 표에서 차이 보여 줍니다.는 <xref:System.DateTime> 경우이 값을 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드 문자열을 구문 분석 하는 "" 4 월 10 6 AM "와 `<EnableAmPmParseAdjustment>` 요소의 `enabled` 속성이"0"또는"1"로 설정.</span><span class="sxs-lookup"><span data-stu-id="ffeee-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="ffeee-138">오늘 날짜가 2017 년 1 월 5 일 이며 지정된 된 문화권의 "G" 서식 문자열을 사용 하 여 형식이 처럼 날짜를 표시 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeee-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="ffeee-139">문화권 이름</span><span class="sxs-lookup"><span data-stu-id="ffeee-139">Culture name</span></span>|<span data-ttu-id="ffeee-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="ffeee-140">enabled="0"</span></span>|<span data-ttu-id="ffeee-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="ffeee-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="ffeee-142">en-US</span><span class="sxs-lookup"><span data-stu-id="ffeee-142">en-US</span></span>|<span data-ttu-id="ffeee-143">2017 년 1 월 5 오전 4 시</span><span class="sxs-lookup"><span data-stu-id="ffeee-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="ffeee-144">2017 년 4 월 10 6시: 00 AM</span><span class="sxs-lookup"><span data-stu-id="ffeee-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="ffeee-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="ffeee-145">en-GB</span></span>|<span data-ttu-id="ffeee-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ffeee-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="ffeee-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ffeee-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffeee-148">참고자료</span><span class="sxs-lookup"><span data-stu-id="ffeee-148">See also</span></span>

- [<span data-ttu-id="ffeee-149">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="ffeee-150">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="ffeee-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
