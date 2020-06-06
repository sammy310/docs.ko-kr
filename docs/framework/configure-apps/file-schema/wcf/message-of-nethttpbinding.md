---
title: <netHttpBinding>의 <message>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738965"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="0f599-102">\<netHttpBinding>의 \<message></span><span class="sxs-lookup"><span data-stu-id="0f599-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="0f599-103">의 메시지 수준 보안 설정을 정의 합니다 [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="0f599-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="0f599-104">구문</span><span class="sxs-lookup"><span data-stu-id="0f599-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0f599-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0f599-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0f599-106">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f599-107">특성</span><span class="sxs-lookup"><span data-stu-id="0f599-107">Attributes</span></span>  
  
|<span data-ttu-id="0f599-108">attribute</span><span class="sxs-lookup"><span data-stu-id="0f599-108">Attribute</span></span>|<span data-ttu-id="0f599-109">Description</span><span class="sxs-lookup"><span data-stu-id="0f599-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f599-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="0f599-110">algorithmSuite</span></span>|<span data-ttu-id="0f599-111">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-111">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="0f599-112">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식이며 알고리즘 및 키 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="0f599-113">이러한 알고리즘은 보안 정책 언어(WS-SecurityPolicy) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-113">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="0f599-114">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-114">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="0f599-115">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="0f599-115">clientCredentialType</span></span>|<span data-ttu-id="0f599-116">메시지 기반 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-116">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="0f599-117">기본값은 `UserName`입니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-117">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="0f599-118">clientCredentialType 특성</span><span class="sxs-lookup"><span data-stu-id="0f599-118">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="0f599-119">값</span><span class="sxs-lookup"><span data-stu-id="0f599-119">Value</span></span>|<span data-ttu-id="0f599-120">Description</span><span class="sxs-lookup"><span data-stu-id="0f599-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0f599-121">UserName</span><span class="sxs-lookup"><span data-stu-id="0f599-121">UserName</span></span>|<span data-ttu-id="0f599-122">-사용자 이름 자격 증명을 사용 하 여 서버에 대해 클라이언트를 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-122">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="0f599-123">이 자격 증명은 <> 요소를 사용 하 여 지정 해야 `clientCredentials` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-123">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="0f599-124">-WCF는 암호 다이제스트를 보내거나 암호를 사용 하 여 키를 파생 하 고 메시지 보안에 이러한 키를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-124">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="0f599-125">따라서 WCF는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-125">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="0f599-126">`basicHttpBinding`의 경우 SSL 채널을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-126">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="0f599-127">인증서</span><span class="sxs-lookup"><span data-stu-id="0f599-127">Certificate</span></span>|<span data-ttu-id="0f599-128">클라이언트가 인증서를 사용하여 서버의 인증을 받도록 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-128">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="0f599-129">이 경우 <`clientCredentials`> 및 <>를 사용 하 여 클라이언트 자격 증명을 지정 해야 합니다 `clientCertificate` .</span><span class="sxs-lookup"><span data-stu-id="0f599-129">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="0f599-130">또한 메시지 보안 모드를 사용하는 경우 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-130">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="0f599-131">이 경우 클래스 또는 동작 요소를 사용 하 여 서비스 자격 증명을 지정 하 <xref:System.ServiceModel.Description.ClientCredentials> `ClientCredentials` 고 \<serviceCertificate> serviceCredentials의 요소를 사용 하 여 서비스 인증서를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-131">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f599-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0f599-132">Child Elements</span></span>  
 <span data-ttu-id="0f599-133">None</span><span class="sxs-lookup"><span data-stu-id="0f599-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f599-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0f599-134">Parent Elements</span></span>  
  
|<span data-ttu-id="0f599-135">요소</span><span class="sxs-lookup"><span data-stu-id="0f599-135">Element</span></span>|<span data-ttu-id="0f599-136">Description</span><span class="sxs-lookup"><span data-stu-id="0f599-136">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0f599-137"><`security`<의> 요소`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="0f599-137"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="0f599-138"><> 요소에 대 한 보안 기능을 정의 합니다 `netHttpBinding` .</span><span class="sxs-lookup"><span data-stu-id="0f599-138">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0f599-139">예제</span><span class="sxs-lookup"><span data-stu-id="0f599-139">Example</span></span>  
 <span data-ttu-id="0f599-140">이 샘플에서는 basicHttpBinding 및 메시지 보안을 사용하는 애플리케이션을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-140">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="0f599-141">다음 서비스 구성 예제에서 엔드포인트 정의는 basicHttpBinding을 지정하고 `Binding1`이라는 바인딩 구성을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-141">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="0f599-142">서비스가 클라이언트에게 자신을 인증하는 데 사용하는 인증서는 구성 파일의 `behaviors` 섹션에 있는 `serviceCredentials` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-142">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="0f599-143">클라이언트가 서비스에 자신을 인증하는 데 사용하는 인증서에 적용되는 유효성 검사 모드 또한 `behaviors` 섹션에서 `clientCertificate` 요소 아래에 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-143">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="0f599-144">동일한 바인딩 및 보안 세부 정보가 클라이언트 구성 파일에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f599-144">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
                 is in the user's Trusted People store, then it will be trusted without performing a
                 validation of the certificate's issuer chain. This setting is used here for convenience so that the
                 sample can be run without having to have certificates issued by a certification authority (CA).
                 This setting is less secure than the default, ChainTrust. The security implications of this
                 setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="0f599-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f599-145">See also</span></span>

- [<span data-ttu-id="0f599-146">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0f599-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0f599-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="0f599-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0f599-148">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="0f599-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0f599-149">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="0f599-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
