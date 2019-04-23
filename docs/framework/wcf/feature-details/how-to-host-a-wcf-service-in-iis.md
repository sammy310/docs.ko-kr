---
title: '방법: IIS에서 WCF 서비스 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: f106ce1bca67f8b88df0835496eea0b3297ac946
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59309682"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="a92a0-102">방법: IIS에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="a92a0-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="a92a0-103">이 항목에서는 인터넷 정보 서비스 (IIS)에서 호스트 되는 Windows Communication Foundation (WCF) 서비스를 만드는 데 필요한 기본 단계를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="a92a0-104">이 항목에서는 사용자가 IIS에 대해 잘 알고 있으며 IIS 관리 도구를 사용해 IIS 응용 프로그램을 만들고 관리하는 방법을 이해하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="a92a0-105">IIS에 대 한 자세한 내용은 참조 하세요. [인터넷 정보 서비스](https://go.microsoft.com/fwlink/?LinkId=132449)합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-105">For more information about IIS see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=132449).</span></span> <span data-ttu-id="a92a0-106">IIS 환경에서 실행 되는 프로세스 재활용와 같은 IIS 기능을 최대한 활용 하는 WCF 서비스 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화를 유휴입니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="a92a0-107">이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 애플리케이션의 일부로 작성하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="a92a0-108">HTTP 전송을 사용하는 경우에만 IIS 호스팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="a92a0-109">방법에 대 한 자세한 내용은 WCF 및 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 상호 작용을 참조 하십시오 [WCF 서비스 및 ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-109">For more information about how WCF and [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] interact, see [WCF Services and ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="a92a0-110">보안 구성에 대 한 자세한 내용은 참조 하세요. [보안](../../../../docs/framework/wcf/feature-details/security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-110">For more information about configuring security, see [Security](../../../../docs/framework/wcf/feature-details/security.md).</span></span>  
  
 <span data-ttu-id="a92a0-111">이 예제의 소스 복사에 대해서 [IIS 호스트를 사용 하 여 인라인 코드](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="a92a0-112">IIS에 의해 호스팅되는 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a92a0-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="a92a0-113">IIS가 컴퓨터에 설치되어 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="a92a0-114">IIS 설치 및 구성 하는 방법에 대 한 자세한 내용은 참조 하세요. [Installing and Configuring IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span><span class="sxs-lookup"><span data-stu-id="a92a0-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=132128)</span></span>  
  
2. <span data-ttu-id="a92a0-115">응용 프로그램 파일의 새 폴더("IISHostedCalcService")를 만들고, [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]이 폴더 내용에 대한 액세스 권한을 가지고 있는지 확인하고, IIS 관리 도구를 사용하여 실제로 이 응용 프로그램 디렉터리에 있는 새 IIS 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-115">Create a new folder for your application files called "IISHostedCalcService", ensure that [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="a92a0-116">응용 프로그램 디렉터리의 별칭을 만들 때는 “IISHostedCalc”를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="a92a0-117">응용 프로그램 디렉터리에 “service.svc”라는 새 파일을 만든 다음</span><span class="sxs-lookup"><span data-stu-id="a92a0-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="a92a0-118">다음을 추가 하 여이 파일을 편집 @ServiceHost 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
    ```  
    <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>  
    ```  
  
4. <span data-ttu-id="a92a0-119">응용 프로그램 디렉터리 내에 App_Code 하위 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="a92a0-120">App_Code subdirectory에 Service.cs라는 코드 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="a92a0-121">Service.cs 파일의 맨 위에 다음의 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="a92a0-122">using 문 뒤에 다음 네임스페이스 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="a92a0-123">다음 코드와 같이 네임스페이스 선언 내에 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="a92a0-124">다음 코드와 같이 서비스 계약 정의 뒤에서 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="a92a0-125">응용 프로그램 디렉터리에 “Web.config”라는 파일을 만들고 다음 구성 코드를 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="a92a0-126">런타임에 WCF 인프라는 클라이언트 응용 프로그램이 통신할 수 있는 끝점을 생성 하는 정보를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]      
  
     <span data-ttu-id="a92a0-127">다음 예제에서는 구성 파일의 엔드포인트를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="a92a0-128">서비스에 엔드포인트를 추가하지 않으면 런타임에서 기본 엔드포인트를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="a92a0-129">기본 끝점, 바인딩 및 동작 참조 하는 방법에 대 한 자세한 내용은 [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) 하 고 [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="a92a0-130">서비스가 올바르게 호스팅되는지 확인하려면 Internet Explorer 인스턴스를 열고 서비스 URL인 `http://localhost/IISHostedCalc/Service.svc`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="a92a0-131">예제</span><span class="sxs-lookup"><span data-stu-id="a92a0-131">Example</span></span>  
 <span data-ttu-id="a92a0-132">다음은 IIS에서 호스팅되는 계산기 서비스에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a92a0-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)] 
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)] 
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="a92a0-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="a92a0-133">See also</span></span>

- [<span data-ttu-id="a92a0-134">인터넷 정보 서비스에서 호스팅</span><span class="sxs-lookup"><span data-stu-id="a92a0-134">Hosting in Internet Information Services</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [<span data-ttu-id="a92a0-135">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="a92a0-135">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="a92a0-136">WCF 서비스 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a92a0-136">WCF Services and ASP.NET</span></span>](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [<span data-ttu-id="a92a0-137">보안</span><span class="sxs-lookup"><span data-stu-id="a92a0-137">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
- [<span data-ttu-id="a92a0-138">Windows Server App Fabric 호스팅 기능</span><span class="sxs-lookup"><span data-stu-id="a92a0-138">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
