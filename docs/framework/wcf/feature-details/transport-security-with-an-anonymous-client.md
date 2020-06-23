---
title: 익명 클라이언트를 사용 하는 전송 보안
description: 전송 보안을 사용 하 여 클라이언트에서 신뢰 하는 인증서를 사용 하 여 서버를 인증 하는이 WCF 시나리오를 검토 합니다. 클라이언트가 인증 되지 않았습니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 08cfb8c1a5581f17a251224430018764bed80b0f
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245013"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="4355b-104">익명 클라이언트를 사용 하는 전송 보안</span><span class="sxs-lookup"><span data-stu-id="4355b-104">Transport security with an anonymous client</span></span>

<span data-ttu-id="4355b-105">이 Windows Communication Foundation (WCF) 시나리오에서는 전송 보안 (HTTPS)을 사용 하 여 기밀성과 무결성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-105">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="4355b-106">서버는 SSL(Secure Sockets Layer) 인증서로 인증되어야 하며 클라이언트는 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-106">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="4355b-107">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-107">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="4355b-108">응용 프로그램 예제는 [WS 전송 보안](../samples/ws-transport-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4355b-108">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="4355b-109">전송 보안에 대 한 자세한 내용은 [전송 보안 개요](transport-security-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4355b-109">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="4355b-110">서비스에서 인증서를 사용 하는 방법에 대 한 자세한 내용은 [인증서 작업](working-with-certificates.md) 및 [방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4355b-110">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![익명 클라이언트에서 전송 보안 사용](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="4355b-112">특성</span><span class="sxs-lookup"><span data-stu-id="4355b-112">Characteristic</span></span>|<span data-ttu-id="4355b-113">Description</span><span class="sxs-lookup"><span data-stu-id="4355b-113">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="4355b-114">보안 모드</span><span class="sxs-lookup"><span data-stu-id="4355b-114">Security Mode</span></span>|<span data-ttu-id="4355b-115">전송</span><span class="sxs-lookup"><span data-stu-id="4355b-115">Transport</span></span>|
|<span data-ttu-id="4355b-116">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="4355b-116">Interoperability</span></span>|<span data-ttu-id="4355b-117">기존 웹 서비스 및 클라이언트와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="4355b-117">With existing Web services and clients</span></span>|
|<span data-ttu-id="4355b-118">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="4355b-118">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="4355b-119">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="4355b-119">Authentication (Client)</span></span>|<span data-ttu-id="4355b-120">Yes</span><span class="sxs-lookup"><span data-stu-id="4355b-120">Yes</span></span><br /><br /> <span data-ttu-id="4355b-121">응용 프로그램 수준 (WCF 지원 안 함)</span><span class="sxs-lookup"><span data-stu-id="4355b-121">Application level (no WCF support)</span></span>|
|<span data-ttu-id="4355b-122">무결성</span><span class="sxs-lookup"><span data-stu-id="4355b-122">Integrity</span></span>|<span data-ttu-id="4355b-123">Yes</span><span class="sxs-lookup"><span data-stu-id="4355b-123">Yes</span></span>|
|<span data-ttu-id="4355b-124">기밀성</span><span class="sxs-lookup"><span data-stu-id="4355b-124">Confidentiality</span></span>|<span data-ttu-id="4355b-125">Yes</span><span class="sxs-lookup"><span data-stu-id="4355b-125">Yes</span></span>|
|<span data-ttu-id="4355b-126">전송</span><span class="sxs-lookup"><span data-stu-id="4355b-126">Transport</span></span>|<span data-ttu-id="4355b-127">HTTPS</span><span class="sxs-lookup"><span data-stu-id="4355b-127">HTTPS</span></span>|
|<span data-ttu-id="4355b-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="4355b-128">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="4355b-129">서비스</span><span class="sxs-lookup"><span data-stu-id="4355b-129">Service</span></span>

<span data-ttu-id="4355b-130">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-130">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4355b-131">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-131">Do one of the following:</span></span>

- <span data-ttu-id="4355b-132">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-132">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="4355b-133">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-133">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="4355b-134">코드</span><span class="sxs-lookup"><span data-stu-id="4355b-134">Code</span></span>

<span data-ttu-id="4355b-135">다음 코드는 전송 보안을 사용하여 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-135">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="4355b-136">Configuration</span><span class="sxs-lookup"><span data-stu-id="4355b-136">Configuration</span></span>

<span data-ttu-id="4355b-137">다음 코드에서는 구성을 사용하여 동일한 엔드포인트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-137">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="4355b-138">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-138">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a><span data-ttu-id="4355b-139">Client</span><span class="sxs-lookup"><span data-stu-id="4355b-139">Client</span></span>

<span data-ttu-id="4355b-140">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-140">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4355b-141">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-141">Do one of the following:</span></span>

- <span data-ttu-id="4355b-142">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-142">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="4355b-143">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-143">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="4355b-144">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-144">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="4355b-145">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4355b-145">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="4355b-146">코드</span><span class="sxs-lookup"><span data-stu-id="4355b-146">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="4355b-147">Configuration</span><span class="sxs-lookup"><span data-stu-id="4355b-147">Configuration</span></span>

<span data-ttu-id="4355b-148">다음 구성은 서비스 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4355b-148">The following configuration can be used instead of the code to set up the service.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
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

## <a name="see-also"></a><span data-ttu-id="4355b-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4355b-149">See also</span></span>

- [<span data-ttu-id="4355b-150">보안 개요</span><span class="sxs-lookup"><span data-stu-id="4355b-150">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="4355b-151">WS 전송 보안</span><span class="sxs-lookup"><span data-stu-id="4355b-151">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="4355b-152">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="4355b-152">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="4355b-153">[Windows Server AppFabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4355b-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
