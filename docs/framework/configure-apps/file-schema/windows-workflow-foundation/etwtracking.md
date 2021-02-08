---
description: 다음에 대해 자세히 알아보세요. <etwTracking>
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: b89d832e73440d5b60a05477ccf85178c2f43a2d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795081"
---
# \<etwTracking>

<span data-ttu-id="0c7ff-102">서비스가 <xref:System.Activities.Tracking.EtwTrackingParticipant>를 통해 ETW 추적을 사용할 수 있도록 하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-102">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etwTracking>**  
  
## <a name="syntax"></a><span data-ttu-id="0c7ff-103">구문</span><span class="sxs-lookup"><span data-stu-id="0c7ff-103">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c7ff-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c7ff-104">Attributes and Elements</span></span>  

 <span data-ttu-id="0c7ff-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c7ff-106">특성</span><span class="sxs-lookup"><span data-stu-id="0c7ff-106">Attributes</span></span>  
  
|<span data-ttu-id="0c7ff-107">attribute</span><span class="sxs-lookup"><span data-stu-id="0c7ff-107">Attribute</span></span>|<span data-ttu-id="0c7ff-108">설명</span><span class="sxs-lookup"><span data-stu-id="0c7ff-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c7ff-109">profileName</span><span class="sxs-lookup"><span data-stu-id="0c7ff-109">profileName</span></span>|<span data-ttu-id="0c7ff-110">이 동작과 연결된 추적 프로필의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-110">A string that specifies the name of the tracking profile associated with this behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c7ff-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c7ff-111">Child Elements</span></span>  

 <span data-ttu-id="0c7ff-112">없음</span><span class="sxs-lookup"><span data-stu-id="0c7ff-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c7ff-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c7ff-113">Parent Elements</span></span>  
  
|<span data-ttu-id="0c7ff-114">요소</span><span class="sxs-lookup"><span data-stu-id="0c7ff-114">Element</span></span>|<span data-ttu-id="0c7ff-115">설명</span><span class="sxs-lookup"><span data-stu-id="0c7ff-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c7ff-116">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="0c7ff-116">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="0c7ff-117">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-117">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c7ff-118">설명</span><span class="sxs-lookup"><span data-stu-id="0c7ff-118">Remarks</span></span>  

 <span data-ttu-id="0c7ff-119">이 구성 요소를 서비스의 동작 구성에 추가하는 경우 워크플로 서비스에서 추적 참가자를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-119">When added to the service’s behavior configuration, this configuration element configures a tracking participant on a workflow service.</span></span>  
  
 <span data-ttu-id="0c7ff-120">추적 참가자는 워크플로에서 내보내지는 추적 데이터를 가져오고 이 데이터를 다른 미디어에 저장하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-120">Tracking participants are used to get the tracking data emitted from the workflow and store it into different mediums.</span></span> <span data-ttu-id="0c7ff-121">마찬가지로 추적 레코드에 대한 모든 사후 처리를 추적 참가자 내에서 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-121">Likewise, any post processing on the tracking Records can also be done within the tracking participant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c7ff-122">예제</span><span class="sxs-lookup"><span data-stu-id="0c7ff-122">Example</span></span>  

 <span data-ttu-id="0c7ff-123">다음 구성 예제에서는 Web.config 파일에서 구성되는 표준 ETW 추적 참가자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-123">The following configuration example shows the standard ETW tracking participant being configured in the Web.config file.</span></span>  
  
 <span data-ttu-id="0c7ff-124">Etw 추적 참가자가 ETW에 추적 레코드를 기록 하는 데 사용 하는 공급자 Id는 섹션에서 정의 됩니다 **\<diagnostics>** .</span><span class="sxs-lookup"><span data-stu-id="0c7ff-124">The Provider Id that the ETW Tracking Participant uses for writing the Tracking Records to ETW is defined in the **\<diagnostics>** section.</span></span> <span data-ttu-id="0c7ff-125">추적 참가자에는 구독하는 추적 레코드를 지정하기 위해 연결된 프로필이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-125">The tracking participant has a profile associated with it to specify the tracking records it has subscribed to.</span></span> <span data-ttu-id="0c7ff-126">이는 요소의 **profileName** 특성에 의해 정의 됩니다 **\<add>** .</span><span class="sxs-lookup"><span data-stu-id="0c7ff-126">This is defined by the **profileName** attribute of the **\<add>** element.</span></span> <span data-ttu-id="0c7ff-127">이러한 설정이 정의 되 면 추적 참가자가 서비스 동작에 추가 됩니다 **\<etwTracking>** .</span><span class="sxs-lookup"><span data-stu-id="0c7ff-127">Once these are defined, the Tracking Participant is added to the **\<etwTracking>** service behavior.</span></span> <span data-ttu-id="0c7ff-128">이렇게 하면 선택된 추적 참가자가 워크플로 인스턴스의 확장에 추가되어 추적 레코드를 받기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="0c7ff-128">This will add the selected Tracking Participants to the Workflow instance’s extensions, so that they begin to receive the Tracking Records.</span></span>  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c7ff-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c7ff-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [<span data-ttu-id="0c7ff-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="0c7ff-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0c7ff-131">추적 참가자</span><span class="sxs-lookup"><span data-stu-id="0c7ff-131">Tracking Participants</span></span>](../../../windows-workflow-foundation/tracking-participants.md)
