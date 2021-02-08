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
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment> 요소

날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 하는지 여부를 결정 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 날짜 및 시간 구문 분석 메서드가 조정 된 규칙 집합을 사용 하 여 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석할 지 여부를 지정 합니다.|  
  
### <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|0|날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하는 데 조정 된 규칙을 사용 하지 않습니다.|  
|1|날짜 및 시간 구문 분석 메서드는 날짜, 월, 시간 및 AM/PM 지정자만 포함 하는 날짜 문자열을 구문 분석 하기 위해 조정 된 규칙을 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  

 `<EnableAmPmParseAdjustment>`요소는 다음 메서드가 숫자 일과 월을 포함 하는 날짜 문자열과 시간 및 AM/PM 지정자 (예: "4/10 6 AM")를 포함 하는 날짜 문자열을 구문 분석 하는 방법을 제어 합니다.  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 다른 패턴에는 영향을 주지 않습니다.  
  
 `<EnableAmPmParseAdjustment>`요소는 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> ,, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> 및 메서드에 영향을 주지 않습니다 <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .  
  
> [!IMPORTANT]
> .NET Core 및 .NET 네이티브에서 조정 된 AM/PM 구문 분석 규칙은 기본적으로 사용 하도록 설정 되어 있습니다.  
  
 구문 분석 조정 규칙을 사용 하지 않는 경우 문자열의 첫 번째 숫자는 12 시간제의 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다. 구문 분석 메서드에서 반환 되는 날짜 및 시간은 현재 날짜와 날짜 문자열에서 추출 된 날짜의 시간으로 구성 됩니다.  
  
 구문 분석 조정 규칙을 사용 하는 경우 구문 분석 메서드는 현재 연도에 속하는 요일과 월을 해석 하 고 12 시간 형식의 시간으로 해석 합니다.  
  
 다음 표에서는 <xref:System.DateTime> <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드를 사용 하 여 `<EnableAmPmParseAdjustment>` 요소 `enabled` 속성이 "0" 또는 "1"로 설정 된 "" 4/10 6 AM "문자열을 구문 분석할 때 값의 차이점을 보여 줍니다. 오늘 날짜가 2017 년 1 월 5 일 이라고 가정 하 고 지정 된 문화권의 "G" 형식 문자열을 사용 하 여 서식이 지정 된 것 처럼 날짜를 표시 합니다.  
  
|문화권 이름|enabled = "0"|enabled = "1"|  
|------------------|------------------|------------------|  
|ko-KR|오전 1/5/2017 4:00:00|오전 4/10/2017 6:00:00|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>참조

- [\<runtime> 요소](runtime-element.md)
- [\<configuration> 요소](../configuration-element.md)
