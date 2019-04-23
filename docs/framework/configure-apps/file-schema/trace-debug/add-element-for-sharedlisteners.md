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
ms.openlocfilehash: e7934ed5e71005cfd28271298ff6ce1eb8829a0d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59095635"
---
# <a name="add-element-for-sharedlisteners"></a>\<추가 > 요소에 대 한 \<sharedListeners >
`sharedListeners` 컬렉션에 수신기를 추가합니다. `sharedListeners` 이 수신기의 컬렉션인 모든 [ \<소스 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [ \<추적 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md) 참조할 수 있습니다.  기본적으로 수신기에는 `sharedListeners` 컬렉션에 있지 않은지를 `Listeners` 컬렉션입니다. 이름으로 추가 해야 합니다 [ \<소스 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md) 또는 [ \<추적 >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)합니다. 수신기에서 가져올 수 없는 `sharedListeners` 런타임 시 코드의 컬렉션입니다.  
  
 \<configuration>  
&nbsp;&nbsp;\<system.diagnostics>  
&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > 요소  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 공유 수신기를 추가 하는 데 사용 되는 수신기의 이름을 지정는 `Listeners` 컬렉션입니다.|  
|`type`|필수 특성입니다.<br /><br /> 수신기의 형식을 지정합니다. 에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
|`traceOutputOptions`|선택적 특성입니다.<br/><br/>하나 이상의의 문자열 표현을 <xref:System.Diagnostics.TraceOptions> 추적 출력에 쓸 데이터를 나타내는 열거형 멤버입니다. 여러 항목은 쉼표로 구분 됩니다. 기본값은 "None"입니다.|

### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 소스 또는 추적 요소가 참조할 수 있는 수신기의 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  
 .NET Framework와 함께 제공 되는 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener> 클래스입니다. 에 대 한 값을 `name` 특성 공유 수신기를 추가 하는 데 사용 됩니다는 `Listeners` 추적 또는 추적 소스에 대 한 컬렉션입니다. 에 대 한 값을 `initializeData` 특성 만든 수신기의 형식에 따라 달라 집니다. 모든 추적 수신기에 지정 해야 `initializeData`합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `initializeData` 특성인 컴파일러 "'initializeData' 특성이 선언 되지 않았습니다." 경고를 발생할 수 있습니다 이 경고는 추상 기본 클래스에 대 한 구성 설정이 검증 되었으며 때문에 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않습니다는 `initializeData` 특성입니다. 일반적으로 매개 변수를 사용 하는 생성자가 하는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.  
  
 다음 표는.NET Framework에 포함 된 추적 수신기를 보여 주고 값을 설명 합니다 해당 `initializeData` 특성입니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|합니다 `useErrorStream` 에 대 한 값을 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.  설정 된 `initializeData` 특성을 "`true`"쓸 추적 및 디버그 출력을 표준 오류 스트림에;로 설정"`false`" 표준 출력 스트림에 쓸입니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|파일의 이름을는 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|파일의 이름을는 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|파일의 이름을는 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.|  
  
## <a name="configuration-file"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 `<add>` 요소를 추가 하는 <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 에 `sharedListeners` 컬렉션입니다.   `textListener` 이름으로 추가 되는 `Listeners` 추적 소스에 대 한 컬렉션 `TraceSourceApp`합니다. `textListener` 수신기 파일 myListener.log에 추적 출력을 씁니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
