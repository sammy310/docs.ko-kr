---
description: '자세한 정보: WCF Visual Studio 템플릿'
title: WCF Visual Studio 템플릿
ms.date: 03/30/2017
ms.assetid: 6a608575-3535-4190-89da-911e24c8374f
ms.openlocfilehash: 95d320b2a425ddef7e48f915c8f66d759702ccce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99676367"
---
# <a name="wcf-visual-studio-templates"></a><span data-ttu-id="9d6ee-103">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-103">WCF Visual Studio Templates</span></span>

<span data-ttu-id="9d6ee-104">WCF (Windows Communication Foundation) Visual Studio 템플릿은 Visual Studio에서 WCF 서비스 및 주변 응용 프로그램을 신속 하 게 빌드하기 위해 사용할 수 있는 미리 정의 된 프로젝트 및 항목 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-104">Windows Communication Foundation (WCF) Visual Studio templates are predefined project and item templates you can use in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
## <a name="using-the-wcf-templates"></a><span data-ttu-id="9d6ee-105">WCF 템플릿 사용</span><span class="sxs-lookup"><span data-stu-id="9d6ee-105">Using the WCF Templates</span></span>  

 <span data-ttu-id="9d6ee-106">WCF Visual Studio 템플릿은 서비스 개발을 위한 기본 클래스 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-106">WCF Visual Studio templates provide a basic class structure for service development.</span></span> <span data-ttu-id="9d6ee-107">특히 이러한 템플릿은 서비스 계약, 데이터 계약, 서비스 구현 및 구성에 대한 기본 정의를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-107">Specifically, these templates provide the basic definitions for service contract, data contract, service implementation, and configuration.</span></span> <span data-ttu-id="9d6ee-108">이러한 템플릿을 사용하여 최소의 코드 상호 작용만으로 간단한 서비스를 만들 수 있을 뿐만 아니라 고급 서비스에 대한 빌딩 블록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-108">You can use these templates to create a simple service with minimal code interaction, as well as a building block for more advanced services.</span></span>  
  
### <a name="wcf-service-library-project-template"></a><span data-ttu-id="9d6ee-109">WCF 서비스 라이브러리 프로젝트 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-109">WCF Service Library Project Template</span></span>  

 <span data-ttu-id="9d6ee-110">WCF 서비스 라이브러리 프로젝트 템플릿은 새 프로젝트 대화 상자의 **visual c # \wcf** 및 **visual basic\wcf** 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-110">The WCF Service Library project template is available in the new project dialog box under **Visual C#\WCF** and **Visual Basic\WCF**.</span></span>  
  
 <span data-ttu-id="9d6ee-111">**WCF 서비스** 템플릿을 사용 하 여 새 프로젝트를 만들면 새 프로젝트에 자동으로 다음 세 개의 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-111">When you create a new project using the **WCF Service** template, the new project automatically includes the following three files:</span></span>  
  
- <span data-ttu-id="9d6ee-112">서비스 계약 파일(IService1.cs 또는 IService1.vb).</span><span class="sxs-lookup"><span data-stu-id="9d6ee-112">Service contract file (IService1.cs or IService1.vb).</span></span> <span data-ttu-id="9d6ee-113">서비스 계약 파일은 WCF 서비스 특성이 적용 되는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-113">The service contract file is an interface that has WCF service attributes applied.</span></span> <span data-ttu-id="9d6ee-114">이 파일은 서비스를 정의하는 방법을 보여 주는 간단한 서비스 정의를 제공하고 매개 변수 기반 작업과 간단한 데이터 계약 샘플을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-114">This file provides a definition of a simple service to show you how to define your services, and includes parameter-based operations and a simple data contract sample.</span></span> <span data-ttu-id="9d6ee-115">이 파일은 WCF 서비스 프로젝트를 만든 후 코드 편집기에 표시 되는 기본 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-115">This is the default file displayed in the code editor after creating a WCF service project.</span></span>  
  
- <span data-ttu-id="9d6ee-116">서비스 구현 파일(Service1.cs 또는 Service1.vb).</span><span class="sxs-lookup"><span data-stu-id="9d6ee-116">Service implementation file (Service1.cs or Service1.vb).</span></span> <span data-ttu-id="9d6ee-117">서비스 구현 파일은 서비스 계약 파일에 정의된 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-117">The service implementation file implements the contract defined in the service contract file.</span></span>  
  
