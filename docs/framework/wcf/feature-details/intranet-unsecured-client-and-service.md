---
description: '자세히 알아보기: 인트라넷 보안 되지 않은 클라이언트 및 서비스'
title: 보안이 설정되지 않은 인트라넷 클라이언트 및 서비스
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: a03abc5b8eb0317c4d5d19347b3974d615570069
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704526"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="6ce25-103">보안이 설정되지 않은 인트라넷 클라이언트 및 서비스</span><span class="sxs-lookup"><span data-stu-id="6ce25-103">Intranet Unsecured Client and Service</span></span>

<span data-ttu-id="6ce25-104">다음 그림은 WCF 응용 프로그램에 보안 개인 네트워크에 대 한 정보를 제공 하기 위해 개발 된 간단한 Windows Communication Foundation (WCF) 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-104">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="6ce25-105">데이터가 중요 하지 않거나, 네트워크를 본질적으로 안전 하 게 보호 하거나, WCF 인프라 아래 계층에서 보안을 제공 하기 때문에 보안이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-105">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![보안이 적용 되지 않은 인트라넷 클라이언트 및 서비스 시나리오](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="6ce25-107">특성</span><span class="sxs-lookup"><span data-stu-id="6ce25-107">Characteristic</span></span>|<span data-ttu-id="6ce25-108">설명</span><span class="sxs-lookup"><span data-stu-id="6ce25-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6ce25-109">보안 모드</span><span class="sxs-lookup"><span data-stu-id="6ce25-109">Security Mode</span></span>|<span data-ttu-id="6ce25-110">없음</span><span class="sxs-lookup"><span data-stu-id="6ce25-110">None</span></span>|  
|<span data-ttu-id="6ce25-111">전송</span><span class="sxs-lookup"><span data-stu-id="6ce25-111">Transport</span></span>|<span data-ttu-id="6ce25-112">TCP</span><span class="sxs-lookup"><span data-stu-id="6ce25-112">TCP</span></span>|  
|<span data-ttu-id="6ce25-113">바인딩</span><span class="sxs-lookup"><span data-stu-id="6ce25-113">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="6ce25-114">상호 운용성</span><span class="sxs-lookup"><span data-stu-id="6ce25-114">Interoperability</span></span>|<span data-ttu-id="6ce25-115">WCF만</span><span class="sxs-lookup"><span data-stu-id="6ce25-115">WCF only</span></span>|  
|<span data-ttu-id="6ce25-116">인증</span><span class="sxs-lookup"><span data-stu-id="6ce25-116">Authentication</span></span>|<span data-ttu-id="6ce25-117">없음</span><span class="sxs-lookup"><span data-stu-id="6ce25-117">None</span></span>|  
|<span data-ttu-id="6ce25-118">무결성</span><span class="sxs-lookup"><span data-stu-id="6ce25-118">Integrity</span></span>|<span data-ttu-id="6ce25-119">없음</span><span class="sxs-lookup"><span data-stu-id="6ce25-119">None</span></span>|  
|<span data-ttu-id="6ce25-120">기밀성</span><span class="sxs-lookup"><span data-stu-id="6ce25-120">Confidentiality</span></span>|<span data-ttu-id="6ce25-121">없음</span><span class="sxs-lookup"><span data-stu-id="6ce25-121">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="6ce25-122">서비스</span><span class="sxs-lookup"><span data-stu-id="6ce25-122">Service</span></span>  

 <span data-ttu-id="6ce25-123">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-123">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6ce25-124">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-124">Do one of the following:</span></span>  
  
- <span data-ttu-id="6ce25-125">구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-125">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="6ce25-126">제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-126">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6ce25-127">코드</span><span class="sxs-lookup"><span data-stu-id="6ce25-127">Code</span></span>  

 <span data-ttu-id="6ce25-128">다음 코드는 보안 없이 엔드포인트를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-128">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="6ce25-129">Configuration</span><span class="sxs-lookup"><span data-stu-id="6ce25-129">Configuration</span></span>  

 <span data-ttu-id="6ce25-130">다음 코드는 구성을 사용하여 동일한 엔드포인트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-130">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="6ce25-131">클라이언트</span><span class="sxs-lookup"><span data-stu-id="6ce25-131">Client</span></span>  

 <span data-ttu-id="6ce25-132">다음 코드와 구성은 독립적으로 실행되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-132">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6ce25-133">다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-133">Do one of the following:</span></span>  
  
- <span data-ttu-id="6ce25-134">이 코드와 클라이언트 코드를 사용하여 독립 실행형 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-134">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="6ce25-135">엔드포인트 주소를 정의하지 않는 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-135">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6ce25-136">대신 구성 이름을 인수로 사용하는 클라이언트 생성자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-136">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6ce25-137">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="6ce25-137">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6ce25-138">코드</span><span class="sxs-lookup"><span data-stu-id="6ce25-138">Code</span></span>  

 <span data-ttu-id="6ce25-139">다음 코드에서는 TCP 프로토콜을 사용 하 여 보안 되지 않은 끝점에 액세스 하는 기본 WCF 클라이언트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-139">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="6ce25-140">Configuration</span><span class="sxs-lookup"><span data-stu-id="6ce25-140">Configuration</span></span>  

 <span data-ttu-id="6ce25-141">다음 구성 코드는 클라이언트에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ce25-141">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ce25-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ce25-142">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="6ce25-143">보안 개요</span><span class="sxs-lookup"><span data-stu-id="6ce25-143">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="6ce25-144">[Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="6ce25-144">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
