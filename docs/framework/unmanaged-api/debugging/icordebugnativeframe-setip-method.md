---
title: ICorDebugNativeFrame::SetIP 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
ms.openlocfilehash: 1d978cab0817af68356d95d635f8d2bfa3fd546a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096746"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP 메서드
네이티브 코드에서 지정 된 오프셋 위치에 대 한 명령 포인터를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `nOffset`  
 진행 네이티브 코드의 오프셋 위치입니다.  
  
## <a name="remarks"></a>주의  
 `SetIP`를 호출 하면 현재 스레드에 대 한 모든 프레임과 체인이 즉시 무효화 됩니다. `SetIP`를 호출한 후 디버거에 프레임 정보가 필요한 경우 새 스택 추적을 수행 해야 합니다.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 는 스택 프레임을 유효한 상태로 유지 하려고 합니다. 그러나 런타임이 중요 한 것 처럼 프레임이 유효한 상태에 있더라도 지역 변수를 초기화 하지 않는 등의 문제가 있을 수 있습니다. 호출자는 실행 중인 프로그램의 일관성을 지 게 할 책임이 있습니다.  
  
 64 비트 플랫폼에서 명령 포인터는 `catch` 또는 `finally` 블록 밖으로 이동할 수 없습니다. `SetIP`를 호출 하 여 64 비트 플랫폼에서 이러한 이동을 수행 하는 경우 실패를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참조