- <span data-ttu-id="9d6ee-118">애플리케이션 구성 파일(App.config).</span><span class="sxs-lookup"><span data-stu-id="9d6ee-118">Application configuration file (App.config).</span></span> <span data-ttu-id="9d6ee-119">구성 파일은 보안 HTTP 바인딩을 사용 하 여 WCF 서비스 모델의 기본 요소를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-119">The configuration file provides the basic elements of a WCF service model with a secure HTTP binding.</span></span> <span data-ttu-id="9d6ee-120">또한 서비스에 대한 엔드포인트를 포함하고 메타데이터 교환을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-120">It also includes an endpoint for the service and enables metadata exchange.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d6ee-121">Visual Studio는 기본 구성 인 [WCF 서비스 호스트 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)를 사용 하 여 실행 될 때 App.config 파일을 프로젝트에 대 한 구성 파일로 인식 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-121">Visual Studio is configured to recognize the App.config file as the configuration file for the project when it is run using the [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md), which is the default configuration.</span></span> <span data-ttu-id="9d6ee-122">실행 파일에서 서비스 라이브러리를 호스팅할 경우 DLL의 구성 파일이 유효하지 않게 되므로 구성 코드를 실행 파일의 구성 파일로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-122">If you host the service library in an executable, you have to move the configuration code to the configuration file of the executable, as configuration files for DLLs are not valid.</span></span>  
  
### <a name="wcf-service-application-template"></a><span data-ttu-id="9d6ee-123">WCF 서비스 애플리케이션 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-123">WCF Service Application Template</span></span>  

 <span data-ttu-id="9d6ee-124">WCF 서비스 응용 프로그램 템플릿은 새 프로젝트 대화 상자의 **visual c # \wcf** 및 **visual basic\wcf** 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-124">The WCF Service Application template is available in the New Project dialog box under **Visual C#\WCF** and **Visual Basic\WCF**.</span></span>  
  
 <span data-ttu-id="9d6ee-125">**WCF 웹 응용 프로그램 서비스** 템플릿을 사용 하 여 새 프로젝트를 만들 때 프로젝트에는 다음 4 개의 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-125">When you create a new project using the **WCF Web Application Service** template, the project includes the following four files:</span></span>  
  
- <span data-ttu-id="9d6ee-126">서비스 호스트 파일(service1.svc)</span><span class="sxs-lookup"><span data-stu-id="9d6ee-126">Service host file (service1.svc).</span></span>  
  
- <span data-ttu-id="9d6ee-127">서비스 계약 파일(IService1.cs 또는 IService1.vb).</span><span class="sxs-lookup"><span data-stu-id="9d6ee-127">Service contract file (IService1.cs or IService1.vb).</span></span>  
  
- <span data-ttu-id="9d6ee-128">서비스 구현 파일(Service1.svc.cs 또는 Service1.svc.vb)</span><span class="sxs-lookup"><span data-stu-id="9d6ee-128">Service implementation file (Service1.svc.cs or Service1.svc.vb).</span></span>  
  
- <span data-ttu-id="9d6ee-129">웹 구성 파일(Web.config)</span><span class="sxs-lookup"><span data-stu-id="9d6ee-129">Web configuration file (Web.config).</span></span>  
  
 <span data-ttu-id="9d6ee-130">템플릿은 가상 디렉터리에 배포할 웹 사이트를 자동으로 만들고 해당 디렉터리에 서비스를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-130">The template automatically creates a Web site (to be deployed to a virtual directory) and hosts a service in it.</span></span>  
  
### <a name="wcf-web-site-template"></a><span data-ttu-id="9d6ee-131">WCF 웹 사이트 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-131">WCF Web Site Template</span></span>  

 <span data-ttu-id="9d6ee-132">WCF 웹 사이트 템플릿은 **visual c # \Web Site\wcf 서비스** 및 **visual Basic\web Site\wcf 서비스** 의 새 프로젝트 대화 상자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-132">The WCF Web Site template is available in the New Project dialog box under **Visual C#\Web Site\WCF Service** and **Visual Basic\Web Site\WCF Service**.</span></span> <span data-ttu-id="9d6ee-133">이 템플릿은 WCF 서비스 애플리케이션 템플릿과 같은 파일을 만들지만 ASP.NET 웹 사이트인 것처럼 정리합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-133">This creates the same files as the WCF Service Application template but organizes it as if it were a ASP.NET web site.</span></span> <span data-ttu-id="9d6ee-134">App_Code 및 App_Data 폴더가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-134">App_Code and App_Data folders are created.</span></span>  
  
