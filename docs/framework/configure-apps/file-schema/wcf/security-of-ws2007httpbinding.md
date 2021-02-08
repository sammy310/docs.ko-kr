---
description: '다음에 대 한 자세한 정보:: <security><ws2007HttpBinding>'
title: <ws2007HttpBinding>의 <security>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: ef8b82d34b318db79db061b9c01b147e619d39c4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786813"
---
# <a name="security-of-ws2007httpbinding"></a>\<ws2007HttpBinding>의 \<security>

요소에 사용 되는 보안 설정을 나타냅니다 [\<ws2007HttpBinding>](ws2007httpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|`mode`|필드. 적용되는 보안 형식을 지정합니다. 기본값은 `Message`입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.|  
  
## <a name="mode-attribute"></a>Mode 특성  
  
|값|설명|  
|-----------|-----------------|  
|`None`|보안이 해제되어 있습니다.|  
|`Transport`|HTTPS를 사용하여 보안이 제공됩니다. SSL(Secure Sockets Layer) 인증서를 사용하여 서비스를 구성해야 합니다. 메시지는 HTTPS를 사용하여 완전하게 보안 처리되며, 서비스는 서비스의 SSL 인증서를 사용하여 클라이언트에 의해 인증됩니다. 클라이언트 인증은 요소의 특성을 통해 제어 됩니다 `ClientCredentials` [\<transport>](transport-of-ws2007httpbinding.md) .|  
|`Message`|SOAP 메시지 보안을 사용하여 보안이 제공됩니다. 기본적으로 SOAP 본문은 암호화되고 서명됩니다. 이 모드는 서비스 자격 증명을 out-of-band 클라이언트에서 사용할 수 있는지 여부, 사용할 알고리즘 모음 및 <xref:System.ServiceModel.Security.SecurityMessageProperty>를 통해 메시지 본문에 적용할 보호 수준과 같은 다양한 기능을 제공합니다. 클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.|  
|`TransportWithMessageCredential`|이 모드에서 HTTPS는 무결성, 기밀성 및 서버 인증을 제공하고 SOAP 메시지 보안은 클라이언트 인증을 제공합니다. 기본적으로 클라이언트 인증은 각 세션에 대해 한 번씩 수행되며 세션 기간 동안 인증 결과가 캐시됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|전송 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> 형식에 해당합니다. 이 설정은 모드를 Transport로 설정한 경우에만 적용됩니다.|  
|[\<message>](message-of-ws2007httpbinding.md)|메시지에 대한 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> 형식에 해당합니다. 이 설정은 모드를 Transport로 설정한 경우에 적용되지 않습니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|HTTP 전송 애플리케이션에 대한 보안 바인딩입니다.|  
  
## <a name="remarks"></a>설명  

 이 요소는 WS-* 사양을 구현하는 서비스와 상호 운용하도록 디자인되었습니다. 이 바인딩의 전송 보안은 HTTP 또는 SSL(Secure Sockets Layer) over HTTP입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [서비스 및 클라이언트에 보안 설정](../../../wcf/feature-details/securing-services-and-clients.md)
- [바인딩](../../../wcf/bindings.md)
- [시스템 제공 바인딩 구성](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
