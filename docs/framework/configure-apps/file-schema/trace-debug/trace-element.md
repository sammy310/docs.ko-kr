---
title: <trace> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 7d8a989219d84e8604e767456c84c0092bc73b22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153168"
---
# <a name="trace-element"></a>\<추적> 요소
추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<추적>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|`autoflush`|선택적 특성입니다.<br /><br /> 추적 리스너가 모든 쓰기 작업 후에 출력 버퍼를 자동으로 플러시할지 여부를 지정합니다.|  
|`indentsize`|선택적 특성입니다.<br /><br /> 들여쓰기할 공백 수를 지정합니다.|  
|`useGlobalLock`|선택적 특성입니다.<br /><br /> 전역 잠금을 사용해야 하는지 여부를 나타냅니다.|  
  
## <a name="autoflush-attribute"></a>자동 플러시 특성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|출력 버퍼를 자동으로 플러시하지 않습니다. 이것이 기본값입니다.|  
|`true`|출력 버퍼를 자동으로 플러시합니다.|  
  
## <a name="usegloballock-attribute"></a>use글로벌록 속성  
  
|값|Description|  
|-----------|-----------------|  
|`false`|수신기가 스레드에 안전한 경우 전역 잠금을 사용하지 않습니다. 그렇지 않으면 전역 잠금을 사용합니다.|  
|`true`|수신기가 스레드에 안전한지 여부에 관계없이 전역 잠금을 사용합니다. 이것이 기본값입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<청취자>](listeners-element-for-trace.md)|메시지를 수집, 저장 및 라우팅하는 수신기를 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 사용하여 `<trace>` 컬렉션에 리스터를 `MyListener` 추가하는 `Listeners` 방법을 보여 주며 있습니다. `MyListener`이라는 이름의 `MyListener.log` 파일을 만들고 출력을 파일에 씁니다. 특성은 `useGlobalLock` `false`로 설정되어 추적 수신기가 스레드에서 안전한 경우 전역 잠금을 사용하지 않습니다. 특성은 `autoflush` `true`로 설정되어 추적 수신기가 <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> 메서드가 호출되는지 여부에 관계없이 파일에 기록됩니다. 특성은 `indentsize` 0(0)으로 설정되어 메서드가 호출될 때 수신기가 0 공백을 <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> 들여쓰기합니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [추적 및 디버그 설정 스키마](index.md)
