---
description: '자세한 정보: 방법: WCF 클라이언트를 사용 하 여 WSE 3.0 서비스 액세스'
title: '방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 5a117b4c3d743d783c37ed3e27e3cf11e44abec3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742929"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a><span data-ttu-id="5b853-103">방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스</span><span class="sxs-lookup"><span data-stu-id="5b853-103">How to: Access a WSE 3.0 Service with a WCF Client</span></span>

<span data-ttu-id="5b853-104">Wcf 클라이언트가 WS-Addressing 사양의 8 월 2004 버전을 사용 하도록 구성 된 경우 WCF (Windows Communication Foundation) 클라이언트는 Microsoft .NET 서비스의 WSE (Web Services 개선) 3.0와 유선 수준으로 호환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-104">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements (WSE) 3.0 for Microsoft .NET services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span> <span data-ttu-id="5b853-105">그러나 WSE 3.0 서비스는 MEX (metadata exchange) 프로토콜을 지원 하지 않으므로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 wcf 클라이언트 클래스를 만들 때 생성 된 wcf 클라이언트에는 보안 설정이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-105">However, WSE 3.0 services do not support the metadata exchange (MEX) protocol, so when you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client class, the security settings are not applied to the generated WCF client.</span></span> <span data-ttu-id="5b853-106">따라서 WCF 클라이언트가 생성 된 후 WSE 3.0 서비스에서 요구 하는 보안 설정을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-106">Therefore, you must specify the security settings that the WSE 3.0 service requires after the WCF client is generated.</span></span>  
  
 <span data-ttu-id="5b853-107">Wse 3.0 서비스와 WCF 클라이언트 간의 상호 운용 가능한 요구 사항 및 WSE 3.0 서비스의 요구 사항을 고려 하 여 사용자 지정 바인딩을 사용 하 여 이러한 보안 설정을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-107">You can apply these security settings by using a custom binding to take into account the WSE 3.0 service's requirements and the interoperable requirements between a WSE 3.0 service and a WCF client.</span></span> <span data-ttu-id="5b853-108">이러한 상호 운용성 요구 사항에는 앞에서 말한 August 2004 WS-Addressing 사양 및 WSE 3.0의 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> 기본 메시지 보호를 사용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-108">These interoperability requirements include the aforementioned use of the August 2004 WS-Addressing specification and the  WSE 3.0default message protection of <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span> <span data-ttu-id="5b853-109">WCF에 대 한 기본 메시지 보호는 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> 입니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-109">The default message protection for WCF is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="5b853-110">이 항목에서는 WSE 3.0 서비스와 상호 작용 하는 WCF 바인딩을 만드는 방법에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-110">This topic details how to create a WCF binding that interoperates with a WSE 3.0 service.</span></span> <span data-ttu-id="5b853-111">WCF는이 바인딩을 통합 하는 샘플도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-111">WCF also provides a sample that incorporates this binding.</span></span> <span data-ttu-id="5b853-112">이 샘플에 대 한 자세한 내용은 [ASMX 웹 서비스와 상호 운용](../samples/interoperating-with-asmx-web-services.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b853-112">For more information about this sample, see [Interoperating with ASMX Web Services](../samples/interoperating-with-asmx-web-services.md).</span></span>  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a><span data-ttu-id="5b853-113">WCF 클라이언트를 사용하여 WSE 3.0 웹 서비스에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="5b853-113">To access a WSE 3.0 Web service with a WCF client</span></span>  
  
1. <span data-ttu-id="5b853-114">[ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 실행 하 여 WSE 3.0 웹 서비스에 대 한 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-114">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="5b853-115">WSE 3.0 웹 서비스의 경우 WCF 클라이언트가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-115">For a WSE 3.0 Web service, a WCF client is created.</span></span> <span data-ttu-id="5b853-116">WSE 3.0이 MEX 프로토콜을 지원하지 않으므로 해당 도구를 사용하여 웹 서비스에 대한 보안 요구 사항을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-116">Because WSE 3.0 does not support the MEX protocol, you cannot use the tool to retrieve the security requirements for the Web service.</span></span> <span data-ttu-id="5b853-117">애플리케이션 개발자는 해당 클라이언트에 대한 보안 설정을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-117">The application developer must add the security settings for the client.</span></span>  
  
     <span data-ttu-id="5b853-118">WCF 클라이언트를 만드는 방법에 대 한 자세한 내용은 [방법: 클라이언트 만들기](../how-to-create-a-wcf-client.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5b853-118">For more information about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="5b853-119">WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-119">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="5b853-120">다음 클래스는 WSE 샘플과의 [상호 운용](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) 의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-120">The following class is part of the [Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) sample:</span></span>  
  
    1. <span data-ttu-id="5b853-121"><xref:System.ServiceModel.Channels.Binding> 클래스에서 파생되는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-121">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="5b853-122">다음 코드 예제에서는 `WseHttpBinding` 클래스로부터 파생되는 <xref:System.ServiceModel.Channels.Binding>이라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-122">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="5b853-123">WSE 서비스에서 사용되는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-123">Add properties to the class that specify the WSE turnkey assertion used by the WSE service, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span> <span data-ttu-id="5b853-124">WSE 3.0에서 턴키 어설션은 클라이언트 또는 웹 서비스에 대 한 보안 요구 사항을 지정 하며, WCF의 바인딩 인증 모드와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-124">In WSE 3.0, a turnkey assertion specifies the security requirements for a client or Web service—similar to the authentication mode of a binding in WCF.</span></span>  
  
         <span data-ttu-id="5b853-125">다음 코드 예제에서는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 각각 지정하는 `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` 및 `MessageProtectionOrder` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-125">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="5b853-126"><xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-126">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="5b853-127">다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-127">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="5b853-128">클라이언트 애플리케이션 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-128">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="5b853-129">다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션에 정의 된 대로 WCF 클라이언트가 메시지 보호 및 인증을 사용 하도록 지정 합니다 `AnonymousForCertificate` .</span><span class="sxs-lookup"><span data-stu-id="5b853-129">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="5b853-130">또한 보안 세션 및 파생된 키도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-130">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="5b853-131">예제</span><span class="sxs-lookup"><span data-stu-id="5b853-131">Example</span></span>  

 <span data-ttu-id="5b853-132">다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-132">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="5b853-133">그런 다음 이라는 사용자 지정 바인딩을 사용 하 여 `WseHttpBinding` WSSecurityAnonymous WSE 3.0 퀵 스타트 샘플과 통신 하는 WCF 클라이언트에 대 한 바인딩 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b853-133">That custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client that communicates with the WSSecurityAnonymous WSE 3.0 QuickStart sample.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5b853-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b853-134">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <span data-ttu-id="5b853-135">[WSE와 상호 운용](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="5b853-135">[Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span></span>
