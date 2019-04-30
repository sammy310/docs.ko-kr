---
title: ICorDebugEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989068"
---
# <a name="icordebugenum-interface"></a>ICorDebugEnum 인터페이스

디버깅 응용 프로그램에서 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|이 복사본을 만들고 `ICorDebugEnum` 개체입니다.|  
|[GetCount 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|열거형의 항목 수를 가져옵니다.|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|열거형의 시작 부분에 커서를 이동합니다.|  
|[Skip 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|열거형에서 항목의 지정된 된 수 만큼 앞으로 커서를 이동합니다.|  
  
## <a name="remarks"></a>설명  
 파생 되는 다음 열거자 `ICorDebugEnum`:  
  
- "ICorDebugAppDomainEnum"  
  
- "ICorDebugAssemblyEnum"  
  
- [ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- "ICorDebugBreakpointEnum"  
  
- "ICorDebugChainEnum"  
  
- "ICorDebugCodeEnum"  
  
- "ICorDebugErrorInfoEnum"  
  
- [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- "ICorDebugFrameEnum"  
  
- [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- "ICorDebugModuleEnum"  
  
- "ICorDebugObjectEnum"  
  
- "ICorDebugProcessEnum"  
  
- "ICorDebugStepperEnum"  
  
- "ICorDebugThreadEnum"  
  
- "ICorDebugTypeEnum"  
  
- "ICorDebugValueEnum"  
  
- [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
