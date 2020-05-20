---
title: 워크플로 유지
description: .NET Framework 4.6.1에는 SQL Server 데이터베이스에 대 한 워크플로 데이터 및 메타 데이터의 지 속성을 허용 하는 SqlWorkflowInstanceStore 클래스가 포함 됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
ms.openlocfilehash: 1178bd3800fce95be96e601a17bfeff2c05cfceb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419306"
---
# <a name="workflow-persistence"></a><span data-ttu-id="35f16-103">워크플로 유지</span><span class="sxs-lookup"><span data-stu-id="35f16-103">Workflow Persistence</span></span>
<span data-ttu-id="35f16-104">워크플로 지속성은 프로세스 또는 컴퓨터 정보에 독립적인 영구 워크플로 인스턴스 상태 캡처입니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-104">Workflow persistence is the durable capture of a workflow instance's state, independent of process or computer information.</span></span> <span data-ttu-id="35f16-105">이 작업은 시스템 오류가 발생한 경우에 워크플로 인스턴스에 대한 잘 알려진 복구 지점을 제공하거나, 현재 작업 중이 아닌 워크플로 인스턴스를 언로드하여 메모리를 보존하거나, 워크플로 인스턴스의 상태를 서버 팜의 한 노드에서 다른 노드로 이동하기 위해 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-105">This is done to provide a well-known point of recovery for the workflow instance in the event of system failure, or to preserve memory by unloading workflow instances that are not actively doing work, or to move the state of the workflow instance from one node to another node in a server farm.</span></span>  
  
 <span data-ttu-id="35f16-106">지속성은 프로세스의 신속성, 확장성, 오류 복구, 효율적인 메모리 관리를 가능하게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-106">Persistence enables process agility, scalability, recovery in the face of failure, and the ability to manage memory more efficiently.</span></span> <span data-ttu-id="35f16-107">지속성 프로세스는 유지 지점을 식별하고, 저장할 데이터를 수집하며, 마지막으로 지속성 공급자에게 실제 데이터 스토리지를 위임하는 과정으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-107">The persistence process includes the identification of a persistence point, the gathering of the data to be saved, and finally the delegation of the actual storage of the data to a persistence provider.</span></span>  
  
 <span data-ttu-id="35f16-108">워크플로에 지 속성을 사용 하도록 설정 하려면 [방법: 워크플로 및 워크플로 서비스에 지 속성 사용](how-to-enable-persistence-for-workflows-and-workflow-services.md)에서 설명한 대로 인스턴스 저장소를 **WorkflowApplication** 또는 **WorkflowServiceHost** 와 연결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-108">To enable persistence for a workflow, you need to associate an instance store with the **WorkflowApplication** or **WorkflowServiceHost** as mentioned in [How to: Enable Persistence for Workflows and Workflow Services](how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="35f16-109">**WorkflowApplication** 및 **WorkflowServiceHost** 는 연결 된 인스턴스 저장소를 사용 하 여 워크플로 인스턴스를 지 속성 저장소에 유지 하 고 지 속성 저장소에 저장 된 워크플로 인스턴스 데이터를 기반으로 워크플로 인스턴스를 메모리에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-109">The **WorkflowApplication** and **WorkflowServiceHost** use the instance store associated with them to enable persisting workflow instances into a persistence store and loading workflow instances into memory based on the workflow instance data stored in the persistence store.</span></span>  
  
 <span data-ttu-id="35f16-110">에는 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] SQL Server 2005 또는 SQL Server 2008 데이터베이스로 워크플로 인스턴스에 대 한 데이터 및 메타 데이터의 지 속성을 허용 하는 **SqlWorkflowInstanceStore** 클래스가 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-110">The [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] ships with the **SqlWorkflowInstanceStore** class, which allows persistence of data and metadata about workflow instances into a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="35f16-111">자세한 내용은 [SQL 워크플로 인스턴스 저장소](sql-workflow-instance-store.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35f16-111">See [SQL Workflow Instance Store](sql-workflow-instance-store.md) for more details.</span></span>  
  
 <span data-ttu-id="35f16-112">워크플로 인스턴스 관련 정보와 함께 애플리케이션별 데이터를 저장하고 로드하려면 <xref:System.Activities.Persistence.PersistenceParticipant> 클래스를 확장하는 지속성 참석자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-112">To store and load your application-specific data along with the workflow instance-related information, you can create persistence participants that extend the <xref:System.Activities.Persistence.PersistenceParticipant> class.</span></span> <span data-ttu-id="35f16-113">지속성 참석자는 지속성 프로세스에 참여하여 serialize 가능한 사용자 지정 데이터를 지속성 저장소에 저장하고, 인스턴스 저장소의 데이터를 메모리로 로드하며, 지속성 트랜잭션에서 추가 논리를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-113">A persistence participant participates in the persistence process to save custom serializable data into the persistence store, to load the data from the instance store into memory, and to perform any additional logic under a persistence transaction.</span></span> <span data-ttu-id="35f16-114">자세한 내용은 [지 속성 참가자](persistence-participants.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35f16-114">For more information, see [Persistence Participants](persistence-participants.md).</span></span>  
  
 <span data-ttu-id="35f16-115">Windows Server AppFabric은 지속성의 구성 프로세스를 단순화합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-115">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="35f16-116">자세한 내용은 [Windows Server App Fabric의 지 속성 개념](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35f16-116">For more information, see [Persistence Concepts with Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10))</span></span>  
  
