---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151847"
---
# <a name="workflowidle"></a>\<워크플로우유>
유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.  
  
[**\<구성>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<시스템. 서비스 모델>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>동작**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<서비스 행동>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<행동>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<워크플로유유>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan"
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|timeToPersist|워크플로가 유휴 상태가 되고 유지되는 시간 간의 기간을 지정하는 Timespan 값입니다. 기본값은 TimeSpan.MaxValue입니다.<br /><br /> 워크플로 인스턴스가 유휴 상태가 되면 기간이 경과되기 시작합니다. 이 특성은 인스턴스를 가능하면 오랫동안 메모리에 보관하면서 워크플로 인스턴스를 적극적으로 유지하려는 경우 유용합니다. 이 특성은 해당 값이 **timeToUnload** 특성보다 적은 경우에만 유효합니다. 이보다 크면 무시됩니다. **timeToUnload** 특성에 의해 지정된 값 앞에 이 특성이 경과하는 경우 워크플로를 언로드하기 전에 지속성이 완료되어야 합니다. 이것은 워크플로가 유지될 때까지 언로드 작업이 지연될 수 있음을 의미합니다. 지속성 계층은 일시적인 오류가 발생할 경우 재시도를 처리하고 복구할 수 없는 오류가 발생하는 경우에만 예외를 throw하는 역할을 담당합니다. 따라서 유지 중에 throw되는 예외는 심각한 예외로 간주되며 워크플로 인스턴스가 중단됩니다.|  
|timeToUnload|워크플로가 유휴 상태가 되고 언로드되는 시간 간의 기간을 지정하는 Timespan 값입니다. 기본값은 1분입니다.<br /><br /> 워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다. 이 특성이 0으로 설정되면 워크플로가 유휴 상태가 되는 즉시 워크플로 인스턴스가 유지되고 언로드됩니다. 이 특성을 TimeSpan.MaxValue로 설정하면 언로드 작업이 사용되지 않습니다. 즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<\<행동> 서비스 행동>](behavior-of-servicebehaviors-of-workflow.md)|동작 요소를 지정합니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
