---
title: '방법: 메시징 활동을 사용하여 워크플로 서비스 만들기'
ms.date: 03/30/2017
ms.assetid: 53d094e2-6901-4aa1-88b8-024b27ccf78b
ms.openlocfilehash: f5bb8df5936be1890bf744300daa7ccb68e341e3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337775"
---
# <a name="how-to-create-a-workflow-service-with-messaging-activities"></a><span data-ttu-id="a447d-102">방법: 메시징 활동을 사용하여 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="a447d-102">How to: Create a Workflow Service with Messaging Activities</span></span>
<span data-ttu-id="a447d-103">이 항목에서는 메시징 작업을 사용하여 간단한 워크플로 서비스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-103">This topic describes how to create a simple workflow service using messaging activities.</span></span> <span data-ttu-id="a447d-104">이 항목에서는 서비스가 메시징 작업만으로 구성된 워크플로 서비스를 만드는 방법에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-104">This topic focuses on the mechanics of creating a workflow service where the service consists solely of messaging activities.</span></span> <span data-ttu-id="a447d-105">실제 서비스의 워크플로에는 다른 많은 작업이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-105">In a real-world service, the workflow contains many other activities.</span></span> <span data-ttu-id="a447d-106">이 항목의 서비스에서는 문자열을 받아서 호출자에게 반환하는 Echo라는 하나의 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-106">The service implements one operation called Echo, which takes a string and returns the string to the caller.</span></span> <span data-ttu-id="a447d-107">이 항목은 시리즈로 된 두 항목 중 첫 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-107">This topic is the first in a series of two topics.</span></span> <span data-ttu-id="a447d-108">다음 항목에서는 [방법: 서비스는 워크플로 응용 프로그램에서 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) 이 항목에서 만든 서비스를 호출할 수 있는 워크플로 응용 프로그램을 만드는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-108">The next topic [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) discusses how to create a workflow application that can call the service created in this topic.</span></span>  
  
### <a name="to-create-a-workflow-service-project"></a><span data-ttu-id="a447d-109">워크플로 서비스 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a447d-109">To create a workflow service project</span></span>  
  
1. <span data-ttu-id="a447d-110">Start Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="a447d-110">Start Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="a447d-111">클릭 합니다 **파일** 메뉴에서 **새로 만들기**를 차례로 **프로젝트** 표시할를 **새 프로젝트 대화 상자**.</span><span class="sxs-lookup"><span data-stu-id="a447d-111">Click the **File** menu, select **New**, and then **Project** to display the **New Project Dialog**.</span></span> <span data-ttu-id="a447d-112">선택 **워크플로** 설치 된 템플릿 목록에서 및 **WCF 워크플로 서비스 응용 프로그램** 프로젝트 형식 목록에서.</span><span class="sxs-lookup"><span data-stu-id="a447d-112">Select **Workflow** from the list of installed templates and **WCF Workflow Service Application** from the list of project types.</span></span> <span data-ttu-id="a447d-113">프로젝트 이름을 `MyWFService` 하 고 다음 그림에 나와 있는 것 처럼 기본 위치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-113">Name the project `MyWFService` and use the default location as shown in the following illustration.</span></span>  
  
     <span data-ttu-id="a447d-114">클릭 합니다 **확인** 해제 하려면 단추를 **새 프로젝트 대화 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-114">Click the **OK** button to dismiss the **New Project Dialog**.</span></span>  
  
3. <span data-ttu-id="a447d-115">프로젝트가 생성되면 다음 그림과 같이 Service1.xamlx 파일이 디자이너에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-115">When the project is created, the Service1.xamlx file is opened in the designer as shown in the following illustration.</span></span>  
  
     ![스크린샷은은 디자이너에서 Service1.xamlx 파일 열기를 보여 줍니다.](./media/how-to-create-a-workflow-service-with-messaging-activities/default-workflow-service.jpg)  
  
     <span data-ttu-id="a447d-117">레이블이 지정 된 활동을 마우스 오른쪽 단추로 클릭 **순차 서비스** 선택한 **삭제**합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-117">Right-click the activity labeled **Sequential Service** and select **Delete**.</span></span>  
  
### <a name="to-implement-the-workflow-service"></a><span data-ttu-id="a447d-118">워크플로 서비스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="a447d-118">To implement the workflow service</span></span>  
  
