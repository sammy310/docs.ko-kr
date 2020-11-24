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
ms.openlocfilehash: 96e3a90bcb7700915bfd3618d7bae40c0ff64a75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678599"
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
  
## <a name="remarks"></a>설명  

 `InterceptCurrentException`메서드는 예외 콜백 ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) 또는 [ICorDebugManagedCallback2:: exception](icordebugmanagedcallback2-exception-method.md))과 연결 된 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)호출 사이에서 호출 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  

 **플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
