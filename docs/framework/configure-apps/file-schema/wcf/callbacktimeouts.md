---
title: <callbackTimeouts>
ms.date: 03/30/2017
ms.assetid: d7fcfc5f-6d35-491e-8fa6-2f964c1e792f
ms.openlocfilehash: e666bac0be772e417f140e1482649f82ea70e2f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673422"
---
# <a name="callbacktimeouts"></a>\<callbackTimeouts>
이중 콜백 계약 시나리오에서 트랜잭션이 서버에서 클라이언트로 이동할 때의 시간 제한 값을 지정합니다.  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<callbackTimeOuts>  
  
## <a name="syntax"></a>구문  
  
```xml  
<callbackTimeOuts transactionTimeout="TimeSpan" />
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`transactionTimeout`|트랜잭션이 완료되어야 하거나, 완료되지 못할 경우 자동으로 종료되어야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다. 기본값은 "00: 00:00"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|엔드포인트 동작을 지정합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.CallbackTimeoutsElement>
