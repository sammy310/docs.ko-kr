---
title: <add>의 <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 5c9937cb6302a194228461f3e2e06ecdf4d43269
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377757"
---
# <a name="add-of-issuerchannelbehaviors"></a>\<추가 >의 \<issuerChannelBehaviors >

STS와 통신할 때 사용할 엔드포인트 동작을 추가합니다.

> [!NOTE]
> 끝점 동작을 포함 하는 경우는 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에서 예외가 throw 됩니다.

\<system.ServiceModel>\
\<behaviors>\
endpointBehaviors 섹션 \<동작 > \
\<clientCredentials>\
\<issuedToken>\
\<issuerChannelBehaviors > Element\
\<add>

## <a name="syntax"></a>구문

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|issuerAddress|통신할 보안 토큰 발급자의 URI입니다.|
|behaviorConfiguration|동일한 구성 파일에 정의된 엔드포인트 동작 이름입니다.|

### <a name="child-elements"></a>자식 요소

없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|지정한 서비스 토큰 서비스와 통신할 때 사용 되는 Windows Communication Foundation (WCF) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.|

## <a name="remarks"></a>설명

`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다. `behaviorConfiguration` 응용 프로그램 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 Windows Communication Foundation (WCF)에서 만든 채널에서 사용 하는 끝점 동작을 가리킵니다.

## <a name="see-also"></a>참고자료

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
- [방법: 페더레이션된 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
