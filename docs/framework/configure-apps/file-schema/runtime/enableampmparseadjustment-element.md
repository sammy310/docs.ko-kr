---
title: <EnableAmPmParseAdjustment> 요소
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222512"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment > 요소
날짜 및 시간 구문 분석 메서드에 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 조정 된 규칙 집합을 사용할지 여부를 결정 합니다.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment>  
  
## <a name="syntax"></a>구문  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석 조정 된 규칙 집합을 사용할지 여부를 지정 합니다.|  
  
### <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|0|날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정된 규칙을 사용 하지 마세요.|  
|1|날짜 및 시간 구문 분석 메서드는 일, 월, 시간 및 AM/PM 지정자를 포함 하는 날짜 문자열을 구문 분석에 대 한 조정 된 규칙을 사용 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `<EnableAmPmParseAdjustment>` 요소는 다음 방법 숫자 일 및 월을 시간 하 고 (예: "4 월 10 6 AM")는 AM/PM 지정자 뒤에 있는 날짜 문자열의 구문을 분석 하는 방법을 제어 합니다.  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 다른 패턴이 없습니다 영향을 받습니다.  
  
 합니다 `<EnableAmPmParseAdjustment>` 요소가 영향을 주지 않습니다 합니다 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, 및 <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> 메서드.  
  
> [!IMPORTANT]
>  .NET Core 및.NET 네이티브에서는 조정 된 AM/PM 구문 분석 규칙은 기본적으로 활성화 됩니다.  
  
 구문 분석 조정 규칙을 사용 하지 않는 문자열의 첫 번째 숫자는 12 시간제 시계 시간으로 해석 되 고 AM/PM 지정자를 제외 하 고 문자열의 나머지는 무시 됩니다. 날짜 및 시간 구문 분석 메서드에서 반환 된 현재 날짜 및 날짜 문자열에서 추출 된 날의 시간으로 구성 됩니다.  
  
 구문 분석 조정 규칙을 사용 하는 경우 메서드를 구문 분석 일 및 월 현재 연도에 속하는 것으로 해석 하 고 12 시간제 시계 시간으로 시간을 해석 합니다.  
  
 다음 표에서 차이 보여 줍니다.는 <xref:System.DateTime> 경우이 값을 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 메서드 문자열을 구문 분석 하는 "" 4 월 10 6 AM "와 `<EnableAmPmParseAdjustment>` 요소의 `enabled` 속성이"0"또는"1"로 설정. 오늘 날짜가 2017 년 1 월 5 일 이며 지정된 된 문화권의 "G" 서식 문자열을 사용 하 여 형식이 처럼 날짜를 표시 가정 합니다.  
  
|문화권 이름|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|2017 년 1 월 5 오전 4 시|2017 년 4 월 10 6시: 00 AM|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>참고자료

- [\<런타임 > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [\<configuration> 요소](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
