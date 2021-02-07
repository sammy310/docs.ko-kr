---
description: '자세한 정보: 일시 중단 된 인스턴스 관리'
title: 일시 중단된 인스턴스 관리
ms.date: 03/30/2017
ms.assetid: f5ca3faa-ba1f-4857-b92c-d927e4b29598
ms.openlocfilehash: d68dd8b61b6e0e7a618cf05f1df07e58ab75e27f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741733"
---
# <a name="suspended-instance-management"></a><span data-ttu-id="1e93c-103">일시 중단된 인스턴스 관리</span><span class="sxs-lookup"><span data-stu-id="1e93c-103">Suspended Instance Management</span></span>

<span data-ttu-id="1e93c-104">이 샘플에서는 일시 중단된 워크플로 인스턴스를 관리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-104">This sample demonstrates how to manage workflow instances that have been suspended.</span></span>  <span data-ttu-id="1e93c-105"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>의 기본 동작은 `AbandonAndSuspend`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-105">The default action for <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is `AbandonAndSuspend`.</span></span> <span data-ttu-id="1e93c-106">즉, 기본적으로 <xref:System.ServiceModel.WorkflowServiceHost>에서 호스트되는 워크플로 인스턴스에서 처리되지 않은 예외가 throw될 경우 인스턴스가 메모리에서 삭제(중단)되고 영속/지속적 버전의 인스턴스는 일시 중단된 인스턴스로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-106">This means that by default, unhandled exceptions thrown from a workflow instance hosted in the <xref:System.ServiceModel.WorkflowServiceHost> will cause the instance to be disposed from memory (abandoned) and the durable/persisted version of the instance to be marked as suspended.</span></span> <span data-ttu-id="1e93c-107">일시 중단된 워크플로 인스턴스는 일시 중단이 해제될 때까지 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-107">A suspended workflow instance will not be able to run until it has been unsuspended.</span></span>

 <span data-ttu-id="1e93c-108">이 샘플에서는 일시 중단된 인스턴스를 쿼리하는 명령줄 유틸리티를 구현하는 방법과 사용자에게 해당 인스턴스를 다시 시작하거나 종료하는 옵션을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-108">The sample shows how a command-line utility can be implemented to query for suspended instances, and how to give the user the option to resume or terminate the instance.</span></span> <span data-ttu-id="1e93c-109">이 샘플에서는 워크플로 서비스가 의도적으로 예외를 throw하여 일시 중단 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-109">In this sample, a workflow service intentionally throws an exception, causing it to become suspended.</span></span> <span data-ttu-id="1e93c-110">그런 다음 명령줄 유틸리티를 사용하여 인스턴스를 쿼리하고 이후에 인스턴스를 다시 시작하거나 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-110">The command-line utility can then be used to query for the instance and subsequently resume or terminate the instance.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="1e93c-111">데모</span><span class="sxs-lookup"><span data-stu-id="1e93c-111">Demonstrates</span></span>

 <span data-ttu-id="1e93c-112"><xref:System.ServiceModel.WorkflowServiceHost><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> WF (Windows Workflow Foundation)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-112"><xref:System.ServiceModel.WorkflowServiceHost> with <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> and <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> in Windows Workflow Foundation (WF).</span></span>

