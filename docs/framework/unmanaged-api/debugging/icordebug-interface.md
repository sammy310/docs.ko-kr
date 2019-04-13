---
title: ICorDebug 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193232ce1006a9cf209db9330343386404948440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168287"
---
# <a name="icordebug-interface"></a>ICorDebug 인터페이스
공용 언어 런타임 (CLR) 환경에서 응용 프로그램을 디버그 하는 데 사용할 수 있는 방법을 제공 합니다.  
  
> [!NOTE]
>  Windows 95, Windows 98 또는 Windows ME 또는 x86이 아닌 플랫폼 (예: IA64, AMD64) (관리 / 네이티브 코드) 혼합 모드 디버깅이 지원 되지 않습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CanLaunchOrAttach 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|새 프로세스를 시작 하거나 지정된 된 프로세스에 연결 합니다. 현재 컴퓨터 및 런타임 구성의 컨텍스트 내에서 가능한 지 여부를 결정 합니다.|  
|[CreateProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|디버거의 제어 기본 스레드 및 프로세스를 시작합니다.|  
|[DebugActiveProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|기존 프로세스에 디버거를 연결 합니다.|  
|[EnumerateProcesses 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|디버그 중인 프로세스에 대 한 열거자를 가져옵니다.|  
|[GetProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|지정 된 프로세스 ID 사용 하 여 "ICorDebugProcess" 개체를 반환합니다.|  
|[Initialize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|초기화는 `ICorDebug` 개체입니다.|  
|[SetManagedHandler 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|관리 되는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.|  
|[SetUnmanagedHandler 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|관리 되지 않는 이벤트에 대 한 이벤트 처리기 개체를 지정합니다.|  
|[Terminate 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|종료는 `ICorDebug` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 `ICorDebug` 디버거 프로세스에 대 한 이벤트 처리 루프를 나타냅니다. 디버거 기다려야 합니다 [icordebugmanagedcallback:: Exitprocess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) 이 인터페이스를 해제 하기 전에 디버깅 중인 모든 프로세스에서 콜백 합니다.  
  
 `ICorDebug` 개체가 추가 관리 되는 디버깅을 제어 하는 초기 개체입니다. 이 개체를.NET Framework 버전 1.0 및 1.1에서는 `CoClass` 만든 com에서 개체 .NET framework 버전 2.0에서이 개체는 더 이상를 `CoClass` 개체입니다. 만들어야 합니다 [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) 버전 인식 하는 함수. 이 새 생성 함수 가져오기의 특정 구현에는 클라이언트를 사용 하면 `ICorDebug`, 디버깅 API의 특정 버전을 에뮬레이트합니다.  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
