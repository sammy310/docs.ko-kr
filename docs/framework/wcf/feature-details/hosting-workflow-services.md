---
title: 워크플로 서비스 호스팅
ms.date: 03/30/2017
ms.assetid: 2d55217e-8697-4113-94ce-10b60863342e
ms.openlocfilehash: 3bd45575e06ba742b0e6c43766c5e80dff47c03b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256003"
---
# <a name="hosting-workflow-services"></a><span data-ttu-id="f59e8-102">워크플로 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f59e8-102">Hosting Workflow Services</span></span>

<span data-ttu-id="f59e8-103">워크플로 서비스가 들어오는 메시지에 응답하기 위해서는 해당 워크플로 서비스를 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-103">A workflow service must be hosted for it to respond to incoming messages.</span></span> <span data-ttu-id="f59e8-104">워크플로 서비스는 WCF 메시징 인프라를 사용하기 때문에 WCF 서비스와 비슷한 방식으로 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-104">Workflow services use the WCF messaging infrastructure and are therefore hosted in similar ways.</span></span> <span data-ttu-id="f59e8-105">WCF 서비스와 마찬가지로 워크플로 서비스는 모든 관리 되는 응용 프로그램, 인터넷 정보 서비스 (IIS) 또는 WAS (Windows Process Activation Services)에서 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-105">Like WCF services, workflow services can be hosted in any managed application, under Internet Information Services (IIS), or under Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="f59e8-106">또한 Windows Server 응용 프로그램 패브릭에서 워크플로 서비스를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-106">In addition, workflow services can be hosted under Windows Server App Fabric.</span></span> <span data-ttu-id="f59e8-107">Windows Server Fabric에 대 한 자세한 내용은 [Windows Server App fabric 설명서](/previous-versions/appfabric/ff384253(v=azure.10)), [appfabric 호스팅 기능](/previous-versions/appfabric/ee677189(v=azure.10))및 [appfabric 호스팅 개념](/previous-versions/appfabric/ee677371(v=azure.10))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f59e8-107">For more information about Windows Server App Fabric see [Windows Server App Fabric documentation](/previous-versions/appfabric/ff384253(v=azure.10)), [AppFabric Hosting Features](/previous-versions/appfabric/ee677189(v=azure.10)), and [AppFabric Hosting Concepts](/previous-versions/appfabric/ee677371(v=azure.10)).</span></span> <span data-ttu-id="f59e8-108">WCF 서비스를 호스팅하는 다양 한 방법에 대 한 자세한 내용은 [호스팅 서비스](../hosting-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f59e8-108">For more information about the various ways to host WCF services see [Hosting Services](../hosting-services.md).</span></span>

## <a name="hosting-in-a-managed-application"></a><span data-ttu-id="f59e8-109">관리되는 애플리케이션에서 호스팅</span><span class="sxs-lookup"><span data-stu-id="f59e8-109">Hosting in a managed application</span></span>

 <span data-ttu-id="f59e8-110">관리되는 애플리케이션에서 워크플로 서비스를 호스팅하려면 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-110">To host a workflow service in a managed application, use the <xref:System.ServiceModel.Activities.WorkflowServiceHost> class.</span></span> <span data-ttu-id="f59e8-111"><xref:System.ServiceModel.Activities.WorkflowServiceHost> 생성자를 사용하면 singleton 워크플로 서비스 인스턴스, 워크플로 서비스 정의 또는 워크플로 메시징 작업을 사용하는 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-111">The <xref:System.ServiceModel.Activities.WorkflowServiceHost> constructor allows you to specify a singleton workflow service instance, a workflow service definition, or an activity that uses the workflow messaging activities.</span></span> <span data-ttu-id="f59e8-112"><xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>을 호출하면 서비스가 들어오는 메시지에 대한 수신 대기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-112">Calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> causes the service to start listening for incoming messages.</span></span>