1. <span data-ttu-id="a447d-119">선택 된 **도구 상자** 도구 상자를 표시 된 창을 열어 압정을 클릭 하 고 화면 왼쪽에 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-119">Select the **Toolbox** tab on the left side of the screen to display the toolbox and click the pushpin to keep the window open.</span></span> <span data-ttu-id="a447d-120">확장 된 **메시징** 다음 그림과에서 같이 메시징 작업과 메시징 작업 템플릿을 표시 하려면 도구 상자의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-120">Expand the **Messaging** section of the toolbox to display the messaging activities and the messaging activity templates as shown in the following illustration.</span></span>  
  
     ![확장 된 메시징 섹션을 사용 하 여 도구 상자를 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/toolbox-messaging-section.jpg)  
  
2. <span data-ttu-id="a447d-122">끌어서 놓기는 **ReceiveAndSendReply** 템플릿을 워크플로 디자이너로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-122">Drag and drop a **ReceiveAndSendReply** template to the workflow designer.</span></span> <span data-ttu-id="a447d-123">이렇게를 <xref:System.Activities.Statements.Sequence> 활동을 **수신** 작업과 그 뒤를 <xref:System.ServiceModel.Activities.SendReply> 다음 그림과에서 같이 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-123">This creates a <xref:System.Activities.Statements.Sequence> activity with a **Receive** activity followed by a <xref:System.ServiceModel.Activities.SendReply> activity as shown in the following illustration.</span></span>  
  
     ![ReceiveAndSendReply 템플릿의 보여주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/receiveandsendreply-template.jpg)  
  
     <span data-ttu-id="a447d-125"><xref:System.ServiceModel.Activities.SendReply> 작업의 <xref:System.ServiceModel.Activities.SendReply.Request%2A> 속성이 `Receive` 작업이 회신하는 <xref:System.ServiceModel.Activities.Receive> 작업의 이름인 <xref:System.ServiceModel.Activities.SendReply>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-125">Notice that the <xref:System.ServiceModel.Activities.SendReply> activity’s <xref:System.ServiceModel.Activities.SendReply.Request%2A> property is set to `Receive`, the name of the <xref:System.ServiceModel.Activities.Receive> activity to which the <xref:System.ServiceModel.Activities.SendReply> activity is replying.</span></span>  
  
3. <span data-ttu-id="a447d-126">에 <xref:System.ServiceModel.Activities.Receive> 활동 유형 `Echo` 레이블이 지정 된 텍스트 상자에 **OperationName**합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-126">In the <xref:System.ServiceModel.Activities.Receive> activity type `Echo` into the textbox labeled **OperationName**.</span></span> <span data-ttu-id="a447d-127">그러면 서비스가 구현하는 작업의 이름이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-127">This defines the name of the operation the service implements.</span></span>  
  
     ![작업 이름을 지정 하는 위치를 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/define-operation-name.jpg)  
  
4. <span data-ttu-id="a447d-129">사용 하 여는 <xref:System.ServiceModel.Activities.Receive> 작업이 선택 속성 창을 클릭 하 여 열려 있지 않으면 합니다 **보기** 메뉴에서 **속성 창**합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-129">With the <xref:System.ServiceModel.Activities.Receive> activity selected, open the properties window if not already open by clicking the **View** menu and selecting **Properties Window**.</span></span> <span data-ttu-id="a447d-130">에 **속성 창** 표시 될 때까지 아래로 스크롤하여 **CanCreateInstance** 다음 그림에 나와 있는 것 처럼 확인란을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-130">In the **Properties Window** scroll down until you see **CanCreateInstance** and click the checkbox as shown in the following illustration.</span></span> <span data-ttu-id="a447d-131">이렇게 설정하면 메시지를 받을 때 필요한 경우 워크플로 서비스 호스트가 서비스의 새 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-131">This setting enables the workflow service host to create a new instance of the service (if needed) when a message is received.</span></span>  
  
     ![CanCreateInstance 속성을 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/cancreateinstance-property.jpg)  
  
