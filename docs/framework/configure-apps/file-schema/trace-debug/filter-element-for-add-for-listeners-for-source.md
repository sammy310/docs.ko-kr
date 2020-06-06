---
title: <filter>의에 <add> 대 한의 요소 <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153518"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a>\<filter>의에 \<add> 대 한의 요소 \<listeners>\<source>
추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a>구문  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`type`|필수 특성입니다.<br /><br /> 클래스에서 상속 해야 하는 필터의 유형을 지정 합니다 <xref:System.Diagnostics.TraceFilter> . 형식의 네임 스페이스 정규화 된 이름을 사용 하거나, 형식의 속성에 해당 하는 형식의 정규화 된 <xref:System.Type.FullName%2A> 형식 이름을 사용 하거나, 속성에 해당 하는 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다 <xref:System.Type.AssemblyQualifiedName%2A> . 정규화 된 형식 이름에 대 한 자세한 내용은 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)을 참조 하세요.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정 된 필터 클래스의 생성자에 전달 된 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
|`source`|추적 메시지를 시작하는 추적 소스를 지정합니다.|  
|`listeners`|메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다. 수신기는 추적 출력을 적절 한 대상으로 보냅니다.|  
|`add`|추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.|  
  
## <a name="remarks"></a>설명  
 `<filter>`요소는 `<add>` 에 정의 된 수신기의 이름 뿐만 아니라 수신기의 형식을 지정 하는 추적 소스 수신기의 요소에 포함 되어야 합니다 [\<sharedListeners>](sharedlisteners-element.md) . 수신기가에 정의 된 경우 해당 [\<sharedListeners>](sharedlisteners-element.md) 수신기의 필터를 해당 요소에 정의 해야 합니다.  
  
 이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 사용 하 여 `<filter>` `console` 추적 소스에 대 한 컬렉션의 수신기에 필터를 추가 하 `Listeners` `myTraceSource` 고 필터 이벤트 수준을로 지정 `Error` 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [추적 및 디버그 설정 스키마](index.md)
