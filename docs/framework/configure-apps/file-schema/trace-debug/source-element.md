---
title: <source> 요소
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153297"
---
# <a name="source-element"></a>\<source> 요소
추적 메시지를 시작하는 추적 소스를 지정합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a>구문  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`name`|선택적 특성입니다.<br /><br /> 추적 원본의 이름을 지정 합니다.|  
|`switchName`|선택적 특성입니다.<br /><br /> 응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정 합니다. 스위치가 요소에서 식별 되지 않은 경우이 `<switches>` 값은 스위치의 수준을 지정 합니다.|  
|`switchType`|선택적 특성입니다.<br /><br /> 추적 스위치의 유형을 지정 합니다. 있는 경우 형식은 올바른 클래스 이름 이어야 하며 빈 문자열일 수 없습니다.|  
|`extraAttribute`|선택적 특성입니다.<br /><br /> <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A>해당 추적 소스에 대해 메서드로 식별 되는 추적 소스 관련 특성의 값을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 사용 하 여 `<source>` 추적 소스를 추가 하 `mySource` 고 라는 소스 스위치의 수준을 설정 하는 방법을 보여 줍니다 `sourceSwitch` . 콘솔에 추적 정보를 기록 하는 콘솔 추적 수신기가 추가 됩니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- [추적 및 디버그 설정 스키마](index.md)
- [추적 스위치](../../../debug-trace-profile/trace-switches.md)
