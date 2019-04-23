---
title: <source> 요소
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 8860f5d3ed7ee0c04d1e8afd7614f3f73b470808
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186552"
---
# <a name="source-element"></a>\<소스 > 요소
추적 메시지를 시작하는 추적 소스를 지정합니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<sources>  
\<source>  
  
## <a name="syntax"></a>구문  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|선택적 특성입니다.<br /><br /> 추적 소스의 이름을 지정합니다.|  
|`switchName`|선택적 특성입니다.<br /><br /> 응용 프로그램에서 추적 스위치 인스턴스의 이름을 지정합니다. 스위치에서 식별 되지 않는 경우는 `<switches>` 요소 값에 스위치의 수준을 지정 합니다.|  
|`switchType`|선택적 특성입니다.<br /><br /> 추적 스위치의 형식을 지정합니다. 있는 경우 형식을 유효한 클래스 이름 이어야 합니다 하 고 빈 문자열일 수 없습니다.|  
|`extraAttribute`|선택적 특성입니다.<br /><br /> 로 식별 되는 추적 소스 관련 특성의 값을 지정 합니다 <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> 메서드는 추적 소스에 대 한 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<source>` 추적 소스를 추가할 요소의 `mySource` 명명 된 소스 스위치의 수준을 설정 하 고 `sourceSwitch`입니다. 콘솔 추적 수신기는 추적 정보를 콘솔에 쓰는 추가 됩니다.  
  
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
  
## <a name="see-also"></a>참고자료

- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [추적 스위치](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
