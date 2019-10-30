---
title: 'ICorDebugType2:: GetTypeID 메서드'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 944313893d88b8eff97291d2517e4863a5ae958a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092759"
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2:: GetTypeID 메서드
이 형식에 대 한 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `id`  
 제한이 이 ICorDebugType에 대 한 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다. `HRESULT` 코드는 다음과 같습니다.  
  
|반환 코드|설명|  
|-----------------|-----------------|  
|`S_OK`|메서드가 정상적으로 실행되었습니다. 메서드가 유효한 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)을 검색 했습니다.|  
|`CORDBG_E_CLASS_NOT_LOADED`|형식이 로드 되지 않았습니다.|  
|`CORDBG_E_UNSUPPORTED`|지원 되지 않는 형식입니다.|  
  
## <a name="remarks"></a>주의  
 이 메서드는 런타임으로 로드 될 수도 있고, 런타임에 로드 된 형식을 식별 하는 불투명 핸들 역할을 하는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)에 대 한 ICorDebugType의 매핑을 제공 합니다.  
  
 ICorDebugType가 나타내는 형식이 아직 로드 되지 않은 경우이 메서드는 `CORDBG_E_CLASS_NOT_LOADED`반환 합니다.  형식이 지원 되지 않는 경우 `CORDBG_E_UNSUPPORTED`반환 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugType2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
