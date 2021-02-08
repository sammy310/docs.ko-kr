---
description: '다음에 대 한 자세한 정보: <EnableAmPmParseAdjustment> 요소'
title: <EnableAmPmParseAdjustment> 요소
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 86fd04ab536f44f0cffdb5a37f4718fc03698485
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787060"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="53806-103">\<EnableAmPmParseAdjustment> 요소</span><span class="sxs-lookup"><span data-stu-id="53806-103">\<EnableAmPmParseAdjustment> Element</span></span>

<span data-ttu-id="53806-104">날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-104">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="53806-105">구문</span><span class="sxs-lookup"><span data-stu-id="53806-105">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53806-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="53806-106">Attributes and Elements</span></span>  

 <span data-ttu-id="53806-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53806-108">특성</span><span class="sxs-lookup"><span data-stu-id="53806-108">Attributes</span></span>  
  
|<span data-ttu-id="53806-109">attribute</span><span class="sxs-lookup"><span data-stu-id="53806-109">Attribute</span></span>|<span data-ttu-id="53806-110">설명</span><span class="sxs-lookup"><span data-stu-id="53806-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="53806-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="53806-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="53806-112">날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석할 지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-112">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="53806-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="53806-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="53806-114">값</span><span class="sxs-lookup"><span data-stu-id="53806-114">Value</span></span>|<span data-ttu-id="53806-115">설명</span><span class="sxs-lookup"><span data-stu-id="53806-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="53806-116">0</span><span class="sxs-lookup"><span data-stu-id="53806-116">0</span></span>|<span data-ttu-id="53806-117">날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하는 데 조정 된 규칙을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53806-117">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="53806-118">1</span><span class="sxs-lookup"><span data-stu-id="53806-118">1</span></span>|<span data-ttu-id="53806-119">날짜 및 시간 구문 분석 메서드는 날짜, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하기 위해 조정 된 규칙을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-119">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53806-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="53806-120">Child Elements</span></span>  

 <span data-ttu-id="53806-121">없음</span><span class="sxs-lookup"><span data-stu-id="53806-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53806-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="53806-122">Parent Elements</span></span>  
  
|<span data-ttu-id="53806-123">요소</span><span class="sxs-lookup"><span data-stu-id="53806-123">Element</span></span>|<span data-ttu-id="53806-124">설명</span><span class="sxs-lookup"><span data-stu-id="53806-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="53806-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="53806-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="53806-126">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53806-127">설명</span><span class="sxs-lookup"><span data-stu-id="53806-127">Remarks</span></span>  

 <span data-ttu-id="53806-128">`<EnableAmPmParseAdjustment>`요소는 다음 메서드가 숫자 일과 월을 포함 하는 날짜 문자열과 시간 및 AM/PM 지정자 (예: "4/10 6 AM")를 포함 하는 날짜 문자열을 구문 분석 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-128">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="53806-129">다른 패턴에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="53806-129">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="53806-130">`<EnableAmPmParseAdjustment>`요소는 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> ,, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> 및 메서드에 영향을 주지 않습니다 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="53806-130">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="53806-131">.NET Core 및 .NET 네이티브에서 조정 된 AM/PM 구문 분석 규칙은 기본적으로 사용 하도록 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53806-131">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="53806-132">구문 분석 조정 규칙을 사용 하지 않는 경우 문자열의 첫 번째 숫자는 12 시간제의 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53806-132">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="53806-133">구문 분석 메서드에서 반환 되는 날짜 및 시간은 현재 날짜와 날짜 문자열에서 추출 된 날짜의 시간으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53806-133">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="53806-134">구문 분석 조정 규칙을 사용 하는 경우 구문 분석 메서드는 현재 연도에 속하는 요일과 월을 해석 하 고 12 시간 형식의 시간으로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-134">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="53806-135">다음 표에서는 <xref:System.DateTime> <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드를 사용 하 여 `<EnableAmPmParseAdjustment>` 요소 `enabled` 속성이 "0" 또는 "1"로 설정 된 "" 4/10 6 AM "문자열을 구문 분석할 때 값의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53806-135">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="53806-136">오늘 날짜가 2017 년 1 월 5 일 이라고 가정 하 고 지정 된 문화권의 "G" 형식 문자열을 사용 하 여 서식이 지정 된 것 처럼 날짜를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="53806-136">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="53806-137">문화권 이름</span><span class="sxs-lookup"><span data-stu-id="53806-137">Culture name</span></span>|<span data-ttu-id="53806-138">enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="53806-138">enabled="0"</span></span>|<span data-ttu-id="53806-139">enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="53806-139">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="53806-140">ko-KR</span><span class="sxs-lookup"><span data-stu-id="53806-140">en-US</span></span>|<span data-ttu-id="53806-141">오전 1/5/2017 4:00:00</span><span class="sxs-lookup"><span data-stu-id="53806-141">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="53806-142">오전 4/10/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="53806-142">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="53806-143">en-GB</span><span class="sxs-lookup"><span data-stu-id="53806-143">en-GB</span></span>|<span data-ttu-id="53806-144">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="53806-144">5/1/2017 6:00:00</span></span>|<span data-ttu-id="53806-145">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="53806-145">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53806-146">참조</span><span class="sxs-lookup"><span data-stu-id="53806-146">See also</span></span>

- [<span data-ttu-id="53806-147">\<runtime> 요소</span><span class="sxs-lookup"><span data-stu-id="53806-147">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="53806-148">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="53806-148">\<configuration> Element</span></span>](../configuration-element.md)
