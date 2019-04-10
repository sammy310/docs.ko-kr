---
title: 문서 승인 프로세스
ms.date: 03/30/2017
ms.assetid: 9b240937-76a7-45cd-8823-7f82c34d03bd
ms.openlocfilehash: dfc2e0a12d053733823427ac50066b1e4a0f97aa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318470"
---
# <a name="document-approval-process"></a><span data-ttu-id="2f38c-102">문서 승인 프로세스</span><span class="sxs-lookup"><span data-stu-id="2f38c-102">Document Approval Process</span></span>
<span data-ttu-id="2f38c-103">이 샘플 많은 Windows WF (Workflow Foundation) 및 Windows Communication Foundation (WCF) 기능의 사용을 함께 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-103">This sample demonstrates the use of many Windows Workflow Foundation (WF) and Windows Communication Foundation (WCF) features together.</span></span> <span data-ttu-id="2f38c-104">이 기능들은 문서 승인 프로세스 시나리오를 구현하는 데 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-104">Together they implement a document approval process scenario.</span></span> <span data-ttu-id="2f38c-105">클라이언트 응용 프로그램은 승인이 필요한 문서를 제출하고 문서를 승인합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-105">A client application can submit documents for approval and approve documents.</span></span> <span data-ttu-id="2f38c-106">클라이언트 사이의 원활한 통신을 지원하고 승인 프로세스의 규칙을 적용하는 데는 승인 관리자 응용 프로그램이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-106">An approval manager application exists to facilitate communications between clients and to enforce the rules of the approval process.</span></span> <span data-ttu-id="2f38c-107">승인 프로세스는 여러 가지 유형의 승인을 실행할 수 있는 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-107">The approval process is a workflow that can execute several types of approval.</span></span> <span data-ttu-id="2f38c-108">단일 승인 프로세스, 정족수 승인(승인자 집합의 백분율) 프로세스 및 정족수 승인과 단일 승인이 차례로 이루어지는 복합 승인 프로세스를 처리하기 위하여 각기 다른 활동이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-108">Activities exist to get a single approval, a quorum approval (a percentage of set of approvers), and a complex approval process that consists of a quorum and single approval in a sequence.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="2f38c-109">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2f38c-110">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="2f38c-110">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2f38c-111">이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="2f38c-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2f38c-112">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-112">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Application\DocumentApprovalProcess`  
  
## <a name="sample-details"></a><span data-ttu-id="2f38c-113">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="2f38c-113">Sample Details</span></span>  
 <span data-ttu-id="2f38c-114">다음 그림에는 문서 승인 프로세스 워크플로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-114">The following graphic demonstrates the document approval process workflow:</span></span>  
  
 ![문서 승인 프로세스 워크플로](./media/document-approval-process/document-approval-process.jpg)  
  
 <span data-ttu-id="2f38c-116">클라이언트측에서 볼 때 승인 프로세스는 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-116">From the client's perspective, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="2f38c-117">승인 프로세스 시스템의 사용자로 클라이언트를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-117">A client subscribes to be a user in the approval process system.</span></span>  
  
2. <span data-ttu-id="2f38c-118">WCF 클라이언트 승인 관리자 응용 프로그램에서 호스팅되는 WCF 서비스에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-118">A WCF client sends to a WCF service hosted by the approval manager application.</span></span>  
  
3. <span data-ttu-id="2f38c-119">고유한 사용자 ID가 클라이언트로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-119">A unique user ID is returned to the client.</span></span> <span data-ttu-id="2f38c-120">이제 클라이언트가 승인 프로세스에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-120">The client can now participate in approval processes.</span></span>  
  
4. <span data-ttu-id="2f38c-121">조인된 클라이언트에서 단일, 정속수 또는 복합 승인 프로세스를 사용하여 승인이 필요한 문서를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-121">Once joined, a client can send a document for approval using single, quorum or complex approval processes.</span></span>  
  
5. <span data-ttu-id="2f38c-122">클라이언트의 인터페이스 단추를 클릭하면 클라이언트 워크플로 서비스 호스트에서 워크플로 인스턴스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-122">A button in the client’s interface is clicked, starting a workflow instance in a client Workflow Service Host.</span></span>  
  
6. <span data-ttu-id="2f38c-123">워크플로에서 승인 관리자 응용 프로그램으로 승인 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-123">The workflow sends an approval request to the approval manager application.</span></span>  
  
