---
title: ICorDebugThread2::InterceptCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: c25a03ef5bbba18da31787c911f83a1348badd4b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791446"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a>ICorDebugThread2::InterceptCurrentException 메서드
디버거가이 스레드의 현재 예외를 가로챌 수 있도록 허용 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a>매개 변수  
 `pFrame`  
 진행 활성 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.  
  
## <a name="remarks"></a>주의  
 예외 콜백 ([ICorDebugManagedCallback:: exception](icordebugmanagedcallback-exception-method.md) 또는 [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md))과 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)에 대 한 연결 된 호출 사이에 `InterceptCurrentException` 메서드를 호출할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
