---
title: ICorDebugProcess::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
ms.openlocfilehash: c6def272ecc7bd2b6e946e2c9623f0b60587d317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128804"
---
# <a name="icordebugprocessgetthreadcontext-method"></a>ICorDebugProcess::GetThreadContext 메서드
이 프로세스의 지정 된 스레드에 대 한 컨텍스트를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadID`  
 진행 컨텍스트를 검색할 스레드의 ID입니다.  
  
 `contextSize`  
 [in] `context` 배열의 크기입니다.  
  
 `context`  
 [in, out] 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.  
  
 컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.  
  
## <a name="remarks"></a>주의  
 스레드가 실제로 해당 컨텍스트가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 `GetThreadContext` 메서드 대신이 메서드를 호출 해야 합니다. 이 메서드는 스레드가 네이티브 코드에 있는 경우에만 사용 해야 합니다. 관리 코드에서 스레드에 대해 [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) 를 사용 합니다.  
  
 반환 된 데이터는 현재 플랫폼에 대 한 컨텍스트 구조입니다. Win32 `GetThreadContext` 메서드와 마찬가지로 호출자는이 메서드를 호출 하기 전에 `context` 매개 변수를 초기화 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
