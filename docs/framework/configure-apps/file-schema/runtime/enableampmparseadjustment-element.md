---
title: <EnableAmPmParseAdjustment> 요소
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 8920e51fcaaca5cb78b80a99ea321163c9b5240f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117363"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="5798a-102">\<EnableAmPmParseAdjustment> 요소</span><span class="sxs-lookup"><span data-stu-id="5798a-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="5798a-103">날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="5798a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5798a-104">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5798a-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5798a-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5798a-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5798a-107">특성</span><span class="sxs-lookup"><span data-stu-id="5798a-107">Attributes</span></span>  
  
|<span data-ttu-id="5798a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5798a-108">Attribute</span></span>|<span data-ttu-id="5798a-109">Description</span><span class="sxs-lookup"><span data-stu-id="5798a-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5798a-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="5798a-111">날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석할 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-111">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="5798a-112">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="5798a-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="5798a-113">값</span><span class="sxs-lookup"><span data-stu-id="5798a-113">Value</span></span>|<span data-ttu-id="5798a-114">Description</span><span class="sxs-lookup"><span data-stu-id="5798a-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5798a-115">0</span><span class="sxs-lookup"><span data-stu-id="5798a-115">0</span></span>|<span data-ttu-id="5798a-116">날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하는 데 조정 된 규칙을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-116">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="5798a-117">1</span><span class="sxs-lookup"><span data-stu-id="5798a-117">1</span></span>|<span data-ttu-id="5798a-118">날짜 및 시간 구문 분석 메서드는 날짜, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하기 위해 조정 된 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-118">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5798a-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5798a-119">Child Elements</span></span>  
 <span data-ttu-id="5798a-120">없음</span><span class="sxs-lookup"><span data-stu-id="5798a-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5798a-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5798a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5798a-122">요소</span><span class="sxs-lookup"><span data-stu-id="5798a-122">Element</span></span>|<span data-ttu-id="5798a-123">Description</span><span class="sxs-lookup"><span data-stu-id="5798a-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5798a-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5798a-125">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5798a-126">설명</span><span class="sxs-lookup"><span data-stu-id="5798a-126">Remarks</span></span>  
 <span data-ttu-id="5798a-127">`<EnableAmPmParseAdjustment>`요소는 다음 메서드가 숫자 일과 월을 포함 하는 날짜 문자열과 시간 및 AM/PM 지정자 (예: "4/10 6 AM")를 포함 하는 날짜 문자열을 구문 분석 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-127">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="5798a-128">다른 패턴에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-128">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="5798a-129">`<EnableAmPmParseAdjustment>`요소는 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> ,, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> 및 메서드에 영향을 주지 않습니다 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5798a-129">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="5798a-130">.NET Core 및 .NET 네이티브에서 조정 된 AM/PM 구문 분석 규칙은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-130">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="5798a-131">구문 분석 조정 규칙을 사용 하지 않는 경우 문자열의 첫 번째 숫자는 12 시간제의 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-131">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="5798a-132">구문 분석 메서드에서 반환 되는 날짜 및 시간은 현재 날짜와 날짜 문자열에서 추출 된 날짜의 시간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-132">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="5798a-133">구문 분석 조정 규칙을 사용 하는 경우 구문 분석 메서드는 현재 연도에 속하는 요일과 월을 해석 하 고 12 시간 형식의 시간으로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-133">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="5798a-134">다음 표에서는 <xref:System.DateTime> <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드를 사용 하 여 `<EnableAmPmParseAdjustment>` 요소 `enabled` 속성이 "0" 또는 "1"로 설정 된 "" 4/10 6 AM "문자열을 구문 분석할 때 값의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-134">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="5798a-135">오늘 날짜가 2017 년 1 월 5 일 이라고 가정 하 고 지정 된 문화권의 "G" 형식 문자열을 사용 하 여 서식이 지정 된 것 처럼 날짜를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5798a-135">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="5798a-136">문화권 이름</span><span class="sxs-lookup"><span data-stu-id="5798a-136">Culture name</span></span>|<span data-ttu-id="5798a-137">enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="5798a-137">enabled="0"</span></span>|<span data-ttu-id="5798a-138">enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="5798a-138">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="5798a-139">en-US</span><span class="sxs-lookup"><span data-stu-id="5798a-139">en-US</span></span>|<span data-ttu-id="5798a-140">오전 1/5/2017 4:00:00</span><span class="sxs-lookup"><span data-stu-id="5798a-140">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="5798a-141">오전 4/10/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="5798a-141">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="5798a-142">en-GB</span><span class="sxs-lookup"><span data-stu-id="5798a-142">en-GB</span></span>|<span data-ttu-id="5798a-143">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="5798a-143">5/1/2017 6:00:00</span></span>|<span data-ttu-id="5798a-144">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="5798a-144">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5798a-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5798a-145">See also</span></span>

- [<span data-ttu-id="5798a-146">\<runtime>요소인</span><span class="sxs-lookup"><span data-stu-id="5798a-146">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="5798a-147">\<configuration>요소인</span><span class="sxs-lookup"><span data-stu-id="5798a-147">\<configuration> Element</span></span>](../configuration-element.md)
