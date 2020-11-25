---
title: IReferenceAppId 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
ms.openlocfilehash: 9aa7173d81d84d9080d90b0890769ffeaee6a738
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728617"
---
# <a name="ireferenceappid-interface"></a>IReferenceAppId 인터페이스

현재 범위의 응용 프로그램에 대 한 고유 식별자에 대 한 참조를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|이에서 참조 하는 응용 프로그램의 코드 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId` .|  
|`IReferenceAppId::put_CodeBase`|이에서 참조 하는 응용 프로그램에 대 한 코드 식별자를 설정 합니다 `IReferenceAppId` .|  
|`IReferenceAppId::EnumAppPath`|`IEnumReferenceIdentity`이의 멤버를 나타내는 인스턴스를 포함 하는 인스턴스에 대 한 인터페이스 포인터를 가져옵니다 `IReferenceIdentity` `IReferenceAppId` .|  
|`IReferenceAppId::get_SubscriptionId`|이에 대 한 구독의 토큰 식별자에 대 한 문자열 표현에 대 한 포인터를 가져옵니다 `IReferenceAppId` .|  
|`IReferenceAppId::put_SubscriptionId`|이에 대 한 구독의 토큰 식별자를 `IReferenceAppId` 지정 된 문자열 값으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
- [IEnumReferenceIdentity 인터페이스](ienumreferenceidentity-interface.md)
- [IReferenceIdentity 인터페이스](ireferenceidentity-interface.md)
