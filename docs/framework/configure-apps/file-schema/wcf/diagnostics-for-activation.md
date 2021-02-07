---
description: '자세히 알아보기: <diagnostics> 활성화'
title: <diagnostics> 활성화
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: aa1529a478ac367ea89c8926571c6c6f2f57cf74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698364"
---
# <a name="diagnostics-for-activation"></a>\<diagnostics> 활성화

WCF (Windows Communication Foundation) 수신기의 진단 기능을 구성 합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<diagnostics>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>Type  

 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`performanceCountersEnabled`|진단 용도로 성능 카운터를 사용할지 여부를 나타내는 부울 값입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|수신기 프로세스 SMSvcHost.exe에 대한 구성 설정을 포함합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>
