---
title: '방법: 관리형 애플리케이션에서 WCF 서비스 호스트'
description: 자체 호스팅 서비스를 만들고 테스트 하 여 관리 되는 응용 프로그램 내에서 WCF 서비스를 호스트 하는 방법에 대해 알아봅니다.
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 7d1d61b683f60a6c643d2a2f03d367a6ae6c6c15
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246170"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="fd89f-103">방법: 관리 되는 응용 프로그램에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="fd89f-103">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="fd89f-104">관리되는 애플리케이션 내에서 서비스를 호스팅하려면 관리되는 애플리케이션 코드 내에 서비스에 대한 코드를 포함하고, 코드에서 명령적으로, 구성을 통해 선언적으로 또는 기본 엔드포인트를 사용해 서비스에 대한 엔드포인트를 정의한 다음 <xref:System.ServiceModel.ServiceHost>의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-104">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="fd89f-105">메시지 받기를 시작하려면 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-105">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="fd89f-106">이렇게 하면 서비스에 대한 수신기가 만들어지고 열립니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-106">This creates and opens the listener for the service.</span></span> <span data-ttu-id="fd89f-107">관리되는 애플리케이션이 호스팅 작업을 직접 수행하므로 이런 방식으로 서비스를 호스팅하는 것을 &quot;자체 호스팅&quot;이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-107">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="fd89f-108">서비스를 닫으려면 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType>에서 <xref:System.ServiceModel.ServiceHost>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-108">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="fd89f-109">서비스는 관리되는 Windows 서비스, IIS(인터넷 정보 서비스) 또는 WAS(Windows Process Activation Service)에서 호스팅될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-109">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="fd89f-110">서비스의 호스팅 옵션에 대 한 자세한 내용은 [호스팅 서비스](hosting-services.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd89f-110">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="fd89f-111">관리되는 애플리케이션에서 서비스를 호스팅할 경우 최소한의 배포 인프라를 필요로 하기 때문에 가장 유연한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-111">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="fd89f-112">관리 되는 응용 프로그램에서 서비스를 호스팅하는 방법에 대 한 자세한 내용은 [관리 되는 응용 프로그램에서 호스팅](./feature-details/hosting-in-a-managed-application.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd89f-112">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="fd89f-113">다음 절차에서는 콘솔 애플리케이션에서 자체 호스팅된 서비스를 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-113">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="fd89f-114">자체 호스팅 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="fd89f-114">Create a self-hosted service</span></span>

