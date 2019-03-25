---
title: '자습서: 기본 Windows Communication Foundation 서비스 호스트 및 실행'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 38fd9b89e2719be8ce4d33b1b50f68171d587369
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410097"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="9a3be-102">자습서: 기본 Windows Communication Foundation 서비스 호스트 및 실행</span><span class="sxs-lookup"><span data-stu-id="9a3be-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="9a3be-103">이 자습서는 기본적인 Windows Communication Foundation (WCF) 응용 프로그램을 만드는 데 필요한 다섯 가지 작업 중 세 번째 작업을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9a3be-104">자습서 개요를 참조 하세요. [자습서: Windows Communication Foundation 응용 프로그램 시작](getting-started-tutorial.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="9a3be-105">WCF 응용 프로그램을 만드는 다음 작업 콘솔 응용 프로그램에서 WCF 서비스를 호스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="9a3be-106">WCF 서비스를 하나 이상 노출 *끝점*, 각각 하나 이상의 서비스 작업을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="9a3be-107">서비스 끝점에는 다음 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="9a3be-108">서비스를 찾을 수 있는 위치는 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-108">An address where you can find the service.</span></span>
- <span data-ttu-id="9a3be-109">클라이언트가 서비스와 통신 해야 하는 방법을 설명 하는 정보를 포함 하는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="9a3be-110">서비스를 클라이언트에 게 제공 하는 기능을 정의 하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="9a3be-111">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9a3be-112">만들고 WCF 서비스 호스팅에 대 한 콘솔 앱 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="9a3be-113">WCF 서비스를 호스트 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="9a3be-114">구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-114">Update the configuration file.</span></span>
> - <span data-ttu-id="9a3be-115">WCF 서비스를 시작 하 고 확인 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-115">Start the WCF service and verify it's running.</span></span>


## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="9a3be-116">서비스를 호스트 하는 것에 대 한 콘솔 앱 프로젝트 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="9a3be-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="9a3be-117">Visual Studio에서 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="9a3be-118">**파일** 메뉴에서 **열기** > **프로젝트/솔루션** 로 이동한 합니다 **GettingStarted** 솔루션 있습니다 이전에 만든 (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="9a3be-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="9a3be-119">**열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-119">Select **Open**.</span></span>

    2. <span data-ttu-id="9a3be-120">**뷰** 메뉴에서 **솔루션 탐색기**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="9a3be-121">에 **솔루션 탐색기** 창에서 선택 합니다 **GettingStarted** 솔루션 (최상위 노드)를 선택한 후 **추가** > **새 프로젝트** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9a3be-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="9a3be-122">에 **새 프로젝트 추가** 창의 왼쪽된에 있는 선택 합니다 **Windows Desktop** 에서 범주 **Visual C#**  또는 **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="9a3be-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="9a3be-123">선택 합니다 **콘솔 앱 (.NET Framework)** 템플릿을 enter *GettingStartedHost* 에 대 한 합니다 **이름**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="9a3be-124">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-124">Select **OK**.</span></span>

2. <span data-ttu-id="9a3be-125">참조를 추가 합니다 **GettingStartedHost** 프로젝트가 합니다 **GettingStartedLib** 프로젝트:</span><span class="sxs-lookup"><span data-stu-id="9a3be-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="9a3be-126">에 **솔루션 탐색기** 창에서를 **참조** 아래에 폴더를 **GettingStartedHost** 프로젝트를 선택한 후 **참조추가** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9a3be-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="9a3be-127">에 **참조 추가** 대화 상자 아래에 있는 **프로젝트** 창의 왼쪽에서 선택 **솔루션**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="9a3be-128">선택 **GettingStartedLib** 창과 선택의 가운데 섹션에서 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="9a3be-129">이렇게에 정의 된 형식을 합니다 **GettingStartedLib** 프로젝트를 사용할 수는 **GettingStartedHost** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="9a3be-130">참조를 추가 합니다 **GettingStartedHost** 프로젝트를 <xref:System.ServiceModel> 어셈블리:</span><span class="sxs-lookup"><span data-stu-id="9a3be-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="9a3be-131">에 **솔루션 탐색기** 창에서를 **참조** 아래에 폴더를 **GettingStartedHost** 프로젝트를 선택한 후 **참조추가** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9a3be-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="9a3be-132">에 **참조 추가** 창 아래에 있는 **어셈블리** 창의 왼쪽에서 선택 **Framework**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="9a3be-133">선택 **System.ServiceModel**를 선택한 후 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="9a3be-134">선택 하 여 솔루션을 저장할 **파일** > **모두 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="9a3be-135">서비스를 호스트 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-135">Add code to host the service</span></span>

