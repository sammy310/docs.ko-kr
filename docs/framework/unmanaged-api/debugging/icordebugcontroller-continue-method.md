---
title: ICorDebugController::Continue 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eacffe5769bc77ab626f6adbc99db1137da565f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146811"
---
# <a name="icordebugcontrollercontinue-method"></a>ICorDebugController::Continue 메서드
호출한 후 관리 되는 스레드의 실행을 다시 시작 [Stop 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `fIsOutOfBand`  
 [in] 로 `true` 대역의 이벤트;에서 계속 실행 하는 경우이 고, 그렇지로 `false`합니다.  
  
## <a name="remarks"></a>설명  
 `Continue` 호출한 후 프로세스를 계속 합니다 `ICorDebugController::Stop` 메서드.  
  
 혼합 모드 디버깅을 수행 하는 경우 호출 하지 마십시오 `Continue` Win32에서 이벤트 스레드 대역의 이벤트에서 계속 실행 하는 경우가 아니면 합니다.  
  
 *대역 내 이벤트* 는 관리 되는 이벤트 또는 디버거는 프로세스의 관리 되는 상태와의 상호 작용을 지 원하는 일반 관리 되지 않는 이벤트입니다. 이 경우 디버거가 수신 합니다 [icordebugunmanagedcallback:: Debugevent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) 사용 하 여 콜백을 해당 `fOutOfBand` 매개 변수 설정 `false`합니다.  
  
 *대역의 이벤트* 는 프로세스의 관리 되는 상태와의 상호 작용 가능 하지 않은 이벤트로 인해 프로세스를 중지 하는 동안 관리 되지 않는 이벤트입니다. 이 경우 디버거가 수신 합니다 `ICorDebugUnmanagedCallback::DebugEvent` 사용 하 여 콜백을 해당 `fOutOfBand` 매개 변수 설정 `true`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료
