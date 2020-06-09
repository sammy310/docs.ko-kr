---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: e93651ce9fe9dae55c299fcb061da6bdc4b6bc5e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598972"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>방법: 이중 페더레이션 바인딩 만들기

<xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다. 이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다. 다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다. 3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.

코드에서 바인딩을 만들 수도 있습니다. 만들 바인딩 요소 스택에 대 한 설명은 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조 하세요.

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .

2. 요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexHttpMessageSecurityBinding` .

3. 요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .

4. 요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. 요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) .

6. 요소 뒤 [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) 에 빈 요소를 만듭니다 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) .

7. 요소 뒤 [\<oneWay>](../../configure-apps/file-schema/wcf/oneway.md) 에 빈 요소를 만듭니다 [\<httpTransport>](../../configure-apps/file-schema/wcf/httptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .

2. 요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpMessageSecurityBinding` .

3. 요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .

4. 요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. 요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md)구성 파일의 노드에서 요소를 만듭니다 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .

2. 요소 내 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) 에서 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 특성이로 설정 된 요소를 만듭니다 `name` `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` .

3. 요소 내 [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) 에서 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 특성이로 설정 된 요소를 만듭니다 `authenticationMode` `SecureConversation` .

4. 요소 내 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에서 [\<secureConversationBootstrap>](../../configure-apps/file-schema/wcf/secureconversationbootstrap.md) `authenticationMode` 특성이 또는로 설정 된 요소를 만듭니다 `IssuedTokenForCertificate` `IssuedTokenForSslNegotiated` .

5. 요소 뒤 [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) 에 빈 요소를 만듭니다 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) .

6. 요소 뒤 [\<sslStreamSecurity>](../../configure-apps/file-schema/wcf/sslstreamsecurity.md) 에 빈 요소를 만듭니다 [\<tcpTransport>](../../configure-apps/file-schema/wcf/tcptransport.md) .

## <a name="code-sample"></a>코드 예제

### <a name="sample-with-3-bindings"></a>3개의 바인딩에 대한 샘플

1. 구성 파일에 다음 코드를 삽입합니다.

## <a name="example"></a>예제

```xml
<bindings>
   <customBinding>
      <binding name="FederationDuplexHttpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <compositeDuplex />
          <oneWay />
          <httpTransport />
       </binding>
<!-- duplex over https is not supported -->
       <binding name="FederationDuplexTcpMessageSecurityBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />
          </security>
          <tcpTransport />
       </binding>
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">
<!-- duplex contract requires secure conversation with require cancellation = true -->
          <security authenticationMode="SecureConversation">
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />
          </security>
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->
          <sslStreamSecurity />
          <tcpTransport />
       </binding>
    </customBinding>
</bindings>
```
