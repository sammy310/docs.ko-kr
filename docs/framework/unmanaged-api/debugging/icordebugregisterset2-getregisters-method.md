---
title: ICorDebugRegisterSet2::GetRegisters 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegisters
helpviewer_keywords:
- GetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegisters method [.NET Framework debugging]
ms.assetid: dbc498a8-ba3f-42f2-bdd9-b623c77a1019
topic_type:
- apiref
ms.openlocfilehash: 8e5583acfe338c185200c0b8e41b7d6e051fa146
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131349"
---
# <a name="icordebugregisterset2getregisters-method"></a>ICorDebugRegisterSet2::GetRegisters 메서드
지정 된 비트 마스크로 지정 된 각 레지스터의 값 (코드가 현재 실행 중인 플랫폼의 경우)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [out, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `maskCount`  
 진행 `mask` 배열의 크기 (바이트)입니다.  
  
 `mask`  
 진행 각 비트가 레지스터에 해당 하는 바이트 배열입니다. 비트가 1 이면 해당 레지스터의 값이 검색 됩니다.  
  
 `regCount`  
 진행 검색할 레지스터 값의 수입니다.  
  
 `regBuffer`  
 제한이 각각 레지스터의 값을 수신 하는 `CORDB_REGISTER` 개체의 배열입니다.  
  
## <a name="remarks"></a>주의  
 `GetRegisters` 메서드는 마스크로 지정 된 레지스터에서 값의 배열을 반환 합니다. 배열에 해당 마스크 비트가 설정 되지 않은 레지스터의 값이 없습니다. 따라서 `regBuffer` 배열의 크기는 마스크에 있는 1의 수와 같아야 합니다. 마스크가 나타내는 레지스터 수에 대해 `regCount` 값이 너무 작으면 집합에서 더 높은 숫자의 레지스터 값이 잘립니다. `regCount` 너무 크면 사용 하지 않는 `regBuffer` 요소가 수정 되지 않습니다.  
  
 사용할 수 없는 레지스터가 마스크로 표시 되 면 해당 레지스터에 대해 결정 되지 않은 값이 반환 됩니다.  
  
 `ICorDebugRegisterSet2::GetRegisters` 메서드는 레지스터가 64 개를 초과 하는 플랫폼에 필요 합니다. 예를 들어 IA64에는 128 범용 레지스터와 128 부동 소수점 레지스터가 있으므로 비트 마스크에 64 비트 이상이 필요 합니다.  
  
 64 개 이상의 레지스터가 있는 경우 x 86과 같은 플랫폼의 경우 처럼 `GetRegisters` 메서드는 실제로 `mask` 바이트 배열의 바이트를 `ULONG64` 변환한 다음 [ICorDebugRegisterSet:: GetRegisters](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregisters-method.md) 메서드를 호출 합니다. 는 `ULONG64` 마스크를 사용 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
