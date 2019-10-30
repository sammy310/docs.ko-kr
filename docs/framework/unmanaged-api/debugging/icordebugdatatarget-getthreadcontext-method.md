---
title: ICorDebugDataTarget::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122034"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a>ICorDebugDataTarget::GetThreadContext 메서드
지정 된 스레드에 대 한 현재 스레드 컨텍스트를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a>매개 변수  
 `dwThreadID`  
 진행 컨텍스트를 검색할 스레드의 식별자입니다. 식별자는 운영 체제에 의해 정의 됩니다.  
  
 `contextFlags`  
 진행 읽을 컨텍스트의 부분을 나타내는 플랫폼 종속 플래그의 비트 조합입니다.  
  
 `contextSize`  
 [in] `pContext`의 크기입니다.  
  
 `pContext`  
 제한이 스레드 컨텍스트가 저장 될 버퍼입니다.  
  
## <a name="remarks"></a>주의  
 Windows 플랫폼에서 `pContext`은 [ICorDebugDataTarget:: GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드로 지정 된 컴퓨터 유형에 적절 한 `CONTEXT` 구조 (winnt.exe에 정의 되어 있어야 함) 여야 합니다. `contextFlags`은 `CONTEXT` 구조체의 `ContextFlags` 필드와 값이 같아야 합니다. `CONTEXT` 구조는 프로세서 전용입니다. 자세한 내용은 Winnt.sif 파일을 참조 하세요.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [ICorDebugDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
