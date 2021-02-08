---
description: 다음에 대해 자세히 알아보세요. <sqlWorkflowInstanceStore>
title: <sqlWorkflowInstanceStore>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 8fcf5dd970adf5aa668d90b012c94e04c5373752
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782013"
---
# \<sqlWorkflowInstanceStore>

<span data-ttu-id="fa5cb-102">워크플로 서비스 인스턴스의 상태 정보를 SQL Server 2005 또는 SQL Server 2008 데이터베이스에 유지하도록 지원하는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 기능을 구성하는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-102">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="fa5cb-103">이 기능에 대 한 자세한 내용은 [SQL 워크플로 인스턴스 저장소](../../../windows-workflow-foundation/sql-workflow-instance-store.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-103">For more information on this feature, see [SQL Workflow Instance Store](../../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<sqlWorkflowInstanceStore>**  
  
## <a name="syntax"></a><span data-ttu-id="fa5cb-104">구문</span><span class="sxs-lookup"><span data-stu-id="fa5cb-104">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String"
                                hostLockRenewalPeriod="TimeSpan"
                                instanceCompletionAction="DeleteNothing/DeleteAll"
                                instanceEncodingAction="None/GZip"
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa5cb-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fa5cb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fa5cb-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa5cb-107">특성</span><span class="sxs-lookup"><span data-stu-id="fa5cb-107">Attributes</span></span>  
  
|<span data-ttu-id="fa5cb-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fa5cb-108">Attribute</span></span>|<span data-ttu-id="fa5cb-109">설명</span><span class="sxs-lookup"><span data-stu-id="fa5cb-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa5cb-110">connectionString</span><span class="sxs-lookup"><span data-stu-id="fa5cb-110">connectionString</span></span>|<span data-ttu-id="fa5cb-111">기본 지속성 데이터베이스에 연결하는 데 사용되는 연결 문자열을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-111">A string that contains a connection string used to connect to an underlying persistence database.</span></span>|  
|<span data-ttu-id="fa5cb-112">connectionStringName</span><span class="sxs-lookup"><span data-stu-id="fa5cb-112">connectionStringName</span></span>|<span data-ttu-id="fa5cb-113">데이터베이스 서버에 대한 명명된 연결 문자열을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-113">A string that contains a named connection string to the database server.</span></span> <span data-ttu-id="fa5cb-114">명명된 된 연결 문자열의 예로 "defaultconnectionstring"입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-114">An example of a named connection string is "DefaultConnectionString".</span></span>|  
|<span data-ttu-id="fa5cb-115">hostLockRenewalPeriod</span><span class="sxs-lookup"><span data-stu-id="fa5cb-115">hostLockRenewalPeriod</span></span>|<span data-ttu-id="fa5cb-116">호스트에서 인스턴스에 대한 잠금을 갱신해야 하는 기간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-116">A Timespan value that specifies the time period in which the host must renew the lock on an instance.</span></span> <span data-ttu-id="fa5cb-117">호스트에서 지정된 기간 내에 잠금을 갱신하지 않으면 인스턴스 잠금이 해제되어 다른 호스트가 이를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-117">If the host does not renew the lock in the specified time period, the instance is unlocked and may be picked up by another host.</span></span><br /><br /> <span data-ttu-id="fa5cb-118">워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-118">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="fa5cb-119">이 특성이 0으로 설정되면 워크플로가 유휴 상태가 되는 즉시 워크플로 인스턴스가 유지되고 언로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-119">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="fa5cb-120">이 특성을 TimeSpan.MaxValue로 설정하면 언로드 작업이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-120">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="fa5cb-121">즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-121">Idle workflow instances are never unloaded.</span></span>|  
|<span data-ttu-id="fa5cb-122">instanceCompletionAction</span><span class="sxs-lookup"><span data-stu-id="fa5cb-122">instanceCompletionAction</span></span>|<span data-ttu-id="fa5cb-123">워크플로 인스턴스가 완료되면 워크플로 인스턴스 데이터가 지속성 저장소에 보관되는지 아니면 해당 시점에 삭제되는지를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-123">A value that specifies whether workflow instance data is kept in the persistence store after the workflow instance completes or if it is deleted at that point.</span></span> <span data-ttu-id="fa5cb-124">이 값은 <xref:System.Activities.DurableInstancing.InstanceCompletionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-124">This value is of type <xref:System.Activities.DurableInstancing.InstanceCompletionAction>.</span></span><br /><br /> <span data-ttu-id="fa5cb-125">열거된 동작은 인스턴스에서 해당 작업을 완료하면 지속성 저장소에서 인스턴스 데이터를 삭제하거나 지속성 저장소에서 인스턴스 데이터를 삭제하지 않는 것으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-125">The enumerated actions consist of deleting the instance data from the persistence store or not deleting the instance data from the persistence store, when the instance has completed its operation.</span></span><br /><br /> <span data-ttu-id="fa5cb-126">완료된 후 인스턴스를 유지하면 지속성 데이터베이스가 빠르게 커지고 데이터베이스 성능에 영향을 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-126">Keeping instances after completion causes the persistence database to grow rapidly and this affects the performance of the database.</span></span> <span data-ttu-id="fa5cb-127">성능 요구 사항을 충족하는 수준으로 데이터베이스 성능을 유지하려면 이러한 레코드를 주기적으로 삭제하는 데이터베이스 비우기 정책을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-127">You should configure a database purge policy to delete these records periodically to ensure that the performance of the database is at the level that satisfy your performance requirements.</span></span>|  
|<span data-ttu-id="fa5cb-128">instanceEncodingOption</span><span class="sxs-lookup"><span data-stu-id="fa5cb-128">instanceEncodingOption</span></span>|<span data-ttu-id="fa5cb-129">정보를 지속성 저장소에 저장하기 전에 인스턴스 상태 정보를 GZip 알고리즘을 사용하여 압축할지 여부를 지정하는 선택적 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-129">An optional value that specifies  whether the instance state information is compressed using the GZip algorithm before the information is saved in the persistence store..</span></span> <span data-ttu-id="fa5cb-130">이 값은 <xref:System.Activities.DurableInstancing.InstanceEncodingOption> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-130">This value is of type <xref:System.Activities.DurableInstancing.InstanceEncodingOption>.</span></span> <span data-ttu-id="fa5cb-131">이 속성에 사용할 수 있는 값은 <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None> 압축 안 함을 지정 하 고,는 <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip> 인스턴스 데이터를 압축 하 고 gzip 알고리즘을 사용 하도록 지정 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-131">Possible values for this property are <xref:System.Activities.DurableInstancing.InstanceEncodingOption.None>, which specifies no compression, and <xref:System.Activities.DurableInstancing.InstanceEncodingOption.GZip>, which specifies that instance data is compressed and uses the gzip algorithm.</span></span>|  
|<span data-ttu-id="fa5cb-132">instanceLockedExceptionAction</span><span class="sxs-lookup"><span data-stu-id="fa5cb-132">instanceLockedExceptionAction</span></span>|<span data-ttu-id="fa5cb-133">호스트에서 인스턴스를 잠그려고 할 때 현재 다른 호스트에서 해당 인스턴스를 잠근 경우에 throw되는 예외에 대한 응답으로 발생하는 동작을 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-133">A value that specifies the action that occurs in response to an exception that is thrown when the host tries to lock an instance because the instance is currently locked by another host.</span></span> <span data-ttu-id="fa5cb-134">이 값은 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-134">This value is of type <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>.</span></span><br /><br /> <span data-ttu-id="fa5cb-135">이 필드에 사용할 수 있는 옵션은 None, Basic Retry 및 Aggressive Retry입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-135">The options allowed for this field are: None, Basic Retry, and Aggressive Retry.</span></span> <span data-ttu-id="fa5cb-136">기본값은 None입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-136">The default value is None.</span></span> <span data-ttu-id="fa5cb-137">다음은 이러한 세 옵션에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-137">The following list provides you with the descriptions for these three options:</span></span><br /><br /> <span data-ttu-id="fa5cb-138">- 없음</span><span class="sxs-lookup"><span data-stu-id="fa5cb-138">-   None.</span></span> <span data-ttu-id="fa5cb-139">서비스 호스트가 인스턴스 잠금을 시도하지 않고 <xref:System.Runtime.DurableInstancing.InstanceLockedException>을 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-139">The service host does not attempt to lock the instance and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller.</span></span><br /><span data-ttu-id="fa5cb-140">-기본 다시 시도.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-140">-   Basic Retry.</span></span> <span data-ttu-id="fa5cb-141">서비스 호스트가 선형 다시 시도 간격을 사용하여 인스턴스 잠금을 다시 시도하고 시퀀스의 끝에 예외를 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-141">The service host reattempts to lock the instance with a linear retry interval and passes the exception to the caller at the end of the sequence.</span></span><br /><span data-ttu-id="fa5cb-142">-적극적인 다시 시도.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-142">-   Aggressive Retry.</span></span> <span data-ttu-id="fa5cb-143">서비스 호스트에서 지연 간격을 기하급수적으로 증가시켜 인스턴스 잠금을 다시 시도하고 시퀀스 마지막에 <xref:System.Runtime.DurableInstancing.InstanceLockedException>을 호출자에게 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-143">The service host reattempts to lock the instance with an exponentially increasing delay and passes the <xref:System.Runtime.DurableInstancing.InstanceLockedException> to the caller at the end of the sequence.</span></span>|  
|<span data-ttu-id="fa5cb-144">runnableInstancesDetectionPeriod</span><span class="sxs-lookup"><span data-stu-id="fa5cb-144">runnableInstancesDetectionPeriod</span></span>||  
  
### <a name="child-elements"></a><span data-ttu-id="fa5cb-145">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fa5cb-145">Child Elements</span></span>  

 <span data-ttu-id="fa5cb-146">없음</span><span class="sxs-lookup"><span data-stu-id="fa5cb-146">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa5cb-147">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fa5cb-147">Parent Elements</span></span>  
  
|<span data-ttu-id="fa5cb-148">요소</span><span class="sxs-lookup"><span data-stu-id="fa5cb-148">Element</span></span>|<span data-ttu-id="fa5cb-149">설명</span><span class="sxs-lookup"><span data-stu-id="fa5cb-149">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa5cb-150">\<serviceBehaviors>의 \<behavior></span><span class="sxs-lookup"><span data-stu-id="fa5cb-150">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="fa5cb-151">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa5cb-151">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa5cb-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa5cb-152">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>
- <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>
- <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>
- [<span data-ttu-id="fa5cb-153">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="fa5cb-153">SQL Workflow Instance Store</span></span>](../../../windows-workflow-foundation/sql-workflow-instance-store.md)
