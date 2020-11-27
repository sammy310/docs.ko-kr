---
title: '방법: 워크플로 애플리케이션에서 서비스 액세스'
ms.date: 03/30/2017
ms.assetid: 925ef8ea-5550-4c9d-bb7b-209e20c280ad
ms.openlocfilehash: 13fae7dec3026e96e3c196467da29fe768a3655f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257934"
---
# <a name="how-to-access-a-service-from-a-workflow-application"></a><span data-ttu-id="82dc2-102">방법: 워크플로 애플리케이션에서 서비스 액세스</span><span class="sxs-lookup"><span data-stu-id="82dc2-102">How To: Access a Service From a Workflow Application</span></span>

<span data-ttu-id="82dc2-103">이 항목에서는 워크플로 콘솔 애플리케이션에서 워크플로 서비스를 호출하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-103">This topic describes how to call a workflow service from a workflow console application.</span></span> <span data-ttu-id="82dc2-104">이 [는 방법: 메시징 작업을 사용 하 여 워크플로 서비스 만들기](how-to-create-a-workflow-service-with-messaging-activities.md) 항목의 완료에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-104">It depends on completion of the [How to: Create a Workflow Service with Messaging Activities](how-to-create-a-workflow-service-with-messaging-activities.md) topic.</span></span> <span data-ttu-id="82dc2-105">이 항목에서는 워크플로 응용 프로그램에서 워크플로 서비스를 호출 하는 방법에 대해 설명 하지만, 워크플로 응용 프로그램에서 WCF (Windows Communication Foundation) 서비스를 호출 하는 데 동일한 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-105">Although this topic describes how to call a workflow service from a workflow application, the same methods can be used to call any Windows Communication Foundation (WCF) service from a workflow application.</span></span>

### <a name="create-a-workflow-console-application-project"></a><span data-ttu-id="82dc2-106">워크플로 콘솔 애플리케이션 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="82dc2-106">Create a Workflow Console Application Project</span></span>

1. <span data-ttu-id="82dc2-107">Visual Studio 2012를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-107">Start Visual Studio 2012.</span></span>

2. <span data-ttu-id="82dc2-108">[방법: 메시징 작업을 사용 하 여 워크플로 서비스 만들기](how-to-create-a-workflow-service-with-messaging-activities.md) 항목에서 만든 MyWFService 프로젝트를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-108">Load the MyWFService project you created in the [How to: Create a Workflow Service with Messaging Activities](how-to-create-a-workflow-service-with-messaging-activities.md) topic.</span></span>

3. <span data-ttu-id="82dc2-109">**솔루션 탐색기** 에서 **MyWFService** 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **추가**, **새 프로젝트** 를 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-109">Right click the **MyWFService** solution in the **Solution Explorer** and select **Add**, **New Project**.</span></span> <span data-ttu-id="82dc2-110">**설치 된 템플릿** 에서 **워크플로** 를 선택 하 고 프로젝트 형식 목록에서 워크플로 **콘솔 응용 프로그램** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-110">Select **Workflow** in the **Installed Templates** and **Workflow Console Application** from the list of project types.</span></span> <span data-ttu-id="82dc2-111">다음 그림과 같이 프로젝트 이름을 MyWFClient로 지정하고 기본 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-111">Name the project MyWFClient and use the default location as shown in the following illustration.</span></span>

     ![새 프로젝트 추가 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-new-project-dialog.jpg)

     <span data-ttu-id="82dc2-113">**확인** 단추를 클릭 하 여 **새 프로젝트 추가 대화 상자** 를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-113">Click the **OK** button to dismiss the **Add New Project Dialog**.</span></span>

4. <span data-ttu-id="82dc2-114">프로젝트가 만들어진 후 디자이너에서 Workflow1.xaml 파일이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-114">After the project is created, the Workflow1.xaml file is opened in the designer.</span></span> <span data-ttu-id="82dc2-115">**도구 상자 탭을** 클릭 하 여 도구 상자를 열고 (아직 열려 있지 않은 경우) 압정을 클릭 하 여 도구 상자 창을 열어 둡니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-115">Click the **Toolbox** tab to open the toolbox if it is not already open and click the pushpin to keep the toolbox window open.</span></span>

