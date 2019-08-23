---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: c46d1fb9eb853e57c7ad1b97eb9a22556cdfb7d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913107"
---
# <a name="workflowunhandledexception"></a>\<workflowUnhandledException>
워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.  
  
\<system.ServiceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<workflowUnhandledException>  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|Description|  
|---------------|-----------------|  
|action|처리되지 않은 예외가 발생했을 때 수행할 동작을 지정하는 문자열입니다. 이 특성은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<servicebehaviors의 \<동작 > >](behavior-of-servicebehaviors-of-workflow.md)|동작 요소를 지정합니다.|  
  
## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
