---
title: 사용자 이름 클라이언트를 사용하는 메시지 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 36335cb9-76b8-4443-92c7-44f081eabb21
ms.openlocfilehash: 9bcac0e45d44270d27a4cf04677e967a80e94b90
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550204"
---
# <a name="message-security-with-a-user-name-client"></a>사용자 이름 클라이언트를 사용하는 메시지 보안
다음 그림에서는 메시지 수준 보안을 사용 하 여 보호 되는 Windows Communication Foundation (WCF) 서비스 및 클라이언트를 보여 줍니다. 서비스는 X.509 인증서를 사용하여 인증됩니다. 클라이언트는 사용자 이름 및 암호를 사용하여 인증합니다.  
  
 응용 프로그램 예제는 [메시지 보안 사용자 이름](../samples/message-security-user-name.md)을 참조 하세요.  
  
 ![사용자 이름 인증을 사용하는 메시지 보안](media/1fb10a61-7e1d-42f5-b1af-195bfee5b3c6.gif "1fb10a61-7e1d-42f5-b1af-195bfee5b3c6")  
  
|특성|Description|  
|--------------------|-----------------|  
|보안 모드|메시지|  
|상호 운용성|Windows Communication Foundation (WCF)만|  
|인증(서버)|최초 협상에는 서버 인증이 필요합니다.|  
|인증(클라이언트)|사용자 이름/암호|  
|무결성|예, 공유 보안 컨텍스트 사용|  
|기밀성|예, 공유 보안 컨텍스트 사용|  
|전송|HTTP|  
|바인딩|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>서비스  
 다음 코드와 구성은 독립적으로 실행되어야 합니다. 다음 중 하나를 수행합니다.  
  
- 구성 없이 코드를 사용하여 독립 실행형 서비스를 만듭니다.  
  
- 제공된 구성을 사용하여 서비스를 만들지만 엔드포인트를 정의하지 않습니다.  
  
### <a name="code"></a>코드  
 다음 코드에서는 메시지 보안을 사용하는 서비스 엔드포인트를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[C_SecurityScenarios#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#9)]
 [!code-vb[C_SecurityScenarios#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#9)]  
  
### <a name="configuration"></a>구성  
 코드 대신 다음 구성을 사용할 수 있습니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"
                                storeLocation="LocalMachine"  
                                storeName="My"
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
                  bindingConfiguration="MessageAndUserName"  
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MessageAndUserName">  
          <security mode="Message">
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>클라이언트  
  
### <a name="code"></a>코드  
 다음 코드에서는 클라이언트를 만듭니다. 바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `UserName`로 설정됩니다. 사용자 이름 및 암호는 코드(구성할 수 없음)를 사용해서만 지정할 수 있습니다. 사용자 이름 및 암호를 반환할 코드는 애플리케이션 수준에서 수행되는 작업이기 때문에 여기에 표시되지 않습니다. 예를 들어 데이터에 대한 사용자를 쿼리하려면 Windows Forms 대화 상자를 사용합니다.  
  
 [!code-csharp[C_SecurityScenarios#16](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#16)]
 [!code-vb[C_SecurityScenarios#16](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#16)]  
  
### <a name="configuration"></a>구성  
 다음 코드에서는 클라이언트를 구성합니다. 바인딩은 메시지 모드 보안으로 설정되며 클라이언트 자격 증명 형식은 `UserName`로 설정됩니다. 사용자 이름 및 암호는 코드(구성할 수 없음)를 사용해서만 지정할 수 있습니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value ="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>참조

- [보안 개요](security-overview.md)
- [Message Security User Name](../samples/message-security-user-name.md)
- [서비스 ID 및 인증](service-identity-and-authentication.md)
- [\<identity>](../../configure-apps/file-schema/wcf/identity.md)
- [Windows Server AppFabric 보안 모델](/previous-versions/appfabric/ee677202(v=azure.10))
