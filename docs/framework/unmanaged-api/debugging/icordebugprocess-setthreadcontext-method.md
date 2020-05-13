---
title: ICorDebugProcess::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: c9e403dc8cbb75a1e93c426a9e0b3a2083f1f10e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210464"
---
# <a name="icordebugprocesssetthreadcontext-method"></a>ICorDebugProcess::SetThreadContext 메서드
이 프로세스의 지정 된 스레드에 대 한 컨텍스트를 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a>매개 변수  
 `threadID`  
 진행 컨텍스트를 설정할 스레드의 ID입니다.  
  
 `contextSize`  
 [in] `context` 배열의 크기입니다.  
  
 `context`  
 진행 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.  
  
 컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `SetThreadContext`스레드가 실제로 해당 컨텍스트가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 함수 대신이 메서드를 호출 해야 합니다. 이 메서드는 스레드가 네이티브 코드에 있는 경우에만 사용 해야 합니다. 관리 코드에서 스레드에 대해 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 를 사용 합니다. OOB (대역 외) 디버그 이벤트 중에는 스레드의 컨텍스트를 수정할 필요가 없습니다.  
  
 전달 된 데이터는 현재 플랫폼에 대 한 컨텍스트 구조 여야 합니다.  
  
 이 메서드는 부적절 하 게 사용 되는 경우 런타임을 손상 시킬 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
