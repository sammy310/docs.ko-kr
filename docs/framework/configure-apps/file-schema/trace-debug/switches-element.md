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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153232"
---
# <a name="switches-element"></a>\<> 요소 전환
추적 스위치 및 추적 스위치가 설정된 수준이 포함되어 있습니다.  

[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.진단>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<>스위치**

## <a name="syntax"></a>구문  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<>추가](add-element-for-switches.md)|추적 스위치를 설정하는 수준을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`System.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 추적 스위치의 수준을 구성 파일에 배치하여 변경할 수 있습니다. 스위치가 있는 <xref:System.Diagnostics.BooleanSwitch>경우 을 켜고 끌 수 있습니다. 스위치가 a인 <xref:System.Diagnostics.TraceSwitch>경우 다른 수준을 할당하여 응용 프로그램에서 출력하는 추적 또는 디버그 메시지 유형을 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 ** \<스위치>** 요소를 사용하여 `General` 추적 스위치를 <xref:System.Diagnostics.TraceLevel> 수준으로 설정하고 부울 추적 스위치를 `Data` 사용하도록 설정하는 방법을 보여 주며 있습니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [추적 및 디버그 설정 스키마](index.md)
