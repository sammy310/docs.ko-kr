---
description: '자세한 정보: 트랜잭션 흐름 및 워크플로 서비스에서 트랜잭션 이동'
title: 트랜잭션을 워크플로 서비스 내부 및 외부로 이동
ms.date: 03/30/2017
ms.assetid: 03ced70e-b540-4dd9-86c8-87f7bd61f609
ms.openlocfilehash: f39740c45dd70fbc06963b8e842f9a01a0393f7e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704968"
---
# <a name="flowing-transactions-into-and-out-of-workflow-services"></a><span data-ttu-id="6a938-103">트랜잭션을 워크플로 서비스 내부 및 외부로 이동</span><span class="sxs-lookup"><span data-stu-id="6a938-103">Flowing Transactions into and out of Workflow Services</span></span>

<span data-ttu-id="6a938-104">워크플로 서비스 및 클라이언트는 트랜잭션에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-104">Workflow services and clients can participate in transactions.</span></span>  <span data-ttu-id="6a938-105">서비스 작업이 앰비언트 트랜잭션의 일부가 되도록 하려면 <xref:System.ServiceModel.Activities.Receive> 활동 내에 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-105">For a service operation to become part of an ambient transaction, place a <xref:System.ServiceModel.Activities.Receive> activity within a <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="6a938-106"><xref:System.ServiceModel.Activities.Send> 내의 <xref:System.ServiceModel.Activities.SendReply> 또는 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동에서 실행하는 모든 호출은 앰비언트 트랜잭션 내에서도 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-106">Any calls made by a <xref:System.ServiceModel.Activities.Send> or a <xref:System.ServiceModel.Activities.SendReply> activity within the <xref:System.ServiceModel.Activities.TransactedReceiveScope> will also be made within the ambient transaction.</span></span> <span data-ttu-id="6a938-107">워크플로 클라이언트 애플리케이션에서는 <xref:System.Activities.Statements.TransactionScope> 활동을 사용하여 앰비언트 트랜잭션을 만들고 앰비언트 트랜잭션을 사용하여 서비스 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-107">A workflow client application can create an ambient transaction by using the <xref:System.Activities.Statements.TransactionScope> activity and call service operations using the ambient transaction.</span></span> <span data-ttu-id="6a938-108">이 항목에서는 트랜잭션에 참여하는 워크플로 서비스와 워크플로 클라이언트를 만드는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-108">This topic walks you through creating a workflow service and workflow client that participate in transactions.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="6a938-109">워크플로 서비스 인스턴스가 트랜잭션 내에서 로드 되 고 워크플로에 작업이 포함 된 경우 <xref:System.Activities.Statements.Persist> 워크플로 인스턴스는 해당 트랜잭션이 시간 초과 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-109">If a workflow service instance is loaded within a transaction and the workflow contains a <xref:System.Activities.Statements.Persist> activity, the workflow instance will block until the transaction times out.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6a938-110"><xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용할 때마다 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 활동 내에 워크플로의 모든 Receive를 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-110">Whenever you use a <xref:System.ServiceModel.Activities.TransactedReceiveScope> it is recommended to place all Receives in the workflow within <xref:System.ServiceModel.Activities.TransactedReceiveScope> activities.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6a938-111"><xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용할 때 메시지가 잘못된 순서로 도착하는 경우 워크플로가 순서가 잘못된 첫 번째 메시지를 전달하려고 할 때 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-111">When using <xref:System.ServiceModel.Activities.TransactedReceiveScope> and messages arrive in the incorrect order, the workflow will be aborted when trying to deliver the first out of order message.</span></span> <span data-ttu-id="6a938-112">워크플로가 유휴 상태일 때 항상 일관된 중지 지점에 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-112">You must make sure your workflow is always at a consistent stopping point when the workflow idles.</span></span> <span data-ttu-id="6a938-113">이렇게 하면 워크플로가 중단된 경우 이전 유지 지점에서 워크플로를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-113">This will allow you to restart the workflow from a previous persistence point should the workflow be aborted.</span></span>  
  
