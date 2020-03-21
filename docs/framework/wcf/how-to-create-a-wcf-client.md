---
title: '자습서: Windows 통신 파운데이션 클라이언트 만들기'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184107"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="a9e6b-102">자습서: Windows 통신 파운데이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="a9e6b-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="a9e6b-103">이 자습서에서는 기본 WCF(Windows 통신 Foundation) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 네 번째 에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="a9e6b-104">자습서의 개요는 [자습서: Windows 통신 파운데이션 응용 프로그램을 시작](getting-started-tutorial.md)하십시오.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="a9e6b-105">WCF 응용 프로그램을 만드는 다음 작업은 WCF 서비스에서 메타데이터를 검색하여 클라이언트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="a9e6b-106">Visual Studio를 사용하여 서비스의 MEX 끝점에서 메타데이터를 가져오는 서비스 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="a9e6b-107">그런 다음 Visual Studio는 선택한 언어로 클라이언트 프록시에 대해 관리되는 소스 코드 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="a9e6b-108">또한 클라이언트 구성*파일(App.config)을*만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="a9e6b-109">이 파일을 사용하면 클라이언트 응용 프로그램이 끝점에서 서비스에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6b-110">Visual Studio의 클래스 라이브러리 프로젝트에서 WCF 서비스를 호출하는 경우 **서비스 참조 추가** 기능을 사용하여 프록시 및 관련 구성 파일을 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="a9e6b-111">그러나 클래스 라이브러리 프로젝트는 이 구성 파일을 사용하지 않으므로 클래스 라이브러리를 호출하는 실행 파일에 대해 생성된 구성 파일의 설정을 *App.config* 파일에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="a9e6b-112">또는 Visual Studio 대신 [ServiceModel 메타데이터 유틸리티 도구를](#servicemodel-metadata-utility-tool) 사용하여 프록시 클래스 및 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="a9e6b-113">클라이언트 애플리케이션은 생성된 프록시 클래스를 사용하여 서비스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="a9e6b-114">이 절차는 [자습서: 클라이언트 사용에](how-to-use-a-wcf-client.md)설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="a9e6b-115">이 자습서에서는 다음 작업 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a9e6b-116">WCF 클라이언트에 대한 콘솔 앱 프로젝트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="a9e6b-117">WCF 서비스에 서비스 참조를 추가하여 프록시 클래스 및 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="a9e6b-118">Windows 통신 기반 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="a9e6b-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="a9e6b-119">Visual Studio에서 콘솔 앱 프로젝트 만들기:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="a9e6b-120">**파일** 메뉴에서**프로젝트/솔루션** **열기를** > 선택하고 이전에 만든 **GettingStarted** *솔루션(GettingStarted.sln)을*찾아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="a9e6b-121">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-121">Select **Open**.</span></span>

    2. <span data-ttu-id="a9e6b-122">**보기** 메뉴에서 **솔루션 탐색기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="a9e6b-123">솔루션 **탐색기** 창에서 **GettingStarted** 솔루션(맨 위 노드)을 선택한 다음 바로 가기 메뉴에서**새 프로젝트** **추가를** > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="a9e6b-124">새 **프로젝트 추가** 창왼쪽에서 **Visual C#** 또는 **Visual Basic**에서 Windows **데스크톱** 범주를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="a9e6b-125">콘솔 **앱(.NET 프레임워크)** 템플릿을 선택하고 **이름에**대해 *GettingStartedClient* 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="a9e6b-126">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-126">Select **OK**.</span></span>

2. <span data-ttu-id="a9e6b-127">어셈블리에 **GettingStartedClient** 프로젝트에서 <xref:System.ServiceModel> 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="a9e6b-128">솔루션 **탐색기** 창에서 **GettingStartedClient** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **참조 추가를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="a9e6b-129">참조 **추가** 창에서 창 왼쪽에 있는 **어셈블리** 아래에서 **프레임워크**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="a9e6b-130">**System.ServiceModel을**찾아서 선택한 다음 **확인을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="a9e6b-131">**파일** > 저장 모두를 선택하여 솔루션을**저장합니다.**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="a9e6b-132">계산기 서비스에 서비스 참조추가:</span><span class="sxs-lookup"><span data-stu-id="a9e6b-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="a9e6b-133">솔루션 **탐색기** 창에서 **GettingStartedClient** 프로젝트 에서 **참조** 폴더를 선택한 다음 바로 가기 메뉴에서 **서비스 참조 추가를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="a9e6b-134">서비스 **참조 추가** 창에서 **검색을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="a9e6b-135">계산기서비스 서비스가 시작되고 Visual Studio가 **서비스** 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="a9e6b-136">**계산기 서비스를** 선택하여 확장하고 서비스에서 구현한 서비스 계약을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="a9e6b-137">기본 **네임스페이스를** 두고 **확인을**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="a9e6b-138">Visual Studio는 **GettingStartedClient** 프로젝트의 **연결된 서비스** 폴더 아래에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="a9e6b-139">서비스 모델 메타데이터 유틸리티 도구</span><span class="sxs-lookup"><span data-stu-id="a9e6b-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="a9e6b-140">다음 예제에서는 [서비스모델 메타데이터 유틸리티 도구(Svcutil.exe)를](servicemodel-metadata-utility-tool-svcutil-exe.md) 선택적으로 사용하여 프록시 클래스 파일을 생성하는 방법을 보여 준다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="a9e6b-141">이 도구는 프록시 클래스 파일과 *App.config* 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="a9e6b-142">다음 예제에서는 각각 C# 및 Visual Basic에서 프록시를 생성하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 준다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="a9e6b-143">클라이언트 구성 파일</span><span class="sxs-lookup"><span data-stu-id="a9e6b-143">Client configuration file</span></span>

<span data-ttu-id="a9e6b-144">클라이언트를 만든 후 Visual Studio는 다음 예제와 유사해야 하는 **GettingStartedClient** 프로젝트에서 **App.config** 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="a9e6b-145">system.serviceModel>섹션에서 [ \<끝점>](../configure-apps/file-schema/wcf/endpoint-element.md) 요소를 확인합니다. [ \<](../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="a9e6b-146">**끝점&gt; 요소는 클라이언트가 서비스에 액세스하는 데 사용하는 끝점을 다음과 같이 정의합니다. &lt;**</span><span class="sxs-lookup"><span data-stu-id="a9e6b-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="a9e6b-147">주소: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="a9e6b-148">엔드포인트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-148">The address of the endpoint.</span></span>
- <span data-ttu-id="a9e6b-149">서비스 계약: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="a9e6b-150">서비스 계약은 WCF 클라이언트와 서비스 간의 통신을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="a9e6b-151">Visual Studio는 서비스 참조 **추가** 기능을 사용할 때 이 계약을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="a9e6b-152">기본적으로 GettingStartedLib 프로젝트에서 정의한 계약의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="a9e6b-153">바인딩: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="a9e6b-154">바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 정보로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a9e6b-155">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a9e6b-155">Next steps</span></span>

<span data-ttu-id="a9e6b-156">이 자습서에서는 다음 작업 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a9e6b-157">WCF 클라이언트에 대한 콘솔 앱 프로젝트를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="a9e6b-158">WCF 서비스에 서비스 참조를 추가하여 클라이언트 응용 프로그램에 대한 프록시 클래스 및 구성 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="a9e6b-159">생성된 클라이언트를 사용하는 방법을 알아보려면 다음 자습서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a9e6b-160">자습서: WCF 클라이언트 사용</span><span class="sxs-lookup"><span data-stu-id="a9e6b-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
