---
title: Windows 인증을 사용하는 전송 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 96dd26e2-46e7-4de0-9a29-4fcb05bf187b
ms.openlocfilehash: 6703da4f97cba38ee0dc334d3010ca509d1fb3ef
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598699"
---
# <a name="transport-security-with-windows-authentication"></a><span data-ttu-id="65f4e-102">Windows 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="65f4e-102">Transport Security with Windows Authentication</span></span>
<span data-ttu-id="65f4e-103">다음 시나리오에서는 Windows 보안에 의해 보호 되는 WCF (Windows Communication Foundation) 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by Windows security.</span></span> <span data-ttu-id="65f4e-104">프로그래밍에 대 한 자세한 내용은 [방법: Windows 자격 증명을 사용 하 여 서비스 보호](../how-to-secure-a-service-with-windows-credentials.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65f4e-104">For more information about programming, see [How to: Secure a Service with Windows Credentials](../how-to-secure-a-service-with-windows-credentials.md).</span></span>  
  
 <span data-ttu-id="65f4e-105">인트라넷 웹 서비스는 인사 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-105">An intranet Web service displays human resources information.</span></span> <span data-ttu-id="65f4e-106">클라이언트는 Windows Form 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-106">The client is a Windows Form application.</span></span> <span data-ttu-id="65f4e-107">애플리케이션은 도메인을 보호하는 Kerberos 컨트롤러와 함께 도메인에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-107">The application is deployed in a domain with a Kerberos controller securing the domain.</span></span>  
  
 ![Windows 인증을 사용하는 전송 보안](./media/transport-security-with-windows-authentication/secured-windows-authentication.gif)  
  
|<span data-ttu-id="65f4e-109">특성</span><span class="sxs-lookup"><span data-stu-id="65f4e-109">Characteristic</span></span>|<span data-ttu-id="65f4e-110">Description</span><span class="sxs-lookup"><span data-stu-id="65f4e-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="65f4e-111">보안 모드</span><span class="sxs-lookup"><span data-stu-id="65f4e-111">Security Mode</span></span>|<span data-ttu-id="65f4e-112">전송</span><span class="sxs-lookup"><span data-stu-id="65f4e-112">Transport</span></span>|  
|<span data-ttu-id="65f4e-113">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="65f4e-113">Interoperability</span></span>|<span data-ttu-id="65f4e-114">WCF만</span><span class="sxs-lookup"><span data-stu-id="65f4e-114">WCF only</span></span>|  
|<span data-ttu-id="65f4e-115">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="65f4e-115">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="65f4e-116">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="65f4e-116">Authentication (Client)</span></span>|<span data-ttu-id="65f4e-117">예, Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-117">Yes (using Windows integrated authentication)</span></span><br /><br /> <span data-ttu-id="65f4e-118">예, Windows 통합 인증을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-118">Yes (using Windows integrated authentication)</span></span>|  
|<span data-ttu-id="65f4e-119">무결성</span><span class="sxs-lookup"><span data-stu-id="65f4e-119">Integrity</span></span>|<span data-ttu-id="65f4e-120">예</span><span class="sxs-lookup"><span data-stu-id="65f4e-120">Yes</span></span>|  
|<span data-ttu-id="65f4e-121">기밀성</span><span class="sxs-lookup"><span data-stu-id="65f4e-121">Confidentiality</span></span>|<span data-ttu-id="65f4e-122">예</span><span class="sxs-lookup"><span data-stu-id="65f4e-122">Yes</span></span>|  
|<span data-ttu-id="65f4e-123">전송</span><span class="sxs-lookup"><span data-stu-id="65f4e-123">Transport</span></span>|<span data-ttu-id="65f4e-124">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="65f4e-124">NET.TCP</span></span>|  
|<span data-ttu-id="65f4e-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="65f4e-125">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="65f4e-126">서비스</span><span class="sxs-lookup"><span data-stu-id="65f4e-126">Service</span></span>  
 <span data-ttu-id="65f4e-127">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="65f4e-128">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="65f4e-129">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="65f4e-130">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="65f4e-131">코드</span><span class="sxs-lookup"><span data-stu-id="65f4e-131">Code</span></span>  
 <span data-ttu-id="65f4e-132">다음 코드에서는 Windows 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-132">The following code shows how to create a service endpoint that uses a Windows security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#3)]
 [!code-vb[C_SecurityScenarios#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#3)]  
  
### <a name="configuration"></a><span data-ttu-id="65f4e-133">구성</span><span class="sxs-lookup"><span data-stu-id="65f4e-133">Configuration</span></span>  
 <span data-ttu-id="65f4e-134">다음 구성은 서비스 엔드포인트를 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-134">The following configuration can be used instead of the code to set up the service endpoint:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="65f4e-135">클라이언트</span><span class="sxs-lookup"><span data-stu-id="65f4e-135">Client</span></span>  
 <span data-ttu-id="65f4e-136">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="65f4e-137">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="65f4e-138">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="65f4e-139">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="65f4e-140">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="65f4e-141">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="65f4e-142">코드</span><span class="sxs-lookup"><span data-stu-id="65f4e-142">Code</span></span>  
 <span data-ttu-id="65f4e-143">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-143">The following code creates the client.</span></span> <span data-ttu-id="65f4e-144">바인딩은 TCP 전송과 함께 클라이언트 자격 증명 형식이 Windows로 설정된 전송 모드 보안을 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-144">The binding is configured to use the Transport mode security, with the TCP transport, with the client credential type set to Windows.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#4)]
 [!code-vb[C_SecurityScenarios#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#4)]  
  
### <a name="configuration"></a><span data-ttu-id="65f4e-145">구성</span><span class="sxs-lookup"><span data-stu-id="65f4e-145">Configuration</span></span>  
 <span data-ttu-id="65f4e-146">다음 구성은 클라이언트를 만드는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65f4e-146">The following configuration can be used instead of the code to create the client.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="65f4e-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65f4e-147">See also</span></span>

- [<span data-ttu-id="65f4e-148">보안 개요</span><span class="sxs-lookup"><span data-stu-id="65f4e-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="65f4e-149">방법: Windows 자격 증명을 사용하여 서비스 보호</span><span class="sxs-lookup"><span data-stu-id="65f4e-149">How to: Secure a Service with Windows Credentials</span></span>](../how-to-secure-a-service-with-windows-credentials.md)
- <span data-ttu-id="65f4e-150">[Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="65f4e-150">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
