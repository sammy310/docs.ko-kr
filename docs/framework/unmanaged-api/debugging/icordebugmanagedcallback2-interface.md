---
title: ICorDebugManagedCallback2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1ecfea208f87f53f15fcc4cdafb58341c293e43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096090"
---
# <a name="icordebugmanagedcallback2-interface"></a>ICorDebugManagedCallback2 인터페이스
디버거 예외 처리 및 MDA(관리 디버깅 도우미)를 지원하기 위한 메서드를 제공합니다. `ICorDebugManagedCallback2` 논리적으로 확장 되는 [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) 인터페이스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[ChangeConnection 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|지정 된 연결과 관련 된 작업 집합이 변경 된 디버거에 알립니다.|  
|[CreateConnection 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|새 연결을 만들어졌는지 디버거에 알립니다.|  
|[DestroyConnection 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|지정한 연결 종료 되었다는 디버거에 알립니다.|  
|[Exception 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|예외 처리기 검색을 시작한 디버거에 알립니다.|  
|[ExceptionUnwind 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|예외 해제 프로세스 중에 상태 알림을 제공합니다.|  
|[FunctionRemapComplete 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|편집 된 함수의 새 버전으로 코드 실행이 전환는 디버거에 알립니다.|  
|[FunctionRemapOpportunity 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|코드 실행 이전 버전의 편집된 된 함수에서 시퀀스 위치에 도달 했습니다 디버거에 알립니다.|  
|[MDANotification 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|코드 실행 관리 디버깅 도우미 (MDA) 메시지를 발생 하는 알림을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `ICorDebugManagedCallback2` 인터페이스를 확장 합니다 `ICorDebugManagedCallback` 는.NET Framework 버전 2.0에에서 도입 된 새 디버그 이벤트를 처리 하는 인터페이스입니다.  
  
 디버거를 구현 해야 `ICorDebugManagedCallback2` .NET Framework 2.0 응용 프로그램을 디버깅 하는 경우. 인스턴스의 `ICorDebugManagedCallback` 나 `ICorDebugManagedCallback2` 콜백 개체로 전달 됩니다 [icordebug:: Setmanagedhandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [관리 디버깅 도우미를 사용하여 오류 진단](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