## <a name="discussion"></a><span data-ttu-id="1e93c-113">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="1e93c-113">Discussion</span></span>

 <span data-ttu-id="1e93c-114">이 샘플에서 구현하는 명령줄 유틸리티는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 제공되는 SQL 인스턴스 저장소 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-114">The command-line utility implemented in this sample is specific to the SQL instance store implementation that ships in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span> <span data-ttu-id="1e93c-115">인스턴스 저장소의 사용자 지정 구현이 있는 경우 샘플의 `WorkflowInstanceCommand` 구현을 현재 인스턴스 저장소와 관련된 구현으로 바꿔 이 유틸리티를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-115">If you have a custom implementation of the instance store, then you can adapt this utility by replacing the `WorkflowInstanceCommand` implementations in the sample with implementations that are specific to your instance store.</span></span>

 <span data-ttu-id="1e93c-116">제공된 구현에서는 SQL 인스턴스 저장소에 대해 직접 SQL 명령을 실행하여 일시 중단된 인스턴스를 나열하고, 인스턴스를 다시 시작하거나 종료하기 위해 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 추가된 <xref:System.ServiceModel.WorkflowServiceHost>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-116">The provided implementation runs SQL commands against the SQL instance store directly to list suspended instances, and it relies on a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> added to the <xref:System.ServiceModel.WorkflowServiceHost> in order to resume or terminate the instances.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1e93c-117">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="1e93c-117">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="1e93c-118">이 샘플에는 다음과 같은 Windows 구성 요소를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-118">This sample requires that the following Windows components are enabled:</span></span>

    1. <span data-ttu-id="1e93c-119">MSMQ(Microsoft Message Queue) Server</span><span class="sxs-lookup"><span data-stu-id="1e93c-119">Microsoft Message Queues (MSMQ) Server</span></span>

    2. <span data-ttu-id="1e93c-120">SQL Server Express</span><span class="sxs-lookup"><span data-stu-id="1e93c-120">SQL Server Express</span></span>

2. <span data-ttu-id="1e93c-121">SQL Server 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-121">Set up the SQL Server database.</span></span>

    1. <span data-ttu-id="1e93c-122">Visual Studio 2010 명령 프롬프트에서 다음을 수행 하는 SuspendedInstanceManagement 샘플 디렉터리에서 "setup.exe"를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-122">From a Visual Studio 2010 command prompt, run "setup.cmd" from the SuspendedInstanceManagement sample directory, which does the following:</span></span>

        1. <span data-ttu-id="1e93c-123">SQL Server Express를 사용하여 지속성 데이터베이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-123">Creates a persistence database using SQL Server Express.</span></span> <span data-ttu-id="1e93c-124">지속성 데이터베이스가 이미 있으면 삭제된 다음 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-124">If the persistence database already exists, then it is dropped and re-created</span></span>

        2. <span data-ttu-id="1e93c-125">지속성 데이터베이스를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-125">Sets up the database for persistence.</span></span>

        3. <span data-ttu-id="1e93c-126">지속성 데이터베이스를 설정할 때 정의된 InstanceStoreUsers 역할에 IIS APPPOOL\DefaultAppPool 및 NT AUTHORITY\Network Service를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-126">Adds IIS APPPOOL\DefaultAppPool and NT AUTHORITY\Network Service to the InstanceStoreUsers role that was defined when setting up the database for persistence.</span></span>

3. <span data-ttu-id="1e93c-127">서비스 큐를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-127">Set up the service queue.</span></span>

    1. <span data-ttu-id="1e93c-128">Visual Studio 2010에서 **SampleWorkflowApp** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트로 설정** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-128">In Visual Studio 2010, right-click the **SampleWorkflowApp** project and click **Set as Startup Project**.</span></span>

    2. <span data-ttu-id="1e93c-129">**F5** 키를 눌러 SampleWorkflowApp를 컴파일하고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-129">Compile and run the SampleWorkflowApp by pressing **F5**.</span></span> <span data-ttu-id="1e93c-130">이렇게 하면 필요한 큐가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-130">This will create the required queue.</span></span>

    3. <span data-ttu-id="1e93c-131">**Enter** 키를 눌러 SampleWorkflowApp을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-131">Press **Enter** to stop the SampleWorkflowApp.</span></span>

    4. <span data-ttu-id="1e93c-132">명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-132">Open the Computer Management console by running Compmgmt.msc from a command prompt.</span></span>

    5. <span data-ttu-id="1e93c-133">**서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐** 를 차례로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-133">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

    6. <span data-ttu-id="1e93c-134">**ReceiveTx** 큐를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-134">Right click the **ReceiveTx** queue and select **Properties**.</span></span>

    7. <span data-ttu-id="1e93c-135">**보안** 탭을 선택 하 고 **모든 사용자** 가 메시지를 **받고** **, 메시지를 읽고,** **메시지를 보낼** 수 있는 권한을 갖도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-135">Select the **Security** tab and allow **Everyone** to have permissions to **Receive Message**, **Peek Message**, and **Send Message**.</span></span>