5. <span data-ttu-id="82dc2-116">**Ctrl** + **F5** 를 눌러 서비스를 빌드하고 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-116">Press **Ctrl**+**F5** to build and launch the service.</span></span> <span data-ttu-id="82dc2-117">이전과 마찬가지로 ASP.NET Development Server가 시작되고 Internet Explorer에 WCF 도움말 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-117">As before, the ASP.NET Development Server is launched and Internet Explorer displays the WCF Help Page.</span></span> <span data-ttu-id="82dc2-118">이 페이지의 URI는 다음 단계에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-118">Notice the URI for this page as you must use it in the next step.</span></span>

     ![WCF 도움말 페이지 및 URI를 표시 하는 IE](./media/how-to-access-a-service-from-a-workflow-application/ie-wcf-help-page-uri.jpg)

6. <span data-ttu-id="82dc2-120">**솔루션 탐색기** 에서 **MyWFClient** 프로젝트를 마우스 오른쪽 단추로 클릭 하 **Add** 고  >  **서비스 참조** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-120">Right click the **MyWFClient** project in the **Solution Explorer** and select **Add** > **Service Reference**.</span></span> <span data-ttu-id="82dc2-121">**검색** 단추를 클릭 하 여 서비스에 대 한 현재 솔루션을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-121">Click the **Discover** button to search the current solution for any services.</span></span> <span data-ttu-id="82dc2-122">서비스 목록에서 Service1.xamlx 옆에 있는 삼각형을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-122">Click the triangle next to Service1.xamlx in the Services list.</span></span> <span data-ttu-id="82dc2-123">Service1 옆에 있는 삼각형을 클릭하여 Service1 서비스에 의해 구현되는 계약을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-123">Click the triangle next to Service1 to list the contracts implemented by the Service1 service.</span></span> <span data-ttu-id="82dc2-124">**서비스** 목록에서 **Service1** 노드를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-124">Expand the **Service1** node in the **Services** list.</span></span> <span data-ttu-id="82dc2-125">다음 그림과 같이 **작업** 목록에 Echo 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-125">The Echo operation is displayed in the **Operations** list as shown in the following illustration.</span></span>

     ![서비스 참조 추가 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference.jpg)

     <span data-ttu-id="82dc2-127">기본 네임 스페이스를 유지 하 고 **확인** 을 클릭 하 여 **서비스 참조 추가** 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-127">Keep the default namespace and click **OK** to dismiss the **Add Service Reference** dialog.</span></span> <span data-ttu-id="82dc2-128">다음 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-128">The following dialog is displayed.</span></span>

     ![서비스 참조 추가 알림 대화 상자](./media/how-to-access-a-service-from-a-workflow-application/add-service-reference-dialog.jpg)

     <span data-ttu-id="82dc2-130">**확인** 을 클릭 하 여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-130">Click **OK** to dismiss the dialog.</span></span> <span data-ttu-id="82dc2-131">그런 다음 Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-131">Next, press CTRL+SHIFT+B to build the solution.</span></span> <span data-ttu-id="82dc2-132">도구 상자에서 **MyWFClient** 라는 새 섹션이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-132">Notice in the toolbox a new section has been added called **MyWFClient.ServiceReference1.Activities**.</span></span> <span data-ttu-id="82dc2-133">다음 그림과 같이 이 섹션을 확장하고 추가된 Echo 작업을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-133">Expand this section and notice the Echo activity that has been added as shown in the following illustration.</span></span>

     ![도구 상자의 Echo 활동](./media/how-to-access-a-service-from-a-workflow-application/echo-activity-toolbox.jpg)

7. <span data-ttu-id="82dc2-135">디자이너 화면으로 <xref:System.Activities.Statements.Sequence> 작업을 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-135">Drag and drop a <xref:System.Activities.Statements.Sequence> activity onto the designer surface.</span></span> <span data-ttu-id="82dc2-136">도구 상자의 **제어 흐름** 섹션 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-136">It is under the **Control Flow** section of the toolbox.</span></span>

8. <span data-ttu-id="82dc2-137">활동에 포커스가 있는 상태에서 <xref:System.Activities.Statements.Sequence> **변수** 링크를 클릭 하 고 라는 문자열 변수를 추가 `inString` 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-137">With the <xref:System.Activities.Statements.Sequence> activity in focus, click the **Variables** link and add a string variable named `inString`.</span></span> <span data-ttu-id="82dc2-138">`"Hello, world"` `outString` 다음 다이어그램에 표시 된 것 처럼 라는 문자열 변수를 비롯 하 여 변수에 기본값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-138">Give the variable a default value of `"Hello, world"` as well as a string variable named `outString` as shown in the following diagram.</span></span>

     ![InString 변수 추가](./media/how-to-access-a-service-from-a-workflow-application/add-instring-variable.jpg)