1. <span data-ttu-id="fd89f-115">새 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-115">Create a new console application:</span></span>

   1. <span data-ttu-id="fd89f-116">Visual Studio를 열고 **New**  >  **파일** 메뉴에서 새**프로젝트** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-116">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="fd89f-117">**설치 된 템플릿** 목록에서 **Visual c #** 또는 **Visual Basic**을 선택한 다음 **Windows 데스크톱**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-117">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="fd89f-118">**콘솔 앱** 템플릿을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-118">Select the **Console App** template.</span></span> <span data-ttu-id="fd89f-119">`SelfHost` **이름** 상자에를 입력 한 다음 **확인을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-119">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="fd89f-120">**솔루션 탐색기** 에서 **SelfHost** 을 마우스 오른쪽 단추로 클릭 하 고 **참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-120">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="fd89f-121">**.Net** 탭에서 **system.servicemodel** 을 선택 하 고 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-121">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fd89f-122">**솔루션 탐색기** 창이 표시 되지 않으면 **보기** 메뉴에서 **솔루션 탐색기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-122">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="fd89f-123">**솔루션 탐색기** 에서 **Program.cs** 또는 module1.vb를 두 번 클릭 하 여 코드 창에서 엽니다 (아직 열려 있지 않은 경우 **).**</span><span class="sxs-lookup"><span data-stu-id="fd89f-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="fd89f-124">파일의 맨 위에 다음 문을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-124">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="fd89f-125">서비스 계약을 정의 및 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-125">Define and implement a service contract.</span></span> <span data-ttu-id="fd89f-126">이 예제에서는 서비스에 대한 입력을 기준으로 메시지를 반환하는 `HelloWorldService`를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-126">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="fd89f-127">서비스 인터페이스를 정의 하 고 구현 하는 방법에 대 한 자세한 내용은 [방법: 서비스 계약 정의](how-to-define-a-wcf-service-contract.md) 및 [방법: 서비스 계약 구현](how-to-implement-a-wcf-contract.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd89f-127">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="fd89f-128">서비스의 기본 주소를 사용하여 `Main` 메서드 맨 위에 <xref:System.Uri> 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-128">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="fd89f-129"><xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들어 서비스 형식 및 기본 주소 URI(Uniform Resource Identifier)를 나타내는 <xref:System.Type>을 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-129">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="fd89f-130">메타데이터 게시를 사용하도록 설정한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출하여 서비스를 초기화하고 메시지를 받도록 서비스를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-130">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="fd89f-131">이 예제에서는 기본 엔드포인트를 사용하며, 이 서비스에는 구성 파일이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-131">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="fd89f-132">엔드포인트를 구성하지 않으면 런타임이 서비스에서 구현되는 각 서비스 계약의 각 기본 주소에 대해 엔드포인트를 하나씩 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-132">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="fd89f-133">기본 끝점에 대 한 자세한 내용은 [WCF 서비스에 대 한](./samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd89f-133">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="fd89f-134">**Ctrl** + **Shift** + **B** 를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-134">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="fd89f-135">서비스 테스트</span><span class="sxs-lookup"><span data-stu-id="fd89f-135">Test the service</span></span>

1. <span data-ttu-id="fd89f-136">**Ctrl** + **F5** 를 눌러 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-136">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="fd89f-137">**WCF 테스트 클라이언트**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-137">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fd89f-138">**WCF 테스트 클라이언트**를 열려면 Visual Studio에 대 한 개발자 명령 프롬프트를 열고 **WcfTestClient.exe**를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-138">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="fd89f-139">**파일** 메뉴에서 **서비스 추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-139">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="fd89f-140">`http://localhost:8080/hello`주소 상자에를 입력 하 고 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-140">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fd89f-141">서비스가 실행 중인지 확인하십시오. 그렇지 않으면 이 단계는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-141">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="fd89f-142">코드에서 기본 주소를 변경한 경우에는 이 단계에서 수정된 기본 주소를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd89f-142">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="fd89f-143">**내 서비스 프로젝트** 노드 아래에서 **SayHello** 를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-143">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="fd89f-144">**요청** 목록에서 **값** 열에 이름을 입력 하 고 **호출**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-144">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="fd89f-145">**응답** 목록에 회신 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-145">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="fd89f-146">예제</span><span class="sxs-lookup"><span data-stu-id="fd89f-146">Example</span></span>

<span data-ttu-id="fd89f-147">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 개체를 만들어 `HelloWorldService` 형식의 서비스를 호스팅한 다음 <xref:System.ServiceModel.ICommunicationObject.Open%2A>에서 <xref:System.ServiceModel.ServiceHost> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-147">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="fd89f-148">기본 주소는 코드에서 제공되고 메타데이터 게시가 사용하도록 설정되며 기본 엔드포인트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd89f-148">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="fd89f-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd89f-149">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="fd89f-150">방법: IIS에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="fd89f-150">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="fd89f-151">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="fd89f-151">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="fd89f-152">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="fd89f-152">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="fd89f-153">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="fd89f-153">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="fd89f-154">방법: 서비스 계약 구현</span><span class="sxs-lookup"><span data-stu-id="fd89f-154">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="fd89f-155">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="fd89f-155">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="fd89f-156">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="fd89f-156">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="fd89f-157">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="fd89f-157">System-Provided Bindings</span></span>](system-provided-bindings.md)
