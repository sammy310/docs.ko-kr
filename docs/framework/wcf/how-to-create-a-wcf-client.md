---
title: '자습서: Windows Communication Foundation 클라이언트 만들기'
description: Wcf 응용 프로그램을 만들기 시작 하는 데 도움이 되는 일련의 문서에서 WCF 서비스의 메타 데이터를 검색 하 여 클라이언트를 만드는 방법에 대해 알아봅니다.
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d5a2a2b5175c9e34eaf1dbaff20ac57f34117c4e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246326"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="197e6-103">자습서: Windows Communication Foundation 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="197e6-103">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="197e6-104">이 자습서에서는 WCF (기본 Windows Communication Foundation) 응용 프로그램을 만드는 데 필요한 5 가지 작업 중 네 번째 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-104">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="197e6-105">자습서에 대 한 개요는 [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="197e6-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="197e6-106">WCF 응용 프로그램을 만들기 위한 다음 작업은 WCF 서비스에서 메타 데이터를 검색 하 여 클라이언트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-106">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="197e6-107">Visual Studio를 사용 하 여 서비스의 MEX 끝점에서 메타 데이터를 가져오는 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-107">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="197e6-108">그러면 Visual Studio에서 사용자가 선택한 언어로 클라이언트 프록시에 대 한 관리 되는 소스 코드 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-108">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="197e6-109">또한 클라이언트 구성 파일 (*App.config*)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-109">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="197e6-110">이 파일을 사용 하면 클라이언트 응용 프로그램이 끝점에서 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-110">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="197e6-111">Visual Studio의 클래스 라이브러리 프로젝트에서 WCF 서비스를 호출 하는 경우 **서비스 참조 추가** 기능을 사용 하 여 프록시 및 연결 된 구성 파일을 자동으로 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-111">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="197e6-112">그러나 클래스 라이브러리 프로젝트에서는이 구성 파일을 사용 하지 않으므로 생성 된 구성 파일의 설정을 클래스 라이브러리를 호출 하는 실행 파일에 대 한 *App.config* 파일에 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-112">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="197e6-113">대신, Visual Studio 대신 [ServiceModel Metadata 유틸리티 도구](#servicemodel-metadata-utility-tool) 를 사용 하 여 프록시 클래스와 구성 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-113">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="197e6-114">클라이언트 애플리케이션은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-114">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="197e6-115">이 절차는 [자습서: 클라이언트 사용](how-to-use-a-wcf-client.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-115">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="197e6-116">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-116">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="197e6-117">WCF 클라이언트용 콘솔 응용 프로그램 프로젝트를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-117">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="197e6-118">WCF 서비스에 대 한 서비스 참조를 추가 하 여 프록시 클래스 및 구성 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-118">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="197e6-119">Windows Communication Foundation 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="197e6-119">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="197e6-120">Visual Studio에서 콘솔 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-120">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="197e6-121">**파일** 메뉴에서 **Open**  >  **프로젝트/솔루션** 열기를 선택 하 고 이전에 만든 **get로 시작** 된 솔루션 (*gete r 시작 .sln*)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-121">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="197e6-122">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-122">Select **Open**.</span></span>

    2. <span data-ttu-id="197e6-123">**보기** 메뉴에서 **솔루션 탐색기**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-123">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="197e6-124">**솔루션 탐색기** 창에서 **get이상 시작** 된 솔루션 (최상위 노드)을 선택한 다음 **Add**  >  바로 가기 메뉴에서**새 프로젝트** 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-124">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="197e6-125">**새 프로젝트 추가** 창의 왼쪽에 있는 **Visual c #** 또는 **Visual Basic**에서 **Windows 데스크톱** 범주를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-125">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="197e6-126">**콘솔 앱 (.NET Framework)** 템플릿을 선택 하 고 **이름**에 *GettingStartedClient* 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-126">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="197e6-127">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-127">Select **OK**.</span></span>

2. <span data-ttu-id="197e6-128">**GettingStartedClient** 프로젝트의 참조를 어셈블리에 추가 합니다 <xref:System.ServiceModel> .</span><span class="sxs-lookup"><span data-stu-id="197e6-128">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="197e6-129">**솔루션 탐색기** 창의 **GettingStartedClient** 프로젝트 아래에서 **참조** 폴더를 선택 하 고 바로 가기 메뉴에서 **참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-129">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="197e6-130">**참조 추가** 창의 창 왼쪽에 있는 **어셈블리** 에서 **프레임 워크**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-130">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="197e6-131">**System.servicemodel**을 찾아 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-131">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="197e6-132">**파일**  >  **모두 저장**을 선택 하 여 솔루션을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-132">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="197e6-133">계산기 서비스에 대 한 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-133">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="197e6-134">**솔루션 탐색기** 창의 **GettingStartedClient** 프로젝트 아래에서 **참조** 폴더를 선택 하 고 바로 가기 메뉴에서 **서비스 참조 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-134">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="197e6-135">**서비스 참조 추가** 창에서 **검색**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-135">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="197e6-136">CalculatorService 서비스가 시작 되 고 Visual Studio가 **서비스** 상자에이를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-136">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="197e6-137">**CalculatorService** 를 선택 하 여 확장 하 고 서비스에서 구현 하는 서비스 계약을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-137">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="197e6-138">기본 **네임 스페이스** 를 그대로 두고 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-138">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="197e6-139">**GettingStartedClient** 프로젝트의 **연결된 서비스** 폴더 아래에 새 항목이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-139">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="197e6-140">ServiceModel Metadata 유틸리티 도구</span><span class="sxs-lookup"><span data-stu-id="197e6-140">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="197e6-141">다음 예제에서는 선택적으로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 프록시 클래스 파일을 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-141">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="197e6-142">이 도구는 프록시 클래스 파일 및 *App.config* 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-142">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="197e6-143">다음 예제에서는 c # 및 Visual Basic에서 각각 프록시를 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-143">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="197e6-144">클라이언트 구성 파일</span><span class="sxs-lookup"><span data-stu-id="197e6-144">Client configuration file</span></span>

<span data-ttu-id="197e6-145">클라이언트를 만든 후 Visual Studio에서 **GettingStartedClient** 프로젝트에 **App.config** 구성 파일을 만듭니다 .이 예제는 다음 예제와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-145">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="197e6-146">섹션 아래에서 [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) 요소를 확인 [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-146">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="197e6-147">\*\* &lt; 끝점 &gt; \*\* 요소는 클라이언트에서 서비스에 액세스 하는 데 사용 하는 끝점을 다음과 같이 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-147">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="197e6-148">주소: `http://localhost:8000/GettingStarted/CalculatorService` .</span><span class="sxs-lookup"><span data-stu-id="197e6-148">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="197e6-149">엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-149">The address of the endpoint.</span></span>
- <span data-ttu-id="197e6-150">서비스 계약: `ServiceReference1.ICalculator` .</span><span class="sxs-lookup"><span data-stu-id="197e6-150">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="197e6-151">서비스 계약은 WCF 클라이언트와 서비스 간의 통신을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-151">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="197e6-152">**서비스 참조 추가** 함수를 사용 하는 경우 Visual Studio에서이 계약을 생성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-152">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="197e6-153">기본적으로 GettingStartedLib 프로젝트에 정의 된 계약의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-153">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="197e6-154">바인딩: <xref:System.ServiceModel.WSHttpBinding> .</span><span class="sxs-lookup"><span data-stu-id="197e6-154">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="197e6-155">바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-155">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="197e6-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="197e6-156">Next steps</span></span>

<span data-ttu-id="197e6-157">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-157">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="197e6-158">WCF 클라이언트용 콘솔 응용 프로그램 프로젝트를 만들고 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-158">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="197e6-159">WCF 서비스에 대 한 서비스 참조를 추가 하 여 클라이언트 응용 프로그램에 대 한 프록시 클래스 및 구성 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="197e6-159">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="197e6-160">다음 자습서로 이동 하 여 생성 된 클라이언트를 사용 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="197e6-160">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="197e6-161">자습서: WCF 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="197e6-161">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
