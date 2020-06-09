---
title: '방법: IIS에서 WCF 서비스 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 326a270c4af38738c910828acd483070ab02ecd1
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593089"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="e716f-102">방법: IIS에서 WCF 서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="e716f-102">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="e716f-103">이 항목에서는 인터넷 정보 서비스 (IIS)에서 호스트 되는 WCF (Windows Communication Foundation) 서비스를 만드는 데 필요한 기본 단계에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-103">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="e716f-104">이 항목에서는 사용자가 IIS에 대해 잘 알고 있으며 IIS 관리 도구를 사용해 IIS 애플리케이션을 만들고 관리하는 방법을 이해하고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-104">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="e716f-105">IIS에 대 한 자세한 내용은 [인터넷 정보 서비스](https://www.iis.net/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-105">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="e716f-106">IIS 환경에서 실행 되는 WCF 서비스는 프로세스 재활용, 유휴 상태 종료, 프로세스 상태 모니터링 및 메시지 기반 활성화와 같은 IIS 기능을 최대한 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-106">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="e716f-107">이 호스팅 옵션을 사용하려면 IIS를 적절히 구성해야 하지만 호스팅 코드를 애플리케이션의 일부로 작성하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-107">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="e716f-108">HTTP 전송을 사용하는 경우에만 IIS 호스팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-108">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="e716f-109">WCF 및 ASP.NET가 상호 작용 하는 방법에 대 한 자세한 내용은 [Wcf 서비스 및 ASP.NET](wcf-services-and-aspnet.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-109">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="e716f-110">보안 구성에 대 한 자세한 내용은 [보안](security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-110">For more information about configuring security, see [Security](security.md).</span></span>  
  
 <span data-ttu-id="e716f-111">이 예제의 소스 복사에 대해서는 [인라인 코드를 사용 하는 IIS 호스팅](../samples/iis-hosting-using-inline-code.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-111">For the source copy of this example, see [IIS Hosting Using Inline Code](../samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="e716f-112">IIS에 의해 호스팅되는 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e716f-112">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="e716f-113">IIS가 컴퓨터에 설치되어 실행되고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-113">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="e716f-114">IIS를 설치 하 고 구성 하는 방법에 대 한 자세한 내용은 [iis 7.0 설치 및 구성을](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-114">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="e716f-115">"IISHostedCalcService" 라는 응용 프로그램 파일에 대 한 새 폴더를 만들고, ASP.NET에 폴더의 콘텐츠에 대 한 액세스 권한이 있는지 확인 하 고, IIS 관리 도구를 사용 하 여이 응용 프로그램 디렉터리에 실제로 있는 새 IIS 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-115">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="e716f-116">애플리케이션 디렉터리의 별칭을 만들 때는 “IISHostedCalc”를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-116">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="e716f-117">애플리케이션 디렉터리에 “service.svc”라는 새 파일을 만든 다음</span><span class="sxs-lookup"><span data-stu-id="e716f-117">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="e716f-118">다음 요소를 추가 하 여이 파일을 편집 @ServiceHost 합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-118">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="e716f-119">애플리케이션 디렉터리 내에 App_Code 하위 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-119">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="e716f-120">App_Code subdirectory에 Service.cs라는 코드 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-120">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="e716f-121">Service.cs 파일의 맨 위에 다음의 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-121">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="e716f-122">using 문 뒤에 다음 네임스페이스 선언을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-122">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="e716f-123">다음 코드와 같이 네임스페이스 선언 내에 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-123">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="e716f-124">다음 코드와 같이 서비스 계약 정의 뒤에서 서비스 계약을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-124">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="e716f-125">애플리케이션 디렉터리에 “Web.config”라는 파일을 만들고 다음 구성 코드를 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-125">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="e716f-126">런타임에 WCF 인프라는이 정보를 사용 하 여 클라이언트 응용 프로그램이 통신할 수 있는 끝점을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-126">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="e716f-127">다음 예제에서는 구성 파일의 엔드포인트를 명시적으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-127">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="e716f-128">서비스에 엔드포인트를 추가하지 않으면 런타임에서 기본 엔드포인트를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="e716f-129">기본 끝점, 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e716f-129">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="e716f-130">서비스가 올바르게 호스팅되는지 확인하려면 Internet Explorer 인스턴스를 열고 서비스 URL인 `http://localhost/IISHostedCalc/Service.svc`로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-130">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="e716f-131">예제</span><span class="sxs-lookup"><span data-stu-id="e716f-131">Example</span></span>  
 <span data-ttu-id="e716f-132">다음은 IIS에서 호스팅되는 계산기 서비스에 해당되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="e716f-132">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="e716f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e716f-133">See also</span></span>

- [<span data-ttu-id="e716f-134">인터넷 정보 서비스에서의 호스팅</span><span class="sxs-lookup"><span data-stu-id="e716f-134">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="e716f-135">서비스 호스팅</span><span class="sxs-lookup"><span data-stu-id="e716f-135">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="e716f-136">WCF 서비스 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e716f-136">WCF Services and ASP.NET</span></span>](wcf-services-and-aspnet.md)
- [<span data-ttu-id="e716f-137">보안</span><span class="sxs-lookup"><span data-stu-id="e716f-137">Security</span></span>](security.md)
- <span data-ttu-id="e716f-138">[Windows Server App Fabric 호스팅 기능](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="e716f-138">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
