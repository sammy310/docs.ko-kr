---
title: <behaviors> 워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 3c6017b6-0c4f-4192-bd67-9515f5d1ec82
ms.openlocfilehash: b7c5cf93a82ac88c25f9c478ad52cf41eb6f6d65
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129209"
---
# <a name="behaviors-of-workflow"></a>\<동작 > 워크플로
이 요소에 포함 된 **serviceBehaviors** 컬렉션입니다.  컬렉션의 각 요소는 워크플로 서비스에서 사용하는 동작 요소를 정의합니다. 각 동작 요소는 고유한으로 식별 되 **이름을** 특성입니다.  
  
 \<system.ServiceModel>  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|이 구성 섹션은 특정 워크플로 서비스에 정의된 모든 동작을 나타냅니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.serviceModel>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|모든 워크플로 구성 요소의 루트 요소입니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [동작을 사용하여 런타임 구성 및 확장](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
