---
title: <add>에 <listeners> 대 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153674"
---
# <a name="add-element-for-listeners-for-trace"></a>\<추적> \<대한> \<청취자에 대한> 요소 추가
리스너 컬렉션에 수신기를 **추가합니다.**  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<추적>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<청취자>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>추가**

## <a name="syntax"></a>구문  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|**종류**|필수 특성입니다.<br /><br /> 수신기의 유형을 지정합니다. [정규화된 형식 이름 지정에](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)지정된 요구 사항을 충족하는 문자열을 사용해야 합니다.|  
|**초기화데이터**|선택적 특성입니다.<br /><br /> 문자열은 지정된 클래스의 생성자에게 전달되었습니다.|  
|**(이름)**|선택적 특성입니다.<br /><br /> 수신기의 이름을 지정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<필터>](filter-element-for-add-for-listeners-for-trace.md)|추적에 대한 컬렉션의 `Listeners` 수신기에 필터를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`listeners`|메시지를 수집, 저장 및 라우팅하는 수신기를 지정합니다. 리스너들은 추적 출력을 적절한 대상으로 지시합니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
  
## <a name="remarks"></a>설명  
 및 <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> 클래스는 동일한 리스너 컬렉션을 **공유합니다.** 이러한 클래스 중 하나에서 컬렉션에 수신기 개체를 추가하면 다른 클래스는 동일한 수신기를 사용합니다. 수신기 클래스는 에서 <xref:System.Diagnostics.TraceListener>파생됩니다.  
  
 추적 수신기의 특성을 `name` 지정하지 않으면 추적 <xref:System.Diagnostics.TraceListener.Name%2A> 수신기의 기본값이 빈 문자열("")으로 설정됩니다. 응용 프로그램에 수신기가 하나만 있는 경우 이름을 지정하지 않고 추가하고 이름에 대한 빈 문자열을 지정하여 제거할 수 있습니다. 그러나 응용 프로그램에 두 개 이상의 수신기가 있는 경우 각 추적 수신기에 대해 고유한 이름을 지정해야 <xref:System.Diagnostics.Debug.Listeners%2A> 하며, 이를 통해 컬렉션 내의 <xref:System.Diagnostics.Trace.Listeners%2A> 개별 추적 리스너를 식별하고 관리할 수 있습니다.  
  
> [!NOTE]
> 동일한 형식의 추적 수신기를 두 개 이상 추가하고 이름이 같은 경우 해당 형식과 이름의 추적 `Listeners` 수신기가 하나만 컬렉션에 추가됩니다. 그러나 프로그래밍 방식으로 컬렉션에 동일한 여러 `Listeners` 수신기를 추가할 수 있습니다.  
  
 **initializeData** 특성의 값은 만드는 수신기의 유형에 따라 다릅니다. 모든 추적 리스너가 **initializeData**를 지정해야 하는 것은 아닙니다.  
  
> [!NOTE]
> 특성을 `initializeData` 사용하면 컴파일러 경고 "initializeData" 특성이 선언되지 않을 수 있습니다. 이 경고는 구성 설정이 특성을 인식하지 <xref:System.Diagnostics.TraceListener>못하는 추상 기본 `initializeData` 클래스에 대해 유효성을 검사하기 때문에 발생합니다. 일반적으로 매개 변수를 취하는 생성자가 있는 추적 수신기 구현에 대해 이 경고를 무시할 수 있습니다.  
  
 다음 표에서는 .NET Framework에 포함된 추적 리스너와 **initializeData** 특성의 값을 설명합니다.  
  
|추적 리스너 클래스|initializeData 특성 값|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|생성자의 `useErrorStream` 값입니다. <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>  추적 `initializeData` 및 디버그 출력을 작성하려면 " <xref:System.Console.Error%2A?displayProperty=nameWithType>특성을 "로`true`설정합니다. "`false`" 에 <xref:System.Console.Out%2A?displayProperty=nameWithType>쓸 수 있습니다.|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.DelimitedListTraceListener>가 쓸 파일 이름입니다.|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|기존 이벤트 로그 원본의 이름입니다.|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.EventSchemaTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.TextWriterTraceListener> 기록하는 파일의 이름입니다.|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<xref:System.Diagnostics.XmlWriterTraceListener> 기록하는 파일의 이름입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는>** \<추가** 요소를 사용하여 리스너와 `MyListener` `MyEventListener` **리스너** 컬렉션을 추가하는 방법을 보여 주어집니다. `MyListener`이라는 `MyListener.log` 파일을 만들고 출력을 파일에 씁니다. `MyEventListener`이벤트 로그에 항목을 만듭니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [추적 및 디버그 설정 스키마](index.md)
- [추적 수신기](../../../debug-trace-profile/trace-listeners.md)
