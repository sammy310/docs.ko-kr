---
title: <scopes>
ms.date: 03/30/2017
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
ms.openlocfilehash: dd6513930798e9e1ab263f75c9350511c2dcdcd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935177"
---
# <a name="scopes"></a>\<scopes>
쿼리 중에 서비스 엔드포인트를 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.  
  
\<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<endpointDiscovery>  
\<scopes>  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|특성|Description|  
|---------------|-----------------|  
|[\<add>](add-of-scopes.md)|서비스를 찾기 위한 일치 기준으로 사용할 수 있는 엔드포인트의 범위 정보를 추가합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<endpointDiscovery>](endpointdiscovery.md)|검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 엔드포인트에 대한 다양한 검색 설정을 지정합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
