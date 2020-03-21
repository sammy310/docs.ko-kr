---
title: <시스템.진단> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153209"
---
# <a name="systemdiagnostics-element"></a>\<시스템.진단> 요소
메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.  
  
[**\<구성>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.진단>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<어설션>](assert-element.md)|<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.|  
|[\<성능 카운터>](performancecounters-element.md)|성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.|  
|[\<공유청취자>](sharedlisteners-element.md)|소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다. 공유 리스너로 식별된 수신기는 원본 또는 이름으로 추적에 추가할 수 있습니다.|  
|[\<소스>](sources-element.md)|추적 메시지를 시작하는 추적 소스를 지정합니다.|  
|[\<>스위치](switches-element.md)|추적 스위치와 추적 스위치가 설정된 수준을 포함합니다.|  
|[\<추적>](trace-element.md)|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 ** \<system.diagnostics>** 요소 내에 추적 스위치와 추적 수신기를 포함 하는 방법을 보여 주입니다. `General` 추적 스위치가 <xref:System.Diagnostics.TraceLevel> 수준으로 설정됩니다. 추적 수신기는 `myListener` 라는 `MyListener.log` 파일을 만들고 파일에 출력을 씁니다.  
  
> [!NOTE]
> .NET Framework 버전 2.0에서 텍스트를 사용하여 스위치의 값을 지정할 수 있습니다. `true` 예를 들어 에 <xref:System.Diagnostics.BooleanSwitch> 대해 지정하거나 `Error` <xref:System.Diagnostics.TraceSwitch>에 대해 와 같은 열거형 값을 나타내는 텍스트를 사용할 수 있습니다. 선은 `<add name="myTraceSwitch" value="Error" />` `<add name="myTraceSwitch" value="1" />`와 같습니다.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [추적 및 디버그 설정 스키마](index.md)
