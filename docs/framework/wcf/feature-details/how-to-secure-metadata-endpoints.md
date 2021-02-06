---
description: '자세히 알아보기: 방법: 메타 데이터 끝점 보안 설정'
title: '방법: 메타데이터 엔드포인트 보안'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9f71b6ae-737c-4382-8d89-0a7b1c7e182b
ms.openlocfilehash: bcce3fd0708049435c791cae5064f84133dfd612
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643308"
---
# <a name="how-to-secure-metadata-endpoints"></a><span data-ttu-id="a3766-103">방법: 메타데이터 엔드포인트 보안</span><span class="sxs-lookup"><span data-stu-id="a3766-103">How to: Secure Metadata Endpoints</span></span>

<span data-ttu-id="a3766-104">서비스의 메타데이터에는 악의적인 사용자가 활용할 수 있는 애플리케이션에 대한 중요한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-104">Metadata for a service can contain sensitive information about your application that a malicious user can leverage.</span></span> <span data-ttu-id="a3766-105">또한 서비스의 소비자는 서비스의 메타데이터를 가져오기 위한 보안 메커니즘이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-105">Consumers of your service may also require a secure mechanism for obtaining metadata about your service.</span></span> <span data-ttu-id="a3766-106">따라서 보안 엔드포인트를 사용하여 메타데이터를 게시해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-106">Therefore, it is sometimes necessary to publish your metadata using a secure endpoint.</span></span>

<span data-ttu-id="a3766-107">메타 데이터 끝점은 일반적으로 응용 프로그램 끝점 보안을 위해 WCF (Windows Communication Foundation)에 정의 된 표준 보안 메커니즘을 사용 하 여 보호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-107">Metadata endpoints are generally secured using the standard security mechanisms defined in Windows Communication Foundation (WCF) for securing application endpoints.</span></span> <span data-ttu-id="a3766-108">자세한 내용은 [보안 개요](security-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3766-108">For more information, see [Security Overview](security-overview.md).</span></span>

<span data-ttu-id="a3766-109">이 항목에서는 SSL(Secure Sockets Layer) 인증서 즉, HTTPS 엔드포인트로 보안되는 엔드포인트를 만드는 방법에 대해 단계별로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-109">This topic walks through the steps to create an endpoint secured by a Secure Sockets Layer (SSL) certificate or, in other words, an HTTPS endpoint.</span></span>

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-code"></a><span data-ttu-id="a3766-110">코드에 보안 HTTPS GET 메타데이터 엔드포인트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a3766-110">To create a secure HTTPS GET metadata endpoint in code</span></span>

