---
description: '에 대 한 자세한 정보: <add> 요소 <sharedListeners>'
title: <sharedListeners>에 대한 <add> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: df3348fa0cbb357b2ceeb5d9db940a1ae3ae102c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726080"
---
# <a name="add-element-for-sharedlisteners"></a>\<sharedListeners>에 대한 \<add> 요소

`sharedListeners` 컬렉션에 수신기를 추가합니다. `sharedListeners` 는 또는에서 참조할 수 있는 수신기의 컬렉션입니다 [\<source>](source-element.md) [\<trace>](trace-element.md) .  기본적으로 컬렉션의 수신기 `sharedListeners` 는 컬렉션에 배치 되지 않습니다 `Listeners` . 이름을 기준으로 또는에 추가 해야 합니다 [\<source>](source-element.md) [\<trace>](trace-element.md) . 런타임에 코드에서 컬렉션의 수신기를 가져올 수는 없습니다 `sharedListeners` .  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

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
  
|attribute|설명|  
|---------------|-----------------|  
|`name`|필수 특성입니다.<br /><br /> 컬렉션에 공유 수신기를 추가 하는 데 사용 되는 수신기의 이름을 지정 합니다 `Listeners` .|  
|`type`|필수 특성입니다.<br /><br /> 수신기의 유형을 지정 합니다. 정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다.|  
|`initializeData`|선택적 특성입니다.<br /><br /> 지정 된 클래스의 생성자에 전달 된 문자열입니다.|  
|`traceOutputOptions`|선택적 특성입니다.<br/><br/><xref:System.Diagnostics.TraceOptions>추적 출력에 쓸 데이터를 나타내는 하나 이상의 열거형 멤버에 대 한 문자열 표현입니다. 여러 항목은 쉼표로 구분 됩니다. 기본값은 "None"입니다.|

### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 소스 또는 추적 요소가 참조할 수 있는 수신기의 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  

 .NET Framework와 함께 제공 되는 수신기 클래스는 클래스에서 파생 <xref:System.Diagnostics.TraceListener> 됩니다. 특성 값은 `name` `Listeners` 추적 또는 추적 소스에 대 한 컬렉션에 공유 수신기를 추가 하는 데 사용 됩니다. 특성의 값은 `initializeData` 만드는 수신기의 형식에 따라 달라 집니다. 모든 추적 수신기에서을 지정 해야 하는 것은 아닙니다 `initializeData` .  
  
> [!NOTE]
> 특성을 사용 하는 경우 `initializeData` 컴파일러 경고 "' initializeData ' 특성이 선언 되지 않았습니다." 라는 메시지가 표시 될 수 있습니다. 이 경고는 특성을 인식 하지 않는 추상 기본 클래스에 대해 구성 설정의 유효성을 검사 하기 때문에 발생 합니다 <xref:System.Diagnostics.TraceListener> `initializeData` . 일반적으로 매개 변수를 사용 하는 생성자가 있는 추적 수신기 구현에 대해서는이 경고를 무시할 수 있습니다.  
  
 다음 표에서는 .NET Framework에 포함 된 추적 수신기를 보여 주고 해당 특성의 값을 설명 합니다 `initializeData` .  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|`useErrorStream`생성자에 대 한 값 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 입니다.  `initializeData` `true` 표준 오류 스트림에 추적 및 디버그 출력을 쓰려면 특성을 ""로 설정 하 고, `false` 표준 출력 스트림에 쓰려면 ""로 설정 합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 소스의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.EventSchemaTraceListener> .|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.TextWriterTraceListener> .|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|에서 쓰는 파일의 이름입니다 <xref:System.Diagnostics.XmlWriterTraceListener> .|  
  
## <a name="configuration-file"></a>구성 파일  

 이 요소는 컴퓨터 구성 파일 (Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  

 다음 예제에서는 요소를 사용 하 여를 `<add>` <xref:System.Diagnostics.TextWriterTraceListener> `textListener` 컬렉션에 추가 하는 방법을 보여 줍니다 `sharedListeners` .   `textListener` 는 `Listeners` 추적 소스에 대 한 컬렉션에 이름으로 추가 됩니다 `TraceSourceApp` . `textListener`수신기는 추적 출력을 myListener .log 파일에 기록 합니다.  
  
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
