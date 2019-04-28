---
title: 익명 클라이언트를 사용-WCF 전송 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932960"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="45ace-102">익명 클라이언트를 사용 하 여 전송 보안</span><span class="sxs-lookup"><span data-stu-id="45ace-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="45ace-103">이 Windows Communication Foundation (WCF) 시나리오에서는 기밀성 및 무결성을 보장 하려면 전송 보안 (HTTPS)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="45ace-104">서버는 SSL(Secure Sockets Layer) 인증서로 인증되어야 하며 클라이언트는 서버의 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="45ace-105">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="45ace-106">샘플 응용 프로그램을 참조 하세요 [WS 전송 보안](../samples/ws-transport-security.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="45ace-107">전송 보안에 대 한 자세한 내용은 참조 하세요. [전송 보안 개요](transport-security-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="45ace-108">서비스에서 인증서를 사용 하는 방법에 대 한 자세한 내용은 참조 하세요. [Working with Certificates](working-with-certificates.md) 고 [방법: SSL 인증서로 포트 구성](how-to-configure-a-port-with-an-ssl-certificate.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![익명 클라이언트에서 전송 보안 사용](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="45ace-110">특성</span><span class="sxs-lookup"><span data-stu-id="45ace-110">Characteristic</span></span>|<span data-ttu-id="45ace-111">설명</span><span class="sxs-lookup"><span data-stu-id="45ace-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="45ace-112">보안 모드</span><span class="sxs-lookup"><span data-stu-id="45ace-112">Security Mode</span></span>|<span data-ttu-id="45ace-113">전송</span><span class="sxs-lookup"><span data-stu-id="45ace-113">Transport</span></span>|
|<span data-ttu-id="45ace-114">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="45ace-114">Interoperability</span></span>|<span data-ttu-id="45ace-115">기존 웹 서비스 및 클라이언트와의 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="45ace-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="45ace-116">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="45ace-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="45ace-117">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="45ace-117">Authentication (Client)</span></span>|<span data-ttu-id="45ace-118">예</span><span class="sxs-lookup"><span data-stu-id="45ace-118">Yes</span></span><br /><br /> <span data-ttu-id="45ace-119">응용 프로그램 수준 (WCF 지원 없음)</span><span class="sxs-lookup"><span data-stu-id="45ace-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="45ace-120">무결성</span><span class="sxs-lookup"><span data-stu-id="45ace-120">Integrity</span></span>|<span data-ttu-id="45ace-121">예</span><span class="sxs-lookup"><span data-stu-id="45ace-121">Yes</span></span>|
|<span data-ttu-id="45ace-122">기밀성</span><span class="sxs-lookup"><span data-stu-id="45ace-122">Confidentiality</span></span>|<span data-ttu-id="45ace-123">예</span><span class="sxs-lookup"><span data-stu-id="45ace-123">Yes</span></span>|
|<span data-ttu-id="45ace-124">전송</span><span class="sxs-lookup"><span data-stu-id="45ace-124">Transport</span></span>|<span data-ttu-id="45ace-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="45ace-125">HTTPS</span></span>|
|<span data-ttu-id="45ace-126">바인딩</span><span class="sxs-lookup"><span data-stu-id="45ace-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="45ace-127">서비스</span><span class="sxs-lookup"><span data-stu-id="45ace-127">Service</span></span>

<span data-ttu-id="45ace-128">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45ace-129">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-129">Do one of the following:</span></span>

- <span data-ttu-id="45ace-130">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="45ace-131">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="45ace-132">코드</span><span class="sxs-lookup"><span data-stu-id="45ace-132">Code</span></span>

<span data-ttu-id="45ace-133">다음 코드는 전송 보안을 사용하여 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="45ace-134">구성</span><span class="sxs-lookup"><span data-stu-id="45ace-134">Configuration</span></span>

<span data-ttu-id="45ace-135">다음 코드에서는 구성을 사용하여 동일한 엔드포인트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="45ace-136">클라이언트는 어떤 메커니즘으로도 인증되지 않는 익명 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

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

## <a name="client"></a><span data-ttu-id="45ace-137">클라이언트</span><span class="sxs-lookup"><span data-stu-id="45ace-137">Client</span></span>

<span data-ttu-id="45ace-138">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="45ace-139">다음 작업 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-139">Do one of the following:</span></span>

- <span data-ttu-id="45ace-140">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="45ace-141">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="45ace-142">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="45ace-143">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="45ace-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="45ace-144">코드</span><span class="sxs-lookup"><span data-stu-id="45ace-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="45ace-145">구성</span><span class="sxs-lookup"><span data-stu-id="45ace-145">Configuration</span></span>

<span data-ttu-id="45ace-146">다음 구성은 서비스 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45ace-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="45ace-147">참고자료</span><span class="sxs-lookup"><span data-stu-id="45ace-147">See also</span></span>

- [<span data-ttu-id="45ace-148">보안 개요</span><span class="sxs-lookup"><span data-stu-id="45ace-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="45ace-149">WS 전송 보안</span><span class="sxs-lookup"><span data-stu-id="45ace-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="45ace-150">전송 보안 개요</span><span class="sxs-lookup"><span data-stu-id="45ace-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="45ace-151">[Windows Server appfabric 보안 모델](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="45ace-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>