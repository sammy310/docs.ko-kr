---
title: <filter> 요소에 대 한 <add> 에 대 한 <sharedListeners>
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
ms.openlocfilehash: 2bef729f179b41509d3c0381b26e38e364dbf86b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120746"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a>\<필터 > 요소에 대 한 \<추가 >에 대 한 \<sharedListeners >
`sharedListeners` 컬렉션에 있는 수신기에 필터를 추가합니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<sharedListeners > 요소  
\<add>  
\<filter>  
  
## <a name="syntax"></a>구문  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|**type**|필수 특성입니다.<br /><br /> 필터의 형식을 지정합니다. 형식의 전체 이름을 사용할 수 있습니다 (형식의 합니다 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 속성), 어셈블리 정보를 포함 하 여 정규화 된 형식 이름을 사용할 수 있습니다 (형식의 <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> 속성). 정규화 된 형식 이름 만들기에 대 한 내용은 참조 하세요 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.|  
|**initializeData**|선택적 특성입니다.<br /><br /> 지정된 된 클래스에 대 한 생성자에 전달 된 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`sharedListeners`|모든 소스 또는 추적 요소가 참조할 수 있는 수신기의 컬렉션입니다.|  
|`add`|수신기를 추가 합니다 **sharedListeners** 컬렉션입니다.|  
  
## <a name="remarks"></a>설명  
 수신기에 정의 된 경우는 `<add>` 의 요소를 `<sharedListeners>` 요소에는 수신기에 대 한 필터를 정의 해야를 `<filter>` 의 자식 요소는 `<add>` 요소.  
  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 `<filter>` 추적 수신기에 필터를 추가할 요소입니다 `console` 에 `sharedListeners` 컬렉션입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
