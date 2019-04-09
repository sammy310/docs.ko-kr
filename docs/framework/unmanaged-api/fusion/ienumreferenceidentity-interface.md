---
title: IEnumReferenceIdentity 인터페이스
ms.date: 03/30/2017
api_name:
- IEnumReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumReferenceIdentity
helpviewer_keywords:
- IEnumReferenceIdentity interface [.NET Framework fusion]
ms.assetid: a17b3155-7216-4e16-8c9f-abce21f549e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 766b17bae0c58d9872ff9c118f330ebc3220257e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123489"
---
# <a name="ienumreferenceidentity-interface"></a>IEnumReferenceIdentity 인터페이스
컬렉션의 열거자 역할을 `IReferenceIdentity` 개체입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|`IEnumReferenceIdentity::Clone`|새 인터페이스 포인터를 가져옵니다 `IEnumReferenceIdentity` 이 동일한 멤버를 포함 하는 `IEnumReferenceIdentity`합니다.|  
|`IEnumReferenceIdentity::Next`|지정 된 수를 가져옵니다 `IReferenceIdentity` 개체를 현재 위치에서 시작 합니다.|  
|`IEnumReferenceIdentity::Reset`|이 부분에 명령 포인터를 이동 `IEnumReferenceIdentity`합니다.|  
|`IEnumReferenceIdentity::Skip`|요소를 현재 위치부터 지정한 수 만큼 앞으로 명령 포인터를 이동 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** Isolation.h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [Fusion 인터페이스](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [IReferenceIdentity 인터페이스](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
