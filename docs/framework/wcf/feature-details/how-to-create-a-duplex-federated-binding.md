---
title: '방법: 이중 페더레이션 바인딩 만들기'
ms.date: 03/30/2017
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
ms.openlocfilehash: 3ecd9e2dbeb30bb255cbf66488b50a9b20219431
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141723"
---
# <a name="how-to-create-a-duplex-federated-binding"></a>방법: 이중 페더레이션 바인딩 만들기

<xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청/응답 메시지 교환 계약만 지원합니다. 이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다. 다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다. 3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.

코드에서 바인딩을 만들 수도 있습니다. 만들 바인딩 요소 스택에 대 한 설명은 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조 하세요.

## <a name="to-create-a-duplex-federated-custom-binding-with-http"></a>HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. 구성 파일의 [\<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드에서 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만듭니다.

2. [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소 내에서 `name` 특성이 `FederationDuplexHttpMessageSecurityBinding`로 설정 된 [\<바인딩 >](../../configure-apps/file-schema/wcf/bindings.md) 요소를 만듭니다.

3. [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) 요소 내에서 `authenticationMode` 특성이 `SecureConversation`로 설정 된 [\<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만듭니다.

4. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 내에서 `authenticationMode` 특성이 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`로 설정 된 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 만듭니다.

5. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 다음에 빈 [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소를 만듭니다.

6. [\<compositeDuplex >](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소 다음에 빈 [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소를 만듭니다.

7. [\<oneWay >](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소 다음에 빈 [\<httptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 요소를 만듭니다.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-message-security-mode"></a>TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. 구성 파일의 [\<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드에서 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만듭니다.

2. [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소 내에서 `name` 특성이 `FederationDuplexTcpMessageSecurityBinding`로 설정 된 [\<바인딩 >](../../configure-apps/file-schema/wcf/bindings.md) 요소를 만듭니다.

3. [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) 요소 내에서 `authenticationMode` 특성이 `SecureConversation`로 설정 된 [\<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만듭니다.

4. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 내에서 `authenticationMode` 특성이 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`로 설정 된 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 만듭니다.

5. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 따라 빈 [\<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소를 만듭니다.

## <a name="to-create-a-duplex-federated-custom-binding-with-tcp-mixed-security-mode"></a>TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면

1. 구성 파일의 [\<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 노드에서 [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만듭니다.

2. [\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소 내에서 `name` 특성이 `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`로 설정 된 [\<바인딩 >](../../configure-apps/file-schema/wcf/bindings.md) 요소를 만듭니다.

3. [\<binding >](../../configure-apps/file-schema/wcf/bindings.md) 요소 내에서 `authenticationMode` 특성이 `SecureConversation`로 설정 된 [\<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만듭니다.

4. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 내에서 `authenticationMode` 특성이 `IssuedTokenForCertificate` 또는 `IssuedTokenForSslNegotiated`로 설정 된 [\<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소를 만듭니다.

5. [\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소에 따라 빈 [\<sslstreamsecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소를 만듭니다.

6. [\<sslStreamSecurity >](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소를 따라 빈 [\<tcptransport >](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소를 만듭니다.

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
