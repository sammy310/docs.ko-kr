---
title: '방법: 클라이언트 자격 증명 값 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 2417c2dd16224d6cbf00d3f1f4a8958420830b6c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319857"
---
# <a name="how-to-specify-client-credential-values"></a>방법: 클라이언트 자격 증명 값 지정

WCF (Windows Communication Foundation)를 사용 하 여 서비스는 클라이언트를 서비스에 인증 하는 방법을 지정할 수 있습니다. 예를 들면 서비스는 클라이언트가 인증서를 사용하여 인증하도록 규정할 수 있습니다.

## <a name="to-determine-the-client-credential-type"></a>클라이언트 자격 증명 형식을 결정하려면

1. 서비스의 메타데이터 엔드포인트에서 메타데이터를 검색합니다. 메타데이터는 보통 사용자가 선택한 프로그래밍 언어로 된 클라이언트 코드(기본적으로 Visual C#)와 XML 구성 파일의 두 파일로 구성됩니다. 메타데이터를 검색하는 방법 중 하나는 Svcutil.exe 도구를 사용해 클라이언트 코드와 클라이언트 구성을 반환하는 것입니다. 자세한 내용은 [메타 데이터 검색](./feature-details/retrieving-metadata.md) 및 [ServiceModel metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)를 참조 하세요.

2. XML 구성 파일을 엽니다. Svcutil.exe 도구를 사용하는 경우 이 파일의 기본 이름은 Output.config입니다.

3. **Mode** 특성을 사용 하 여 **\<security >** 요소를 찾습니다 ( **\<security mode =** `MessageOrTransport` **>** 는 보안 모드 중 하나로 설정 됩니다.

4. 모드 값과 일치하는 자식 요소를 찾습니다. 예를 들어 모드가 **Message**로 설정 된 경우 **\<security >** 요소에 포함 된 **\<message >** 요소를 찾습니다.

5. **ClientCredentialType** 특성에 할당 된 값을 확인 합니다. 실제 값은 사용하는 모드(Transport/Message)에 따라 다릅니다.

다음 XML 코드는 메시지 보안을 사용하며 인증서를 사용해 클라이언트를 인증하도록 하는 클라이언트의 구성을 보여 줍니다.

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>예제: 인증서를 클라이언트 자격 증명으로 사용하는 TCP Transport 모드

이 예제에서는 보안 모드를 Transport 모드로 설정하고 클라이언트 자격 증명 값을 X.509 인증서로 설정합니다. 다음 절차에서는 코드와 구성에 클라이언트에 대한 클라이언트 자격 증명 값을 설정하는 방법을 보여 줍니다. 여기서는 [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스에서 메타 데이터 (코드 및 구성)를 반환 했다고 가정 합니다. 자세한 내용은 [방법: 클라이언트 만들기](how-to-create-a-wcf-client.md)를 참조 하세요.

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>코드에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면

1. [ServiceModel Metadata 유틸리티 도구 (svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) 를 사용 하 여 서비스에서 코드 및 구성을 생성 합니다.

2. 생성 된 코드를 사용 하 여 WCF 클라이언트의 인스턴스를 만듭니다.

3. 클라이언트 클래스에서 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 클래스의 <xref:System.ServiceModel.ClientBase%601> 속성을 적절한 값으로 설정합니다. 이 예제에서는 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 클래스의 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> 메서드를 사용하여 속성을 X.509 인증서로 설정합니다.

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <xref:System.Security.Cryptography.X509Certificates.X509FindType> 클래스의 열거를 사용할 수 있습니다. 주체 이름은 만료 날짜로 인해 인증서가 변경된 경우 여기서 사용됩니다. 주체 이름을 사용하면 인프라에서 인증서를 다시 찾을 수 있습니다.

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>구성에 클라이언트에 대한 클라이언트 자격 증명 값을 지정하려면

1. [@No__t_3behaviors >](../configure-apps/file-schema/wcf/behaviors.md) 요소에 [\<behavior >](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 요소를 추가 합니다.

2. [@No__t_3behaviors >](../configure-apps/file-schema/wcf/behaviors.md) 요소에 [\<clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) 요소를 추가 합니다. 필수 `name` 특성을 적절한 값으로 설정해야 합니다.

3. [@No__t_3clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) 요소에 [\<clientCertificate >](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) 요소를 추가 합니다.

4. 다음 코드에서처럼 `storeLocation`, `storeName`, `x509FindType` 및 `findValue` 특성을 적절한 값으로 설정합니다. 자세한 내용은 [인증서 작업](./feature-details/working-with-certificates.md)을 참조하세요.

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

5. 클라이언트를 구성할 때 다음 코드에서처럼 `behaviorConfiguration` 요소의 `<endpoint>` 특성을 설정하여 동작을 지정합니다. 끝점 요소는 [\<client >](../configure-apps/file-schema/wcf/client.md) 요소의 자식입니다. 또한 `bindingConfiguration` 특성을 클라이언트에 대한 바인딩으로 설정하여 바인딩 구성 이름을 지정합니다. 생성된 구성 파일을 사용하는 경우 바인딩의 이름이 자동으로 생성됩니다. 이 예제에서는 이름이 `"tcpBindingWithCredential"`입니다.

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a>참조

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [WCF 보안 프로그래밍](./feature-details/programming-wcf-security.md)
- [자격 증명 형식 선택](./feature-details/selecting-a-credential-type.md)
- [ServiceModel Metadata 유틸리티 도구(Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [인증서 작업](./feature-details/working-with-certificates.md)
- [방법: 클라이언트 만들기](how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security >](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<message >](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior >](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors >](../configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate >](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md)
