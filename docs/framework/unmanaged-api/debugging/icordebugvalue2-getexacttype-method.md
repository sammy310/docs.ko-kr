---
title: ICorDebugValue2::GetExactType 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03d701d0801c55b6e91600f0767a6d737e4915c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479950"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType 메서드
인터페이스 포인터를 나타내는 "ICorDebugType" 개체를 가져옵니다는 <xref:System.Type> 이 값의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `ppType`  
 [out] 주소에 대 한 포인터를 `ICorDebugType` 나타내는 개체를 <xref:System.Type> 이 "ICorDebugValue2" 개체를 나타내는 값입니다.  
  
## <a name="remarks"></a>설명  
 제네릭 인식 `GetExactType` 메서드를 둘 다 대체를 [icordebugobjectvalue:: Getclass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) 하며 [icordebugvalue:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) 메서드를 각 값의 형식에 대 한 정보는 반환 .  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

