---
description: '자세한 정보: 117-WorkflowInstanceTerminatedRecordWithId'
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.date: 03/30/2017
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
ms.openlocfilehash: d57940801cd9850136355a9ad4f91ba7c44fd5b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703239"
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="55123-103">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="55123-103">117 - WorkflowInstanceTerminatedRecordWithId</span></span>

## <a name="properties"></a><span data-ttu-id="55123-104">속성</span><span class="sxs-lookup"><span data-stu-id="55123-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="55123-105">ID</span><span class="sxs-lookup"><span data-stu-id="55123-105">ID</span></span>|<span data-ttu-id="55123-106">117</span><span class="sxs-lookup"><span data-stu-id="55123-106">117</span></span>|  
|<span data-ttu-id="55123-107">키워드</span><span class="sxs-lookup"><span data-stu-id="55123-107">Keywords</span></span>|<span data-ttu-id="55123-108">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="55123-108">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="55123-109">Level</span><span class="sxs-lookup"><span data-stu-id="55123-109">Level</span></span>|<span data-ttu-id="55123-110">Error</span><span class="sxs-lookup"><span data-stu-id="55123-110">Error</span></span>|  
|<span data-ttu-id="55123-111">채널</span><span class="sxs-lookup"><span data-stu-id="55123-111">Channel</span></span>|<span data-ttu-id="55123-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="55123-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="55123-113">설명</span><span class="sxs-lookup"><span data-stu-id="55123-113">Description</span></span>  

 <span data-ttu-id="55123-114">워크플로 인스턴스가 WorkflowInstanceTerminatedRecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="55123-114">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="55123-115">메시지</span><span class="sxs-lookup"><span data-stu-id="55123-115">Message</span></span>  

 <span data-ttu-id="55123-116">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="55123-116">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="55123-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="55123-117">Details</span></span>  
  
|<span data-ttu-id="55123-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="55123-118">Data Item Name</span></span>|<span data-ttu-id="55123-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="55123-119">Data Item Type</span></span>|<span data-ttu-id="55123-120">설명</span><span class="sxs-lookup"><span data-stu-id="55123-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="55123-121">InstanceId</span><span class="sxs-lookup"><span data-stu-id="55123-121">InstanceId</span></span>|<span data-ttu-id="55123-122">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="55123-122">xs:GUID</span></span>|<span data-ttu-id="55123-123">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="55123-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="55123-124">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="55123-124">RecordNumber</span></span>|<span data-ttu-id="55123-125">xs:long</span><span class="sxs-lookup"><span data-stu-id="55123-125">xs:long</span></span>|<span data-ttu-id="55123-126">내보낸 레코드의 시퀀스 번호</span><span class="sxs-lookup"><span data-stu-id="55123-126">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="55123-127">EventTime</span><span class="sxs-lookup"><span data-stu-id="55123-127">EventTime</span></span>|<span data-ttu-id="55123-128">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="55123-128">xs:dateTime</span></span>|<span data-ttu-id="55123-129">이벤트를 내보낸 시간(UTC)</span><span class="sxs-lookup"><span data-stu-id="55123-129">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="55123-130">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="55123-130">ActivityDefinitionId</span></span>|<span data-ttu-id="55123-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-131">xs:string</span></span>|<span data-ttu-id="55123-132">워크플로의 루트 활동 이름</span><span class="sxs-lookup"><span data-stu-id="55123-132">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="55123-133">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="55123-133">State</span></span>|<span data-ttu-id="55123-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-134">xs:string</span></span>|<span data-ttu-id="55123-135">워크플로의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="55123-135">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="55123-136">주석</span><span class="sxs-lookup"><span data-stu-id="55123-136">Annotations</span></span>|<span data-ttu-id="55123-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-137">xs:string</span></span>|<span data-ttu-id="55123-138">이 이벤트에 추가된 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="55123-138">The annotations that were added to this event.</span></span> <span data-ttu-id="55123-139">값은 xml 요소에 a 형식으로 저장 됩니다 \<items> \< item name = "annotationName" type="System.String"> \</item> \</items> .</span><span class="sxs-lookup"><span data-stu-id="55123-139">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="55123-140">주석을 지정 하지 않으면 문자열에가 포함 \<items/> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55123-140">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="55123-141">ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="55123-141">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="55123-142">이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값을 ...로 대체 하 여 이벤트를 자릅니다. \<items> \</items></span><span class="sxs-lookup"><span data-stu-id="55123-142">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="55123-143">ProfileName</span><span class="sxs-lookup"><span data-stu-id="55123-143">ProfileName</span></span>|<span data-ttu-id="55123-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-144">xs:string</span></span>|<span data-ttu-id="55123-145">이 이벤트를 내보낸 이름 또는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="55123-145">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="55123-146">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="55123-146">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="55123-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-147">xs:string</span></span>|<span data-ttu-id="55123-148">워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="55123-148">The workflow definition id</span></span>|  
|<span data-ttu-id="55123-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="55123-149">AppDomain</span></span>|<span data-ttu-id="55123-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="55123-150">xs:string</span></span>|<span data-ttu-id="55123-151">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="55123-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
