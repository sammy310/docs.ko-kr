---
title: '방법: 관리되는 애플리케이션에서 WCF 서비스 호스팅'
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: e3adcad6ba70aa64b797325cd45a043301d7e680
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320973"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="f67a8-102">방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f67a8-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="f67a8-103">관리되는 애플리케이션 내에서 서비스를 호스팅하려면 관리되는 애플리케이션 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 엔드포인트를 사용해 서비스에 대한 엔드포인트를 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="f67a8-104">메시지 받기를 시작하려면 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f67a8-105">이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="f67a8-106">관리되는 애플리케이션이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 &quot;자체 호스팅&quot;이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="f67a8-107">서비스를 닫으려면 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="f67a8-108">서비스는 관리되는 Windows 서비스, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 호스팅될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="f67a8-109">서비스의 호스팅 옵션에 대 한 자세한 내용은 [호스팅 서비스](hosting-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a8-109">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="f67a8-110">관리되는 애플리케이션에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="f67a8-111">관리 되는 응용 프로그램에서 서비스를 호스팅하는 방법에 대 한 자세한 내용은 [관리 되는 응용 프로그램에서 호스팅](./feature-details/hosting-in-a-managed-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a8-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="f67a8-112">다음 절차에서는 콘솔 애플리케이션에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="f67a8-113">자체 호스팅 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="f67a8-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="f67a8-114">새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-114">Create a new console application:</span></span>

   1. <span data-ttu-id="f67a8-115">Visual Studio를 열고 **파일** 메뉴에서 **새로 만들기**  > **프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="f67a8-116">**설치 된 템플릿** 목록에서  **C# 시각적 개체** 또는 **Visual Basic**을 선택한 다음 **Windows 데스크톱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="f67a8-117">**콘솔 앱** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-117">Select the **Console App** template.</span></span> <span data-ttu-id="f67a8-118">**이름** 상자에 `SelfHost`를 입력 한 다음 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="f67a8-119">**솔루션 탐색기** 에서 **SelfHost** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="f67a8-120">**.Net** 탭에서 **system.servicemodel** 을 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f67a8-121">**솔루션 탐색기** 창이 표시 되지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="f67a8-122">**솔루션 탐색기** 에서 **Program.cs** 또는 module1.vb를 두 번 클릭 하 여 코드 창에서 엽니다 (아직 열려 있지 않은 경우 **).**</span><span class="sxs-lookup"><span data-stu-id="f67a8-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="f67a8-123">파일의 맨 위에 다음 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="f67a8-124">서비스 계약을 정의 및 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-124">Define and implement a service contract.</span></span> <span data-ttu-id="f67a8-125">이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="f67a8-126">서비스 인터페이스를 정의 하 고 구현 하는 방법에 대 한 자세한 내용은 [방법: 서비스 계약 정의](how-to-define-a-wcf-service-contract.md) 및 [방법: 서비스 계약 구현](how-to-implement-a-wcf-contract.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a8-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="f67a8-127">서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="f67a8-128"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI(Uniform Resource Identifier)를 나타내는 <xref:System.Type>을 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="f67a8-129">메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="f67a8-130">이 예제에서는 기본 엔드포인트를 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="f67a8-131">엔드포인트를 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 엔드포인트를 하나씩 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="f67a8-132">기본 끝점에 대 한 자세한 내용은 [WCF 서비스에 대 한](./samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f67a8-132">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="f67a8-133">**Ctrl** +**shift** +**B** 를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="f67a8-134">서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="f67a8-134">Test the service</span></span>

1. <span data-ttu-id="f67a8-135">**Ctrl** +**f5** 키를 눌러 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="f67a8-136">**WCF 테스트 클라이언트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f67a8-137">**WCF 테스트 클라이언트**를 열려면 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 **wcftestclient.exe**를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="f67a8-138">**파일** 메뉴에서 **서비스 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="f67a8-139">주소 상자에 `http://localhost:8080/hello`을 입력 하 고 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f67a8-140">서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="f67a8-141">코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="f67a8-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="f67a8-142">**내 서비스 프로젝트** 노드 아래에서 **SayHello** 를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="f67a8-143">**요청** 목록에서 **값** 열에 이름을 입력 하 고 **호출**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="f67a8-144">**응답** 목록에 회신 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="f67a8-145">예제</span><span class="sxs-lookup"><span data-stu-id="f67a8-145">Example</span></span>

<span data-ttu-id="f67a8-146">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="f67a8-147">기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 엔드포인트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f67a8-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="f67a8-148">참조</span><span class="sxs-lookup"><span data-stu-id="f67a8-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="f67a8-149">방법: IIS에서 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="f67a8-149">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="f67a8-150">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="f67a8-150">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="f67a8-151">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="f67a8-151">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="f67a8-152">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="f67a8-152">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="f67a8-153">방법: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="f67a8-153">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="f67a8-154">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="f67a8-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="f67a8-155">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="f67a8-155">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f67a8-156">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="f67a8-156">System-Provided Bindings</span></span>](system-provided-bindings.md)
