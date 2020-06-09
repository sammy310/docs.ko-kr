---
title: 장기 실행 워크플로 서비스 만들기
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: 4ae01201230bf848c045158424db60097d8dd767
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599349"
---
# <a name="create-a-long-running-workflow-service"></a><span data-ttu-id="7d6e6-102">장기 실행 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7d6e6-102">Create a Long-running Workflow Service</span></span>

<span data-ttu-id="7d6e6-103">이 항목에서는 장기 실행 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-103">This topic describes how to create a long-running workflow service.</span></span> <span data-ttu-id="7d6e6-104">장기 실행 워크플로 서비스는 장기간 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-104">Long running workflow services may run for long periods of time.</span></span> <span data-ttu-id="7d6e6-105">특정 지점에서 워크플로는 추가 정보를 기다리며 유휴 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-105">At some point the workflow may go idle waiting for some additional information.</span></span> <span data-ttu-id="7d6e6-106">이 경우 워크플로는 SQL 데이터베이스에 유지되고 메모리에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-106">When this occurs the workflow is persisted to a SQL database and is removed from memory.</span></span> <span data-ttu-id="7d6e6-107">추가 정보를 사용할 수 있으면 워크플로 인스턴스가 다시 메모리에 로드되어 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-107">When the additional information becomes available the workflow instance is loaded back into memory and continues executing.</span></span>  <span data-ttu-id="7d6e6-108">이 시나리오에서는 매우 간단한 주문 시스템을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-108">In this scenario you are implementing a very simplified ordering system.</span></span>  <span data-ttu-id="7d6e6-109">클라이언트가 워크플로 서비스에 초기 메시지를 보내 주문을 시작하고,</span><span class="sxs-lookup"><span data-stu-id="7d6e6-109">The client sends an initial message to the workflow service to start the order.</span></span> <span data-ttu-id="7d6e6-110">워크플로 서비스는 주문 ID를 클라이언트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-110">It returns an order ID to the client.</span></span> <span data-ttu-id="7d6e6-111">이 시점에서 워크플로 서비스가 클라이언트에서 다른 메시지를 기다리며 유휴 상태가 되고 SQL Server 데이터베이스에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-111">At this point the workflow service is waiting for another message from the client and goes into the idle state and is persisted to a SQL Server database.</span></span>  <span data-ttu-id="7d6e6-112">클라이언트가 품목을 주문하기 위해 다음 메시지를 보내면 워크플로 서비스는 메모리에 다시 로드되고 주문 처리를 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-112">When the client sends the next message to order an item, the workflow service is loaded back into memory and finishes processing the order.</span></span> <span data-ttu-id="7d6e6-113">코드 샘플에서 워크플로 서비스는 품목이 주문에 추가되었음을 나타내는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-113">In the code sample it returns a string stating the item has been added to the order.</span></span> <span data-ttu-id="7d6e6-114">코드 샘플은 이 기술의 실제 애플리케이션이라기보다는 장기 실행 워크플로 서비스를 보여 주는 간단한 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-114">The code sample is not meant to be a real world application of the technology, but rather a simple sample that illustrates long running workflow services.</span></span> <span data-ttu-id="7d6e6-115">이 항목에서는 Visual Studio 2012 프로젝트 및 솔루션을 만드는 방법을 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-115">This topic assumes you know how to create Visual Studio 2012 projects and solutions.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d6e6-116">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d6e6-116">Prerequisites</span></span>

<span data-ttu-id="7d6e6-117">이 연습을 사용하려면 다음 소프트웨어를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-117">You must have the following software installed to use this walkthrough:</span></span>

1. <span data-ttu-id="7d6e6-118">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="7d6e6-118">Microsoft SQL Server 2008</span></span>

2. <span data-ttu-id="7d6e6-119">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="7d6e6-119">Visual Studio 2012</span></span>

3. <span data-ttu-id="7d6e6-120">Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d6e6-120">Microsoft  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span></span>

4. <span data-ttu-id="7d6e6-121">WCF 및 Visual Studio 2012에 익숙하고 프로젝트/솔루션을 만드는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-121">You are familiar with WCF and Visual Studio 2012 and know how to create projects/solutions.</span></span>

## <a name="set-up-the-sql-database"></a><span data-ttu-id="7d6e6-122">SQL Database 설정</span><span class="sxs-lookup"><span data-stu-id="7d6e6-122">Set up the SQL Database</span></span>

