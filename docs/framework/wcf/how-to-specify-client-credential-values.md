---
title: '방법: 클라이언트 자격 증명 값 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: ecb8f7ef74f1f0625454eb2d6cebf9d282a5ece3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003030"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="0fafe-102">방법: 클라이언트 자격 증명 값 지정</span><span class="sxs-lookup"><span data-stu-id="0fafe-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="0fafe-103">Windows Communication Foundation (WCF)를 사용 하는, 서비스 클라이언트가 서비스에 인증 하는 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="0fafe-104">예를 들면 서비스는 클라이언트가 인증서를 사용하여 인증하도록 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="0fafe-105">클라이언트 자격 증명 형식을 결정하려면</span><span class="sxs-lookup"><span data-stu-id="0fafe-105">To determine the client credential type</span></span>  
  
1. <span data-ttu-id="0fafe-106">서비스의 메타데이터 엔드포인트에서 메타데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="0fafe-107">메타데이터는 보통 사용자가 선택한 프로그래밍 언어로 된 클라이언트 코드(기본적으로 Visual C#)와 XML 구성 파일의 두 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="0fafe-108">메타데이터를 검색하는 방법 중 하나는 Svcutil.exe 도구를 사용해 클라이언트 코드와 클라이언트 구성을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="0fafe-109">자세한 내용은 [메타 데이터 가져오기](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) 하 고 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2. <span data-ttu-id="0fafe-110">XML 구성 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-110">Open the XML configuration file.</span></span> <span data-ttu-id="0fafe-111">Svcutil.exe 도구를 사용하는 경우 이 파일의 기본 이름은 Output.config입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3. <span data-ttu-id="0fafe-112">찾을 합니다  **\<보안 >** 사용 하 여 요소를 **모드** 특성 (**< 보안 모드 =** `MessageOrTransport` **>** 여기서 `MessageOrTransport` 보안 모드 중 하나로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4. <span data-ttu-id="0fafe-113">모드 값과 일치하는 자식 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="0fafe-114">예를 들어, 모드로 설정 된 경우 **메시지**, 찾을  **\<메시지 >** 에 포함 된 요소를  **\<보안 >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5. <span data-ttu-id="0fafe-115">에 할당 된 값을 확인 합니다 **clientCredentialType** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="0fafe-116">실제 값은 사용하는 모드(Transport/Message)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="0fafe-117">다음 XML 코드는 메시지 보안을 사용하며 인증서를 사용해 클라이언트를 인증하도록 하는 클라이언트의 구성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="0fafe-118">예제: 클라이언트 자격 증명으로 인증서를 사용 하 여 TCP Transport 모드</span><span class="sxs-lookup"><span data-stu-id="0fafe-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="0fafe-119">이 예제에서는 보안 모드를 Transport 모드로 설정하고 클라이언트 자격 증명 값을 X.509 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="0fafe-120">다음 절차에서는 코드와 구성에 클라이언트에 대한 클라이언트 자격 증명 값을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="0fafe-121">사용 했다고 가정 합니다 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에서 메타 데이터 (코드 및 구성)를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="0fafe-122">자세한 내용은 [방법: 클라이언트를 만드는](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-122">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="0fafe-123">코드에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="0fafe-123">To specify the client credential value on the client in code</span></span>  
  
1. <span data-ttu-id="0fafe-124">사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스에서 코드 및 구성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2. <span data-ttu-id="0fafe-125">생성된 된 코드를 사용 하 여 WCF 클라이언트의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-125">Create an instance of the WCF client using the generated code.</span></span>  
  
3. <span data-ttu-id="0fafe-126">클라이언트 클래스에서 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="0fafe-127">이 예제에서는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> 메서드를 사용하여 속성을 X.509 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="0fafe-128"><xref:System.Security.Cryptography.X509Certificates.X509FindType> 클래스의 열거를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="0fafe-129">주체 이름은 만료 날짜로 인해 인증서가 변경된 경우 여기서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="0fafe-130">주체 이름을 사용하면 인프라에서 인증서를 다시 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="0fafe-131">구성에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="0fafe-131">To specify the client credential value on the client in configuration</span></span>  
  
1. <span data-ttu-id="0fafe-132">추가 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2. <span data-ttu-id="0fafe-133">추가 된 [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소를 [ \<동작 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="0fafe-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="0fafe-134">필수 `name` 특성을 적절한 값으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="0fafe-135">추가 된 [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) 요소를 [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소.</span><span class="sxs-lookup"><span data-stu-id="0fafe-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4. <span data-ttu-id="0fafe-136">다음 코드에서처럼 `storeLocation`, `storeName`, `x509FindType` 및 `findValue` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="0fafe-137">자세한 내용은 [인증서 작업](../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0fafe-137">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5. <span data-ttu-id="0fafe-138">클라이언트를 구성할 때 다음 코드에서처럼 `behaviorConfiguration` 요소의 `<endpoint>` 특성을 설정하여 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="0fafe-139">끝점 요소는 자식 합니다 [ \<클라이언트 >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="0fafe-140">또한 `bindingConfiguration` 특성을 클라이언트에 대한 바인딩으로 설정하여 바인딩 구성 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="0fafe-141">생성된 구성 파일을 사용하는 경우 바인딩의 이름이 자동으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="0fafe-142">이 예제에서 이름은 `"tcpBindingWithCredential"`입니다.</span><span class="sxs-lookup"><span data-stu-id="0fafe-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0fafe-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="0fafe-143">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="0fafe-144">WCF 보안 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0fafe-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [<span data-ttu-id="0fafe-145">자격 증명 형식 선택</span><span class="sxs-lookup"><span data-stu-id="0fafe-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="0fafe-146">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0fafe-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="0fafe-147">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="0fafe-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0fafe-148">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0fafe-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="0fafe-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="0fafe-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)
- [<span data-ttu-id="0fafe-150">\<security></span><span class="sxs-lookup"><span data-stu-id="0fafe-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [<span data-ttu-id="0fafe-151">\<message></span><span class="sxs-lookup"><span data-stu-id="0fafe-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [<span data-ttu-id="0fafe-152">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0fafe-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [<span data-ttu-id="0fafe-153">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0fafe-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
- [<span data-ttu-id="0fafe-154">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="0fafe-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [<span data-ttu-id="0fafe-155">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="0fafe-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
