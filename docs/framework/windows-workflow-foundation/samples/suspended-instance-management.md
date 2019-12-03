---
title: 일시 중단된 인스턴스 관리
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: 3f1f4f8edcbe0e05067d3ca739ef3d5f4fe4d798
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715939"
---
# <a name="suspended-instance-management"></a><span data-ttu-id="e5c8b-102">일시 중단된 인스턴스 관리</span><span class="sxs-lookup"><span data-stu-id="e5c8b-102">Suspended Instance Management</span></span>
<span data-ttu-id="e5c8b-103">이 샘플에서는 일시 중단된 워크플로 인스턴스를 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-103">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="e5c8b-104"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>의 기본 동작은 `AbandonAndSuspend`입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-104">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="e5c8b-105">즉, 기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스트되는 워크플로 인스턴스에서 처리되지 않은 예외가 throw될 경우 인스턴스가 메모리에서 삭제(중단)되고 영속/지속적 버전의 인스턴스는 일시 중단된 인스턴스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-105">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="e5c8b-106">일시 중단된 워크플로 인스턴스는 일시 중단이 해제될 때까지 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-106">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>

 <span data-ttu-id="e5c8b-107">이 샘플에서는 일시 중단된 인스턴스를 쿼리하는 명령줄 유틸리티를 구현하는 방법과 사용자에게 해당 인스턴스를 다시 시작하거나 종료하는 옵션을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-107">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="e5c8b-108">이 샘플에서는 워크플로 서비스가 의도적으로 예외를 throw하여 일시 중단 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-108">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="e5c8b-109">그런 다음 명령줄 유틸리티를 사용하여 인스턴스를 쿼리하고 이후에 인스턴스를 다시 시작하거나 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-109">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="e5c8b-110">데모</span><span class="sxs-lookup"><span data-stu-id="e5c8b-110">Demonstrates</span></span>
 <span data-ttu-id="e5c8b-111">WF (Windows Workflow Foundation)의 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> 및 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>를 사용 하 여 <xref:System.ServiceModel.WorkflowServiceHost> 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-111"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>

## <a name="discussion"></a><span data-ttu-id="e5c8b-112">토론</span><span class="sxs-lookup"><span data-stu-id="e5c8b-112">Discussion</span></span>
 <span data-ttu-id="e5c8b-113">이 샘플에서 구현하는 명령줄 유틸리티는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 제공되는 SQL 인스턴스 저장소 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-113">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="e5c8b-114">인스턴스 저장소의 사용자 지정 구현이 있는 경우 샘플의 `WorkflowInstanceCommand` 구현을 현재 인스턴스 저장소와 관련된 구현으로 바꿔 이 유틸리티를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-114">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>

 <span data-ttu-id="e5c8b-115">제공된 구현에서는 SQL 인스턴스 저장소에 대해 직접 SQL 명령을 실행하여 일시 중단된 인스턴스를 나열하고, 인스턴스를 다시 시작하거나 종료하기 위해 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 추가된 <xref:System.ServiceModel.WorkflowServiceHost>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-115">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e5c8b-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="e5c8b-116">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="e5c8b-117">이 샘플에는 다음과 같은 Windows 구성 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-117">This sample requires that the following Windows components are enabled:</span></span>

    1. <span data-ttu-id="e5c8b-118">MSMQ(Microsoft Message Queue) Server</span><span class="sxs-lookup"><span data-stu-id="e5c8b-118">Microsoft Message Queues (MSMQ) Server</span></span>

    2. <span data-ttu-id="e5c8b-119">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="e5c8b-119">SQL Server Express</span></span>

