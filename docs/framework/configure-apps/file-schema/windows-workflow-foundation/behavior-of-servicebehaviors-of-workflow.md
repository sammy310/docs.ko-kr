---
title: <behavior>of <serviceBehaviors> 워크플로
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152322"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a>\<behavior>of \<serviceBehaviors> 워크플로
**Behavior** 요소는 서비스의 동작에 대 한 설정 컬렉션을 포함 합니다. 각 동작은 **이름**으로 인덱싱됩니다. 서비스는 요소의 **behaviorConfiguration** 특성을 사용 하 여이 이름을 통해 각 동작에 연결할 수 있습니다 [\<endpoint>](../wcf/endpoint-element.md) . 따라서 설정을 다시 정의하지 않고도 엔드포인트에서 일반 동작 구성을 공유할 수 있습니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan"
                           leaseTimeout="TimeSpan"
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String"
                                  hostLockRenewalPeriod="TimeSpan"
                                  instanceCompletionAction="DeleteNothing/DeleteAll"
                                  instanceEncodingAction="None/GZip"
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan"
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|Description|  
|---------------|-----------------|  
|name|동작의 구성 이름을 포함하는 고유 문자열입니다. 이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|서비스에서 버퍼링되는 수신 처리를 사용할 수 있도록 하는 서비스 동작입니다. 이를 통해 워크플로 서비스가 순서가 맞지 않는 메시지를 처리할 수 있습니다.|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|서비스가 <xref:System.Activities.Tracking.EtwTrackingParticipant>를 통해 ETW 추적을 사용할 수 있도록 하는 서비스 동작입니다.|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|캐시 공유 수준, 채널 팩터리 캐시 설정 및 Send 메시징 활동을 사용하여 서비스 엔드포인트로 메시지를 전송하는 워크플로를 위한 채널 캐시 설정에 대한 사용자 지정을 가능하게 하는 서비스 동작입니다.|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|워크플로 서비스 인스턴스의 상태 정보를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 유지하도록 지원하는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 기능을 구성하는 서비스 동작입니다.|  
|[\<workflowIdle>](workflowidle.md)|유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|지속성 예외, 처리되지 않은 예외 동작 및 유휴 동작을 비롯하여 워크플로 인스턴스 실행 방법을 제어하는 설정을 지정할 수 있는 서비스 동작입니다.|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|워크플로 서비스 내에서 처리되지 않은 예외가 발생할 때 수행할 동작을 지정할 수 있는 서비스 동작입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|Description|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|서비스 동작 요소의 컬렉션입니다.|
