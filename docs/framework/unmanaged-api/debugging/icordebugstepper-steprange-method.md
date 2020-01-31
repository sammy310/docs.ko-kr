---
title: ICorDebugStepper::StepRange 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
ms.openlocfilehash: 21b8bf618e197372e301d5f56e7592c20710014d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791718"
---
# <a name="icordebugsteppersteprange-method"></a>ICorDebugStepper::StepRange 메서드
이 ICorDebugStepper는 포함 하는 스레드를 한 단계씩 실행 하 고 지정 된 범위를 벗어난 코드에 도달 하면를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `bStepIn`  
 진행 `true` 설정 하 여 스레드 내에서 호출 되는 함수를 한 단계씩 실행 합니다. 함수를 프로시저 단위로 실행 하려면 `false`로 설정 합니다.  
  
 `ranges`  
 진행 각각 범위를 지정 하는 COR_DEBUG_STEP_RANGE 구조체의 배열입니다.  
  
 `cRangeCount`  
 [in] `ranges` 배열의 크기입니다.  
  
## <a name="remarks"></a>주의  
 `StepRange` 메서드는 지정 된 범위를 벗어난 코드에 도달할 때까지 완료 되지 않는다는 점을 제외 하 고는 [ICorDebugStepper:: Step](icordebugstepper-step-method.md) 메서드와 유사 하 게 작동 합니다.  
  
 이는 한 번에 하나의 명령을 실행 하는 것 보다 효율적일 수 있습니다. 범위는 스텝 퍼 프레임의 시작 부분에서 오프셋 쌍의 목록으로 지정 됩니다.  
  
 범위는 메서드의 MSIL (Microsoft 중간 언어) 코드를 기준으로 합니다. `false`를 사용 하 여 [ICorDebugStepper:: SetRangeIL](icordebugstepper-setrangeil-method.md) 를 호출 하 여 메서드의 네이티브 코드를 기준으로 범위를 만듭니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
