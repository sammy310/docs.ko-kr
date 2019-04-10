---
title: '자습서: Windows Communication Foundation 클라이언트 만들기'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: a16a0ccabfd0f9fbe69db1ea88d4613185f3c1da
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174371"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="bd114-102">자습서: Windows Communication Foundation 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="bd114-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="bd114-103">이 자습서에서는 기본 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 네 번째를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="bd114-104">자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="bd114-105">WCF 응용 프로그램을 만드는 다음 작업을 WCF 서비스에서 메타 데이터를 검색 하 여 클라이언트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="bd114-106">Visual Studio를 사용 하 여 서비스의 MEX 끝점에서 메타 데이터를 가져오는 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="bd114-107">그러면 visual Studio 사용자가 선택한 언어로 클라이언트 프록시에 대 한 관리 되는 소스 코드 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="bd114-108">또한 클라이언트 구성 파일을 만듭니다 (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="bd114-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="bd114-109">이 파일에는 클라이언트 응용 프로그램을 서비스 끝점에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="bd114-110">Visual Studio에서 클래스 라이브러리 프로젝트에서 WCF 서비스를 호출 하는 경우 사용 합니다 **서비스 참조 추가** 프록시 및 관련된 구성 파일을 자동으로 생성 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="bd114-111">그러나 클래스 라이브러리 프로젝트에서이 구성 파일을 사용 하지 때문에 추가 해야 설정을 생성 된 구성 파일에는 *App.config* 클래스 라이브러리를 호출 하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="bd114-112">대신 사용 합니다 [ServiceModel Metadata 유틸리티 도구](#servicemodel-metadata-utility-tool) 프록시 클래스와 구성 파일을 생성 하기 위해 Visual Studio 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="bd114-113">클라이언트 응용 프로그램은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="bd114-114">이 절차에 설명 되어 [자습서: 클라이언트를 사용 하 여](how-to-use-a-wcf-client.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="bd114-115">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="bd114-116">만들고 WCF 클라이언트에 대 한 콘솔 앱 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="bd114-117">프록시 클래스와 구성 파일을 생성 하는 WCF 서비스에 대 한 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="bd114-118">Windows Communication Foundation 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="bd114-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="bd114-119">Visual Studio에서 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="bd114-120">**파일** 메뉴에서 **열기** > **프로젝트/솔루션** 로 이동한 합니다 **GettingStarted** 솔루션 있습니다 이전에 만든 (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="bd114-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="bd114-121">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-121">Select **Open**.</span></span>

    2. <span data-ttu-id="bd114-122">**뷰** 메뉴에서 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="bd114-123">에 **솔루션 탐색기** 창에서 선택 합니다 **GettingStarted** 솔루션 (최상위 노드)를 선택한 후 **추가** > **새 프로젝트** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="bd114-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="bd114-124">에 **새 프로젝트 추가** 창의 왼쪽된에 있는 선택 합니다 **Windows Desktop** 에서 범주 **Visual C#**  또는 **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="bd114-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="bd114-125">선택 합니다 **콘솔 앱 (.NET Framework)** 템플릿을 enter *GettingStartedClient* 에 대 한 합니다 **이름**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="bd114-126">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-126">Select **OK**.</span></span>

2. <span data-ttu-id="bd114-127">참조를 추가 합니다 **GettingStartedClient** 프로젝트를 <xref:System.ServiceModel> 어셈블리:</span><span class="sxs-lookup"><span data-stu-id="bd114-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1.  <span data-ttu-id="bd114-128">에 **솔루션 탐색기** 창에서를 **참조** 아래에 폴더를 **GettingStartedClient** 프로젝트를 선택한 후 **참조추가** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="bd114-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="bd114-129">에 **참조 추가** 창 아래에 있는 **어셈블리** 창의 왼쪽에서 선택 **Framework**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="bd114-130">찾기 및 선택 **System.ServiceModel**를 선택한 후 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="bd114-131">선택 하 여 솔루션을 저장할 **파일** > **모두 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="bd114-132">계산기 서비스에 대 한 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="bd114-133">에 **솔루션 탐색기** 창에서 합니다 **참조** 아래에 폴더를 **GettingStartedClient** 프로젝트를 선택한 후 **서비스 참조 추가**  바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="bd114-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="bd114-134">에 **서비스 참조 추가** 창에서 **Discover**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="bd114-135">CalculatorService 서비스 시작 및 Visual Studio에 표시 된 **Services** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="bd114-136">선택 **CalculatorService** 여 확장 하 고 서비스에서 구현 되는 서비스 계약을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="bd114-137">기본값을 그대로 두고 **Namespace** 선택한 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="bd114-138">Visual Studio에서 새 항목을 추가 합니다 **연결 된 서비스** 폴더에는 **GettingStartedClient** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="bd114-139">ServiceModel Metadata 유틸리티 도구</span><span class="sxs-lookup"><span data-stu-id="bd114-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="bd114-140">다음 예에서는 선택적으로 사용 하는 방법을 보여 줍니다 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 프록시 클래스 파일을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="bd114-141">이 도구는 프록시 클래스 파일을 생성 하며 *App.config* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="bd114-142">다음 예제에서 프록시를 생성 하는 방법을 보여 줍니다 C# 및 Visual Basic의 경우 각각:</span><span class="sxs-lookup"><span data-stu-id="bd114-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="bd114-143">클라이언트 구성 파일</span><span class="sxs-lookup"><span data-stu-id="bd114-143">Client configuration file</span></span>

<span data-ttu-id="bd114-144">클라이언트를 만든 후 Visual Studio 만듭니다는 **App.config** 에서 구성 파일을 **GettingStartedClient** 다음 예제와 유사 해야 하는 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="bd114-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="bd114-145">아래는 [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) 섹션을 확인 합니다 [ \<끝점 >](../configure-apps/file-schema/wcf/endpoint-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="bd114-146">합니다 **&lt;끝점&gt;** 요소는 다음과 같이 서비스에 액세스 하는 클라이언트 끝점을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="bd114-147">주소: `http://localhost:8000/GettingStarted/CalculatorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="bd114-148">엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-148">The address of the endpoint.</span></span>
- <span data-ttu-id="bd114-149">서비스 계약: `ServiceReference1.ICalculator`합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="bd114-150">WCF 클라이언트와 서비스 간의 통신을 처리 하는 서비스 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="bd114-151">Visual Studio에서이 계약 생성 하는 데 사용 하는 경우 해당 **서비스 참조 추가** 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="bd114-152">본질적으로 GettingStartedLib 프로젝트에 정의 된 계약의 복사본 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="bd114-153">바인딩: <xref:System.ServiceModel.WSHttpBinding>합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="bd114-154">HTTP 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정 하는 바인딩.</span><span class="sxs-lookup"><span data-stu-id="bd114-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bd114-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bd114-155">Next steps</span></span>

<span data-ttu-id="bd114-156">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="bd114-157">만들고 WCF 클라이언트에 대 한 콘솔 앱 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="bd114-158">클라이언트 응용 프로그램에 대 한 프록시 클래스와 구성 파일을 생성 하는 WCF 서비스에 대 한 서비스 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="bd114-159">생성된 된 클라이언트를 사용 하는 방법을 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bd114-160">자습서: WCF 클라이언트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd114-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
