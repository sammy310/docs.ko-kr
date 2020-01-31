---
title: ICorDebugRegisterSet::GetRegistersAvailable 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: b137b956e06a2b2954918e4024860f9b234e7583
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792102"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a>ICorDebugRegisterSet::GetRegistersAvailable 메서드
이 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 에서 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pAvailable`  
 제한이 현재 사용할 수 있는 레지스터를 나타내는 비트 마스크입니다.  
  
## <a name="remarks"></a>주의  
 지정 된 상황에 대해 해당 값을 확인할 수 없는 경우에는 레지스터를 사용할 수 없습니다.  
  
 반환 된 마스크에는 각 레지스터의 비트 (1 < 레지스터 인덱스 <)가 포함 됩니다. 레지스터를 사용할 수 있으면 비트 값은 1이 고, 사용할 수 없는 경우 0입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugRegisterSet 인터페이스](icordebugregisterset-interface.md)
- [ICorDebugRegisterSet2 인터페이스](icordebugregisterset2-interface.md)
