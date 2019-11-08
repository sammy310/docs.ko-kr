---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736514"
---
# <a name="peertransport"></a>peerTransport > \<
사용자 지정 바인딩에 대한 피어 전송을 정의합니다.  
  
[ **\<configuration>** ](../configuration-element.md)\
[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; \
&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) >
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**peerTransport >**  
  
## <a name="syntax"></a>구문  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|listenIpAddress|피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다. 기본값은 `null`입니다.|  
|maxBufferPoolSize|버퍼 풀의 최대 크기를 지정하는 양의 정수입니다. 기본값은 524288입니다.<br /><br /> WCF의 많은 부분에서 버퍼를 사용 합니다. 사용 될 때마다 버퍼를 만들고 삭제 하는 것은 비용이 많이 들고 버퍼에 대 한 가비지 수집도 비용이 많이 듭니다. 버퍼 풀을 사용 하면 풀에서 버퍼를 가져와서 사용 하 고 완료 되 면 풀로 반환할 수 있습니다. 따라서 버퍼를 만들고 삭제 하는 오버 헤드는 피할 수 있습니다.|  
|maxReceivedMessageSize|헤더를 포함하는 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다. 수신자에게 너무 큰 메시지를 보내면 메시지의 발신자에게 SOAP 오류가 발생합니다. 수신자는 메시지를 삭제 하 고 추적 로그에 이벤트 항목을 만듭니다. 기본값은 65536입니다.|  
|포트|이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다. 이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다. 기본값은 0입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<security >](security-of-peertransport.md)|이 전송의 보안 설정을 정의합니다. 이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>주의  
 이 전송은 요청/회신 작업을 포함 하는 계약과 함께 사용할 수 없습니다.  
  
## <a name="see-also"></a>참조

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [전송](../../../wcf/feature-details/transports.md)
- [전송 선택](../../../wcf/feature-details/choosing-a-transport.md)
- [바인딩](../../../wcf/bindings.md)
- [바인딩 확장](../../../wcf/extending/extending-bindings.md)
- [사용자 지정 바인딩](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
