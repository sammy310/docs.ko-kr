---
title: <TimeSpan_LegacyFormatMode> 요소
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38adde3cd51a96f0e15ed5a0c539e088f2d3b480
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701634"
---
# <a name="timespanlegacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > 요소
런타임에서 사용 하 여 작업을 서식 지정에 레거시 동작을 유지할지 여부를 결정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.  
  
 \<configuration>  
\<runtime>  
<TimeSpan_LegacyFormatMode>  
  
## <a name="syntax"></a>구문  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`enabled`|필수 특성입니다.<br /><br /> 런타임에서 사용 하 여 레거시 서식 지정 동작을 사용할지 여부를 지정 <xref:System.TimeSpan?displayProperty=nameWithType> 값입니다.|  
  
## <a name="enabled-attribute"></a>enabled 특성  
  
|값|설명|  
|-----------|-----------------|  
|`false`|런타임이 레거시 서식 지정 동작을 복원 하지 않습니다.|  
|`true`|런타임이 레거시 서식 지정 동작을 복원합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`runtime`|런타임 초기화 옵션에 대한 정보를 포함합니다.|  
  
## <a name="remarks"></a>설명  
 부터 합니다 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]의 <xref:System.TimeSpan?displayProperty=nameWithType> 구현 구조체는 <xref:System.IFormattable> 인터페이스 및 서식 지정 작업 표준 및 사용자 지정 형식 문자열을 사용 하 여 지원 합니다. 구문 분석 메서드는 지원 되지 않는 형식 지정자 또는 서식 문자열을 발견 하면, throw 된 <xref:System.FormatException>합니다.  
  
 이전 버전의.NET Framework에는 <xref:System.TimeSpan> 구조를 구현 하지 않았습니다 <xref:System.IFormattable> 형식 문자열을 지원 하지 않았습니다. 그러나 많은 개발자가 잘못 된 것으로 간주 <xref:System.TimeSpan> 에 사용 및 형식 문자열 집합을 지원 하지 못했습니다 [복합 서식 지정 작업](../../../../../docs/standard/base-types/composite-formatting.md) 와 같은 메서드를 사용 하 여 <xref:System.String.Format%2A?displayProperty=nameWithType>입니다. 일반적으로 형식을 구현 하는 경우 <xref:System.IFormattable> 지원 형식 문자열, 문자열 일반적으로 throw 하는 지원 되지 않는 형식으로 서식 지정 메서드를 호출 하 고는 <xref:System.FormatException>합니다. 그러나 때문 <xref:System.TimeSpan> 를 구현 하지 않았습니다 <xref:System.IFormattable>, 런타임에서 형식 문자열을 무시 하 고 대신 호출는 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 메서드. 즉,는 형식 문자열은 서식 지정 작업에 영향을 주지 않지만, 근무 발생 하지는 <xref:System.FormatException>합니다.  
  
 사용할 수 있는 레거시 코드 복합 서식 지정 메서드 및 잘못 된 형식 문자열을 전달 하 고 해당 코드를 다시 컴파일할 수 없는 경우-합니다 `<TimeSpan_LegacyFormatMode>` 레거시 복원 하는 요소 <xref:System.TimeSpan> 동작 합니다. 설정한 경우는 `enabled` 이 요소의 특성 `true`, 형식 지정 메서드 호출에서 복합 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 대신 <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, 및 <xref:System.FormatException> throw 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.TimeSpan> 개체를 사용 하 여 형식을 지정 하는 <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> 메서드는 지원 되지 않는 표준 형식 문자열을 사용 하 여 합니다.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 예제를 실행 하 여 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] 하거나 이전 버전에서 다음과 같은 출력이 표시:  
  
```  
12:30:45  
```  
  
 이는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력과 다르게 표시됩니다.  
  
```  
Invalid Format  
```  
  
 그러나 다음 구성 파일을 예제 디렉터리에 추가한 다음 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 이상 버전에서 예제를 실행하는 경우 출력은 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]에서 실행할 때 예제가 생성한 출력과 동일합니다.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- [런타임 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [구성 파일 스키마](../../../../../docs/framework/configure-apps/file-schema/index.md)
