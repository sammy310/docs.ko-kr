---
title: 기본 인증을 사용하는 전송 보안
description: WCF 서비스 및 클라이언트에 대 한 기본 인증을 보여 주는이 WCF 시나리오를 검토 합니다. 서비스에는 클라이언트에서 신뢰 하는 유효한 인증서가 필요 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: 2add8c21ca8ade4b530e0e6b1b3c5bba66e100ab
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556787"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="ee5a8-104">기본 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="ee5a8-104">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="ee5a8-105">다음 그림은 WCF (Windows Communication Foundation) 서비스 및 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-105">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="ee5a8-106">서버에 SSL(Secure Sockets Layer)에 사용할 유효한 X.509 인증서가 있어야 하며 클라이언트에서 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-106">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="ee5a8-107">또한 웹 서비스에는 이미 사용할 수 있는 SSL 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-107">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="ee5a8-108">인터넷 정보 서비스 (IIS)에서 기본 인증을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은을 참조 하십시오 <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication> .</span><span class="sxs-lookup"><span data-stu-id="ee5a8-108">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![기본 인증을 사용 하는 전송 보안을 보여 주는 스크린샷](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="ee5a8-110">특성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-110">Characteristic</span></span>|<span data-ttu-id="ee5a8-111">Description</span><span class="sxs-lookup"><span data-stu-id="ee5a8-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ee5a8-112">보안 모드</span><span class="sxs-lookup"><span data-stu-id="ee5a8-112">Security Mode</span></span>|<span data-ttu-id="ee5a8-113">전송</span><span class="sxs-lookup"><span data-stu-id="ee5a8-113">Transport</span></span>|  
|<span data-ttu-id="ee5a8-114">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-114">Interoperability</span></span>|<span data-ttu-id="ee5a8-115">기존 웹 서비스 클라이언트 및 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="ee5a8-116">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="ee5a8-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="ee5a8-117">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="ee5a8-117">Authentication (Client)</span></span>|<span data-ttu-id="ee5a8-118">예(HTTPS 사용)</span><span class="sxs-lookup"><span data-stu-id="ee5a8-118">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="ee5a8-119">예(사용자 이름/암호 사용)</span><span class="sxs-lookup"><span data-stu-id="ee5a8-119">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="ee5a8-120">무결성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-120">Integrity</span></span>|<span data-ttu-id="ee5a8-121">예</span><span class="sxs-lookup"><span data-stu-id="ee5a8-121">Yes</span></span>|  
|<span data-ttu-id="ee5a8-122">기밀성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-122">Confidentiality</span></span>|<span data-ttu-id="ee5a8-123">예</span><span class="sxs-lookup"><span data-stu-id="ee5a8-123">Yes</span></span>|  
|<span data-ttu-id="ee5a8-124">전송</span><span class="sxs-lookup"><span data-stu-id="ee5a8-124">Transport</span></span>|<span data-ttu-id="ee5a8-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ee5a8-125">HTTPS</span></span>|  
|<span data-ttu-id="ee5a8-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="ee5a8-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="ee5a8-127">서비스</span><span class="sxs-lookup"><span data-stu-id="ee5a8-127">Service</span></span>  
 <span data-ttu-id="ee5a8-128">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="ee5a8-129">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-129">Do one of the following:</span></span>  
  
- <span data-ttu-id="ee5a8-130">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-130">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="ee5a8-131">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ee5a8-132">코드</span><span class="sxs-lookup"><span data-stu-id="ee5a8-132">Code</span></span>  
 <span data-ttu-id="ee5a8-133">다음 코드에서는 전송 보안에 Windows 도메인 사용자 이름과 암호를 사용하는 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-133">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="ee5a8-134">서비스에서 X.509 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-134">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="ee5a8-135">자세한 내용은 [인증서 작업](working-with-certificates.md) 및 [방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-135">For more information, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="ee5a8-136">구성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-136">Configuration</span></span>  
 <span data-ttu-id="ee5a8-137">다음에서는 전송 수준 보안이 설정된 기본 인증을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-137">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="ee5a8-138">클라이언트</span><span class="sxs-lookup"><span data-stu-id="ee5a8-138">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="ee5a8-139">코드</span><span class="sxs-lookup"><span data-stu-id="ee5a8-139">Code</span></span>  
 <span data-ttu-id="ee5a8-140">다음 코드에서는 사용자 이름 및 암호를 포함한 클라이언트 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-140">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="ee5a8-141">사용자는 유효한 Windows 사용자 이름과 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-141">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="ee5a8-142">사용자 이름과 암호를 반환하는 코드는 여기에 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-142">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="ee5a8-143">대화 상자나 다른 인터페이스를 사용하여 사용자에게 정보를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-143">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee5a8-144">사용자 이름 및 암호는 코드를 사용해야만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-144">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="ee5a8-145">구성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-145">Configuration</span></span>  
 <span data-ttu-id="ee5a8-146">다음 코드에서는 클라이언트 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-146">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee5a8-147">구성을 사용하여 사용자 이름 및 암호를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-147">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="ee5a8-148">여기 표시된 구성은 사용자 이름 및 암호를 설정하는 코드를 사용하여 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee5a8-148">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee5a8-149">참조</span><span class="sxs-lookup"><span data-stu-id="ee5a8-149">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="ee5a8-150">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="ee5a8-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="ee5a8-151">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="ee5a8-151">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="ee5a8-152">보안 개요</span><span class="sxs-lookup"><span data-stu-id="ee5a8-152">Security Overview</span></span>](security-overview.md)
- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="ee5a8-153">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="ee5a8-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
