---
description: '다음에 대 한 자세한 정보:: <transport><peerTransport>'
title: <peerTransport>의 <transport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: ba3405c5dfadb513f92ebd537409a3f7b12fa291
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664511"
---
# <a name="transport-of-peertransport"></a>\<peerTransport>의 \<transport>

이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>구문  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  

 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|attribute|설명|  
|---------------|-----------------|  
|credentialType|선택 사항입니다. 피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다. 이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.|  
  
## <a name="credentialtype-attribute"></a>credentialType 특성  
  
|값|설명|  
|-----------|-----------------|  
|인증서|피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.|  
|암호|피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.|  
  
### <a name="child-elements"></a>자식 요소  

 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|피어 전송의 보안 설정을 정의합니다.|  
  
## <a name="remarks"></a>설명  

 이 요소는의 mode 특성이 또는로 설정 된 경우에만 설정 됩니다 [\<security>](security-of-peertransport.md) `Transport` `TransportWithMessageCredential` .  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [전송 보안](../../../wcf/feature-details/transport-security.md)
- [전송](../../../wcf/feature-details/transports.md)
- [전송 선택](../../../wcf/feature-details/choosing-a-transport.md)
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장명](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
