---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937197"
---
# <a name="services"></a>\<services>
서비스는 구성 파일의 `services` 섹션에 정의됩니다. 서비스별로 해당 `service` 구성 섹션이 있습니다.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<service>](service.md)|특정 서비스의 서비스 계약, 동작 및 엔드포인트를 정의합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.ServicesSection>
