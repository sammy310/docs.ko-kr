---
title: <filter>에 <add> 대 한 요소<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153455"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<공유리스> \<대한 \<추가>> 요소 필터링
`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<공유청취자>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>추가**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<필터>**

## <a name="syntax"></a>구문  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|**종류**|필수 특성입니다.<br /><br /> 필터 유형을 지정합니다. 형식의 전체 이름만 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 사용하거나(속성 형식) 어셈블리 정보를 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> 포함하여 정규화된 형식 이름을 사용할 수 있습니다. 정규화된 형식 이름을 만드는 방법에 대한 자세한 내용은 [정규화된 형식 이름 지정을](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)참조하십시오.|  
|**초기화데이터**|선택적 특성입니다.<br /><br /> 문자열은 지정된 클래스의 생성자에게 전달되었습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 소스 또는 추적 요소가 참조할 수 있는 리스너 컬렉션입니다.|  
|`add`|**공유리스 컬렉션에** 수신기를 추가합니다.|  
  
## <a name="remarks"></a>설명  
 `<add>` 리스너가 `<sharedListeners>` 요소의 요소에 정의된 경우 해당 수신기에 대한 필터는 `<filter>` `<add>` 요소의 자식인 요소에서 정의되어야 합니다.  
  
 이 요소는 컴퓨터 구성 파일(Machine.config) 및 응용 프로그램 구성 파일에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 요소를 사용하여 `<filter>` 컬렉션의 추적 `console` 수신기에 필터를 `sharedListeners` 추가하는 방법을 보여 주며 있습니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [추적 및 디버그 설정 스키마](index.md)