7. <span data-ttu-id="2f38c-124">워크플로 관리자가 승인 프로세스와 관련된 워크플로를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-124">The workflow manager starts a workflow on its own side to represent an approval process.</span></span>  
  
8. <span data-ttu-id="2f38c-125">관리자가 승인 워크플로를 실행하고 나면 그 결과가 클라이언트로 다시 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-125">Once the manager approval workflow executes, the results are sent back to the client.</span></span>  
  
9. <span data-ttu-id="2f38c-126">클라이언트에 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-126">The client displays the results.</span></span>  
  
10. <span data-ttu-id="2f38c-127">클라이언트가 승인 요청을 받고 언제든지 해당 요청에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-127">A client may receive an approval request and respond to the request at any point in time.</span></span>  
  
11. <span data-ttu-id="2f38c-128">클라이언트에서 호스팅되는 WCF 서비스는 승인 관리자 응용 프로그램에서 승인 요청을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-128">A WCF service hosted on the client can receive an approval request from the approval manager application.</span></span>  
  
12. <span data-ttu-id="2f38c-129">문서 정보가 검토를 위해 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-129">The document information is presented on the client for review.</span></span>  
  
13. <span data-ttu-id="2f38c-130">사용자가 문서를 승인하거나 거부할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-130">The user can approve or reject the document.</span></span>  
  
14. <span data-ttu-id="2f38c-131">WCF 클라이언트를 통해 승인 응답이 승인 관리자 응용 프로그램에 다시 보낼 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-131">A WCF client is used to send an approval response back to the approval manager application.</span></span>  
  
 <span data-ttu-id="2f38c-132">승인 관리자 응용 프로그램측에서 볼 때 승인 프로세스는 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-132">From the approval manager application’s point of view, the approval process functions as follows:</span></span>  
  
1. <span data-ttu-id="2f38c-133">승인 프로세스 시스템에 대한 참가 요청이 클라이언트로부터 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-133">A client requests to participate to the approval process system.</span></span>  
  
2. <span data-ttu-id="2f38c-134">승인 관리자에서 WCF 서비스는 승인 프로세스 시스템의 일부로 요청을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-134">A WCF service on the approval manager receives a request to be part of the approval process system.</span></span>  
  
3. <span data-ttu-id="2f38c-135">클라이언트를 위한 고유한 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-135">A unique ID is generated for the client.</span></span> <span data-ttu-id="2f38c-136">사용자 정보가 데이터베이스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-136">The user information is stored in a database.</span></span>  
  
4. <span data-ttu-id="2f38c-137">고유 ID가 사용자에게 다시 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-137">The unique ID is sent back to the user.</span></span>  
  
5. <span data-ttu-id="2f38c-138">승인 요청이 접수됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-138">An approval request is receive.</span></span> <span data-ttu-id="2f38c-139">승인 관리자가 승인 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-139">The approval manager executes an approval process.</span></span>  
  
6. <span data-ttu-id="2f38c-140">승인 관리자가 승인 요청을 받으면 새 워크플로가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-140">An approval request is received by the approval manager, starting a new workflow.</span></span>  
  
7. <span data-ttu-id="2f38c-141">요청의 유형(단순, 정족수 또는 복합)에 따라 각기 다른 활동이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-141">Depending on the type of request (simple, quorum, or complex) a different activity is executed.</span></span>  
  
8. <span data-ttu-id="2f38c-142">검토할 승인 요청을 클라이언트로 보내고 응답을 받는 데는 상관 관계가 있는 보내기 및 받기 활동이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-142">Send and Receive activities with correlation are used to send the approval request to the client for review and receive the response.</span></span>  
  
9. <span data-ttu-id="2f38c-143">승인 프로세스 워크플로의 결과가 클라이언트로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-143">The result of the approval process workflow is sent to the client.</span></span>  
  
## <a name="using-the-sample"></a><span data-ttu-id="2f38c-144">샘플 사용</span><span class="sxs-lookup"><span data-stu-id="2f38c-144">Using the Sample</span></span>  
  
##### <a name="to-set-up-the-database"></a><span data-ttu-id="2f38c-145">데이터베이스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-145">To set up the database</span></span>  
  
