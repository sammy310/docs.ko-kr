---
title: Asynchronous Communication
ms.date: 03/30/2017
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
ms.openlocfilehash: db5a8f415479967d7579357bd0c8058c7fb961c5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255847"
---
# <a name="asynchronous-communication"></a><span data-ttu-id="b377b-102">Asynchronous Communication</span><span class="sxs-lookup"><span data-stu-id="b377b-102">Asynchronous Communication</span></span>

<span data-ttu-id="b377b-103">이 샘플에서는 두 개의 다른 WF (Windows Workflow Foundation) 서비스 간 통신이 기본적으로 비동기적으로 수행 되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-103">This sample demonstrates how the communication between two different Windows Workflow Foundation (WF) services is done asynchronously by default.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b377b-104">데모</span><span class="sxs-lookup"><span data-stu-id="b377b-104">Demonstrates</span></span>  

 <span data-ttu-id="b377b-105">[!INCLUDE[wf1](../../../../includes/wf1-md.md)] 서비스 간의 비동기 통신</span><span class="sxs-lookup"><span data-stu-id="b377b-105">Asynchronous communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] services.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b377b-106">토론(Discussion)</span><span class="sxs-lookup"><span data-stu-id="b377b-106">Discussion</span></span>  

 <span data-ttu-id="b377b-107">이 샘플에서는 .NET Framework에서 제공되는 메시징 활동을 통해 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 애플리케이션 간의 통신이 비동기적으로 이루어지는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-107">This sample shows how the communication between [!INCLUDE[wf1](../../../../includes/wf1-md.md)] applications is done asynchronously by using the messaging activities provided by .NET Framework.</span></span>  
  
 <span data-ttu-id="b377b-108">이 샘플은 다음 세 개의 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-108">This sample consists of the following three projects.</span></span>  
  
 <span data-ttu-id="b377b-109">CreditCheckService</span><span class="sxs-lookup"><span data-stu-id="b377b-109">CreditCheckService</span></span>  
 <span data-ttu-id="b377b-110">이 서비스는 특정 개인의 신용 점수나 승인할 품목의 가치를 받은 다음 해당 개인에게 신용을 부여할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-110">This service receives the credit score of a particular person or the value of the item to acquire, and then decides whether the credit is given to the person.</span></span>  
  
 <span data-ttu-id="b377b-111">RentalApprovalService</span><span class="sxs-lookup"><span data-stu-id="b377b-111">RentalApprovalService</span></span>  
 <span data-ttu-id="b377b-112">이 서비스는 신용 거래를 필요로 하는 개인으로부터 신청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-112">This service receives an application from a person who is in need of some credit.</span></span> <span data-ttu-id="b377b-113">이 서비스는 `CreditCheckService`와 비동기적으로 통신하여 신용 거래 신청이 유효한지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-113">This service communicates asynchronously with the `CreditCheckService` to decide whether the credit application is valid.</span></span>  
  
 <span data-ttu-id="b377b-114">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b377b-114">Client</span></span>  
 <span data-ttu-id="b377b-115">클라이언트는 `RentalApprovalService`와 동기적으로 통신하여 신용 거래가 승인되었는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-115">The client communicates synchronously with the `RentalApprovalService` to know whether the credit is approved.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b377b-116">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="b377b-116">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b377b-117">**AsynchronousCommunication** 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-117">Right-click the **AsynchronousCommunication** solution and select **Properties**.</span></span>  
  
2. <span data-ttu-id="b377b-118">**공용 속성** 에서 **시작 프로젝트** 를 선택 하 고 **여러 개의 시작 프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-118">In **Common Properties**, select **Startup Project**, and select **Multiple Startup Projects**.</span></span>  
  
3. <span data-ttu-id="b377b-119">**RentalApprovalService** 를 목록의 첫 번째 위치로 이동 하 고 그 뒤에 **CreditCheckService** 를 오고 **클라이언트** 를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-119">Move **RentalApprovalService** to the first position in the list, followed by **CreditCheckService**, followed by **Client**.</span></span> <span data-ttu-id="b377b-120">세 프로젝트 모두에 대해 **시작** 동작을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-120">Set the **Start** action on all three projects.</span></span>  
  
4. <span data-ttu-id="b377b-121">**확인** 을 클릭 하 고 f5 키를 눌러 샘플을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-121">Click **OK**, and press F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b377b-122">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b377b-123">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b377b-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b377b-124">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b377b-125">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b377b-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`
