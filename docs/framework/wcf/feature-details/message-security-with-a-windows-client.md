---
description: '자세한 정보: Windows 클라이언트를 사용 하는 메시지 보안'
title: Windows 클라이언트를 사용하는 메시지 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 97d415f68b4374ab2b18360347d7753f6be51313
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756099"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="2d2f9-103">Windows 클라이언트를 사용하는 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="2d2f9-103">Message Security with a Windows Client</span></span>

<span data-ttu-id="2d2f9-104">이 시나리오에서는 메시지 보안 모드에서 보호 되는 WCF (Windows Communication Foundation) 클라이언트 및 서버를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-104">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="2d2f9-105">클라이언트와 서비스는 Windows 자격 증명을 사용하여 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-105">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="2d2f9-106">![Windows 클라이언트를 사용 하는 메시지 보안](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="2d2f9-106">![Message security with a Windows client](media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="2d2f9-107">특성</span><span class="sxs-lookup"><span data-stu-id="2d2f9-107">Characteristic</span></span>|<span data-ttu-id="2d2f9-108">설명</span><span class="sxs-lookup"><span data-stu-id="2d2f9-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="2d2f9-109">보안 모드</span><span class="sxs-lookup"><span data-stu-id="2d2f9-109">Security Mode</span></span>|<span data-ttu-id="2d2f9-110">메시지</span><span class="sxs-lookup"><span data-stu-id="2d2f9-110">Message</span></span>|  
|<span data-ttu-id="2d2f9-111">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2d2f9-111">Interoperability</span></span>|<span data-ttu-id="2d2f9-112">WCF만</span><span class="sxs-lookup"><span data-stu-id="2d2f9-112">WCF Only</span></span>|  
|<span data-ttu-id="2d2f9-113">인증(서버)</span><span class="sxs-lookup"><span data-stu-id="2d2f9-113">Authentication (Server)</span></span>|<span data-ttu-id="2d2f9-114">서버와 클라이언트의 상호 인증</span><span class="sxs-lookup"><span data-stu-id="2d2f9-114">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="2d2f9-115">인증(클라이언트)</span><span class="sxs-lookup"><span data-stu-id="2d2f9-115">Authentication (Client)</span></span>|<span data-ttu-id="2d2f9-116">서버와 클라이언트의 상호 인증</span><span class="sxs-lookup"><span data-stu-id="2d2f9-116">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="2d2f9-117">무결성</span><span class="sxs-lookup"><span data-stu-id="2d2f9-117">Integrity</span></span>|<span data-ttu-id="2d2f9-118">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="2d2f9-118">Yes, using shared security context</span></span>|  
|<span data-ttu-id="2d2f9-119">기밀성</span><span class="sxs-lookup"><span data-stu-id="2d2f9-119">Confidentiality</span></span>|<span data-ttu-id="2d2f9-120">예, 공유 보안 컨텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="2d2f9-120">Yes, using shared security context</span></span>|  
|<span data-ttu-id="2d2f9-121">전송</span><span class="sxs-lookup"><span data-stu-id="2d2f9-121">Transport</span></span>|<span data-ttu-id="2d2f9-122">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="2d2f9-122">NET.TCP</span></span>|  
|<span data-ttu-id="2d2f9-123">바인딩</span><span class="sxs-lookup"><span data-stu-id="2d2f9-123">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="2d2f9-124">서비스</span><span class="sxs-lookup"><span data-stu-id="2d2f9-124">Service</span></span>  

 <span data-ttu-id="2d2f9-125">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2d2f9-126">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-126">Do one of the following:</span></span>  
  
- <span data-ttu-id="2d2f9-127">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="2d2f9-128">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2d2f9-129">코드</span><span class="sxs-lookup"><span data-stu-id="2d2f9-129">Code</span></span>  

 <span data-ttu-id="2d2f9-130">다음 코드에서는 Windows 컴퓨터의 안전한 컨텍스트를 설정하기 위해 메시지 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-130">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="2d2f9-131">Configuration</span><span class="sxs-lookup"><span data-stu-id="2d2f9-131">Configuration</span></span>  

 <span data-ttu-id="2d2f9-132">다음 구성은 서비스를 설정하는 데 코드 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-132">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="2d2f9-133">클라이언트</span><span class="sxs-lookup"><span data-stu-id="2d2f9-133">Client</span></span>  

 <span data-ttu-id="2d2f9-134">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-134">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="2d2f9-135">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-135">Do one of the following:</span></span>  
  
- <span data-ttu-id="2d2f9-136">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-136">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="2d2f9-137">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-137">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="2d2f9-138">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-138">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="2d2f9-139">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="2d2f9-139">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="2d2f9-140">코드</span><span class="sxs-lookup"><span data-stu-id="2d2f9-140">Code</span></span>  

 <span data-ttu-id="2d2f9-141">다음 코드에서는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-141">The following code creates a client.</span></span> <span data-ttu-id="2d2f9-142">바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `Windows`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-142">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="2d2f9-143">Configuration</span><span class="sxs-lookup"><span data-stu-id="2d2f9-143">Configuration</span></span>  

 <span data-ttu-id="2d2f9-144">다음 구성은 클라이언트 속성을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2f9-144">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d2f9-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d2f9-145">See also</span></span>

- [<span data-ttu-id="2d2f9-146">보안 개요</span><span class="sxs-lookup"><span data-stu-id="2d2f9-146">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="2d2f9-147">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2d2f9-147">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
