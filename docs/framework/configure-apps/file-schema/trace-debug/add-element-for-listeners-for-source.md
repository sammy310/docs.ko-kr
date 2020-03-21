---
title: <add>에 <listeners> 대 한 요소<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153687"
---
# <a name="add-element-for-listeners-for-source"></a>\<소스> \<>> 요소를 추가합니다. \<
추적 소스의 `Listeners` 컬렉션에 수신기를 추가합니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<소스>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**

## <a name="syntax"></a>구문  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`type`|`sharedListeners` 컬렉션에서 리스너를 참조하지 않는 한 필수 특성은 이름으로만 참조하면 [됩니다(예제](#example)참조).<br /><br /> 수신기의 유형을 지정합니다. [정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 문자열은 지정된 클래스의 생성자에게 전달되었습니다. 클래스에 문자열을 받는 생성자가 없는 경우 A가 <xref:System.Configuration.ConfigurationException> throw됩니다.|  
|`name`|선택적 특성입니다.<br /><br /> 수신기의 이름을 지정합니다.|  
|`traceOutputOptions`|선택적 특성입니다.<br /><br /> 추적 수신기에 <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> 대한 속성 값을 지정합니다.|  
|[사용자 지정 속성]|선택적 특성입니다.<br /><br /> 해당 수신기에 대 한 메서드에서 식별 하는 <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> 수신기 별 특성에 대 한 값을 지정 합니다. <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>는 클래스에 고유한 추가 특성의 <xref:System.Diagnostics.DelimitedListTraceListener> 예입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<필터>](filter-element-for-add-for-listeners-for-source.md)|추적 소스의 `Listeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sources`|추적 메시지를 시작하는 추적 소스가 포함되어 있습니다.|  
|`source`|추적 메시지를 시작하는 추적 소스를 지정합니다.|  
|`listeners`|메시지를 수집, 저장 및 라우팅하는 리스너를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다.  
  
 추적 수신기의 특성을 `name` 지정하지 않으면 추적 <xref:System.Diagnostics.TraceListener.Name%2A> 수신기의 속성이 빈 문자열("")으로 기본설정됩니다. 응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정하지 않고 추가할 수 있으며 이름에 대한 빈 문자열을 지정하여 제거할 수 있습니다. 그러나 응용 프로그램에 두 개 이상의 수신기가 있는 경우 각 추적 수신기에 대해 고유한 이름을 지정해야 하므로 <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> 컬렉션에서 개별 추적 리스너를 식별하고 관리할 수 있습니다.  
  
> [!NOTE]
> 동일한 형식의 추적 수신기를 두 개 이상 추가하고 이름이 같은 경우 해당 형식과 이름의 추적 `Listeners` 수신기가 하나만 컬렉션에 추가됩니다. 그러나 프로그래밍 방식으로 컬렉션에 동일한 여러 `Listeners` 수신기를 추가할 수 있습니다.  
  
 특성의 `initializeData` 값은 만드는 수신기의 유형에 따라 다릅니다. 모든 추적 리스너가 `initializeData`을 지정해야 하는 것은 아닙니다.  
  
> [!NOTE]
> 특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다. 이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다. 일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.  
  
 다음 표에서는 .NET Framework에 포함된 추적 수신기를 보여 주며 `initializeData` 해당 특성의 값을 설명합니다.  
  
|추적 리스너 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>  추적 `initializeData` 및 디버그 출력을 표준 오류 스트림에 쓰기 위해 ""`true`특성을 설정합니다. 을`false`"로 설정하여 표준 출력 스트림에 쓰도록 합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.|  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 `<add>` 사용하여 `console` 리스너를 `textListener` 추가하고 추적 `Listeners` 소스에 `TraceSourceApp`대한 컬렉션을 추가하는 방법을 보여 주어집니다. 수신기는 `textListener` myListener.log 파일에 추적 출력을 씁니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [추적 및 디버그 설정 스키마](index.md)
- [추적 수신기](../../../debug-trace-profile/trace-listeners.md)