## <a name="hosting-under-iis-or-was"></a><span data-ttu-id="f59e8-113">IIS 또는 WAS에서 호스팅</span><span class="sxs-lookup"><span data-stu-id="f59e8-113">Hosting under IIS or WAS</span></span>

 <span data-ttu-id="f59e8-114">IIS 또는 WAS에서 워크플로 서비스를 호스팅하는 작업에는 가상 디렉터리를 만들고 이 가상 디렉터리에 서비스와 해당 동작을 정의하는 파일을 저장하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-114">Hosting a workflow service under IIS or WAS involves creating a virtual directory and placing files in the virtual directory that define the service and its behavior.</span></span> <span data-ttu-id="f59e8-115">IIS 또는 WAS에서는 다음과 같은 여러 가지 방법으로 워크플로 서비스를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-115">When hosting a workflow service under IIS or WAS there are several possibilities:</span></span>

- <span data-ttu-id="f59e8-116">워크플로 서비스를 정의하는 .xamlx 파일을 서비스 동작, 엔드포인트 및 기타 구성 요소를 지정하는 Web.config 파일과 함께 IIS/WAS 가상 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-116">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory along with a Web.config file that specifies the service behaviors, endpoints, and other configuration elements.</span></span>

- <span data-ttu-id="f59e8-117">워크플로 서비스를 정의하는 .xamlx 파일을 IIS/WAS 가상 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-117">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory.</span></span> <span data-ttu-id="f59e8-118">.xamlx 파일을 사용하면 노출할 엔드포인트를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-118">The .xamlx file specifies the endpoints to expose.</span></span> <span data-ttu-id="f59e8-119">엔드포인트는 다음 예제와 같이 `WorkflowService.Endpoints` 요소에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-119">Endpoints are specified in a `WorkflowService.Endpoints` element as shown in the following example.</span></span>

    ```xml
    <WorkflowService xmlns="http://schemas.microsoft.com/netfx/2009/xaml/servicemodel"  xmlns:p1="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:sad="clr-namespace:System.Activities.Debugger;assembly=System.Activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
      <WorkflowService.Endpoints>
        <Endpoint ServiceContractName="IWorkFlowEchoService" AddressUri="">
          <Endpoint.Binding>
            <BasicHttpBinding />
          </Endpoint.Binding>
        </Endpoint>
      </WorkflowService.Endpoints>
    <!-- ... -->
    </WorkflowService>
    ```

    > [!NOTE]
    > <span data-ttu-id="f59e8-120">.xamlx 파일에는 동작을 지정할 수 없으므로 동작 설정을 지정해야 하는 경우에는 Web.config를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-120">Behaviors cannot be specified in a .xamlx file, so you must use a Web.config if you need to specify behavior settings.</span></span>

- <span data-ttu-id="f59e8-121">워크플로 서비스를 정의하는 .xamlx 파일을 IIS/WAS 가상 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-121">Place a .xamlx file that defines the workflow service in an IIS/WAS virtual directory.</span></span> <span data-ttu-id="f59e8-122">또한 .svc 파일도 IIS/WAS 가상 디렉터리에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-122">In addition, place a .svc file in the virtual directory.</span></span> <span data-ttu-id="f59e8-123">.svc 파일을 사용하면 사용자 지정 웹 서비스 호스트 팩터리를 지정하거나, 사용자 지정 동작을 적용하거나, 사용자 지정 위치에서 구성을 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-123">The .svc file allows you to specify a custom Web service host factory, apply custom behavior, or load configuration from a custom location.</span></span>

- <span data-ttu-id="f59e8-124">IIS/WAS 가상 디렉터리에 WCF 메시징 작업을 사용하는 작업이 포함된 어셈블리를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-124">Place an assembly in the IIS/WAS virtual directory that contains an activity that uses the WCF messaging activities.</span></span>

 <span data-ttu-id="f59e8-125">워크플로 서비스를 정의 하는 .xamlx 파일에는 <`Service`> root 요소 또는에서 파생 된 형식을 포함 하는 루트 요소가 포함 되어야 <xref:System.Workflow.ComponentModel.Activity> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-125">A .xamlx file that defines a workflow service must contain a <`Service`> root element or a root element that contains any type derived from <xref:System.Workflow.ComponentModel.Activity>.</span></span> <span data-ttu-id="f59e8-126">Visual Studio 작업 템플릿을 사용 하는 경우 .xamlx 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-126">When using the Visual Studio activity template, a .xamlx file is created.</span></span> <span data-ttu-id="f59e8-127">WCF Workflow Service 템플릿을 사용 하는 경우 .xamlx 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-127">When using the WCF Workflow Service template, a .xamlx file is created.</span></span>

