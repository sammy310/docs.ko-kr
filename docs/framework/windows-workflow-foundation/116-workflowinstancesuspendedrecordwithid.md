---
description: '자세한 정보: 116-WorkflowInstanceSuspendedRecordWithId'
title: 116 - WorkflowInstanceSuspendedRecordWithId
ms.date: 03/30/2017
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
ms.openlocfilehash: 32746777d32ed0c8320d53da9f73ddb8d55a5573
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99703252"
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a><span data-ttu-id="b6e12-103">116 - WorkflowInstanceSuspendedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="b6e12-103">116 - WorkflowInstanceSuspendedRecordWithId</span></span>

## <a name="properties"></a><span data-ttu-id="b6e12-104">속성</span><span class="sxs-lookup"><span data-stu-id="b6e12-104">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b6e12-105">ID</span><span class="sxs-lookup"><span data-stu-id="b6e12-105">ID</span></span>|<span data-ttu-id="b6e12-106">116</span><span class="sxs-lookup"><span data-stu-id="b6e12-106">116</span></span>|  
|<span data-ttu-id="b6e12-107">키워드</span><span class="sxs-lookup"><span data-stu-id="b6e12-107">Keywords</span></span>|<span data-ttu-id="b6e12-108">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="b6e12-108">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="b6e12-109">Level</span><span class="sxs-lookup"><span data-stu-id="b6e12-109">Level</span></span>|<span data-ttu-id="b6e12-110">정보</span><span class="sxs-lookup"><span data-stu-id="b6e12-110">Information</span></span>|  
|<span data-ttu-id="b6e12-111">채널</span><span class="sxs-lookup"><span data-stu-id="b6e12-111">Channel</span></span>|<span data-ttu-id="b6e12-112">Microsoft-Windows-애플리케이션 서버-애플리케이션/분석</span><span class="sxs-lookup"><span data-stu-id="b6e12-112">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b6e12-113">설명</span><span class="sxs-lookup"><span data-stu-id="b6e12-113">Description</span></span>  

 <span data-ttu-id="b6e12-114">워크플로 인스턴스가 WorkflowInstanceSuspended Record를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-114">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceSuspended Record.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b6e12-115">메시지</span><span class="sxs-lookup"><span data-stu-id="b6e12-115">Message</span></span>  

 <span data-ttu-id="b6e12-116">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="b6e12-116">TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="b6e12-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b6e12-117">Details</span></span>  
  
|<span data-ttu-id="b6e12-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b6e12-118">Data Item Name</span></span>|<span data-ttu-id="b6e12-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b6e12-119">Data Item Type</span></span>|<span data-ttu-id="b6e12-120">설명</span><span class="sxs-lookup"><span data-stu-id="b6e12-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b6e12-121">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b6e12-121">InstanceId</span></span>|<span data-ttu-id="b6e12-122">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="b6e12-122">xs:GUID</span></span>|<span data-ttu-id="b6e12-123">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="b6e12-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="b6e12-124">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="b6e12-124">RecordNumber</span></span>|<span data-ttu-id="b6e12-125">xs:long</span><span class="sxs-lookup"><span data-stu-id="b6e12-125">xs:long</span></span>|<span data-ttu-id="b6e12-126">내보낸 레코드의 시퀀스 번호</span><span class="sxs-lookup"><span data-stu-id="b6e12-126">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="b6e12-127">EventTime</span><span class="sxs-lookup"><span data-stu-id="b6e12-127">EventTime</span></span>|<span data-ttu-id="b6e12-128">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="b6e12-128">xs:dateTime</span></span>|<span data-ttu-id="b6e12-129">이벤트를 내보낸 시간(UTC)</span><span class="sxs-lookup"><span data-stu-id="b6e12-129">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="b6e12-130">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="b6e12-130">ActivityDefinitionId</span></span>|<span data-ttu-id="b6e12-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-131">xs:string</span></span>|<span data-ttu-id="b6e12-132">워크플로의 루트 활동 이름</span><span class="sxs-lookup"><span data-stu-id="b6e12-132">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="b6e12-133">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="b6e12-133">State</span></span>|<span data-ttu-id="b6e12-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-134">xs:string</span></span>|<span data-ttu-id="b6e12-135">워크플로의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="b6e12-135">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="b6e12-136">주석</span><span class="sxs-lookup"><span data-stu-id="b6e12-136">Annotations</span></span>|<span data-ttu-id="b6e12-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-137">xs:string</span></span>|<span data-ttu-id="b6e12-138">이 이벤트에 추가된 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-138">The annotations that were added to this event.</span></span> <span data-ttu-id="b6e12-139">값은 xml 요소에 a 형식으로 저장 됩니다 \<items> \< item name = "annotationName" type="System.String"> \</item> \</items> .</span><span class="sxs-lookup"><span data-stu-id="b6e12-139">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="b6e12-140">주석을 지정 하지 않으면 문자열에가 포함 \<items/> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-140">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="b6e12-141">ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-141">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="b6e12-142">이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값을 ...로 대체 하 여 이벤트를 자릅니다. \<items> \</items></span><span class="sxs-lookup"><span data-stu-id="b6e12-142">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="b6e12-143">ProfileName</span><span class="sxs-lookup"><span data-stu-id="b6e12-143">ProfileName</span></span>|<span data-ttu-id="b6e12-144">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-144">xs:string</span></span>|<span data-ttu-id="b6e12-145">이 이벤트를 내보낸 이름 또는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b6e12-145">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="b6e12-146">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="b6e12-146">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="b6e12-147">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-147">xs:string</span></span>|<span data-ttu-id="b6e12-148">워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-148">The workflow definition id</span></span>|  
|<span data-ttu-id="b6e12-149">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b6e12-149">AppDomain</span></span>|<span data-ttu-id="b6e12-150">xs:string</span><span class="sxs-lookup"><span data-stu-id="b6e12-150">xs:string</span></span>|<span data-ttu-id="b6e12-151">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e12-151">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
