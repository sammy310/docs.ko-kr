---
description: '자세히 알아보기: 변조'
title: 변조
ms.date: 03/30/2017
ms.assetid: 3bad93be-60bb-4f89-96ab-a1c3dc7c0fad
ms.openlocfilehash: 3b14fef66e5c98737d8d2f6a8b889f16c83020f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793326"
---
# <a name="tampering"></a>변조

*변조* 는 메시지를 변경 하거나 메시지를 배달 하는 작업과 변경 된 메시지를 사용 하는 것 외의 목적으로 변경 된 메시지를 사용 하는 행위입니다.  
  
## <a name="do-not-disable-ws-addressing"></a>WS-Addressing 활성화  

 WS-Addressing 사양은 각 메시지에 대한 주소 헤더를 제공하여 메시지 받는 사람이 메시지를 보낸 사람을 확인할 수 있습니다. <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성을 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>으로 설정하여 이 기능을 비활성화할 수 있습니다.  
  
 보안 모드를 메시지로 설정하는 경우 WS-Addressing을 사용하지 않도록 설정하면 공격자가 클라이언트에서 요청을 가져와 다른 서비스에 보낼 수 있으며 두 번째 서비스는 메시지가 원래 클라이언트에서 전송되었는지를 검색할 수 없습니다. 실제로 첫 번째 서비스는 두 번째 서비스와 통신할 때 클라이언트인 것처럼 가장할 수 있습니다.  
  
 이러한 문제를 줄이려면 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성을 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>으로 설정하지 않고 <xref:System.ServiceModel.Channels.MessageVersion> 속성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12%2A>로 설정하는 정적 <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> 속성과 같이 <xref:System.ServiceModel.Channels.AddressingVersion.None%2A>을 사용하지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [Security Considerations](security-considerations-in-wcf.md)
- [정보 공개](information-disclosure.md)
- [권한 상승](elevation-of-privilege.md)
- [서비스 거부](denial-of-service.md)
- [지원 되지 않는 시나리오](unsupported-scenarios.md)
- [재생 공격](replay-attacks.md)