5. <span data-ttu-id="a447d-133">선택 합니다 <xref:System.Activities.Statements.Sequence> 활동을 클릭 합니다 **변수** 디자이너의 왼쪽된 아래 모퉁이의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-133">Select the <xref:System.Activities.Statements.Sequence> activity and click the **Variables** button in the lower left corner of the designer.</span></span> <span data-ttu-id="a447d-134">그러면 변수 편집기가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-134">This displays the variables editor.</span></span> <span data-ttu-id="a447d-135">클릭 합니다 **변수 만들기** 작업에 보내진 문자열을 저장 하는 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-135">Click the **Create Variable** link to add a variable to store the string sent to the operation.</span></span> <span data-ttu-id="a447d-136">변수 이름을 `msg` 설정 및 해당 **변수** 다음 그림에 나와 있는 것 처럼 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-136">Name the variable `msg` and set its **Variable** type to String as shown in the following illustration.</span></span>  
  
     ![변수를 추가 하는 방법을 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/add-variable-msg-string.jpg)  
  
     <span data-ttu-id="a447d-138">클릭 합니다 **변수** 하려면 단추를 다시 변수 편집기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-138">Click the **Variables** button again to close the variables editor.</span></span>  
  
6. <span data-ttu-id="a447d-139">클릭 된 **정의...**</span><span class="sxs-lookup"><span data-stu-id="a447d-139">Click the **Define..**</span></span> <span data-ttu-id="a447d-140">링크는 **콘텐츠** 텍스트 상자에 <xref:System.ServiceModel.Activities.Receive> 표시 하도록 작업을 **콘텐츠 정의** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-140">link in the **Content** text box in the <xref:System.ServiceModel.Activities.Receive> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="a447d-141">선택는 **매개 변수** 라디오 단추를 클릭 합니다 **새 매개 변수를 추가** 링크를 입력 `inMsg` 에 **이름** 텍스트 상자에서 **문자열**에 **형식** 드롭다운 목록 상자 및 형식 목록 `msg` 에 **에 할당** 다음 그림에 표시 된 것과 같이 입력란.</span><span class="sxs-lookup"><span data-stu-id="a447d-141">Select the **Parameters** radio button, click the **Add new Parameter** link, type `inMsg` in the **name** text box, select **String** in the **Type** drop down list box, and type `msg` in the **Assign To** text box as shown in the following illustration.</span></span>  
  
     ![추가 매개 변수 콘텐츠를 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/adding-parameters-content.jpg)  
  
     <span data-ttu-id="a447d-143">그러면 받기 작업이 문자열 매개 변수를 받고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-143">This specifies that the Receive activity receives string parameter and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="a447d-144">클릭 **확인** 닫으려면 합니다 **콘텐츠 정의** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-144">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
7. <span data-ttu-id="a447d-145">클릭 된 **정의 하는 중...**  링크를 **콘텐츠** 상자에 <xref:System.ServiceModel.Activities.SendReply> 표시 하도록 작업을 **콘텐츠 정의** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-145">Click the **Define...** link in the **Content** box in the <xref:System.ServiceModel.Activities.SendReply> activity to display the **Content Definition** dialog.</span></span> <span data-ttu-id="a447d-146">선택를 **매개 변수** 라디오 단추를 클릭 합니다 **새 매개 변수를 추가** 링크를 입력 `outMsg` 에 **이름** 텍스트 상자 선택 **문자열**에 **형식** 드롭다운 목록 상자 및 `msg` 에 **값** 다음 그림에 나와 있는 것 처럼 텍스트 상자.</span><span class="sxs-lookup"><span data-stu-id="a447d-146">Select the **Parameters** radio button, click the **Add new Parameter** link, type `outMsg` in the **name** textbox, select **String** in the **Type** dropdown list box, and `msg` in the **Value** text box as shown in the following illustration.</span></span>  
  
     ![OutMsg 매개 변수를 추가 하는 방법을 보여주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/outmsg-parameters-content.jpg)  
  
     <span data-ttu-id="a447d-148">그러면 <xref:System.ServiceModel.Activities.SendReply> 작업이 메시지 또는 메시지 계약 형식을 보내고 데이터가 `msg` 변수에 바인딩되도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-148">This specifies that the <xref:System.ServiceModel.Activities.SendReply> activity sends a message or message contract type and that data is bound to the `msg` variable.</span></span> <span data-ttu-id="a447d-149">이 작업이 <xref:System.ServiceModel.Activities.SendReply> 작업이므로 이는 이 작업이 클라이언트에 다시 보내는 메시지를 채우는 데 `msg`의 데이터가 사용됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-149">Because this is a <xref:System.ServiceModel.Activities.SendReply> activity, this means the data in `msg` is used to populate the message the activity sends back to the client.</span></span> <span data-ttu-id="a447d-150">클릭 **확인** 닫으려면 합니다 **콘텐츠 정의** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-150">Click **OK** to close the **Content Definition** dialog.</span></span>  
  
