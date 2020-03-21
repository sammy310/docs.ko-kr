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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153297"
---
# <a name="source-element"></a>\<소스> 요소
추적 메시지를 시작하는 추적 소스를 지정합니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<소스>**

## <a name="syntax"></a>구문  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`name`|선택적 특성입니다.<br /><br /> 추적 소스의 이름을 지정합니다.|  
|`switchName`|선택적 특성입니다.<br /><br /> 응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정합니다. `<switches>` 요소에서 스위치를 식별하지 않으면 이 값은 스위치의 레벨을 지정합니다.|  
|`switchType`|선택적 특성입니다.<br /><br /> 추적 스위치의 유형을 지정합니다. 있는 경우 형식은 유효한 클래스 이름이어야 하며 빈 문자열일 수 없습니다.|  
|`extraAttribute`|선택적 특성입니다.<br /><br /> 해당 추적 원본에 대 한 메서드에서 식별 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 하는 추적 소스 별 특성에 대 한 값을 지정 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<청취자>](listeners-element-for-source.md)|메시지를 수집, 저장 및 라우팅하는 리스너가 포함됩니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<source>` 요소를 사용하여 추적 소스를 `mySource` 추가하고 명명된 `sourceSwitch`소스 스위치의 수준을 설정하는 방법을 보여 주며 있습니다. 콘솔에 추적 정보를 기록하는 콘솔 추적 수신기가 추가됩니다.  
  
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
