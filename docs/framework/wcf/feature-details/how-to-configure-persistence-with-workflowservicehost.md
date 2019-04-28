---
title: '방법: WorkflowServiceHost를 사용하여 지속성 구성'
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: b8839f42a9b8b5f4da0a1a8364c7eac5a4c06d4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699775"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="934f2-102">방법: WorkflowServiceHost를 사용하여 지속성 구성</span><span class="sxs-lookup"><span data-stu-id="934f2-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="934f2-103">이 항목에서는 구성 파일을 사용하여 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에 호스트된 워크플로에 대해 지속성을 사용하도록 SQL 워크플로 인스턴스 저장소 기능을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="934f2-104">SQL 워크플로 인스턴스 저장소 기능을 사용하려면 먼저 워크플로 인스턴스를 유지하는 데 사용되는 SQL 데이터베이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="934f2-105">자세한 내용은 [방법: 워크플로 및 워크플로 서비스에 대 한 SQL 지 속성 사용](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="934f2-106">구성에서 SQL 워크플로 인스턴스 저장소를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="934f2-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="934f2-107">SQL 워크플로 인스턴스 저장소의 속성은 XML 구성을 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="934f2-108">다음 구성 예제에 사용 하 여 SQL 워크플로 인스턴스 저장소를 구성 하는 방법을 보여 줍니다는 <`sqlWorkflowInstanceStore`> 구성 파일에서 동작 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
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
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="934f2-109">SQL 워크플로 인스턴스 저장소를 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 워크플로 및 워크플로 서비스에 대 한 SQL 지 속성 사용](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="934f2-110">개별 설정에 대 한 자세한 내용은 <`sqlWorkflowInstanceStore`> 동작 요소를 참조 하세요 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="934f2-111">Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="934f2-112">자세한 내용은 [Windows Server App Fabric 지 속성](https://go.microsoft.com/fwlink/?LinkId=193121)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-112">For more information, see [Windows Server App Fabric Persistence](https://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="934f2-113">위의 예제에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="934f2-114">자세한 내용은 참조 하세요. [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="934f2-114">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="934f2-115">코드에서 SQL 워크플로 인스턴스 저장소를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="934f2-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="934f2-116">SQL 워크플로 인스턴스 저장소의 속성은 코드를 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="934f2-117">다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작 요소를 사용하여 SQL 워크플로 인스턴스 저장소를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
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
  
     <span data-ttu-id="934f2-118">SQL 워크플로 인스턴스 저장소를 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 워크플로 및 워크플로 서비스에 대 한 SQL 지 속성 사용](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="934f2-119">개별 설정에 대 한 자세한 합니다 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작 요소를 참조 하세요 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="934f2-120">Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="934f2-121">자세한 내용은 [Windows Server App Fabric 지 속성](https://go.microsoft.com/fwlink/?LinkId=193121)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-121">For more information, see [Windows Server App Fabric Persistence](https://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="934f2-122">위의 예제에서 사용하는 구성은 단순화된 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="934f2-123">자세한 내용은 참조 하세요. [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="934f2-123">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="934f2-124">지 속성을 프로그래밍 방식으로 구성 하는 방법의 예제를 참조 하세요. [방법: 워크플로 및 워크플로 서비스에 대 한 지](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="934f2-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934f2-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="934f2-125">See also</span></span>

- [<span data-ttu-id="934f2-126">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="934f2-126">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="934f2-127">워크플로 유지</span><span class="sxs-lookup"><span data-stu-id="934f2-127">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)
- [<span data-ttu-id="934f2-128">Windows Server App Fabric 지 속성</span><span class="sxs-lookup"><span data-stu-id="934f2-128">Windows Server App Fabric Persistence</span></span>](https://go.microsoft.com/fwlink/?LinkId=193121)