### <a name="create-a-shared-library"></a><span data-ttu-id="6a938-114">공유 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="6a938-114">Create a shared library</span></span>  
  
1. <span data-ttu-id="6a938-115">비어 있는 새 Visual Studio 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-115">Create a new empty Visual Studio Solution.</span></span>  
  
2. <span data-ttu-id="6a938-116">`Common`이라는 새 클래스 라이브러리 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="6a938-116">Add a new class library project called `Common`.</span></span> <span data-ttu-id="6a938-117">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-117">Add references to the following assemblies:</span></span>  
  
    - <span data-ttu-id="6a938-118">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-118">System.Activities.dll</span></span>  
  
    - <span data-ttu-id="6a938-119">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-119">System.ServiceModel.dll</span></span>  
  
    - <span data-ttu-id="6a938-120">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-120">System.ServiceModel.Activities.dll</span></span>  
  
    - <span data-ttu-id="6a938-121">System.Transactions.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-121">System.Transactions.dll</span></span>  
  
3. <span data-ttu-id="6a938-122">`PrintTransactionInfo` 프로젝트에 `Common`라는 새 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-122">Add a new class called `PrintTransactionInfo` to the `Common` project.</span></span> <span data-ttu-id="6a938-123">이 클래스는 <xref:System.Activities.NativeActivity>에서 파생되며 <xref:System.Activities.NativeActivity.Execute%2A> 메서드를 오버로드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-123">This class is derived from <xref:System.Activities.NativeActivity> and overloads the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>  
  
    ```csharp
    using System;  
    using System;  
    using System.Activities;  
    using System.Transactions;  
  
    namespace Common  
    {  
        public class PrintTransactionInfo : NativeActivity  
        {  
            protected override void Execute(NativeActivityContext context)  
            {  
                RuntimeTransactionHandle rth = context.Properties.Find(typeof(RuntimeTransactionHandle).FullName) as RuntimeTransactionHandle;  
  
                if (rth == null)  
                {  
                    Console.WriteLine("There is no ambient RuntimeTransactionHandle");  
                }  
  
                Transaction t = rth.GetCurrentTransaction(context);  
  
                if (t == null)  
                {  
                    Console.WriteLine("There is no ambient transaction");  
                }  
                else  
                {  
                    Console.WriteLine("Transaction: {0} is {1}", t.TransactionInformation.DistributedIdentifier, t.TransactionInformation.Status);  
                }  
            }  
        }  
  
    }  
    ```  
  
     <span data-ttu-id="6a938-124">이는 앰비언트 트랜잭션에 대한 정보를 표시하는 기본 활동으로서, 이 항목에 사용되는 서비스 및 클라이언트 워크플로 모두에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-124">This is a native activity that displays information about the ambient transaction and is used in both the service and client workflows used in this topic.</span></span> <span data-ttu-id="6a938-125">**도구 상자** 의 **일반** 섹션에서이 작업을 사용할 수 있도록 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-125">Build the solution to make this activity available in the **Common** section of the **Toolbox**.</span></span>  
  
### <a name="implement-the-workflow-service"></a><span data-ttu-id="6a938-126">워크플로 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="6a938-126">Implement the workflow service</span></span>  
  
1. <span data-ttu-id="6a938-127">프로젝트에 라는 새 WCF 워크플로 서비스를 추가 `WorkflowService` `Common` 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-127">Add a new WCF Workflow Service, called `WorkflowService` to the `Common` project.</span></span> <span data-ttu-id="6a938-128">이렇게 하려면 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 `Common` **추가**, **새 항목 ...** 을 차례로 선택 하 고 **설치 된 템플릿** 에서 **워크플로** 를 선택한 다음 **WCF 워크플로 서비스** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-128">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **WCF Workflow Service**.</span></span>  
  
     ![워크플로 서비스 추가](./media/flowing-transactions-into-and-out-of-workflow-services/add-workflow-service.jpg)  
  
