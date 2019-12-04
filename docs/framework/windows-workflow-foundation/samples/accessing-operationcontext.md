---
title: OperationContext 액세스
ms.date: 03/30/2017
ms.assetid: 4e92efe8-7e79-41f3-b50e-bdc38b9f41f8
ms.openlocfilehash: b8a09aff7b5a30b5267fbdbd7bd6391996f359c7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715098"
---
# <a name="accessing-operationcontext"></a><span data-ttu-id="fc7bd-102">OperationContext 액세스</span><span class="sxs-lookup"><span data-stu-id="fc7bd-102">Accessing OperationContext</span></span>
<span data-ttu-id="fc7bd-103">이 샘플에서는 메시징 활동 (<xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.Send>)을 사용자 지정 범위 작업과 함께 사용 하 여 보내는 메시지 또는 들어오는 메시지 내의 사용자 지정 메시지 헤더에 <xref:System.ServiceModel.OperationContext.Current%2A> 액세스 하 고 연결 하거나 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-103">This sample demonstrates how the messaging activities (<xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.Send>) can be used with a custom scope activity to access <xref:System.ServiceModel.OperationContext.Current%2A> and attach or retrieve a custom message header within an outgoing or incoming message.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="fc7bd-104">데모</span><span class="sxs-lookup"><span data-stu-id="fc7bd-104">Demonstrates</span></span>  
 <span data-ttu-id="fc7bd-105">메시징 활동, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback></span><span class="sxs-lookup"><span data-stu-id="fc7bd-105">Messaging Activities, <xref:System.ServiceModel.Activities.ISendMessageCallback>, <xref:System.ServiceModel.Activities.IReceiveMessageCallback>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="fc7bd-106">토론</span><span class="sxs-lookup"><span data-stu-id="fc7bd-106">Discussion</span></span>  
 <span data-ttu-id="fc7bd-107">이 샘플에서는 메시징 활동에 확장성 지점(<xref:System.ServiceModel.Activities.ISendMessageCallback> 및 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>)을 사용하여 <xref:System.ServiceModel.OperationContext.Current%2A>에 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-107">This sample shows how to use extensibility points (<xref:System.ServiceModel.Activities.ISendMessageCallback>) <xref:System.ServiceModel.Activities.IReceiveMessageCallback>) in the messaging activities to access <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="fc7bd-108">콜백은 실행 시 메시징 활동에서 선택하는 <xref:System.Activities.IExecutionProperty>의 구현으로 워크플로 런타임 내에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-108">The callbacks are registered within the workflow runtime as an implementation of <xref:System.Activities.IExecutionProperty> that is picked up by the messaging activities upon execution.</span></span> <span data-ttu-id="fc7bd-109">해당 <xref:System.Activities.IExecutionProperty> 구현과 동일한 범위의 모든 메시징 활동이 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-109">Any messaging activity in the same scope as that <xref:System.Activities.IExecutionProperty> implementation is affected.</span></span> <span data-ttu-id="fc7bd-110">특히 이 샘플에서는 사용자 지정 범위 활동을 사용하여 콜백 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-110">In particular, this sample uses a custom scope activity to enforce the callback behavior.</span></span> <span data-ttu-id="fc7bd-111">클라이언트 워크플로에서 <xref:System.ServiceModel.Activities.ISendMessageCallback>을 사용하여 워크플로의 <xref:System.Activities.WorkflowApplication.Id%2A>를 보내는 <xref:System.ServiceModel.Channels.MessageHeader>로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-111">The <xref:System.ServiceModel.Activities.ISendMessageCallback> is used in the client workflow to include the workflow’s <xref:System.Activities.WorkflowApplication.Id%2A> as an outgoing <xref:System.ServiceModel.Channels.MessageHeader>.</span></span> <span data-ttu-id="fc7bd-112">그런 다음 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>을 사용하여 서비스에서 이 헤더를 선택하고 헤더 값을 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-112">This header is then picked up in the service using the <xref:System.ServiceModel.Activities.IReceiveMessageCallback> and the value of the header is printed out to the console.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fc7bd-113">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fc7bd-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="fc7bd-114">이 샘플에서는 HTTP 엔드포인트를 사용하여 워크플로 서비스를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-114">This sample exposes a workflow service using HTTP endpoints.</span></span> <span data-ttu-id="fc7bd-115">이 샘플을 실행 하려면 Visual Studio를 관리자 권한으로 실행 하거나 관리자 권한 프롬프트에서 다음 명령을 실행 하 여 적절 한 Acl을 추가 하 여 적절 한 URL Acl을 추가 해야 합니다 (자세한 내용은 [HTTP 및 HTTPS 구성](https://go.microsoft.com/fwlink/?LinkId=70353) 참조).</span><span class="sxs-lookup"><span data-stu-id="fc7bd-115">To run this sample, proper URL ACLs must be added (see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details), either by running Visual Studio as Administrator or by executing the following command at an elevated prompt to add the appropriate ACLs.</span></span> <span data-ttu-id="fc7bd-116">도메인과 사용자 이름이 대체되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-116">Ensure that your Domain and Username are substituted.</span></span>  
  
    ```console  
    netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%  
    ```  
  
2. <span data-ttu-id="fc7bd-117">URL ACL이 추가되었으면 다음 단계를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-117">Once the URL ACLs are added, use the following steps.</span></span>  
  
    1. <span data-ttu-id="fc7bd-118">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-118">Build the solution.</span></span>  
  
    2. <span data-ttu-id="fc7bd-119">솔루션을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트 설정**을 선택 하 여 여러 시작 프로젝트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-119">Set multiple start-up projects by right-clicking the solution and selecting **Set Startup Projects**.</span></span>  
  
    3. <span data-ttu-id="fc7bd-120">**서비스** 와 **클라이언트** (해당 순서로)를 여러 시작 프로젝트로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-120">Add **Service** and **Client** (in that order) as multiple start-up projects.</span></span>  
  
    4. <span data-ttu-id="fc7bd-121">응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-121">Run the application.</span></span> <span data-ttu-id="fc7bd-122">클라이언트 콘솔에 워크플로가 두 번 실행되고 있다고 표시되고 서비스 창에는 해당 워크플로의 인스턴스 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-122">The client console shows a workflow running twice and the Service window shows the instance ID of those workflows.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="fc7bd-123">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fc7bd-124">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-124">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="fc7bd-125">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fc7bd-126">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc7bd-126">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\Accessing Operation Context`
