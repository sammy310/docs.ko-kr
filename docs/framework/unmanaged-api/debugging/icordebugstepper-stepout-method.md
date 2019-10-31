---
title: ICorDebugStepper::StepOut 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 6c1d7db8aacaf81d47abd4a9cd972b44f56a3bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137517"
---
# <a name="icordebugstepperstepout-method"></a>ICorDebugStepper::StepOut 메서드
이 ICorDebugStepper이 포함 하는 스레드를 한 단계씩 실행 하 고 현재 프레임에서 제어를 호출 프레임으로 반환할 때 완료 되도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>주의  
 현재 프레임에서 호출 프레임으로 정상적으로 반환 된 후 `StepOut` 작업이 완료 됩니다.  
  
 비관리 코드에서 `StepOut`가 호출 되 면 현재 프레임이 해당를 호출한 관리 코드로 반환 될 때 단계가 완료 됩니다.  
  
 .NET Framework 버전 2.0에서는 STOP_UNMANAGED 플래그가 설정 된 `StepOut`를 사용 하지 않습니다. ( [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) 를 사용 하 여 단계별 실행 플래그를 설정 합니다.) Interop 디버거는 네이티브 코드 자체를 프로시저 단위로 실행 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
