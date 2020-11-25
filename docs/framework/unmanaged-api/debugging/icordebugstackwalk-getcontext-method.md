---
title: ICorDebugStackWalk::GetContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 927f2077b4bb71177c24816774d06643ebdaa922
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711964"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext 메서드

[ICorDebugStackWalk](icordebugstackwalk-interface.md) 개체의 현재 프레임에 대 한 컨텍스트를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>매개 변수  

 `contextFlags`  
 진행 WinNT에 정의 된 컨텍스트 버퍼의 요청 된 콘텐츠를 나타내는 플래그입니다.  
  
 `contextBufSize`  
 진행 할당 된 컨텍스트 버퍼 크기입니다.  
  
 `contextSize`  
 제한이 컨텍스트의 실제 크기입니다. 이 값은 컨텍스트 버퍼의 크기 보다 작거나 같아야 합니다.  
  
 `contextBuf`  
 제한이 컨텍스트 버퍼입니다.  
  
## <a name="return-value"></a>반환 값  

 이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.  
  
|HRESULT|설명|  
|-------------|-----------------|  
|S_OK|현재 프레임에 대 한 컨텍스트가 성공적으로 반환 되었습니다.|  
|E_FAIL|컨텍스트를 반환할 수 없습니다.|  
|HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT 버퍼)|컨텍스트 버퍼가 너무 작습니다.|  
|CORDBG_E_PAST_END_OF_STACK|프레임 포인터가 이미 스택의 끝에 있습니다. 따라서 추가 프레임에는 액세스할 수 없습니다.|  
  
## <a name="exceptions"></a>예외  
  
## <a name="remarks"></a>설명  

 해제 하면 비휘발성 레지스터와 같이 레지스터의 하위 집합만 복원 되므로 컨텍스트는 호출 시 등록 상태와 정확 하 게 일치 하지 않을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참조

- [디버깅 인터페이스](debugging-interfaces.md)
- [디버깅](index.md)
