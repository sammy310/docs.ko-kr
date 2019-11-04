---
title: WCF 서비스 호스트(WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: a4efa0d5a46eb0d8e6eef08fd17c38f7db3e7e9e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423831"
---
# <a name="wcf-service-host-wcfsvchostexe"></a><span data-ttu-id="15ff7-102">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="15ff7-102">WCF Service Host (WcfSvcHost.exe)</span></span>

<span data-ttu-id="15ff7-103">WCF (Windows Communication Foundation) 서비스 호스트 (Wcfsvchost.exe)를 사용 하면 Visual Studio 디버거 (F5)를 시작 하 여 구현 된 서비스를 자동으로 호스트 하 고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-103">Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="15ff7-104">그런 다음 WCF 테스트 클라이언트 (Wcftestclient.exe) 또는 자체 클라이언트를 사용 하 여 서비스를 테스트 하 여 잠재적인 오류를 찾아 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-104">You can then test the service using WCF Test Client (WcfTestClient.exe), or your own client, to find and fix any potential errors.</span></span>

## <a name="wcf-service-host"></a><span data-ttu-id="15ff7-105">WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="15ff7-105">WCF Service Host</span></span>

<span data-ttu-id="15ff7-106">WCF 서비스 호스트는 WCF 서비스 프로젝트에서 서비스를 열거 하 고 프로젝트의 구성을 로드 한 다음 찾은 각 서비스에 대 한 호스트를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-106">WCF Service Host enumerates the services in a WCF service project, loads the project’s configuration, and instantiates a host for each service that it finds.</span></span> <span data-ttu-id="15ff7-107">이 도구는 WCF 서비스 템플릿을 통해 Visual Studio에 통합 되며 프로젝트 디버깅을 시작할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-107">The tool is integrated into Visual Studio through the WCF Service template and is invoked when you start to debug your project.</span></span>

<span data-ttu-id="15ff7-108">WCF 서비스 호스트를 사용 하면 개발 하는 동안 추가 코드를 작성 하거나 특정 호스트를 커밋하지 않고도 wcf 서비스 라이브러리 프로젝트에서 wcf 서비스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-108">By using WCF Service Host, you can host a WCF service (in a WCF service library project) without writing extra code or committing to a specific host during development.</span></span>

> [!NOTE]
> <span data-ttu-id="15ff7-109">WCF 서비스 호스트는 부분 신뢰를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-109">WCF Service Host does not support Partial Trust.</span></span> <span data-ttu-id="15ff7-110">부분 신뢰에서 WCF 서비스를 사용 하려면 서비스를 빌드하기 위해 Visual Studio에서 WCF 서비스 라이브러리 프로젝트 템플릿을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="15ff7-110">If you want to use a WCF Service in Partial Trust, do not use the WCF Service Library Project template in Visual Studio to build your service.</span></span> <span data-ttu-id="15ff7-111">대신 wcf 부분 신뢰가 지원 되는 웹 서버에서 서비스를 호스팅할 수 있는 WCF 서비스 웹 사이트 템플릿을 선택 하 여 Visual Studio에서 새 웹 사이트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-111">Instead, create a New WebSite in Visual Studio by choosing the WCF Service WebSite template, which can host the service in a WebServer on which WCF Partial Trust is supported.</span></span>

## <a name="project-types-hosted-by-wcf-service-host"></a><span data-ttu-id="15ff7-112">WCF 서비스 호스트에서 호스팅하는 프로젝트 형식</span><span class="sxs-lookup"><span data-stu-id="15ff7-112">Project Types hosted by WCF Service Host</span></span>

<span data-ttu-id="15ff7-113">Wcf 서비스 호스트는 wcf 서비스 라이브러리, 순차 워크플로 서비스 라이브러리, 상태 시스템 워크플로 서비스 라이브러리 및 배포 서비스 라이브러리와 같은 WCF 서비스 라이브러리 프로젝트 형식을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-113">WCF Service Host can host the following WCF service library project types: WCF Service Library, Sequential Workflow Service Library, State Machine Workflow Service Library and Syndication Service Library.</span></span> <span data-ttu-id="15ff7-114">WCF 서비스 호스트는 **항목 추가** 기능을 사용 하 여 서비스 라이브러리 프로젝트에 추가할 수 있는 서비스를 호스팅할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-114">WCF Service Host can also host those services that can be added to a service library project using the **Add Item** functionality.</span></span> <span data-ttu-id="15ff7-115">여기에는 WCF 서비스, WF 상태 시스템 서비스, WF 순차 서비스, XAML WF 상태 시스템 서비스 및 XAML WF 순차 서비스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-115">This includes WCF Service, WF State Machine Service, WF Sequential Service, XAML WF State Machine Service and XAML WF Sequential Service.</span></span>

<span data-ttu-id="15ff7-116">그러나 이 도구를 사용하여 호스트를 구성할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-116">You should note, however, that the tool will not help you to configure a host.</span></span> <span data-ttu-id="15ff7-117">이 작업의 경우 App.config 파일을 수동으로 편집해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-117">For this task, you must manually edit the App.config file.</span></span> <span data-ttu-id="15ff7-118">또한 이 도구는 사용자 정의 구성 파일의 유효성을 검사하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-118">The tool also does not validate user-defined configuration files.</span></span>

> [!CAUTION]
> <span data-ttu-id="15ff7-119">이 목적을 위해 엔지니어링 되지 않았으므로 WCF 서비스 호스트를 사용 하 여 프로덕션 환경에서 서비스를 호스트 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-119">You should not use WCF Service Host to host services in a production environment, as it was not engineered for this purpose.</span></span>  <span data-ttu-id="15ff7-120">WCF 서비스 호스트는 이러한 환경의 안정성, 보안 및 관리 효율성 요구 사항을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-120">WCF Service Host does not support the reliability, security, and manageability requirements of such an environment.</span></span> <span data-ttu-id="15ff7-121">IIS는 우수한 안정성 및 모니터링 기능을 제공하는 호스팅 서비스의 기본 솔루션이므로 대신 IIS를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-121">Instead, use IIS since it provides superior reliability and monitoring features, and is the preferred solution for hosting services.</span></span> <span data-ttu-id="15ff7-122">서비스 개발이 완료 되 면 WCF 서비스 호스트에서 IIS로 서비스를 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-122">Once development of your services is complete, you should migrate the services from WCF Service Host to IIS.</span></span>

## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a><span data-ttu-id="15ff7-123">Visual Studio 내에서 WCF 서비스 호스트를 사용하기 위한 시나리오</span><span class="sxs-lookup"><span data-stu-id="15ff7-123">Scenarios for Using WCF Service Host inside Visual Studio</span></span>

<span data-ttu-id="15ff7-124">다음 표에서는 Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 디버그를 선택 하 여 찾을 수 있는 **명령줄 인수** 대화 상자의 모든 매개 변수를 보여 줍니다.탭 하 고 **프로젝트 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-124">The following table lists all the parameters in the **Command line arguments** dialog box, which can be found by right-clicking your project in **Solutions Explorer** in Visual Studio, selecting **Properties**, then selecting the **Debug** tab and clicking **Start Project**.</span></span> <span data-ttu-id="15ff7-125">이러한 매개 변수는 WCF 서비스 호스트를 구성 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-125">These parameters are useful in configuring WCF Service Host.</span></span>

|<span data-ttu-id="15ff7-126">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15ff7-126">Parameter</span></span>|<span data-ttu-id="15ff7-127">의미</span><span class="sxs-lookup"><span data-stu-id="15ff7-127">Meaning</span></span>|
|---------------|-------------|
|`/client`|<span data-ttu-id="15ff7-128">서비스가 호스팅된 후에 실행할 실행 파일의 경로를 지정하는 선택적 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-128">An optional parameter that specifies the path to an executable to run after the services are hosted.</span></span> <span data-ttu-id="15ff7-129">그러면 호스팅 후 WCF 테스트 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-129">This launches WCF Test Client following hosting.</span></span>|
|`/clientArg`|<span data-ttu-id="15ff7-130">문자열을 사용자 지정 클라이언트 애플리케이션에 전달되는 인수로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-130">Specify a string as an argument that is passed to the custom client application.</span></span>|
|`/?`|<span data-ttu-id="15ff7-131">도움말 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-131">Displays the help text.</span></span>|

#### <a name="using-wcf-test-client"></a><span data-ttu-id="15ff7-132">WCF 테스트 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="15ff7-132">Using WCF Test Client</span></span>

<span data-ttu-id="15ff7-133">새 WCF 서비스 프로젝트를 만들고 F5 키를 눌러 디버거를 시작 하면 WCF 서비스 호스트는 프로젝트에서 발견 한 모든 서비스를 호스트 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-133">After you create a new WCF service project and press F5 to start the debugger, WCF Service Host starts hosting all the services it finds in your project.</span></span> <span data-ttu-id="15ff7-134">WCF 테스트 클라이언트는 구성 파일에 정의 된 서비스 끝점 목록을 자동으로 열고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-134">WCF Test Client automatically opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="15ff7-135">주 창에서 매개 변수를 테스트하고 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-135">From the main window, you can test the parameters and invoke your service.</span></span>

<span data-ttu-id="15ff7-136">WCF 테스트 클라이언트가 사용 되는지 확인 하려면 Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **디버그** 탭을 선택 합니다. **프로젝트 시작** 을 클릭 하 고 다음이 다음에 표시 **되는지 확인 합니다. 명령줄 인수** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="15ff7-136">To make sure that WCF Test Client is used, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and ensure that the following appears in the **Command line arguments** dialog box.</span></span>

`/client:WcfTestClient.exe`

#### <a name="using-a-custom-client"></a><span data-ttu-id="15ff7-137">사용자 지정 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="15ff7-137">Using a Custom Client</span></span>

<span data-ttu-id="15ff7-138">사용자 지정 클라이언트를 사용 하려면 Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **디버그** 탭을 선택 합니다. 명령줄 인수에서 **프로젝트 시작** 을 클릭 하 고 `/client` 매개 변수를 편집 합니다.다음 예제에 표시 된 것 처럼 사용자 지정 클라이언트를 가리키는 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-138">To use a custom client, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and edit the `/client` parameter in the **Command line arguments** dialog box to point to your custom client, as indicated in the following example.</span></span>

`/client:"path/CustomClient.exe"`

<span data-ttu-id="15ff7-139">F5 키를 눌러 서비스를 다시 시작 하면 디버거를 시작할 때 WCF 서비스 호스트가 자동으로 사용자 지정 클라이언트를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-139">When you press F5 to start the service again, WCF Service Host automatically starts your custom client when you launch the debugger.</span></span>

<span data-ttu-id="15ff7-140">또한 `/clientArg:` 매개 변수를 사용하여 다음 예제에서처럼 문자열을 사용자 지정 클라이언트 애플리케이션에 전달되는 인수로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-140">You can also use the `/clientArg:` parameter to specify a string as an argument that is passed to the custom client application, as indicated in the following example.</span></span>

`/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`

<span data-ttu-id="15ff7-141">예를 들어 배포 서비스 라이브러리 템플릿을 사용하는 경우 다음 명령줄 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-141">For example, if you are using the Syndication Service Library template, you can use the following command line arguments,</span></span>

`/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`

#### <a name="specifying-no-client"></a><span data-ttu-id="15ff7-142">클라이언트 없음 지정</span><span class="sxs-lookup"><span data-stu-id="15ff7-142">Specifying No Client</span></span>

<span data-ttu-id="15ff7-143">WCF 서비스를 호스팅하는 후에 클라이언트를 사용 하지 않도록 지정 하려면 Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **디버그** 탭을 선택 합니다. **프로젝트 시작** 을 클릭 하 고 명령을 그대로 둡니다.  **줄 인수** 대화 상자를 비워 둡니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-143">To specify that no client will be used after WCF service hosting, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and leave the **Command line arguments** dialog box blank.</span></span>

#### <a name="using-a-custom-host"></a><span data-ttu-id="15ff7-144">사용자 지정 호스트 사용</span><span class="sxs-lookup"><span data-stu-id="15ff7-144">Using a Custom Host</span></span>

<span data-ttu-id="15ff7-145">사용자 지정 호스트를 사용 하려면 Visual Studio의 **솔루션 탐색기** 에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **속성**을 선택한 다음 **디버그** 탭을 선택 합니다. **시작 외부 프로그램** 을 클릭 하 고 사용자 지정 호스트의 전체 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-145">To use a custom host, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start External Program** and enter the full path to the custom host.</span></span> <span data-ttu-id="15ff7-146">**명령줄 인수** 대화 상자를 사용 하 여 호스트에 전달할 인수를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-146">You can also use the **Command line arguments** dialog box to specify arguments to be passed to the host.</span></span>

## <a name="wcf-service-host-user-interface"></a><span data-ttu-id="15ff7-147">WCF 서비스 호스트 사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15ff7-147">WCF Service Host User Interface</span></span>

<span data-ttu-id="15ff7-148">Visual Studio 내에서 F5 키를 눌러 WCF 서비스 호스트를 처음 호출 하면 **Wcf 서비스 호스트** 창이 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-148">When you initially invoke WCF Service Host (by pressing F5 inside Visual Studio), the **WCF Service Host** window automatically opens.</span></span> <span data-ttu-id="15ff7-149">WCF 서비스 호스트가 실행 중일 때 프로그램의 아이콘이 알림 영역에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-149">When WCF Service Host is running, the program's icon appears in the notification area.</span></span> <span data-ttu-id="15ff7-150">아이콘을 두 번 클릭 하 여 **WCF 서비스 호스트** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-150">Double-click the icon to open the **WCF Service Host** window</span></span>

<span data-ttu-id="15ff7-151">서비스를 호스팅하는 동안 오류가 발생 하면 WCF 서비스 호스트 대화 상자가 열리고 관련 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-151">When errors occur during service hosting, WCF Service Host dialog box will open to display relevant information.</span></span>

<span data-ttu-id="15ff7-152">**WCF 서비스 호스트** 주 창에는 두 개의 메뉴가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-152">The **WCF Service Host** main window contains two menus:</span></span>

- <span data-ttu-id="15ff7-153">**File**: **Close** 및 **Exit** 명령을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-153">**File**: Contains the **Close** and **Exit** commands.</span></span> <span data-ttu-id="15ff7-154">**닫기**를 클릭 하면 **WCF 서비스 호스트** 대화 상자가 닫히지만 서비스는 계속 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-154">When you click **Close**, the **WCF Service Host** dialog box closes, but the services continue to be hosted.</span></span> <span data-ttu-id="15ff7-155">**끝내기**를 클릭 하면 WCF 서비스 호스트도 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-155">When you click **Exit**, WCF Service Host is also shut down.</span></span> <span data-ttu-id="15ff7-156">또한 호스팅되는 서비스가 모두 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-156">This also stops all hosted services.</span></span>

- <span data-ttu-id="15ff7-157">**도움말**: 버전 정보를 포함 하는 **About** 명령을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-157">**Help**: Contains the **About** command that contains version information.</span></span> <span data-ttu-id="15ff7-158">또한 도움말 파일을 열 수 있는 **도움말** 명령도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-158">It also contains the **Help** command that can open a help file.</span></span>

<span data-ttu-id="15ff7-159">기본 **WCF 서비스 호스트** 창에는 다음과 같은 두 가지 영역이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-159">The main **WCF Service Host** window contains two areas:</span></span>

- <span data-ttu-id="15ff7-160">첫 번째 영역은 **서비스**입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-160">The first area is **Service**.</span></span> <span data-ttu-id="15ff7-161">여기에는 모든 서비스의 기본 정보를 표시하는 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-161">It contains a list that displays basic information of all services.</span></span> <span data-ttu-id="15ff7-162">이 정보에는 다음과 같은 내용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-162">The information includes:</span></span>

  - <span data-ttu-id="15ff7-163">**서비스**: 모든 서비스를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-163">**Service**: Lists all the services.</span></span>

  - <span data-ttu-id="15ff7-164">**상태**: 서비스의 상태를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-164">**Status**: Lists the status of the service.</span></span> <span data-ttu-id="15ff7-165">유효한 값은 "시작됨", "중지됨" 및 "오류"입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-165">Valid values are "Started", "Stopped," and "Error".</span></span>

  - <span data-ttu-id="15ff7-166">**메타 데이터 주소**: 서비스의 메타 데이터 주소를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-166">**Metadata Address**: Displays the metadata address of the services.</span></span>

- <span data-ttu-id="15ff7-167">두 번째 영역은 **추가 정보**입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-167">The second area is **Additional Information**.</span></span> <span data-ttu-id="15ff7-168">**서비스 영역에서** 특정 서비스 회선이 선택 된 경우 서비스 상태에 대 한 자세한 설명을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-168">It displays a detailed explanation of the service status when the specific service line is selected in the **Service** area.</span></span> <span data-ttu-id="15ff7-169">상태가 Error인 경우 화면에서 전체 오류 메시지를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-169">If the status is Error, you can view the full error message on the screen.</span></span>

## <a name="stopping-wcf-service-host"></a><span data-ttu-id="15ff7-170">WCF 서비스 호스트 중지</span><span class="sxs-lookup"><span data-stu-id="15ff7-170">Stopping WCF Service Host</span></span>

<span data-ttu-id="15ff7-171">다음 네 가지 방법으로 WCF 서비스 호스트를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-171">You can shut down WCF Service Host in the following four ways:</span></span>

- <span data-ttu-id="15ff7-172">Visual Studio에서 디버깅 세션을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-172">Stop the debugging session in Visual Studio.</span></span>

- <span data-ttu-id="15ff7-173">**WCF 서비스 호스트** 창의 **파일** 메뉴에서 **끝내기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-173">Select **Exit** from the **File** menu in the **WCF Service Host** window.</span></span>

- <span data-ttu-id="15ff7-174">시스템 알림 영역에서 WCF 서비스 호스트 트레이 아이콘의 상황에 맞는 메뉴에서 **끝내기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-174">Select **Exit** from context menu of WCF Service Host tray icon in the system notification area.</span></span>

- <span data-ttu-id="15ff7-175">WCF 테스트 클라이언트를 사용 하는 경우 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-175">Exit WCF Test Client if it is being used.</span></span>

## <a name="using-service-host-without-administrator-privilege"></a><span data-ttu-id="15ff7-176">관리자 권한 없이 서비스 호스트 사용</span><span class="sxs-lookup"><span data-stu-id="15ff7-176">Using Service Host without Administrator privilege</span></span>

<span data-ttu-id="15ff7-177">관리자 권한이 없는 사용자가 WCF 서비스를 개발할 수 있도록 Visual Studio를 설치 하는 동안 네임 스페이스 "http://+:8731/Design_Time_Addresses"에 대 한 ACL (Access Control 목록)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-177">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="15ff7-178">ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-178">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="15ff7-179">관리자는이 ACL에서 사용자를 추가 또는 제거 하거나 추가 포트를 열 수 있습니다. 이 ACL을 통해 사용자는 관리자 권한을 부여 하지 않고 WCF 서비스 자동 호스트 (Wcfsvchost.exe)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-179">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>

<span data-ttu-id="15ff7-180">[!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-180">You can modify access using the netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="15ff7-181">다음은 netsh.exe를 사용하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="15ff7-181">The following is an example of using netsh.exe.</span></span>

```console
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>
```

<span data-ttu-id="15ff7-182">Netsh.exe에 대 한 자세한 내용은 "[Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법](https://go.microsoft.com/fwlink/?LinkId=97877)"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15ff7-182">For more information on netsh.exe, see "[How to Use the Netsh.exe Tool and Command-Line Switches](https://go.microsoft.com/fwlink/?LinkId=97877)".</span></span>

## <a name="see-also"></a><span data-ttu-id="15ff7-183">참조</span><span class="sxs-lookup"><span data-stu-id="15ff7-183">See also</span></span>

- [<span data-ttu-id="15ff7-184">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="15ff7-184">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
