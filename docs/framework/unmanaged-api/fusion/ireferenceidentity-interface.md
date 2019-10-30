---
title: IReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127062"
---
# <a name="ireferenceidentity-interface"></a>IReferenceIdentity 인터페이스
코드 개체의 고유 서명에 대 한 참조를 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|지정 된 특성이 변경 되는 경우를 제외 하 고이 `IReferenceIdentity`와 동일한 새 `IReferenceIdentity` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IReferenceIdentity::EnumAttributes`|이 `IReferenceIdentity`와 연결 된 특성을 포함 하는 `IEnumIDENTITY_ATTRIBUTE` 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.|  
|`IReferenceIdentity::GetAttribute`|지정 된 이름을 사용 하 여 지정 된 네임 스페이스에 있는 특성의 값을 가져옵니다.|  
|`IReferenceIdentity::SetAttribute`|지정 된 네임 스페이스와 지정 된 이름을 가진 특성을 지정 된 값으로 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** 격리. h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [Fusion 인터페이스](fusion-interfaces.md)
- [IEnumIDENTITY_ATTRIBUTE 인터페이스](ienumidentity-attribute-interface.md)