1. <span data-ttu-id="a3766-111">적절한 X.509 인증서를 사용하여 포트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-111">Configure a port with an appropriate X.509 certificate.</span></span> <span data-ttu-id="a3766-112">인증서는 신뢰할 수 있는 기관에서 가져와야 하며 "서비스 인증"의 용도로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-112">The certificate must come from a trusted authority, and it must have an intended use of "Service Authorization."</span></span> <span data-ttu-id="a3766-113">HttpCfg.exe 도구를 사용하여 인증서를 포트에 첨부해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-113">You must use the HttpCfg.exe tool to attach the certificate to the port.</span></span> <span data-ttu-id="a3766-114">[방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a3766-114">See [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a3766-115">인증서의 주체 또는 인증서의 DNS(Domain Name System)는 컴퓨터의 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-115">The subject of the certificate or its Domain Name System (DNS) must match the name of the computer.</span></span> <span data-ttu-id="a3766-116">이는 HTTPS 메커니즘에서 수행하는 첫 번째 단계 중 하나로서 인증서가 호출된 주소와 동일한 URI(Uniform Resource Identifier)에 발급되었는지 확인하는 단계이므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-116">This is essential because one of the first steps the HTTPS mechanism performs is to check that the certificate is issued to the same Uniform Resource Identifier (URI) as the address upon which it is invoked.</span></span>

2. <span data-ttu-id="a3766-117"><xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-117">Create a new instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class.</span></span>

3. <span data-ttu-id="a3766-118"><xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 클래스의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class to `true`.</span></span>

4. <span data-ttu-id="a3766-119"><xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> 속성을 적절한 URL로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-119">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A> property to an appropriate URL.</span></span> <span data-ttu-id="a3766-120">절대 주소를 지정 하는 경우 URL은 스키마로 시작 해야 합니다 `https://` .</span><span class="sxs-lookup"><span data-stu-id="a3766-120">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="a3766-121">상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-121">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="a3766-122">이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-122">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

5. <span data-ttu-id="a3766-123">다음 코드에서처럼 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 클래스의 <xref:System.ServiceModel.Description.ServiceDescription> 속성이 반환하는 동작 컬렉션에 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-123">Add the instance to the behaviors collection that the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> property of the <xref:System.ServiceModel.Description.ServiceDescription> class returns, as shown in the following code.</span></span>

    [!code-csharp[c_HowToSecureEndpoint#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#1)]
    [!code-vb[c_HowToSecureEndpoint#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#1)]

### <a name="to-create-a-secure-https-get-metadata-endpoint-in-configuration"></a><span data-ttu-id="a3766-124">구성에 보안 HTTPS GET 메타데이터 엔드포인트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a3766-124">To create a secure HTTPS GET metadata endpoint in configuration</span></span>

1. <span data-ttu-id="a3766-125">[\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) 서비스에 대 한 구성 파일의 요소에 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-125">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element of the configuration file for your service.</span></span>

2. <span data-ttu-id="a3766-126">요소 [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) 를 요소에 추가 [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-126">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) element to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

3. <span data-ttu-id="a3766-127">요소 [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) 를 요소에 추가 `<serviceBehaviors>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-127">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element to the `<serviceBehaviors>` element.</span></span>

4. <span data-ttu-id="a3766-128">`name` 요소의 `<behavior>` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-128">Set the `name` attribute of the `<behavior>` element to an appropriate value.</span></span> <span data-ttu-id="a3766-129">`name` 특성은 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-129">The `name` attribute is required.</span></span> <span data-ttu-id="a3766-130">아래 예제에서는 `mySvcBehavior` 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-130">The example below uses the value `mySvcBehavior`.</span></span>

5. <span data-ttu-id="a3766-131">[\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md)요소에를 추가 `<behavior>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-131">Add a [\<serviceMetadata>](../../configure-apps/file-schema/wcf/servicemetadata.md) to the `<behavior>` element.</span></span>

6. <span data-ttu-id="a3766-132">`httpsGetEnabled` 요소의 `<serviceMetadata>` 특성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-132">Set the `httpsGetEnabled` attribute of the `<serviceMetadata>` element to `true`.</span></span>

7. <span data-ttu-id="a3766-133">`httpsGetUrl` 요소의 `<serviceMetadata>` 특성을 적절한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-133">Set the `httpsGetUrl` attribute of the `<serviceMetadata>` element to an appropriate value.</span></span> <span data-ttu-id="a3766-134">절대 주소를 지정 하는 경우 URL은 스키마로 시작 해야 합니다 `https://` .</span><span class="sxs-lookup"><span data-stu-id="a3766-134">Note that if you specify an absolute address, the URL must begin with the scheme `https://`.</span></span> <span data-ttu-id="a3766-135">상대 주소를 지정하는 경우 서비스 호스트의 HTTPS 기본 주소를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-135">If you specify a relative address, you must supply an HTTPS base address for your service host.</span></span> <span data-ttu-id="a3766-136">이 속성을 설정하지 않으면 기본 주소는 ""이거나 바로 서비스의 HTTPS 기본 주소로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-136">If this property is not set, the default address is "", or directly at the HTTPS base address for the service.</span></span>

8. <span data-ttu-id="a3766-137">서비스에서 동작을 사용 하려면 `behaviorConfiguration` 요소의 특성을 [\<service>](../../configure-apps/file-schema/wcf/service.md) behavior 요소의 name 특성 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-137">To use the behavior with a service, set the `behaviorConfiguration` attribute of the [\<service>](../../configure-apps/file-schema/wcf/service.md) element to the value of the name attribute of the behavior element.</span></span> <span data-ttu-id="a3766-138">다음 구성 코드에서는 자세한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-138">The following configuration code shows a complete example.</span></span>

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
     <system.serviceModel>
      <behaviors>
       <serviceBehaviors>
        <behavior name="mySvcBehavior">
         <serviceMetadata httpsGetEnabled="true"
              httpsGetUrl="https://localhost:8036/calcMetadata" />
        </behavior>
       </serviceBehaviors>
      </behaviors>
     <services>
      <service behaviorConfiguration="mySvcBehavior"
            name="Microsoft.Security.Samples.Calculator">
       <endpoint address="http://localhost:8037/ServiceModelSamples/calculator"
       binding="wsHttpBinding" bindingConfiguration=""
       contract="Microsoft.Security.Samples.ICalculator" />
      </service>
     </services>
    </system.serviceModel>
    </configuration>
    ```

## <a name="example"></a><span data-ttu-id="a3766-139">예제</span><span class="sxs-lookup"><span data-stu-id="a3766-139">Example</span></span>

<span data-ttu-id="a3766-140">다음 예제에서는 <xref:System.ServiceModel.ServiceHost> 클래스의 인스턴스를 만들고 엔드포인트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-140">The following example creates an instance of a <xref:System.ServiceModel.ServiceHost> class and adds an endpoint.</span></span> <span data-ttu-id="a3766-141">그런 다음 코드는 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 클래스의 인스턴스를 만들고, 속성을 설정하여 보안 메타데이터 교환 지점을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-141">The code then creates an instance of the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> class and sets the properties to create a secure metadata exchange point.</span></span>

[!code-csharp[c_HowToSecureEndpoint#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosecureendpoint/cs/source.cs#0)]
[!code-vb[c_HowToSecureEndpoint#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosecureendpoint/vb/source.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="a3766-142">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a3766-142">Compiling the Code</span></span>

<span data-ttu-id="a3766-143">코드 예제에서는 다음 네임스페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a3766-143">The code example uses the following namespaces:</span></span>

- <xref:System.ServiceModel?displayProperty=nameWithType>

- <xref:System.ServiceModel.Description?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="a3766-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3766-144">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>
- [<span data-ttu-id="a3766-145">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="a3766-145">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="a3766-146">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="a3766-146">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="a3766-147">메타데이터 관련 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="a3766-147">Security Considerations with Metadata</span></span>](security-considerations-with-metadata.md)
- [<span data-ttu-id="a3766-148">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a3766-148">Securing Services and Clients</span></span>](securing-services-and-clients.md)