### <a name="wcf-service-item-template"></a><span data-ttu-id="9d6ee-135">WCF 서비스 항목 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-135">WCF Service Item Template</span></span>  

 <span data-ttu-id="9d6ee-136">WCF 서비스 항목 템플릿은 기존 Visual Studio 프로젝트에 WCF 서비스를 신속 하 게 추가 하는 방법을 제공 하는 사용자 지정 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-136">The WCF Service Item template is a custom template that provides a quick way to add WCF services to your existing Visual Studio projects.</span></span>  
  
 <span data-ttu-id="9d6ee-137">이 템플릿을 사용 하려면 **솔루션 탐색기** 창으로 이동 하 여 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 **추가** 를 가리킨 다음 **새 항목** 을 클릭 하 여 **새 항목 추가** 대화 상자를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-137">To use this template, go to the **Solution Explorer** pane, right-click your project name, point to **Add**, and then click **New Item** to launch the **Add New Item** dialog box.</span></span>  
  
 <span data-ttu-id="9d6ee-138">서비스 인터페이스와 구현 파일은 루트 프로젝트 폴더에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-138">The service interface and implementation files are placed in the root project folder.</span></span>  
  
 <span data-ttu-id="9d6ee-139">템플릿은 새 서비스의 구성 섹션과 기존 구성 파일이 호환 가능한 형식인 경우 서로 병합하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-139">The template attempts to merge the configuration section of the new service to the existing configuration file, if they are compatible types.</span></span>  
  
 <span data-ttu-id="9d6ee-140">기존 프로젝트가 웹 프로젝트인 경우 서비스 호스트 파일(service1.svc)도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-140">A service host file (service1.svc) is also created if the existing project is a Web project.</span></span>  
  
