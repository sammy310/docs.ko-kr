---
description: 다음에 대해 자세히 알아보세요. <persistenceProvider>
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 60ddaf9f26f496bd7d79ccab84f84135e46963d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683556"
---
# \<persistenceProvider>

사용할 지속성 공급자 구현 형식 및 지속성 작업에 사용할 제한 시간을 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistenceProvider>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|persistenceOperationTimeout|지속성 작업에 사용되는 제한 시간을 지정하는 <xref:System.TimeSpan> 값입니다. 기본값은 "00:00:30"입니다.|  
|형식|사용할 지속성 공급자 팩터리의 형식을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  

 이 요소는 WCF 서비스의 상태를 serialize하는 데 사용되는 지속성 공급자를 지정합니다. 이 요소는 HTTP 헤더에서 상태 정보를 전달하는 `wsHttpContextBinding`과 함께 사용되어야 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
