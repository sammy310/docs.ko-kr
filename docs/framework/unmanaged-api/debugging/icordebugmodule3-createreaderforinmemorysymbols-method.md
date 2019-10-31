---
title: ICorDebugModule3::CreateReaderForInMemorySymbols 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137313"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a>ICorDebugModule3::CreateReaderForInMemorySymbols 메서드
동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a>매개 변수  
 riid  
 진행 반환할 COM 인터페이스의 IID입니다. 일반적으로이 인터페이스는 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)입니다.  
  
 ppObj  
 제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 S_OK  
 판독기를 만들었습니다.  
  
 CORDBG_E_MODULE_LOADED_FROM_DISK  
 모듈이 메모리 내 또는 동적 모듈이 아닙니다.  
  
 CORDBG_E_SYMBOLS_NOT_AVAILABLE  
 응용 프로그램에서 기호를 제공 하지 않았거나 아직 사용할 수 없습니다.  
  
 E_FAIL(또는 다른 E_ 반환 코드)  
 판독기를 만들 수 없습니다.  
  
## <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 메모리 내 (동적이 아닌) 모듈에 대 한 기호 판독기 개체를 만들 수도 있습니다. 단, 기호를 처음 사용할 수 있는 경우에만 ( [UpdateModuleSymbols 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백에서 표시).  
  
 이 메서드는 호출 될 때마다 새 판독기 인스턴스를 반환 합니다 (예 [: Ccomptrbase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)). 따라서 디버거는 기본 데이터가 변경 되었을 수 있는 경우 (즉, [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백이 수신 될 때)에만 결과를 캐시 하 고 새 인스턴스를 요청 해야 합니다.  
  
 동적 모듈에는 첫 번째 형식이 로드 될 때까지 사용할 수 있는 기호가 없습니다 ( [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백에 표시 됨).  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>참조

- [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