4. <span data-ttu-id="1e93c-136">이제 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-136">Now, run the sample.</span></span>

    1. <span data-ttu-id="1e93c-137">Visual Studio 2010에서 **Ctrl + F5** 를 눌러 디버깅 하지 않고 SampleWorkflowApp 프로젝트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-137">In Visual Studio 2010, run the SampleWorkflowApp project again without debugging by pressing **Ctrl+F5**.</span></span> <span data-ttu-id="1e93c-138">두 엔드포인트 주소가 콘솔 창에 출력됩니다. 이 주소 중 하나를 애플리케이션 엔드포인트에 대한 주소이고, 다른 하나는 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-138">Two endpoint addresses will be printed in the console window: one for the application endpoint and then other from the <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>.</span></span> <span data-ttu-id="1e93c-139">그런 다음 워크플로 인스턴스가 만들어지고, 해당 인스턴스에 대한 추적 레코드가 콘솔 창에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-139">A workflow instance is then created, and tracking records for that instance will appear in the console window.</span></span> <span data-ttu-id="1e93c-140">워크플로 인스턴스를 예외를 throw하며, 인스턴스가 일시 중단되고 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-140">The workflow instance will throw an exception causing the instance to be suspended and aborted.</span></span>

    2. <span data-ttu-id="1e93c-141">명령줄 유틸리티를 사용하여 모든 인스턴스에 대해 추가 동작을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-141">The command-line utility can then be used to take further action on any of these instances.</span></span> <span data-ttu-id="1e93c-142">명령줄 인수에 대한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-142">The syntax for command line arguments is as follows::</span></span>

         `SuspendedInstanceManagement -Command:[CommandName] -Server:[ServerName] -Database:[DatabaseName] -InstanceId:[InstanceId]`

         <span data-ttu-id="1e93c-143">지원되는 명령은 `Query`, `Resume` 및 `Terminate`이며,</span><span class="sxs-lookup"><span data-stu-id="1e93c-143">The supported commands are: `Query`, `Resume`, and `Terminate`.</span></span>  <span data-ttu-id="1e93c-144">InstanceId 스위치는 `Resume` 및 `Terminate` 작업에만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-144">The InstanceId switch is only required for `Resume` and `Terminate` operations.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="1e93c-145">정리하려면(옵션)</span><span class="sxs-lookup"><span data-stu-id="1e93c-145">To cleanup (Optional)</span></span>

1. <span data-ttu-id="1e93c-146">`vs2010` 명령 프롬프트에서 Compmgmt.msc를 실행하여 컴퓨터 관리 콘솔을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-146">Open the Computer Management console by running Compmgmt.msc from a `vs2010` command prompt.</span></span>

2. <span data-ttu-id="1e93c-147">**서비스 및 응용 프로그램**, **메시지 큐**, **개인 큐** 를 차례로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-147">Expand **Service and Applications**, **Message Queuing**, **Private Queues**.</span></span>

3. <span data-ttu-id="1e93c-148">**ReceiveTx** 큐를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-148">Delete the **ReceiveTx** queue.</span></span>

4. <span data-ttu-id="1e93c-149">지속성 데이터베이스를 제거하려면 cleanup.cmd를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-149">To remove the persistence database, run cleanup.cmd.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e93c-150">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-150">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e93c-151">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1e93c-151">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1e93c-152">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-152">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e93c-153">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e93c-153">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Application\SuspendedInstanceManagement`