1. <span data-ttu-id="2f38c-146">관리자 권한으로 연 Visual Studio 2010 명령 프롬프트에서이 DocumentApprovalProcess 폴더로 이동한 다음 Setup.cmd를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-146">From a Visual Studio 2010 command prompt opened with Administrator privileges, navigate to this DocumentApprovalProcess folder and run Setup.cmd.</span></span>  
  
##### <a name="to-set-up-the-application"></a><span data-ttu-id="2f38c-147">응용 프로그램을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-147">To set up the application</span></span>  
  
1. <span data-ttu-id="2f38c-148">DocumentApprovalProcess.sln 솔루션 파일을 열고 Visual Studio 2010을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-148">Using Visual Studio 2010, open the DocumentApprovalProcess.sln solution file.</span></span>  
  
2. <span data-ttu-id="2f38c-149">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-149">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3. <span data-ttu-id="2f38c-150">솔루션을 실행 하려면에서 ApprovalManager 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 승인 관리자 응용 프로그램을 시작 합니다 **솔루션 탐색기** 를 클릭 하 고 **디버그**->**시작**  오른쪽 클릭 메뉴에서 새 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="2f38c-150">To run the solution, launch the Approval Manager Application by right-clicking the ApprovalManager project in the **Solution Explorer** and clicking **Debug**->**Start** new instance from the right-click menu.</span></span>  
  
     <span data-ttu-id="2f38c-151">실행 준비가 되었다는 관리자의 메시지가 표시될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-151">Wait for the manager’s output to let you know that it is ready.</span></span>  
  
##### <a name="to-run-the-single-approval-scenario"></a><span data-ttu-id="2f38c-152">단일 승인 시나리오를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-152">To run the single approval scenario</span></span>  
  
1. <span data-ttu-id="2f38c-153">관리자 권한으로 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-153">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="2f38c-154">솔루션이 들어 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-154">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="2f38c-155">ApprovalClient\Bin\Debug 폴더로 이동하여 ApprovalClient.exe의 두 인스턴스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-155">Navigate to the ApprovalClient\Bin\Debug folder and execute two instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="2f38c-156">클릭 **검색**, 될 때까지 대기 합니다 **구독** 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-156">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="2f38c-157">모든 사용자 이름을 입력 하 고 클릭 **구독**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-157">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="2f38c-158">한 클라이언트에는 `UserType1`을 사용하고 다른 클라이언트에는 `UserType2` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-158">For one client, use `UserType1` and the other type `UserType2`.</span></span>  
  
6. <span data-ttu-id="2f38c-159">`UserType1` 클라이언트의 드롭다운 메뉴에서 단일 승인 유형을 선택하고 문서 이름과 콘텐츠를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-159">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="2f38c-160">클릭 **승인 요청**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-160">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="2f38c-161">승인을 기다리는 문서가 `UserType2` 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-161">In the `UserType2` client, a document awaiting approval appears.</span></span> <span data-ttu-id="2f38c-162">선택 하 고 키를 눌러 **승인할** 하거나 **거부**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-162">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="2f38c-163">`UserType1` 클라이언트에 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-163">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-quorum-approval-scenario"></a><span data-ttu-id="2f38c-164">정족수 승인 시나리오를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-164">To run the quorum approval scenario</span></span>  
  
1. <span data-ttu-id="2f38c-165">관리자 권한으로 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-165">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="2f38c-166">솔루션이 들어 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-166">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="2f38c-167">ApprovalClient\Bin\Debug 폴더로 이동하여 ApprovalClient.exe의 세 인스턴스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-167">Navigate to the ApprovalClient\Bin\Debug folder and execute three instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="2f38c-168">클릭 **검색**, 될 때까지 대기 합니다 **구독** 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-168">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="2f38c-169">모든 사용자 이름을 입력 하 고 클릭 **구독**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-169">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="2f38c-170">한 클라이언트에는 `UserType1`을 사용하고 다른 두 클라이언트에는 `UserType2` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-170">For one client use `UserType1` and the other two type `UserType2`.</span></span>  
  
