---
title: < System.diagnostics > 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 026805ffb9b89aa55e84cf9a5c4afb8ed63cec09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142716"
---
# <a name="systemdiagnostics-element"></a>\<system.diagnostics> Element
메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.  
  
 \<configuration>  
\<system.diagnostics>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.diagnostics>   
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|<xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> 메서드를 호출할 때 메시지 상자를 표시할지 여부를 지정합니다. 또한 메시지를 작성할 파일의 이름도 지정합니다.|  
|[\<performanceCounters>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|성능 카운터에서 공유하는 전역 메모리의 크기를 지정합니다.|  
|[\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다. 공유 수신기로 식별 하는 수신기 이름으로 추적 소스를 추가할 수 있습니다.|  
|[\<sources>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|추적 메시지를 시작 하는 추적 소스를 지정 합니다.|  
|[\<switches>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|추적 스위치 및 추적 스위치가 설정 되어 있는 수준에 포함 되어 있습니다.|  
|[\<trace>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 추적 스위치 및 내부 추적 수신기를 포함 하는  **\<system.diagnostics >** 요소입니다. 합니다 `General` 추적 스위치가 설정 된는 <xref:System.Diagnostics.TraceLevel> 수준입니다. 추적 수신기 `myListener` 라는 파일을 만들고 `MyListener.log` 출력 파일에 씁니다.  
  
> [!NOTE]
>  .NET Framework 버전 2.0에서는 텍스트를 사용하여 스위치의 값을 지정할 수 있습니다. 예를 들어 지정할 수 있습니다 `true` 에 대 한는 <xref:System.Diagnostics.BooleanSwitch> 와 같은 열거형 값을 나타내는 텍스트를 사용 하거나 `Error` 에 대 한는 <xref:System.Diagnostics.TraceSwitch>합니다. `<add name="myTraceSwitch" value="Error" />` 줄은 `<add name="myTraceSwitch" value="1" />`과 같습니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