2. <span data-ttu-id="e5c8b-120">SQL Server 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-120">Set up the SQL Server database.</span></span>

    1. <span data-ttu-id="e5c8b-121">Visual Studio 2010 명령 프롬프트에서 다음을 수행 하는 SuspendedInstanceManagement 샘플 디렉터리에서 "setup.exe"를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-121">From a Visual Studio 2010 command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>

        1. <span data-ttu-id="e5c8b-122">SQL Server Express를 사용하여 지속성 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-122">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="e5c8b-123">지속성 데이터베이스가 이미 있으면 삭제된 다음 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-123">If the persistence database already exists, then it is dropped and re-created</span></span>

        2. <span data-ttu-id="e5c8b-124">지속성 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-124">Sets up the database for persistence.</span></span>

        3. <span data-ttu-id="e5c8b-125">지속성 데이터베이스를 설정할 때 정의된 InstanceStoreUsers 역할에 IIS APPPOOL\DefaultAppPool 및 NT AUTHORITY\Network Service를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-125">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>

3. <span data-ttu-id="e5c8b-126">서비스 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-126">Set up the service queue.</span></span>

    1. <span data-ttu-id="e5c8b-127">Visual Studio 2010에서 **SampleWorkflowApp** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-127">In Visual Studio 2010, right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>

    2. <span data-ttu-id="e5c8b-128">**F5**키를 눌러 SampleWorkflowApp를 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-128">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="e5c8b-129">이렇게 하면 필요한 큐가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-129">This will create the required queue.</span></span>

    3. <span data-ttu-id="e5c8b-130">**Enter** 키를 눌러 SampleWorkflowApp을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-130">Press **Enter** to stop the SampleWorkflowApp.</span></span>

    4. <span data-ttu-id="e5c8b-131">명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-131">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>

    5. <span data-ttu-id="e5c8b-132">**서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐**를 차례로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-132">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

    6. <span data-ttu-id="e5c8b-133">**ReceiveTx** 큐를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-133">Right click the **ReceiveTx** queue and select **Properties**.</span></span>

    7. <span data-ttu-id="e5c8b-134">**보안** 탭을 선택 하 고 **모든 사용자** 가 메시지를 **받고** **, 메시지를 읽고,** **메시지를 보낼**수 있는 권한을 갖도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-134">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>

4. <span data-ttu-id="e5c8b-135">이제 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-135">Now, run the sample.</span></span>

    1. <span data-ttu-id="e5c8b-136">Visual Studio 2010에서 **Ctrl + F5**를 눌러 디버깅 하지 않고 SampleWorkflowApp 프로젝트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-136">In Visual Studio 2010, run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="e5c8b-137">두 엔드포인트 주소가 콘솔 창에 출력됩니다. 이 주소 중 하나를 애플리케이션 엔드포인트에 대한 주소이고, 다른 하나는 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-137">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="e5c8b-138">그런 다음 워크플로 인스턴스가 만들어지고, 해당 인스턴스에 대한 추적 레코드가 콘솔 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-138">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="e5c8b-139">워크플로 인스턴스를 예외를 throw하며, 인스턴스가 일시 중단되고 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-139">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>

    2. <span data-ttu-id="e5c8b-140">명령줄 유틸리티를 사용하여 모든 인스턴스에 대해 추가 동작을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-140">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="e5c8b-141">명령줄 인수에 대한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-141">The syntax for command line arguments is as follows::</span></span>

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         <span data-ttu-id="e5c8b-142">지원되는 명령은 `Query`, `Resume` 및 `Terminate`이며,</span><span class="sxs-lookup"><span data-stu-id="e5c8b-142">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="e5c8b-143">InstanceId 스위치는 `Resume` 및 `Terminate` 작업에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-143">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="e5c8b-144">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="e5c8b-144">To cleanup (Optional)</span></span>

1. <span data-ttu-id="e5c8b-145">`vs2010` 명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-145">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>

2. <span data-ttu-id="e5c8b-146">**서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐**를 차례로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-146">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

3. <span data-ttu-id="e5c8b-147">**ReceiveTx** 큐를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-147">Delete the **ReceiveTx** queue.</span></span>

4. <span data-ttu-id="e5c8b-148">지속성 데이터베이스를 제거하려면 cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-148">To remove the persistence database, run cleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5c8b-149">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-149">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e5c8b-150">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-150">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="e5c8b-151">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-151">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e5c8b-152">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5c8b-152">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