<span data-ttu-id="9a3be-136">서비스를 호스트 하려면 다음 단계를 수행 하는 코드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="9a3be-137">기본 주소에 대 한 URI를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="9a3be-138">서비스를 호스팅하기 위한 클래스 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="9a3be-139">서비스 끝점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="9a3be-140">메타데이터 교환을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="9a3be-141">들어오는 메시지를 수신 대기 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="9a3be-142">코드를 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="9a3be-143">열기는 **Program.cs** 또는 **Module1.vb** 파일를 **GettingStartedHost** 프로젝트 및 해당 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```
    
    <span data-ttu-id="9a3be-144">이 코드의 작동 방식에 대 한 자세한 내용은 [프로그램 단계 호스팅 서비스](#service-hosting-program-steps)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>


2. <span data-ttu-id="9a3be-145">프로젝트 속성을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-145">Update the project properties:</span></span>

   1. <span data-ttu-id="9a3be-146">에 **솔루션 탐색기** 창에서 합니다 **GettingStartedHost** 폴더를 선택한 후 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9a3be-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="9a3be-147">에 **GettingStartedHost** 속성 페이지를 선택 합니다 **응용 프로그램** 탭:</span><span class="sxs-lookup"><span data-stu-id="9a3be-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="9a3be-148">에 대 한 C# 프로젝트를 선택 **GettingStartedHost.Program** 에서 합니다 **시작 개체** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="9a3be-149">Visual Basic 프로젝트에 대 한 선택 **Service.Program** 에서 합니다 **시작 개체** 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="9a3be-150">**파일** 메뉴에서 **모두 저장**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-150">From the **File** menu, select **Save All**.</span></span>


## <a name="verify-the-service-is-working"></a><span data-ttu-id="9a3be-151">서비스가 작동 확인</span><span class="sxs-lookup"><span data-stu-id="9a3be-151">Verify the service is working</span></span>

1. <span data-ttu-id="9a3be-152">솔루션을 빌드하고 실행 합니다 **GettingStartedHost** 콘솔 Visual Studio 내부에서 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="9a3be-153">서비스는 관리자 권한으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="9a3be-154">실행 하는 경우 관리자 권한으로 Visual Studio를 열었기 때문 **GettingStartedHost** Visual Studio에서 응용 프로그램이 관리자 권한으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="9a3be-155">대신, 관리자 권한으로 새 명령 프롬프트를 열 수 있습니다 (선택 **자세한** > **관리자 권한으로 실행** 바로 가기 메뉴에서) 실행 하 고 **GettingStartedHost.exe**  그 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="9a3be-156">웹 브라우저를 열고 서비스의 페이지를 이동할 `http://localhost:8000/GettingStarted/CalculatorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="9a3be-157">이와 같은 서비스에는 수신 대기 하는 것에 대 한 컴퓨터에서 HTTP 주소를 등록할 수 있는 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="9a3be-158">관리자 계정에는 이 권한이 있지만, 관리자 이외의 계정에는 HTTP 네임스페이스에 대한 권한을 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="9a3be-159">네임스페이스 예약을 구성하는 방법에 대한 자세한 내용은 [HTTP 및 HTTPS 구성](feature-details/configuring-http-and-https.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9a3be-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 


## <a name="service-hosting-program-steps"></a><span data-ttu-id="9a3be-160">서비스 호스팅 프로그램 단계</span><span class="sxs-lookup"><span data-stu-id="9a3be-160">Service hosting program steps</span></span>

