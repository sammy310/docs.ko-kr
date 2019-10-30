---
title: ICorDebugThread::GetDebugState 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetDebugState
helpviewer_keywords:
- GetDebugState method [.NET Framework debugging]
- ICorDebugThread::GetDebugState method [.NET Framework debugging]
ms.assetid: 9be27b0c-1d99-4722-b0d4-40cf6753ce5c
topic_type:
- apiref
ms.openlocfilehash: f054f8f2bd7c322e722a1e17290ba6fbad9e37b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133519"
---
# <a name="icordebugthreadgetdebugstate-method"></a>ICorDebugThread::GetDebugState 메서드
이 ICorDebugThread 개체의 현재 디버그 상태를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetDebugState (  
    [out] CorDebugThreadState   *pState  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pState`  
 제한이 이 스레드의 현재 디버그 상태를 설명 하는 CorDebugThreadState 열거형 값의 비트 조합에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 프로세스가 현재 중지 된 경우이 스레드의 실제 현재 상태가 아닌 프로세스가 계속 되는 경우이 스레드에 대해 존재 하는 디버그 상태를 `pState` 나타냅니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
