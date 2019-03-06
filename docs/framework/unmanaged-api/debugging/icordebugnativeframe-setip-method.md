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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33a4315d8908906e9ae1511aa9501969752d4af6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484864"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP 메서드
네이티브 코드에서 지정된 된 오프셋된 위치에 명령 포인터를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `nOffset`  
 [in] 네이티브 코드 오프셋된 위치입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 호출 `SetIP` 즉시 모든 프레임을 현재 스레드에 대 한 체인을 무효화 합니다. 디버거를 호출한 후 프레임 정보가 필요한 경우 `SetIP`, 새 스택 추적을 수행 해야 합니다.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 스택 프레임을 유효한 상태로 유지 하려고 합니다. 그러나 경우에 프레임 유효한 상태, 런타임에 관련해 서, 초기화 되지 않은 로컬 변수 등의 문제가 발생할 수 있습니다. 호출자는 실행 중인 프로그램의 일관성이 유지 되도록 하는 일을 담당 합니다.  
  
 64 비트 플랫폼에서 명령 포인터를 이동할 수 없습니다 개를 `catch` 또는 `finally` 블록입니다. 경우 `SetIP` 라고 하는 64 비트 플랫폼에서 이러한 이동 되도록 실패를 나타내는 HRESULT를 반환 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