2. <span data-ttu-id="6a938-130">기본 `ReceiveRequest` 및 `SendResponse` 활동을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-130">Delete the default `ReceiveRequest` and `SendResponse` activities.</span></span>  
  
3. <span data-ttu-id="6a938-131"><xref:System.Activities.Statements.WriteLine> 활동을 `Sequential Service` 활동으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-131">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity into the `Sequential Service` activity.</span></span> <span data-ttu-id="6a938-132">다음 예제와 같이 텍스트 속성을 `"Workflow Service starting ..."`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-132">Set the text property to `"Workflow Service starting ..."` as shown in the following example.</span></span>  
  
     <span data-ttu-id="6a938-133">! [순차 서비스 활동에 WriteLine 활동 추가 (./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span><span class="sxs-lookup"><span data-stu-id="6a938-133">![Adding a WriteLine activity to the Sequential Service activity(./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-sequential-service.jpg)</span></span>  
  
4. <span data-ttu-id="6a938-134"><xref:System.ServiceModel.Activities.TransactedReceiveScope>을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-134">Drag and drop a <xref:System.ServiceModel.Activities.TransactedReceiveScope> after the <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="6a938-135"><xref:System.ServiceModel.Activities.TransactedReceiveScope>활동은 **도구 상자** 의 **메시징** 섹션에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-135">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity can be found in the **Messaging** section of the **Toolbox**.</span></span> <span data-ttu-id="6a938-136"><xref:System.ServiceModel.Activities.TransactedReceiveScope>활동은 **요청** 및 **본문** 의 두 섹션으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-136">The <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity is composed of two sections **Request** and **Body**.</span></span> <span data-ttu-id="6a938-137">**요청** 섹션에는 <xref:System.ServiceModel.Activities.Receive> 활동이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-137">The **Request** section contains the <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="6a938-138">**본문** 섹션에는 메시지를 받은 후 트랜잭션 내에서 실행할 활동이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-138">The **Body** section contains the activities to execute within a transaction after a message has been received.</span></span>  
  
     ![TransactedReceiveScope 활동 추가](./media/flowing-transactions-into-and-out-of-workflow-services/transactedreceivescope-activity.jpg)  
  
5. <span data-ttu-id="6a938-140">활동을 선택 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 하 고 **변수** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-140">Select the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity and click the **Variables** button.</span></span> <span data-ttu-id="6a938-141">다음 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-141">Add the following variables.</span></span>  
  
     ![TransactedReceiveScope에 변수 추가](./media/flowing-transactions-into-and-out-of-workflow-services/add-transactedreceivescope-variables.jpg)  
  
    > [!NOTE]
    > <span data-ttu-id="6a938-143">기본적으로 여기에 포함된 데이터 변수를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-143">You can delete the data variable that is there by default.</span></span> <span data-ttu-id="6a938-144">기존 핸들 변수를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-144">You can also use the existing handle variable.</span></span>  
  
6. <span data-ttu-id="6a938-145">활동 <xref:System.ServiceModel.Activities.Receive> 의 **요청** 섹션 내에서 활동을 끌어 놓습니다 <xref:System.ServiceModel.Activities.TransactedReceiveScope> .</span><span class="sxs-lookup"><span data-stu-id="6a938-145">Drag and drop a <xref:System.ServiceModel.Activities.Receive> activity within the **Request** section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span> <span data-ttu-id="6a938-146">다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-146">Set the following properties:</span></span>  
  
    |<span data-ttu-id="6a938-147">속성</span><span class="sxs-lookup"><span data-stu-id="6a938-147">Property</span></span>|<span data-ttu-id="6a938-148">값</span><span class="sxs-lookup"><span data-stu-id="6a938-148">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="6a938-149">CanCreateInstance</span><span class="sxs-lookup"><span data-stu-id="6a938-149">CanCreateInstance</span></span>|<span data-ttu-id="6a938-150">True(확인란 선택)</span><span class="sxs-lookup"><span data-stu-id="6a938-150">True (check the checkbox)</span></span>|  
    |<span data-ttu-id="6a938-151">OperationName</span><span class="sxs-lookup"><span data-stu-id="6a938-151">OperationName</span></span>|<span data-ttu-id="6a938-152">StartSample</span><span class="sxs-lookup"><span data-stu-id="6a938-152">StartSample</span></span>|  
    |<span data-ttu-id="6a938-153">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="6a938-153">ServiceContractName</span></span>|<span data-ttu-id="6a938-154">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="6a938-154">ITransactionSample</span></span>|  
  
     <span data-ttu-id="6a938-155">워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-155">The workflow should look like this:</span></span>  
  
     ![Receive 활동 추가](./media/flowing-transactions-into-and-out-of-workflow-services/add-receive-activity.jpg)  
  
7. <span data-ttu-id="6a938-157">활동에서 **정의 ...** 링크를 클릭 <xref:System.ServiceModel.Activities.Receive> 하 고 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-157">Click the **Define...** link in the <xref:System.ServiceModel.Activities.Receive> activity and make the following settings:</span></span>  
  
     ![Receive 활동에 대 한 메시지 설정 설정](./media/flowing-transactions-into-and-out-of-workflow-services/receive-message-settings.jpg)  
  
8. <span data-ttu-id="6a938-159"><xref:System.Activities.Statements.Sequence> 활동을 <xref:System.ServiceModel.Activities.TransactedReceiveScope>의 본문 섹션으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-159">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the Body section of the <xref:System.ServiceModel.Activities.TransactedReceiveScope>.</span></span> <span data-ttu-id="6a938-160"><xref:System.Activities.Statements.Sequence> 활동 내에 두 개의 <xref:System.Activities.Statements.WriteLine> 활동을 끌어 놓고 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 다음 표와 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-160">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop two <xref:System.Activities.Statements.WriteLine> activities and set the <xref:System.Activities.Statements.WriteLine.Text%2A> properties as shown in the following table.</span></span>  
  
    |<span data-ttu-id="6a938-161">활동</span><span class="sxs-lookup"><span data-stu-id="6a938-161">Activity</span></span>|<span data-ttu-id="6a938-162">값</span><span class="sxs-lookup"><span data-stu-id="6a938-162">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="6a938-163">1st WriteLine</span><span class="sxs-lookup"><span data-stu-id="6a938-163">1st WriteLine</span></span>|<span data-ttu-id="6a938-164">"서비스: 수신 완료"</span><span class="sxs-lookup"><span data-stu-id="6a938-164">"Service: Receive Completed"</span></span>|  
    |<span data-ttu-id="6a938-165">2nd WriteLine</span><span class="sxs-lookup"><span data-stu-id="6a938-165">2nd WriteLine</span></span>|<span data-ttu-id="6a938-166">"Service: Received = " + requestMessage</span><span class="sxs-lookup"><span data-stu-id="6a938-166">"Service: Received = " + requestMessage</span></span>|  
  
     <span data-ttu-id="6a938-167">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-167">The workflow should now look like this:</span></span>  
  
     ![WriteLine 활동을 추가한 후의 시퀀스](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-writelines.jpg)  
  
9. <span data-ttu-id="6a938-169">활동을 `PrintTransactionInfo` <xref:System.Activities.Statements.WriteLine> 활동의 **본문** 에서 두 번째 활동 뒤로 끌어 놓습니다 <xref:System.ServiceModel.Activities.TransactedReceiveScope> .</span><span class="sxs-lookup"><span data-stu-id="6a938-169">Drag and drop the `PrintTransactionInfo` activity after the second <xref:System.Activities.Statements.WriteLine> activity in the **Body** in the <xref:System.ServiceModel.Activities.TransactedReceiveScope> activity.</span></span>  
  
     ![PrintTransactionInfo 추가 후 시퀀스](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-printtransactioninfo.jpg )  
  
10. <span data-ttu-id="6a938-171"><xref:System.Activities.Statements.Assign> 활동을 `PrintTransactionInfo` 활동 뒤로 끌어 놓고 해당 속성을 다음 표와 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-171">Drag and drop an <xref:System.Activities.Statements.Assign> activity after the `PrintTransactionInfo` activity and set its properties according to the following table.</span></span>  
  
    |<span data-ttu-id="6a938-172">속성</span><span class="sxs-lookup"><span data-stu-id="6a938-172">Property</span></span>|<span data-ttu-id="6a938-173">값</span><span class="sxs-lookup"><span data-stu-id="6a938-173">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="6a938-174">대상</span><span class="sxs-lookup"><span data-stu-id="6a938-174">To</span></span>|<span data-ttu-id="6a938-175">replyMessage</span><span class="sxs-lookup"><span data-stu-id="6a938-175">replyMessage</span></span>|  
    |<span data-ttu-id="6a938-176">값</span><span class="sxs-lookup"><span data-stu-id="6a938-176">Value</span></span>|<span data-ttu-id="6a938-177">"Service: Sending reply"</span><span class="sxs-lookup"><span data-stu-id="6a938-177">"Service: Sending reply."</span></span>|  
  
11. <span data-ttu-id="6a938-178"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.Activities.Statements.Assign> 활동 뒤로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: Begin reply"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-178">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.Activities.Statements.Assign> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Begin reply."</span></span>  
  
     <span data-ttu-id="6a938-179">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-179">The workflow should now look like this:</span></span>  
  
     ![Assign 및 WriteLine 추가 후](./media/flowing-transactions-into-and-out-of-workflow-services/after-adding-sbr-writeline.jpg)  
  
12. <span data-ttu-id="6a938-181">활동을 마우스 오른쪽 단추로 클릭 <xref:System.ServiceModel.Activities.Receive> 하 고 **SendReply 만들기** 를 선택 하 고 마지막 활동 뒤에 붙여넣습니다 <xref:System.Activities.Statements.WriteLine> .</span><span class="sxs-lookup"><span data-stu-id="6a938-181">Right click the <xref:System.ServiceModel.Activities.Receive> activity and select **Create SendReply** and paste it after the last <xref:System.Activities.Statements.WriteLine> activity.</span></span> <span data-ttu-id="6a938-182">활동에서 **정의 ...** 링크를 클릭 `SendReplyToReceive` 하 고 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-182">Click the **Define...** link in the `SendReplyToReceive` activity and make the following settings.</span></span>  
  
     ![Reply 메시지 설정](./media/flowing-transactions-into-and-out-of-workflow-services/reply-message-settings.jpg)  
  
13. <span data-ttu-id="6a938-184">활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓고 `SendReplyToReceive` 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: Reply sent"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-184">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `SendReplyToReceive` activity and set it’s <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Reply sent."</span></span>  
  
14. <span data-ttu-id="6a938-185"><xref:System.Activities.Statements.WriteLine> 활동을 워크플로의 맨 아래로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Service: Workflow ends, press ENTER to exit"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-185">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the bottom of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Service: Workflow ends, press ENTER to exit."</span></span>  
  
     <span data-ttu-id="6a938-186">완료된 서비스 워크플로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-186">The completed service workflow should look like this:</span></span>  
  
     ![전체 서비스 워크플로](./media/flowing-transactions-into-and-out-of-workflow-services/service-complete-workflow.jpg)  
  
### <a name="implement-the-workflow-client"></a><span data-ttu-id="6a938-188">워크플로 클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="6a938-188">Implement the workflow client</span></span>  
  
1. <span data-ttu-id="6a938-189">`WorkflowClient` 프로젝트에 `Common`라는 새 WCF 워크플로 애플리케이션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-189">Add a new WCF Workflow application, called `WorkflowClient` to the `Common` project.</span></span> <span data-ttu-id="6a938-190">이렇게 하려면 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 `Common` **추가**, **새 항목 ...** 을 차례로 선택 하 고 **설치 된 템플릿** 에서 **워크플로** 를 선택한 다음 **활동** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-190">To do this right click the `Common` project, select **Add**, **New Item ...**, Select **Workflow** under **Installed Templates** and select **Activity**.</span></span>  
  
     ![활동 프로젝트 추가](./media/flowing-transactions-into-and-out-of-workflow-services/add-activity-project.jpg)  
  
2. <span data-ttu-id="6a938-192">디자인 화면으로 <xref:System.Activities.Statements.Sequence> 활동을 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-192">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the design surface.</span></span>  
  
3. <span data-ttu-id="6a938-193"><xref:System.Activities.Statements.Sequence> 활동 내에 <xref:System.Activities.Statements.WriteLine> 활동을 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 `"Client: Workflow starting"`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-193">Within the <xref:System.Activities.Statements.Sequence> activity drag and drop a <xref:System.Activities.Statements.WriteLine> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to `"Client: Workflow starting"`.</span></span> <span data-ttu-id="6a938-194">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-194">The workflow should now look like this:</span></span>  
  
     ![WriteLine 활동 추가](./media/flowing-transactions-into-and-out-of-workflow-services/add-writeline-activity.jpg)  
  
4. <span data-ttu-id="6a938-196"><xref:System.Activities.Statements.TransactionScope> 활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-196">Drag and drop a <xref:System.Activities.Statements.TransactionScope> activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  <span data-ttu-id="6a938-197"><xref:System.Activities.Statements.TransactionScope> 활동을 선택하고 변수 단추를 클릭한 후 다음 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-197">Select the <xref:System.Activities.Statements.TransactionScope> activity, click the Variables button and add the following variables.</span></span>  
  
     ![TransactionScope에 변수 추가](./media/flowing-transactions-into-and-out-of-workflow-services/transactionscope-variables.jpg)  
  
5. <span data-ttu-id="6a938-199"><xref:System.Activities.Statements.Sequence> 활동을 <xref:System.Activities.Statements.TransactionScope> 활동의 본문으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-199">Drag and drop a <xref:System.Activities.Statements.Sequence> activity into the body of the <xref:System.Activities.Statements.TransactionScope> activity.</span></span>  
  
6. <span data-ttu-id="6a938-200">`PrintTransactionInfo` 활동을 <xref:System.Activities.Statements.Sequence> 안으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-200">Drag and drop a `PrintTransactionInfo` activity within the <xref:System.Activities.Statements.Sequence></span></span>  
  
7. <span data-ttu-id="6a938-201">활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓고 `PrintTransactionInfo` 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "클라이언트: 시작 보내기"로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-201">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the `PrintTransactionInfo` activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Beginning Send".</span></span> <span data-ttu-id="6a938-202">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-202">The workflow should now look like this:</span></span>  
  
     ![클라이언트 추가: 시작 보내기 작업](./media/flowing-transactions-into-and-out-of-workflow-services/client-add-cbs-writeline.jpg)  
  
8. <span data-ttu-id="6a938-204"><xref:System.ServiceModel.Activities.Send> 활동을 <xref:System.Activities.Statements.Assign> 활동 뒤로 끌어 놓고 다음 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-204">Drag and drop a <xref:System.ServiceModel.Activities.Send> activity after the <xref:System.Activities.Statements.Assign> activity and set the following properties:</span></span>  
  
    |<span data-ttu-id="6a938-205">속성</span><span class="sxs-lookup"><span data-stu-id="6a938-205">Property</span></span>|<span data-ttu-id="6a938-206">값</span><span class="sxs-lookup"><span data-stu-id="6a938-206">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="6a938-207">EndpointConfigurationName</span><span class="sxs-lookup"><span data-stu-id="6a938-207">EndpointConfigurationName</span></span>|<span data-ttu-id="6a938-208">workflowServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="6a938-208">workflowServiceEndpoint</span></span>|  
    |<span data-ttu-id="6a938-209">OperationName</span><span class="sxs-lookup"><span data-stu-id="6a938-209">OperationName</span></span>|<span data-ttu-id="6a938-210">StartSample</span><span class="sxs-lookup"><span data-stu-id="6a938-210">StartSample</span></span>|  
    |<span data-ttu-id="6a938-211">ServiceContractName</span><span class="sxs-lookup"><span data-stu-id="6a938-211">ServiceContractName</span></span>|<span data-ttu-id="6a938-212">ITransactionSample</span><span class="sxs-lookup"><span data-stu-id="6a938-212">ITransactionSample</span></span>|  
  
     <span data-ttu-id="6a938-213">이제 워크플로가 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-213">The workflow should now look like this:</span></span>  
  
     ![Send 활동 속성 설정](./media/flowing-transactions-into-and-out-of-workflow-services/client-send-activity-settings.jpg)  
  
9. <span data-ttu-id="6a938-215">**정의 ...** 링크를 클릭 하 고 다음과 같이 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-215">Click the **Define...** link and make the following settings:</span></span>  
  
     ![Send 활동 메시지 설정](./media/flowing-transactions-into-and-out-of-workflow-services/send-message-settings.jpg)  
  
10. <span data-ttu-id="6a938-217">활동을 마우스 오른쪽 단추로 클릭 <xref:System.ServiceModel.Activities.Send> 하 고 **ReceiveReply 만들기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-217">Right click the <xref:System.ServiceModel.Activities.Send> activity and select **Create ReceiveReply**.</span></span> <span data-ttu-id="6a938-218"><xref:System.ServiceModel.Activities.ReceiveReply> 활동이 자동으로 <xref:System.ServiceModel.Activities.Send> 활동 뒤에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-218">The <xref:System.ServiceModel.Activities.ReceiveReply> activity will be automatically placed after the <xref:System.ServiceModel.Activities.Send> activity.</span></span>  
  
11. <span data-ttu-id="6a938-219">ReceiveReplyForSend 활동의 정의... 링크를 클릭하고 다음과 같이 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-219">Click the Define... link on the ReceiveReplyForSend activity and make the following settings:</span></span>  
  
     ![ReceiveForSend 메시지 설정 지정](./media/flowing-transactions-into-and-out-of-workflow-services/client-reply-message-settings.jpg)  
  
12. <span data-ttu-id="6a938-221"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.ServiceModel.Activities.Send> 활동과 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 사이로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client: Send complete"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-221">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity between the <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> activities and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client: Send complete."</span></span>  
  
13. <span data-ttu-id="6a938-222"><xref:System.Activities.Statements.WriteLine> 활동을 <xref:System.ServiceModel.Activities.ReceiveReply> 활동 뒤로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client side: Reply received = " + replyMessage로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-222">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity after the <xref:System.ServiceModel.Activities.ReceiveReply> activity and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client side: Reply received = " + replyMessage</span></span>  
  
14. <span data-ttu-id="6a938-223">`PrintTransactionInfo` 활동을 <xref:System.Activities.Statements.WriteLine> 활동 뒤로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-223">Drag and drop a `PrintTransactionInfo` activity after the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
15. <span data-ttu-id="6a938-224"><xref:System.Activities.Statements.WriteLine> 활동을 워크플로 끝으로 끌어 놓고 해당 <xref:System.Activities.Statements.WriteLine.Text%2A> 속성을 "Client workflow ends"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-224">Drag and drop a <xref:System.Activities.Statements.WriteLine> activity at the end of the workflow and set its <xref:System.Activities.Statements.WriteLine.Text%2A> property to "Client workflow ends."</span></span> <span data-ttu-id="6a938-225">완료된 클라이언트 워크플로는 다음 다이어그램과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-225">The completed client workflow should look like the following diagram.</span></span>  
  
     ![완료 된 클라이언트 워크플로](./media/flowing-transactions-into-and-out-of-workflow-services/client-complete-workflow.jpg)  
  
16. <span data-ttu-id="6a938-227">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-227">Build the solution.</span></span>  
  
### <a name="create-the-service-application"></a><span data-ttu-id="6a938-228">서비스 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="6a938-228">Create the Service application</span></span>  
  
1. <span data-ttu-id="6a938-229">솔루션에 `Service`라는 새 콘솔 애플리케이션 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="6a938-229">Add a new Console Application project called `Service` to the solution.</span></span> <span data-ttu-id="6a938-230">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-230">Add references to the following assemblies:</span></span>  
  
    1. <span data-ttu-id="6a938-231">System.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-231">System.Activities.dll</span></span>  
  
    2. <span data-ttu-id="6a938-232">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-232">System.ServiceModel.dll</span></span>  
  
    3. <span data-ttu-id="6a938-233">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="6a938-233">System.ServiceModel.Activities.dll</span></span>  
  
2. <span data-ttu-id="6a938-234">생성된 Program.cs 파일을 열고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-234">Open the generated Program.cs file and the following code:</span></span>  
  
    ```csharp
          static void Main()  
          {  
              Console.WriteLine("Building the server.");  
              using (WorkflowServiceHost host = new WorkflowServiceHost(new DeclarativeServiceWorkflow(), new Uri("net.tcp://localhost:8000/TransactedReceiveService/Declarative")))  
              {
                  //Start the server  
                  host.Open();  
                  Console.WriteLine("Service started.");  
  
                  Console.WriteLine();  
                  Console.ReadLine();  
                  //Shutdown  
                  host.Close();  
              };
          }  
    ```  
  
3. <span data-ttu-id="6a938-235">프로젝트에 다음 app.config 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-235">Add the following app.config file to the project.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <!-- Copyright © Microsoft Corporation.  All rights reserved. -->  
    <configuration>  
        <system.serviceModel>  
            <bindings>  
                <netTcpBinding>  
                    <binding transactionFlow="true" />  
                </netTcpBinding>  
            </bindings>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="create-the-client-application"></a><span data-ttu-id="6a938-236">클라이언트 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="6a938-236">Create the client application</span></span>  
  
1. <span data-ttu-id="6a938-237">솔루션에 `Client`라는 새 콘솔 애플리케이션 프로젝트를 추가하고,</span><span class="sxs-lookup"><span data-stu-id="6a938-237">Add a new Console Application project called `Client` to the solution.</span></span> <span data-ttu-id="6a938-238">System.Activities.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-238">Add a reference to System.Activities.dll.</span></span>  
  
2. <span data-ttu-id="6a938-239">program.cs 파일을 열고 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6a938-239">Open the program.cs file and add the following code.</span></span>  
  
    ```csharp
    class Program  
    {  

        private static AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
        static void Main(string[] args)  
        {  
            //Build client  
            Console.WriteLine("Building the client.");  
            WorkflowApplication client = new WorkflowApplication(new DeclarativeClientWorkflow());  
            client.Completed = Program.Completed;  
            client.Aborted = Program.Aborted;  
            client.OnUnhandledException = Program.OnUnhandledException;  
            //Wait for service to start  
            Console.WriteLine("Press ENTER once service is started.");  
            Console.ReadLine();  
  
            //Start the client
            Console.WriteLine("Starting the client.");  
            client.Run();  
            syncEvent.WaitOne();  
  
            //Sample complete  
            Console.WriteLine();  
            Console.WriteLine("Client complete. Press ENTER to exit.");  
            Console.ReadLine();  
        }  
  
        private static void Completed(WorkflowApplicationCompletedEventArgs e)  
        {  
            Program.syncEvent.Set();  
        }  
  
        private static void Aborted(WorkflowApplicationAbortedEventArgs e)  
        {  
            Console.WriteLine("Client Aborted: {0}", e.Reason);  
            Program.syncEvent.Set();  
        }  
  
        private static UnhandledExceptionAction OnUnhandledException(WorkflowApplicationUnhandledExceptionEventArgs e)  
        {  
            Console.WriteLine("Client had an unhandled exception: {0}", e.UnhandledException);  
            return UnhandledExceptionAction.Cancel;  
        }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6a938-240">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a938-240">See also</span></span>

- [<span data-ttu-id="6a938-241">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="6a938-241">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="6a938-242">Windows Communication Foundation 트랜잭션 개요</span><span class="sxs-lookup"><span data-stu-id="6a938-242">Windows Communication Foundation Transactions Overview</span></span>](transactions-overview.md)
