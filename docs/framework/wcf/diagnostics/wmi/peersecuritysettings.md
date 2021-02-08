---
description: '자세한 정보: PeerSecuritySettings'
title: PeerSecuritySettings
ms.date: 03/30/2017
ms.assetid: 24ae0d35-f3a3-419b-afd6-686e22aae27b
ms.openlocfilehash: a8b5b8c88e71cb46110fa35186599c0f9c366d17
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803011"
---
# <a name="peersecuritysettings"></a>PeerSecuritySettings

PeerSecuritySettings  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class PeerSecuritySettings  
{  
  string Mode;  
  PeerTransportSecuritySettings Transport;  
};  
```  
  
## <a name="methods"></a>메서드  

 PeerSecuritySettings 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  

 PeerSecuritySettings 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="mode"></a>모드  

 데이터 형식: 문자열  
  
 액세스 형식: 읽기 전용  
  
 바인딩으로 구성된 엔드포인트가 메시지 수준 보안을 사용하는지 또는 전송 수준 보안을 사용하는지 여부입니다.  
  
### <a name="transport"></a>전송  

 데이터 형식: PeerTransportSecuritySettings  
  
 액세스 형식: 읽기 전용  
  
 전송 보안 설정입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목

- <xref:System.ServiceModel.PeerSecuritySettings>
