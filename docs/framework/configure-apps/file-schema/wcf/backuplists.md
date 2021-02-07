---
description: 다음에 대해 자세히 알아보세요. <backupLists>
title: <backupLists>
ms.date: 03/30/2017
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
ms.openlocfilehash: 9647c507f85eba6bfd001b34dbf617bc881d3f2e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99749703"
---
# \<backupLists>

오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다. 각 자식 요소는 라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트 집합을 열거하는 백업 목록입니다. 목록의 첫 번째 엔드포인트가 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 엔드포인트로 장애 조치(failover)됩니다.  따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 애플리케이션에 지정할 필요 없이 애플리케이션의 안정성을 빠르게 향상시킬 수 있습니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<backupLists>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  

 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](filter.md)|라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다. .|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>
