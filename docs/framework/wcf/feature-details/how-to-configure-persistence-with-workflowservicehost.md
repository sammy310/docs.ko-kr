---
description: '자세한 정보: 방법: WorkflowServiceHost를 사용 하 여 지 속성 구성'
title: '방법: WorkflowServiceHost를 사용하여 지속성 구성'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 79945fb791cc25bdf362302fa884636942fb5692
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780039"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="d4db4-103">방법: WorkflowServiceHost를 사용하여 지속성 구성</span><span class="sxs-lookup"><span data-stu-id="d4db4-103">How to: Configure Persistence with WorkflowServiceHost</span></span>

<span data-ttu-id="d4db4-104">이 항목에서는 구성 파일을 사용하여 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트된 워크플로에 대해 지속성을 사용하도록 SQL 워크플로 인스턴스 저장소 기능을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-104">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="d4db4-105">SQL 워크플로 인스턴스 저장소 기능을 사용하려면 먼저 워크플로 인스턴스를 유지하는 데 사용되는 SQL 데이터베이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-105">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="d4db4-106">자세한 내용은 [방법: 워크플로 및 워크플로 서비스에 SQL 지 속성 사용](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-106">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="d4db4-107">구성에서 SQL 워크플로 인스턴스 저장소를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d4db4-107">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="d4db4-108">SQL 워크플로 인스턴스 저장소의 속성은 XML 구성을 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-108">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="d4db4-109">다음 구성 예제에서는 `sqlWorkflowInstanceStore` 구성 파일의 <> behavior 요소를 사용 하 여 SQL 워크플로 인스턴스 저장소를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-109">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="d4db4-110">SQL 워크플로 인스턴스 저장소를 구성 하는 방법에 대 한 자세한 내용은 [방법: 워크플로 및 워크플로 서비스에 Sql 지 속성 사용](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-110">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="d4db4-111"><> behavior 요소의 개별 설정에 대 한 자세한 내용은 `sqlWorkflowInstanceStore` [SQL 워크플로 인스턴스 저장소](../../windows-workflow-foundation/sql-workflow-instance-store.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-111">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="d4db4-112">Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-112">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="d4db4-113">자세한 내용은 [Windows Server App Fabric 지 속성](/previous-versions/appfabric/ee677272(v=azure.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-113">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d4db4-114">위의 예제에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-114">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="d4db4-115">자세한 내용은 [간소화 된 구성](../simplified-configuration.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-115">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="d4db4-116">코드에서 SQL 워크플로 인스턴스 저장소를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="d4db4-116">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="d4db4-117">SQL 워크플로 인스턴스 저장소의 속성은 코드를 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-117">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="d4db4-118">다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작 요소를 사용하여 SQL 워크플로 인스턴스 저장소를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-118">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="d4db4-119">SQL 워크플로 인스턴스 저장소를 구성 하는 방법에 대 한 자세한 내용은 [방법: 워크플로 및 워크플로 서비스에 Sql 지 속성 사용](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-119">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="d4db4-120">동작 요소의 개별 설정에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> [SQL 워크플로 인스턴스 저장소](../../windows-workflow-foundation/sql-workflow-instance-store.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-120">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="d4db4-121">Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-121">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="d4db4-122">자세한 내용은 [Windows Server App Fabric 지 속성](/previous-versions/appfabric/ee677272(v=azure.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-122">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d4db4-123">위의 예제에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4db4-123">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="d4db4-124">자세한 내용은 [간소화 된 구성](../simplified-configuration.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-124">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="d4db4-125">지 속성을 프로그래밍 방식으로 구성 하는 방법에 대 한 예제는 [방법: 워크플로 및 워크플로 서비스에 지 속성 사용](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d4db4-125">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4db4-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4db4-126">See also</span></span>

- [<span data-ttu-id="d4db4-127">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="d4db4-127">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="d4db4-128">워크플로 유지</span><span class="sxs-lookup"><span data-stu-id="d4db4-128">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="d4db4-129">[지속성 개념](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d4db4-129">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
