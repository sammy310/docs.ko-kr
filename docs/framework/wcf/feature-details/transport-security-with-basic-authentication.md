---
title: 기본 인증을 사용하는 전송 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: 5cbe6ce6e8e36fc9460295c454014d6f3fbf3983
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64635126"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="2a3f2-102">기본 인증을 사용하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="2a3f2-102">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="2a3f2-103">다음 그림에는 Windows Communication Foundation (WCF) 서비스 및 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-103">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="2a3f2-104">서버에 SSL(Secure Sockets Layer)에 사용할 유효한 X.509 인증서가 있어야 하며 클라이언트에서 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-104">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="2a3f2-105">또한 웹 서비스에는 이미 사용할 수 있는 SSL 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-105">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="2a3f2-106">자세한 내용은 기본 인증을 사용 하는 방법에 대 한 인터넷 정보 서비스 (IIS)를 참조 하세요. <https://go.microsoft.com/fwlink/?LinkId=83822>합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-106">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://go.microsoft.com/fwlink/?LinkId=83822>.</span></span>  
  
 ![기본 인증을 사용 하 여 전송 보안을 보여 주는 스크린샷.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="2a3f2-108">특성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-108">Characteristic</span></span>|<span data-ttu-id="2a3f2-109">설명</span><span class="sxs-lookup"><span data-stu-id="2a3f2-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2a3f2-110">보안 모드</span><span class="sxs-lookup"><span data-stu-id="2a3f2-110">Security Mode</span></span>|<span data-ttu-id="2a3f2-111">전송</span><span class="sxs-lookup"><span data-stu-id="2a3f2-111">Transport</span></span>|  
|<span data-ttu-id="2a3f2-112">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-112">Interoperability</span></span>|<span data-ttu-id="2a3f2-113">기존 웹 서비스 클라이언트 및 서비스와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-113">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="2a3f2-114">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="2a3f2-114">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="2a3f2-115">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="2a3f2-115">Authentication (Client)</span></span>|<span data-ttu-id="2a3f2-116">예(HTTPS 사용)</span><span class="sxs-lookup"><span data-stu-id="2a3f2-116">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="2a3f2-117">예(사용자 이름/암호 사용)</span><span class="sxs-lookup"><span data-stu-id="2a3f2-117">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="2a3f2-118">무결성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-118">Integrity</span></span>|<span data-ttu-id="2a3f2-119">예</span><span class="sxs-lookup"><span data-stu-id="2a3f2-119">Yes</span></span>|  
|<span data-ttu-id="2a3f2-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-120">Confidentiality</span></span>|<span data-ttu-id="2a3f2-121">예</span><span class="sxs-lookup"><span data-stu-id="2a3f2-121">Yes</span></span>|  
|<span data-ttu-id="2a3f2-122">전송</span><span class="sxs-lookup"><span data-stu-id="2a3f2-122">Transport</span></span>|<span data-ttu-id="2a3f2-123">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2a3f2-123">HTTPS</span></span>|  
|<span data-ttu-id="2a3f2-124">바인딩</span><span class="sxs-lookup"><span data-stu-id="2a3f2-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="2a3f2-125">서비스</span><span class="sxs-lookup"><span data-stu-id="2a3f2-125">Service</span></span>  
 <span data-ttu-id="2a3f2-126">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2a3f2-127">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-127">Do one of the following:</span></span>  
  
- <span data-ttu-id="2a3f2-128">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="2a3f2-129">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a3f2-130">코드</span><span class="sxs-lookup"><span data-stu-id="2a3f2-130">Code</span></span>  
 <span data-ttu-id="2a3f2-131">다음 코드에서는 전송 보안에 Windows 도메인 사용자 이름과 암호를 사용하는 서비스 엔드포인트를 만드는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-131">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="2a3f2-132">서비스에서 X.509 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-132">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="2a3f2-133">자세한 내용은 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) 고 [방법: SSL 인증서로 포트 구성](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-133">For more information, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="2a3f2-134">구성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-134">Configuration</span></span>  
 <span data-ttu-id="2a3f2-135">다음에서는 전송 수준 보안이 설정된 기본 인증을 사용하도록 서비스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-135">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="2a3f2-136">클라이언트</span><span class="sxs-lookup"><span data-stu-id="2a3f2-136">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a3f2-137">코드</span><span class="sxs-lookup"><span data-stu-id="2a3f2-137">Code</span></span>  
 <span data-ttu-id="2a3f2-138">다음 코드에서는 사용자 이름 및 암호를 포함한 클라이언트 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-138">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="2a3f2-139">사용자는 유효한 Windows 사용자 이름과 암호를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-139">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="2a3f2-140">사용자 이름과 암호를 반환하는 코드는 여기에 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-140">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="2a3f2-141">대화 상자나 다른 인터페이스를 사용하여 사용자에게 정보를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-141">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a3f2-142">사용자 이름 및 암호는 코드를 사용해야만 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-142">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="2a3f2-143">구성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-143">Configuration</span></span>  
 <span data-ttu-id="2a3f2-144">다음 코드에서는 클라이언트 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-144">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a3f2-145">구성을 사용하여 사용자 이름 및 암호를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-145">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="2a3f2-146">여기 표시된 구성은 사용자 이름 및 암호를 설정하는 코드를 사용하여 확장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3f2-146">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a3f2-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="2a3f2-147">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="2a3f2-148">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="2a3f2-148">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="2a3f2-149">방법: SSL 인증서로 포트 구성</span><span class="sxs-lookup"><span data-stu-id="2a3f2-149">How to: Configure a Port with an SSL Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="2a3f2-150">보안 개요</span><span class="sxs-lookup"><span data-stu-id="2a3f2-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="2a3f2-151">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="2a3f2-151">\<clientCredentials></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
- [<span data-ttu-id="2a3f2-152">Windows Server appfabric 보안 모델</span><span class="sxs-lookup"><span data-stu-id="2a3f2-152">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