### <a name="wcf-wf-service-project-and-item-template"></a><span data-ttu-id="9d6ee-141">WCF WF 서비스 프로젝트 및 항목 템플릿.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-141">WCF WF Service Project and Item Template.</span></span>  

 <span data-ttu-id="9d6ee-142">이러한 템플릿은 웹 서비스 처럼 액세스할 수 있는 워크플로 인 워크플로 서비스를 호스팅하는 WCF 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-142">These templates create WCF services that host a Workflow Service, which is a workflow that can be accessed like a web service.</span></span> <span data-ttu-id="9d6ee-143">XAML 또는 필수 프로그래밍 모델에 대한 별도의 템플릿이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-143">Separate templates exist for XAML or imperative programming models.</span></span> <span data-ttu-id="9d6ee-144">이 템플릿을 사용하여 순차 또는 상태 시스템 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-144">Using the templates, you can create sequential or state machine workflow.</span></span> <span data-ttu-id="9d6ee-145">이러한 유형의 워크플로에 대 한 자세한 내용은 [방법: 워크플로 만들기](../windows-workflow-foundation/how-to-create-a-workflow.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-145">For more information on these types of workflow, see [How to: Create a Workflow](../windows-workflow-foundation/how-to-create-a-workflow.md).</span></span> <span data-ttu-id="9d6ee-146">워크플로 프로젝트를 만드는 방법에 대 한 자세한 내용은 [레거시 워크플로 프로젝트 만들기](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-146">For more information about creating workflow projects, see [Creating Legacy Workflow Projects](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer).</span></span>  
  
 <span data-ttu-id="9d6ee-147">Visual Studio designer는 코드 기반 항목 대신 XOML 형식 워크플로를 사용 하는 경우 더욱 응답성이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-147">Visual Studio designer is more responsive when XOML type workflows are used instead of code based ones.</span></span> <span data-ttu-id="9d6ee-148">만들어지는 기본 워크플로 형식은 XOML 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-148">XOML workflow is the default workflow type to be created.</span></span>  
  
### <a name="wcf-syndication-service-library-template"></a><span data-ttu-id="9d6ee-149">WCF 배포 서비스 라이브러리 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-149">WCF Syndication Service Library Template</span></span>  

 <span data-ttu-id="9d6ee-150">이 템플릿을 사용 하면 RSS 또는 ATOM 형식의 피드를 WCF 서비스로 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-150">This template enables you to expose your feed in the RSS or ATOM format as a WCF service.</span></span> <span data-ttu-id="9d6ee-151">자세한 내용은 [WCF 배포](./feature-details/wcf-syndication.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-151">For more information, see [WCF Syndication](./feature-details/wcf-syndication.md).</span></span>  
  
#### <a name="changing-the-address-of-the-feed"></a><span data-ttu-id="9d6ee-152">피드의 주소 변경</span><span class="sxs-lookup"><span data-stu-id="9d6ee-152">Changing the Address of the Feed</span></span>  

 <span data-ttu-id="9d6ee-153">배포 템플릿은 실행 중에 Internet Explorer를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-153">The syndication template uses Internet Explorer during execution.</span></span> <span data-ttu-id="9d6ee-154">Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성** 을 선택한 다음 **디버그** 탭을 선택 하면 템플릿의 기본 주소를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-154">When you right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab and you can see the default address of the template.</span></span> <span data-ttu-id="9d6ee-155">Internet Explorer는 이 주소에서 피드를 열려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-155">Internet Explorer attempts to open the feed at this address.</span></span>  
  
 <span data-ttu-id="9d6ee-156">피드의 주소를 변경 하는 경우에는 **디버그** 탭 에서도 주소를 변경 해야 합니다. 이렇게 하지 않으면 Internet Explorer는 기본 주소에서 피드를 열려고 시도 하 고 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-156">If you change the address of your feed, you must also change the address in the **Debug** tab. If you do not do this, Internet Explorer attempts to open the feed at the default address and fail.</span></span>  
  
### <a name="ajax-enabled-wcf-service-item-template"></a><span data-ttu-id="9d6ee-157">AJAX 사용 WCF 서비스 항목 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-157">AJAX enabled WCF Service Item Template</span></span>  

 <span data-ttu-id="9d6ee-158">이 템플릿은 AJAX 컨트롤을 WCF 서비스로 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-158">This template exposes an AJAX control as a WCF service.</span></span> <span data-ttu-id="9d6ee-159">AJAX 컨트롤에 대 한 자세한 내용은 [ajax 컨트롤 설명서](/aspnet/ajax/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-159">For more information on AJAX controls, see the [AJAX control documentation](/aspnet/ajax/).</span></span>  
  
### <a name="silverlight-enabled-wcf-service-item-template"></a><span data-ttu-id="9d6ee-160">Silverlight 사용 WCF 서비스 항목 템플릿</span><span class="sxs-lookup"><span data-stu-id="9d6ee-160">Silverlight-enabled WCF Service Item Template</span></span>  

 <span data-ttu-id="9d6ee-161">이 템플릿은 Silverlight 클라이언트 또는 프런트 엔드에 데이터를 제공하는 웹 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-161">This template creates a Web service that provides data to a Silverlight client or front-end.</span></span> <span data-ttu-id="9d6ee-162">웹 사이트 또는 웹 응용 프로그램 프로젝트에 템플릿을 추가 하 여 WCF 서비스를 만들 수 있습니다. 여기에는 Silverlight 클라이언트와의 통신을 지 원하는 서비스 코드와 구성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-162">The template can be added to a Web site or Web application project to create a WCF service, which includes service code and configuration that support communicating with a Silverlight client.</span></span> <span data-ttu-id="9d6ee-163">그런 다음 **서비스 참조 추가** 를 사용 하 여 서비스의 클라이언트 프록시를 클라이언트에 추가 하 고 silverlight 클라이언트와 SILVERLIGHT 사용 WCF 서비스 간에 데이터를 교환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-163">You can then use **Add Service Reference** to add a client proxy of the service to the client, and exchange data between the Silverlight client and the Silverlight-enabled WCF service.</span></span>  
  
 <span data-ttu-id="9d6ee-164">이 템플릿에 액세스 하려면 **솔루션 탐색기** 에서 웹 사이트 또는 웹 응용 프로그램 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **새 항목 추가** 를 클릭 한 다음 **Silverlight 사용 WCF 서비스** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-164">To access this template, right-click a Web site or Web application project in **Solution Explorer**, click **Add a new item**, and click **Silverlight-enabled WCF Service**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d6ee-165">Silverlight 사용 WCF 서비스는 보안 설정을 사용하지 않고 `basicHttpBinding` 엔드포인트를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-165">The Silverlight-enabled WCF Service exposes a `basicHttpBinding` endpoint without enabling any security settings.</span></span> <span data-ttu-id="9d6ee-166">따라서 이 서비스에 연결하는 모든 클라이언트가 서비스에 대한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-166">Therefore, information about the service can be obtained by all clients that connect to this service.</span></span> <span data-ttu-id="9d6ee-167">서비스와 클라이언트 간에 교환되는 메시지도 서명되거나 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-167">Messages exchanged between the service and the client are also not signed or encrypted.</span></span> <span data-ttu-id="9d6ee-168">엔드포인트를 올바르게 보안하려면 ASP.NET 인증, HTTPS 또는 기타 메커니즘을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d6ee-168">To secure the endpoint properly, you should use ASP.NET authentication, HTTPS or other mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6ee-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d6ee-169">See also</span></span>

- [<span data-ttu-id="9d6ee-170">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9d6ee-170">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="9d6ee-171">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9d6ee-171">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
