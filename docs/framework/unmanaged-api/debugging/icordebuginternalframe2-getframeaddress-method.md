---
title: ICorDebugInternalFrame2::GetFrameAddress 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 40e64bdb35cff4e6ad6132c0806cfddd2767443c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122682"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a>ICorDebugInternalFrame2::GetFrameAddress 메서드
내부 프레임의 스택 주소를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAddress`  
 제한이 내부 프레임의 `CORDB_ADDRESS`에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|내부 프레임의 주소가 성공적으로 반환 되었습니다.|  
|E_FAIL|내부 프레임의 주소를 반환할 수 없습니다.|  
|E_INVALIDARG|`pAddress`가 `null`입니다.|  
  
## <a name="remarks"></a>주의  
 `pAddress`에서 반환 된 값을 사용 하 여 스택의 다른 프레임을 기준으로 내부 프레임의 위치를 결정할 수 있습니다. IA-64 기반 컴퓨터의 경우에도 내부 프레임은 스택에만 있고 백업 저장소에는 해당 하는 포인터가 없습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugInternalFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
