---
title: <switches> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: 44f5c918f19f84daf827ad4e8f3b6bfbc3e9f439
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704507"
---
# <a name="switches-element"></a>\<스위치 > 요소
추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.  
  
 \<configuration>  
\<system.diagnostics>  
\<switches>  
  
## <a name="syntax"></a>구문  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|추적 스위치를 설정하는 수준을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`System.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 구성 파일에 배치 하 여 추적 스위치의 수준을 변경할 수 있습니다. 스위치가 <xref:System.Diagnostics.BooleanSwitch>를 켜거나 끌 수 있습니다. 스위치가 <xref:System.Diagnostics.TraceSwitch>, 추적의 유형을 지정 하 고 다른 수준을 할당할 수 있습니다 또는 디버그 메시지 응용 프로그램에서 출력 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는  **\<전환 >** 설정할 요소입니다를 `General` 추적 스위치를를 <xref:System.Diagnostics.TraceLevel> 수준 및 사용을 `Data` Boolean 추적 스위치.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