## <a name="implicit-persistence-points"></a><span data-ttu-id="35f16-117">암시적 유지 지점</span><span class="sxs-lookup"><span data-stu-id="35f16-117">Implicit Persistence Points</span></span>  
 <span data-ttu-id="35f16-118">다음 목록에는 인스턴스 저장소가 워크플로에 연결되어 있을 때 워크플로가 유지되는 조건에 대한 예제가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-118">The following list contains examples of the conditions upon which a workflow is persisted when an instance store is associated with a workflow.</span></span>  
  
- <span data-ttu-id="35f16-119">**TransactionScope** 활동이 완료 되거나 **TransactedReceiveScope** 활동이 완료 될 때</span><span class="sxs-lookup"><span data-stu-id="35f16-119">When a **TransactionScope** activity completes or a **TransactedReceiveScope** activity completes.</span></span>  
  
- <span data-ttu-id="35f16-120">워크플로 인스턴스가 유휴 상태가 되 고 워크플로 호스트에 **WorkflowIdleBehavior** 가 설정 된 경우</span><span class="sxs-lookup"><span data-stu-id="35f16-120">When a workflow instance becomes idle and the **WorkflowIdleBehavior** is set on workflow host.</span></span> <span data-ttu-id="35f16-121">예를 들어 메시징 활동 또는 **지연** 활동을 사용 하는 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-121">This occurs, for example, when you use messaging activities or a **Delay** activity.</span></span>  
  
- <span data-ttu-id="35f16-122">WorkflowApplication이 유휴 상태가 되 고 응용 프로그램의 **Persistableidle** 속성이 **PersistableIdleAction**로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-122">When a WorkflowApplication becomes idle and the **PersistableIdle** property of the application is set to **PersistableIdleAction.Persist**.</span></span>  
  
- <span data-ttu-id="35f16-123">워크플로 인스턴스를 유지하거나 언로드하도록 호스트 애플리케이션에 지시할 경우</span><span class="sxs-lookup"><span data-stu-id="35f16-123">When a host application is instructed to persist or unload a workflow instance.</span></span>  
  
- <span data-ttu-id="35f16-124">워크플로 인스턴스가 종료되거나 완료되는 경우</span><span class="sxs-lookup"><span data-stu-id="35f16-124">When a workflow instance is terminated or finishes.</span></span>  
  
- <span data-ttu-id="35f16-125">**지속** 작업이 실행 될 때.</span><span class="sxs-lookup"><span data-stu-id="35f16-125">When a **Persist** activity executes.</span></span>  
  
- <span data-ttu-id="35f16-126">이전 버전의 Windows Workflow Foundation을 사용하여 개발된 워크플로 인스턴스에서 상호 운용 가능한 방식으로 실행되는 동안 유지 지점을 발견한 경우</span><span class="sxs-lookup"><span data-stu-id="35f16-126">When an instance of a workflow developed using a previous version of Windows Workflow Foundation encounters a persistence point during interoperable execution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35f16-127">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="35f16-127">In This Section</span></span>  
  
- [<span data-ttu-id="35f16-128">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="35f16-128">SQL Workflow Instance Store</span></span>](sql-workflow-instance-store.md)  
  
- [<span data-ttu-id="35f16-129">인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="35f16-129">Instance Stores</span></span>](instance-stores.md)  
  
- [<span data-ttu-id="35f16-130">지속성 참석자</span><span class="sxs-lookup"><span data-stu-id="35f16-130">Persistence Participants</span></span>](persistence-participants.md)  
  
- [<span data-ttu-id="35f16-131">지속성 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="35f16-131">Persistence Best Practices</span></span>](persistence-best-practices.md)  
  
- [<span data-ttu-id="35f16-132">비지속형 워크플로 인스턴스</span><span class="sxs-lookup"><span data-stu-id="35f16-132">Non-Persisted Workflow Instances</span></span>](non-persisted-workflow-instances.md)  
  
- [<span data-ttu-id="35f16-133">워크플로 일시 중지 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="35f16-133">Pausing and Resuming a Workflow</span></span>](pausing-and-resuming-a-workflow.md)
