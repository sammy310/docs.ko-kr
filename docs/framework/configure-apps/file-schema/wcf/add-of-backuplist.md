---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663366"
---
# <a name="add-of-backuplist"></a>\<\<backupList > > 추가
백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.  
  
 \<system.serviceModel>  
\<라우팅 >  
\<backupLists>  
\<backupList>  
\<add>  
  
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
  
|특성|Description|  
|---------------|-----------------|  
|name|백업 엔드포인트의 이름을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|기본 끝점에 연결할 수 없는 경우 라우팅 서비스에서 사용할 끝점 목록을 포함 합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
