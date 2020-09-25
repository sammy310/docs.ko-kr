---
title: <netTcpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: 286cd191-4fd5-4c4e-a223-9c71cf7fdead
ms.openlocfilehash: d39e3e5e655817aa91c5301274a860a00a6ab7ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169988"
---
# <a name="security-of-nettcpbinding"></a>\<netTcpBinding>의 \<security>

바인딩에 대한 보안 설정을 정의합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             protectionLevel="None/Sign/EncryptAndSign" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|mode|선택 사항입니다. 적용되는 보안 형식을 지정합니다. 유효한 값이 아래에 나와 있습니다. 기본값은 `Transport`입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.|  
  
## <a name="mode-attribute"></a>mode 특성  
  
|Value|설명|  
|-----------|-----------------|  
|없음|보안이 해제되어 있습니다.|  
|전송|전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공됩니다. 서비스는 SSL 인증서로 구성해야 할 수도 있습니다. 이 모드에서는 보호 수준을 제어할 수 있습니다.|  
|메시지|SOAP 메시지 보안을 사용하여 보안이 제공됩니다. 기본적으로 SOAP 본문은 암호화되고 서명됩니다. 이 모드는 서비스 자격 증명을 클라이언트에서 밴드 외 방식으로 사용할 수 있는지 여부, 사용할 알고리즘 모음, 메시지 본문에 적용될 보호 수준과 같은 다양한 기능을 제공합니다. 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.|  
|TransportWithMessageCredential|전송 보안이 메시지 보안과 결합되어 있습니다. 전송 보안은 TCP를 통한 TLS 또는 SPNego를 사용하여 제공되며 무결성, 기밀성 및 서버 인증을 보장합니다. SOAP 메시지 보안에서는 클라이언트 인증이 제공됩니다. 기본적으로 클라이언트 인증은 세션당 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시에 저장됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<transport>](transport-of-nettcpbinding.md)|전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.TcpTransportSecurityElement> 형식입니다.|  
|[\<message>](message-element-of-nettcpbinding.md)|메시지에 대한 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverTcpElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|바인딩|의 바인딩 요소 [\<netTcpBinding>](nettcpbinding.md) 입니다.|  
  
## <a name="remarks"></a>설명  

 각 표준 바인딩은 전송 보안 요구 사항을 제어 하기 위한 매개 변수를 제공 합니다. 이러한 매개 변수에는 일반적으로 메시지 수준 또는 전송 수준 보안이 사용 되는지 여부와 선택 된 클라이언트 자격 증명 형식을 지정 하는 보안 모드가 포함 됩니다. 이러한 매개 변수가 제공 하는 옵션에 따라 적절 한 보안을 사용 하 여 채널 스택이 생성 됩니다.  
  
 WCF (Windows Communication Foundation)에서 제공 하는 시스템 제공 바인딩은 가장 일반적인 시나리오 요구 사항 중 일부를 충족 하도록 설계 된 집합입니다. 이러한 각 바인딩은 특정 대상 시나리오에 대 한 보안 요구 사항을 지정할 수 있습니다.  
  
 이 구성 요소는 `netTcpBinding`의 보안 사양을 제공합니다. 이는 시스템 간 통신에 적합 한 안전 하 고 신뢰할 수 있으며 최적화 된 바인딩입니다. 기본적으로 메시지 배달을 위한 TCP, 메시지 보안 및 인증을 위한 Windows 보안, 안정성을 위한 WS-Reliable Messaging 및 이진 메시지 인코딩을 지원하는 런타임 통신 스택을 생성합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.NetTcpSecurity>
- <xref:System.ServiceModel.NetTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [바인딩하](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
