---
title: '방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
ms.openlocfilehash: 847146c2025612689f0d69cc0c23d2be14018c0f
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556839"
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a>방법: WCF 클라이언트를 사용하여 WSE 3.0 서비스에 액세스
Wcf 클라이언트가 WS-ADDRESSING 사양의 8 2004 월 버전을 사용 하도록 구성 된 경우 WCF (Windows Communication Foundation) 클라이언트는 Microsoft .NET 서비스에 대해 WSE (Web Services 향상 된) 3.0의 유선 수준으로 호환 됩니다. 그러나 WSE 3.0 서비스는 MEX (metadata exchange) 프로토콜을 지원 하지 않으므로 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 wcf 클라이언트 클래스를 만들 때 생성 된 wcf 클라이언트에는 보안 설정이 적용 되지 않습니다. 따라서 WCF 클라이언트가 생성 된 후 WSE 3.0 서비스에서 요구 하는 보안 설정을 지정 해야 합니다.  
  
 Wse 3.0 서비스와 WCF 클라이언트 간의 상호 운용 가능한 요구 사항 및 WSE 3.0 서비스의 요구 사항을 고려 하 여 사용자 지정 바인딩을 사용 하 여 이러한 보안 설정을 적용할 수 있습니다. 이러한 상호 운용성 요구 사항에는 앞에서 말한 August 2004 WS-Addressing 사양 및 WSE 3.0의 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> 기본 메시지 보호를 사용하는 것이 포함됩니다. WCF에 대 한 기본 메시지 보호는 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature> 입니다. 이 항목에서는 WSE 3.0 서비스와 상호 작용 하는 WCF 바인딩을 만드는 방법에 대해 자세히 설명 합니다. WCF는이 바인딩을 통합 하는 샘플도 제공 합니다. 이 샘플에 대 한 자세한 내용은 [ASMX 웹 서비스와 상호 운용](../samples/interoperating-with-asmx-web-services.md)을 참조 하세요.  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a>WCF 클라이언트를 사용하여 WSE 3.0 웹 서비스에 액세스하려면  
  
1. [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) 를 실행 하 여 WSE 3.0 웹 서비스에 대 한 WCF 클라이언트를 만듭니다.  
  
     WSE 3.0 웹 서비스의 경우 WCF 클라이언트가 생성 됩니다. WSE 3.0이 MEX 프로토콜을 지원하지 않으므로 해당 도구를 사용하여 웹 서비스에 대한 보안 요구 사항을 검색할 수 없습니다. 애플리케이션 개발자는 해당 클라이언트에 대한 보안 설정을 추가해야 합니다.  
  
     WCF 클라이언트를 만드는 방법에 대 한 자세한 내용은 [방법: 클라이언트 만들기](../how-to-create-a-wcf-client.md)를 참조 하세요.  
  
2. WSE 3.0 웹 서비스와 통신할 수 있는 바인딩을 나타내는 클래스를 만듭니다.  
  
     다음 클래스는 WSE 샘플과의 [상호 운용](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) 의 일부입니다.  
  
    1. <xref:System.ServiceModel.Channels.Binding> 클래스에서 파생되는 클래스를 만듭니다.  
  
         다음 코드 예제에서는 `WseHttpBinding` 클래스로부터 파생되는 <xref:System.ServiceModel.Channels.Binding>이라는 클래스를 만듭니다.  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. WSE 서비스에서 사용되는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 지정하는 클래스에 속성을 추가합니다. WSE 3.0에서 턴키 어설션은 클라이언트 또는 웹 서비스에 대 한 보안 요구 사항을 지정 하며, WCF의 바인딩 인증 모드와 유사 합니다.  
  
         다음 코드 예제에서는 WSE 턴키 어설션, 파생된 키가 필요한지 여부, 보안 세션이 사용되는지 여부, 서명 확인이 필요한지 여부 및 메시지 보호 설정을 각각 지정하는 `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext` 및 `MessageProtectionOrder` 속성을 정의합니다.  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 메서드를 재정의하여 바인딩 속성을 설정합니다.  
  
         다음 코드 예제에서는 `SecurityAssertion` 및 `MessageProtectionOrder` 속성의 값을 가져옴으로써 전송, 메시지 인코딩, 메시지 보호 설정을 지정합니다.  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. 클라이언트 애플리케이션 코드에서 바인딩 속성을 설정하기 위해 코드를 추가합니다.  
  
     다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션에 정의 된 대로 WCF 클라이언트가 메시지 보호 및 인증을 사용 하도록 지정 합니다 `AnonymousForCertificate` . 또한 보안 세션 및 파생된 키도 필요합니다.  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 WSE 3.0 턴키 보안 어설션의 속성에 해당하는 속성을 노출하는 사용자 지정 바인딩을 정의합니다. 그런 다음 이라는 사용자 지정 바인딩을 사용 하 여 `WseHttpBinding` WSSecurityAnonymous WSE 3.0 퀵 스타트 샘플과 통신 하는 WCF 클라이언트에 대 한 바인딩 속성을 지정 합니다.  

## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Channels.Binding>
- [WSE와 상호 운용](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))
