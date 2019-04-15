---
title: <sharedListeners> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 48cb59dfc0871822bfcff5e16d4283008a411479
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190800"
---
# <a name="sharedlisteners-element"></a>\<sharedListeners > 요소
소스 또는 추적 요소가 참조할 수 있는 수신기가 포함되어 있습니다.  이러한 수신기 기본적으로 모든 추적을 받지 않습니다 하 고 런타임 시 이러한 수신기를 검색할 수 없는 합니다. 공유 수신기로 식별 하는 수신기 이름으로 추적 소스를 추가할 수 있습니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners>  
  
## <a name="syntax"></a>구문  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|`sharedListeners` 컬렉션에 수신기를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`Configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|ASP.NET 구성 섹션의 루트 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 공유 수신기 컬렉션에 수신기를 추가 해도 해당 활성 수신기. 여전히 추가 해야 추적 또는 추적 소스에 추가 하 여는 `Listeners` 추적 요소의 컬렉션입니다. .NET Framework의 수신기 클래스에서 파생 된 <xref:System.Diagnostics.TraceListener> 클래스입니다.  
  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는 `<sharedListeners>` 수신기에 추가할 요소 `console` 에 `Listeners` 둘 다에 대 한 컬렉션을 <xref:System.Diagnostics.TraceSource> 및 <xref:System.Diagnostics.Trace> 클래스입니다. 콘솔 추적 수신기에 대 한 호출을 통해 콘솔에 추적 정보를 씁니다 <xref:System.Diagnostics.TraceSource> 또는 <xref:System.Diagnostics.Trace>합니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.TraceListener>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
