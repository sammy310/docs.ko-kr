---
title: ICorDebugModule 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule
helpviewer_keywords:
- ICorDebugModule interface [.NET Framework debugging]
ms.assetid: 32e4d6fa-e5a3-413e-9166-d5e2871d3114
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 257011562a9ea687ef70b842c6d47219283e158e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225640"
---
# <a name="icordebugmodule-interface"></a>ICorDebugModule 인터페이스

실행 파일 또는 동적 연결 라이브러리 (DLL)는 공용 언어 런타임 (CLR) 모듈을 나타냅니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[CreateBreakpoint 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-createbreakpoint-method.md)|구현되지 않았습니다.|  
|[EnableClassLoadCallbacks 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enableclassloadcallbacks-method.md)|결정 하는지 여부를 [icordebugmanagedcallback:: Loadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 하 고 [icordebugmanagedcallback:: Unloadclass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) 이 모듈에 대 한 콜백을 호출 됩니다.|  
|[EnableJITDebugging 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-enablejitdebugging-method.md)|Just-in-time (JIT) 컴파일러가이 모듈 내에서 메서드에 대 한 디버깅 정보를 유지할지 여부를 결정 합니다.|  
|[GetAssembly 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getassembly-method.md)|이 모듈에 대 한 포함 하는 어셈블리를 가져옵니다.|  
|[GetBaseAddress 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getbaseaddress-method.md)|모듈의 기본 주소를 가져옵니다.|  
|[GetClassFromToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getclassfromtoken-method.md)|ICorDebugClass는 메타 데이터에서 가져옵니다.|  
|[GetEditAndContinueSnapshot 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-geteditandcontinuesnapshot-method.md)|더 이상 사용되지 않습니다.|  
|[GetFunctionFromRVA 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromrva-method.md)|구현되지 않았습니다.|  
|[GetFunctionFromToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getfunctionfromtoken-method.md)|메타 데이터 토큰이 지정 된 함수를 가져옵니다.|  
|[GetGlobalVariableValue 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getglobalvariablevalue-method.md)|지정한 전역 변수에 대 한 값 개체를 가져옵니다.|  
|[GetMetaDataInterface 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getmetadatainterface-method.md)|모듈에 대 한 메타 데이터를 검사 하는 메타 데이터 인터페이스 포인터를 가져옵니다.|  
|[GetName 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getname-method.md)|모듈의 파일 이름을 가져옵니다.|  
|[GetProcess 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getprocess-method.md)|이 모듈에 대 한 포함 하는 프로세스를 가져옵니다.|  
|[GetSize 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-getsize-method.md)|모듈의 크기를 바이트 단위로 가져옵니다.|  
|[GetToken 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-gettoken-method.md)|이 모듈에 대 한 테이블 항목에 대 한 토큰을 가져옵니다.|  
|[IsDynamic 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isdynamic-method.md)|동적 모듈 인지 여부를 나타냅니다.|  
|[IsInMemory 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-isinmemory-method.md)|메모리에만이 모듈이 있는지 여부를 나타냅니다.|  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고자료

- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
