---
title: <sharedListeners>에 대한 <add> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153609"
---
# <a name="add-element-for-sharedlisteners"></a>\<공유리스> \<> 요소 추가
`sharedListeners` 컬렉션에 수신기를 추가합니다. `sharedListeners`은 [ \<>](source-element.md) [ \<추적>](trace-element.md) 참조할 수 있는 수신기 의 모음입니다.  기본적으로 컬렉션의 `sharedListeners` 리스너는 `Listeners` 컬렉션에 배치되지 않습니다. 원본>이름으로 [ \<](source-element.md) [ \< ](trace-element.md)추가하거나>추적해야 합니다. 런타임에 `sharedListeners` 코드에서 컬렉션의 리스너를 얻을 수 없습니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<공유청취자>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**

## <a name="syntax"></a>구문  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 공유 수신기를 `Listeners` 컬렉션에 추가하는 데 사용되는 수신기의 이름을 지정합니다.|  
|`type`|필수 특성입니다.<br /><br /> 수신기의 유형을 지정합니다. [정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 문자열은 지정된 클래스의 생성자에게 전달되었습니다.|  
|`traceOutputOptions`|선택적 특성입니다.<br/><br/>추적 출력에 기록할 <xref:System.Diagnostics.TraceOptions> 데이터를 나타내는 하나 이상의 열거형 멤버의 문자열 표현입니다. 여러 항목은 쉼표로 구분됩니다. 기본값은 "없음"입니다.|

### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<필터>](filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 소스 또는 추적 요소가 참조할 수 있는 리스너 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework와 함께 제공되는 수신기 클래스는 <xref:System.Diagnostics.TraceListener> 클래스에서 파생됩니다. 특성의 `name` 값은 추적 또는 추적 원본에 `Listeners` 대한 컬렉션에 공유 리스터를 추가하는 데 사용됩니다. 특성의 `initializeData` 값은 만드는 수신기의 유형에 따라 다릅니다. 모든 추적 리스너가 `initializeData`을 지정해야 하는 것은 아닙니다.  
  
> [!NOTE]
> 특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다. 이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다. 일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.  
  
 다음 표에서는 .NET Framework에 포함된 추적 수신기를 보여 주며 `initializeData` 해당 특성의 값을 설명합니다.  
  
|추적 리스너 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>  추적 `initializeData` 및 디버그 출력을 표준 오류 스트림에 쓰기 위해 ""`true`특성을 설정합니다. 을`false`"로 설정하여 표준 출력 스트림에 쓰도록 합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.|  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 `<add>` 사용하여 컬렉션에 <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 요소를 `sharedListeners` 추가하는 방법을 보여 주어집니다.   `textListener`추적 소스에 `TraceSourceApp`대한 `Listeners` 이름으로 컬렉션에 추가됩니다. 수신기는 `textListener` myListener.log 파일에 추적 출력을 씁니다.  
  
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
