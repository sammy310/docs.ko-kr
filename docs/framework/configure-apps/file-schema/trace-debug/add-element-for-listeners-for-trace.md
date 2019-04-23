---
title: <add> 요소에 대 한 <listeners> 에 대 한 <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: ba0ffc4f95b9af7fcd319068501ce0bb9714c2ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089584"
---
# <a name="add-element-for-listeners-for-trace"></a>\<추가 > 요소에 대 한 \<수신기 >에 대 한 \<추적 >
수신기를 추가 합니다 **수신기** 컬렉션입니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add name="name"   
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**type**|필수 특성입니다.<br /><br /> 수신기의 형식을 지정합니다. 에 지정 된 요구 사항을 충족 하는 문자열을 사용 해야 합니다 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
|**name**|선택적 특성입니다.<br /><br /> 수신기의 이름을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|수신기에 필터를 추가 합니다 `Listeners` 추적에 대 한 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|저장소를 수집 하는 수신기를 지정 하 고 메시지를 라우팅합니다. 수신기는 추적 출력을 적절 한 대상입니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 합니다 <xref:System.Diagnostics.Debug> 하 고 <xref:System.Diagnostics.Trace> 클래스에 동일한 공유 **수신기** 컬렉션입니다. 이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가 하는 경우 다른 클래스는 같은 수신기를 사용 합니다. 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener>합니다.  
  
 지정 하지 않는 경우는 `name` 추적 수신기의 특성을 <xref:System.Diagnostics.TraceListener.Name%2A> 의 추적 수신기 기본값은 빈 문자열 (""). 응용 프로그램에 수신기 하나만 있으면에 이름을 지정 하지 않고 추가 하 고 이름에 대 한 빈 문자열을 지정 하 여 제거할 수 있습니다. 그러나 응용 프로그램에 둘 이상의 수신기를 식별 하 고 내 개별 추적 수신기를 관리할 수 있게 하는 각 추적 수신기에 대 한 고유한 이름을 지정 해야 합니다 <xref:System.Diagnostics.Debug.Listeners%2A> 고 <xref:System.Diagnostics.Trace.Listeners%2A> 컬렉션입니다.  
  
> [!NOTE]
>  하나의 추적 수신기가 해당 형식의 결과 같은 동일한 유형의 추적 수신기를 여러 개 추가 이름과 이름에 추가 되는 `Listeners` 컬렉션입니다. 그러나 동일한 여러 수신기를 프로그래밍 방식으로 추가할 수는 `Listeners` 컬렉션입니다.  
  
 에 대 한 값을 **initializeData** 특성 만든 수신기의 형식에 따라 달라 집니다. 모든 추적 수신기에 지정 해야 **initializeData**합니다.  
  
> [!NOTE]
>  사용 하는 경우는 `initializeData` 특성인 컴파일러 "'initializeData' 특성이 선언 되지 않았습니다." 경고를 발생할 수 있습니다 이 경고는 추상 기본 클래스에 대 한 구성 설정이 검증 되었으며 때문에 발생 <xref:System.Diagnostics.TraceListener>를 인식 하지 않습니다는 `initializeData` 특성입니다. 일반적으로 매개 변수를 사용 하는 생성자가 하는 추적 수신기 구현에 대 한이 경고를 무시할 수 있습니다.  
  
 다음 표는.NET Framework에 포함 된 추적 수신기를 보여 주고 값을 설명 합니다 자신의 **initializeData** 특성입니다.  
  
|추적 수신기 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|합니다 `useErrorStream` 에 대 한 값을 <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> 생성자입니다.  설정 된 `initializeData` 특성을 "`true`" 추적 및 디버그를 쓸 출력을 <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`"에 쓸 <xref:System.Console.Out%2A?displayProperty=nameWithType>합니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 원본의 이름의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|파일의 이름을는 <xref:System.Diagnostics.EventSchemaTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|파일의 이름을는 <xref:System.Diagnostics.TextWriterTraceListener> 를 씁니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|파일의 이름을는 <xref:System.Diagnostics.XmlWriterTraceListener> 를 씁니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다  **\<추가 >** 요소를 추가 하는 수신기 `MyListener` 및 `MyEventListener` 에 **수신기** 컬렉션입니다. `MyListener` 라는 파일을 만들고 `MyListener.log` 출력 파일에 씁니다. `MyEventListener` 이벤트 로그에 항목을 만듭니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