## <a name="hosting-workflow-services-under-windows-server-app-fabric"></a><span data-ttu-id="f59e8-128">Windows Server AppFabric에서 워크플로 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f59e8-128">Hosting Workflow Services under Windows Server App Fabric</span></span>

 <span data-ttu-id="f59e8-129">Windows Server AppFabric에서 워크플로 서비스를 호스팅하는 것은 IIS/WAS에서 호스팅하는 것과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-129">Hosting a workflow service under Windows Server App Fabric is done in the same way as hosting under IIS/WAS.</span></span> <span data-ttu-id="f59e8-130">유일한 차이점은 Windows Server AppFabric이 설치된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-130">The only difference is the fact that Windows Server App Fabric is installed.</span></span> <span data-ttu-id="f59e8-131">Windows Server Fabric은 PowerShell commandlets 뿐만 아니라 인터넷 정보 서비스 Manager에 추가 되는 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-131">Windows Server App Fabric provides tools that are added to Internet Information Services Manager, as well as PowerShell commandlets.</span></span> <span data-ttu-id="f59e8-132">이러한 도구를 사용하면 워크플로 서비스와 WCF 서비스의 배포, 관리 및 추적을 간단하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-132">These tools simplify deploying, managing, and tracking of workflow services and WCF services.</span></span>

## <a name="referencing-custom-activities"></a><span data-ttu-id="f59e8-133">사용자 지정 작업 참조</span><span class="sxs-lookup"><span data-stu-id="f59e8-133">Referencing Custom Activities</span></span>

 <span data-ttu-id="f59e8-134">`Assemblies` `System.Web.Compilation` 응용 프로그램 도메인에 로드 되 고 XAML 역직렬 변환기가 형식을 찾을 수 있도록 사용자 지정 활동에 대 한 참조를 <>의 <> 섹션에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-134">References to custom activities must be added to the <`Assemblies`> section under <`System.Web.Compilation`> so that they are loaded into the Application Domain and the XAML deserializer is able to locate the types.</span></span> <span data-ttu-id="f59e8-135">이러한 설정은 애플리케이션 수준에서 만들거나 컴퓨터의 모든 애플리케이션에 설정을 적용해야 하는 경우 루트 Web.config에서 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-135">These settings can be made at the application level or in the root Web.config if the settings should be applied to all applications on the machine.</span></span>

## <a name="deployment"></a><span data-ttu-id="f59e8-136">배포</span><span class="sxs-lookup"><span data-stu-id="f59e8-136">Deployment</span></span>

 <span data-ttu-id="f59e8-137">웹 배포 도구는 배포 작업을 보다 쉽게 수행할 수 있도록 하기 위해 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-137">The Web Deployment tool has been created to make the job of deployment easier.</span></span> <span data-ttu-id="f59e8-138">이 도구를 사용하면 IIS 6.0과 IIS 7.0 사이에서 애플리케이션을 마이그레이션하고, 서버 팜을 동기화하고, 웹 애플리케이션을 패키징, 보관 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f59e8-138">The tool allows you to migrate applications between IIS 6.0 and IIS 7.0, synchronize server farms, and package, archive and deploy Web applications.</span></span> <span data-ttu-id="f59e8-139">자세한 내용은 [MS Deployment Tool](https://go.microsoft.com/fwlink/?LinkId=178690)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f59e8-139">For more information, see [MS Deployment Tool](https://go.microsoft.com/fwlink/?LinkId=178690).</span></span>

## <a name="see-also"></a><span data-ttu-id="f59e8-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f59e8-140">See also</span></span>

- [<span data-ttu-id="f59e8-141">워크플로 서비스 호스트 내부 기능</span><span class="sxs-lookup"><span data-stu-id="f59e8-141">Workflow Service Host Internals</span></span>](workflow-service-host-internals.md)
- [<span data-ttu-id="f59e8-142">WorkflowServiceHost 구성</span><span class="sxs-lookup"><span data-stu-id="f59e8-142">Configuring WorkflowServiceHost</span></span>](configuring-workflowservicehost.md)
