---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 918a365004efea82f4ef4c8868f6821d4bb6da18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855184"
---
# \<filterTable>
메시지를 평가할 필터 목록 및 필터가 true로 평가될 경우 메시지를 라우팅할 클라이언트 엔드포인트를 포함하는 라우팅 테이블을 나타냅니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<filterTables>**](filtertables.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filterTable>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<routing>
  <filterTables>
     name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|요소|Description|  
|-------------|-----------------|  
|name|이 구성 요소의 고유 이름을 포함하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 엔드포인트 간의 매핑입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<routing>](routing.md)|라우팅 테이블을 포함하는 구성 섹션입니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