9. <span data-ttu-id="82dc2-140">**Echo** 활동을로 끌어 놓습니다 <xref:System.Activities.Statements.Sequence> .</span><span class="sxs-lookup"><span data-stu-id="82dc2-140">Drag and drop an **Echo** activity into the <xref:System.Activities.Statements.Sequence>.</span></span> <span data-ttu-id="82dc2-141">속성 창에서 `inMsg` 인수를 `inString` `outMsg` 다음 그림과 같이 변수에 바인딩하고 인수를 `outString` 변수에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-141">In the properties window bind the `inMsg` argument to the `inString` variable and the `outMsg` argument to the `outString` variable as shown in the following illustration.</span></span> <span data-ttu-id="82dc2-142">그러면 `inString` 변수의 값이 작업에 전달되고 반환 값이 `outString` 변수에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-142">This passes in the value of the `inString` variable to the operation and then takes the return value and places it in the `outString` variable.</span></span>

     ![변수에 인수 바인딩](./media/how-to-access-a-service-from-a-workflow-application/bind-arguments-variables.jpg)

10. <span data-ttu-id="82dc2-144">서비스 호출에서 반환 된 문자열을 표시 하는 **WriteLine** 활동을 **Echo** 활동 아래로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-144">Drag and drop a **WriteLine** activity below the **Echo** activity to display the string returned by the service call.</span></span> <span data-ttu-id="82dc2-145">**WriteLine** 활동은 도구 상자의 **기본 형식** 노드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-145">The **WriteLine** activity is located in the **Primitives** node in the toolbox.</span></span> <span data-ttu-id="82dc2-146">Writeline 활동 **Text** 의 **WriteLine** `outString` `outString` 텍스트 상자에를 **WriteLine** 입력 하 여 writeline 활동의 text 인수를 변수에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-146">Bind the **Text** argument of the **WriteLine** activity to the `outString` variable by typing `outString` into the text box on the **WriteLine** activity.</span></span> <span data-ttu-id="82dc2-147">그러면 워크플로가 다음 그림과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-147">The workflow should now look like the following illustration.</span></span>

     ![완료된 클라이언트 워크플로](./media/how-to-access-a-service-from-a-workflow-application/complete-client-workflow.jpg)

11. <span data-ttu-id="82dc2-149">MyWFService 솔루션을 마우스 오른쪽 단추로 클릭 하 고 **시작 프로젝트 설정**...을 선택 합니다. **여러 시작 프로젝트** 라디오 단추를 선택 하 고 다음 그림과 같이 **작업** 열의 각 프로젝트에 대해 **시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-149">Right-click the MyWFService solution and select **Set Startup Projects ...**. Select the **Multiple startup projects** radio button and select **Start** for each project in the **Action** column as shown in the following illustration.</span></span>

     ![시작 프로젝트 옵션](./media/how-to-access-a-service-from-a-workflow-application/startup-project-options.jpg)

12. <span data-ttu-id="82dc2-151">Ctrl+F5를 눌러 서비스와 클라이언트를 둘 다 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="82dc2-151">Press Ctrl + F5 to launch both the service and the client.</span></span> <span data-ttu-id="82dc2-152">ASP.NET 개발 서버은 서비스를 호스팅하고, Internet Explorer는 WCF 도움말 페이지를 표시 하 고, 클라이언트 워크플로 응용 프로그램은 콘솔 창에서 시작 되며 서비스에서 반환 된 문자열을 표시 합니다 ("Hello, 세계").</span><span class="sxs-lookup"><span data-stu-id="82dc2-152">The ASP.NET Development Server hosts the service, Internet Explorer displays the WCF help page, and the client workflow application is launched in a console window and displays the string returned from the service ("Hello, world").</span></span>

## <a name="see-also"></a><span data-ttu-id="82dc2-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82dc2-153">See also</span></span>

- [<span data-ttu-id="82dc2-154">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="82dc2-154">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="82dc2-155">방법: 메시징 활동을 사용하여 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="82dc2-155">How to: Create a Workflow Service with Messaging Activities</span></span>](how-to-create-a-workflow-service-with-messaging-activities.md)
- [<span data-ttu-id="82dc2-156">웹 프로젝트의 워크플로에서 WCF 서비스 사용</span><span class="sxs-lookup"><span data-stu-id="82dc2-156">Consuming a WCF Service from a Workflow in a Web Project</span></span>](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