1. <span data-ttu-id="7d6e6-123">워크플로 서비스 인스턴스가 유지되려면 Microsoft SQL Server가 설치되어 있어야 하고 유지된 워크플로 인스턴스를 저장하도록 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-123">In order for workflow service instances to be persisted you must have Microsoft SQL Server installed and you must configure a database to store the persisted workflow instances.</span></span> <span data-ttu-id="7d6e6-124">**시작** 단추를 클릭 하 고 **모든 프로그램**, **Microsoft SQL Server 2008**및 **Microsoft SQL Management Studio**를 선택 하 여 microsoft sql Management Studio를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-124">Run Microsoft SQL Management Studio by clicking the **Start** button, selecting **All Programs**, **Microsoft SQL Server 2008**, and **Microsoft SQL Management Studio**.</span></span>

2. <span data-ttu-id="7d6e6-125">**연결** 단추를 클릭 하 여 SQL Server 인스턴스에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-125">Click the **Connect** button to log on to the SQL Server instance</span></span>

3. <span data-ttu-id="7d6e6-126">트리 뷰에서 **데이터베이스** 를 마우스 오른쪽 단추로 클릭 하 고 **새 데이터베이스를** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-126">Right click **Databases** in the tree view and select **New Database..**</span></span> <span data-ttu-id="7d6e6-127">를 호출 하 여 라는 새 데이터베이스를 만듭니다 `SQLPersistenceStore` .</span><span class="sxs-lookup"><span data-stu-id="7d6e6-127">to create a new database called `SQLPersistenceStore`.</span></span>

4. <span data-ttu-id="7d6e6-128">SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreSchema.sql 스크립트 파일을 실행하여 필요한 데이터베이스 스키마를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-128">Run the SqlWorkflowInstanceStoreSchema.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database schemas.</span></span>

5. <span data-ttu-id="7d6e6-129">SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreLogic.sql 스크립트 파일을 실행하여 필요한 데이터베이스 논리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-129">Run the SqlWorkflowInstanceStoreLogic.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database logic.</span></span>

## <a name="create-the-web-hosted-workflow-service"></a><span data-ttu-id="7d6e6-130">웹 호스팅 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="7d6e6-130">Create the Web Hosted Workflow Service</span></span>

1. <span data-ttu-id="7d6e6-131">빈 Visual Studio 2012 솔루션을 만들고 이름을로 표시 `OrderProcessing` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-131">Create an empty Visual Studio 2012 solution, name it `OrderProcessing`.</span></span>

2. <span data-ttu-id="7d6e6-132">`OrderService`라는 새 WCF 워크플로 서비스 애플리케이션 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-132">Add a new WCF Workflow Service Application project called `OrderService` to the solution.</span></span>

3. <span data-ttu-id="7d6e6-133">프로젝트 속성 대화 상자에서 **웹** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-133">In the project properties dialog, select the **Web** tab.</span></span>

    1. <span data-ttu-id="7d6e6-134">**시작 작업** 에서 **특정 페이지** 를 선택 하 고를 지정 `Service1.xamlx` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-134">Under **Start Action** select **Specific Page** and specify `Service1.xamlx`.</span></span>

        <span data-ttu-id="7d6e6-135">![워크플로 서비스 프로젝트 웹 속성](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "웹 호스팅 워크플로 서비스별 페이지 옵션 만들기")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-135">![Workflow Service Project Web Properties](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Create the web hosted workflow service - Specific Page option")</span></span>

    2. <span data-ttu-id="7d6e6-136">**서버** 에서 **로컬 IIS 웹 서버 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-136">Under **Servers** select **Use Local IIS Web server**.</span></span>

        <span data-ttu-id="7d6e6-137">![로컬 웹 서버 설정](./media/creating-a-long-running-workflow-service/use-local-web-server.png "웹 호스팅 워크플로 서비스 만들기-로컬 IIS 웹 서버 사용 옵션")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-137">![Local Web Server Settings](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Create the web hosted workflow service - Use Local IIS Web Server option")</span></span>

        > [!WARNING]
        > <span data-ttu-id="7d6e6-138">이 설정을 지정 하려면 관리자 모드에서 Visual Studio 2012을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-138">You must run Visual Studio 2012 in administrator mode to make this setting.</span></span>

        <span data-ttu-id="7d6e6-139">이러한 두 단계에서는 IIS에서 호스팅하도록 워크플로 서비스 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-139">These two steps configure the workflow service project to be hosted by IIS.</span></span>

