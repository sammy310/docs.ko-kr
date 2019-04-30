---
title: 장기 실행 워크플로 서비스 만들기
ms.date: 03/30/2017
ms.assetid: 4c39bd04-5b8a-4562-a343-2c63c2821345
ms.openlocfilehash: ac0cb83ad428ce98a05fd0626fff835162ad0e41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62048145"
---
# <a name="creating-a-long-running-workflow-service"></a><span data-ttu-id="9b806-102">장기 실행 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="9b806-102">Creating a Long-running Workflow Service</span></span>
<span data-ttu-id="9b806-103">이 항목에서는 장기 실행 워크플로 서비스를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-103">This topic describes how to create a long-running workflow service.</span></span> <span data-ttu-id="9b806-104">장기 실행 워크플로 서비스는 장기간 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-104">Long running workflow services may run for long periods of time.</span></span> <span data-ttu-id="9b806-105">특정 지점에서 워크플로는 추가 정보를 기다리며 유휴 상태가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-105">At some point the workflow may go idle waiting for some additional information.</span></span> <span data-ttu-id="9b806-106">이 경우 워크플로는 SQL 데이터베이스에 유지되고 메모리에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-106">When this occurs the workflow is persisted to a SQL database and is removed from memory.</span></span> <span data-ttu-id="9b806-107">추가 정보를 사용할 수 있으면 워크플로 인스턴스가 다시 메모리에 로드되어 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-107">When the additional information becomes available the workflow instance is loaded back into memory and continues executing.</span></span>  <span data-ttu-id="9b806-108">이 시나리오에서는 매우 간단한 주문 시스템을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-108">In this scenario you are implementing a very simplified ordering system.</span></span>  <span data-ttu-id="9b806-109">클라이언트가 워크플로 서비스에 초기 메시지를 보내 주문을 시작하고,</span><span class="sxs-lookup"><span data-stu-id="9b806-109">The client sends an initial message to the workflow service to start the order.</span></span> <span data-ttu-id="9b806-110">워크플로 서비스는 주문 ID를 클라이언트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-110">It returns an order ID to the client.</span></span> <span data-ttu-id="9b806-111">이 시점에서 워크플로 서비스가 클라이언트에서 다른 메시지를 기다리며 유휴 상태가 되고 SQL Server 데이터베이스에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-111">At this point the workflow service is waiting for another message from the client and goes into the idle state and is persisted to a SQL Server database.</span></span>  <span data-ttu-id="9b806-112">클라이언트가 품목을 주문하기 위해 다음 메시지를 보내면 워크플로 서비스는 메모리에 다시 로드되고 주문 처리를 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-112">When the client sends the next message to order an item, the workflow service is loaded back into memory and finishes processing the order.</span></span> <span data-ttu-id="9b806-113">코드 샘플에서 워크플로 서비스는 품목이 주문에 추가되었음을 나타내는 문자열을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-113">In the code sample it returns a string stating the item has been added to the order.</span></span> <span data-ttu-id="9b806-114">코드 샘플은 이 기술의 실제 응용 프로그램이라기보다는 장기 실행 워크플로 서비스를 보여 주는 간단한 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-114">The code sample is not meant to be a real world application of the technology, but rather a simple sample that illustrates long running workflow services.</span></span> <span data-ttu-id="9b806-115">이 항목을 Visual Studio 2012 프로젝트 및 솔루션을 만드는 방법을 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-115">This topic assumes you know how to create Visual Studio 2012 projects and solutions.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9b806-116">전제 조건</span><span class="sxs-lookup"><span data-stu-id="9b806-116">Prerequisites</span></span>
 <span data-ttu-id="9b806-117">이 연습을 사용하려면 다음 소프트웨어를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-117">You must have the following software installed to use this walkthrough:</span></span>

1. <span data-ttu-id="9b806-118">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9b806-118">Microsoft SQL Server 2008</span></span>

2. <span data-ttu-id="9b806-119">Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="9b806-119">Visual Studio 2012</span></span>

