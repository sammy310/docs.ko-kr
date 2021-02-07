---
description: '자세한 정보: 인증서 클라이언트를 사용 하는 메시지 보안'
title: 인증서 클라이언트를 사용하는 메시지 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: f1924510c5860b377568da204bbd9154e4970c24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99727066"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="9291c-103">인증서 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="9291c-103">Message Security with a Certificate Client</span></span>

<span data-ttu-id="9291c-104">다음 시나리오에서는 메시지 보안 모드를 사용 하 여 보호 되는 WCF (Windows Communication Foundation) 클라이언트 및 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-104">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="9291c-105">클라이언트 및 서비스는 인증서를 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-105">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="9291c-106">자세한 내용은 [배포 응용 프로그램 보안](distributed-application-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9291c-106">For more information, see [Distributed Application Security](distributed-application-security.md).</span></span>

 ![인증서가 있는 클라이언트를 보여 주는 스크린샷](./media/message-security-with-a-certificate-client/client-with-certificate.gif)  
  
 <span data-ttu-id="9291c-108">응용 프로그램 예제는 [메시지 보안 인증서](../samples/message-security-certificate.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9291c-108">For a sample application, see [Message Security Certificate](../samples/message-security-certificate.md).</span></span>  

|<span data-ttu-id="9291c-109">특성</span><span class="sxs-lookup"><span data-stu-id="9291c-109">Characteristic</span></span>|<span data-ttu-id="9291c-110">설명</span><span class="sxs-lookup"><span data-stu-id="9291c-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="9291c-111">보안 모드</span><span class="sxs-lookup"><span data-stu-id="9291c-111">Security Mode</span></span>|<span data-ttu-id="9291c-112">메시지</span><span class="sxs-lookup"><span data-stu-id="9291c-112">Message</span></span>|  
|<span data-ttu-id="9291c-113">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="9291c-113">Interoperability</span></span>|<span data-ttu-id="9291c-114">WCF만</span><span class="sxs-lookup"><span data-stu-id="9291c-114">WCF only</span></span>|  
|<span data-ttu-id="9291c-115">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="9291c-115">Authentication (Server)</span></span>|<span data-ttu-id="9291c-116">서비스 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="9291c-116">Using service certificate</span></span>|  
|<span data-ttu-id="9291c-117">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="9291c-117">Authentication (Client)</span></span>|<span data-ttu-id="9291c-118">클라이언트 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="9291c-118">Using client certificate</span></span>|  
|<span data-ttu-id="9291c-119">무결성</span><span class="sxs-lookup"><span data-stu-id="9291c-119">Integrity</span></span>|<span data-ttu-id="9291c-120">예</span><span class="sxs-lookup"><span data-stu-id="9291c-120">Yes</span></span>|  
|<span data-ttu-id="9291c-121">기밀성</span><span class="sxs-lookup"><span data-stu-id="9291c-121">Confidentiality</span></span>|<span data-ttu-id="9291c-122">Yes</span><span class="sxs-lookup"><span data-stu-id="9291c-122">Yes</span></span>|  
|<span data-ttu-id="9291c-123">전송</span><span class="sxs-lookup"><span data-stu-id="9291c-123">Transport</span></span>|<span data-ttu-id="9291c-124">HTTP</span><span class="sxs-lookup"><span data-stu-id="9291c-124">HTTP</span></span>|  
|<span data-ttu-id="9291c-125">바인딩</span><span class="sxs-lookup"><span data-stu-id="9291c-125">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="9291c-126">서비스</span><span class="sxs-lookup"><span data-stu-id="9291c-126">Service</span></span>  

 <span data-ttu-id="9291c-127">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-127">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9291c-128">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-128">Do one of the following:</span></span>  
  
- <span data-ttu-id="9291c-129">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-129">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="9291c-130">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-130">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9291c-131">코드</span><span class="sxs-lookup"><span data-stu-id="9291c-131">Code</span></span>  

 <span data-ttu-id="9291c-132">다음 코드에서는 안전한 컨텍스트를 설정하기 위해 메시지 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-132">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="9291c-133">Configuration</span><span class="sxs-lookup"><span data-stu-id="9291c-133">Configuration</span></span>  

 <span data-ttu-id="9291c-134">코드 대신 다음 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-134">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCertificateClient"
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="9291c-135">클라이언트</span><span class="sxs-lookup"><span data-stu-id="9291c-135">Client</span></span>  

 <span data-ttu-id="9291c-136">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="9291c-137">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-137">Do one of the following:</span></span>  
  
- <span data-ttu-id="9291c-138">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-138">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="9291c-139">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="9291c-140">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="9291c-141">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="9291c-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="9291c-142">코드</span><span class="sxs-lookup"><span data-stu-id="9291c-142">Code</span></span>  

 <span data-ttu-id="9291c-143">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-143">The following code creates the client.</span></span> <span data-ttu-id="9291c-144">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `Certificate`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-144">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="9291c-145">Configuration</span><span class="sxs-lookup"><span data-stu-id="9291c-145">Configuration</span></span>  

 <span data-ttu-id="9291c-146">다음 구성에서는 엔드포인트 동작을 사용하는 클라이언트 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-146">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="9291c-147">자세한 내용은 [인증서 작업](working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9291c-147">For more information about certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="9291c-148">또한이 코드는 <`identity`> 요소를 사용 하 여 필요한 서버 id의 DNS (Domain Name System)를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9291c-148">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="9291c-149">Id에 대 한 자세한 내용은 [서비스 id 및 인증](service-identity-and-authentication.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9291c-149">For more information about identity, see [Service Identity and Authentication](service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9291c-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9291c-150">See also</span></span>

- [<span data-ttu-id="9291c-151">보안 개요</span><span class="sxs-lookup"><span data-stu-id="9291c-151">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="9291c-152">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="9291c-152">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)
- [<span data-ttu-id="9291c-153">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="9291c-153">Working with Certificates</span></span>](working-with-certificates.md)
- <span data-ttu-id="9291c-154">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="9291c-154">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