8. <span data-ttu-id="a447d-151">저장 하 고 클릭 하 여 솔루션을 빌드합니다 합니다 **빌드** 메뉴에서 **솔루션 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-151">Save and build the solution by clicking the **Build** menu and selecting **Build Solution**.</span></span>  
  
## <a name="configure-the-workflow-service-project"></a><span data-ttu-id="a447d-152">워크플로 서비스 프로젝트 구성</span><span class="sxs-lookup"><span data-stu-id="a447d-152">Configure the Workflow Service Project</span></span>  
 <span data-ttu-id="a447d-153">워크플로 서비스가 완료되었으므로</span><span class="sxs-lookup"><span data-stu-id="a447d-153">The workflow service is complete.</span></span> <span data-ttu-id="a447d-154">이 단원에서는 워크플로 서비스 솔루션을 손쉽게 호스팅하고 실행할 수 있도록 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-154">This section explains how to configure the workflow service solution to make it easy to host and run.</span></span> <span data-ttu-id="a447d-155">이 솔루션은 ASP.NET Development Server를 사용하여 서비스를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-155">This solution uses the ASP.NET Development Server to host the service.</span></span>  
  
#### <a name="to-set-project-start-up-options"></a><span data-ttu-id="a447d-156">프로젝트 시작 옵션을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a447d-156">To set project start up options</span></span>  
  
1. <span data-ttu-id="a447d-157">에 **솔루션 탐색기**, 마우스 오른쪽 단추로 클릭 **MyWFService** 선택한 **속성** 표시할 합니다 **프로젝트 속성** 대화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-157">In the **Solution Explorer**, right-click **MyWFService** and select **Properties** to display the **Project Properties** dialog.</span></span>  
  
2. <span data-ttu-id="a447d-158">선택 합니다 **웹** 탭을 선택한 **특정 페이지** 아래에 있는 **시작 작업** 유형과 `Service1.xamlx` 다음 그림에 나와 있는 것 처럼 텍스트 상자에 합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-158">Select the **Web** tab and select **Specific Page** under **Start Action** and type `Service1.xamlx` in the text box as shown in the following illustration.</span></span>  
  
     ![프로젝트 속성 대화 상자를 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/project-properties-dialog.jpg)  
  
     <span data-ttu-id="a447d-160">그러면 ASP.NET Development Server에서 Service1.xamlx에 정의된 서비스가 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-160">This hosts the service defined in Service1.xamlx in the ASP.NET Development Server.</span></span>  
  
3. <span data-ttu-id="a447d-161">Ctrl+F5를 눌러 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-161">Press Ctrl + F5 to launch the service.</span></span> <span data-ttu-id="a447d-162">그러면 다음 그림과 같이 바탕 화면의 오른쪽 아래에 ASP.NET Development Server 아이콘이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-162">The ASP.NET Development Server icon is displayed in the lower right side of the desktop as shown in the following image.</span></span>  
  
     ![ASP.NET Developer Server 아이콘을 보여주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/asp-net-dev-server-icon.jpg)  
  
     <span data-ttu-id="a447d-164">또한 Internet Explorer에 서비스에 대한 WCF 서비스 도움말 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-164">In addition, Internet Explorer displays the WCF Service Help Page for the service.</span></span>  
  
     ![WCF 서비스 도움말 페이지를 보여 주는 스크린샷.](./media/how-to-create-a-workflow-service-with-messaging-activities/wcf-service-help-page.jpg)  
  
4. <span data-ttu-id="a447d-166">계속 진행 합니다 [방법: 서비스는 워크플로 응용 프로그램에서 액세스](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) 항목에서는이 서비스를 호출 하는 워크플로 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a447d-166">Continue on to the [How To: Access a Service From a Workflow Application](../../../../docs/framework/wcf/feature-details/how-to-access-a-service-from-a-workflow-application.md) topic to create a workflow client that calls this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a447d-167">참고자료</span><span class="sxs-lookup"><span data-stu-id="a447d-167">See also</span></span>

- [<span data-ttu-id="a447d-168">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="a447d-168">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="a447d-169">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="a447d-169">Hosting Workflow Services Overview</span></span>](../../../../docs/framework/wcf/feature-details/hosting-workflow-services-overview.md)
- [<span data-ttu-id="a447d-170">메시징 작업</span><span class="sxs-lookup"><span data-stu-id="a447d-170">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)