4. <span data-ttu-id="7d6e6-140">`Service1.xamlx`아직 열려 있지 않으면를 열고 기존 **ReceiveRequest** 및 **sendresponse** 활동을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-140">Open `Service1.xamlx` if it is not open already and delete the existing **ReceiveRequest** and **SendResponse** activities.</span></span>

5. <span data-ttu-id="7d6e6-141">**순차 서비스** 활동을 선택 하 고 **변수** 링크를 클릭 하 여 다음 그림에 표시 된 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-141">Select the **Sequential Service** activity and click the **Variables** link and add the variables shown in the following illustration.</span></span> <span data-ttu-id="7d6e6-142">이렇게 하면 워크플로 서비스에서 나중에 사용할 일부 변수가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-142">Doing this adds some variables that will be used later on in the workflow service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d6e6-143">CorrelationHandle가 변수 형식 드롭다운에 없으면 드롭다운에서 **형식 찾아보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-143">If CorrelationHandle is not in the Variable Type drop-down, select **Browse for types** from the drop-down.</span></span> <span data-ttu-id="7d6e6-144">**유형 이름** 상자에 CorrelationHandle를 입력 하 고 목록 상자에서 CorrelationHandle를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-144">Type CorrelationHandle in the **Type name** box, select CorrelationHandle from the listbox and click **OK**.</span></span>

    <span data-ttu-id="7d6e6-145">![변수 추가](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "순차 서비스 활동에 변수를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-145">![Add Variables](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Add variables to the Sequential Service activity.")</span></span>

6. <span data-ttu-id="7d6e6-146">**ReceiveAndSendReply** 활동 템플릿을 **순차적 서비스** 활동으로 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-146">Drag and drop a **ReceiveAndSendReply** activity template into the **Sequential Service** activity.</span></span> <span data-ttu-id="7d6e6-147">이 활동 집합은 클라이언트에서 메시지를 받고 회신을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-147">This set of activities will receive a message from a client and send a reply back.</span></span>

    1. <span data-ttu-id="7d6e6-148">**Receive** 활동을 선택 하 고 다음 그림에 강조 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-148">Select the **Receive** activity and set the properties highlighted in the following illustration.</span></span>

        <span data-ttu-id="7d6e6-149">![Receive 활동 속성 설정](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Receive 활동 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-149">![Set Receive Activity Properties](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Set the Receive activity properties.")</span></span>

        <span data-ttu-id="7d6e6-150">DisplayName 속성은 디자이너에서 표시되는 Receive 활동의 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-150">The DisplayName property sets the name displayed for the Receive activity in the designer.</span></span> <span data-ttu-id="7d6e6-151">ServiceContractName 및 OperationName 속성은 Receive 활동으로 구현되는 서비스 계약 및 작업의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-151">The ServiceContractName and OperationName properties specify the name of the service contract and operation that are implemented by the Receive activity.</span></span> <span data-ttu-id="7d6e6-152">워크플로 서비스에서 계약을 사용 하는 방법에 대 한 자세한 내용은 [워크플로에서 계약 사용](using-contracts-in-workflow.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-152">For more information about how contracts are used in Workflow services see [Using Contracts in Workflow](using-contracts-in-workflow.md).</span></span>

    2. <span data-ttu-id="7d6e6-153">**ReceiveStartOrder** 활동의 **정의 ...** 링크를 클릭 하 고 다음 그림에 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-153">Click the **Define...** link in the **ReceiveStartOrder** activity and set the properties shown in the following illustration.</span></span>  <span data-ttu-id="7d6e6-154">**매개 변수** 라디오 단추가 선택 되어 있고 라는 매개 변수가 `p_customerName` 변수에 바인딩되어 있는지 확인 `customerName` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-154">Notice that the **Parameters** radio button is selected, a parameter named `p_customerName` is bound to the `customerName` variable.</span></span> <span data-ttu-id="7d6e6-155">이렇게 하면 일부 데이터를 수신 하 고 해당 데이터를 로컬 변수에 바인딩하기 위한 **수신** 작업이 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-155">This configures the **Receive** activity to receive some data and bind that data to local variables.</span></span>

        <span data-ttu-id="7d6e6-156">![Receive 활동에서 수신하는 데이터 설정](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "수신 작업에서 수신 하는 데이터에 대 한 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-156">![Setting the data received by the Receive activity](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Set the properties for data received by the Receive activity.")</span></span>

    3. <span data-ttu-id="7d6e6-157">**SendReplyToReceive** 활동을 선택 하 고 다음 그림에 표시 된 것 처럼 강조 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-157">Select The **SendReplyToReceive** activity and set the highlighted property shown in the following illustration.</span></span>

        <span data-ttu-id="7d6e6-158">![SendReply 활동의 속성 설정](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-158">![Setting the properties of the SendReply activity](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span></span>

    4. <span data-ttu-id="7d6e6-159">**SendReplyToStartOrder** 활동의 **정의 ...** 링크를 클릭 하 고 다음 그림에 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-159">Click the **Define...** link in the **SendReplyToStartOrder** activity and set the properties shown in the following illustration.</span></span> <span data-ttu-id="7d6e6-160">**매개 변수** 라디오 단추가 선택 되어 있는지 확인 합니다. 이라는 매개 변수는 `p_orderId` `orderId` 변수에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-160">Notice that the **Parameters** radio button is selected; a parameter named `p_orderId` is bound to the `orderId` variable.</span></span> <span data-ttu-id="7d6e6-161">이 설정은 SendReplyToStartOrder 활동이 문자열 형식의 값을 호출자에게 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-161">This setting specifies that the SendReplyToStartOrder activity will return a value of type string to the caller.</span></span>

        <span data-ttu-id="7d6e6-162">![SendReply 활동 콘텐츠 데이터 구성](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "SetReplyToStartOrder 활동에 대 한 설정을 구성 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-162">![Configuring the SendReply activity content data](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Configure setting for SetReplyToStartOrder activity.")</span></span>

    5. <span data-ttu-id="7d6e6-163">**Receive** 작업과 **SendReply** 활동 간에 Assign 활동을 끌어서 놓고 다음 그림과 같이 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-163">Drag and drop an Assign activity in between the **Receive** and **SendReply** activities and set the properties as shown in the following illustration:</span></span>

        <span data-ttu-id="7d6e6-164">![Assign 활동 추가](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Assign 활동을 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-164">![Adding an assign activity](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Add an assign activity.")</span></span>

        <span data-ttu-id="7d6e6-165">이렇게 하면 새 주문 ID가 만들어지고 orderId 변수에 값이 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-165">This creates a new order ID and places the value in the orderId variable.</span></span>

    6. <span data-ttu-id="7d6e6-166">**ReplyToStartOrder** 활동을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-166">Select the **ReplyToStartOrder** activity.</span></span> <span data-ttu-id="7d6e6-167">속성 창에서 **CorrelationInitializers**에 대 한 줄임표 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-167">In the properties window click the ellipsis button for **CorrelationInitializers**.</span></span> <span data-ttu-id="7d6e6-168">**이니셜라이저 추가** 링크를 선택 하 고 `orderIdHandle` 이니셜라이저 텍스트 상자에를 입력 한 다음 상관 관계 형식에 대해 쿼리 상관 관계 이니셜라이저를 선택 하 고 XPATH 쿼리 드롭다운 상자에서 p_orderId를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-168">Select the **Add initializer** link, enter `orderIdHandle` in the Initializer text box, select Query correlation initializer for the Correlation type, and select p_orderId under the XPATH Queries dropdown box.</span></span> <span data-ttu-id="7d6e6-169">다음 그림에 이러한 설정이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-169">These settings are shown in the following illustration.</span></span> <span data-ttu-id="7d6e6-170">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-170">Click **OK**.</span></span>  <span data-ttu-id="7d6e6-171">클라이언트와 이 워크플로 서비스 인스턴스 간에 상관 관계가 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-171">This initializes a correlation between the client and this instance of the workflow service.</span></span> <span data-ttu-id="7d6e6-172">이 주문 ID가 포함된 메시지가 수신되면 이 워크플로 서비스 인스턴스로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-172">When a message containing this order ID is received it is routed to this instance of the workflow service.</span></span>

        <span data-ttu-id="7d6e6-173">![상관 관계 이니셜라이저 추가](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "상관 관계 이니셜라이저를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-173">![Adding a correlation initializer](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Add a correlation initializer.")</span></span>

7. <span data-ttu-id="7d6e6-174">다른 **ReceiveAndSendReply** 활동을 워크플로 끝 (첫 번째 **Receive** 및 **SendReply** 활동이 포함 된 **시퀀스** 의 외부)에 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-174">Drag and drop another **ReceiveAndSendReply** activity to the end of the workflow (outside the **Sequence** containing the first **Receive** and **SendReply** activities).</span></span> <span data-ttu-id="7d6e6-175">이 활동은 클라이언트에서 보낸 두 번째 메시지를 받고 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-175">This will receive the second message sent by the client and respond to it.</span></span>

    1. <span data-ttu-id="7d6e6-176">새로 추가 된 **Receive** 및 **SendReply** 활동이 포함 된 **시퀀스** 를 선택 하 고 **변수** 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-176">Select the **Sequence** that contains the newly added **Receive** and **SendReply** activities and click the **Variables** button.</span></span> <span data-ttu-id="7d6e6-177">다음 그림에 강조 표시된 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-177">Add the variable highlighted in the following illustration:</span></span>

        <span data-ttu-id="7d6e6-178">![새 변수 추가](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "ItemId 변수를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-178">![Adding new variables](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Add the ItemId variable.")</span></span>

        <span data-ttu-id="7d6e6-179">또한 `orderResult` 범위에 **문자열** 을 추가 `Sequence` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-179">Also add `orderResult` as **String** in the `Sequence` scope.</span></span>

    2. <span data-ttu-id="7d6e6-180">**Receive** 활동을 선택 하 고 다음 그림에 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-180">Select the **Receive** activity and set the properties shown in the following illustration:</span></span>

        <span data-ttu-id="7d6e6-181">![Receive 활동 속성 설정](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "수신 작업 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-181">![Set the Receive activity properties](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Set the Receive activities properties.")</span></span>

        > [!NOTE]
        > <span data-ttu-id="7d6e6-182">**ServiceContractName** 필드를로 변경 해야 `../IAddItem` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-182">Don't forget to change **ServiceContractName** field with `../IAddItem`.</span></span>

    3. <span data-ttu-id="7d6e6-183">**ReceiveAddItem** 활동의 **정의 ...** 링크를 클릭 하 고 다음 그림에 표시 된 매개 변수를 추가 합니다 .이 작업은 두 개의 매개 변수, 즉 주문 id와 주문 된 항목의 id를 수락 하도록 수신 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-183">Click the **Define...** link in the **ReceiveAddItem** activity and add the parameters shown in the following illustration:This configures the receive activity to accept two parameters, the order ID and the ID of the item being ordered.</span></span>

        <span data-ttu-id="7d6e6-184">![두 번째 수신을 위한 매개 변수 지정](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "두 개의 매개 변수를 받도록 receive 작업을 구성 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-184">![Specifying parameters for the second receive](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Configure the receive activity to receive two parameters.")</span></span>

    4. <span data-ttu-id="7d6e6-185">**CorrelateOn** 줄임표 단추를 클릭 하 고을 입력 `orderIdHandle` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-185">Click the **CorrelateOn** ellipsis button and enter `orderIdHandle`.</span></span> <span data-ttu-id="7d6e6-186">**XPath 쿼리**아래에서 드롭다운 화살표를 클릭 하 고를 선택 `p_orderId` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-186">Under **XPath Queries**, click the drop down arrow and select `p_orderId`.</span></span> <span data-ttu-id="7d6e6-187">이렇게 하면 두 번째 Receive 활동에 대한 상관 관계가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-187">This configures the correlation on the second receive activity.</span></span> <span data-ttu-id="7d6e6-188">상관 관계에 대 한 자세한 내용은 참조 하세요 [상관 관계](correlation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-188">For more information about correlation see [Correlation](correlation.md).</span></span>

        <span data-ttu-id="7d6e6-189">![CorrelatesOn 속성 설정](./media/creating-a-long-running-workflow-service/correlateson-setting.png "CorrelatesOn 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-189">![Setting the CorrelatesOn property](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Set the CorrelatesOn property.")</span></span>

    5. <span data-ttu-id="7d6e6-190">**ReceiveAddItem** 활동 바로 뒤에 **If** 활동을 끌어 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-190">Drag and drop an **If** activity immediately after the **ReceiveAddItem** activity.</span></span> <span data-ttu-id="7d6e6-191">이 활동은 if 문처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-191">This activity acts just like an if statement.</span></span>

        1. <span data-ttu-id="7d6e6-192">**Condition** 속성을로 설정 합니다.`itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span><span class="sxs-lookup"><span data-stu-id="7d6e6-192">Set the **Condition** property to `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span></span>

        2. <span data-ttu-id="7d6e6-193">다음 그림에 표시 된 것 처럼 **assign** 활동을 **Then** 섹션에 끌어서 놓고 **Else** 섹션에 다른 **할당** 활동의 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-193">Drag and drop an **Assign** activity in to the **Then** section and another into the **Else** section set the properties of the **Assign** activities as shown in the following illustration.</span></span>

            <span data-ttu-id="7d6e6-194">![서비스 호출 결과 할당](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "서비스 호출의 결과를 할당 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-194">![Assigning the result of the service call](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Assign the result of the service call.")</span></span>

            <span data-ttu-id="7d6e6-195">조건이 이면 `true` **then** 섹션이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-195">If the condition is `true` the **Then** section will be executed.</span></span> <span data-ttu-id="7d6e6-196">조건이 `false` **Else** 섹션이 실행 되 면이 고,</span><span class="sxs-lookup"><span data-stu-id="7d6e6-196">If the condition is `false` the **Else** section is executed.</span></span>

        3. <span data-ttu-id="7d6e6-197">**SendReplyToReceive** 활동을 선택 하 고 다음 그림에 표시 된 **DisplayName** 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-197">Select the **SendReplyToReceive** activity and set the **DisplayName** property shown in the following illustration.</span></span>

            <span data-ttu-id="7d6e6-198">![SendReply 활동 속성 설정](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "SendReply 활동 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-198">![Setting the SendReply activity properties](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Set the SendReply activity property.")</span></span>

        4. <span data-ttu-id="7d6e6-199">**SetReplyToAddItem** 활동의 **정의 ...** 링크를 클릭 하 고 다음 그림과 같이 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-199">Click the **Define ...** link in the **SetReplyToAddItem** activity and configure it as shown in the following illustration.</span></span> <span data-ttu-id="7d6e6-200">이렇게 하면 변수의 값을 반환 하도록 **SendReplyToAddItem** 활동을 구성 `orderResult` 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-200">This configures the **SendReplyToAddItem** activity to return the value in the `orderResult` variable.</span></span>

            <span data-ttu-id="7d6e6-201">![SendReply 활동에 대 한 데이터 바인딩 설정](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "SendReplyToAddItem 활동에 대 한 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="7d6e6-201">![Setting the data binding for the SendReply activity](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Set property for SendReplyToAddItem activity.")</span></span>

8. <span data-ttu-id="7d6e6-202">Web.config 파일을 열고 섹션에 다음 요소를 추가 \<behavior> 하 여 워크플로 지 속성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-202">Open the web.config file and add the following elements in the \<behavior> section to enable workflow persistence.</span></span>

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    > <span data-ttu-id="7d6e6-203">이전 코드 조각의 호스트 및 SQL Server 인스턴스 이름을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-203">Make sure to replace your host and SQL server instance name in the previous code snippet.</span></span>

9. <span data-ttu-id="7d6e6-204">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-204">Build the solution.</span></span>

## <a name="create-a-client-application-to-call-the-workflow-service"></a><span data-ttu-id="7d6e6-205">워크플로 서비스를 호출 하는 클라이언트 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="7d6e6-205">Create a Client Application to Call the Workflow Service</span></span>

1. <span data-ttu-id="7d6e6-206">솔루션에 `OrderClient`라는 새 콘솔 애플리케이션 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-206">Add a new Console application project called `OrderClient` to the solution.</span></span>

2. <span data-ttu-id="7d6e6-207">다음 어셈블리에 대한 참조를 `OrderClient` 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-207">Add references to the following assemblies to the `OrderClient` project</span></span>

    1. <span data-ttu-id="7d6e6-208">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="7d6e6-208">System.ServiceModel.dll</span></span>

    2. <span data-ttu-id="7d6e6-209">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="7d6e6-209">System.ServiceModel.Activities.dll</span></span>

3. <span data-ttu-id="7d6e6-210">서비스 참조를 워크플로 서비스에 추가하고 `OrderService`를 네임스페이스로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-210">Add a service reference to the workflow service and specify `OrderService` as the namespace.</span></span>

4. <span data-ttu-id="7d6e6-211">클라이언트 프로젝트의 `Main()` 메서드에서 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-211">In the `Main()` method of the client project add the following code:</span></span>

    ```csharp
    static void Main(string[] args)
    {
       // Send initial message to start the workflow service
       Console.WriteLine("Sending start message");
       StartOrderClient startProxy = new StartOrderClient();
       string orderId = startProxy.StartOrder("Kim Abercrombie");

       // The workflow service is now waiting for the second message to be sent
       Console.WriteLine("Workflow service is idle...");
       Console.WriteLine("Press [ENTER] to send an add item message to reactivate the workflow service...");
       Console.ReadLine();

       // Send the second message
       Console.WriteLine("Sending add item message");
       AddItemClient addProxy = new AddItemClient();
       AddItem item = new AddItem();
       item.p_itemId = "Zune HD";
       item.p_orderId = orderId;

       string orderResult = addProxy.AddItem(item);
       Console.WriteLine("Service returned: " + orderResult);
    }
    ```

5. <span data-ttu-id="7d6e6-212">솔루션을 빌드하고 `OrderClient` 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-212">Build the solution and run the `OrderClient` application.</span></span> <span data-ttu-id="7d6e6-213">클라이언트에서 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-213">The client will display the following text:</span></span>

    ```output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. <span data-ttu-id="7d6e6-214">워크플로 서비스가 지속 되었는지 확인 하려면 **시작** 메뉴로 이동 하 여 **모든 프로그램**, **Microsoft SQL Server 2008** **SQL Server Management Studio**를 선택 하 여 SQL Server Management Studio를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-214">To verify that the workflow service has been persisted, start the SQL Server Management Studio by going to the **Start** menu, Selecting **All Programs**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span></span>

    1. <span data-ttu-id="7d6e6-215">왼쪽 창에서 **데이터베이스**, **SQLPersistenceStore**, **뷰** 를 확장 하 고 **DurableInstancing** 를 마우스 오른쪽 단추로 클릭 한 다음 **상위 1000 행 선택**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-215">In the left hand pane expand, **Databases**, **SQLPersistenceStore**, **Views** and right click **System.Activities.DurableInstancing.Instances** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="7d6e6-216">**결과** 창에서 하나 이상의 인스턴스가 나열 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-216">In the **Results** pane verify you see at least one instance listed.</span></span> <span data-ttu-id="7d6e6-217">실행하는 동안 예외가 발생한 경우 이전 실행의 다른 인스턴스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-217">There may be other instances from prior runs if an exception occurred while running.</span></span> <span data-ttu-id="7d6e6-218">**DurableInstancing** 를 마우스 오른쪽 단추로 클릭 하 고 **상위 200 행 편집**을 선택한 다음 **실행** 단추를 누르고 결과 창에서 모든 행을 선택한 다음 **삭제**를 선택 하 여 기존 행을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-218">You can delete existing rows by right clicking **System.Activities.DurableInstancing.Instances** and selecting **Edit Top 200 rows**, pressing the **Execute** button, selecting all rows in the results pane and selecting **delete**.</span></span>  <span data-ttu-id="7d6e6-219">데이터베이스에 표시되는 인스턴스가 애플리케이션에서 만든 인스턴스인지 확인하려면 클라이언트를 실행하기 전에 인스턴스 뷰가 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-219">To verify the instance displayed in the database is the instance your application created, verify the instances view is empty prior to running the client.</span></span> <span data-ttu-id="7d6e6-220">클라이언트가 실행되고 있으면 쿼리(상위 1000개의 행 선택)를 다시 실행하고 새 인스턴스가 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-220">Once the client is running re-run the query (Select Top 1000 Rows) and verify a new instance has been added.</span></span>

7. <span data-ttu-id="7d6e6-221">Enter 키를 눌러 워크플로 서비스에 품목 추가 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-221">Press enter to send the add item message to the workflow service.</span></span> <span data-ttu-id="7d6e6-222">클라이언트에서 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d6e6-222">The client will display the following text:</span></span>

    ```output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a><span data-ttu-id="7d6e6-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d6e6-223">See also</span></span>

- [<span data-ttu-id="7d6e6-224">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="7d6e6-224">Workflow Services</span></span>](workflow-services.md)