3. <span data-ttu-id="9b806-120">Microsoft [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b806-120">Microsoft  [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]</span></span>

4. <span data-ttu-id="9b806-121">WCF 및 Visual Studio 2012를 사용 하 여 알고 있으며 프로젝트/솔루션을 만드는 방법을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-121">You are familiar with WCF and Visual Studio 2012 and know how to create projects/solutions.</span></span>

### <a name="to-setup-the-sql-database"></a><span data-ttu-id="9b806-122">SQL 데이터베이스를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9b806-122">To Setup the SQL Database</span></span>

1. <span data-ttu-id="9b806-123">워크플로 서비스 인스턴스가 유지되려면 Microsoft SQL Server가 설치되어 있어야 하고 유지된 워크플로 인스턴스를 저장하도록 데이터베이스를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-123">In order for workflow service instances to be persisted you must have Microsoft SQL Server installed and you must configure a database to store the persisted workflow instances.</span></span> <span data-ttu-id="9b806-124">클릭 하 여 Microsoft SQL Management Studio를 실행 합니다 **시작** 단추를 선택 하 **프로그램도**, **Microsoft SQL Server 2008**, 및 **Microsoft SQL Management Studio**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-124">Run Microsoft SQL Management Studio by clicking the **Start** button, selecting **All Programs**, **Microsoft SQL Server 2008**, and **Microsoft SQL Management Studio**.</span></span>

2. <span data-ttu-id="9b806-125">클릭 합니다 **Connect** SQL Server 인스턴스에 로그온 하는 단추</span><span class="sxs-lookup"><span data-stu-id="9b806-125">Click the **Connect** button to log on to the SQL Server instance</span></span>

3. <span data-ttu-id="9b806-126">마우스 오른쪽 단추로 클릭 **데이터베이스** 트리 뷰 및 선택 **새 데이터베이스...**</span><span class="sxs-lookup"><span data-stu-id="9b806-126">Right click **Databases** in the tree view and select **New Database..**</span></span> <span data-ttu-id="9b806-127">라는 새 데이터베이스를 만들려면 `SQLPersistenceStore`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-127">to create a new database called `SQLPersistenceStore`.</span></span>

4. <span data-ttu-id="9b806-128">SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreSchema.sql 스크립트 파일을 실행하여 필요한 데이터베이스 스키마를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-128">Run the SqlWorkflowInstanceStoreSchema.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database schemas.</span></span>

5. <span data-ttu-id="9b806-129">SQLPersistenceStore 데이터베이스의 C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en 디렉터리에 있는 SqlWorkflowInstanceStoreLogic.sql 스크립트 파일을 실행하여 필요한 데이터베이스 논리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-129">Run the SqlWorkflowInstanceStoreLogic.sql script file located in the C:\Windows\Microsoft.NET\Framework\v4.0\SQL\en directory on the SQLPersistenceStore database to set up the needed database logic.</span></span>

### <a name="to-create-the-web-hosted-workflow-service"></a><span data-ttu-id="9b806-130">웹 호스팅 워크플로 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9b806-130">To Create the Web Hosted Workflow Service</span></span>

1. <span data-ttu-id="9b806-131">빈 Visual Studio 2012 솔루션을 만들고, 이름을 `OrderProcessing`입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-131">Create an empty Visual Studio 2012 solution, name it `OrderProcessing`.</span></span>

2. <span data-ttu-id="9b806-132">`OrderService`라는 새 WCF 워크플로 서비스 응용 프로그램 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-132">Add a new WCF Workflow Service Application project called `OrderService` to the solution.</span></span>

3. <span data-ttu-id="9b806-133">프로젝트 속성 대화 상자에서 선택 합니다 **웹** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-133">In the project properties dialog, select the **Web** tab.</span></span>

    1. <span data-ttu-id="9b806-134">아래 **시작 작업** 선택 **특정 페이지** 지정 `Service1.xamlx`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-134">Under **Start Action** select **Specific Page** and specify `Service1.xamlx`.</span></span>

         <span data-ttu-id="9b806-135">![워크플로 서비스 프로젝트 웹 속성](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "특정 페이지 옵션-웹 호스팅 워크플로 서비스를 만들려면")</span><span class="sxs-lookup"><span data-stu-id="9b806-135">![Workflow Service Project Web Properties](./media/creating-a-long-running-workflow-service/start-action-specific-page-option.png "Create the web hosted workflow service - Specific Page option")</span></span>

    2. <span data-ttu-id="9b806-136">아래 **서버** 선택 **사용 하 여 로컬 IIS 웹 서버**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-136">Under **Servers** select **Use Local IIS Web server**.</span></span>

         <span data-ttu-id="9b806-137">![로컬 웹 서버 설정](./media/creating-a-long-running-workflow-service/use-local-web-server.png "옵션 사용 하 여 로컬 IIS 웹 서버-웹 호스팅 워크플로 서비스를 만들려면")</span><span class="sxs-lookup"><span data-stu-id="9b806-137">![Local Web Server Settings](./media/creating-a-long-running-workflow-service/use-local-web-server.png "Create the web hosted workflow service - Use Local IIS Web Server option")</span></span>

        > [!WARNING]
        >  <span data-ttu-id="9b806-138">이 설정을 지정 하려면 관리자 모드에서 Visual Studio 2012를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-138">You must run Visual Studio 2012 in administrator mode to make this setting.</span></span>

         <span data-ttu-id="9b806-139">이러한 두 단계에서는 IIS에서 호스팅하도록 워크플로 서비스 프로젝트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-139">These two steps configure the workflow service project to be hosted by IIS.</span></span>

4. <span data-ttu-id="9b806-140">엽니다 `Service1.xamlx` 것이 열려 없고 기존 삭제 하는 경우 **ReceiveRequest** 하 고 **SendResponse** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-140">Open `Service1.xamlx` if it is not open already and delete the existing **ReceiveRequest** and **SendResponse** activities.</span></span>

5. <span data-ttu-id="9b806-141">선택 합니다 **순차 서비스** 활동을 클릭 합니다 **변수** 에 연결 하 고 다음 그림과에서 같이 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-141">Select the **Sequential Service** activity and click the **Variables** link and add the variables shown in the following illustration.</span></span> <span data-ttu-id="9b806-142">이렇게 하면 워크플로 서비스에서 나중에 사용할 일부 변수가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-142">Doing this adds some variables that will be used later on in the workflow service.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9b806-143">CorrelationHandle 변수 형식 드롭다운 목록에 없는 경우 선택 **형식에 대 한 찾아보기** 드롭다운 목록에서.</span><span class="sxs-lookup"><span data-stu-id="9b806-143">If CorrelationHandle is not in the Variable Type drop-down, select **Browse for types** from the drop-down.</span></span> <span data-ttu-id="9b806-144">에 CorrelationHandle을 입력 합니다 **형식 이름을** 상자, 목록 상자에서 CorrelationHandle을 선택 및 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-144">Type CorrelationHandle in the **Type name** box, select CorrelationHandle from the listbox and click **OK**.</span></span>

     <span data-ttu-id="9b806-145">![변수 추가](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "순차 서비스 작업에 변수를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-145">![Add Variables](./media/creating-a-long-running-workflow-service/add-variables-sequential-service-activity.gif "Add variables to the Sequential Service activity.")</span></span>

6. <span data-ttu-id="9b806-146">끌어서 놓기는 **ReceiveAndSendReply** 활동 템플릿을 합니다 **순차 서비스** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-146">Drag and drop a **ReceiveAndSendReply** activity template into the **Sequential Service** activity.</span></span> <span data-ttu-id="9b806-147">이 활동 집합은 클라이언트에서 메시지를 받고 회신을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-147">This set of activities will receive a message from a client and send a reply back.</span></span>

    1. <span data-ttu-id="9b806-148">선택 된 **수신** 활동 하 고 다음 그림에 강조 표시 된 속성 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-148">Select the **Receive** activity and set the properties highlighted in the following illustration.</span></span>

         <span data-ttu-id="9b806-149">![수신 활동 속성 설정](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Receive 활동 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-149">![Set Receive Activity Properties](./media/creating-a-long-running-workflow-service/set-receive-activity-properties.png "Set the Receive activity properties.")</span></span>

         <span data-ttu-id="9b806-150">DisplayName 속성은 디자이너에서 표시되는 Receive 활동의 이름을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-150">The DisplayName property sets the name displayed for the Receive activity in the designer.</span></span> <span data-ttu-id="9b806-151">ServiceContractName 및 OperationName 속성은 Receive 활동으로 구현되는 서비스 계약 및 작업의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-151">The ServiceContractName and OperationName properties specify the name of the service contract and operation that are implemented by the Receive activity.</span></span> <span data-ttu-id="9b806-152">워크플로 서비스에서 계약을 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [워크플로에서 계약 사용 하 여](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-152">For more information about how contracts are used in Workflow services see [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>

    2. <span data-ttu-id="9b806-153">클릭 된 **정의 하는 중...**  링크를 **ReceiveStartOrder** 활동 하 고 다음 그림에 표시 되는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-153">Click the **Define...** link in the **ReceiveStartOrder** activity and set the properties shown in the following illustration.</span></span>  <span data-ttu-id="9b806-154">있음을 합니다 **매개 변수** 라디오 단추를 선택 하면 라는 매개 변수 `p_customerName` 바인딩되는 `customerName` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-154">Notice that the **Parameters** radio button is selected, a parameter named `p_customerName` is bound to the `customerName` variable.</span></span> <span data-ttu-id="9b806-155">이 구성 합니다 **수신** 을 일부 데이터를 받아서 로컬 변수에 바인딩하도록 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-155">This configures the **Receive** activity to receive some data and bind that data to local variables.</span></span>

         <span data-ttu-id="9b806-156">![받기 작업에서 받은 데이터를 설정](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "받기 작업에서 받은 데이터에 대 한 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-156">![Setting the data received by the Receive activity](./media/creating-a-long-running-workflow-service/set-properties-for-receive-content.png "Set the properties for data received by the Receive activity.")</span></span>

    3. <span data-ttu-id="9b806-157">선택 된 **SendReplyToReceive** 활동 하 고 다음 그림과에서 같이 강조 표시 된 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-157">Select The **SendReplyToReceive** activity and set the highlighted property shown in the following illustration.</span></span>

         <span data-ttu-id="9b806-158">![SendReply 활동의 속성을 설정](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span><span class="sxs-lookup"><span data-stu-id="9b806-158">![Setting the properties of the SendReply activity](./media/creating-a-long-running-workflow-service/set-properties-for-reply-activities.png "SetReplyProperties")</span></span>

    4. <span data-ttu-id="9b806-159">클릭 된 **정의 하는 중...**  링크를 **SendReplyToStartOrder** 활동 하 고 다음 그림에 표시 되는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-159">Click the **Define...** link in the **SendReplyToStartOrder** activity and set the properties shown in the following illustration.</span></span> <span data-ttu-id="9b806-160">있음을 합니다 **매개 변수** 라디오 단추가 선택 되어; 라는 매개 변수가 `p_orderId` 바인딩되는 `orderId` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-160">Notice that the **Parameters** radio button is selected; a parameter named `p_orderId` is bound to the `orderId` variable.</span></span> <span data-ttu-id="9b806-161">이 설정은 SendReplyToStartOrder 활동이 문자열 형식의 값을 호출자에게 반환하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-161">This setting specifies that the SendReplyToStartOrder activity will return a value of type string to the caller.</span></span>

         <span data-ttu-id="9b806-162">![SendReply 활동 콘텐츠 데이터 구성](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "SetReplyToStartOrder 활동에 대 한 설정을 구성 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-162">![Configuring the SendReply activity content data](./media/creating-a-long-running-workflow-service/setreplycontent-for-sendreplytostartorder-activity.png "Configure setting for SetReplyToStartOrder activity.")</span></span>

    5. <span data-ttu-id="9b806-163">Assign 활동을 사이 놓습니다 합니다 **수신** 하 고 **SendReply** 활동 다음 그림에 표시 된 대로 속성을 설정:</span><span class="sxs-lookup"><span data-stu-id="9b806-163">Drag and drop an Assign activity in between the **Receive** and **SendReply** activities and set the properties as shown in the following illustration:</span></span>

         <span data-ttu-id="9b806-164">![Assign 활동 추가](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "assign 활동을 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-164">![Adding an assign activity](./media/creating-a-long-running-workflow-service/add-an-assign-activity.png "Add an assign activity.")</span></span>

         <span data-ttu-id="9b806-165">이렇게 하면 새 주문 ID가 만들어지고 orderId 변수에 값이 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-165">This creates a new order ID and places the value in the orderId variable.</span></span>

    6. <span data-ttu-id="9b806-166">선택 된 **ReplyToStartOrder** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-166">Select the **ReplyToStartOrder** activity.</span></span> <span data-ttu-id="9b806-167">속성 창에서 줄임표 단추를 클릭 **CorrelationInitializers**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-167">In the properties window click the ellipsis button for **CorrelationInitializers**.</span></span> <span data-ttu-id="9b806-168">선택 된 **이니셜라이저 추가** 링크를 입력 `orderIdHandle` 이니셜라이저 텍스트 상자에서 상관 관계 형식에 대 한 쿼리 상관 관계 이니셜라이저를 선택 하 고 XPATH 쿼리 드롭다운 상자에서 p_orderId를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-168">Select the **Add initializer** link, enter `orderIdHandle` in the Initializer text box, select Query correlation initializer for the Correlation type, and select p_orderId under the XPATH Queries dropdown box.</span></span> <span data-ttu-id="9b806-169">이러한 설정이 다음 그림에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-169">These settings are shown in the following illustration.</span></span> <span data-ttu-id="9b806-170">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-170">Click **OK**.</span></span>  <span data-ttu-id="9b806-171">클라이언트와 이 워크플로 서비스 인스턴스 간에 상관 관계가 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-171">This initializes a correlation between the client and this instance of the workflow service.</span></span> <span data-ttu-id="9b806-172">이 주문 ID가 포함된 메시지가 수신되면 이 워크플로 서비스 인스턴스로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-172">When a message containing this order ID is received it is routed to this instance of the workflow service.</span></span>

         <span data-ttu-id="9b806-173">![상관 관계 이니셜라이저 추가](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "상관 관계 이니셜라이저를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-173">![Adding a correlation initializer](./media/creating-a-long-running-workflow-service/add-correlationinitializers.png "Add a correlation initializer.")</span></span>

7. <span data-ttu-id="9b806-174">끌어서 놓기 다른 **ReceiveAndSendReply** 활동을 워크플로의 끝 (외부 합니다 **시퀀스** 첫 번째 포함 된 **수신** 및  **SendReply** 활동).</span><span class="sxs-lookup"><span data-stu-id="9b806-174">Drag and drop another **ReceiveAndSendReply** activity to the end of the workflow (outside the **Sequence** containing the first **Receive** and **SendReply** activities).</span></span> <span data-ttu-id="9b806-175">이 활동은 클라이언트에서 보낸 두 번째 메시지를 받고 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-175">This will receive the second message sent by the client and respond to it.</span></span>

    1. <span data-ttu-id="9b806-176">선택 된 **시퀀스** 포함 하는 새로 추가 된 **수신** 및 **SendReply** 활동 하 고를 **변수** 단추.</span><span class="sxs-lookup"><span data-stu-id="9b806-176">Select the **Sequence** that contains the newly added **Receive** and **SendReply** activities and click the **Variables** button.</span></span> <span data-ttu-id="9b806-177">다음 그림에 강조 표시된 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-177">Add the variable highlighted in the following illustration:</span></span>

         <span data-ttu-id="9b806-178">![새 변수를 추가](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "ItemId 변수를 추가 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-178">![Adding new variables](./media/creating-a-long-running-workflow-service/add-the-itemid-variable.png "Add the ItemId variable.")</span></span>

    2. <span data-ttu-id="9b806-179">선택 된 **수신** 활동 하 고 다음 그림에 표시 되는 속성을 설정:</span><span class="sxs-lookup"><span data-stu-id="9b806-179">Select the **Receive** activity and set the properties shown in the following illustration:</span></span>

         <span data-ttu-id="9b806-180">![Receive 활동 속성 설정](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Receive 활동 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-180">![Set the Receive acitivity properties](./media/creating-a-long-running-workflow-service/set-receive-activities-properties.png "Set the Receive activities properties.")</span></span>

    3. <span data-ttu-id="9b806-181">클릭 된 **정의 하는 중...**  링크를 **ReceiveAddItem** 활동 하 고 다음 그림에 나와 있는 매개 변수를 추가:이 두 매개 변수를 주문 ID와 주문 되는 항목의 ID를 수락 하도록 수신 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-181">Click the **Define...** link in the **ReceiveAddItem** activity and add the parameters shown in the following illustration:This configures the receive activity to accept two parameters, the order ID and the ID of the item being ordered.</span></span>

         <span data-ttu-id="9b806-182">![두 번째 수신에 대 한 매개 변수 지정](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "두 매개 변수를 받을 수신 작업을 구성 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-182">![Specifying parameters for the second receive](./media/creating-a-long-running-workflow-service/add-receive-two-parameters.png "Configure the receive activity to receive two parameters.")</span></span>

    4. <span data-ttu-id="9b806-183">클릭 합니다 **CorrelateOn** 줄임표 (...) 단추 및 입력 `orderIdHandle`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-183">Click the **CorrelateOn** ellipsis button and enter `orderIdHandle`.</span></span> <span data-ttu-id="9b806-184">아래 **XPath 쿼리에**, 드롭다운 화살표를 클릭 하 고 선택 `p_orderId`합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-184">Under **XPath Queries**, click the drop down arrow and select `p_orderId`.</span></span> <span data-ttu-id="9b806-185">이렇게 하면 두 번째 Receive 활동에 대한 상관 관계가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-185">This configures the correlation on the second receive activity.</span></span> <span data-ttu-id="9b806-186">상관 관계에 대 한 자세한 내용은 참조 하세요 [상관 관계](../../../../docs/framework/wcf/feature-details/correlation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-186">For more information about correlation see [Correlation](../../../../docs/framework/wcf/feature-details/correlation.md).</span></span>

         <span data-ttu-id="9b806-187">![CorrelatesOn 속성 설정](./media/creating-a-long-running-workflow-service/correlateson-setting.png "CorrelatesOn 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-187">![Setting the CorrelatesOn property](./media/creating-a-long-running-workflow-service/correlateson-setting.png "Set the CorrelatesOn property.")</span></span>

    5. <span data-ttu-id="9b806-188">끌어서 놓기는 **하는 경우** 활동 직후 합니다 **ReceiveAddItem** 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-188">Drag and drop an **If** activity immediately after the **ReceiveAddItem** activity.</span></span> <span data-ttu-id="9b806-189">이 활동은 if 문처럼 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-189">This activity acts just like an if statement.</span></span>

        1. <span data-ttu-id="9b806-190">설정 된 **조건을** 속성 `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span><span class="sxs-lookup"><span data-stu-id="9b806-190">Set the **Condition** property to `itemId=="Zune HD" (itemId="Zune HD" for Visual Basic)`</span></span>

        2. <span data-ttu-id="9b806-191">끌어서 놓기는 **할당** 활동을 합니다 **다음** 섹션과에 다른를 **Else** 섹션의 속성을 설정 합니다 **할당** 다음 그림에 나와 있는 것 처럼 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-191">Drag and drop an **Assign** activity in to the **Then** section and another into the **Else** section set the properties of the **Assign** activities as shown in the following illustration.</span></span>

             <span data-ttu-id="9b806-192">![서비스 호출의 결과 할당](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "서비스 호출의 결과 할당 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-192">![Assigning the result of the service call](./media/creating-a-long-running-workflow-service/assign-result-of-service-call.png "Assign the result of the service call.")</span></span>

             <span data-ttu-id="9b806-193">조건이 `true` 는 **한 다음** 섹션 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-193">If the condition is `true` the **Then** section will be executed.</span></span> <span data-ttu-id="9b806-194">조건이 `false` 는 **Else** 섹션이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-194">If the condition is `false` the **Else** section is executed.</span></span>

        3. <span data-ttu-id="9b806-195">선택 합니다 **SendReplyToReceive** 활동 집합과 합니다 **DisplayName** 다음 그림에 표시 된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-195">Select the **SendReplyToReceive** activity and set the **DisplayName** property shown in the following illustration.</span></span>

             <span data-ttu-id="9b806-196">![SendReply 활동 속성 설정](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "SendReply 활동 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-196">![Setting the SendReply activity properties](./media/creating-a-long-running-workflow-service/send-reply-activity-property.png "Set the SendReply activity property.")</span></span>

        4. <span data-ttu-id="9b806-197">클릭 된 **정의 하는 중...**  링크를 **SetReplyToAddItem** 활동 하 고 다음 그림과에서 같이 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-197">Click the **Define ...** link in the **SetReplyToAddItem** activity and configure it as shown in the following illustration.</span></span> <span data-ttu-id="9b806-198">이 구성 합니다 **SendReplyToAddItem** 의 값을 반환 하는 작업을 `orderResult` 변수.</span><span class="sxs-lookup"><span data-stu-id="9b806-198">This configures the **SendReplyToAddItem** activity to return the value in the `orderResult` variable.</span></span>

             <span data-ttu-id="9b806-199">![SendReply 활동에 대 한 데이터 바인딩 설정](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "SendReplyToAddItem 활동에 대 한 속성을 설정 합니다.")</span><span class="sxs-lookup"><span data-stu-id="9b806-199">![Setting the data binding for the SendReply activity](./media/creating-a-long-running-workflow-service/set-property-for-sendreplytoadditem.gif "Set property for SendReplyToAddItem activity.")</span></span>

8. <span data-ttu-id="9b806-200">Web.config 파일을 열고 다음 요소에 추가 된 \<동작 > 섹션 워크플로 지 속성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-200">Open the web.config file and add the following elements in the \<behavior> section to enable workflow persistence.</span></span>

    ```xml
    <sqlWorkflowInstanceStore connectionString="Data Source=your-machine\SQLExpress;Initial Catalog=SQLPersistenceStore;Integrated Security=True;Asynchronous Processing=True" instanceEncodingOption="None" instanceCompletionAction="DeleteAll" instanceLockedExceptionAction="BasicRetry" hostLockRenewalPeriod="00:00:30" runnableInstancesDetectionPeriod="00:00:02" />
              <workflowIdle timeToUnload="0"/>
    ```

    > [!WARNING]
    >  <span data-ttu-id="9b806-201">이전 코드 조각의 호스트 및 SQL Server 인스턴스 이름을 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-201">Make sure to replace your host and SQL server instance name in the previous code snippet.</span></span>

9. <span data-ttu-id="9b806-202">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-202">Build the solution.</span></span>

### <a name="to-create-a-client-application-to-call-the-workflow-service"></a><span data-ttu-id="9b806-203">클라이언트 응용 프로그램을 만들어 워크플로 서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="9b806-203">To Create a Client Application to Call the Workflow Service</span></span>

1. <span data-ttu-id="9b806-204">솔루션에 `OrderClient`라는 새 콘솔 응용 프로그램 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-204">Add a new Console application project called `OrderClient` to the solution.</span></span>

2. <span data-ttu-id="9b806-205">다음 어셈블리에 대한 참조를 `OrderClient` 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-205">Add references to the following assemblies to the `OrderClient` project</span></span>

    1. <span data-ttu-id="9b806-206">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="9b806-206">System.ServiceModel.dll</span></span>

    2. <span data-ttu-id="9b806-207">System.ServiceModel.Activities.dll</span><span class="sxs-lookup"><span data-stu-id="9b806-207">System.ServiceModel.Activities.dll</span></span>

3. <span data-ttu-id="9b806-208">서비스 참조를 워크플로 서비스에 추가하고 `OrderService`를 네임스페이스로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-208">Add a service reference to the workflow service and specify `OrderService` as the namespace.</span></span>

4. <span data-ttu-id="9b806-209">클라이언트 프로젝트의 `Main()` 메서드에서 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-209">In the `Main()` method of the client project add the following code:</span></span>

    ```
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

5. <span data-ttu-id="9b806-210">솔루션을 빌드하고 `OrderClient` 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-210">Build the solution and run the `OrderClient` application.</span></span> <span data-ttu-id="9b806-211">클라이언트에서 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-211">The client will display the following text:</span></span>

    ```Output
    Sending start messageWorkflow service is idle...Press [ENTER] to send an add item message to reactivate the workflow service...
    ```

6. <span data-ttu-id="9b806-212">워크플로 서비스가 유지 되었는지 있는지를 확인 하려면로 이동 하 여 SQL Server Management Studio를 시작 합니다 **시작** 메뉴를 선택 하면 **모든 프로그램**, **Microsoft SQL Server 2008**하십시오 **SQL Server Management Studio**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-212">To verify that the workflow service has been persisted, start the SQL Server Management Studio by going to the **Start** menu, Selecting **All Programs**, **Microsoft SQL Server 2008**, **SQL Server Management Studio**.</span></span>

    1. <span data-ttu-id="9b806-213">왼쪽 창에서 다음을 확장 합니다 **데이터베이스**, **SQLPersistenceStore**하십시오 **뷰** 마우스 오른쪽 단추로 클릭 **System.Activities.DurableInstancing.Instances**  선택한 **상위 1000 개의 행 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-213">In the left hand pane expand, **Databases**, **SQLPersistenceStore**, **Views** and right click **System.Activities.DurableInstancing.Instances** and select **Select Top 1000 Rows**.</span></span> <span data-ttu-id="9b806-214">에 **결과** 창 확인 나열 된 하나 이상의 인스턴스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b806-214">In the **Results** pane verify you see at least one instance listed.</span></span> <span data-ttu-id="9b806-215">실행하는 동안 예외가 발생한 경우 이전 실행의 다른 인스턴스가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-215">There may be other instances from prior runs if an exception occurred while running.</span></span> <span data-ttu-id="9b806-216">마우스 오른쪽 단추로 클릭 하 여 기존 행을 삭제할 수 있습니다 **System.Activities.DurableInstancing.Instances** 를 선택 하 고 **편집 상위 200 개 행**를 누르면 합니다 **Execute** 단추를 결과 창에서 모든 행을 선택 하 고 선택 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-216">You can delete existing rows by right clicking **System.Activities.DurableInstancing.Instances** and selecting **Edit Top 200 rows**, pressing the **Execute** button, selecting all rows in the results pane and selecting **delete**.</span></span>  <span data-ttu-id="9b806-217">데이터베이스에 표시되는 인스턴스가 응용 프로그램에서 만든 인스턴스인지 확인하려면 클라이언트를 실행하기 전에 인스턴스 뷰가 비어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-217">To verify the instance displayed in the database is the instance your application created, verify the instances view is empty prior to running the client.</span></span> <span data-ttu-id="9b806-218">클라이언트가 실행되고 있으면 쿼리(상위 1000개의 행 선택)를 다시 실행하고 새 인스턴스가 추가되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-218">Once the client is running re-run the query (Select Top 1000 Rows) and verify a new instance has been added.</span></span>

7. <span data-ttu-id="9b806-219">Enter 키를 눌러 워크플로 서비스에 품목 추가 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-219">Press enter to send the add item message to the workflow service.</span></span> <span data-ttu-id="9b806-220">클라이언트에서 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b806-220">The client will display the following text:</span></span>

    ```Output
    Sending add item messageService returned: Item added to orderPress any key to continue . . .
    ```

## <a name="see-also"></a><span data-ttu-id="9b806-221">참고자료</span><span class="sxs-lookup"><span data-stu-id="9b806-221">See also</span></span>

- [<span data-ttu-id="9b806-222">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="9b806-222">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
