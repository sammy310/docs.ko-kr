---
title: Windows 인증을 사용하는 전송 보안
description: Windows 보안으로 보호 되는 WCF 클라이언트/서비스를 보여 주는이 시나리오를 검토 합니다. 이 예제에서 인트라넷 서비스는 인적 자원 정보를 표시 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: b6134d4cbdff0c1adea704a7f3aaff7e40fd75ec
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244766"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="879af-104">Windows 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="879af-104">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="879af-105">다음 시나리오에서는 Windows 보안에 의해 보호 되는 WCF (Windows Communication Foundation) 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="879af-105">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="879af-106">프로그래밍에 대 한 자세한 내용은 [방법: Windows 자격 증명을 사용 하 여 서비스 보호](../how-to-secure-a-service-with-windows-credentials.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="879af-106">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="879af-107">인트라넷 웹 서비스는 인사 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-107">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="879af-108">클라이언트는 Windows Form 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="879af-108">The client is a Windows Form application.</span></span> <span data-ttu-id="879af-109">애플리케이션은 도메인을 보호하는 Kerberos 컨트롤러와 함께 도메인에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="879af-109">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Windows 인증을 사용하는 전송 보안](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="879af-111">특성</span><span class="sxs-lookup"><span data-stu-id="879af-111">Characteristic</span></span>|<span data-ttu-id="879af-112">Description</span><span class="sxs-lookup"><span data-stu-id="879af-112">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="879af-113">보안 모드</span><span class="sxs-lookup"><span data-stu-id="879af-113">Security Mode</span></span>|<span data-ttu-id="879af-114">전송</span><span class="sxs-lookup"><span data-stu-id="879af-114">Transport</span></span>|  
|<span data-ttu-id="879af-115">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="879af-115">Interoperability</span></span>|<span data-ttu-id="879af-116">WCF만</span><span class="sxs-lookup"><span data-stu-id="879af-116">WCF only</span></span>|  
|<span data-ttu-id="879af-117">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="879af-117">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="879af-118">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="879af-118">Authentication (Client)</span></span>|<span data-ttu-id="879af-119">예, Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-119">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="879af-120">예, Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-120">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="879af-121">무결성</span><span class="sxs-lookup"><span data-stu-id="879af-121">Integrity</span></span>|<span data-ttu-id="879af-122">Yes</span><span class="sxs-lookup"><span data-stu-id="879af-122">Yes</span></span>|  
|<span data-ttu-id="879af-123">기밀성</span><span class="sxs-lookup"><span data-stu-id="879af-123">Confidentiality</span></span>|<span data-ttu-id="879af-124">Yes</span><span class="sxs-lookup"><span data-stu-id="879af-124">Yes</span></span>|  
|<span data-ttu-id="879af-125">전송</span><span class="sxs-lookup"><span data-stu-id="879af-125">Transport</span></span>|<span data-ttu-id="879af-126">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="879af-126">NET.TCP</span></span>|  
|<span data-ttu-id="879af-127">바인딩</span><span class="sxs-lookup"><span data-stu-id="879af-127">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="879af-128">서비스</span><span class="sxs-lookup"><span data-stu-id="879af-128">Service</span></span>  
 <span data-ttu-id="879af-129">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="879af-130">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-130">Do one of the following:</span></span>  
  
- <span data-ttu-id="879af-131">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="879af-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="879af-132">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="879af-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="879af-133">코드</span><span class="sxs-lookup"><span data-stu-id="879af-133">Code</span></span>  
 <span data-ttu-id="879af-134">다음 코드에서는 Windows 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="879af-134">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="879af-135">Configuration</span><span class="sxs-lookup"><span data-stu-id="879af-135">Configuration</span></span>  
 <span data-ttu-id="879af-136">다음 구성은 서비스 엔드포인트를 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="879af-136">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
          bindingConfiguration="WindowsClientOverTcp"
                  name="WindowsClientOverTcp"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="WindowsClientOverTcp">  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="879af-137">Client</span><span class="sxs-lookup"><span data-stu-id="879af-137">Client</span></span>  
 <span data-ttu-id="879af-138">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="879af-139">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-139">Do one of the following:</span></span>  
  
- <span data-ttu-id="879af-140">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="879af-140">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="879af-141">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="879af-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="879af-142">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="879af-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="879af-143">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="879af-143">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="879af-144">코드</span><span class="sxs-lookup"><span data-stu-id="879af-144">Code</span></span>  
 <span data-ttu-id="879af-145">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="879af-145">The following code creates the client.</span></span> <span data-ttu-id="879af-146">바인딩은 TCP 전송과 함께 클라이언트 자격 증명 형식이 Windows로 설정된 전송 모드 보안을 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="879af-146">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="879af-147">Configuration</span><span class="sxs-lookup"><span data-stu-id="879af-147">Configuration</span></span>  
 <span data-ttu-id="879af-148">다음 구성은 클라이언트를 만드는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="879af-148">The following configuration can be used instead of the code to create the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://localhost:8008/Calculator"
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="879af-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="879af-149">See also</span></span>

- [<span data-ttu-id="879af-150">보안 개요</span><span class="sxs-lookup"><span data-stu-id="879af-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="879af-151">방법: Windows 자격 증명을 사용하여 서비스 보호</span><span class="sxs-lookup"><span data-stu-id="879af-151">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="879af-152">[Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="879af-152">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