6. <span data-ttu-id="2f38c-171">`UserType1` 클라이언트의 드롭다운 메뉴에서 정족수 승인 유형을 선택하고 문서 이름과 콘텐츠를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-171">In the `UserType1` client, select the quorum approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="2f38c-172">클릭 **승인 요청**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-172">Click **Request Approval**.</span></span> <span data-ttu-id="2f38c-173">이렇게 하면 문서 승인 또는 거부를 필요로 하는 요청이 두 `UserType2` 클라이언트에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-173">This requests that the two `UserType2` clients approve or reject the document.</span></span> <span data-ttu-id="2f38c-174">이 요청에 대해 두 `UserType2` 클라이언트가 모두 응답해야 하지만, 문서를 승인하려면 클라이언트 중 하나만 이를 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-174">While both `UserType2` clients must respond, only one client must approve the document for it to be approved.</span></span>  
  
7. <span data-ttu-id="2f38c-175">승인을 기다리는 문서가 두 `UserType2` 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-175">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="2f38c-176">선택 하 고 키를 눌러 **승인할** 하거나 **거부**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-176">Select it and press **approve** or **reject**.</span></span> <span data-ttu-id="2f38c-177">`UserType1` 클라이언트에 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-177">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-run-the-complex-approval-scenario"></a><span data-ttu-id="2f38c-178">복합 승인 시나리오를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-178">To run the complex approval scenario</span></span>  
  
1. <span data-ttu-id="2f38c-179">관리자 권한으로 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-179">Open a command prompt with administrator permission.</span></span>  
  
2. <span data-ttu-id="2f38c-180">솔루션이 들어 있는 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-180">Navigate to the directory that contains the solution.</span></span>  
  
3. <span data-ttu-id="2f38c-181">ApprovalClient\Bin\Debug 폴더로 이동하여 ApprovalClient.exe의 네 인스턴스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-181">Navigate to the ApprovalClient\Bin\Debug folder and execute four instances of ApprovalClient.exe.</span></span>  
  
4. <span data-ttu-id="2f38c-182">클릭 **검색**, 될 때까지 대기 합니다 **구독** 단추가 활성화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-182">Click **discover**, wait until the **subscribe** button is enabled.</span></span>  
  
5. <span data-ttu-id="2f38c-183">모든 사용자 이름을 입력 하 고 클릭 **구독**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-183">Type any user name and click **subscribe**.</span></span> <span data-ttu-id="2f38c-184">한 클라이언트에는 `UserType1`을 사용하고 다른 두 클라이언트에는 `UserType2` 형식을, 마지막 클라이언트에는 `UserType3`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-184">For one client use `UserType1`, in two uses type `UserType2`, and in the last use `UserType3`.</span></span>  
  
6. <span data-ttu-id="2f38c-185">`UserType1` 클라이언트의 드롭다운 메뉴에서 단일 승인 유형을 선택하고 문서 이름과 콘텐츠를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-185">In the `UserType1` client, select the single approval type from the drop down menu and type a document name and content.</span></span> <span data-ttu-id="2f38c-186">클릭 **승인 요청**합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-186">Click **Request Approval**.</span></span>  
  
7. <span data-ttu-id="2f38c-187">승인을 기다리는 문서가 두 `UserType2` 클라이언트에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-187">In the `UserType2` clients, a document awaiting approval appears.</span></span> <span data-ttu-id="2f38c-188">선택 하 고 키를 눌러 **승인**, 문서에 전달 되는 `UserType3` 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-188">Select it and press **approve**, the document is passed to the `UserType3` client.</span></span>  
  
     <span data-ttu-id="2f38c-189">첫째 `UserType2` 정족수에서 문서를 승인하면 문서가 `UserType3` 클라이언트로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-189">If the document is approved by the first `UserType2` quorum, the document is passed to the `UserType3` client.</span></span>  
  
8. <span data-ttu-id="2f38c-190">`UserType3` 클라이언트에서 문서를 승인 또는 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-190">Approve or reject the document from the `UserType3` client.</span></span> <span data-ttu-id="2f38c-191">`UserType1` 클라이언트에 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-191">The results should show in the `UserType1` client.</span></span>  
  
##### <a name="to-clean-up"></a><span data-ttu-id="2f38c-192">정리하려면</span><span class="sxs-lookup"><span data-stu-id="2f38c-192">To clean up</span></span>  
  
1. <span data-ttu-id="2f38c-193">Visual Studio 2010 명령 프롬프트에서 DocumentApprovalProcess 폴더로 이동 하 고 Cleanup.cmd를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f38c-193">From a Visual Studio 2010 command prompt, navigate to the DocumentApprovalProcess folder and run Cleanup.cmd.</span></span>
