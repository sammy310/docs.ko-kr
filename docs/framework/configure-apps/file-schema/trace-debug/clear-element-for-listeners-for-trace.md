---
title: <clear>의에 <listeners> 대 한 요소<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 9816ba0f8e4ddd4c38537eb4e014a4240ff20407
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927178"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<추적\<> > 수신기 \<에 대 한 > 요소 지우기
추적의 `Listeners` 컬렉션을 지웁니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
\<clear>  
  
## <a name="syntax"></a>구문  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
|`listeners`|메시지를 수집, 저장 및 라우팅하는 수신기를 포함 합니다. 수신기는 추적 출력을 적절 한 대상으로 보냅니다.|  
  
## <a name="remarks"></a>설명  
 요소 `<clear>` 는 추적을 위해 `Listeners` 컬렉션에서 모든 수신기를 제거 합니다. 요소를 사용 하기 `<clear>` 전에 `<add>` 요소를 사용 하 여 컬렉션에 다른 활성 수신기가 없음을 확신할 수 있습니다.  
  
 `Listeners` <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 속성(`System.Diagnostics.Trace.Listeners.Clear()`)에서 메서드를 호출 하 여 프로그래밍 방식으로 컬렉션을 지울 수 있습니다. <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType>  
  
 이 요소는 컴퓨터 구성 파일 (machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
> [!NOTE]
> 요소 `<clear>` 는 <xref:System.Diagnostics.DefaultTraceListener> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> 컬렉션에서을제거<xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>하 여,, 및<xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드의 동작을 변경 합니다. `Listeners` `Assert` 또는`Fail` 메서드를 호출 하면 일반적으로 메시지 상자가 표시 됩니다. 그러나 <xref:System.Diagnostics.DefaultTraceListener> 가 `Listeners` 컬렉션에 없으면 메시지 상자가 표시 되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `<add>` 요소를 사용 하 여 `<clear>` 추적을 위한 `Listeners` 컬렉션에 수신기 `console` 를 추가 하기 전에 요소를 사용 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [추적 및 디버그 설정 스키마](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [추적 수신기](../../../debug-trace-profile/trace-listeners.md)
