---
title: ICLRDebugging::OpenVirtualProcess 메서드
ms.date: 03/30/2017
api_name:
- ICLRDebugging.OpenVirtualProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebugging::OpenVirtualProcess
helpviewer_keywords:
- OpenVirtualProcess method [.NET Framework debugging]
- ICLRDebugging::OpenVirtualProcess method [.NET Framework debugging]
ms.assetid: e8ab7c41-d508-4ed9-8a31-ead072b5a314
topic_type:
- apiref
ms.openlocfilehash: 1598130eb097655d3e83689956eb3614103eb573
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860368"
---
# <a name="iclrdebuggingopenvirtualprocess-method"></a>ICLRDebugging::OpenVirtualProcess 메서드
프로세스에 로드 된 CLR (공용 언어 런타임) 모듈에 해당 하는 ICorDebugProcess 인터페이스를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT OpenVirtualProcess(  
    [in] ULONG64 moduleBaseAddress,  
    [in] IUnknown * pDataTarget,  
    [in] ICLRDebuggingLibraryProvider * pLibraryProvider,  
    [in] CLR_DEBUGGING_VERSION * pMaxDebuggerSupportedVersion,  
    [in] REFIID riidProcess,  
    [out, iid_is(riidProcess)] IUnknown ** ppProcess,  
    [in, out] CLR_DEBUGGING_VERSION * pVersion,  
    [out] CLR_DEBUGGING_PROCESS_FLAGS * pdwFlags);  
```  
  
## <a name="parameters"></a>매개 변수  
 `moduleBaseAddress`  
 진행 대상 프로세스에 있는 모듈의 기본 주소입니다. 지정 된 모듈이 CLR 모듈이 아닌 경우 COR_E_NOT_CLR 반환 됩니다.  
  
 `pDataTarget`  
 진행 관리 되는 디버거가 프로세스 상태를 검사할 수 있도록 하는 데이터 대상 추상화입니다. 디버거는 [ICorDebugDataTarget](icordebugdatatarget-interface.md) 인터페이스를 구현 해야 합니다. 디버깅 중인 CLR이 컴퓨터에 로컬로 설치 되지 않은 시나리오를 지원 하려면 [ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) 인터페이스를 구현 해야 합니다.  
  
 `pLibraryProvider`  
 진행 버전별 디버깅 라이브러리를 요청 시 배치 하 고 로드할 수 있도록 하는 라이브러리 공급자 콜백 인터페이스입니다. 이 매개 변수는 또는 `ppProcess` `pFlags` 가이 아닌 `null`경우에만 필요 합니다.  
  
 `pMaxDebuggerSupportedVersion`  
 진행 이 디버거가 디버그할 수 있는 가장 높은 버전의 CLR입니다. 이 디버거를 지 원하는 최신 CLR 버전의 주 버전, 부 버전 및 빌드 버전을 지정 하 고 향후 현재 위치의 CLR 서비스 릴리스를 수용할 수 있도록 수정 번호를 65535으로 설정 해야 합니다.  
  
 `riidProcess`  
 진행 검색할 ICorDebugProcess 인터페이스의 ID입니다. 현재 유일 하 게 허용 되는 값은 IID_CORDEBUGPROCESS3, IID_CORDEBUGPROCESS2 및 IID_CORDEBUGPROCESS입니다.  
  
 `ppProcess`  
 제한이 로 `riidProcess`식별 되는 COM 인터페이스에 대 한 포인터입니다.  
  
 `pVersion`  
 [in, out] CLR의 버전입니다. 입력 시이 값은 일 `null`수 있습니다. 구조체의 `wStructVersion` 필드를 0 (영)으로 초기화 해야 하는 [CLR_DEBUGGING_VERSION](clr-debugging-version-structure.md) 구조를 가리킬 수도 있습니다.  
  
 출력 시 반환 `CLR_DEBUGGING_VERSION` 된 구조체는 CLR의 버전 정보로 채워집니다.  
  
 `pdwFlags`  
 제한이 지정 된 런타임에 대 한 정보 플래그입니다. 플래그에 대 한 설명은 [CLR_DEBUGGING_PROCESS_FLAGS](clr-debugging-process-flags-enumeration.md) 항목을 참조 하세요.  
  
## <a name="return-value"></a>Return Value  
 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|메서드가 완료되었습니다.|  
|E_POINTER|`pDataTarget`은 `null`입니다.|  
|CORDBG_E_LIBRARY_PROVIDER_ERROR|[ICLRDebuggingLibraryProvider](iclrdebugginglibraryprovider-interface.md) 콜백에서 오류를 반환 하거나 올바른 핸들을 제공 하지 않습니다.|  
|CORDBG_E_MISSING_DATA_TARGET_INTERFACE|`pDataTarget`는이 버전의 런타임에 필요한 데이터 대상 인터페이스를 구현 하지 않습니다.|  
|CORDBG_E_NOT_CLR|표시 된 모듈이 CLR 모듈이 아닙니다. 이 HRESULT는 메모리가 손상 되었거나, 모듈을 사용할 수 없거나, CLR 버전이 shim 버전 보다 이후 CLR 모듈을 검색할 수 없는 경우에도 반환 됩니다.|  
|CORDBG_E_UNSUPPORTED_DEBUGGING_MODEL|이 런타임 버전은이 디버깅 모델을 지원 하지 않습니다. 현재 디버깅 모델은 .NET Framework 4 이전 CLR 버전에서 지원 되지 않습니다. `pwszVersion` 출력 매개 변수는이 오류가 발생 한 후에도 올바른 값으로 설정 됩니다.|  
|CORDBG_E_UNSUPPORTED_FORWARD_COMPAT|CLR 버전이이 디버거가 지원 하기 위해 클레임 하는 버전 보다 큽니다. `pwszVersion` 출력 매개 변수는이 오류가 발생 한 후에도 올바른 값으로 설정 됩니다.|  
|E_NO_INTERFACE|인터페이스 `riidProcess` 를 사용할 수 없습니다.|  
|CORDBG_E_UNSUPPORTED_VERSION_STRUCT|`CLR_DEBUGGING_VERSION` 구조에에 대해 `wStructVersion`인식 되는 값이 없는 경우 지금은 허용 되는 값은 0입니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