<span data-ttu-id="9a3be-161">서비스를 다음과 같이 설명 하는 호스트에 추가한 코드에 나와 있는 단계:</span><span class="sxs-lookup"><span data-stu-id="9a3be-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="9a3be-162">**1 단계**: 인스턴스를 만듭니다는 `Uri` 서비스의 기본 주소를 저장 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="9a3be-163">기본 주소를 포함 하는 URL은 서비스를 식별 하는 선택적 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="9a3be-164">기본 주소 형식은 다음과 같습니다: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="9a3be-165">계산기 서비스에 대 한 기본 주소는 HTTP 전송, localhost, 포트 8000 및 GettingStarted URI 세그먼트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="9a3be-166">**2 단계**: 인스턴스를 만듭니다는 <xref:System.ServiceModel.ServiceHost> 서비스를 호스트 하는 데 사용할 수 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="9a3be-167">생성자는 두 개의 매개 변수를 사용 합니다: 서비스 계약 및 서비스의 기본 주소를 구현 하는 클래스의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="9a3be-168">**3 단계**: <xref:System.ServiceModel.Description.ServiceEndpoint> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="9a3be-169">서비스 엔드포인트는 주소, 바인딩 및 서비스 계약으로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="9a3be-170"><xref:System.ServiceModel.Description.ServiceEndpoint> 생성자는 서비스 계약 인터페이스 형식, 바인딩 및 주소를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="9a3be-171">서비스 계약은 사용자가 정의한 `ICalculator`이며 서비스 형식에 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="9a3be-172">이 샘플에 대 한 바인딩이 <xref:System.ServiceModel.WSHttpBinding>, 기본 바인딩인 및 WS-따르는 끝점에 연결 하는 \* 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="9a3be-173">WCF 바인딩에 대 한 자세한 내용은 참조 하십시오 [WCF 바인딩 개요](bindings-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="9a3be-174">끝점을 식별 하는 기본 주소에 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="9a3be-175">CalculatorService 끝점에 대 한 정규화 된 주소와 주소를 지정 하는 코드 `http://localhost:8000/GettingStarted/CalculatorService`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9a3be-176">.NET Framework 버전 4 이상에서는 서비스 끝점 추가 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="9a3be-177">이러한 버전에 대 한 프로그램 코드 또는 구성을 추가 하지 않으면 WCF는 기본 주소와 서비스에서 구현 되는 계약의 각 조합에 대해 기본 끝점을 하나씩 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="9a3be-178">기본 끝점에 대 한 자세한 내용은 참조 하세요. [끝점 주소 지정](specifying-an-endpoint-address.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="9a3be-179">기본 끝점, 바인딩 및 동작에 대 한 자세한 내용은 참조 하세요. [간소화 된 구성](simplified-configuration.md) 하 고 [WCF 서비스에 대 한 간소화 된 구성](samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="9a3be-180">**4 단계**: 메타데이터 교환을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="9a3be-181">클라이언트는 메타 데이터 교환 서비스 작업 호출에 대 한 프록시를 생성 하려면 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="9a3be-182">메타 데이터를 교환할 수 있도록, 만들기를 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 인스턴스를 설정 해당 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> 속성을 `true`, 추가 `ServiceMetadataBehavior` 개체를 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 의 컬렉션은 <xref:System.ServiceModel.ServiceHost> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9a3be-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="9a3be-183">**5 단계**: 열기 <xref:System.ServiceModel.ServiceHost> 들어오는 메시지를 수신 대기 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="9a3be-184">응용 프로그램 키를 눌러 기다립니다 **Enter**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="9a3be-185">응용 프로그램을 인스턴스화한 후 <xref:System.ServiceModel.ServiceHost>, try/catch 블록을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="9a3be-186">안전 하 게에서 throw 된 예외를 catch 하는 방법에 대 한 자세한 내용은 <xref:System.ServiceModel.ServiceHost>를 참조 하세요 [사용 하 여 닫기 및 중단 WCF 클라이언트 리소스를 해제 하려면](samples/use-close-abort-release-wcf-client-resources.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a3be-187">WCF 서비스 라이브러리에 추가 하면 서비스 호스트를 시작 하 여 디버깅 하는 경우 Visual Studio를 해당을 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="9a3be-188">충돌을 방지 하려면 호스팅 WCF 서비스 라이브러리에서 Visual Studio를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="9a3be-189">선택 된 **GettingStartedLib** 프로젝트 **솔루션 탐색기** 선택한 **속성** 바로 가기 메뉴에서.</span><span class="sxs-lookup"><span data-stu-id="9a3be-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="9a3be-190">선택 **WCF 옵션** 의 선택을 취소 **WCF 서비스 호스트 시작 동일한 솔루션의 다른 프로젝트를 디버깅할 때**합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>


## <a name="next-steps"></a><span data-ttu-id="9a3be-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9a3be-191">Next steps</span></span>

<span data-ttu-id="9a3be-192">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="9a3be-193">만들고 WCF 서비스 호스팅에 대 한 콘솔 앱 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="9a3be-194">WCF 서비스를 호스트 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="9a3be-195">구성 파일을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-195">Update the configuration file.</span></span>
> - <span data-ttu-id="9a3be-196">WCF 서비스를 시작 하 고 확인 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="9a3be-197">WCF 클라이언트를 만드는 방법에 알아보려면 다음 자습서로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a3be-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9a3be-198">자습서: WCF 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="9a3be-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
