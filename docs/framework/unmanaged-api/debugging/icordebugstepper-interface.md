---
title: ICorDebugStepper 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper
helpviewer_keywords:
- ICorDebugStepper interface [.NET Framework debugging]
ms.assetid: ed8364eb-f01b-46f6-b5e3-5dda9cae2dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f83b9796bb692ce234a03c596387960bd879ebf3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763739"
---
# <a name="icordebugstepper-interface"></a>ICorDebugStepper 인터페이스
디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Deactivate 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md)|이 인해 `ICorDebugStepper` 받은 마지막 단계 명령을 취소 합니다.|  
|[IsActive 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-isactive-method.md)|나타내는 값을 가져옵니다 여부를이 `ICorDebugStepper` 현재 단계를 실행 합니다.|  
|[SetInterceptMask 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md)|한 단계씩 코드 형식을 지정 하는 CorDebugIntercept 값을 설정 합니다.|  
|[SetRangeIL 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md)|나타내는 값을 설정 하는지 여부를 호출 [icordebugstepper:: Steprange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) 네이티브 코드를 기준으로 또는 단계별로 되는 메서드의 MSIL (intermediate language) 코드를 Microsoft에 인수 값을 전달 합니다.|  
|[SetUnmappedStopMask 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md)|매핑되지 않은 코드 실행을 중지할의 형식을 지정 하는 CorDebugUnmappedStop 값을 설정 합니다.|  
|[Step 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md)|이 인해 `ICorDebugStepper` 단일 단계로 포함 스레드를 통해를 필요에 따라 스레드 내에서 호출 되는 함수를 통해 단일 단계를 계속 합니다.|  
|[StepOut 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-stepout-method.md)|이 인해 `ICorDebugStepper` 때 완료 하는 단일 단계로 포함 스레드를 통해 현재 프레임 컨트롤 프레임에 반환 호출 합니다.|  
|[StepRange 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)|이 인해 `ICorDebugStepper` 마지막 지정 된 범위를 벗어난 코드에 도달한 단일 단계로 포함 스레드를 통해 반환 하는 경우.|  
  
## <a name="remarks"></a>설명  
 `ICorDebugStepper` 인터페이스에는 다음 용도로 사용 됩니다.  
  
- 발급 한 단계 명령 및 해당 명령의 완료를 구분 하는 식별자로 작동 합니다.  
  
- 수행할 수 있는 모든 단계별 실행을 캡슐화 하는 중앙 인터페이스를 제공 합니다.  
  
- 중간 단계별 실행 작업을 취소 하는 방법을 제공 합니다.  
  
 스레드당 둘 이상의 스텝 퍼 있을 수 있습니다. 예를 들어, 함수, 프로시저 단위 실행 하는 동안 중단점에 도달할 수 있습니다 하 고 사용자는 해당 함수 내에서 새 단계별 실행 작업을 시작 하려고 합니다. 디버거가이 상황을 처리 하는 방법을 결정 됩니다. 디버거 원래 단계별 실행 작업을 취소 하거나 두 작업을 중첩 해야 합니다. `ICorDebugStepper` 인터페이스에서 모두 선택 항목을 지원 합니다.  
  
 스텝은 CLR (공용 언어 런타임)에서는 마샬링된 크로스 스레드 호출 하는 경우 스레드 간에 마이그레이션될 수 있습니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
