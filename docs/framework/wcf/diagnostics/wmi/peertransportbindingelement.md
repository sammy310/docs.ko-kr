---
description: '자세한 정보: PeerTransportBindingElement'
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: b1ca8020f51a5f9b121f7d238d82b9971d13cdd4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757334"
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement

PeerTransportBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>메서드  

 PeerTransportBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 PeerTransportBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="listenipaddress"></a>ListenIPAddress  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 피어 노드가 메시지를 수신하는 IP 주소입니다.  
  
### <a name="port"></a>포트  

 데이터 형식: sint32  
  
 액세스 형식: 읽기 전용  
  
 이 바인딩이 피어 채널 메시지를 처리할 네트워크 인터페이스 포트입니다.  
  
### <a name="security"></a>보안  

 데이터 형식: PeerSecuritySettings  
  
 액세스 형식: 읽기 전용  
  
 피어 전송 보안 설정입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
